---
title: nastavení HoloLens jako veřejného terminálu
description: naučte se, jak nastavit a používat konfiguraci veřejného terminálu pro uzamknutí aplikací na zařízeních HoloLens.
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
ms.openlocfilehash: 9d9e521f3e337b3a48a60c19e52bfeb3186507af
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640351"
---
# <a name="set-up-hololens-as-a-kiosk"></a>nastavení HoloLens jako veřejného terminálu

zařízení HoloLens můžete nakonfigurovat tak, aby fungovalo jako zařízení s pevným účelem, označované také jako veřejný *terminál*, a to tak, že nakonfigurujete zařízení tak, aby běželo v celoobrazovkovém režimu. Celoobrazovkový režim omezuje aplikace (nebo uživatele), které jsou v zařízení k dispozici. celoobrazovkový režim je pohodlná funkce, kterou můžete použít k vyhradit HoloLens zařízení pro obchodní aplikace nebo používat HoloLens zařízení v ukázce aplikace.

tento článek poskytuje informace o aspektech konfigurace veřejného terminálu, které jsou specifické pro HoloLens zařízení. obecné informace o různých typech veřejného terminálu založeného na Windows a o tom, jak je nakonfigurovat, najdete v tématu [konfigurace terminálů a digitálních podpisů v edicích Windows desktopu](/windows/configuration/kiosk-methods).  

> [!IMPORTANT]  
> Celoobrazovkový režim určuje, které aplikace jsou k dispozici, když se uživatel přihlásí k zařízení. Beznabídkový režim však není metodou zabezpečení. Neukončí aplikaci povolenou otevřením jiné aplikace, která není povolena. aby bylo možné blokovat otevírání aplikací nebo procesů, použijte [zprostředkovatele CSP pro Windows Defender aplikací (WDAC)](/windows/client-management/mdm/applicationcontrol-csp) a vytvořte příslušné zásady.
>
> přečtěte si další informace o služby Microsoft a poskytněte uživatelům pokročilou úroveň zabezpečení, kterou HoloLens 2 používá, další informace o [odděleních stavu a ochraně proti izolaci v defenderu](security-state-separation-isolation.md#defender-protections). nebo se naučíte [používat WDAC a Windows PowerShell k povolení nebo blokování aplikací na zařízeních HoloLens 2 pomocí Microsoft Intune](/mem/intune/configuration/custom-profile-hololens).

Celoobrazovkový režim můžete použít buď v jedné aplikaci, nebo v konfiguraci více aplikací a můžete použít jeden ze tří procesů k nastavení a nasazení konfigurace veřejného terminálu.

> [!IMPORTANT]  
> Odstraněním konfigurace s více aplikacemi dojde k odebrání profilů uzamčení uživatele, které vytvořila funkce přiřazený přístup. Nevrátí ale všechny změny zásad. Chcete-li obnovit tyto zásady, je nutné obnovit zařízení do továrního nastavení.

## <a name="plan-the-kiosk-deployment"></a>Plánování nasazení na veřejném terminálu

Při plánování veřejného terminálu budete muset být schopni odpovědět na následující otázky. Tady jsou některá rozhodnutí, která je potřeba vzít v úvahu při čtení této stránky, a některé aspekty pro tyto otázky.
1. **Kdo bude používat váš terminál a jaký [typ účtů](hololens-identity.md) budou používat?** Jedná se o rozhodnutí, které jste už pravděpodobně udělali, a proto by se nemělo v případě svého veřejného terminálu upravovat, ale bude mít vliv na to, jak se veřejný terminál přiřadí později.
1. **Potřebujete mít jiné veřejné terminály na uživatele nebo skupinu nebo veřejný terminál, který není pro některé z nich povolený?** Pokud ano, budete chtít vytvořit své veřejné terminály prostřednictvím XML. 
1. **Kolik aplikací bude v terminálu?** Pokud máte více než jednu aplikaci, budete potřebovat veřejný terminál s více aplikacemi. 
1. **Které aplikace budou ve vašem veřejném terminálu?** Použijte prosím náš seznam AUMIDs níže a přidejte In-Box aplikace navíc k vlastním.
1. **Jak plánujete nasadit svůj veřejný terminál?** Pokud zaregistrujete zařízení do MDM, doporučujeme, abyste k nasazení veřejného terminálu používali MDM. Pokud nepoužíváte MDM, je k dispozici nasazení s balíčkem zřizování.  

### <a name="kiosk-mode-requirements"></a>Požadavky na celoobrazovkový režim

zařízení HoloLens 2 můžete nakonfigurovat tak, aby používalo celoobrazovkový režim.

> [!IMPORTANT]
> Celoobrazovkový režim je dostupný jenom v případě, že zařízení Windows Holographic for Business. všechna zařízení HoloLens 2 jsou dodávána s Windows Holographic for Business a nejsou k dispozici žádné jiné edice. každé zařízení HoloLens 2 je možné spustit beznabídkový režim.
>
> zařízení HoloLens (1. generace) je potřeba upgradovat z pohledu na sestavení operačního systému i edice operačního systému. zde jsou další informace o aktualizaci HoloLens (1. generace) na [Windows Holographic for Business](hololens1-upgrade-enterprise.md) edition. chcete-li aktualizovat HoloLens (1) zařízení na používání celoobrazovkového režimu, je třeba nejprve zajistit, aby zařízení běželo Windows 10 verze 1803 nebo novější. pokud jste použili nástroj pro obnovení zařízení Windows k obnovení vašeho HoloLens (1.1) zařízení do výchozího buildu nebo pokud máte nainstalované nejnovější aktualizace, vaše zařízení je připravené ke konfiguraci.

> [!IMPORTANT]  
> Pokud chcete chránit zařízení, která běží v celoobrazovkovém režimu, zvažte přidání zásad správy zařízení, které vypíná funkce, jako je třeba připojení USB. Dále zkontrolujte nastavení aktualizačního kruhu a ujistěte se, že automatické aktualizace neproběhne během pracovní doby.

### <a name="decide-between-a-single-app-kiosk-or-a-multi-app-kiosk"></a>Rozhodování mezi veřejným terminálem s jednou aplikací nebo veřejným terminálem s více aplikacemi

Veřejný terminál s jednou aplikací spustí zadanou aplikaci, když se uživatel přihlásí k zařízení. nabídka Start je zakázaný, jak je Cortana. zařízení HoloLens 2 nereaguje na gesto [spuštění](hololens2-basic-usage.md#start-gesture) . HoloLens (první gen) zařízení nereaguje na gesto [bloom](hololens1-basic-usage.md) . Vzhledem k tomu, že může běžet jenom jedna aplikace, uživatel nemůže umístit další aplikace.

veřejný terminál s více aplikacemi zobrazuje nabídka Start, když se uživatel přihlásí k zařízení. konfigurace veřejného terminálu určuje, které aplikace jsou na nabídka Start k dispozici. Můžete použít veřejný terminál s více aplikacemi a poskytnout uživatelům snadno pochopitelné prostředí tím, že jim nabídnete jenom ty věci, které musí použít, a odebrat tak věci, které nepotřebují používat.

V následující tabulce jsou uvedeny funkce funkcí v různých režimech veřejného terminálu.

| &nbsp; |Nabídka Start |Nabídka rychlé akce |Fotoaparát a video |Miracast |Cortana |Integrované hlasové příkazy |
| --- | --- | --- | --- | --- | --- | --- | 
|Veřejný terminál s jednou aplikací |Zakázáno |Zakázáno |Zakázáno |Zakázáno   |Zakázáno |Povoleno<sup>1</sup> |
|Veřejný terminál s více aplikacemi |Povoleno |Povoleno<sup>2</sup> |K dispozici<sup>2</sup> |K dispozici<sup>2</sup> |Dostupné<sup>2, 3</sup>  |Povoleno<sup>1</sup> |

> <sup>1</sup> hlasové příkazy, které se týkají zakázaných funkcí, nefungují.  
> <sup>2</sup> Pokud chcete získat další informace o konfiguraci těchto funkcí, přečtěte si téma [Výběr beznabídkových aplikací](#plan-kiosk-apps).  
> <sup>3</sup> i v případě, že je Cortana zakázaná, jsou integrované hlasové příkazy povolené.

V následující tabulce jsou uvedeny funkce podpory uživatelů v různých režimech veřejného terminálu.

| &nbsp; |Podporované typy uživatelů | Automatické přihlašování | Více úrovní přístupu |
| --- | --- | --- | --- |
|Veřejný terminál s jednou aplikací |účet spravované služby (MSA) v Azure Active Directory (Azure AD) nebo místním účtu |Yes |No |
|Veřejný terminál s více aplikacemi |Účet Azure AD |No |Yes |

Příklady použití těchto možností naleznete v následující tabulce.

|Používejte veřejný terminál s jednou aplikací pro: |Používejte veřejný terminál s více aplikacemi pro: |
| --- | --- |
|Zařízení, které pro nové zaměstnance spouští jenom Průvodce Dynamics 365. |Zařízení, které spouští obě průvodce i vzdálenou pomoc pro řadu zaměstnanců. |
|Zařízení, které spouští pouze vlastní aplikaci. |Zařízení, které funguje jako veřejný terminál pro většinu uživatelů (spouští jenom vlastní aplikaci), ale funguje jako standardní zařízení pro konkrétní skupinu uživatelů. |

### <a name="plan-kiosk-apps"></a>Plánování beznabídkových aplikací

Obecné informace o tom, jak zvolit aplikace na veřejném terminálu, najdete v tématu [pokyny pro výběr aplikace pro přiřazený přístup (celoobrazovkový režim)](/windows/configuration/guidelines-for-assigned-access-app).

pokud používáte portál zařízení Windows ke konfiguraci veřejného terminálu s jednou aplikací, vyberte aplikaci během procesu instalace.  

Pokud ke konfiguraci celoobrazovkového režimu použijete systém správy mobilních zařízení (MDM) nebo zřizovací balíček, použijte k určení aplikací [poskytovatele služby AssignedAccess Configuration Service Provider (CSP)](/windows/client-management/mdm/assignedaccess-csp) . CSP používá k identifikaci aplikací [ID modelu uživatele aplikace (AUMIDs)](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) . V následující tabulce jsou uvedené identifikátory AUMID některých aplikací, které můžete použít v beznaiosku s více aplikacemi.

> [!IMPORTANT]
> Režim veřejného terminálů určuje, které aplikace jsou k dispozici, když se uživatel přihlásí k zařízení. Bezobrazovový režim ale není metoda zabezpečení. Nezastaví aplikaci, která je povolená, otevření jiné aplikace, která není povolená. Vzhledem k tomu, že toto chování neomezujeme, je stále možné aplikace spustit z Edge, Průzkumníka souborů a Microsoft Store aplikací. Pokud nechcete z veřejného terminálů spustit konkrétní aplikace, vytvořte odpovídající zásady pomocí Windows Defender [Application Control (WDAC) CSP.](/windows/client-management/mdm/applicationcontrol-csp) 
> 
> Domovskou stránku Mixed Reality navíc není možné nastavit jako aplikaci veřejného terminálu.

<a id="aumids"></a>

|Název aplikace |AUMID |
| --- | --- |
|3D prohlížeč |Microsoft.Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft.Microsoft3DViewer |
|Kalendář |microsoft.windowscommunicationsapps \_ 8wekyb3d8bbwe \! microsoft.windowslive.calendar |
|Kamera<sup>1, 2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Microsoft.549981C3F5F10 \_ 8wekyb3d8bbwe \! App |
|Výběr zařízení v HoloLens (1. generace) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|Výběr zařízení na HoloLens 2 |Microsoft. Windows. DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft.Windows. DevicesFlowHost |
|Průvodci Dynamics 365 |Microsoft.Dynamics365.Guides \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft.MicrosoftRemoteAssst \_ 8wekyb3d8bbwe \! Microsoft.RemoteAssst |
|Centrum &nbsp; feedback |Aplikace Microsoft.WindowsFeedbackHub \_ 8wekyb3d8bbwe \! |
|Průzkumník souborů |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy! App |
|Poštovní |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|Starý Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge |
|Nové Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe! App |
|Miracast<sup>4</sup> |&nbsp; |
|Movies & TV |Microsoft.ZuneVideo \_ 8wekyb3d8bbwe \! Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive \_ 8wekyb3d8bbwe \! App |
|Fotky |Microsoft. Windows. Aplikace Photos \_ 8wekyb3d8bbwe \! |
|Starý Nastavení |HolographicSystemSettings_cw5n1h2txyewy! App |
|Nové Nastavení |BAEAEF15-9BE-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
|Tipy |Microsoft.HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> Pokud chcete povolit zachytávání fotek nebo videí, musíte aplikaci Fotoaparát povolit jako aplikaci veřejného terminálu.  
> <sup>2</sup> Když povolíte aplikaci Fotoaparát, je třeba mít na paměti následující podmínky:
> - Nabídka Rychlé akce obsahuje tlačítka Fotografie a Video.  
> - Měli byste také povolit aplikaci (například Fotky, Pošta nebo OneDrive), která může pracovat s obrázky nebo načítat obrázky.  
>  
> <sup>3</sup> I v případě, že Cortana jako aplikaci veřejného terminálu, jsou povolené integrované hlasové příkazy. Příkazy, které souvisejí se zakázanými funkcemi, ale nemají žádný vliv.  
> <sup>4</sup> Nelze povolit Miracast. Pokud chcete Miracast jako aplikaci veřejného terminále, povolte aplikaci Fotoaparát a Aplikaci pro výběr zařízení.

### <a name="plan-kiosk-profiles-for-users-or-groups"></a>Plánování profilů veřejného terminálů pro uživatele nebo skupiny

Při vytváření souboru XML nebo při nastavení veřejného terminálu pomocí uživatelského rozhraní Intune budete muset zvážit, kdo ho bude používat. Konfiguraci veřejného terminálů je možné omezit buď na individuální účet, nebo na skupiny Azure AD. 

Veřejného terminály jsou obvykle povolené buď pro uživatele, nebo pro skupinu uživatelů. Pokud ale plánujete psát vlastní beziosk XML, měli byste zvážit přístup s globálním přiřazeným přístupem, ve kterém se tento terminál použije na úrovni zařízení bez ohledu na identitu. Pokud se vám to líbí, [přečtěte si další informace o globálních terminálech s přiřazeným přístupem.](hololens-global-assigned-access-kiosk.md)

#### <a name="if-you-are-creating-an-xml-file"></a>Pokud vytváříte soubor XML:
-   Můžete vytvořit několik profilů veřejného terminálů a každý z nich přiřadit různým uživatelům nebo skupinám. Například kiosk pro vaši skupinu Azure AD, který má mnoho aplikací, a návštěvník, který má více veřejného terminálu aplikace singelární aplikací.
-   Konfigurace veřejného terminálů se bude nazývat **ID profilu** a bude mít identifikátor GUID.
-   Profil přiřadíte v části konfigurace tak, že zadáte typ uživatele a jako ID DefaultProfile zadáte stejný **identifikátor GUID.**
- Soubor XML je možné vytvořit, ale přesto ho použít na zařízení přes MDM tak, že vytvoříte vlastní konfigurační profil zařízení OMA URI a použijete ho pro skupinu zařízení HoloLens s použitím hodnoty URI. ./Device/Vendor/MSFT/AssignedAccess/Configuration

#### <a name="if-you-are-creating-a-kiosk-in-intune"></a>Pokud vytváříte bezobrazovkové terminály v Intune.
-   Každé zařízení může přijímat jenom jeden profil veřejného terminálu, jinak vytvoří konflikt a vůbec neobdrží žádné konfigurace veřejného terminálu. 
    -   Jiné druhy profilů a zásad, například omezení zařízení, která s konfiguračním profilem veřejného terminálů souvisejí, nejsou v konfliktu s konfiguračním profilem veřejného terminálu.
-   Beziosk bude povolený pro všechny uživatele, kteří jsou součástí typu Přihlášení uživatele. Nastaví se u uživatele nebo skupiny Azure AD. 
-   Po nastavení konfigurace veřejného terminálů  a typu Přihlášení uživatele (uživatelé, kteří se mohou přihlašovat k bezobrazovkovém objektu) a vybrané možnosti Aplikace musí být konfigurace zařízení pořád přiřazená ke skupině. Přiřazená skupina (nebo skupiny) určuje, která zařízení obdrží konfiguraci zařízení v bezobrazovkovém režimech, ale pokud je tento bezobrazovk povolený nebo ne, nebude s ním interagovat. 
    - Úplnou diskuzi o dopadech přiřazování konfiguračních profilů v Intune najdete v tématu Přiřazení profilů uživatelů a zařízení [v Microsoft Intune](/intune/configuration/device-profile-assign).

### <a name="select-a-deployment-method"></a>Výběr metody nasazení

Můžete vybrat jednu z následujících metod nasazení konfigurací veřejného terminálů:

- [Microsoft Intune nebo jiná služba správy mobilních zařízení (MDM)](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [Zřizovací balíček](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows Portál zařízení](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > Vzhledem k tomu, že tato metoda vyžaduje, aby byl na zařízení povolený vývojářský režim, doporučujeme ho používat jenom pro ukázky.

Následující tabulka uvádí možnosti a výhody jednotlivých metod nasazení.

| &nbsp; |Nasazení pomocí Windows Portál zařízení |Nasazení pomocí zřizovacího balíčku |Nasazení pomocí MDM |
| --------------------------- | ------------- | -------------------- | ---- |
|Nasazení terminálů s jednou aplikací   | Yes           | Yes                  | Yes  |
|Nasazení terminálů s více aplikacemi    | No            | Yes                  | Yes  |
|Nasazení pouze do místních zařízení | Yes           | Yes                  | No   |
|Nasazení pomocí vývojářského režimu |Vyžadováno       | Nevyžadováno            | Nevyžadováno   |
|Nasazení pomocí Azure Active Directory (Azure AD)  | Nevyžadováno            | Nevyžadováno                   | Vyžadováno  |
|Automatické nasazení      | No            | No                   | Yes  |
|Rychlost nasazení            | Rychlý       | Rychlá                 | Pomalý |
|Nasazení ve velkém | Nedoporučuje se    | Doporučeno        | Doporučeno |

## <a name="use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk"></a>Použití Microsoft Intune nebo jiného MDM k nastavení veřejného terminálu s jednou nebo více aplikacemi

Pokud chcete nastavit bezobrazovový režim pomocí Microsoft Intune nebo jiného systému MDM, postupujte podle těchto kroků.

1. [Připravte se na registraci zařízení.](#mdmenroll)
1. [Vytvořte konfigurační profil veřejného terminálu.](#mdmprofile)
1. Nakonfigurujte beziosk.
   - [Nakonfigurujte nastavení pro beziosk s jednou aplikací.](#mdmconfigsingle)
   - [Nakonfigurujte nastavení pro beziosk s více aplikacemi.](#mdmconfigmulti)
1. [Přiřaďte konfigurační profil veřejného terminálu ke skupině](#mdmassign).
1. Nasaďte zařízení.
   - [Nasaďte beziosk s jednou aplikací.](#mdmsingledeploy)
   - [Nasaďte beziosk s více aplikacemi.](#mdmmultideploy)

### <a name="mdm-step-1-ndash-prepare-to-enroll-the-devices"></a><a id="mdmenroll"></a>MDM– krok 1 &ndash; Příprava registrace zařízení

Systém MDM můžete nakonfigurovat tak, aby automaticky HoloLens zařízení, když se uživatel poprvé přihlásí, nebo aby zařízení zaregistroval ručně. Zařízení musí být také připojená k vaší doméně Azure AD a přiřazena k příslušným skupinám.

Další informace o registraci zařízení najdete v tématu Registrace zařízení [HoloLens v MDM](hololens-enroll-mdm.md) a metodách registrace [Intune pro Windows zařízení.](/mem/intune/enrollment/windows-enrollment-methods)

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

Další informace o tom, jak vytvořit profil konfigurace veřejného terminálu, najdete v tématu [Windows 10 a Windows Holographic for Business,](/intune/configuration/kiosk-settings)která se mají spustit jako vyhrazený beznaiosk pomocí Intune.

### <a name="mdm-step-3-single-app-ndash--configure-the-settings-for-a-single-app-kiosk"></a><a id="mdmconfigsingle"></a>MDM, krok 3 (jedna aplikace) Konfigurace nastavení veřejného terminálu &ndash;  s jednou aplikací

Tato část shrnuje nastavení, která vyžaduje beziosk s jednou aplikací. Další podrobnosti najdete v následujících článcích:

- Informace o tom, jak nakonfigurovat konfigurační profil veřejného terminálů v Intune, najdete v tématu Konfigurace beznaiosku pomocí [Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Další informace o dostupných nastaveních pro veřejného terminály s jednou aplikací v Intune najdete v článku o bezna obrazovce [s jednou aplikací na celé obrazovce.](/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)
- Pokyny k jiným službám MDM najdete v dokumentaci k poskytovateli. Pokud k nastavení veřejného terminálu ve službě MDM musíte použít vlastní konfiguraci XML, vytvořte soubor XML, který definuje konfiguraci [veřejného terminálu.](#ppkioskconfig)

1. Vyberte **Typ přihlášení uživatele** Místní uživatelský účet a pak zadejte uživatelské jméno místního účtu (zařízení) nebo účtu Microsoft (MSA), který se může přihlásit k  >  beziosku.
   > [!NOTE]  
   > Typy uživatelských účtů **Automatické přihlášení** nejsou na zařízení s Windows Holographic for Business podporované.
1. Vyberte **Typ aplikace** Aplikace Aplikace pro  >  **Store** a pak v seznamu vyberte aplikaci.

Dalším krokem je [přiřazení](#mdmassign) profilu ke skupině.

### <a name="mdm-step-3-multi-app-ndash-configure-the-settings-for-a-multi-app-kiosk"></a><a id="mdmconfigmulti"></a>MDM, krok 3 (více aplikací) Konfigurace nastavení veřejného terminálu &ndash; s více aplikacemi

Tato část shrnuje nastavení, která vyžaduje beziosk s více aplikacemi. Podrobnější informace najdete v následujících článcích:

- Informace o tom, jak nakonfigurovat konfigurační profil veřejného terminálů v Intune, najdete v tématu Konfigurace beznaiosku pomocí [Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).
- Další informace o dostupných nastaveních pro bezobrazovkové terminály s více aplikacemi v Intune najdete v tématu Veřejného terminály [s více aplikacemi.](/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- Pokyny k jiným službám MDM najdete v dokumentaci k poskytovateli. Pokud k nastavení veřejného terminálu ve službě MDM potřebujete použít vlastní konfiguraci XML, vytvořte soubor XML, který definuje konfiguraci [veřejného terminálu.](#ppkioskconfig) Pokud používáte soubor XML, nezapomeňte zahrnout [rozložení Start](#start-layout-for-hololens).  
- Volitelně můžete použít vlastní rozložení Start s Intune nebo jinými službami MDM. Další informace najdete v tématu [Spuštění souboru rozložení pro MDM (Intune a další).](#start-layout-file-for-mdm-intune-and-others)

1. Vyberte **Cílový Windows 10 v režimu S Ne.**  >    
>[!NOTE]  
> Režim S se nepodporuje v Windows Holographic for Business.

1. Vyberte **Typ přihlášení uživatele** Uživatel nebo skupina Azure AD nebo Typ přihlášení uživatele HoloLens návštěvníka a pak přidejte jednu nebo více skupin uživatelů  >     >  nebo účtů.  

   Prostředí veřejného terminála mohou používat jenom  uživatelé, kteří patří do skupin nebo účtů, které zadáte v části Typ přihlášení uživatele.

1. Vyberte jednu nebo více aplikací pomocí následujících možností:
   - Pokud chcete přidat nahranou obchodní aplikaci, vyberte **Přidat aplikaci** ze Storu a pak vyberte požadovanou aplikaci.
   - Pokud chcete přidat aplikaci zadáním jejího AUMID, vyberte **Přidat podle AUMID** a pak zadejte AUMID aplikace. [Zobrazení seznamu dostupných identifikátorů AUMID](#aumids)

Dalším krokem je [přiřazení](#mdmassign) profilu ke skupině.

### <a name="mdm-step-4-ndash-assign-the-kiosk-configuration-profile-to-a-group"></a><a id="mdmassign"></a>MDM, krok 4: Přiřazení konfiguračního profilu &ndash; veřejného terminálu ke skupině

Na stránce **Přiřazení konfiguračního** profilu veřejného terminálů nastavte, kam chcete konfiguraci veřejného terminálů nasadit. V nejjednodušším případě přiřadíte konfigurační profil veřejného terminálu ke skupině, která bude obsahovat HoloLens zařízení, když se zařízení zaregistruje do MDM.

### <a name="mdm-step-5-single-app-ndash-deploy-a-single-app-kiosk"></a><a id="mdmsingledeploy"></a>MDM, krok 5 (jedna aplikace) &ndash; Nasazení veřejného terminálu s jednou aplikací

Když používáte systém MDM, můžete zařízení zaregistrovat v MDM během spuštění počítače. Po dokončení OOBE se můžete snadno přihlásit k zařízení.

Během OOBE postupujte takto:

1. Přihlaste se pomocí účtu, který jste zadali v konfiguračním profilu veřejného terminálu.
1. Registrace zařízení Ujistěte se, že je zařízení přidané do skupiny, ke které je konfigurační profil veřejného terminálů přiřazený.
1. Počkejte na dokončení funkce OOBE, na stažení a instalaci aplikace ze Storu a na použití zásad. Pak zařízení restartujte.

Při příštím přihlášení k zařízení by se měla automaticky spustit aplikace veřejného terminálu.

Pokud v tuto chvíli konfiguraci veřejného terminálu nevidíte, [zkontrolujte stav přiřazení](/intune/configuration/device-profile-monitor).

### <a name="mdm-step-5-multi-app-ndash-deploy-a-multi-app-kiosk"></a><a id="mdmmultideploy"></a>MDM, krok 5 (více aplikací) &ndash; Nasazení veřejného terminálu s více aplikacemi

Když používáte systém MDM, můžete zařízení připojit ke svému tenantovi Azure AD a zaregistrovat ho v MDM během spuštění počítače. V případě potřeby zadejte uživatelům informace o registraci, aby je měli k dispozici během procesu OOBE.

> [!NOTE]  
> Pokud jste přiřadili konfigurační profil veřejného terminálů ke skupině, která obsahuje uživatele, ujistěte se, že jeden z těchto uživatelských účtů je prvním účtem pro přihlášení k zařízení.

Během OOBE postupujte takto:

1. Přihlaste se pomocí účtu, který patří do **skupiny typů přihlášení** uživatele.
1. Registrace zařízení
1. Počkejte, až se stáhnou a nainstalují všechny aplikace, které jsou součástí konfiguračního profilu veřejného terminálu. Také počkejte na použití zásad.  
1. Po dokončení počátečního nastavení můžete nainstalovat další aplikace z Microsoft Storu nebo pomocí zkušebního načtení. [Požadované aplikace](/mem/intune/apps/apps-deploy#assign-an-app) pro skupinu, pro kterou zařízení patří k instalaci automaticky
1. Po dokončení instalace zařízení znovu spusťte.

Až se příště přihlásíte k zařízení pomocí účtu, který patří do **typu přihlášení uživatele**, aplikace veřejného terminálu by se měla automaticky spustit.

Pokud v tuto chvíli nevidíte konfiguraci veřejného terminálu, [Zkontrolujte stav přiřazení](/intune/configuration/device-profile-monitor).

## <a name="use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk"></a>Použití zřizovacího balíčku k nastavení veřejného terminálu pro jednu aplikaci nebo více aplikací

Pokud chcete nastavit celoobrazovkový režim pomocí zřizovacího balíčku, postupujte podle těchto kroků.

1. [Vytvořte soubor XML, který definuje konfiguraci veřejného terminálu.](#ppkioskconfig)včetně [počátečního rozložení](#start-layout-for-hololens).
2. [Přidejte soubor XML do zřizovacího balíčku.](#ppconfigadd)
3. [Balíček zřizování nainstalujte na HoloLens.](#ppapply)

### <a name="provisioning-package-step-1-ndash-create-a-kiosk-configuration-xml-file"></a><a id="ppkioskconfig"></a>Zřizovací balíček, krok 1 &ndash; Vytvoření souboru XML konfigurace veřejného terminálu

postupujte podle [obecných pokynů pro vytvoření souboru XML konfigurace veřejného terminálu pro Windows plochu](/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)s výjimkou následujících:

- nezahrnovat klasické Windows aplikace (Win32). HoloLens tyto aplikace nepodporuje.
- Pro HoloLens použijte [zástupný symbol pro začátek rozložení XML](#start-layout-for-hololens) .
- Volitelné: přidejte přístup hosta do konfigurace veřejného terminálu.

#### <a name="optional-add-guest-access-to-the-kiosk-configuration"></a><a id="ppkioskguest"></a>Volitelné: přidejte přístup hosta do konfigurace veřejného terminálu.

V části [ **CONFIGS** souboru XML](/windows/configuration/lock-down-windows-10-to-specific-apps#configs)můžete nakonfigurovat speciální skupinu s názvem **Návštěvníci** , která umožní hostům využívat veřejný terminál. Když je veřejný terminál nakonfigurovaný tak, aby podporoval speciální skupinu **návštěvníků** , přidá se na přihlašovací stránku možnost **Host**. Účet **Guest** nevyžaduje heslo a při odhlášení účtu se odstraní všechna data přidružená k tomuto účtu.

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

v sestavách [Windows holografická verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1) a vyšší:
- Konfigurace AAD a Nepřidání: podporuje jak automatické přihlašování, tak i účty návštěvníků, které jsou povolené pro celoobrazovkový režim.

##### <a name="non-aad-configuration"></a>Konfigurace jiného typu než AAD

1. Vytvořte zřizovací balíček, který:
    1. Nakonfiguruje nastavení modulu runtime/AssignedAccess tak, aby umožňoval účty návštěvníků.
    1. Volitelně můžete zařízení zaregistrovat v MDM (nastavení modulu runtime/pracoviště/registrace), aby se mohlo spravovat později.
    1. Nevytvářet místní účet
2. [Použijte zřizovací balíček](hololens-provisioning.md).

##### <a name="aad-configuration"></a>Konfigurace AAD

Zařízení připojená k AAD nakonfigurovaná pro celoobrazovkový režim se můžou přihlásit k účtu návštěvníka jediným klepnutím na tlačítko na přihlašovací obrazovce. Po přihlášení k účtu návštěvníka se zařízení nevyzve k opětovnému přihlášení, dokud se návštěvník výslovně odhlásí z nabídky Start nebo když se zařízení nerestartuje.

Automatické přihlašování návštěvníka se dá spravovat pomocí [vlastních zásad OMA-URI](/mem/intune/configuration/custom-settings-windows-10):

- Hodnota identifikátoru URI:./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon


| Zásady |Description |Konfigurace 
| --------------------------- | ------------- | -------------------- |
| MixedReality/VisitorAutoLogon | Umožňuje návštěvníkovi automatické přihlašování do veřejného terminálu. | 1 (Ano), 0 (ne, výchozí) |

#### <a name="placeholder-start-layout-for-hololens"></a><a id="start-layout-for-hololens"></a>Zástupný symbol začátku rozložení pro HoloLens

Pokud použijete [zřizovací balíček](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) ke konfiguraci veřejného terminálu s více aplikacemi, procedura vyžaduje počáteční rozložení. Přizpůsobení rozložení při spuštění není v Windows Holographic for Business podporováno. Proto budete muset použít zástupné počáteční rozložení.

> [!NOTE]  
> vzhledem k tomu, že veřejný terminál s jednou aplikací spouští aplikaci na veřejném terminálu, když se uživatel přihlásí, nepoužívá nabídka Start a nemusí mít počáteční rozložení.

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

Následující ukázku uložte jako soubor XML. tento soubor můžete použít při konfiguraci veřejného terminálu s více aplikacemi v Microsoft Intune (nebo v jiné službě MDM, která poskytuje profil veřejného terminálu).

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

1. otevřete [Windows návrháře konfigurace](https://www.microsoft.com/store/apps/9nblggh4tx22).
1. Vyberte **Upřesnit zřizování**, zadejte název projektu a pak vyberte **Další**.
1. vyberte **Windows 10 Holographic** a pak vyberte **další**.
1. Vyberte **Dokončit**. Otevře se pracovní prostor pro váš balíček.
1. Vyberte **nastavení modulu runtime**  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings**.
1. V prostředním podokně vyberte **Procházet** a vyhledejte a vyberte soubor XML konfigurace veřejného terminálu, který jste vytvořili.

   ![snímek obrazovky s polem MultiAppAssignedAccessSettings v návrháři konfigurace Windows](./images/multiappassignedaccesssettings.png)

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
   > Nevybírejte možnost **Povolit šifrování balíčku**. v zařízeních HoloLens toto nastavení způsobí selhání zřizování.
1. Vyberte **Další**.
1. Zadejte umístění výstupu, kde má zřizovací balíček při sestavení přejít. ve výchozím nastavení používá návrhář konfigurace Windows složku projektu jako umístění výstupu. Pokud chcete změnit umístění výstupu, vyberte **Procházet**. Po dokončení vyberte **Další**.
1. Vyberte **sestavení** pro zahájení sestavování balíčku. Zřizovací balíček netrvá déle, než se sestaví. Na stránce Build (sestavení) se zobrazí informace o projektu a indikátor průběhu indikuje stav sestavení.

### <a name="provisioning-package-step-3-ndash-apply-the-provisioning-package-to-hololens"></a><a id="ppapply"></a>Zřizovací balíček, krok 3, &ndash; použití zřizovacího balíčku na HoloLens

článek "konfigurace HoloLens pomocí zřizovacího balíčku" poskytuje podrobné pokyny k použití zřizovacího balíčku za následujících okolností:

- [během instalace můžete zpočátku použít zřizovací balíček, který se HoloLens](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).

- [zřizovací balíček můžete také použít pro HoloLens po instalaci](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup).

## <a name="use-the-windows-device-portal-to-set-up-a-single-app-kiosk"></a>použití portálu Windows zařízení k nastavení veřejného terminálu s jednou aplikací

pokud chcete nastavit celoobrazovkový režim pomocí portálu Windows zařízení, postupujte podle těchto kroků.

1. [nastavte zařízení HoloLens na používání portálu Windows zařízení](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal). portál zařízení je webový server na vašem HoloLens, ke kterému se můžete připojit z webového prohlížeče na svém počítači.

    > [!CAUTION]
    > když nastavíte HoloLens, abyste mohli používat portál zařízení, musíte na zařízení povolit vývojářský režim. vývojářský režim na zařízení, které má Windows Holographic for Business umožňuje vám načítat aplikace. Toto nastavení však vytvoří riziko, že uživatel může instalovat aplikace, které nebyly certifikovány Microsoft Store. Správci můžou zablokovat možnost Povolit vývojářský režim pomocí nastavení **odemčení ApplicationManagement/AllowDeveloper** v [zásadách CSP](/windows/client-management/mdm/policy-configuration-service-provider). [Přečtěte si další informace o režimu pro vývojáře.](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. Na počítači se připojte k HoloLens pomocí [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) nebo [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb).

1. Proveďte některou z následujících akcí:
   - Pokud se ke službě Windows Portál zařízení poprvé, [vytvořte uživatelské jméno a heslo.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - Zadejte uživatelské jméno a heslo, které jste nastavili dříve.

    > [!TIP]
    > Pokud se v prohlížeči zobrazí chyba certifikátu, postupujte podle [těchto kroků pro řešení potíží.](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)

1. V Windows Portál zařízení vyberte **Bezobrazovový režim.**

1. Vyberte **Povolit bezobrazovový režim,** vyberte aplikaci, která se má spustit při spuštění zařízení, a pak vyberte **Uložit.**

    ![Bezobrazovový režim](images/kiosk.png)
1. Restartujte HoloLens. Pokud máte stále otevřenou Portál zařízení, můžete v  horní části stránky vybrat Restartovat.

> [!NOTE]
> Bezobrazovový režim je možné nastavit přes REST API služby Portál zařízení tak, že se pomocí POST nastaví /api/holographic/kioskmode/settings s jedním povinným parametrem řetězce dotazu ("kioskModeEnabled&quot; s hodnotou &quot;true&quot; nebo &quot;false") a jedním volitelným parametrem ("startupApp" s hodnotou názvu balíčku). Mějte na paměti, že Portál zařízení je určený pouze pro vývojáře a neměl by být povolený na zařízeních, která nejsou pro vývojáře. Změny REST API v budoucích aktualizacích a verzích.

## <a name="more-information"></a>Další informace

### <a name="watch-how-to-configure-a-kiosk-by-using-a-provisioning-package"></a>Podívejte se, jak nakonfigurovat beziosk pomocí zřizovacího balíčku.  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <a name="global-assigned-access--kiosk-mode"></a>Globální přiřazený přístup – Bezobrazovový režim
- Snížená správa identit pro bezobrazovkové režimy tím, že se povolí nová metoda veřejného terminálu, která na úrovni systému použije režim veřejného terminálu.

Tato nová funkce umožňuje správci IT nakonfigurovat zařízení HoloLens 2 pro režim veřejného terminálů s více aplikacemi, který je použitelný na úrovni systému, nemá žádné spřažení s žádnou identitou v systému a vztahuje se na všechny uživatele, kteří se k zařízení přihlásí. Další podrobnosti [HoloLens této nové funkci](hololens-global-assigned-access-kiosk.md) najdete v dokumentaci k veřejného terminálu s globálním přiřazeným přístupem.

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
- Windows Holographic, verze 20H2 – pokud má zařízení konfiguraci veřejného terminálů, což je kombinace přístupu přiřazeného globálním i přiřazeného členovi skupiny AAD. Pokud se určení členství ve skupině AAD nezdaří, uživateli se zobrazí nabídka "nic se nezobrazí v nabídce Start".

![Obrázek toho, jak vypadá bezobrazovový režim, když selže](images/hololens-kiosk-failure-behavior.png )


- Počínaje [Windows Holographic verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1)vyhledá bezioskový režim před zobrazením prázdné nabídky Start možnost Globální přiřazený přístup. Prostředí veřejného terminálů se v případě selhání v beznaiosku skupiny AAD propadne do globální konfigurace veřejného terminálu (pokud je k dispozici).

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>Ukládání členství ve skupině Azure AD do mezipaměti pro offline bezobrazovkové režimy

- Bezpečnější bezobrazovkové režimy eliminují selhání dostupných aplikací v bezobrazovkovém režimu.
- Povolili jste offline terminály pro použití se skupinami Azure AD po dobu až 60 dnů.

Tato zásada určuje, kolik dní může být mezipaměť členství ve skupinách Azure AD použita pro konfigurace přiřazeného přístupu, které cílí na skupiny Azure AD pro přihlášené uživatele. Jakmile je hodnota této zásady nastavená na hodnotu větší než 0, použije se mezipaměť, jinak se tato hodnota nenastaví.  

Název: AADGroupMembershipCacheValidityInDays Hodnota identifikátoru URI: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

Min – 0 dní  
Max. – 60 dnů 

Postup správných použití těchto zásad: 
1. Vytvořte profil konfigurace zařízení pro beznaiosk cílení na skupiny Azure AD a přiřaďte ho HoloLens zařízením. 
1. Vytvořte vlastní konfiguraci zařízení založenou na OMA URI, která nastaví tuto hodnotu zásady na požadovaný počet dní (> 0) a přiřadí ji HoloLens zařízením. 
    1. Do textového pole OMA-URI by se měla zadat hodnota URI ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays.
    1. Hodnota může být v rozmezí od minimálního do maximálního povoleného.
1. Zaregistrujte HoloLens zařízení a ověřte, že se na zařízení použijí obě konfigurace. 
1. Nechte uživatele Azure AD 1 přihlásit se, když je k dispozici internet, po úspěšném potvrzení přihlášení uživatele a úspěšného členství ve skupině Azure AD se vytvoří mezipaměť. 
1. Uživatel Azure AD 1 teď může HoloLens režim offline a použít ho pro bezioskový režim, pokud hodnota zásad umožňuje počet dní X. 
1. Kroky 4 a 5 je možné opakovat pro libovolného jiného uživatele Azure AD N. Klíčovým bodem je, že každý uživatel Azure AD se musí přihlásit k zařízení pomocí internetu, takže aspoň jednou můžeme určit, že jsou členem skupiny Azure AD, na kterou je cílem konfigurace veřejného terminálu. 
 
> [!NOTE]
> Dokud se pro uživatele Azure AD neprovádí krok 4, bude docházet k chování při selhání uvedeném v odpojených prostředích. 


## <a name="xml-kiosk-code-samples-for-hololens"></a>Ukázky kódu XML veřejného terminálu pro HoloLens

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a>Bezobrazovový režim s více aplikacemi, který cílí na skupinu Azure AD. 
Tento bezobrazovk nasadí bezobrazovk, který uživatelům ve skupině Azure AD povolí bezobrazovkové režimy, který zahrnuje tyto tři aplikace: Nastavení, Remote Assist a Centrum Feedback. Pokud chcete tuto ukázku upravit tak, aby se používala okamžitě, nezapomeňte změnit identifikátor GUID zvýrazněný níže tak, aby odpovídal vaší vlastní skupině Azure AD. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a>Bezobrazovový režim s více aplikacemi, který cílí na účet Azure AD.
Tento bezobrazovk nasadí veřejného terminál pro jednoho uživatele. Bude mít povolený bezobrazovk, který obsahuje tyto 3 aplikace: Nastavení, Remote Assist a Centrum Feedback. Pokud chcete tuto ukázku upravit tak, aby se používala okamžitě, nezapomeňte změnit účet zvýrazněný níže tak, aby odpovídal vašemu vlastnímu účtu Azure AD. 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

