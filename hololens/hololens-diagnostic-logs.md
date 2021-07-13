---
title: Shromažďování a používání diagnostických informací z HoloLens zařízení
description: Zjistěte, jak shromažďovat, používat a uchovávat diagnostické informace z HoloLens zařízení.
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
ms.openlocfilehash: 082a263bdd7eba694c13124abf40763644c83dfa
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640436"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a>Shromažďování a používání diagnostických informací z HoloLens zařízení

HoloLens si uživatelé a správci mohou vybírat ze čtyř různých metod shromažďování diagnostických informací z HoloLens:

- Centrum Feedback aplikace
- DiagnosticLog CSP
- Nastavení aplikace
- Offline diagnostika

> [!IMPORTANT]  
> Diagnostické protokoly zařízení obsahují identifikovatelné osobní údaje ( PII), například o tom, jaké procesy nebo aplikace uživatel spouští během typického provozu. Když zařízení HoloLens sdílí více uživatelů (například se uživatelé přihlašuje ke stejnému zařízení pomocí různých účtů služby Microsoft Azure Active Directory (Azure AD), mohou diagnostické protokoly obsahovat informace o PII, které platí pro více uživatelů. Další informace najdete v prohlášení [o zásadách ochrany osobních údajů společnosti Microsoft.](https://privacy.microsoft.com/privacystatement)

Následující tabulka porovnává různé metody shromažďování. Názvy metod odkazují na podrobnější informace v částech, které následují po tabulce.

|Metoda |Požadavky |Umístění dat |Přístup k datům a jejich používání |Uchovávání dat |
| --- | --- | --- | --- | --- |
|[Centrum Feedback](#feedback-hub) |Síťové a internetové připojení<br /><br />Centrum Feedback aplikace<br /><br />Oprávnění k nahrávání souborů do cloudu Microsoftu |Cloud Microsoftu<br /><br />HoloLens zařízení (volitelné) |Uživatel požádá o pomoc, souhlasí s podmínkami použití a nahrává data.<br /><br />Zaměstnanci Microsoftu data prochová v souladu s podmínkami použití. |Data v cloudu se uchovávají po dobu definovanou ochranou osobních údajů nové generace (NGP). Data se pak odstraní automaticky.<br /><br />Data v zařízení může kdykoli odstranit uživatel, který má oprávnění vlastníka **zařízení** **nebo** správce. |
|[Nastavení Poradce při potížích](#settings-troubleshooter) |Nastavení aplikace |HoloLens zařízení<br /><br />Připojený počítač (volitelné) |Uživatel ukládá data a k datům přistupuje pouze uživatel (pokud uživatel data výslovně neschová s jiným uživatelem). |Data se uchovávají v zařízení, dokud je uživatel nevystraní.* |
|[DiagnosticLog CSP](#diagnosticlog-csp) |Síťové připojení<br /><br />Prostředí MDM, které podporuje csP DiagnosticLog |Správce nakonfiguruje umístění úložiště. |Ve spravovaném prostředí uživatel implicitně souhlasí s přístupem správce k datům.<br /><br />Správce konfiguruje přístupové role a oprávnění. | Data se uchovávají v cloudovém úložišti a správce nakonfiguruje zásady uchovávání informací. |
|[Offline diagnostika](#offline-diagnostics) |Konfigurace zařízení:<ul><li>Zapnuté a připojené k počítači</li><li>Funkce tlačítek napájení a hlasitosti</li></ul> |HoloLens zařízení<br /><br />Připojený počítač |Uživatel ukládá data a k datům přistupuje pouze uživatel (pokud uživatel data výslovně neschová s jiným uživatelem). |Data se uchovávají v zařízení, dokud je uživatel nevystraní. |

* Koncový uživatel zodpovídá za zodpovědné sdílení protokolů s někým jiným. Tyto soubory jsou primárně užitečné při kontaktování služeb zákazníkům a podpory.  

## <a name="feedback-hub"></a>Centrum Feedback

Uživatel HoloLens může pomocí desktopové aplikace Microsoft Centrum Feedback odesílat diagnostické informace do Podpora Microsoftu. Podrobnosti a kompletní pokyny najdete v tématu [Váš názor.](hololens-feedback.md)  

> [!NOTE]  
> **Komerční nebo podniková uživatelé:** Pokud pomocí aplikace Centrum Feedback nahlásit problém související s MDM, zřizováním nebo jiným aspektem správy zařízení, změňte kategorii aplikace na Enterprise **Správa**  >  **zařízení.**

>[!IMPORTANT]
> Pro zajištění nejlepších možných dat pro řešení problémů důrazně doporučujeme nastavit telemetrii zařízení na **Nepovinné.** Tuto hodnotu můžete nastavit během prostředí při provozu nebo pomocí **Nastavení** aplikace. Pokud to chcete provést pomocí Nastavení, vyberte **Start > Nastavení > Privacy > App Diagnostics > On**(Spustit > Nastavení > ochrany osobních údajů a > aplikací).
### <a name="prerequisites"></a>Požadavky

- Zařízení je připojené k síti.
- Aplikace Centrum Feedback dostupná na stolním počítači uživatele a uživatel může nahrávat soubory do cloudu Microsoftu.

### <a name="data-locations-access-and-retention"></a>Umístění dat, přístup a uchovávání

Souhlasem s podmínkami použití služby Centrum Feedback uživatel výslovně souhlasí s ukládáním a používáním dat (jak je definováno v této smlouvě).

Na Centrum Feedback jsou dvě místa, kam může uživatel ukládat diagnostické informace:

- **Cloud Microsoftu**. Data, která uživatel nahraje pomocí aplikace Centrum Feedback, se ukládají po dobu, která odpovídá požadavkům na ochranu osobních údajů nové generace (NGP). Zaměstnanci Microsoftu mohou pro přístup k informacím během tohoto období použít prohlížeč kompatibilní s protokolem NGP.

   > [!NOTE]  
   > Tyto požadavky platí pro data ve všech Centrum Feedback kategoriích.

- **Zařízení HoloLens .** Při vytváření sestavy v Centrum Feedback může uživatel vybrat Možnost Uložit místní kopii diagnostiky a příloh vytvořenou při poskytnutí **zpětné vazby.** Pokud uživatel vybere tuto možnost, Centrum Feedback uloží kopii diagnostických informací na HoloLens zařízení. Tyto informace zůstanou přístupné uživateli (nebo komukoli, kdo se pomocí tohoto účtu přihlásí k HoloLens). Pokud chcete tyto informace odstranit, musí mít uživatel na **zařízení** **oprávnění** Vlastníka zařízení nebo Správce. Uživatel s příslušnými oprávněními se může přihlásit k Centrum Feedback, vybrat **Nastavení** Zobrazit diagnostické protokoly a  >  odstranit informace.

## <a name="settings-troubleshooter"></a>Nastavení Poradce při potížích

Uživatel HoloLens použít aplikaci **Nastavení** zařízení k řešení problémů a shromažďování diagnostických informací. Postupujte takto:

1. Otevřete aplikaci Nastavení a vyberte **stránku Řešení potíží & zabezpečením.**  >  
1. Vyberte příslušnou oblast a vyberte **Spustit.**
1. Reprodukujte problém.
1. Po reprodukování problému se vraťte do Nastavení a pak vyberte **Zastavit.**

Uživatel může také nakonfigurovat chování fallback diagnostics z **Nastavení** aplikace. Toto nastavení **nakonfigurujte tak, že > Ochrana** osobních údajů – > řešení potíží.
> [!NOTE]
> Pokud jsou pro zařízení nakonfigurované zásady MDM, uživatel nebude moct toto chování přepsat.

### <a name="os-update-troubleshooter"></a>Poradce při potížích s aktualizací operačního systému
V [buildech Windows Holographic verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1) a novější:
- Kromě předchozích poradců při potížích v aplikaci Nastavení byl přidán nový poradce při potížích s přidáním nové aplikace Nastavení pro aktualizace operačního systému. Přejděte na **Nastavení -> Update & Security -> Troubleshoot -> Windows Update** a vyberte **Spustit.** Díky tomu můžete shromažďovat trasování a reprodukovat problém s aktualizacemi operačního systému, což vám pomůže lépe při řešení potíží s IT nebo podporou.
### <a name="prerequisites"></a>Požadavky

- Aplikace **Nastavení** nainstalovaná na zařízení a je dostupná pro uživatele.

### <a name="data-locations-access-and-retention"></a>Umístění dat, přístup a uchovávání

Protože uživatel zahájí shromažďování dat, uživatel implicitně souhlasí s uložením diagnostických informací. K datům má přístup jenom uživatel nebo kdokoli, s kým data sdílí.

Diagnostické informace se ukládají na zařízení. Pokud je zařízení připojené k počítači uživatele, nachází se informace také v počítači v následujícím souboru:

> Soubor \\ \<*HoloLens device name*> \\ .etl trasování Storage \\ tomto \\ interním \<*ddmmyyhhmmss*> počítači

> [!NOTE]  
> V této cestě k souboru a názvu představuje název HoloLens zařízení a datum a čas vytvoření \<*HoloLens device name*> \<*ddmmyyhhmmss*> souboru.

Diagnostické informace zůstanou v těchto umístěních, dokud je uživatel nevy odstraní.

## <a name="diagnosticlog-csp"></a>DiagnosticLog CSP

V prostředí Mobile Správa zařízení (MDM) může správce IT použít poskytovatele konfiguračních služeb [DiagnosticLog](/windows/client-management/mdm/diagnosticlog-csp) ke konfiguraci nastavení diagnostiky na zaregistrovaných HoloLens zařízeních. Správce IT může tato nastavení nakonfigurovat tak, aby shromažďovala protokoly z zaregistrovaná zařízení.

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
3.  Pokud **se Storage** interního úložiště, zařízení čeká na přihlášení uživatele. Buď se přihlaste, nebo zacyklte napájení zařízení podržením tlačítka POWER po dobu 10 sekund.
4.  Stiskněte a okamžitě uvolněte **tlačítka Power + Volume Down** společně.
5.  Chvíli počkejte, než zařízení připraví archivy ZIP. (Dočasný soubor HololensDiagnostics.temp se může zobrazit, když zařízení generuje archivy ZIP. K souboru nepřistupovat ani ho ukládat. Po dokončení procesu se nahradí archivy zip.)
6.  Aktualizujte Průzkumníka souborů a přejděte **do složky \Documents.**
7.  Zkopírujte diagnostické soubory ZIP a sdílejte je s týmem podpory Microsoftu.

> [!NOTE]
> Některé z diagnostických souborů ZIP mohou obsahovat PII.
