---
title: nastavení HoloLens jako veřejného terminálu
description: naučte se, jak nastavit a použít konfiguraci veřejného terminálu pro uzamknutí aplikací na zařízeních HoloLens.
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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032243"
---
# <a name="set-up-hololens-as-a-kiosk"></a>nastavení HoloLens jako veřejného terminálu

## <a name="what-is-kiosk-mode"></a>Co je celoobrazovkový režim?

Celoobrazovkový režim je funkce, kde můžete určit, které aplikace se zobrazí v nabídce Start, když se uživatel přihlásí k HoloLens. Existují dva podporované scénáře:

1. **Celoobrazovkový režim s jednou aplikací** – nezobrazuje se žádná nabídka Start a při přihlášení uživatele se spustí jedna aplikace automaticky. <br> *Příklad použití*: zařízení, ve kterém se spouští jenom aplikace průvodce Dynamics 365.
2. **celoobrazovkový režim více aplikací** – nabídka Start zobrazuje pouze aplikace, které byly zadány v konfiguraci veřejného terminálu, když se uživatel přihlásí. Aplikace se dá zvolit, aby se v případě potřeby automaticky spouštěla. <br> *příklad použití*: zařízení, které v nabídce start obsahuje jenom aplikaci pro Store, centrum Feedback a aplikaci Nastavení.

    <img alt="Multi app kiosk example" src=".\images\multi-app-kiosk.jpg" width="411" height="500" />

## <a name="description-of-kiosk-mode-experience-when-a-user-signs-in"></a>Popis možností celoobrazovkového režimu, když se uživatel přihlásí

V následující tabulce jsou uvedeny funkce funkcí v různých režimech veřejného terminálu.

| &nbsp; |Nabídka Start |Nabídka rychlé akce |Fotoaparát a video |Miracast |Cortana |Integrované hlasové příkazy |
| --- | --- | --- | --- | --- | --- | --- |
|Veřejný terminál s jednou aplikací |Zakázáno |Zakázáno |Zakázáno |Zakázáno   |Zakázáno |Umožněn |
|Veřejný terminál s více aplikacemi |Povoleno |Umožněn  |K dispozici  |K dispozici |K dispozici   |Umožněn  |

\*další informace o povolení zakázaných funkcí nebo způsobu, jakým hlasové příkazy pracují s zakázanými funkcemi a Cortana najdete v tématu [HoloLens AUMIDs for apps](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids).

## <a name="key-general-considerations-before-configuring-kiosk-mode"></a>Obecné důležité otázky před konfigurací celoobrazovkového režimu

1. určete druh uživatelského účtu pro přihlášení do HoloLens ve vašem prostředí – HoloLens podporuje účty Azure Active Directory (AAD), účty Microsoft (MSA) a místní účty. Kromě toho jsou podporovány také dočasně vytvořené účty označované jako hosté/Návštěvníci (pouze pro zařízení s připojením AAD). Další informace najdete v informacích o [správě identity uživatelů a přihlašování pro HoloLens](hololens-identity.md).
2. Určete cíle prostředí celoobrazovkového režimu – ať už se jedná o všechny, jednoho uživatele, určité uživatele nebo uživatele, kteří jsou členy skupin AAD atd.
3. Pro celoobrazovkový režim více aplikací určete aplikace, které se mají zobrazit v nabídce Start. Pro každou aplikaci bude nutné mít [ID modelu uživatele aplikace (AUMID)](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) .
4. určete, jestli se má celoobrazovkový režim použít pro HoloLens prostřednictvím zřizovacích balíčků modulu runtime nebo serveru správy mobilních zařízení (MDM).

## <a name="security-considerations"></a>Důležité informace o zabezpečení

Beznabídkový režim by se neměl považovat za metodu zabezpečení, ale jako prostředek pro řízení prostředí pro spouštění při přihlašování uživatelů. Prostředí celoobrazovkového režimu můžete kombinovat s níže uvedenými možnostmi, pokud jsou k dispozici konkrétní požadavky související se zabezpečením:

- když je aplikace Nastavení nakonfigurovaná tak, aby se zobrazovala v celoobrazovkovém režimu, a chcete určit, které stránky se zobrazí v Nastavení aplikace, přečtěte si téma [Nastavení viditelnost stránky](settings-uri-list.md) .
- pokud chcete řídit přístup k určitým hardwarovým funkcím, třeba k fotoaparátu, Bluetooth atd. pro určité aplikace atd. projděte si [zásady v tématu zprostředkovatel CSP, který podporuje HoloLens 2 Windows správu klientů](/windows/client-management/mdm/policies-in-policy-csp-supported-by-hololens2). Můžete si projít naše [běžná omezení zařízení](hololens-common-device-restrictions.md) pro nápady.
- Celoobrazovkový režim neblokuje aplikaci (nakonfigurovanou jako součást veřejného terminálu) z spuštění jiných aplikací. pokud chcete úplně zablokovat spouštění určitých aplikací nebo procesů na HoloLens, přečtěte si téma [použití Windows Defender řízení aplikací na HoloLens 2 zařízeních v Microsoft Intune – Azure](/mem/intune/configuration/custom-profile-hololens) .

## <a name="key-technical-considerations-for-kiosk-mode-for-hololens"></a>Klíčové technické požadavky pro celoobrazovkový režim pro HoloLens

Platí pouze v případě, že plánujete použít balíčky zřizování za běhu nebo ruční vytváření konfigurací na veřejném terminálu. Konfigurace celoobrazovkového režimu používá hierarchickou strukturu založenou na XML:

- Přiřazený profil přístupu definuje, které aplikace se zobrazí v nabídce Start v celoobrazovkovém režimu. Můžete definovat více profilů ve stejné struktuře XML, na které lze později odkazovat.
- Konfigurace přiřazeného přístupu odkazuje na profil a cílové uživatele tohoto profilu, například na konkrétního uživatele nebo na skupinu AAD nebo návštěvníka atd. V závislosti na složitosti scénářů použití můžete definovat více konfigurací ve stejné struktuře XML (viz část podporované scénáře níže).
- Další informace najdete v tématu [ASSIGNEDACCESS CSP](/windows/client-management/mdm/assignedaccess-csp).

## <a name="supported-scenarios-for-kiosk-mode-based-on-identity-type"></a>Podporované scénáře pro celoobrazovkový režim na základě typu identity

V tématu [Referenční odkazy](hololens-kiosk-reference.md#kiosk-xml-code-samples) najdete příklady v závislosti na vašem scénáři a aktualizaci podle potřeby před kopírováním a vkládáním.

> [!NOTE]
> Použijte XML jenom v případě, že k vytvoření konfigurace veřejného terminálu nepoužíváte uživatelské rozhraní Intune.

### <a name="for-users-who-sign-in-as-either-local-account-or-msa"></a>Pro uživatele, kteří se přihlásí buď jako místní účet, nebo na MSA

| **Požadované možnosti celoobrazovkového terminálu** | **Doporučená konfigurace veřejného terminálu** | **Způsoby konfigurace**  | **Poznámky** |
| --- | --- | --- | --- |
| Všichni uživatelé, kteří se přihlásí, mají celoobrazovkový zážitek. | [Konfigurace vícenásobného přístupového profilu pro globální aplikace](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune vlastní šablonu](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Zřizování za běhu – aplikace s více aplikacemi](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Globální přiřazený přístup vyžaduje [20H2 a novější buildy](hololens-release-notes.md#windows-holographic-version-20h2) . |
| Konkrétní uživatel, který se přihlásí, bude mít možnost celoobrazovkového.  | [Nakonfigurujte přístup k jednomu nebo více aplikacím přiřazenému profilu přístupu (podle potřeby) zadáním názvu konkrétního uživatele.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account) | [Níže najdete informace o podporovaných možnostech.](#steps-in-configuring-kiosk-mode-for-hololens) | V celoobrazovkovém režimu jedné aplikace se HoloLens podporuje jenom místní uživatelský účet nebo účet MSA. <br> V případě více beznabídkového režimu aplikace je HoloLens podporován pouze účet MSA nebo účet AAD. |

### <a name="for-users-who-sign-in-as-aad-account"></a>Pro uživatele, kteří se přihlásí jako účet AAD

| **Požadované možnosti celoobrazovkového terminálu** | **Doporučená konfigurace veřejného terminálu** | **Způsoby konfigurace** | **Poznámky** |
| --- | --- | --- | --- |
| Všichni uživatelé, kteří se přihlásí, mají celoobrazovkový zážitek. | [Konfigurace vícenásobného přístupového profilu pro globální aplikace](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune vlastní šablonu](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Zřizování za běhu – aplikace s více aplikacemi](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Globální přiřazený přístup vyžaduje [20H2 a novější buildy](hololens-release-notes.md#windows-holographic-version-20h2) . |
| Každý uživatel, který se přihlásí, získá celoobrazovkový zážitek s výjimkou určitých uživatelů. | [Nakonfigurujte více globálních uživatelských přidaných profilů přístupu, a to vyloučením určitých uživatelů (kteří musí být vlastníky zařízení)](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile-excluding-device-owners). | • [Microsoft Intune vlastní šablonu](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Zřizování za běhu – aplikace s více aplikacemi](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Globální přiřazený přístup vyžaduje [20H2 a novější buildy](hololens-release-notes.md#windows-holographic-version-20h2) . |
| Každý uživatel AAD získá samostatné možnosti veřejného terminálu pro tohoto uživatele. | [Nakonfigurujte konfiguraci přiřazeného přístupu pro každého uživatele, který určuje název svého účtu AAD.](hololens-kiosk-reference.md#multiple-app-assigned-access-profiles-for-two-aad-users-or-more) | • [Microsoft Intune vlastní šablonu](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Zřizování za běhu – aplikace s více aplikacemi](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | &nbsp; |
| Uživatelé v různých skupinách AAD mají celoobrazovkový režim, který je určen pouze pro skupinu. | [Nakonfigurujte konfiguraci přiřazeného přístupu pro každou požadovanou skupinu AAD.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-two-aad-groups-or-more) | • [Microsoft Intune vlastní šablonu](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Zřizování za běhu – aplikace s více aplikacemi](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | • když se uživatel přihlásí a HoloLens je připojený k internetu, pokud se tento uživatel najde jako člen skupiny aad, pro který existuje konfigurace veřejného terminálu, získá uživatel pro tuto skupinu AAD možnost beznabídkového vstupu. <br> • [pokud není k dispozici internet po přihlášení uživatele, bude mít uživatel možnost HoloLens chování režimu selhání.](#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode) <br> • Pokud není zaručena dostupnost internetu, když se uživatel přihlásí a je potřeba použít kiosk založený na skupině AAD, zvažte použití [zásad AADGroupMembershipCacheValidityInDayspolicy.](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk) <br> • Pro optimální prostředí se skupinami AAD během přihlašování doporučujeme použít [zásady AADGroupMembershipCacheValidityInDayspolicy.](/hololens/hololens-release-notes#cache-azure-ad-group-membership-for-offline-kiosk) |
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

Na buildech [Windows Holographic verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1) a novější:

- Konfigurace AAD i bez přidání podporují automatické protokolování účtů návštěvníka pro režim veřejného terminálu.

[!INCLUDE[](includes/kiosk-autologin.md)]

### <a name="is-kiosk-experience-supported-on-hololens-1st-gen"></a>Je prostředí veřejného terminálu podporované HoloLens (1. generace)?

Bezobrazovový režim je dostupný jenom v případě, že zařízení Windows Holographic for Business. Všechna HoloLens 2 se dodá s Windows Holographic for Business a nejsou k dispozici žádné jiné edice. Každé HoloLens 2 zařízení může bez spuštění spustit bezioskový režim.

HoloLens (1. generace) je potřeba upgradovat jak z hlediska sestavení operačního systému, tak edice operačního systému. Tady jsou další informace o aktualizaci HoloLens (1. generace) [na Windows Holographic for Business](hololens1-upgrade-enterprise.md) edici. Pokud chcete zařízení HoloLens (1. generace) tak, aby bylo v beznarovém režimu, musíte nejprve zajistit, aby na zařízení běží Windows 10, verze 1803 nebo novější. Pokud jste k obnovení zařízení HoloLens (1. generace) použili nástroj Windows Device Recovery Tool do výchozího sestavení, nebo pokud jste nainstalovali nejnovější aktualizace, je zařízení připravené ke konfiguraci.

### <a name="how-to-use-device-portal-to-configure-kiosk-in-non-production-environments"></a>Jak používat portál zařízení ke konfiguraci veřejného terminálů v neprodukcích prostředí?

Nastavte HoloLens [zařízení tak, aby Windows Portál zařízení.](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) The Portál zařízení is a web server on your HoloLens that you can connect to from a web browser on your PC.

 > [!CAUTION]
 > Když nastavíte, HoloLens používat Portál zařízení, musíte na zařízení povolit vývojářský režim. Vývojářský režim na zařízení s Windows Holographic for Business umožňuje zkušební načtení aplikací. Toto nastavení ale vytváří riziko, že uživatel může instalovat aplikace, které nejsou certifikované Microsoft Store. Správci můžou blokovat možnost povolit režim pro vývojáře pomocí nastavení **ApplicationManagement/AllowDeveloper Unlock** v [csP zásad.](/windows/client-management/mdm/policy-configuration-service-provider) [Přečtěte si další informace o režimu pro vývojáře.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)

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
