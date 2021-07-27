---
title: Insider Preview pro Microsoft HoloLens
description: Naučte se, jak začít s buildy Insider, a poskytněte vám užitečnou zpětnou vazbu k naší další aktualizaci operačního systému HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 12c5586f931487d871d4b6e98992ca0047b2adbf
ms.sourcegitcommit: 5130823947caffd2a444e9d8fb15cd24cbb6414c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/24/2021
ms.locfileid: "114659195"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider Preview pro Microsoft HoloLens

Vítejte v nejnovějších buildech Insider Preview pro HoloLens! Je jednoduché začít a poskytnout cennou zpětnou [vazbu k naší](hololens-insider.md#start-receiving-insider-builds) další hlavní aktualizaci operačního systému pro HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Poznámky k verzi programu Insider

s radostí zahájíme nové funkce, které Windows insidery. Pro nejnovější aktualizace budou nové buildy zacházet s kanály pro vývoj a beta verze. tato stránka bude i nadále aktualizována, protože přidáváme další funkce a aktualizace našich Windows buildů Insider. Využijte rádi a připravte se na tyto aktualizace ke své realitě.

| Funkce                 | Popis                | Uživatel nebo scénář | Sestavení představeno |
|-------------------------|----------------------------|--------------|------------------|
| [CSP se mění pro vytváření sestav HoloLens podrobnosti](#csp-changes-for-reporting-hololens-details) | Noví poskytovatelé CSP pro k dotazování na data | Správci IT    | 20348,1403                 |
| [Zásady automatického přihlašování řízené zprostředkovatelem CSP](#auto-login-policy-controlled-by-csp) | Používá se k automatickému přihlášení k účtu. | Správci IT | 20348,1405 |
| [Podpora souborů PFX pro správce certifikátů](#pfx-file-support-for-certificate-manager) | přidání certifikátů PFX prostřednictvím Nastavení uživatelského rozhraní | Koncový uživatel | 20348,1405 |
| [zobrazit pokročilou diagnostickou sestavu v Nastavení v HoloLens](#view-advanced-diagnostic-report-in-settings-on-hololens) | Zobrazit diagnostické protokoly MDM na zařízení | Řešení potíží | 20348,1405 |
| [Upozornění offline diagnostiky](#offline-diagnostics-notifications) | Audiovizuální zpětná vazba pro shromažďování protokolů | Řešení potíží | 20348,1405 |
| [Používejte pouze aplikace privátního úložiště pro Microsoft Store](#use-only-private-store-apps-for-microsoft-store) | Konfigurace aplikace pro Store tak, aby zobrazovala pouze aplikace z organizace | Správce IT | 20348,1408 |

### <a name="csp-changes-for-reporting-hololens-details"></a>CSP se mění pro vytváření sestav HoloLens podrobnosti

- představeno v Windows build Insider, 20348,1403

následující poskytovatelé csp byli aktualizováni novými způsoby, jak ohlásit informace ze zařízení HoloLens.

#### <a name="devdetail-csp---free-storage"></a>DevDetail CSP – bezplatná Storage

DevDetail CSP nyní také oznamuje volné místo v úložišti HoloLens zařízení. hodnota by měla odpovídat hodnotě zobrazené na stránce Storage aplikace Nastavení. Následuje konkrétní uzel, který obsahuje tyto informace.

- ./DevDetail/Ext/Microsoft/FreeStorage (pouze operace GET)

#### <a name="devicestatus-csp---ssid-and-bssid"></a>DeviceStatus CSP – SSID a BSSID

DeviceStatus CSP nyní také hlásí identifikátory SSID a BSSID Wi-Fi sítě, se kterou HoloLens aktivně připojená. Níže jsou uvedené konkrétní uzly, které obsahují tyto informace.

- *Adresa MAC adaptéru Wi-Fi*/SSID/Vendor/MSFT/DeviceStatus/NetworkIdentifiers/
- *Adresa MAC adaptéru Wi-Fi*/BSSID/Vendor/MSFT/DeviceStatus/NetworkIdentifiers/

Příklad objektu BLOB SyncML (pro dodavatele MDM) pro dotazování na NetworkIdentifiers

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="auto-login-policy-controlled-by-csp"></a>Zásady automatického přihlašování řízené zprostředkovatelem CSP

Tato nová zásada AutoLogonUser určuje, jestli se uživatel automaticky přihlašuje. Někteří zákazníci chtějí nastavit zařízení, která jsou vázaná na identitu, ale nechtějí žádné přihlašovací prostředí. Imagine vyzvednutí zařízení a okamžitě pomocí programu vzdálená pomoc. nebo využijte výhod, které vám umožní rychle distribuovat HoloLens zařízení a umožnit koncovým uživatelům urychlení přihlašovacích údajů.

Když je zásada nastavená na neprázdnou hodnotu, určí se e-mailová adresa uživatele automatického přihlašování. Zadaný uživatel se musí k zařízení přihlašovat aspoň jednou, aby se povolilo automatické přihlašování.

OMA-URI nové `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` hodnoty řetězce zásad

- Uživatel se stejnou e-mailovou adresou bude mít povoleno automatické přihlašování.

V zařízení, na kterém je tato zásada nakonfigurovaná, se uživatel zadaný v zásadě musí přihlašovat aspoň jednou. Následná restartování zařízení po prvním přihlášení budou mít zadaného uživatele automaticky přihlášeni. Podporuje se jenom jeden uživatel s automatickým přihlašováním. Po povolení se automaticky přihlášený uživatel nebude moci odhlásit ručně. Pokud se chcete přihlásit jako jiný uživatel, musí být tato zásada nejdřív zakázaná.

> [!NOTE]
> - Některé události, jako jsou hlavní aktualizace operačního systému, můžou vyžadovat, aby zadaný uživatel znovu přihlásí k zařízení a obnovil chování automatického přihlašování. 
> - Automatické přihlašování se podporuje jenom pro uživatele MSA a AAD.

### <a name="pfx-file-support-for-certificate-manager"></a>Podpora souborů PFX pro správce certifikátů

představeno v Windows build Insider build 20348,1405. Přidali jsme podporu [Správce certifikátů](certificate-manager.md) pro teď použití certifikátů. pfx. když uživatel přejde na **Nastavení**  >  **Update &**  >  **certifikáty** zabezpečení a vybere možnost **nainstalovat certifikát** , uživatelské rozhraní teď podporuje soubor certifikátu. pfx.
Uživatelé mohou importovat certifikát. pfx s privátním klíčem do úložiště uživatele nebo do úložiště počítače.

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a>zobrazit pokročilou diagnostickou sestavu v Nastavení v HoloLens

Pro spravovaná zařízení při řešení potíží ověřte, že se používá očekávaná konfigurace zásad, což je důležitý krok. dříve se tato nová funkce musela po exportu protokolů pro diagnostiku mdm shromážděných prostřednictvím **Nastavení**  ->  **účtů**  >  **přistupovat do práce nebo do školy** a vybrat možnost **exportovat protokoly správy** a zobrazit je na nejbližším počítači v blízkosti zařízení.

Diagnostiku MDM je teď možné zobrazit na zařízení pomocí prohlížeče Edge. Chcete-li snadněji zobrazit diagnostickou zprávu MDM, přejděte na stránku přístup do práce nebo do školy a vyberte **Zobrazit pokročilou diagnostickou sestavu**. Tato akce vygeneruje a otevře sestavu v novém okně Edge.

![zobrazit pokročilou diagnostickou sestavu v aplikaci Nastavení.](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a>Upozornění offline diagnostiky

Tato aktualizace pro existující funkci se nazývá [offline Diagnostika](hololens-diagnostic-logs.md#offline-diagnostics). Dříve neexistoval žádný jasný indikátor pro uživatele, kteří aktivovali diagnostické shromažďování nebo dokončili.
nově přidaná v Windows buildů Insider existují dvě formy audiovizuální zpětné vazby pro Offline diagnostiku. První je oznámení, která se zobrazují pro obě při spuštění a dokončení shromažďování. Ty se zobrazí, když je uživatel přihlášený a obsahuje vizuály.

![Informační zprávy pro shromažďování protokolů.](./images/logcollection1.jpg)

![Informační zprávy, když je shromažďování protokolů dokončeno.](./images/logcollection2.jpg)
 
Vzhledem k tomu, že uživatelé často používají offline diagnostiku jako záložní mechanismus pro shromažďování protokolů, kdy nemají přístup k zobrazení, nemůžete se přihlásit nebo jsou pořád v počátečním souboru OOBE, při shromažďování protokolů se taky dohraje zvukový signál. Tento zvuk se přehraje kromě informačního oznámení.

Tato nová funkce bude povolená, když se vaše zařízení aktualizuje a nebude nutné ho povolit ani spravovat. V případě, že tuto novou zpětnou vazbu nelze zobrazit nebo zobrazit, bude i nadále vygenerována offline Diagnostika.

Doufáme, že s tímto novějším přidáním audiovizuální zpětné vazby je snazší shromažďovat diagnostická data a rychleji řešit problémy.

### <a name="use-only-private-store-apps-for-microsoft-store"></a>Pro Microsoft Store používat jenom soukromé aplikace ze Storu

Zásada RequirePrivateStoreOnly je povolená pro HoloLens. tato zásada umožňuje, aby byla aplikace Microsoft Store nakonfigurovaná tak, aby zobrazovala jenom privátní úložiště nakonfigurované pro vaši organizaci. Omezení přístupu pouze k aplikacím, které byly k dispozici.

Další informace o [ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

### <a name="fixes-and-improvements"></a>Opravy a vylepšení:

- Opravili [jsme známý problém s portálem zařízení, kde se nestáhly uzamčené soubory.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)
- Opravili [jsme známý problém s Portál zařízení s časovými limity nahrávání a stahování souborů.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)
- Řeší problémy související s hlášením vlastností dodržování předpisů HoloLens zařízeními. K aktivaci správných sestav v sestaveních Insider může být nutné restartovat počítač.  
- Aktualizace dodácí verze Remote Assistu, která je nainstalovaná na aktuálních flash serverech.


## <a name="start-receiving-insider-builds"></a>Zahájení přijímání sestavení Insider

> [!NOTE]
> Pokud jste to ještě neudělali, restartujte zařízení, aktualizujte stav a získejte nejnovější build.
> - Hlasový příkaz Restartovat zařízení funguje dobře. 
> - Můžete také zvolit tlačítko restartování v Nastavení/Windows Insider Program.
>
> Na back-endu jsme měli chybu, se kterou jste se mohli setkat, a tím se vrátíte na cestu.

Na zařízení HoloLens 2 přejděte na **Nastavení** Update & Security Windows Insider Program a  >    >   vyberte **Začínáme.** Propojte účet, který jste použili k registraci, Windows Insider.

Windows insider se teď přesouvá na Kanály. Kanál **Fast** se stane **vývojový** kanál, kanál **Slow** se stane **kanálem Beta kanál** a kanál release **preview** se stane **kanálem Release Preview**. Toto mapování vypadá takhle:

![Windows Vysvětlení kanálů insider](images/WindowsInsiderChannels.png)

Další informace najdete v tématu [Představení kanálů Windows Insider na](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) Windows blogech.
Pak vyberte **Aktivní vývoj Windows,** zvolte, jestli chcete dostávat Dev **Channel** nebo Beta kanál **sestavení,** a zkontrolujte podmínky programu.
Dokončete **> Potvrdit a** restartovat. Po restartování zařízení přejděte do Nastavení > **Update & Security >** Vyhledejte aktualizace a získejte nejnovější build.

### <a name="update-error-0x80070490-work-around"></a>Aktualizace 0x80070490 obchádky

Pokud při aktualizaci na kanálu pro 0x80070490 nebo beta verzi dojde k chybě aktualizace, vyzkoušejte následující krátkodobé řešení. Zahrnuje přesunutí kanálu insider, vyzvednutí aktualizace a pak přesunutí kanálu Insider zpět.

#### <a name="stage-one---release-preview"></a>Fáze 1 – Verze Preview

1.  Nastavení, & Security a Windows Insider Program vyberte Kanál Release **Preview.**

2.  Nastavení, Aktualizace & Security, Windows Update, **Kontrola aktualizací**. Po aktualizaci pokračujte k fázi 2.

#### <a name="stage-two---dev-channel"></a>Fáze 2 – Vývojový kanál

1. Nastavení, Aktualizovat & Security, Windows Insider Program vyberte **Dev Channel**.

2. Nastavení, Aktualizace & Security, Windows Update, **Kontrola aktualizací**.

## <a name="ffu-download-and-flash-directions"></a>Pokyny ke stažení ffu a flash

Pokud chcete testovat pomocí ffu podepsaného letem, musíte nejprve letět s odemknutým zařízením před flash flash diskem ffu.

1. Na počítači:
    1. Stáhněte si ffu do počítače z [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Nainstalujte ARC (Advanced Recovery Companion) z Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. Na HoloLens – Letové odemčení: Otevřete **Nastavení** Update & Security Windows Insider Program a pak  >    >   se zaregistrujte a restartujte zařízení.

1. Flash FFU – Nyní můžete flash diskem podepsaného letem FFU použít ARC.

### <a name="provide-feedback-and-report-issues"></a>Poskytnutí zpětné vazby a hlášení problémů

Pokud chcete [poskytnout Centrum Feedback a nahlásit problémy,](hololens-feedback.md) použijte aplikaci HoloLens na svém počítači. Pomocí Centrum Feedback zajistíte, že se zahrnou všechny potřebné diagnostické informace, které našim technikům pomůžou rychle ladit a vyřešit problém.  Problémy s čínštinou a japonštinou HoloLens by měly být hlášeny stejným způsobem.

> [!NOTE]
> Nezapomeňte přijmout výzvu s dotazem, jestli Centrum Feedback přístup ke složce  Dokumenty (po zobrazení výzvy vyberte Ano).

## <a name="note-for-developers"></a>Poznámka pro vývojáře

Vítá vás a doporučujeme, abyste si zkusili vyvíjet aplikace pomocí buildů insider HoloLens.  Pokud chcete [začít, HoloLens si prohlédněte dokumentaci pro](https://developer.microsoft.com/windows/mixed-reality/development) vývojáře. Stejné pokyny fungují i se sestaveními insider HoloLens.  Můžete použít stejná sestavení Unity a Visual Studio, které už používáte pro HoloLens vývoj.

## <a name="stop-receiving-insider-builds"></a>Zastavení přijímání sestavení Insider

Pokud už nechcete dostávat buildy Insider služby Windows Holographic, můžete to vyjádřit výslovně, když HoloLens [](hololens-recovery.md) používá produkční build, nebo můžete obnovit zařízení pomocí doplňku Advanced Recovery Companion a obnovit zařízení na verzi Windows Holographic, která není z programu Insider.

> [!CAUTION]
> Existuje známý problém, kdy se uživatelům, kteří po ruční přeinstalaci nové verze Preview buildu ruší registraci ve verzi Insider Preview, zobrazí modrá obrazovka. Potom musí zařízení obnovit ručně. Úplné podrobnosti o tom, jestli by vás to ovlivnilo nebo ne, najdete v části Další informace o tomto [známém problému.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Pokud chcete ověřit, HoloLens vaše aplikace používá produkční sestavení:

1. Přejděte na **Nastavení > System > About** a vyhledejte číslo sestavení.

1. [Podívejte se na poznámky k verzi pro čísla produkčních buildů](hololens-release-notes.md).

Odhlášení sestavení Insider:

1. Na HoloLens produkčním sestavení přejděte na **Nastavení > Update & Security > Windows Insider Program** a vyberte Zastavit sestavení **Insider.**

1. Postupujte podle pokynů a odhlásit zařízení.
