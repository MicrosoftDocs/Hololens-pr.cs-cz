---
title: Nastavení HoloLens jako veřejného terminálu
description: Zjistěte, jak nastavit a používat konfiguraci veřejného terminálů k uzamčení aplikací na zařízeních HoloLens.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/27/2020
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 347501c3ac8f1b115b0d537332a17938a99d3257
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111377651"
---
# <a name="set-up-hololens-as-a-kiosk"></a>Nastavení HoloLens jako veřejného terminálu

Zařízení HoloLens můžete nakonfigurovat tak, aby fungovalo jako zařízení s pevným účelem, také nazývané veřejného terminálu, a to tak, že zařízení nakonfigurujete tak, aby se spouštěl v beznalém režimu. Bezobrazovový režim omezuje aplikace (nebo uživatele), které jsou na zařízení dostupné. Režim veřejného terminálů je praktická funkce, pomocí které můžete vytyčovat zařízení HoloLens pro obchodní aplikace nebo používat zařízení HoloLens v ukázce aplikace.

Tento článek obsahuje informace o aspektech konfigurace veřejného terminálů, které jsou specifické pro zařízení HoloLens. Obecné informace o různých typech terminálů s Windows a jejich konfiguraci najdete v tématu Konfigurace terminálů a digitálních značek v desktopových [edicích Windows.](https://docs.microsoft.com/windows/configuration/kiosk-methods)  

> [!IMPORTANT]  
> Režim veřejného terminálů určuje, které aplikace jsou k dispozici, když se uživatel přihlásí k zařízení. Bezobrazovový režim ale není metoda zabezpečení. Nezastaví aplikaci, která je povolená, otevření jiné aplikace, která není povolená. Pokud chcete aplikacím nebo procesům zablokovat otevírání, vytvořte Windows Defender zásady pomocí nástroje [WDAC (Application Control) CSP.](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp)
>
> Přečtěte si další informace o služby Microsoft, které uživatelům poskytují pokročilou úroveň zabezpečení, kterou HoloLens 2 používá, přečtěte si další informace o oddělení a izolaci stavu – ochrana [pomocí programu Defender.](security-state-separation-isolation.md#defender-protections) Nebo zjistěte, jak pomocí WDAC a Windows PowerShell povolit nebo blokovat aplikace na [zařízeních HoloLens 2 s Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).

Bezobrazovový režim můžete použít v konfiguraci s jednou nebo více aplikacemi a k nastavení a nasazení konfigurace veřejného terminálu můžete použít jeden ze tří procesů.

> [!IMPORTANT]  
> Odstraněním konfigurace s více aplikacemi odeberete profily uzamčení uživatele, které vytvořila funkce přiřazeného přístupu. Nevrátil ale všechny změny zásad. Pokud chcete tyto zásady vrátit zpět, musíte zařízení obnovit do továrního nastavení.

## <a name="plan-the-kiosk-deployment"></a>Plánování nasazení veřejného terminálu

Při plánování veřejného terminálů budete muset být schopni zodpovědět následující otázky. Tady jsou některá rozhodnutí, na která byste se měli při čtení této stránky zamyslet, a některé aspekty pro tyto otázky.
1. **Kdo bude používat váš beziosk [](hololens-identity.md) a jaký typ účtů bude používat?** Jedná se o rozhodnutí, které jste už pravděpodobně udělali, a nemělo by se upravovat kvůli vašemu veřejného terminálu, ale bude to mít vliv na to, jak se bude kiosk přidělovat později.
1. **Potřebujete mít pro uživatele nebo skupinu různé bezobrazovkové terminály, nebo pro některé není povolený beziosk?** Pokud ano, budete chtít vytvořit bezobrazovk přes XML. 
1. **Kolik aplikací bude ve vašem bezobrazovkovém systému?** Pokud máte více než jednu aplikaci, budete potřebovat bezobrazovkové terminály s více aplikacemi. 
1. **Které aplikace budou ve vašem bezobrazovkovém systému?** Pomocí našeho seznamu identifikátorů AUMID níže přidejte In-Box vlastní aplikace.
1. **Jak plánujete nasadit beziosk?** Pokud zařízení zaregistrujete v MDM, doporučujeme k nasazení veřejného terminálu použít MDM. Pokud MDM používáte, je k dispozici nasazení se zřizovacím balíčkem.  

### <a name="kiosk-mode-requirements"></a>Požadavky na bezobrazovkové režimy

Libovolné zařízení HoloLens 2 můžete nakonfigurovat tak, aby bylo možné používat beznaioskový režim.

> [!IMPORTANT]
> Bezobrazovový režim je dostupný jenom v případě, že zařízení Windows Holographic for Business. Všechna zařízení HoloLens 2 se Windows Holographic for Business a nejsou k dispozici žádné jiné edice. Všechna zařízení HoloLens 2 jsou schopná beznaběhový režim spouštět.
>
> Zařízení HoloLens (1. generace) je potřeba upgradovat jak z hlediska sestavení operačního systému, tak edice operačního systému. Tady jsou další informace o aktualizaci HoloLens (1. generace) [na Windows Holographic for Business](hololens1-upgrade-enterprise.md) edici. Pokud chcete zařízení HoloLens (1. generace) aktualizovat tak, aby bylo v beznalém režimu, musíte se nejdřív ujistit, že na zařízení běží Windows 10 verze 1803 nebo novější. Pokud jste k obnovení zařízení HoloLens (1. generace) do výchozího sestavení použili nástroj Pro obnovení zařízení Windows, nebo pokud jste nainstalovali nejnovější aktualizace, je zařízení připravené ke konfiguraci.

> [!IMPORTANT]  
> Pokud chcete chránit zařízení, která běží v beznabránovém režimu, zvažte přidání zásad správy zařízení, které vypnou funkce, jako je připojení USB. Zkontrolujte také nastavení aktualizačního okruhu a ujistěte se, že během pracovní doby nedochází k automatickým aktualizacím.

### <a name="decide-between-a-single-app-kiosk-or-a-multi-app-kiosk"></a>Rozhodnutí mezi bezioskem s jednou aplikací nebo bezobrazovkovém prostředí s více aplikacemi

Bezna terminál s jednou aplikací spustí zadanou aplikaci, když se uživatel přihlásí k zařízení. Funkce nabídka Start zakázaná, stejně jako Cortana. Zařízení HoloLens 2 nereaguje na [gesto Spuštění.](hololens2-basic-usage.md#start-gesture) Zařízení HoloLens (1. generace) nereaguje na gesto [bloomu.](hololens1-basic-usage.md) Protože může běžet jenom jedna aplikace, nemůže uživatel umístit jiné aplikace.

Bezna terminál s více aplikacemi zobrazí nabídka Start, když se uživatel přihlásí k zařízení. Konfigurace veřejného terminálů určuje, které aplikace jsou k dispozici v nabídka Start. Pomocí veřejného terminálu s více aplikacemi můžete uživatelům poskytnout snadno pochopitelné prostředí tím, že jim prezentuje jenom to, co musí použít, a odebráním toho, co nepožádá.

Následující tabulka uvádí funkce v různých režimech veřejného terminálů.

| &nbsp; |Nabídka Start |Nabídka Rychlé akce |Kamera a video |Miracast |Cortana |Integrované hlasové příkazy |
| --- | --- | --- | --- | --- | --- | --- | 
|Beziosk s jednou aplikací |Zakázáno |Zakázáno |Zakázáno |Zakázáno   |Zakázáno |Povoleno<sup>1</sup> |
|Beziosk s více aplikacemi |Povoleno |Povoleno<sup>2</sup> |K dispozici<sup>2</sup> |K dispozici<sup>2</sup> |K<sup>dispozici 2, 3</sup>  |Povoleno<sup>1</sup> |

> <sup>1</sup> Hlasové příkazy, které se vztahují k zakázaným funkcím, nebudou fungovat.  
> <sup>2</sup> Další informace o tom, jak tyto funkce nakonfigurovat, najdete v tématu [Výběr aplikací veřejného terminála.](#plan-kiosk-apps)  
> <sup>3</sup> I když je Cortana zakázaná, integrované hlasové příkazy jsou povolené.

Následující tabulka uvádí funkce uživatelské podpory různých režimů veřejného terminálů.

| &nbsp; |Podporované typy uživatelů | Automatické přihlášení | Více úrovní přístupu |
| --- | --- | --- | --- |
|Beziosk s jednou aplikací |Účet spravované služby (MSA) v Azure Active Directory (Azure AD) nebo místní účet |Yes |No |
|Beziosk s více aplikacemi |Účet Azure AD |No |Yes |

Příklady použití těchto funkcí najdete v následující tabulce.

|Použití veřejného terminálu s jednou aplikací pro: |Použití veřejného terminálu s více aplikacemi pro: |
| --- | --- |
|Zařízení, na které běží jenom příručka Dynamics 365 pro nové zaměstnance |Zařízení, na které běží průvodci i vzdálená pomoc pro celou řadu zaměstnanců. |
|Zařízení, na které běží jenom vlastní aplikace. |Zařízení, které funguje jako beziosk pro většinu uživatelů (jenom vlastní aplikace), ale funguje jako standardní zařízení pro konkrétní skupinu uživatelů. |

### <a name="plan-kiosk-apps"></a>Plánování aplikací v bezobrazovkovém systému

Obecné informace o tom, jak zvolit aplikace v bezobrazovkovém režimu, najdete v tématu Pokyny pro výběr aplikace pro přiřazený přístup [(bezioskový režim).](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)

Pokud ke konfiguraci veřejného Portál zařízení s Windows s jednou aplikací použijete nástroj , vyberete aplikaci během procesu nastavení.  

Pokud ke konfiguraci beziosku používáte systém Mobile Správa zařízení (MDM) nebo zřizovací balíček, použijete k určení aplikací poskytovatele konfiguračních služeb [AssignedAccess.](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) CSP používá k identifikaci aplikací [IDENTIFIKÁTORY AUMID (Application User Model](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) ID). V následující tabulce je uveden seznam AUMIDs některých integrovaných aplikací, které můžete použít v terminálu s více aplikacemi.

> [!IMPORTANT]
> Celoobrazovkový režim určuje, které aplikace jsou k dispozici, když se uživatel přihlásí k zařízení. Beznabídkový režim však není metodou zabezpečení. Neukončí aplikaci povolenou otevřením jiné aplikace, která není povolena. Vzhledem k tomu, že toto chování neomezujeme, můžou být aplikace pořád spuštěné z Edge, Průzkumníka souborů a aplikací Microsoft Store. Pokud existují konkrétní aplikace, které nechcete spustit z veřejného terminálu, vytvořte pomocí [zprostředkovatele CSP (WDAC) Application Control pro Windows Defender](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) příslušné zásady. 
> 
> Kromě toho není možné nastavit domovskou stránku hybridní reality jako beznabídkovou aplikaci.

<a id="aumids"></a>

|Název aplikace |AUMID |
| --- | --- |
|Prohlížeč 3D |Microsoft. Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft. Microsoft3DViewer |
|Kalendář |Microsoft. windowscommunicationsapps \_ 8wekyb3d8bbwe \! Microsoft. windowslive. Calendar |
|Kamera<sup>1, 2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Aplikace Microsoft. 549981C3F5F10 \_ 8wekyb3d8bbwe \! |
|Výběr zařízení na HoloLens (1. generace) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|Výběr zařízení na HoloLens 2 |Microsoft. Windows. DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft. Windows. DevicesFlowHost |
|Příručky k Dynamics 365 |Microsoft. Dynamics365. příruček \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Vzdálená pomoc pro Dynamics 365 |Microsoft. MicrosoftRemoteAssist \_ 8wekyb3d8bbwe \! Microsoft. RemoteAssist |
|&nbsp;Centrum Feedback |Aplikace Microsoft. WindowsFeedbackHub \_ 8wekyb3d8bbwe \! |
|Průzkumník souborů |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy! Aplikace |
|Poštovní |microsoft.windowscommunicationsapps_8wekyb3d8bbwe! Microsoft. windowslive. mail |
|Starý Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge |
|Nové Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe! Aplikace |
|Miracast<sup>4</sup> |&nbsp; |
|Filmy & televizor |Microsoft. ZuneVideo \_ 8wekyb3d8bbwe \! Microsoft. ZuneVideo |
|OneDrive |aplikace Microsoft. microsoftskydrive \_ 8wekyb3d8bbwe \! |
|Fotky |Aplikace Microsoft. Windows. photos \_ 8wekyb3d8bbwe \! |
|Stará nastavení |HolographicSystemSettings_cw5n1h2txyewy! Aplikace |
|Nové nastavení |BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! Aplikace |
|Tipy |Microsoft. HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> Pokud chcete povolit digitalizaci fotek nebo videa, musíte aplikaci kamery povolit jako beznabídkovou aplikaci.  
> <sup>2</sup> Pokud povolíte aplikaci kamery, pamatujte na následující podmínky:
> - Nabídka rychlé akce obsahuje tlačítka pro fotografii a video.  
> - Měli byste taky povolit aplikaci (například fotky, poštu nebo OneDrive), která může pracovat s obrázky nebo ji načítat.  
>  
> <sup>3</sup> i v případě, že Cortana nepovolíte jako beznabídkovou aplikaci, jsou integrované hlasové příkazy povolené. Příkazy, které se vztahují k zakázaným funkcím, ale nemají žádný vliv.  
> <sup>4</sup> nelze povolit Miracast přímo. Pokud chcete povolit Miracast jako beznabídkovou aplikaci, povolte aplikaci kamery a aplikaci pro výběr zařízení.

### <a name="plan-kiosk-profiles-for-users-or-groups"></a>Naplánování profilů veřejného terminálu pro uživatele nebo skupiny

Když buď vytvoříte soubor XML, nebo pomocí uživatelského rozhraní Intune nastavíte veřejný terminál, budete muset vzít v úvahu, kdo bude mít uživatele v celoobrazovkovém režimu. Konfiguraci veřejného terminálu můžete omezit buď na jednotlivé účty, nebo na skupiny Azure AD. 

Veřejné terminály jsou obvykle povoleny buď pro uživatele, nebo pro skupinu uživatelů. Pokud však plánujete psaní vlastního veřejného terminálu XML, budete možná chtít vzít v úvahu globální přiřazený přístup, ve kterém se veřejný terminál použije na úrovni zařízení bez ohledu na identitu. Pokud se vám tyto potíže [týkají, přečtěte si další informace o globálním přístupovém Webterminálu.](hololens-global-assigned-access-kiosk.md)

#### <a name="if-you-are-creating-an-xml-file"></a>Pokud vytváříte soubor XML:
-   Máte spoustu vytvoření více profilů veřejného terminálu a přiřadíte jednotlivé uživatele nebo skupiny různým uživatelům. Například veřejný terminál pro skupinu Azure AD, který má mnoho aplikací, a návštěvník, který má s aplikací jednotného terminálu více aplikací.
-   Vaše konfigurace veřejného terminálu se nazývá **ID profilu** a identifikátor GUID.
-   Tento profil přiřadíte v oddílu konfigurace zadáním typu uživatele a použitím stejného identifikátoru GUID pro **ID DefaultProfile**.
- Soubor XML se dá vytvořit, ale pořád se aplikuje na zařízení přes MDM. vytvoří se vlastní konfigurační profil zařízení OMA URI a použije se pro skupinu zařízení HoloLens s použitím hodnoty identifikátoru URI:./Device/Vendor/MSFT/AssignedAccess/Configuration

#### <a name="if-you-are-creating-a-kiosk-in-intune"></a>Pokud vytváříte veřejný terminál v Intune.
-   Každé zařízení může obdržet jenom jeden profil veřejného terminálu. v opačném případě vytvoří konflikt a nepřijme žádné konfigurace veřejného terminálu. 
    -   Jiné druhy profilů a zásad, například omezení zařízení, která nesouvisí s profilem konfigurace veřejného terminálu, nejsou v konfliktu s profilem konfigurace veřejného terminálu.
-   Veřejný terminál bude povolen pro všechny uživatele, kteří jsou součástí typu přihlášení uživatele, který se nastaví s uživatelem nebo skupinou Azure AD. 
-   Po nastavení konfigurace veřejného terminálu a **typu přihlášení uživatele** (uživatelé, kteří se můžou přihlásit k veřejnému terminálu) a vybrané aplikace, musí být konfigurace zařízení pořád přiřazená ke skupině. Přiřazené skupiny určují, která zařízení dostanou konfiguraci veřejného zařízení, ale nekomunikují, pokud je povolený veřejný terminál. 
    - Úplnou diskuzi o účincích přiřazení konfiguračních profilů v Intune najdete v tématu [přiřazení profilů uživatelů a zařízení v Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-profile-assign).

### <a name="select-a-deployment-method"></a>Vyberte metodu nasazení

Pro nasazení konfigurací veřejného terminálu můžete vybrat jednu z následujících metod:

- [Microsoft Intune nebo jiná služba správy mobilních zařízení (MDM)](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [Zřizovací balíček](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Portál zařízení Windows](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > Vzhledem k tomu, že tato metoda vyžaduje, aby byl v zařízení povolený vývojářský režim, doporučujeme, abyste ho používali jenom pro ukázky.

V následující tabulce jsou uvedeny možnosti a výhody jednotlivých metod nasazení.

| &nbsp; |Nasazení pomocí portálu zařízení Windows |Nasazení pomocí zřizovacího balíčku |Nasazení pomocí MDM |
| --------------------------- | ------------- | -------------------- | ---- |
|Nasazení terminálů s jednou aplikací   | Yes           | Yes                  | Yes  |
|Nasadit veřejné terminály s více aplikacemi    | No            | Yes                  | Yes  |
|Nasadit jenom na místní zařízení | Yes           | Yes                  | No   |
|Nasazení pomocí vývojářského režimu |Vyžadováno       | Nevyžadováno            | Nevyžadováno   |
|Nasazení pomocí Azure Active Directory (Azure AD)  | Nevyžadováno            | Nevyžadováno                   | Vyžadováno  |
|Automatické nasazení      | No            | No                   | Yes  |
|Rychlost nasazení            | Rychlý       | Rychlá                 | Pomalý |
|Nasazení ve velkém | Nedoporučuje se    | Doporučeno        | Doporučeno |

## <a name="use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk"></a>Použití Microsoft Intune nebo jiných řešení MDM k nastavení veřejného terminálu s jednou nebo více aplikacemi

Pokud chcete nastavit bezobrazovový režim pomocí Microsoft Intune nebo jiného systému MDM, postupujte podle těchto kroků.

1. [Připravte se na registraci zařízení.](#mdmenroll)
1. [Vytvořte konfigurační profil veřejného terminálu.](#mdmprofile)
1. Nakonfigurujte bezobrazovkové terminály.
   - [Nakonfigurujte nastavení pro bezobrazovk s jednou aplikací.](#mdmconfigsingle)
   - [Nakonfigurujte nastavení pro beziosk s více aplikacemi.](#mdmconfigmulti)
1. [Přiřaďte konfigurační profil veřejného terminálu ke skupině](#mdmassign).
1. Nasaďte zařízení.
   - [Nasazení veřejného terminálu s jednou aplikací](#mdmsingledeploy)
   - [Nasazení veřejného terminálu s více aplikacemi](#mdmmultideploy)

### <a name="mdm-step-1-ndash-prepare-to-enroll-the-devices"></a><a id="mdmenroll"></a>MDM– krok 1 &ndash; Příprava registrace zařízení

Systém MDM můžete nakonfigurovat tak, aby automaticky zaregistroval zařízení HoloLens, když se uživatel poprvé přihlásí, nebo aby zařízení zaregistroval ručně. Zařízení musí být také připojená k vaší doméně Azure AD a přiřazena k příslušným skupinám.

Další informace o tom, jak zaregistrovat zařízení, najdete v tématu Registrace [HoloLens](hololens-enroll-mdm.md) v MDM a způsobech registrace zařízení s [Windows v Intune.](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods)

### <a name="mdm-step-2-ndash-create-a-kiosk-configuration-profile"></a><a id="mdmprofile"></a>MDM, krok 2 &ndash; Vytvoření konfiguračního profilu veřejného terminálu

1. Otevřete [Azure Portal](https://portal.azure.com/) a přihlaste se ke svému Správce Intune účtu.
1. Vyberte **Microsoft Intune**  >  **Konfigurace zařízení – Profily** Vytvořit  >  **profil.**
1. Zadejte název profilu.
1. Vyberte **Možnost**  >  **Windows 10 a novější a** pak vyberte Typ profilu **Omezení**  > **zařízení.**
1. Vyberte **Konfigurovat**  >  **beziosk** a pak vyberte jednu z následujících možností:
   - Pokud chcete vytvořit beziosk s jednou aplikací, vyberte **Bezobrazovový** režim Bez přípony.  >  
   - Pokud chcete vytvořit bezobrazovk s více aplikacemi, vyberte **Bezobrazovový režim** Režim více aplikací Beziosk.  >  
1. Pokud chcete začít konfigurovat beziosk, vyberte **Přidat.**

Další kroky se liší v závislosti na typu veřejného terminálů, který chcete. Další informace získáte výběrem jedné z následujících možností:  

- [Beziosk s jednou aplikací](#mdmconfigsingle)
- [Beziosk s více aplikacemi](#mdmconfigmulti)

Další informace o tom, jak vytvořit konfigurační profil veřejného terminálu, najdete v tématu [Windows 10 a Windows Holographic for Business,](https://docs.microsoft.com/intune/configuration/kiosk-settings)která se mají spustit jako vyhrazený beznaiosk pomocí Intune.

### <a name="mdm-step-3-single-app-ndash--configure-the-settings-for-a-single-app-kiosk"></a><a id="mdmconfigsingle"></a>MDM, krok 3 (jedna aplikace) Konfigurace nastavení veřejného terminálu &ndash;  s jednou aplikací

Tato část shrnuje nastavení, která vyžaduje beziosk s jednou aplikací. Další podrobnosti najdete v následujících článcích:

- Informace o tom, jak nakonfigurovat konfigurační profil veřejného terminálů v Intune, najdete v tématu Konfigurace beznaiosku pomocí [Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Další informace o dostupných nastaveních pro veřejného terminály s jednou aplikací v Intune najdete v článku o bezna obrazovce [s jednou aplikací na celé obrazovce.](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)
- Pokyny k jiným službám MDM najdete v dokumentaci k poskytovateli. Pokud k nastavení veřejného terminálu ve službě MDM musíte použít vlastní konfiguraci XML, vytvořte soubor XML, který definuje konfiguraci [veřejného terminálu.](#ppkioskconfig)

1. Vyberte **Typ přihlášení uživatele** Místní uživatelský účet a pak zadejte uživatelské jméno místního účtu (zařízení) nebo účtu Microsoft (MSA), který se může přihlásit k  >  beziosku.
   > [!NOTE]  
   > Typy uživatelských účtů **Automatické přihlášení** nejsou na zařízení s Windows Holographic for Business podporované.
1. Vyberte **Typ aplikace** Aplikace Aplikace pro  >  **Store** a pak v seznamu vyberte aplikaci.

Dalším krokem je [přiřazení](#mdmassign) profilu ke skupině.

### <a name="mdm-step-3-multi-app-ndash-configure-the-settings-for-a-multi-app-kiosk"></a><a id="mdmconfigmulti"></a>MDM, krok 3 (více aplikací) Konfigurace nastavení veřejného &ndash; terminálu s více aplikacemi

Tato část shrnuje nastavení, která vyžaduje beziosk s více aplikacemi. Podrobnější informace najdete v následujících článcích:

- Informace o tom, jak nakonfigurovat konfigurační profil veřejného terminálů v Intune, najdete v tématu Konfigurace beznaiosku pomocí [Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Další informace o dostupných nastaveních pro bezobrazovkové terminály s více aplikacemi v Intune najdete v tématu Veřejného terminály [s více aplikacemi.](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- Pokyny k jiným službám MDM najdete v dokumentaci k poskytovateli. Pokud k nastavení veřejného terminálu ve službě MDM potřebujete použít vlastní konfiguraci XML, vytvořte soubor XML, který definuje konfiguraci [veřejného terminálu.](#ppkioskconfig) Pokud používáte soubor XML, nezapomeňte zahrnout [rozložení Start](#start-layout-for-hololens).  
- Volitelně můžete použít vlastní rozložení Start s Intune nebo jinými službami MDM. Další informace najdete v tématu [Spuštění souboru rozložení pro MDM (Intune](#start-layout-file-for-mdm-intune-and-others)a další).

1. Vyberte **Cílové Windows 10 v režimu S Ne.**  >  .  
>[!NOTE]  
> Režim S není podporován v Windows Holographic for Business.

1. Vyberte **Typ přihlášení uživatele** Uživatel nebo skupina Azure AD nebo Typ přihlášení uživatele Návštěvník  >     >  **HoloLens** a pak přidejte jednu nebo více skupin uživatelů nebo účtů.  

   Prostředí veřejného terminálů mohou používat jenom  uživatelé, kteří patří do skupin nebo účtů, které zadáte v části Typ přihlášení uživatele.

1. Vyberte jednu nebo více aplikací pomocí následujících možností:
   - Pokud chcete přidat nahranou obchodní aplikaci, vyberte **Přidat aplikaci** ze Storu a pak vyberte požadovanou aplikaci.
   - Pokud chcete přidat aplikaci zadáním jejího AUMID, vyberte **Přidat podle AUMID** a pak zadejte AUMID aplikace. [Zobrazení seznamu dostupných identifikátorů AUMID](#aumids)

Dalším krokem je [přiřazení](#mdmassign) profilu ke skupině.

### <a name="mdm-step-4-ndash-assign-the-kiosk-configuration-profile-to-a-group"></a><a id="mdmassign"></a>MDM, krok 4: Přiřazení konfiguračního profilu &ndash; veřejného terminálu ke skupině

Na stránce **Přiřazení konfiguračního** profilu veřejného terminálů nastavte, kam chcete konfiguraci veřejného terminálů nasadit. V nejjednodušším případě přiřadíte konfigurační profil veřejného terminálů skupině, která bude obsahovat zařízení HoloLens, když se zařízení zaregistruje v MDM.

### <a name="mdm-step-5-single-app-ndash-deploy-a-single-app-kiosk"></a><a id="mdmsingledeploy"></a>MDM, krok 5 (jedna aplikace) &ndash; Nasazení veřejného terminálu s jednou aplikací

Když používáte systém MDM, můžete zařízení zaregistrovat v MDM během spuštění počítače. Po dokončení OOBE se můžete snadno přihlásit k zařízení.

Během OOBE postupujte takto:

1. Přihlaste se pomocí účtu, který jste zadali v konfiguračním profilu veřejného terminálu.
1. Registrace zařízení Ujistěte se, že je zařízení přidané do skupiny, ke které je konfigurační profil veřejného terminálů přiřazený.
1. Počkejte na dokončení funkce OOBE, na stažení a instalaci aplikace ze Storu a na použití zásad. Pak zařízení restartujte.

Při příštím přihlášení k zařízení by se měla automaticky spustit aplikace veřejného terminálu.

Pokud v tuto chvíli konfiguraci veřejného terminálu nevidíte, [zkontrolujte stav přiřazení](https://docs.microsoft.com/intune/configuration/device-profile-monitor).

### <a name="mdm-step-5-multi-app-ndash-deploy-a-multi-app-kiosk"></a><a id="mdmmultideploy"></a>MDM, krok 5 (více aplikací) &ndash; Nasazení veřejného terminálu s více aplikacemi

Když používáte systém MDM, můžete zařízení připojit ke svému tenantovi Azure AD a zaregistrovat ho v MDM během spuštění počítače. V případě potřeby zadejte uživatelům informace o registraci, aby je měli k dispozici během procesu OOBE.

> [!NOTE]  
> Pokud jste přiřadili konfigurační profil veřejného terminálů ke skupině, která obsahuje uživatele, ujistěte se, že jeden z těchto uživatelských účtů je prvním účtem pro přihlášení k zařízení.

Během OOBE postupujte takto:

1. Přihlaste se pomocí účtu, který patří do **skupiny typů přihlášení** uživatele.
1. Registrace zařízení
1. Počkejte, až se stáhnou a nainstalují všechny aplikace, které jsou součástí konfiguračního profilu veřejného terminálu. Také počkejte na použití zásad.  
1. Po dokončení počátečního nastavení můžete nainstalovat další aplikace z Microsoft Storu nebo pomocí zkušebního načtení. [Požadované aplikace](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) pro skupinu, pro kterou zařízení patří k instalaci automaticky
1. Po dokončení instalace zařízení znovu spusťte.

Až se příště přihlásíte k zařízení pomocí účtu, který patří do **typu přihlášení uživatele**, aplikace veřejného terminálu by se měla automaticky spustit.

Pokud v tuto chvíli nevidíte konfiguraci veřejného terminálu, [Zkontrolujte stav přiřazení](https://docs.microsoft.com/intune/configuration/device-profile-monitor).

## <a name="use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk"></a>Použití zřizovacího balíčku k nastavení veřejného terminálu pro jednu aplikaci nebo více aplikací

Pokud chcete nastavit celoobrazovkový režim pomocí zřizovacího balíčku, postupujte podle těchto kroků.

1. [Vytvořte soubor XML, který definuje konfiguraci veřejného terminálu.](#ppkioskconfig)včetně [počátečního rozložení](#start-layout-for-hololens).
2. [Přidejte soubor XML do zřizovacího balíčku.](#ppconfigadd)
3. [Použijte zřizovací balíček na HoloLens.](#ppapply)

### <a name="provisioning-package-step-1-ndash-create-a-kiosk-configuration-xml-file"></a><a id="ppkioskconfig"></a>Zřizovací balíček, krok 1 &ndash; Vytvoření souboru XML konfigurace veřejného terminálu

Postupujte podle [obecných pokynů pro vytvoření souboru XML konfigurace veřejného terminálu pro plochu Windows](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file), s výjimkou následujících:

- Nezahrnujte klasické aplikace pro Windows (Win32). HoloLens tyto aplikace nepodporuje.
- Pro HoloLens použijte [zástupný symbol pro začátek rozložení XML](#start-layout-for-hololens) .
- Volitelné: přidejte přístup hosta do konfigurace veřejného terminálu.

#### <a name="optional-add-guest-access-to-the-kiosk-configuration"></a><a id="ppkioskguest"></a>Volitelné: přidejte přístup hosta do konfigurace veřejného terminálu.

V části [ **CONFIGS** souboru XML](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)můžete nakonfigurovat speciální skupinu s názvem **Návštěvníci** , která umožní hostům využívat veřejný terminál. Když je veřejný terminál nakonfigurovaný tak, aby podporoval speciální skupinu **návštěvníků** , přidá se na přihlašovací stránku možnost **Host**. Účet **Guest** nevyžaduje heslo a při odhlášení účtu se odstraní všechna data přidružená k tomuto účtu.

Pokud chcete povolit účet **Guest** , přidejte následující fragment kódu do souboru XML konfigurace veřejného terminálu:

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```
#### <a name="enable-visitor-autologon"></a>Povolit automatické přihlašování návštěvníků

V sestavách [Windows holografické verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1) a vyšší:
- Konfigurace AAD a Nepřidání: podporuje jak automatické přihlašování, tak i účty návštěvníků, které jsou povolené pro celoobrazovkový režim.

##### <a name="non-aad-configuration"></a>Konfigurace jiného typu než AAD

1. Vytvořte zřizovací balíček, který:
    1. Nakonfiguruje nastavení modulu runtime/AssignedAccess tak, aby umožňoval účty návštěvníků.
    1. Volitelně můžete zařízení zaregistrovat v MDM (nastavení modulu runtime/pracoviště/registrace), aby se mohlo spravovat později.
    1. Nevytvářet místní účet
2. [Použijte zřizovací balíček](https://docs.microsoft.com/hololens/hololens-provisioning).

##### <a name="aad-configuration"></a>Konfigurace AAD

Zařízení připojená k AAD nakonfigurovaná pro celoobrazovkový režim se můžou přihlásit k účtu návštěvníka jediným klepnutím na tlačítko na přihlašovací obrazovce. Po přihlášení k účtu návštěvníka se zařízení nevyzve k opětovnému přihlášení, dokud se návštěvník výslovně odhlásí z nabídky Start nebo když se zařízení nerestartuje.

Automatické přihlašování návštěvníka se dá spravovat pomocí [vlastních zásad OMA-URI](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10):

- Hodnota identifikátoru URI:./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon


| Zásady |Description |Konfigurace 
| --------------------------- | ------------- | -------------------- |
| MixedReality/VisitorAutoLogon | Umožňuje návštěvníkovi automatické přihlašování do veřejného terminálu. | 1 (Ano), 0 (ne, výchozí) |

#### <a name="placeholder-start-layout-for-hololens"></a><a id="start-layout-for-hololens"></a>Zástupný symbol pro počáteční rozložení pro HoloLens

Pokud použijete [zřizovací balíček](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) ke konfiguraci veřejného terminálu s více aplikacemi, procedura vyžaduje počáteční rozložení. Přizpůsobení rozložení od začátku se ve Windows holografickém pro firmy nepodporuje. Proto budete muset použít zástupné počáteční rozložení.

> [!NOTE]  
> Vzhledem k tomu, že veřejný terminál s jednou aplikací spouští aplikaci na veřejném terminálu, když se uživatel přihlásí, nepoužívá nabídku Start a nemusí mít počáteční rozložení.

> [!NOTE]  
> Pokud používáte [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) k nastavení veřejného terminálu s více aplikacemi, můžete volitelně použít počáteční rozložení. Další informace najdete v tématu [zástupný symbol pro začátek souboru rozložení pro MDM (Intune a další)](#start-layout-file-for-mdm-intune-and-others).

Pro možnost začít rozložení přidejte do souboru XML pro veřejné zřizování následující část **upravily** :

```xml
<!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
            <StartLayout>
                <![CDATA[<LayoutModificationTemplate xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout" Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
                      <LayoutOptions StartTileGroupCellWidth="6" />
                      <DefaultLayoutOverride>
                        <StartLayoutCollection>
                          <defaultlayout:StartLayout GroupCellWidth="6">
                            <start:Group Name="">
                              <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
                            </start:Group>
                          </defaultlayout:StartLayout>
                        </StartLayoutCollection>
                      </DefaultLayoutOverride>
                    </LayoutModificationTemplate>
                ]]>
            </StartLayout>
            <!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
```

#### <a name="placeholder-start-layout-file-for-mdm-intune-and-others"></a><a id="start-layout-file-for-mdm-intune-and-others"></a>Zástupný symbol pro začátek souboru rozložení pro MDM (Intune a další)

Následující ukázku uložte jako soubor XML. Tento soubor můžete použít při konfiguraci veřejného terminálu s více aplikacemi v Microsoft Intune (nebo v jiné službě MDM, která poskytuje profil veřejného terminálu).

> [!NOTE]
> Pokud pro nastavení veřejného terminálu ve službě MDM používáte vlastní nastavení a úplnou konfiguraci XML, použijte [pokyny pro vytvoření balíčku pro zřizovací balíček](#start-layout-for-hololens).

```xml
<LayoutModificationTemplate
    xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification"
    xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout"
    xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout"
    Version="1">
  <RequiredStartGroupsCollection>
    <RequiredStartGroups>
      <AppendGroup Name="">
        <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
      </AppendGroup>
    </RequiredStartGroups>
  </RequiredStartGroupsCollection>
 </LayoutModificationTemplate>
```

### <a name="prov-package-step-2-ndash-add-the-kiosk-configuration-xml-file-to-a-provisioning-package"></a><a id="ppconfigadd"></a>Kazatel. balíček, krok 2 &ndash; přidejte do zřizovacího balíčku konfigurační soubor XML pro veřejné terminály.

1. Otevřete [Windows Configuration Designer](https://www.microsoft.com/store/apps/9nblggh4tx22).
1. Vyberte **Upřesnit zřizování**, zadejte název projektu a pak vyberte **Další**.
1. Vyberte **Windows 10 holografické** a potom vyberte **Další**.
1. Vyberte **Dokončit**. Otevře se pracovní prostor pro váš balíček.
1. Vyberte **nastavení modulu runtime**  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings**.
1. V prostředním podokně vyberte **Procházet** a vyhledejte a vyberte soubor XML konfigurace veřejného terminálu, který jste vytvořili.

   ![Snímek obrazovky s polem MultiAppAssignedAccessSettings v Návrháři konfigurace Windows](./images/multiappassignedaccesssettings.png)

1. **Volitelné**. (Pokud chcete zřizovací balíček použít po počátečním nastavení zařízení a na veřejném zařízení je již k dispozici uživatel s právy pro správu, přeskočte tento krok.) Vyberte **nastavení modulu runtime** &gt; **účty** &gt; **Uživatelé** a pak vytvořte uživatelský účet. Zadejte uživatelské jméno a heslo a pak vyberte   >  **skupiny** uživatelů.  
  
     Pomocí tohoto účtu můžete zobrazit stav zřizování a protokoly.  
1. **Volitelné**. (Pokud už nemáte účet správce na veřejném zařízení, přeskočte tento krok.) Vyberte **nastavení modulu runtime** &gt; **účty** &gt; **Uživatelé** a pak vytvořte místní uživatelský účet. Ujistěte se, že je uživatelské jméno stejné jako pro účet, který zadáte v konfigurační XML. Vyberte **uživatele** se  >  **standardními** uživateli.
1. Vyberte   >  **Uložit** soubor.
1. Vyberte **exportovat**  >  **zřizovací balíček** a pak vyberte **vlastník**  >  **IT správce**. Tím se nastaví priorita tohoto zřizovacího balíčku vyšší než zřizovací balíčky, které se na toto zařízení aplikují z jiných zdrojů.
1. Vyberte **Další**.
1. Na stránce **zabezpečení balíčku zřizování** vyberte možnost zabezpečení.
   > [!IMPORTANT]  
   > Pokud vyberete možnost **povolit podepisování balíčků**, budete také muset vybrat platný certifikát, který se má použít k podepsání balíčku. Pokud to chcete provést, vyberte **Procházet** a vyberte certifikát, který chcete použít k podepsání balíčku.
   
   > [!CAUTION]  
   > Nevybírejte možnost **Povolit šifrování balíčku**. U zařízení s HoloLens toto nastavení způsobí, že se zřizování nezdaří.
1. Vyberte **Další**.
1. Zadejte umístění výstupu, kde má zřizovací balíček při sestavení přejít. Ve výchozím nastavení používá nástroj Windows Configuration Designer složku projektu jako umístění výstupu. Pokud chcete změnit umístění výstupu, vyberte **Procházet**. Po dokončení vyberte **Další**.
1. Vyberte **sestavení** pro zahájení sestavování balíčku. Zřizovací balíček netrvá déle, než se sestaví. Na stránce Build (sestavení) se zobrazí informace o projektu a indikátor průběhu indikuje stav sestavení.

### <a name="provisioning-package-step-3-ndash-apply-the-provisioning-package-to-hololens"></a><a id="ppapply"></a>Zřizovací balíček, krok 3, &ndash; použití zřizovacího balíčku na HoloLens

Článek konfigurace HoloLens pomocí zřizovacího balíčku poskytuje podrobné pokyny k použití zřizovacího balíčku za následujících okolností:

- [Během instalace můžete nejdřív použít zřizovací balíček na HoloLens](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

- [Zřizovací balíček můžete použít také pro HoloLens po instalaci](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup).

## <a name="use-the-windows-device-portal-to-set-up-a-single-app-kiosk"></a>Použití portálu zařízení Windows k nastavení veřejného terminálu s jednou aplikací

Pokud chcete nastavit celoobrazovkový režim pomocí portálu zařízení s Windows, postupujte podle těchto kroků.

1. [Nastavte zařízení HoloLens na používání portálu zařízení Windows](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal). Portál zařízení je webový server na HoloLens, ke kterému se můžete připojit z webového prohlížeče na svém počítači.

    > [!CAUTION]
    > Když nastavíte HoloLens tak, aby používal portál zařízení, musíte na zařízení povolit vývojářský režim. Vývojářský režim na zařízení, které má Windows Holografick pro firmy, vám umožní načítat aplikace po straně. Toto nastavení však vytvoří riziko, že uživatel může instalovat aplikace, které nebyly certifikovány Microsoft Store. Správci můžou zablokovat možnost Povolit vývojářský režim pomocí nastavení **odemčení ApplicationManagement/AllowDeveloper** v [zásadách CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider). [Přečtěte si další informace o vývojářského režimu.](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. Na počítači se připojte k HoloLens pomocí [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) nebo [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb).

1. Proveďte některou z následujících akcí:
   - Pokud se ke službě Portál zařízení s Windows poprvé, [vytvořte uživatelské jméno a heslo.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - Zadejte uživatelské jméno a heslo, které jste nastavili dříve.

    > [!TIP]
    > Pokud se v prohlížeči zobrazí chyba certifikátu, postupujte [podle těchto kroků pro řešení potíží.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)

1. V Portál zařízení s Windows vyberte **Bezobrazovový režim.**

1. Vyberte **Povolit bezobrazovový režim,** vyberte aplikaci, která se má spustit při spuštění zařízení, a pak vyberte **Uložit.**

    ![Bezobrazovový režim](images/kiosk.png)
1. Restartujte HoloLens. Pokud máte stále otevřenou Portál zařízení, můžete v  horní části stránky vybrat Restartovat.

> [!NOTE]
> Bezobrazovový režim je možné nastavit přes REST API služby Portál zařízení tak, že se pomocí POST nastaví /api/holographic/kioskmode/settings s jedním povinným parametrem řetězce dotazu ("kioskModeEnabled&quot; s hodnotou &quot;true&quot; nebo &quot;false") a jedním volitelným parametrem ("startupApp" s hodnotou názvu balíčku). Mějte na paměti, že Portál zařízení je určený pouze pro vývojáře a neměl by být povolený na zařízeních, která nejsou vývojáři. Změny REST API v budoucích aktualizacích a verzích.

## <a name="more-information"></a>Další informace

### <a name="watch-how-to-configure-a-kiosk-by-using-a-provisioning-package"></a>Podívejte se, jak nakonfigurovat beziosk pomocí zřizovacího balíčku.  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <a name="global-assigned-access--kiosk-mode"></a>Globální přiřazený přístup – Bezobrazovový režim
- Snížená správa identit pro bezobrazovkové režimy tím, že se povolí nová metoda veřejného terminálu, která na úrovni systému použije režim veřejného terminálu.

Tato nová funkce umožňuje správci IT nakonfigurovat zařízení HoloLens 2 pro režim veřejného terminálů s více aplikacemi, který je použitelný na úrovni systému, nemá žádné spřažení s žádnou identitou v systému a vztahuje se na všechny uživatele, kteří se k zařízení přihlásí. Další podrobnosti o této nové funkci najdete v dokumentaci k veřejného terminálu s globálním přiřazeným přístupem k [HoloLens.](hololens-global-assigned-access-kiosk.md)

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>Automatické spuštění aplikace v bezobrazovkovém režimu s více aplikacemi 
- Cílené prostředí s automatickým spouštěním aplikací, které dále zvyšuje možnosti uživatelského rozhraní a aplikací zvolené pro prostředí bezobrazovkovém režimu.

Platí jenom pro beznarový režim s více aplikacemi a jenom 1 aplikaci je možné pomocí zvýrazněných atributů níže v konfiguraci Přiřazený přístup určená k automatickému spuštění. 

Aplikace se automaticky spustí při přihlášení uživatele. 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>Změny chování v bezobrazovkovém režimu pro zpracování selhání
Při selhání při použití bezobrazovkovém režimu se zobrazí následující chování:

- Před Windows Holographic se ve verzi 20H2 – HoloLens zobrazí všechny aplikace v nabídka Start.
- Windows Holographic verze 20H2 – pokud má zařízení konfiguraci veřejného terminálů, což je kombinace přístupu přiřazeného globálně i přiřazeného členovi skupiny AAD. Pokud se nepodaří určit členství ve skupině AAD, uživateli se zobrazí nabídka "nic se nezobrazuje v nabídce Start".

![Obrázek toho, jak vypadá bezobrazovový režim, když selže](images/hololens-kiosk-failure-behavior.png )


- Od [Windows Holographic verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1)hledá bezobrazovový režim před zobrazením prázdné nabídky Start možnost Globální přiřazený přístup. Prostředí veřejného terminálů se v případě selhání v beznaiosku skupiny AAD propadne do globální konfigurace veřejného terminálu (pokud je k dispozici).

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Ukládání členství ve skupině Azure AD do mezipaměti pro offline bezobrazovkové režimy

- Bezpečnější bezobrazovkové režimy eliminují selhání dostupných aplikací v bezobrazovkovém režimu.
- Povolili jste offline terminály pro použití se skupinami Azure AD po dobu až 60 dnů.

Tato zásada určuje, kolik dní může být mezipaměť členství ve skupinách Azure AD použita pro konfigurace přiřazeného přístupu, které cílí na skupiny Azure AD pro přihlášené uživatele. Jakmile je hodnota této zásady nastavená na hodnotu větší než 0, použije se mezipaměť, jinak se hodnota mezipaměti nenastaví.  

Název: AADGroupMembershipCacheValidityInDays Hodnota identifikátoru URI: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min – 0 dní  
Max. – 60 dnů 

Postup správnému použití této zásady: 
1. Vytvořte profil konfigurace zařízení pro beznaiosk cílení na skupiny Azure AD a přiřaďte ho k zařízením HoloLens. 
1. Vytvořte vlastní konfiguraci zařízení založenou na OMA URI, která nastaví tuto hodnotu zásady na požadovaný počet dní (> 0) a přiřadí ji k zařízením HoloLens. 
    1. Do textového pole OMA-URI by se měla zadat hodnota URI ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays.
    1. Hodnota může být v rozmezí od minimálního do maximálního povoleného.
1. Zaregistrujte zařízení HoloLens a ověřte, že se na zařízení použijí obě konfigurace. 
1. Nechte uživatele Azure AD 1 přihlásit se, když je k dispozici internet, po úspěšném potvrzení přihlášení uživatele a úspěšného členství ve skupině Azure AD se vytvoří mezipaměť. 
1. Uživatel Azure AD 1 teď může HoloLens pře offline a používat ho pro beznaioskový režim, pokud hodnota zásady umožňuje počet dní X. 
1. Kroky 4 a 5 je možné opakovat pro libovolného jiného uživatele Azure AD N. Klíčovým bodem je, že každý uživatel Azure AD se musí přihlásit k zařízení pomocí internetu, takže aspoň jednou můžeme určit, že jsou členem skupiny Azure AD, na kterou je cílem konfigurace veřejného terminálu. 
 
> [!NOTE]
> Dokud se pro uživatele Azure AD neprovádí krok 4, bude docházet k chování při selhání uvedeném v odpojených prostředích. 


## <a name="xml-kiosk-code-samples-for-hololens"></a>Ukázky kódu XML kiosku pro HoloLens

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a>Bezobrazovový režim s více aplikacemi, který cílí na skupinu Azure AD. 
Tento beziosk nasadí bezobrazovk, který uživatelům ve skupině Azure AD povolí beziosk, který zahrnuje tři aplikace: Nastavení, Vzdálená pomoc a Centrum Feedback. Pokud chcete tuto ukázku upravit tak, aby se používala okamžitě, nezapomeňte změnit identifikátor GUID zvýrazněný níže tak, aby odpovídal vaší vlastní skupině Azure AD. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a>Bezobrazovový režim s více aplikacemi, který cílí na účet Azure AD.
Tento beziosk nasadí pro jednoho uživatele beziosk. Bude mít povolený bezobrazovk, který obsahuje tři aplikace: Nastavení, Vzdálená pomoc a Centrum Feedback. Pokud chcete tuto ukázku upravit tak, aby se používala okamžitě, nezapomeňte změnit účet zvýrazněný níže tak, aby odpovídal vašemu vlastnímu účtu Azure AD. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

