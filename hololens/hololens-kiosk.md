---
title: Nastavení HoloLens jako beziosku
description: Zjistěte, jak nastavit a používat konfiguraci veřejného terminálů k uzamčení aplikací na HoloLens zařízení.
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
ms.sourcegitcommit: 37611ac0a4efaf69816a734e16b763c810655f1a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2021
ms.locfileid: "123411340"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Nastavení HoloLens jako beziosku

## <a name="what-is-kiosk-mode"></a>Co je bezobrazovový režim?

Režim veřejného terminálů je funkce, ve které můžete řídit, které aplikace se zobrazí v nabídce Start, když se uživatel přihlásí HoloLens. Existují 2 podporované scénáře:

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

1. Určení druhu uživatelského účtu, který se přihlašuje HoloLens ve vašem prostředí – HoloLens podporuje účty Azure Active Directory (AAD), účty Microsoft (MSA) a místní účty. Kromě toho se podporují také dočasně vytvořené účty nazývané hosté nebo návštěvníci (pouze pro zařízení, která se připojují k AAD). Další informace najdete [v části Správa identity uživatele](hololens-identity.md)a přihlašování pro HoloLens .
2. Určete cíle prostředí beznarového režimu – jestli se jedná o každého uživatele, jednoho uživatele, určité uživatele nebo uživatele, kteří jsou členy skupin AAD atd.
3. V případě bezobrazovkového režimu s více aplikacemi určete aplikace, které se zobrazí v nabídce Start. Pro každou aplikaci bude potřeba JEJÍ [ID AUMID (Application User Model ID).](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids)
4. Určete, jestli se na server HoloLens přes zřizovací balíčky modulu runtime nebo server Mobile Správa zařízení (MDM).

## <a name="security-considerations"></a>Důležité informace o zabezpečení

Bezobrazovový režim by se neměl považovat za metodu zabezpečení, ale jako způsob řízení prostředí pro spuštění při přihlašování uživatelů. Prostředí bezobrazovkového režimu můžete kombinovat s níže uvedenými možnostmi, pokud existují specifické požadavky související se zabezpečením:

- Pokud Nastavení aplikace nakonfigurovaná tak, aby se v beznarovém režimu zobrazuje, a chcete řídit, které stránky se v aplikaci Nastavení zobrazují, přečtěte si o viditelnosti Nastavení [stránky.](settings-uri-list.md)
- Pokud chcete řídit přístup k určitým hardwarovým funkcím, například fotoaparátu, Bluetooth atd. u určitých aplikací atd., přečtěte si informace v tématu Zásady poskytovatele CSP zásad podporovaného poskytovatelem cloudových služeb [HoloLens 2 – Windows Správa klientů.](/windows/client-management/mdm/policies-in-policy-csp-supported-by-hololens2) Nápady najdete v [našich běžných omezeních](hololens-common-device-restrictions.md) zařízení.
- Bezobrazovový režim neblokuje aplikacím (nakonfigurované jako součást prostředí veřejného terminálů) spouštění jiných aplikací. Pokud chcete úplně zablokovat spouštění určitých aplikací nebo procesů v HoloLens, přečtěte si část Použití řízení aplikací Windows Defender na zařízeních se systémem HoloLens 2 v [Microsoft Intune – Azure.](/mem/intune/configuration/custom-profile-hololens)

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
| Konkrétní uživatel, který se přihlásí, získá prostředí veřejného terminálu.  | [Nakonfigurujte jeden nebo více přístupových profilů přiřazených aplikací (podle potřeby) a zadejte jméno konkrétního uživatele.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account) | [Podporované možnosti najdete níže.](#steps-in-configuring-kiosk-mode-for-hololens) | V beznaiosku s jednou aplikací se v místním uživatelském režimu podporuje pouze místní uživatelský účet nebo účet MSA HoloLens. <br> Pro režim veřejného terminálů s více aplikacemi se na virtuálních zařízeních podporuje pouze účet MSA nebo účet AAD HoloLens. |

### <a name="for-users-who-sign-in-as-aad-account"></a>Pro uživatele, kteří se přihlásí jako účet AAD

| **Požadované prostředí veřejného terminálu** | **Doporučená konfigurace veřejného terminálu** | **Způsoby konfigurace** | **Poznámky** |
| --- | --- | --- | --- |
| Každý uživatel, který se přihlásí, získá prostředí veřejného terminálu. | [Konfigurace více profilů globálního přiřazeného přístupu aplikace](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune vlastní šablony](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Zřizování za běhu – Více aplikací](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Globální přiřazený přístup vyžaduje [20H2 a novější sestavení.](hololens-release-notes.md#windows-holographic-version-20h2) |
| Každý uživatel, který se přihlásí, získá prostředí veřejného terminálu s výjimkou určitých uživatelů. | [Nakonfigurujte více profilů globálního přiřazeného přístupu aplikace vyloučením určitých uživatelů (kteří musí být vlastníky zařízení).](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile-excluding-device-owners) | • [Microsoft Intune vlastní šablony](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Zřizování za běhu – Více aplikací](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | Globální přiřazený přístup vyžaduje [20H2 a novější sestavení.](hololens-release-notes.md#windows-holographic-version-20h2) |
| Každý uživatel AAD získá samostatné prostředí veřejného terminálů specifické pro tohoto uživatele. | [Nakonfigurujte konfiguraci přiřazeného přístupu pro každého uživatele, který zadá název svého účtu AAD.](hololens-kiosk-reference.md#multiple-app-assigned-access-profiles-for-two-aad-users-or-more) | • [Microsoft Intune vlastní šablony](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Zřizování za běhu – Více aplikací](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | &nbsp; |
| Uživatelé v různých skupinách AAD mají kiosk režim, který je jenom pro jejich skupinu. | [Nakonfigurujte konfiguraci přiřazeného přístupu pro každou požadovanou skupinu AAD.](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-two-aad-groups-or-more) | • [Microsoft Intune vlastní šablony](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Zřizování za běhu – Více aplikací](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | • Když se uživatel přihlásí a HoloLens je připojený k internetu a tento uživatel je členem skupiny AAD, pro kterou existuje konfigurace veřejného terminálu, uživatel se dostane do prostředí veřejného terminálu pro skupinu AAD. <br> • Pokud není při přihlašování uživatelů k dispozici žádný internet, pak se HoloLens [režimu selhání.](#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode) <br> • Pokud není zaručená dostupnost internetu i v případě, že je potřeba použít přihlášení uživatele a veřejný terminál založený na skupině AAD, [zvažte použití AADGroupMembershipCacheValidityInDayspolicy](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk). <br> • Pro optimální prostředí se skupinami AAD během přihlašování doporučujeme použít [AADGroupMembershipCacheValidityInDayspolicy](/hololens/hololens-release-notes#cache-azure-ad-group-membership-for-offline-kiosk) |
| uživatelé, kteří potřebují používat HoloLens pro dočasné účely, získají možnosti pro zajištění veřejného terminálu. | [Konfigurace přiřazeného přístupu pro návštěvníky](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-visitors) | • [Microsoft Intune vlastní šablonu](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [Zřizování za běhu – jedna aplikace](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens) | • dočasný uživatelský účet se automaticky vytvoří HoloLens při přihlášení a při odhlášení dočasného uživatele se odebere. <br> • Zvažte možnost povolit [zásady automatického přihlašování návštěvníků](#how-can-visitor-accounts-automatically-logon-to-kiosk-experience). |

## <a name="steps-in-configuring-kiosk-mode-for-hololens"></a>Postup konfigurace celoobrazovkového režimu pro HoloLens

Konfigurace veřejného terminálu se dají vytvořit a použít následujícími způsoby:

1. S uživatelským rozhraním MDM, např. se šablonami veřejného terminálu Intune nebo vlastní konfigurace OMA-URI, které se pak vzdáleně používají na HoloLens.
2. Pomocí zřizovacích balíčků modulu runtime, které jsou následně přímo aplikovány na HoloLens.

Tady jsou následující způsoby, jak nakonfigurovat, vyberte kartu, která odpovídá procesu, který chcete použít.

1. [šablona veřejného terminálu pro Microsoft Intune pro jednu aplikaci](hololens-kiosk.md?tabs=uisak#steps-in-configuring-kiosk-mode-for-hololens)
2. [šablona veřejného terminálu pro Microsoft Intune více aplikací](hololens-kiosk.md?tabs=uimak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Microsoft Intune vlastní šablonu](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens)
1. [Zřizování za běhu – aplikace s více aplikacemi](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Zřizování za běhu – jedna aplikace](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens)

[!INCLUDE[](includes/kiosk-configure-steps.md)]

## <a name="frequently-asked-questions"></a>Nejčastější dotazy

### <a name="how-can-visitor-accounts-automatically-logon-to-kiosk-experience"></a>Jak se můžou účty návštěvníka automaticky přihlašovat k veřejnému terminálu?

v sestavách [Windows holografická verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1) a vyšší:

- Konfigurace AAD a Nepřidání: podporuje jak automatické přihlašování, tak i bez přidávání, pro celoobrazovkového režimy.

[!INCLUDE[](includes/kiosk-autologin.md)]

### <a name="is-kiosk-experience-supported-on-hololens-1st-gen"></a>je pro HoloLens (1. generace) podporovaná možnost celoobrazovkového prostředí?

Celoobrazovkový režim je dostupný jenom v případě, že zařízení Windows Holographic for Business. všechna zařízení HoloLens 2 jsou dodávána s Windows Holographic for Business a nejsou k dispozici žádné jiné edice. každé zařízení HoloLens 2 je schopné spustit celoobrazovkový režim mimo pole.

zařízení HoloLens (1. generace) je potřeba upgradovat z pohledu na sestavení operačního systému i edice operačního systému. zde jsou další informace o aktualizaci HoloLens (1. generace) na [Windows Holographic for Business](hololens1-upgrade-enterprise.md) edition. chcete-li aktualizovat HoloLens (1) zařízení na používání celoobrazovkového režimu, je třeba nejprve zajistit, aby zařízení běželo Windows 10 verze 1803 nebo novější. pokud jste použili nástroj pro obnovení zařízení Windows k obnovení vašeho HoloLens (1.1) zařízení do výchozího buildu nebo pokud máte nainstalované nejnovější aktualizace, vaše zařízení je připravené ke konfiguraci.

### <a name="how-to-use-device-portal-to-configure-kiosk-in-non-production-environments"></a>Jak používat portál zařízení ke konfiguraci veřejného terminálu v neprodukčních prostředích?

nastavte [zařízení HoloLens na používání portálu Windows zařízení](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal). portál zařízení je webový server na vašem HoloLens, ke kterému se můžete připojit z webového prohlížeče na svém počítači.

 > [!CAUTION]
 > když nastavíte HoloLens, abyste mohli používat portál zařízení, musíte na zařízení povolit vývojářský režim. vývojářský režim na zařízení, které má Windows Holographic for Business umožňuje vám načítat aplikace. Toto nastavení však vytvoří riziko, že uživatel může instalovat aplikace, které nebyly certifikovány Microsoft Store. Správci můžou zablokovat možnost Povolit vývojářský režim pomocí nastavení **odemčení ApplicationManagement/AllowDeveloper** v [zásadách CSP](/windows/client-management/mdm/policy-configuration-service-provider). [Přečtěte si další informace o vývojářském režimu.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)

Celoobrazovkový režim se dá nastavit pomocí REST API portálu zařízení tak, že provedete příspěvek do/API/Holographic/KioskMode/Settings s jedním požadovaným parametrem řetězce dotazu ("kioskModeEnabled" s hodnotou "true" nebo "false") a jedním volitelným parametrem ("startupApp" s hodnotou názvu balíčku). Mějte na paměti, že portál zařízení je určený jenom vývojářům a neměl by být povolený na zařízeních, která nejsou vývojářem. REST API se může změnit v budoucích aktualizacích nebo vydáních.

## <a name="troubleshooting"></a>Řešení potíží

### <a name="issue---no-apps-are-shown-in-start-menu-in-kiosk-mode"></a>Problém – v celoobrazovkovém režimu nejsou v nabídce Start zobrazeny žádné aplikace

**Příznaky**

Při zjištění selhání při použití celoobrazovkového režimu se zobrazí následující chování:

- před Windows holografickou 20H2 verze HoloLens zobrazí všechny aplikace v nabídka Start.
- Windows Holografická verze 20H2 – Pokud má zařízení konfiguraci veřejného terminálu, která je kombinací obou skupin s přiřazeným přístupem globálního přístupu a člena skupiny AAD, zobrazí se uživateli v nabídce Start zobrazená zpráva "nic nezobrazuje".

    ![Obrázek, který celoobrazovkový režim teď vypadá, když se nezdařil.](images/hololens-kiosk-failure-behavior.png )

- od [Windows holografická verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1), celoobrazovkový režim hledá globální přiřazený přístup před zobrazením prázdné nabídky start. Pokud dojde k chybám během celoobrazovkového režimu, budou se možnosti celoobrazovkového prostředí vracet do globální konfigurace veřejného terminálu (pokud existuje).

**Postup při řešení potíží**

- Ověřte, že je AUMID aplikace správně zadaná a neobsahuje verze. příklady najdete v tématu [HoloLens AUMIDs](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) pro aplikace doručených zpráv.
- Ujistěte se, že je aplikace v zařízení pro daného uživatele nainstalovaná.
- Pokud je konfigurace veřejného terminálu založená na skupinách AAD, ujistěte se, že je k dispozici připojení k Internetu, když se uživatel AAD přihlásí. V případě potřeby nakonfigurujte zásady [MixedReality/AADGroupMembershipCacheValidityInDays](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-aadgroupmembershipcachevalidityindays) , aby tato funkce mohla fungovat i bez internetu.

### <a name="issue---building-a-package-with-kiosk-mode-failed"></a>Problém – sestavení balíčku s beznabídkovým režimem se nezdařilo.

**Příznaky**

Zobrazí se dialogové okno podobné následujícímu.

<kbd>
    <img alt="Kiosk failure to build" src="./images/kiosk-steps/kiosk-ppkg-failure.png"/>
</kbd>

**Postup při řešení potíží**

1. Klikněte na odkaz na Hyper-v zobrazeném dialogovém okně.
1. Otevřete ICD. log v textovém editoru a jeho obsah by měl indikovat chybu.

> [!NOTE]
> Pokud jste provedli několik pokusů, ověřte časová razítka v protokolu. To vám pomůže kontrolovat jenom aktuální problémy.

### <a name="issue--provisioning-package-built-successfully-but-failed-to-apply"></a>Problém – zřizování balíčku se úspěšně vytvořilo, ale nepovedlo se ho použít.

**Příznaky**

Při použití zřizovacího balíčku na HoloLens se zobrazí chyba.

**Postup při řešení potíží**

1. přejděte do složky, ve které existuje Windows projekt návrháře konfigurace pro zřizovací balíček za běhu.
1. Otevřete soubor ICD. log a ujistěte se, že protokol neobsahuje žádné chyby při vytváření zřizovacího balíčku. Některé chyby se během sestavování nezobrazují, ale pořád se přihlásí do ICD. log.

### <a name="issue--multiple-app-assigned-access-to-aad-group-does-not-work"></a>Problém – více aplikací přiřazený přístup ke skupině AAD nefunguje

**Příznaky**

Když se uživatel AAD přihlašuje, zařízení nepřejde do celoobrazovkového režimu.

**Postup při řešení potíží**

- Ověřte v souboru XML s přiřazenou konfigurací přístupu, který používá identifikátor GUID skupiny AAD, ke které je přihlášený uživatel členem, a ne identifikátor GUID uživatele AAD.
- Potvrďte, že na portálu Intune, který je ve skutečnosti uživatel AAD, je zobrazený jako člen cílové skupiny AAD.
