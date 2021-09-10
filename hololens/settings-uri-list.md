---
title: Nastavení viditelnost stránky
description: udržujte si přehled o našich podporovaných identifikátorech uri pro PageVisibilityList a průvodce na HoloLens hybridních hybridních zařízení.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: HoloLens, HoloLens 2, přiřazený přístup, veřejný terminál, stránka nastavení
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 92040019b093c5ef63d74f095dcb3809112ae7a0
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427999"
---
# <a name="page-settings-visibility"></a>Nastavení viditelnost stránky

jedna z spravovatelných funkcí pro HoloLens zařízení používá [zásady Nastavení/PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) k omezení stránek zobrazených v rámci aplikace Nastavení. PageVisibilityList je zásada, která správcům IT umožňuje zabránit tomu, aby určité stránky v systémové Nastavení aplikaci byly viditelné nebo přístupné, nebo aby tak učinily pro všechny stránky kromě těch, které jsou uvedené.

> [!NOTE]
> tato funkce je dostupné jenom v [Windows holografická, verze 20H2](hololens-release-notes.md#windows-holographic-version-20h2) nebo vyšší pro zařízení HoloLens 2. Ujistěte se, že zařízení, která hodláte použít, se aktualizují.


## <a name="examples"></a>Příklady
Stránky jsou označeny zkrácenou verzí publikovaných identifikátorů URI, což je identifikátor URI mínus předpona MS-Settings:.

Následující příklad ilustruje zásadu, která by povolovala přístup jenom na stránky o technologii Bluetooth, které mají identifikátor URI "síť-WiFi" a "Bluetooth":
- `showonly:network-wifi;network-proxy;bluetooth`

Následující příklad ilustruje zásadu, která by mohla skrýt stránku pro obnovení operačního systému:
- `hide:reset`


## <a name="deploying-this-policy-via-intune"></a>Nasazení této zásady prostřednictvím Intune

Jedná se o konfigurační hodnoty, které se dodávají do Intune:

- **Název:** Zobrazovaný název preferovaného správce pro profil.
- **OMA-URI:** Plně kvalifikovaný identifikátor URI stránky nastavení, včetně jejího [oboru](/windows/client-management/mdm/policy-configuration-service-provider). Tento příklad na této stránce používá `./Device` obor.
- **Hodnota:** Řetězcová hodnota, která označuje, zda se mají skrýt nebo zobrazit *pouze* zadané stránky. Možné hodnoty jsou `hide:<pagename>` a `showonly:<pagename>` . 
 
Více stránek je možné zadat tak, že je oddělíte středníkem, a seznam běžných stránek najdete níže.

1. Vytvořte **vlastní zásadu**.
1. Při nastavování **OMA-URI** zadejte plně vymezený identifikátor URI. Například: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. Když vybíráte výběr dat, zvolte: **řetězec** .
1. Při zadávání **hodnoty** použijte pokyny výše. Například: **`showonly:network-wifi;network-proxy;bluetooth`** nebo **`hide:reset`** 
> [!IMPORTANT]
> Ujistěte se, že jste přidělili vlastní konfiguraci zařízení skupině, na kterou má zařízení nacházet. Pokud tento krok není proveden, zásada bude vložena, ale nebude použita.

další informace o skupinách a konfiguracích zařízení služby intune najdete v tématu [HoloLens konfigurace MDM](hololens-mdm-configure.md) .


## <a name="deploying-this-policy-via-a-provisioning-package"></a>Nasazení této zásady prostřednictvím zřizovacího balíčku

jedná se o konfigurační hodnoty, které budou zadány v nástroji Windows configuration Designer:

**Hodnota:** Řetězcová hodnota, která označuje, zda se mají skrýt nebo zobrazit *pouze* zadané stránky. Možné hodnoty jsou `hide:<pagename>` a `showonly:<pagename>` . Více stránek je možné zadat tak, že je oddělíte středníkem, a seznam běžných stránek najdete níže.


1. při vytváření balíčku v návrháři konfigurace Windows přejděte na **zásady > Nastavení > PageVisibilityList**
1. Zadejte řetězec: **`showonly:network-wifi;network-proxy;bluetooth`**
1. Exportujte zřizovací balíček.
1. Použijte balíček pro vaše zařízení.
úplné informace o tom, jak vytvořit a použít zřizovací balíček, najdete [na stránce věnovaném zřizování HoloLens](hololens-provisioning.md).


bez ohledu na zvolenou metodu by vaše zařízení nyní mělo přijímat změny a uživatelům se zobrazí následující aplikace Nastavení.

![snímek obrazovky s aktivními hodinami upravovanými v aplikaci Nastavení](images/hololens-page-visibility-list.jpg)

pokud chcete nakonfigurovat stránky aplikace Nastavení tak, aby zobrazovaly nebo skryly vlastní výběr stránek, podívejte se na Nastavení identifikátory uri, které jsou k dispozici na HoloLens.

## <a name="settings-uris"></a>Nastavení Identifikátory URI

HoloLens zařízení a Windows 10 zařízení mají v rámci aplikace Nastavení jinou možnost výběru stránek. Na této stránce najdete pouze nastavení, která existují na HoloLens.

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
| Aplikace & funkce > pokročilé možnosti <sup>2</sup>     | `appsfeatures-app` <br> |
| aplikace & funkce > Offline Mapy <sup>2</sup>     | `maps-maps` <br> |
| aplikace & funkce > Offline Mapy > stáhnout mapy <sup>2</sup>     | `maps-downloadmaps` <br> |

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
| Diagnostika & zpětná vazba | `privacy-feedback`                    |
| dokumenty.                | `privacy-documents`                   |
| E-mail                    | `privacy-email`                       |
| Systém souborů              | `privacy-broadfilesystemaccess`       |
| Obecné <sup>2</sup>             | `privacy-general`       |
| Ink & – přizpůsobení textu <sup>2</sup>             | `privacy-speechtyping`       |
| Umístění                 | `privacy-location`                    |
| Zasílání zpráv                | `privacy-messaging`                   |
| Mikrofon               | `privacy-microphone`                  |
| Pohyb <sup>2</sup>               | `privacy-motion`                  |
| Oznámení            | `privacy-notifications`               |
| Jiná zařízení            | `privacy-customdevices`               |
| Obrázky                 | `privacy-pictures`                    |
| Radiostanicím                   | `privacy-radios`                      |
| Snímek obrazovky s ohraničením <sup>2</sup>             | `privacy-graphicsCaptureWithoutBorder`       |
| Snímky obrazovky a aplikace <sup>2</sup>             | `privacy-graphicsCaptureProgrammatic`       |
| Řeč                   | `privacy-speech`                      |
| Úkoly                    | `privacy-tasks`                       |
| Pohyby uživatelů           | `privacy-backgroundspatialperception` |
| Videa                   | `privacy-videos`                      |
| Aktivace hlasu       | `privacy-voiceactivation`             |

### <a name="network--internet"></a>Síť a internet
| Stránka Nastavení | Identifikátor URI                              |
|---------------|----------------------------------|
| Režim v letadle <sup>2</sup> | `network-airplanemode`        |
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
| Obnovení & <sup>obnovení 2</sup>      | `reset`         |
| Program Windows Insider               | `windowsinsider` <br>`windowsinsider-optin`          |
| Windows Update                        | `windowsupdate`<br> `windowsupdate-activehours`  <br> `windowsupdate-history` <br> `windowsupdate-optionalupdates` <br><sup>1</sup>`windowsupdate-options`<br><sup>1</sup>`windowsupdate-restartoptions` |
| Windows Aktualizace – kontroluje aktualizace. | `windowsupdate-action`          |


- <sup>1</sup> – Ve verzích starších než Windows Holographic verze 21H1 vás následující dvě identifikátory URI ve skutečnosti nesmídí na stránky Upřesnit možnosti nebo **Možnosti.**  Zablokují nebo zobrazí jenom hlavní stránku Windows aktualizace.
  -  windowsupdate-options
  -  windowsupdate-restartoptions

- <sup>2</sup> – K dispozici Windows Holographic 21H1 nebo novějším.


Úplný seznam identifikátorů URI Windows 10 Nastavení najdete v dokumentaci [ke spouštěcím nastavením.](/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)
