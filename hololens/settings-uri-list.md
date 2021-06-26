---
title: Viditelnost nastavení stránky
description: Seznam podporovaných identifikátorů URI pro PageVisibilityList a Průvodce pro zařízení s hybridní realitou HoloLens
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
ms.openlocfilehash: d28994d911532a940d82756aa45609571ee80ac3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924328"
---
# <a name="page-settings-visibility"></a>Viditelnost nastavení stránky

Jednou ze spravovatelných funkcí pro zařízení HoloLens je použití zásad [Settings/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) k omezení stránek, které se zobrazí v aplikaci Nastavení. PageVisibilityList je zásada, která správcům IT umožňuje zabránit zobrazení nebo přístupu konkrétních stránek v aplikaci Nastavení systému, nebo to provést pro všechny stránky kromě těch, které jsou zadané.

> [!NOTE]
> Tato funkce je k dispozici pouze ve [Windows Holographic verze 20H2](hololens-release-notes.md#windows-holographic-version-20h2) nebo novější pro zařízení HoloLens 2. Ujistěte se, že jsou aktualizovaná zařízení, pro která ho chcete použít.

Následující příklad znázorňuje zásadu, která by umožnila přístup jenom ke stránkám about a bluetooth, které mají identifikátory URI ms-settings:network-wifi a ms-settings:bluetooth:
- `showonly:network-wifi;network-proxy;bluetooth`

Nastavení prostřednictvím zřizovacího balíčku:

1. Při vytváření balíčku v nástroji Windows Configuration Designer přejděte do **části Zásady > nastavení > PageVisibilityList.**
1. Zadejte řetězec: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Exportujte zřizovací balíček.
1. Použijte balíček na zařízení.
Úplné podrobnosti o vytvoření a použití zřizovacího balíčku najdete na [této stránce.](hololens-provisioning.md)

Můžete to udělat přes Intune pomocí OMA-URI:

1. Vytvořte **vlastní zásadu**.
1. Při nastavování OMA-URI použijte řetězec: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. Při výběru dat zvolte: **Řetězec**
1. Při zadávání hodnoty použijte: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Nezapomeňte přiřadit vlastní konfiguraci zařízení ke skupině, ve které má být zařízení.

Další informace o skupinách Intune a konfiguracích zařízení najdete v tématu Konfigurace [HoloLens MDM.](hololens-mdm-configure.md)

Bez ohledu na zvolenou metodu by teď vaše zařízení mělo přijímat změny a uživatelům se zobrazí následující aplikace nastavení.

![Snímek obrazovky s úpravami aktivních hodin v aplikaci Nastavení](images/hololens-page-visibility-list.jpg)

Pokud chcete nakonfigurovat stránky aplikace Nastavení tak, aby se ve vašem výběru stránek zobrazují nebo skryly vlastní výběry, podívejte se na identifikátory URI nastavení dostupné na HoloLens.

## <a name="settings-uris"></a>Identifikátory URI nastavení

Zařízení HoloLens a Windows 10 zařízení mají v aplikaci Nastavení jiný výběr stránek. Na této stránce najdete pouze nastavení, která existují na HoloLens.

### <a name="accounts"></a>Účty
| Stránka Nastavení           | Identifikátor URI                                            |
|-------------------------|------------------------------------------------|
| Přístup do práce nebo do školy | `ms-settings:workplace`                         |
| Registrace Iris       | `ms-settings:signinoptions-launchirisenrollment` |
| Možnosti přihlášení         | ` ms-settings:signinoptions `                   |

### <a name="apps"></a>Aplikace
| Stránka Nastavení | Identifikátor URI                          |
|---------------|------------------------------|
| Aplikace & funkce<sup>2</sup>     | `ms-settings:appsfeatures` <br> |
| Aplikace & funkce > Upřesnit možnosti <sup>2</sup>     | `ms-settings::appsfeatures-app` <br> |
| Aplikace & funkcemi > Offline Maps <sup>2</sup>     | `ms-settings:maps-maps` <br> |
| Aplikace & funkcemi > Offline Maps > Stažení map <sup>2</sup>     | `ms-settings:maps-downloadmaps` <br> |

### <a name="devices"></a>Zařízení
| Stránka Nastavení | Identifikátor URI                          |
|---------------|------------------------------|
| Bluetooth     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |
| Myš <sup>2</sup>      | `ms-settings:mouse` <br>  |
| USB <sup>2</sup>      | `ms-settings:usb` <br>  |

### <a name="privacy"></a>Ochrana osobních údajů
| Stránka Nastavení            | Identifikátor URI                                             |
|--------------------------|-------------------------------------------------|
| Informace o účtu             | `ms-settings:privacy-accountinfo`              |
| Diagnostika aplikací        | `ms-settings:privacy-appdiagnostics`              |
| Aplikace na pozadí        | `ms-settings:privacy-backgroundapps`              |
| Kalendář                 | `ms-settings:privacy-calendar`                    |
| Historie volání             | `ms-settings:privacy-callhistory`                 |
| Camera                   | `ms-settings:privacy-webcam`                      |
| Kontakty                 | `ms-settings:privacy-contacts`                    |
| Zpětná vazba & diagnostiky | `ms-settings:privacy-feedback`                    |
| dokumenty.                | `ms-settings:privacy-documents`                   |
| E-mail                    | `ms-settings:privacy-email`                       |
| Systém souborů              | `ms-settings:privacy-broadfilesystemaccess`       |
| Obecné <sup>2</sup>             | `ms-settings:privacy-general`       |
| Psaní & rukopisu <sup>2</sup>             | `ms-settings:privacy-speechtyping`       |
| Umístění                 | `ms-settings:privacy-location`                    |
| Zasílání zpráv                | `ms-settings:privacy-messaging`                   |
| Mikrofon               | `ms-settings:privacy-microphone`                  |
| Pohyb <sup>2</sup>               | `ms-settings:privacy-motion`                  |
| Oznámení            | `ms-settings:privacy-notifications`               |
| Další zařízení            | `ms-settings:privacy-customdevices`               |
| Obrázky                 | `ms-settings:privacy-pictures`                    |
| Rádia                   | `ms-settings:privacy-radios`                      |
| Snímek obrazovky s <sup>ohraničením 2</sup>             | `ms-settings:privacy-graphicsCaptureWithoutBorder`       |
| Snímky obrazovky a aplikace <sup>2</sup>             | `ms-settings:privacy-graphicsCaptureProgrammatic`       |
| Řeč                   | `ms-settings:privacy-speech`                      |
| Úlohy                    | `ms-settings:privacy-tasks`                       |
| Pohyby uživatelů           | `ms-settings:privacy-backgroundspatialperception` |
| Videa                   | `ms-settings:privacy-videos`                      |
| Hlasová aktivace       | `ms-settings:privacy-voiceactivation`             |

### <a name="network--internet"></a>Síť a internet
| Stránka Nastavení | Identifikátor URI                              |
|---------------|----------------------------------|
| Režim v <sup>letadle 2</sup> | `ms-settings:network-airplanemode`        |
| Proxy server | `ms-settings:network-proxy`        |
| Síť VPN   | `ms-settings:network-vpn`          |
| Wi-Fi  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |



### <a name="system"></a>Systémový
| Stránka Nastavení      | Identifikátor URI                                |
|--------------------|------------------------------------|
| Baterie <sup>2</sup>           | `ms-settings:batterysaver`<br>|
| Baterie <sup>2</sup>           | `ms-settings:batterysaver-settings`<br>|
| Barvy             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| Hologramy <sup>2</sup>  |  `ms-settings:holograms`  |
| <sup>Uchýlovací 2</sup> |  `ms-settings:calibration` |
| Oznámení & akce  | `ms-settings:notifications`          |
| Sdílená prostředí | `ms-settings:crossdevice` 
| Zvuk <sup>2</sup>           | `ms-settings:sound`<br>|
| Zvuk > Svazek aplikace a předvolba zařízení <sup>2</sup>           | `ms-settings:apps-volume`<br>|
| Sound > Správa zvukových zařízení <sup>2</sup>           | `ms-settings:sound-devices`<br>|
| Storage            | `ms-settings:storagesense`           |
| Konfigurace > úložiště Inteligentní úložiště <sup>2</sup>           | `ms-settings:storagepolicies`<br>|

### <a name="time--language"></a>Time & Language
| Stránka Nastavení | Identifikátor URI                                           |
|---------------|-----------------------------------------------|
| Datum & čas <sup>2</sup> | `ms-settings:dateandtime`                  |
| Klávesnice <sup>2</sup> | `ms-settings:keyboard`                  |
| Jazyk <sup>2</sup> | `ms-settings:language`                  |
| Jazyk <sup>2</sup> | `ms-settings:regionlanguage-languageoptions`                  |
| Jazyk      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |
| Oblast        | `ms-settings:regionformatting`                  |

### <a name="update--security"></a>Zabezpečení & aktualizací
| Stránka Nastavení                         | Identifikátor URI                                       |
|---------------------------------------|-------------------------------------------|
| Rozšířené možnosti                    | `ms-settings:windowsupdate-options`         |
| Obnovení & obnovení <sup>2</sup>      | `ms-settings:reset`         |
| Program Windows Insider               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| Windows Update                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><sup>1</sup>`ms-settings:windowsupdate-options`<br><sup>1</sup>`ms-settings:windowsupdate-restartoptions` |
| služba Windows Update – Kontroluje aktualizace. | `ms-settings:windowsupdate-action`          |


- <sup>1</sup> – U verzí starších než Windows Holographic verze 21H1 vás následující dvě  identifikátory URI ve skutečnosti nesmídí na stránky Upřesnit možnosti **nebo** Možnosti. Zablokují nebo zobrazí jenom hlavní služba Windows Update stránky.
  -  ms-settings:windowsupdate-options
  -  ms-settings:windowsupdate-restartoptions

- <sup>2</sup> – K dispozici ve Windows Holographic 21H1 nebo novějším.


Úplný seznam identifikátorů URI Windows 10 najdete v dokumentaci ke [spouštěcím nastavením.](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)
