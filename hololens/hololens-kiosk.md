---
title: Nastavení HoloLens jako beziosku
description: Zjistěte, jak nastavit a používat konfiguraci veřejného terminálů k uzamčení aplikací na HoloLens zařízeních.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/24/2021
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e856ac74e959743e8d05ea6acf583700a6450373
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428022"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Nastavení HoloLens jako beziosku

## <a name="what-is-kiosk-mode"></a>Co je bezobrazovový režim?

Režim veřejného terminálů je funkce, ve které můžete řídit, které aplikace se zobrazí v nabídce Start, když se uživatel přihlásí k HoloLens. Existují 2 podporované scénáře:

1. **Beznaioskový režim** s jednou aplikací – nezobrazí se žádná nabídka Start a při přihlášení uživatele se automaticky spustí jedna aplikace. <br> *Příklad použití:* Zařízení, na které běží jenom aplikace Průvodci Dynamics 365.
2. **Beznaioskový režim** s více aplikacemi – nabídka Start jenom aplikace, které byly zadány v konfiguraci veřejného terminálů, když se uživatel přihlásí. Aplikace se může v případě potřeby automaticky spustit. <br> *Příklad použití:* Zařízení, které zobrazuje jenom aplikaci pro Store, Centrum Feedback a Nastavení v nabídce Start.

    <img alt="Multi app kiosk example" src=".\images\multi-app-kiosk.jpg" width="411" height="500" />

## <a name="description-of-kiosk-mode-experience-when-a-user-signs-in"></a>Popis prostředí beznaiosku při přihlášení uživatele

Následující tabulka uvádí funkce v různých režimech veřejného terminálů.

| &nbsp; |Nabídka Start |Nabídka Rychlé akce |Kamera a video |Miracast |Cortana |Integrované hlasové příkazy |
| --- | --- | --- | --- | --- | --- | --- |
|Beziosk s jednou aplikací |Zakázáno |Zakázáno |Zakázáno |Zakázáno   |Zakázáno |Povoleno* |
|Beziosk s více aplikacemi |Povoleno |Povoleno*  |K dispozici*  |K dispozici* |K dispozici*   |Povoleno*  |

\*Další informace o tom, jak povolit zakázané funkce nebo jak hlasové příkazy komunikují se zakázanými funkcemi a Cortana najdete [HoloLens AUMID pro aplikace.](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids)

## <a name="key-general-considerations-before-configuring-kiosk-mode"></a>Klíčové obecné aspekty před konfigurací bezobrazovkového režimu

1. Určení druhu uživatelského účtu, který se přihlašuje k HoloLens ve vašem prostředí – HoloLens podporuje účty Azure Active Directory (AAD), účty Microsoft (MSA) a místní účty. Kromě toho se podporují také dočasně vytvořené účty nazývané hosté nebo návštěvníci (pouze pro zařízení, která se připojují k AAD). Další informace najdete [v části Správa identity uživatele](hololens-identity.md)a přihlašování pro HoloLens .
2. Určete cíle prostředí beznarového režimu – jestli se jedná o každého uživatele, jednoho uživatele, určité uživatele nebo uživatele, kteří jsou členy skupin AAD atd.
3. V případě bezobrazovkového režimu s více aplikacemi určete aplikace, které se zobrazí v nabídce Start. Pro každou aplikaci bude potřeba JEJÍ [ID AUMID (Application User Model ID).](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids)
4. Zjistěte, jestli se na server HoloLens přes zřizovací balíčky modulu runtime nebo server Mobile Správa zařízení (MDM).

## <a name="security-considerations"></a>Důležité informace o zabezpečení

Bezobrazovový režim by se neměl považovat za metodu zabezpečení, ale jako způsob řízení prostředí pro spuštění při přihlašování uživatelů. Prostředí bezobrazovkového režimu můžete kombinovat s níže uvedenými možnostmi, pokud existují specifické požadavky související se zabezpečením:

- Pokud Nastavení aplikace nakonfigurovaná tak, aby se v beznarovém režimu a chcete řídit, které stránky se v aplikaci Nastavení mají zobrazit, přečtěte si o zobrazení [Nastavení viditelnosti.](settings-uri-list.md)
- Pokud chcete řídit přístup k určitým hardwarovým funkcím, například fotoaparátu, Bluetooth atd. u určitých aplikací atd., přečtěte si informace v tématu Zásady v csP pro zásady podporované poskytovatelem cloudových služeb [HoloLens 2 – Windows Client Management](/windows/client-management/mdm/policies-in-policy-csp-supported-by-hololens2). Nápady najdete v [našich běžných omezeních](hololens-common-device-restrictions.md) zařízení.
- Bezobrazovový režim neblokuje aplikacím (nakonfigurované jako součást prostředí veřejného terminálů) spouštění jiných aplikací. Pokud chcete úplně zablokovat spouštění určitých aplikací nebo procesů v HoloLens, přečtěte si část Použití řízení aplikací Windows Defender na zařízeních se systémem [HoloLens 2 v Microsoft Intune – Azure.](/mem/intune/configuration/custom-profile-hololens)

## <a name="key-technical-considerations-for-kiosk-mode-for-hololens"></a>Klíčové technické aspekty bezobrazovkového režimu pro HoloLens

Platí pouze v případě, že plánujete sami používat zřizovací balíčky modulu runtime nebo ručně vytvářet konfigurace veřejného terminálu. Konfigurace bezobrazovkového režimu používá hierarchickou strukturu založenou na XML:

- Přiřazený přístupový profil definuje, které aplikace se v beznaiosku zobrazují v nabídce Start. Můžete definovat více profilů ve stejné struktuře XML, na které lze odkazovat později.
- Konfigurace přiřazeného přístupu odkazuje na profil a cílové uživatele tohoto profilu, například konkrétního uživatele, skupinu AAD nebo návštěvníka atd. V závislosti na složitosti scénářů použití můžete definovat více konfigurací ve stejné struktuře XML (viz část podporované scénáře níže).
- Další informace najdete v tématu [AssignedAccess CSP](/windows/client-management/mdm/assignedaccess-csp).

## <a name="supported-scenarios-for-kiosk-mode-based-on-identity-type"></a>Podporované scénáře pro beznaioskový režim na základě typu identity

Příklady [založené na vašem](hololens-kiosk-reference.md#kiosk-xml-code-samples) scénáři najdete na referenčních odkazech a před vložením kopírování podle potřeby aktualizujte.

> [!NOTE]
> XML používejte jenom v případě, že k vytvoření konfigurace veřejného terminálu nepou3/4íte uživatelské rozhraní Intune.

### <a name="for-users-who-sign-in-as-either-local-account-or-msa"></a>Pro uživatele, kteří se přihlásí jako místní účet nebo msa

| **Požadované prostředí veřejného terminálu** | **Doporučená konfigurace veřejného terminálu** | **Způsoby konfigurace**  | **Poznámky** |
| --- | --- | --- | --- |
| Každý uživatel, který se přihlásí, získá prostředí veřejného terminálu. | [Konfigurace více profilů globálního přiřazeného přístupu aplikace](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune vlastní šablony](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Zřizování za běhu – Více aplikací](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Globální přiřazený přístup vyžaduje [20H2 a novější sestavení.](hololens-release-notes.md#windows-holographic-version-20h2) |
| Konkrétní uživatel, který se přihlásí, získá prostředí veřejného terminálu.  | [Nakonfigurujte jeden nebo více přístupových profilů přiřazených aplikací (podle potřeby) a zadejte jméno konkrétního uživatele.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account) | [Podporované možnosti najdete níže.](#steps-in-configuring-kiosk-mode-for-hololens) | V případě beznarového režimu s jednou aplikací se v místním uživatelském účtu nebo účtu MSA podporuje HoloLens. <br> Pro režim veřejného terminálů s více aplikacemi se v tomto režimu podporuje pouze účet MSA nebo účet AAD HoloLens. |

### <a name="for-users-who-sign-in-as-aad-account"></a>Pro uživatele, kteří se přihlásí jako účet AAD

| **Požadované prostředí veřejného terminálu** | **Doporučená konfigurace veřejného terminálu** | **Způsoby konfigurace** | **Poznámky** |
| --- | --- | --- | --- |
| Každý uživatel, který se přihlásí, získá prostředí veřejného terminálu. | [Konfigurace více profilů globálního přiřazeného přístupu aplikace](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune vlastní šablony](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Zřizování za běhu – Více aplikací](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Globální přiřazený přístup vyžaduje [20H2 a novější sestavení.](hololens-release-notes.md#windows-holographic-version-20h2) |
| Každý uživatel, který se přihlásí, získá prostředí veřejného terminálu s výjimkou určitých uživatelů. | [Nakonfigurujte více profilů globálního přiřazeného přístupu aplikace vyloučením určitých uživatelů (kteří musí být vlastníky zařízení).](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile-excluding-device-owners) | • [Microsoft Intune vlastní šablony](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Zřizování za běhu – Více aplikací](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Globální přiřazený přístup vyžaduje [20H2 a novější sestavení.](hololens-release-notes.md#windows-holographic-version-20h2) |
| Každý uživatel AAD získá samostatné prostředí veřejného terminálů specifické pro tohoto uživatele. | [Nakonfigurujte konfiguraci přiřazeného přístupu pro každého uživatele, který zadá název svého účtu AAD.](hololens-kiosk-reference.md#multiple-app-assigned-access-profiles-for-two-aad-users-or-more) | • [Microsoft Intune vlastní šablony](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Zřizování za běhu – Více aplikací](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | &nbsp; |
| Uživatelé v různých skupinách AAD mají kiosk režim, který je jenom pro jejich skupinu. | [Nakonfigurujte konfiguraci přiřazeného přístupu pro každou požadovanou skupinu AAD.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-two-aad-groups-or-more) | • [Microsoft Intune vlastní šablony](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Zřizování za běhu – Více aplikací](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | • Když se uživatel přihlásí a HoloLens je připojený k internetu, pokud se u tohoto uživatele shledá, že je členem skupiny AAD, pro kterou existuje konfigurace veřejného terminálu, uživatel se dostane do prostředí veřejného terminálu pro skupinu AAD. <br> • Pokud při přihlašování uživatele není k dispozici žádný internet, pak se HoloLens [režimu selhání.](#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode) <br> • Pokud není zaručena dostupnost internetu, když se uživatel přihlásí a je potřeba použít kiosk založený na skupině AAD, zvažte použití [zásady AADGroupMembershipCacheValidityInDays.](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk) <br> • Pro optimální prostředí se skupinami AAD během přihlašování doporučujeme použít [zásady AADGroupMembershipCacheValidityInDayspolicy.](/hololens/hololens-release-notes#cache-azure-ad-group-membership-for-offline-kiosk) |
| Uživatelé, kteří potřebují používat HoloLens k dočasným účelům, mají k dispozici prostředí veřejného terminálu. | [Konfigurace přiřazeného přístupu pro návštěvníky](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-visitors) | • [Microsoft Intune vlastní šablony](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Zřizování modulu runtime – Jedna aplikace](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens) | • Dočasný uživatelský účet se automaticky vytvoří HoloLens přihlášení a při odhlášení dočasného uživatele se odebere. <br> • Zvažte povolení [zásad automatického přihlášení návštěvníka.](#how-can-visitor-accounts-automatically-logon-to-kiosk-experience) |

## <a name="steps-in-configuring-kiosk-mode-for-hololens"></a>Postup konfigurace bezobrazovkového režimu pro HoloLens

Konfigurace veřejného terminálů je možné vytvořit a použít následujícími způsoby:

1. S uživatelským rozhraním serveru MDM, například šablonami veřejného terminálů Intune nebo vlastními konfiguracemi OMA-URI, které se pak vzdáleně použijí na HoloLens.
2. Se zřizovacími balíčky modulu runtime, které se pak přímo aplikují na HoloLens.

Tady jsou následující způsoby konfigurace. Vyberte kartu odpovídající procesu, který chcete použít.

1. [Microsoft Intune veřejného terminálu s jednou aplikací](hololens-kiosk.md?tabs=uisak#steps-in-configuring-kiosk-mode-for-hololens)
2. [Microsoft Intune veřejného terminálu s více aplikacemi](hololens-kiosk.md?tabs=uimak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Microsoft Intune vlastní šablony](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens)
1. [Zřizování za běhu – Více aplikací](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Zřizování za běhu – Jedna aplikace](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens)

[!INCLUDE[](includes/kiosk-configure-steps.md)]

## <a name="frequently-asked-questions"></a>Nejčastější dotazy

### <a name="how-can-visitor-accounts-automatically-logon-to-kiosk-experience"></a>Jak se mohou účty návštěvníků automaticky přihlásit k prostředí veřejného terminálů?

V [buildech Windows Holographic verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1) a novější:

- Konfigurace AAD i bez přidání podporují automatické protokolování účtů návštěvníka pro režim veřejného terminálu.

[!INCLUDE[](includes/kiosk-autologin.md)]

### <a name="is-kiosk-experience-supported-on-hololens-1st-gen"></a>Je prostředí veřejného terminálu podporované HoloLens (1. generace)?

Bezobrazovový režim je dostupný jenom v případě, že zařízení Windows Holographic for Business. Všechna HoloLens 2 se dodá s Windows Holographic for Business a nejsou k dispozici žádné jiné edice. Každé HoloLens 2 zařízení může bez spuštění spustit bezioskový režim.

HoloLens (1. generace) je potřeba upgradovat jak z hlediska sestavení operačního systému, tak edice operačního systému. Tady jsou další informace o aktualizaci HoloLens (1. generace) [na Windows Holographic for Business](hololens1-upgrade-enterprise.md) edici. Pokud chcete aktualizovat zařízení HoloLens (1. generace), aby bylo v beznarovém režimu, musíte nejdřív zajistit, aby na zařízení běží Windows 10, verze 1803 nebo novější. Pokud jste k obnovení zařízení HoloLens (1. generace) použili nástroj Windows Device Recovery Tool do výchozího sestavení, nebo pokud jste nainstalovali nejnovější aktualizace, je zařízení připravené ke konfiguraci.

### <a name="how-to-use-device-portal-to-configure-kiosk-in-non-production-environments"></a>Jak používat portál zařízení ke konfiguraci veřejného terminálů v neprodukcích prostředí?

Nastavte HoloLens [zařízení tak, aby Windows Portál zařízení.](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) The Portál zařízení is a web server on your HoloLens that you can connect to from a web browser on your PC.

 > [!CAUTION]
 > Když nastavíte, HoloLens používat Portál zařízení, musíte na zařízení povolit vývojářský režim. Vývojářský režim na zařízení, které Windows Holographic for Business umožňuje zkušební načtení aplikací. Toto nastavení ale vytváří riziko, že uživatel může instalovat aplikace, které nejsou certifikované Microsoft Store. Správci můžou blokovat možnost povolit režim pro vývojáře pomocí nastavení **ApplicationManagement/AllowDeveloper Unlock** v [csP zásad.](/windows/client-management/mdm/policy-configuration-service-provider) [Přečtěte si další informace o režimu pro vývojáře.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)

Bezobrazovový režim se může nastavit přes REST API služby Portál zařízení tak, že se pomocí POST nastaví /api/holographic/kioskmode/settings s jedním povinným parametrem řetězce dotazu ("kioskModeEnabled" s hodnotou "true" nebo "false") a jedním volitelným parametrem ("startupApp" s hodnotou názvu balíčku). Mějte na paměti, Portál zařízení je určená pouze pro vývojáře a neměla by být povolena na zařízeních, která nejsou vývojáři. Změny REST API v budoucích aktualizacích a vydáních se měňte.

## <a name="troubleshooting"></a>Řešení potíží

### <a name="issue---no-apps-are-shown-in-start-menu-in-kiosk-mode"></a>Problém – V nabídce Start v bezobrazovkovém režimu se nezobrazí žádné aplikace

**Příznaky**

Pokud při použití bezobrazovkovém režimu dochází k selháním, zobrazí se následující chování:

- Před Windows Holographic se ve verzi 20H2 – HoloLens zobrazí všechny aplikace v nabídka Start.
- Windows Holographic verze 20H2 – pokud má zařízení konfiguraci veřejného terminálů, což je kombinace přístupu přiřazeného globálním i přiřazeným členem skupiny AAD. Pokud se určení členství ve skupině AAD nezdaří, uživateli se zobrazí nabídka "nic se nezobrazí v nabídce Start".

    ![Obrázek toho, jak vypadá bezobrazovový režim, když selže](images/hololens-kiosk-failure-behavior.png )

- Počínaje [Windows Holographic verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1)hledá bezobrazovkové režim před zobrazením prázdné nabídky Start možnost Globální přiřazený přístup. Prostředí veřejného terminálů se vrátí ke globální konfiguraci veřejného terminálů (pokud je k dispozici), pokud dojde k selhání v režimu veřejného terminálu skupiny AAD.

**Postup při řešení potíží**

- Ověřte, že je správně zadané AUMID aplikace a že neobsahuje verze. Příklady najdete [HoloLens aUMID](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) pro aplikace doručené pošty.
- Ujistěte se, že je na zařízení pro tohoto uživatele nainstalovaná aplikace.
- Pokud je konfigurace veřejného terminálu založená na skupinách AAD, ujistěte se, že při přihlášení uživatele AAD existuje připojení k internetu. V případě potřeby nakonfigurujte zásady [MixedReality/AADGroupMembershipCacheValidityInDays](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-aadgroupmembershipcachevalidityindays) tak, aby fungovaly i bez internetu.

### <a name="issue---building-a-package-with-kiosk-mode-failed"></a>Problém – Sestavení balíčku s bezobrazovkovém režimu selhalo

**Příznaky**

Zobrazí se dialogové okno jako níže.

<kbd>
    <img alt="Kiosk failure to build" src="./images/kiosk-steps/kiosk-ppkg-failure.png"/>
</kbd>

**Postup při řešení potíží**

1. Klikněte na hyper-link zobrazený v dialogovém okně výše.
1. Otevřete soubor ICD.log v textovém editoru a jeho obsah by měl značit chybu.

> [!NOTE]
> Pokud jste provedli několik pokusů, zkontrolujte časová razítka v protokolu. To vám pomůže zkontrolovat pouze aktuální problémy.

### <a name="issue--provisioning-package-built-successfully-but-failed-to-apply"></a>Problém – Zřizovací balíček je úspěšně sestavený, ale nepovedlo se ho použít.

**Příznaky**

Při použití zřizovacího balíčku na Hololens se zobrazí chyba

**Postup při řešení potíží**

1. Přejděte do složky, kde Windows konfiguračního návrháře pro zřizovací balíček modulu runtime.
1. Otevřete soubor ICD.log a ujistěte se, že protokol při sestavování zřizovacího balíčku obsahuje žádné chyby. Některé chyby se během sestavování nezobrazují, ale jsou stále zaprotokolované v souboru ICD.log

### <a name="issue--multiple-app-assigned-access-to-aad-group-does-not-work"></a>Problém – Nefunguje více přístupů přiřazených aplikací ke skupině AAD

**Příznaky**

Při přihlášení uživatele AAD zařízení nepřechádá do režimu veřejného terminálů.

**Postup při řešení potíží**

- V XML konfigurace přiřazeného přístupu potvrďte, že se použije identifikátor GUID skupiny AAD, ve které je přihlášený uživatel členem, a ne identifikátor GUID uživatele AAD.
- Potvrďte, že na portálu Intune se uživatel AAD skutečně zobrazuje jako člen cílové skupiny AAD.
