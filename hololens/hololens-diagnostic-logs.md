---
title: shromažďování a používání diagnostických informací z HoloLens zařízení
description: naučte se shromažďovat, používat a uchovávat diagnostické informace z HoloLensch zařízení.
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/15/2020
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
ms.custom:
- CI 115131
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: medium
keywords: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 96fe9492da035747a22123ee1cd0c1481cd821a4f2e549b6414a21810ec268d6
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665297"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>shromažďování a používání diagnostických informací z HoloLens zařízení

HoloLens uživatelé a správci si můžou ze čtyř různých metod shromažďovat diagnostické informace z HoloLens:

- Aplikace centra Feedback
- DiagnosticLog CSP
- aplikace Nastavení
- Diagnostika offline

> [!IMPORTANT]  
> Protokoly diagnostiky zařízení obsahují identifikovatelné osobní údaje (PII), například informace o tom, jaké procesy nebo aplikace uživatel spouští během typických operací. pokud se zařízení HoloLens sdílí více uživatelů (například se uživatelé přihlašují ke stejnému zařízení pomocí různých účtů Microsoft Azure Active Directory (Azure AD)), diagnostické protokoly mohou obsahovat informace PII, které platí pro více uživatelů. Další informace najdete v tématu [prohlášení o zásadách ochrany osobních údajů společnosti Microsoft](https://privacy.microsoft.com/privacystatement).

Následující tabulka porovnává různé metody kolekce. Názvy metod odkazují na podrobnější informace v oddílech, které následují po tabulce.

|Metoda |Požadavky |Umístění dat |Přístup k datům a jejich použití |Uchovávání dat |
| --- | --- | --- | --- | --- |
|[Centrum Feedback](#feedback-hub) |Připojení k síti a Internetu<br /><br />Aplikace centra Feedback<br /><br />Oprávnění k nahrání souborů do cloudu Microsoftu |Cloud Microsoftu<br /><br />zařízení HoloLens (volitelné) |Pomoc požadavky uživatelů, souhlasí s podmínkami použití a nahrává data<br /><br />Zaměstnanci Microsoftu si data zobrazí v souladu s podmínkami použití. |Data v cloudu se uchovávají po dobu, která je definovaná pomocí ochrany osobních údajů nové generace (NGP). Data se pak odstraní automaticky.<br /><br />Data v zařízení může kdykoli odstranit uživatel, který má oprávnění vlastníka nebo **správce** **zařízení** . |
|[Nastavení Poradce při potížích](#settings-troubleshooter) |aplikace Nastavení |HoloLens zařízení<br /><br />Připojený počítač (volitelné) |Uživatel ukládá data a přistupuje k datům jenom uživatel (Pokud uživatel konkrétně nesdílí data s jiným uživatelem). |Data se na zařízení uchovávají, dokud ho uživatel neodstraní. * |
|[DiagnosticLog CSP](#diagnosticlog-csp) |Síťové připojení<br /><br />Prostředí MDM, které podporuje zprostředkovatele CSP pro DiagnosticLog |Správce nakonfiguruje umístění úložiště. |Ve spravovaném prostředí uživatel implicitně souhlasí s přístupem správce k datům.<br /><br />Správce nakonfiguruje role přístupu a oprávnění. | Data se uchovávají v cloudovém úložišti a správce nakonfiguruje zásady uchovávání informací. |
|[Diagnostika offline](#offline-diagnostics) |Konfigurace zařízení:<ul><li>Zapnuté a připojené k počítači</li><li>Tlačítka napájení a hlasitosti fungují</li></ul> |HoloLens zařízení<br /><br />Připojený počítač |Uživatel ukládá data a přistupuje k datům jenom uživatel (Pokud uživatel konkrétně nesdílí data s jiným uživatelem). |Data se na zařízení uchovávají, dokud ho uživatel neodstraní. |

* Koncový uživatel zodpovídá za sdílení protokolů zodpovědnou s někým jiným. Tyto soubory jsou primárně užitečné při kontaktování zákaznických služeb a podpory.  

## <a name="feedback-hub"></a>Centrum Feedback

uživatel HoloLens může použít desktopovou aplikaci centra Feedback v Microsoft k posílání diagnostických informací do podpora Microsoftu. Podrobnosti a podrobné pokyny najdete v tématu o tom, jak [nám sdělit svůj názor](hololens-feedback.md).  

> [!NOTE]  
> **Komerční nebo podnikoví uživatelé:** pokud použijete aplikaci centra Feedback k nahlášení problému, který souvisí s MDM, zřizováním nebo jakýmkoli jiným aspektem správy zařízení, změňte kategorii aplikace na **Enterprise**  >  **kategorie zařízení** pro správu.

>[!IMPORTANT]
> Abychom zajistili nejlepší možnou dostupnost dat pro řešení problémů, důrazně doporučujeme, abyste si nastavili telemetrii zařízení jako **volitelnou**. tuto hodnotu můžete nastavit během představování mimo prostředí (OOBE) nebo pomocí aplikace **Nastavení** . pokud to chcete provést pomocí Nastavení, vyberte **Start > Nastavení > ochrany osobních údajů > > diagnostiky aplikací**.
### <a name="prerequisites"></a>Požadavky

- Zařízení je připojené k síti.
- Aplikace centra Feedback je dostupná na stolním počítači uživatele a uživatel může nahrávat soubory do cloudu Microsoftu.

### <a name="data-locations-access-and-retention"></a>Umístění dat, přístup a uchování

Když souhlasíte s podmínkami použití centra zpětné vazby, uživatel výslovně souhlasí s uložením a využitím dat (jak je definováno v této smlouvě).

Centrum zpětné vazby poskytuje dvě místa, kde si uživatel bude ukládat diagnostické informace:

- **Cloud Microsoftu**. Data, která uživatel nahraje pomocí aplikace centra feedback, se ukládají po dobu v počtu dní, který je v souladu s požadavky nové generace ochrany osobních údajů (NGP). Zaměstnanci Microsoftu můžou k přístupu k informacím během této doby používat prohlížeč kompatibilní s NGP.

   > [!NOTE]  
   > Tyto požadavky platí pro data ve všech kategoriích centra zpětné vazby.

- **zařízení HoloLens**. Při ukládání sestavy do centra Feedback může uživatel vybrat možnost **Uložit místní kopii diagnostiky a přílohy vytvořené při poskytování zpětné vazby**. pokud uživatel tuto možnost vybere, centrum zpětné vazby uloží kopii diagnostických informací na zařízení HoloLens. Tyto informace zůstávají k dispozici uživateli (nebo komukoli, který používá tento účet k přihlášení do HoloLens). Aby bylo možné tyto informace odstranit, musí mít uživatel na zařízení oprávnění vlastníka nebo **správce** **zařízení** . uživatel, který má příslušná oprávnění, se může přihlásit do centra pro zpětnou vazbu, vybrat **Nastavení**  >  **zobrazit diagnostické protokoly** a odstranit informace.

## <a name="settings-troubleshooter"></a>Nastavení Poradce při potížích

uživatel HoloLens může pomocí aplikace **Nastavení** na zařízení řešit problémy a shromažďovat diagnostické informace. Postupujte takto:

1. otevřete aplikaci Nastavení a vyberte stránku **aktualizace**  >  **řešení potíží** se zabezpečením &.
1. Vyberte příslušnou oblast a vyberte **Spustit**.
1. Reprodukujte problém.
1. po reprodukování problému se vraťte do Nastavení a pak vyberte **zastavit**.

uživatel může také nakonfigurovat chování záložní diagnostiky z aplikace **Nastavení** . Pokud chcete nakonfigurovat toto nastavení, přejděte na stránku **ochrany osobních údajů – > Poradce při potížích** .
> [!NOTE]
> Pokud je pro zařízení nakonfigurovaná zásada MDM, uživatel nebude moct toto chování přepsat.

### <a name="os-update-troubleshooter"></a>Poradce při potížích s aktualizací operačního systému
v sestavách [Windows holografická verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1) a vyšší:
- kromě předchozích poradců při potížích v aplikaci Nastavení byla přidána nová poradce při potížích s přidáním nové aplikace Nastavení pro aktualizace operačního systému. přejděte na **Nastavení > aktualizace & zabezpečení > řešení potíží – > web Windows Update** a vyberte **spustit**. Díky tomu můžete shromažďovat trasování a při reprodukci problému s aktualizacemi operačního systému pomoct lépe při řešení problémů s vaším IT nebo podporou.
### <a name="prerequisites"></a>Požadavky

- aplikace **Nastavení** je nainstalovaná na zařízení a je k dispozici pro uživatele.

### <a name="data-locations-access-and-retention"></a>Umístění dat, přístup a uchování

Vzhledem k tomu, že uživatel spustí shromažďování dat, uživatel implicitně souhlasí s úložištěm diagnostických informací. Přístup k datům může získat pouze uživatel, nebo kdokoli, se kterým uživatel sdílí data.

Diagnostické informace jsou uloženy v zařízení. Pokud je zařízení připojené k počítači uživatele, tyto informace se taky nacházejí v počítači v následujícím souboru:

> tento počítač \\ \<*HoloLens device name*> \\ interní Storage \\ dokumenty \\ Trace \<*ddmmyyhhmmss*> . etl

> [!NOTE]  
> v této cestě k souboru a názvu \<*HoloLens device name*> představuje název HoloLens zařízení a \<*ddmmyyhhmmss*> představuje datum a čas vytvoření souboru.

Diagnostické informace zůstanou v těchto umístěních, dokud je uživatel neodstraní.

## <a name="diagnosticlog-csp"></a>DiagnosticLog CSP

V prostředí Mobile Správa zařízení (MDM) může správce IT použít poskytovatele konfiguračních služeb [DiagnosticLog ke](/windows/client-management/mdm/diagnosticlog-csp) konfiguraci nastavení diagnostiky na zaregistrovaných HoloLens zařízeních. Správce IT může tato nastavení nakonfigurovat tak, aby shromažďovala protokoly z zaregistrovaná zařízení.

Další informace:
- [Shromažďování diagnostiky z Windows zařízení](/mem/intune/remote-actions/collect-diagnostics)
- [Intune Public Preview – Windows 10 Diagnostika zařízení](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-public-preview-windows-10-device-diagnostics/ba-p/2179712#:~:text=This%20first%20release%20of%20device%20diagnostics%20utilizes%20the,taking%20about%205%20minutes%20from%20start%20to%20finish.)

### <a name="prerequisites"></a>Požadavky

- Zařízení je připojené k síti.
- Zařízení je zaregistrované v prostředí MDM, které podporuje diagnostické protokoly CSP.

### <a name="data-locations-access-and-retention"></a>Umístění dat, přístup a uchovávání

Vzhledem k tomu, že je zařízení součástí spravovaného prostředí, uživatel implicitně souhlasí s přístupem pro správu k diagnostickým informacím.

Správce IT používá poskytovatele CSP DiagnosticLog ke konfiguraci zásad ukládání, uchovávání a přístupu k datům, včetně zásad, které řídí následující:

- Cloudová infrastruktura, do které se ukládají diagnostické informace.
- Doba uchovávání diagnostických informací.
- Oprávnění, která řídí přístup k diagnostickým informacím.

## <a name="offline-diagnostics"></a>Offline diagnostika
V situacích, kdy zařízení nemůže shromažďovat diagnostiku prostřednictvím Centrum Feedback nebo Nastavení poradce při potížích, můžete shromažďovat diagnostiku ručně. Jedním ze scénářů, kdy je to nezbytné, je situace, kdy se zařízení nemůže připojit Wi-Fi nebo nemáte přístup k jiným metodám uvedeným výše. Diagnostika shromažďuje výpisy stavu systému a protokoly ze zařízení, které pomáhají technikovi podpory Microsoftu izolovat problémy.

Funguje to, když se zařízení zobrazí v Průzkumník souborů po jeho připojení k počítači pomocí kabelu USB.

> [!NOTE]
> Generování a správa offline diagnostiky se řídí různě v závislosti na verzi operačního systému. Dříve byla řízena nastavením telemetrie, ale teď je přímo řízená prostřednictvím zásad MDM. Pokud je tato možnost zakázaná nastavením nebo zásadou MDM, není možné pomocí tohoto mechanismu shromažďovat diagnostické protokoly.

Chování před [Windows Holographic verze 20H2:](hololens-release-notes.md#windows-holographic-version-20h2)
 - Offline diagnostika je povolená jenom v případě, že uživatel prochází prostředím prvního spuštění počítače nebo je hodnota zásad [System\AllowTelemetry](/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) nastavená na hodnotu Úplná (základní hodnota na HoloLens). 
- Pokud chcete zakázat offline diagnostiku, přejděte na **stránku Nastavení App > Privacy** a v části **Diagnostická data vyberte Základní.**  Na sestaveních, kde offline diagnostika závisí na nastavení telemetrie, má vliv pouze na to, jestli se shromažďují nějaké protokoly. Nemá vliv na to, jaké soubory se shromažďují.
- Pokud je zařízení uzamčené, protokoly se nezobrazí.

V [buildech Windows Holographic verze 20H2](hololens-release-notes.md#windows-holographic-version-20h2) a novější:
- Když je povolená záložní diagnostika, bude řízena konkrétní zásadou MDM s odpovídajícím nastavením [MixedReality/FallbackDiagnostics.](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)
- Pokud je zařízení uzamčené, protokoly se nezobrazí.

Další informace najdete v tomto videu.

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

Diagnostiku shromáždíte podle těchto kroků:
1.  Připojení zařízení kabelem USB k počítači.
2.  V Průzkumník souborů počítači přejděte na Tento **počítač \<hololens-device> \Interní Storage.**
3.  Pokud **se Storage** interního úložiště, zařízení čeká na přihlášení uživatele. Buď se přihlaste, nebo zacyklte napájení zařízení tak, že podržíte tlačítko POWER po dobu 10 sekund.
4.  Stiskněte a okamžitě uvolněte **tlačítka Power + Volume Down** společně.
5.  Chvíli počkejte, než zařízení připraví archivy ZIP. (Dočasný soubor HololensDiagnostics.temp se může zobrazit, když zařízení generuje archivy ZIP. K souboru nepřistupovat ani ho ukládat. Po dokončení procesu se nahradí archivy zip.)
6.  Aktualizujte Průzkumníka souborů a přejděte **do složky \Documents.**
7.  Zkopírujte diagnostické soubory ZIP a sdílejte je s týmem podpory Microsoftu.

> [!NOTE]
> Některé z diagnostických souborů ZIP mohou obsahovat PII.
