---
title: Viditelnost Nastavení stránky
description: Seznam podporovaných identifikátorů URI pro PageVisibilityList a průvodce pro zařízení HoloLens hybridní realitou
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: hololens, hololens 2, přiřazený přístup, kiosk, stránka nastavení
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 92040019b093c5ef63d74f095dcb3809112ae7a0
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190425"
---
# <a name="page-settings-visibility"></a>Viditelnost Nastavení stránky

Jednou ze spravovatelných funkcí pro HoloLens zařízení je použití zásad [Nastavení/PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) k omezení stránek, které se zobrazí v Nastavení aplikaci. PageVisibilityList je zásada, která správcům IT umožňuje zabránit zobrazení nebo přístupu konkrétních stránek v aplikaci System Nastavení, nebo to udělat pro všechny stránky kromě těch, které jsou zadané.

> [!NOTE]
> Tato funkce je cenná jenom [v Windows Holographic verze 20H2](hololens-release-notes.md#windows-holographic-version-20h2) nebo vyšší pro HoloLens 2. Ujistěte se, že jsou aktualizovaná zařízení, pro která ho chcete použít.


## <a name="examples"></a>Příklady
Stránky jsou identifikované zkrácenou verzí publikovaných identifikátorů URI, což je identifikátor URI minus předpona ms-settings:.

Následující příklad ukazuje zásadu, která by umožnila přístup jenom ke stránkám about a bluetooth, které mají identifikátor URI network-wifi a bluetooth:
- `showonly:network-wifi;network-proxy;bluetooth`

Následující příklad ukazuje zásadu, která by skryla stránku pro resetování operačního systému:
- `hide:reset`


## <a name="deploying-this-policy-via-intune"></a>Nasazení této zásady přes Intune

Toto jsou konfigurační hodnoty, které se budou do Intune zadávají:

- **Name (Název):** Zobrazovaný název profilu upřednostňovaný správcem.
- **OMA-URI:** Plně kvalifikovaný identifikátor URI stránky nastavení včetně jejího [oboru](/windows/client-management/mdm/policy-configuration-service-provider). V těchto příkladech na této stránce se používá `./Device` obor .
- **Hodnota:** Řetězcová hodnota, která určuje, jestli se mají skrýt nebo *zobrazit jenom* zadané stránky. Možné hodnoty jsou `hide:<pagename>` a `showonly:<pagename>` . 
 
Více stránek lze zadat tak, že je oddělíte středníkem a níže najdete seznam běžných stránek.

1. Vytvořte **vlastní zásadu**.
1. Při nastavování **OMA-URI** zadejte plně vymezený identifikátor URI. Příklad: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. Při výběru dat zvolte: **Řetězec**
1. Při zadávání hodnoty **použijte** výše uvedené pokyny. Příklad: **`showonly:network-wifi;network-proxy;bluetooth`** nebo **`hide:reset`** 
> [!IMPORTANT]
> Nezapomeňte přiřadit vlastní konfiguraci zařízení ke skupině, ve které má být zařízení. Pokud tento krok není proveden, zásada se nas nabízené oznámení provede, ale nebude použita.

Další informace o HoloLens Intune a konfiguracích zařízení najdete v tématu Konfigurace [MDM.](hololens-mdm-configure.md)


## <a name="deploying-this-policy-via-a-provisioning-package"></a>Nasazení této zásady prostřednictvím zřizovacího balíčku

Toto jsou konfigurační hodnoty, které budou zadány v Windows Configuration Designeru:

**Hodnota:** Řetězcová hodnota, která určuje, jestli se mají skrýt nebo *zobrazit jenom* zadané stránky. Možné hodnoty jsou `hide:<pagename>` a `showonly:<pagename>` . Více stránek lze zadat tak, že je oddělíte středníkem a níže najdete seznam běžných stránek.


1. Při vytváření balíčku v návrháři konfigurace Windows přejděte na **Zásady > Nastavení > PageVisibilityList.**
1. Zadejte řetězec: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Exportujte zřizovací balíček.
1. Použijte balíček na zařízení.
Úplné podrobnosti o tom, jak vytvořit a použít zřizovací balíček, najdete [na HoloLens zřizování.](hololens-provisioning.md)


Bez ohledu na zvolenou metodu by teď vaše zařízení mělo přijímat změny a uživatelům se zobrazí následující Nastavení App.

![Snímek obrazovky s úpravami aktivních hodin v Nastavení aplikaci](images/hololens-page-visibility-list.jpg)

Pokud chcete nakonfigurovat Nastavení, aby se na stránkách aplikace zobrazují nebo skryly vlastní výběry stránek, podívejte se na Nastavení identifikátory URI, které jsou HoloLens.

## <a name="settings-uris"></a>Nastavení Uri

HoloLens zařízení Windows 10 zařízení mají v rámci aplikace Nastavení jiný výběr stránek. Na této stránce najdete pouze nastavení, která existují v HoloLens.

### <a name="accounts"></a>Účty
| Stránka Nastavení           | Identifikátor URI                                            |
|-------------------------|------------------------------------------------|
| Přístup do práce nebo do školy | `workplace`                         |
| Registrace Iris       | `signinoptions-launchirisenrollment` |
| Možnosti přihlášení         | ` signinoptions `                   |

### <a name="apps"></a>Aplikace
| Stránka Nastavení | Identifikátor URI                          |
|---------------|------------------------------|
| Aplikace & funkce <sup>2</sup>     | `appsfeatures` <br> |
| Funkce & aplikací > Rozšířené možnosti <sup>2</sup>     | `appsfeatures-app` <br> |
| Funkce & aplikací > offline Mapy <sup>2</sup>     | `maps-maps` <br> |
| Aplikace & funkce > offline Mapy > Stáhnout mapy <sup>2</sup>     | `maps-downloadmaps` <br> |

### <a name="devices"></a>Zařízení
| Stránka Nastavení | Identifikátor URI                          |
|---------------|------------------------------|
| Bluetooth     | `bluetooth` <br> `connecteddevices` |
| Myš <sup>2</sup>      | `mouse` <br>  |
| USB <sup>2</sup>      | `usb` <br>  |

### <a name="privacy"></a>Ochrana osobních údajů
| Stránka Nastavení            | Identifikátor URI                                             |
|--------------------------|-------------------------------------------------|
| Informace o účtu             | `privacy-accountinfo`              |
| Diagnostika aplikací        | `privacy-appdiagnostics`              |
| Aplikace na pozadí        | `privacy-backgroundapps`              |
| Kalendář                 | `privacy-calendar`                    |
| Historie volání             | `privacy-callhistory`                 |
| Camera                   | `privacy-webcam`                      |
| Kontakty                 | `privacy-contacts`                    |
| Zpětná vazba & diagnostiky | `privacy-feedback`                    |
| dokumenty.                | `privacy-documents`                   |
| E-mail                    | `privacy-email`                       |
| Systém souborů              | `privacy-broadfilesystemaccess`       |
| Obecné <sup>2</sup>             | `privacy-general`       |
| Psaní & rukopisu <sup>2</sup>             | `privacy-speechtyping`       |
| Umístění                 | `privacy-location`                    |
| Zasílání zpráv                | `privacy-messaging`                   |
| Mikrofon               | `privacy-microphone`                  |
| Pohyb <sup>2</sup>               | `privacy-motion`                  |
| Oznámení            | `privacy-notifications`               |
| Další zařízení            | `privacy-customdevices`               |
| Obrázky                 | `privacy-pictures`                    |
| Rádia                   | `privacy-radios`                      |
| Snímek obrazovky s <sup>ohraničením 2</sup>             | `privacy-graphicsCaptureWithoutBorder`       |
| Snímky obrazovky a aplikace <sup>2</sup>             | `privacy-graphicsCaptureProgrammatic`       |
| Řeč                   | `privacy-speech`                      |
| Úkoly                    | `privacy-tasks`                       |
| Pohyby uživatelů           | `privacy-backgroundspatialperception` |
| Videa                   | `privacy-videos`                      |
| Hlasová aktivace       | `privacy-voiceactivation`             |

### <a name="network--internet"></a>Síť a internet
| Stránka Nastavení | Identifikátor URI                              |
|---------------|----------------------------------|
| Režim v <sup>letadle 2</sup> | `network-airplanemode`        |
| Proxy server | `network-proxy`        |
| Síť VPN   | `network-vpn`          |
| Wi-Fi  | `network-wifi`<br>`network-wifisettings`<br>`network-status`<br>`wifi-provisioning`    |



### <a name="system"></a>Systémový
| Stránka Nastavení      | Identifikátor URI                                |
|--------------------|------------------------------------|
| Baterie <sup>2</sup>           | `batterysaver`<br>|
| Baterie <sup>2</sup>           | `batterysaver-settings`<br>|
| Barvy             | `colors`<br>`personalization-colors` |
| Hologramy <sup>2</sup>  |  `holograms`  |
| <sup>Uchýlovací 2</sup> |  `calibration` |
| Oznámení & akce  | `notifications`          |
| Sdílená prostředí | `crossdevice` 
| Zvuk <sup>2</sup>           | `sound`<br>|
| Zvuk > Svazek aplikace a předvolba zařízení <sup>2</sup>           | `apps-volume`<br>|
| Sound > Správa zvukových zařízení <sup>2</sup>           | `sound-devices`<br>|
| Storage            | `storagesense`           |
| Storage > konfigurace Storage Sense <sup>2</sup>           | `storagepolicies`<br>|

### <a name="time--language"></a>Time & Language
| Stránka Nastavení | Identifikátor URI                                           |
|---------------|-----------------------------------------------|
| Datum & čas <sup>2</sup> | `dateandtime`                  |
| Klávesnice <sup>2</sup> | `keyboard`                  |
| Jazyk <sup>2</sup> | `language`                  |
| Jazyk <sup>2</sup> | `regionlanguage-languageoptions`                  |
| Jazyk      | `regionlanguage`<br>`regionlanguage-adddisplaylanguage`<br>`regionlanguage-setdisplaylanguage` |
| Oblast        | `regionformatting`                  |

### <a name="update--security"></a>Zabezpečení & aktualizací
| Stránka Nastavení                         | Identifikátor URI                                       |
|---------------------------------------|-------------------------------------------|
| Rozšířené možnosti                    | `windowsupdate-options`         |
| Obnovení & obnovení <sup>2</sup>      | `reset`         |
| Program Windows Insider               | `windowsinsider` <br>`windowsinsider-optin`          |
| Windows Update                        | `windowsupdate`<br> `windowsupdate-activehours`  <br> `windowsupdate-history` <br> `windowsupdate-optionalupdates` <br><sup>1</sup>`windowsupdate-options`<br><sup>1</sup>`windowsupdate-restartoptions` |
| Windows Aktualizace – kontroluje aktualizace. | `windowsupdate-action`          |


- <sup>1</sup> – Ve verzích starších než Windows Holographic verze 21H1 vás následující dvě  identifikátory URI ve skutečnosti nesmídí na stránky Upřesnit možnosti nebo **Možnosti.** Zablokují nebo zobrazí jenom hlavní stránku Windows aktualizace.
  -  windowsupdate-options
  -  windowsupdate-restartoptions

- <sup>2</sup> – K dispozici Windows Holographic 21H1 nebo novějším.


Úplný seznam identifikátorů URI Windows 10 Nastavení najdete v dokumentaci [ke spouštěcím nastavením.](/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)
