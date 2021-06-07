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
ms.openlocfilehash: b5779ffa1de1700b4fcd17fc17b8ae3a82a45c22
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379253"
---
# <a name="page-settings-visibility"></a><span data-ttu-id="8a24d-104">Viditelnost nastavení stránky</span><span class="sxs-lookup"><span data-stu-id="8a24d-104">Page Settings Visibility</span></span>

<span data-ttu-id="8a24d-105">Jednou ze spravovatelných funkcí pro zařízení HoloLens je použití zásad [Settings/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) k omezení stránek, které se zobrazí v aplikaci Nastavení.</span><span class="sxs-lookup"><span data-stu-id="8a24d-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="8a24d-106">PageVisibilityList je zásada, která správcům IT umožňuje zabránit zobrazení nebo přístupu konkrétních stránek v aplikaci Nastavení systému, nebo to provést pro všechny stránky kromě těch, které jsou zadané.</span><span class="sxs-lookup"><span data-stu-id="8a24d-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="8a24d-107">Tato funkce je k dispozici pouze ve [Windows Holographic verze 20H2](hololens-release-notes.md#windows-holographic-version-20h2) nebo novější pro zařízení HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="8a24d-107">This feature is only avalible in [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) or higher for HoloLens 2 devices.</span></span> <span data-ttu-id="8a24d-108">Ujistěte se, že jsou aktualizovaná zařízení, pro která ho chcete použít.</span><span class="sxs-lookup"><span data-stu-id="8a24d-108">Please ensure devices you intend to use this for are updated.</span></span>

<span data-ttu-id="8a24d-109">Následující příklad znázorňuje zásadu, která by umožnila přístup jenom ke stránkám about a bluetooth, které mají identifikátory URI ms-settings:network-wifi a ms-settings:bluetooth:</span><span class="sxs-lookup"><span data-stu-id="8a24d-109">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "ms-settings:network-wifi" and "ms-settings:bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="8a24d-110">Nastavení prostřednictvím zřizovacího balíčku:</span><span class="sxs-lookup"><span data-stu-id="8a24d-110">To set this via a Provisioning Package:</span></span>

1. <span data-ttu-id="8a24d-111">Při vytváření balíčku v nástroji Windows Configuration Designer přejděte do části **Zásady > nastavení > PageVisibilityList.**</span><span class="sxs-lookup"><span data-stu-id="8a24d-111">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="8a24d-112">Zadejte řetězec: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="8a24d-112">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="8a24d-113">Exportujte zřizovací balíček.</span><span class="sxs-lookup"><span data-stu-id="8a24d-113">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="8a24d-114">Použijte balíček na zařízení.</span><span class="sxs-lookup"><span data-stu-id="8a24d-114">Apply the package to your device.</span></span>
<span data-ttu-id="8a24d-115">Úplné podrobnosti o vytvoření a použití zřizovacího balíčku najdete na [této stránce.](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="8a24d-115">For full details on how to create and apply a provisioning package visit [this page](hololens-provisioning.md).</span></span>

<span data-ttu-id="8a24d-116">Můžete to udělat přes Intune pomocí OMA-URI:</span><span class="sxs-lookup"><span data-stu-id="8a24d-116">This can be done via Intune using OMA-URI:</span></span>

1. <span data-ttu-id="8a24d-117">Vytvořte **vlastní zásadu**.</span><span class="sxs-lookup"><span data-stu-id="8a24d-117">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="8a24d-118">Při nastavování OMA-URI použijte řetězec: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span><span class="sxs-lookup"><span data-stu-id="8a24d-118">When setting the OMA-URI use the string: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="8a24d-119">Při výběru dat zvolte: **Řetězec**</span><span class="sxs-lookup"><span data-stu-id="8a24d-119">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="8a24d-120">Při zadávání hodnoty použijte: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="8a24d-120">When typing the value use: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="8a24d-121">Nezapomeňte přiřadit vlastní konfiguraci zařízení ke skupině, ve které má být zařízení.</span><span class="sxs-lookup"><span data-stu-id="8a24d-121">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span>

<span data-ttu-id="8a24d-122">Další informace o skupinách Intune a konfiguracích zařízení najdete v tématu Konfigurace [HoloLens MDM.](hololens-mdm-configure.md)</span><span class="sxs-lookup"><span data-stu-id="8a24d-122">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>

<span data-ttu-id="8a24d-123">Bez ohledu na zvolenou metodu by teď vaše zařízení mělo přijímat změny a uživatelům se zobrazí následující aplikace nastavení.</span><span class="sxs-lookup"><span data-stu-id="8a24d-123">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![Snímek obrazovky s úpravami aktivních hodin v aplikaci Nastavení](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="8a24d-125">Pokud chcete nakonfigurovat stránky aplikace Nastavení tak, aby se ve vašem výběru stránek zobrazují nebo skryly vlastní výběry, podívejte se na identifikátory URI nastavení dostupné na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8a24d-125">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <a name="settings-uris"></a><span data-ttu-id="8a24d-126">Identifikátory URI nastavení</span><span class="sxs-lookup"><span data-stu-id="8a24d-126">Settings URIs</span></span>

<span data-ttu-id="8a24d-127">Zařízení HoloLens a Windows 10 zařízení mají v aplikaci Nastavení jiný výběr stránek.</span><span class="sxs-lookup"><span data-stu-id="8a24d-127">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="8a24d-128">Na této stránce najdete pouze nastavení, která existují na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="8a24d-128">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <a name="accounts"></a><span data-ttu-id="8a24d-129">Účty</span><span class="sxs-lookup"><span data-stu-id="8a24d-129">Accounts</span></span>
| <span data-ttu-id="8a24d-130">Stránka Nastavení</span><span class="sxs-lookup"><span data-stu-id="8a24d-130">Settings page</span></span>           | <span data-ttu-id="8a24d-131">Identifikátor URI</span><span class="sxs-lookup"><span data-stu-id="8a24d-131">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="8a24d-132">Přístup do práce nebo do školy</span><span class="sxs-lookup"><span data-stu-id="8a24d-132">Access work or school</span></span> | `ms-settings:workplace`                         |
| <span data-ttu-id="8a24d-133">Registrace Iris</span><span class="sxs-lookup"><span data-stu-id="8a24d-133">Iris Enrollment</span></span>       | `ms-settings:signinoptions-launchirisenrollment` |
| <span data-ttu-id="8a24d-134">Možnosti přihlášení</span><span class="sxs-lookup"><span data-stu-id="8a24d-134">Sign In Options</span></span>         | ` ms-settings:signinoptions `                   |

### <a name="apps"></a><span data-ttu-id="8a24d-135">Aplikace</span><span class="sxs-lookup"><span data-stu-id="8a24d-135">Apps</span></span>
| <span data-ttu-id="8a24d-136">Stránka Nastavení</span><span class="sxs-lookup"><span data-stu-id="8a24d-136">Settings page</span></span> | <span data-ttu-id="8a24d-137">Identifikátor URI</span><span class="sxs-lookup"><span data-stu-id="8a24d-137">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="8a24d-138">Aplikace & funkce<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8a24d-138">Apps & features<sup>2</sup></span></span>     | `ms-settings:appsfeatures` <br> |
| <span data-ttu-id="8a24d-139">Aplikace & funkce > Upřesnit možnosti <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8a24d-139">Apps & features > Advanced Options <sup>2</sup></span></span>     | `ms-settings::appsfeatures-app` <br> |
| <span data-ttu-id="8a24d-140">Aplikace & funkcemi > Offline Maps <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8a24d-140">Apps & features > Offline Maps <sup>2</sup></span></span>     | `ms-settings:maps-maps` <br> |
| <span data-ttu-id="8a24d-141">Aplikace & funkcemi > Offline Maps > Stažení map <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8a24d-141">Apps & features > Offline Maps > Download maps <sup>2</sup></span></span>     | `ms-settings:maps-downloadmaps` <br> |

### <a name="devices"></a><span data-ttu-id="8a24d-142">Zařízení</span><span class="sxs-lookup"><span data-stu-id="8a24d-142">Devices</span></span>
| <span data-ttu-id="8a24d-143">Stránka Nastavení</span><span class="sxs-lookup"><span data-stu-id="8a24d-143">Settings page</span></span> | <span data-ttu-id="8a24d-144">Identifikátor URI</span><span class="sxs-lookup"><span data-stu-id="8a24d-144">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="8a24d-145">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="8a24d-145">Bluetooth</span></span>     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |
| <span data-ttu-id="8a24d-146">Myš <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8a24d-146">Mouse <sup>2</sup></span></span>      | `ms-settings:mouse` <br>  |
| <span data-ttu-id="8a24d-147">USB <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8a24d-147">USB <sup>2</sup></span></span>      | `ms-settings:usb` <br>  |

### <a name="privacy"></a><span data-ttu-id="8a24d-148">Ochrana osobních údajů</span><span class="sxs-lookup"><span data-stu-id="8a24d-148">Privacy</span></span>
| <span data-ttu-id="8a24d-149">Stránka Nastavení</span><span class="sxs-lookup"><span data-stu-id="8a24d-149">Settings page</span></span>            | <span data-ttu-id="8a24d-150">Identifikátor URI</span><span class="sxs-lookup"><span data-stu-id="8a24d-150">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="8a24d-151">Informace o účtu</span><span class="sxs-lookup"><span data-stu-id="8a24d-151">Account Info</span></span>             | `ms-settings:privacy-accountinfo`              |
| <span data-ttu-id="8a24d-152">Diagnostika aplikací</span><span class="sxs-lookup"><span data-stu-id="8a24d-152">App Diagnostics</span></span>        | `ms-settings:privacy-appdiagnostics`              |
| <span data-ttu-id="8a24d-153">Aplikace na pozadí</span><span class="sxs-lookup"><span data-stu-id="8a24d-153">Background Apps</span></span>        | `ms-settings:privacy-backgroundapps`              |
| <span data-ttu-id="8a24d-154">Kalendář</span><span class="sxs-lookup"><span data-stu-id="8a24d-154">Calendar</span></span>                 | `ms-settings:privacy-calendar`                    |
| <span data-ttu-id="8a24d-155">Historie volání</span><span class="sxs-lookup"><span data-stu-id="8a24d-155">Call History</span></span>             | `ms-settings:privacy-callhistory`                 |
| <span data-ttu-id="8a24d-156">Camera</span><span class="sxs-lookup"><span data-stu-id="8a24d-156">Camera</span></span>                   | `ms-settings:privacy-webcam`                      |
| <span data-ttu-id="8a24d-157">Kontakty</span><span class="sxs-lookup"><span data-stu-id="8a24d-157">Contacts</span></span>                 | `ms-settings:privacy-contacts`                    |
| <span data-ttu-id="8a24d-158">Zpětná vazba & diagnostiky</span><span class="sxs-lookup"><span data-stu-id="8a24d-158">Diagnostics & Feedback</span></span> | `ms-settings:privacy-feedback`                    |
| <span data-ttu-id="8a24d-159">dokumenty.</span><span class="sxs-lookup"><span data-stu-id="8a24d-159">Documents</span></span>                | `ms-settings:privacy-documents`                   |
| <span data-ttu-id="8a24d-160">E-mail</span><span class="sxs-lookup"><span data-stu-id="8a24d-160">Email</span></span>                    | `ms-settings:privacy-email`                       |
| <span data-ttu-id="8a24d-161">Systém souborů</span><span class="sxs-lookup"><span data-stu-id="8a24d-161">File system</span></span>              | `ms-settings:privacy-broadfilesystemaccess`       |
| <span data-ttu-id="8a24d-162">Obecné <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8a24d-162">General <sup>2</sup></span></span>             | `ms-settings:privacy-general`       |
| <span data-ttu-id="8a24d-163">Psaní & rukopisu <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8a24d-163">Ink & typing personalization <sup>2</sup></span></span>             | `ms-settings:privacy-speechtyping`       |
| <span data-ttu-id="8a24d-164">Umístění</span><span class="sxs-lookup"><span data-stu-id="8a24d-164">Location</span></span>                 | `ms-settings:privacy-location`                    |
| <span data-ttu-id="8a24d-165">Zasílání zpráv</span><span class="sxs-lookup"><span data-stu-id="8a24d-165">Messaging</span></span>                | `ms-settings:privacy-messaging`                   |
| <span data-ttu-id="8a24d-166">Mikrofon</span><span class="sxs-lookup"><span data-stu-id="8a24d-166">Microphone</span></span>               | `ms-settings:privacy-microphone`                  |
| <span data-ttu-id="8a24d-167">Pohyb <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8a24d-167">Motion <sup>2</sup></span></span>               | `ms-settings:privacy-motion`                  |
| <span data-ttu-id="8a24d-168">Oznámení</span><span class="sxs-lookup"><span data-stu-id="8a24d-168">Notifications</span></span>            | `ms-settings:privacy-notifications`               |
| <span data-ttu-id="8a24d-169">Další zařízení</span><span class="sxs-lookup"><span data-stu-id="8a24d-169">Other devices</span></span>            | `ms-settings:privacy-customdevices`               |
| <span data-ttu-id="8a24d-170">Obrázky</span><span class="sxs-lookup"><span data-stu-id="8a24d-170">Pictures</span></span>                 | `ms-settings:privacy-pictures`                    |
| <span data-ttu-id="8a24d-171">Rádia</span><span class="sxs-lookup"><span data-stu-id="8a24d-171">Radios</span></span>                   | `ms-settings:privacy-radios`                      |
| <span data-ttu-id="8a24d-172">Snímek obrazovky s <sup>ohraničením 2</sup></span><span class="sxs-lookup"><span data-stu-id="8a24d-172">Screenshot borders <sup>2</sup></span></span>             | `ms-settings:privacy-graphicsCaptureWithoutBorder`       |
| <span data-ttu-id="8a24d-173">Snímky obrazovky a aplikace <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8a24d-173">Screenshots and apps <sup>2</sup></span></span>             | `ms-settings:privacy-graphicsCaptureProgrammatic`       |
| <span data-ttu-id="8a24d-174">Řeč</span><span class="sxs-lookup"><span data-stu-id="8a24d-174">Speech</span></span>                   | `ms-settings:privacy-speech`                      |
| <span data-ttu-id="8a24d-175">Úlohy</span><span class="sxs-lookup"><span data-stu-id="8a24d-175">Tasks</span></span>                    | `ms-settings:privacy-tasks`                       |
| <span data-ttu-id="8a24d-176">Pohyby uživatelů</span><span class="sxs-lookup"><span data-stu-id="8a24d-176">User movements</span></span>           | `ms-settings:privacy-backgroundspatialperception` |
| <span data-ttu-id="8a24d-177">Videa</span><span class="sxs-lookup"><span data-stu-id="8a24d-177">Videos</span></span>                   | `ms-settings:privacy-videos`                      |
| <span data-ttu-id="8a24d-178">Hlasová aktivace</span><span class="sxs-lookup"><span data-stu-id="8a24d-178">Voice Activation</span></span>       | `ms-settings:privacy-voiceactivation`             |

### <a name="network--internet"></a><span data-ttu-id="8a24d-179">Síť a internet</span><span class="sxs-lookup"><span data-stu-id="8a24d-179">Network & Internet</span></span>
| <span data-ttu-id="8a24d-180">Stránka Nastavení</span><span class="sxs-lookup"><span data-stu-id="8a24d-180">Settings page</span></span> | <span data-ttu-id="8a24d-181">Identifikátor URI</span><span class="sxs-lookup"><span data-stu-id="8a24d-181">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="8a24d-182">Režim v <sup>letadle 2</sup></span><span class="sxs-lookup"><span data-stu-id="8a24d-182">Airplane Mode <sup>2</sup></span></span> | `ms-settings:network-airplanemode`        |
| <span data-ttu-id="8a24d-183">Proxy server</span><span class="sxs-lookup"><span data-stu-id="8a24d-183">Proxy</span></span> | `ms-settings:network-proxy`        |
| <span data-ttu-id="8a24d-184">Síť VPN</span><span class="sxs-lookup"><span data-stu-id="8a24d-184">VPN</span></span>   | `ms-settings:network-vpn`          |
| <span data-ttu-id="8a24d-185">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="8a24d-185">Wi-Fi</span></span>  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |



### <a name="system"></a><span data-ttu-id="8a24d-186">Systémový</span><span class="sxs-lookup"><span data-stu-id="8a24d-186">System</span></span>
| <span data-ttu-id="8a24d-187">Stránka Nastavení</span><span class="sxs-lookup"><span data-stu-id="8a24d-187">Settings page</span></span>      | <span data-ttu-id="8a24d-188">Identifikátor URI</span><span class="sxs-lookup"><span data-stu-id="8a24d-188">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="8a24d-189">Baterie <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8a24d-189">Battery <sup>2</sup></span></span>           | `ms-settings:batterysaver`<br>|
| <span data-ttu-id="8a24d-190">Baterie <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8a24d-190">Battery <sup>2</sup></span></span>           | `ms-settings:batterysaver-settings`<br>|
| <span data-ttu-id="8a24d-191">Barvy</span><span class="sxs-lookup"><span data-stu-id="8a24d-191">Colors</span></span>             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| <span data-ttu-id="8a24d-192">Hologramy <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8a24d-192">Holograms <sup>2</sup></span></span>  |  `ms-settings:holograms`  |
| <span data-ttu-id="8a24d-193"><sup>Uchýlovací 2</sup></span><span class="sxs-lookup"><span data-stu-id="8a24d-193">Calibration <sup>2</sup></span></span> |  `ms-settings:calibration` |
| <span data-ttu-id="8a24d-194">Oznámení & akce</span><span class="sxs-lookup"><span data-stu-id="8a24d-194">Notifications & actions</span></span>  | `ms-settings:notifications`          |
| <span data-ttu-id="8a24d-195">Sdílená prostředí</span><span class="sxs-lookup"><span data-stu-id="8a24d-195">Shared Experiences</span></span> | `ms-settings:crossdevice` 
| <span data-ttu-id="8a24d-196">Zvuk <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8a24d-196">Sound <sup>2</sup></span></span>           | `ms-settings:sound`<br>|
| <span data-ttu-id="8a24d-197">Zvuk > Svazek aplikace a předvolba zařízení <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8a24d-197">Sound > App volume and device preference <sup>2</sup></span></span>           | `ms-settings:apps-volume`<br>|
| <span data-ttu-id="8a24d-198">Sound > Správa zvukových zařízení <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8a24d-198">Sound > Manage sound devices <sup>2</sup></span></span>           | `ms-settings:sound-devices`<br>|
| <span data-ttu-id="8a24d-199">Storage</span><span class="sxs-lookup"><span data-stu-id="8a24d-199">Storage</span></span>            | `ms-settings:storagesense`           |
| <span data-ttu-id="8a24d-200">Konfigurace > úložiště Inteligentní úložiště <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8a24d-200">Storage > Configue Storage Sense <sup>2</sup></span></span>           | `ms-settings:storagepolicies`<br>|

### <a name="time--language"></a><span data-ttu-id="8a24d-201">Time & Language</span><span class="sxs-lookup"><span data-stu-id="8a24d-201">Time & Language</span></span>
| <span data-ttu-id="8a24d-202">Stránka Nastavení</span><span class="sxs-lookup"><span data-stu-id="8a24d-202">Settings page</span></span> | <span data-ttu-id="8a24d-203">Identifikátor URI</span><span class="sxs-lookup"><span data-stu-id="8a24d-203">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="8a24d-204">Datum & čas <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8a24d-204">Date & time <sup>2</sup></span></span> | `ms-settings:dateandtime`                  |
| <span data-ttu-id="8a24d-205">Klávesnice <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8a24d-205">Keyboard <sup>2</sup></span></span> | `ms-settings:keyboard`                  |
| <span data-ttu-id="8a24d-206">Jazyk <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8a24d-206">Language <sup>2</sup></span></span> | `ms-settings:language`                  |
| <span data-ttu-id="8a24d-207">Jazyk <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8a24d-207">Language <sup>2</sup></span></span> | `ms-settings:regionlanguage-languageoptions`                  |
| <span data-ttu-id="8a24d-208">Jazyk</span><span class="sxs-lookup"><span data-stu-id="8a24d-208">Language</span></span>      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |
| <span data-ttu-id="8a24d-209">Oblast</span><span class="sxs-lookup"><span data-stu-id="8a24d-209">Region</span></span>        | `ms-settings:regionformatting`                  |

### <a name="update--security"></a><span data-ttu-id="8a24d-210">Zabezpečení & aktualizací</span><span class="sxs-lookup"><span data-stu-id="8a24d-210">Update & Security</span></span>
| <span data-ttu-id="8a24d-211">Stránka Nastavení</span><span class="sxs-lookup"><span data-stu-id="8a24d-211">Settings page</span></span>                         | <span data-ttu-id="8a24d-212">Identifikátor URI</span><span class="sxs-lookup"><span data-stu-id="8a24d-212">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="8a24d-213">Rozšířené možnosti</span><span class="sxs-lookup"><span data-stu-id="8a24d-213">Advanced Options</span></span>                    | `ms-settings:windowsupdate-options`         |
| <span data-ttu-id="8a24d-214">Obnovení & obnovení <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8a24d-214">Reset & Recovery <sup>2</sup></span></span>      | `ms-settings:reset`         |
| <span data-ttu-id="8a24d-215">Program Windows Insider</span><span class="sxs-lookup"><span data-stu-id="8a24d-215">Windows Insider Program</span></span>               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| <span data-ttu-id="8a24d-216">Windows Update</span><span class="sxs-lookup"><span data-stu-id="8a24d-216">Windows Update</span></span>                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><span data-ttu-id="8a24d-217"><sup>1</sup>`ms-settings:windowsupdate-options`</span><span class="sxs-lookup"><span data-stu-id="8a24d-217"><sup>1</sup>`ms-settings:windowsupdate-options`</span></span><br><span data-ttu-id="8a24d-218"><sup>1</sup>`ms-settings:windowsupdate-restartoptions`</span><span class="sxs-lookup"><span data-stu-id="8a24d-218"><sup>1</sup>`ms-settings:windowsupdate-restartoptions`</span></span> |
| <span data-ttu-id="8a24d-219">služba Windows Update – Kontroluje aktualizace.</span><span class="sxs-lookup"><span data-stu-id="8a24d-219">Windows Update - Checks for updates</span></span> | `ms-settings:windowsupdate-action`          |


>  <span data-ttu-id="8a24d-220"><sup>1</sup> Ve verzích starších než Windows Holographic verze 21H1 vás následující dvě  identifikátory URI ve skutečnosti nesmídí na stránky Upřesnit možnosti **nebo** Možnosti. Zablokují nebo zobrazí jenom hlavní služba Windows Update stránky.</span><span class="sxs-lookup"><span data-stu-id="8a24d-220"><sup>1</sup> For versions prior to Windows Holographic, version 21H1, the following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
> - <span data-ttu-id="8a24d-221">ms-settings:windowsupdate-options</span><span class="sxs-lookup"><span data-stu-id="8a24d-221">ms-settings:windowsupdate-options</span></span>
> - <span data-ttu-id="8a24d-222">ms-settings:windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="8a24d-222">ms-settings:windowsupdate-restartoptions</span></span>
 
> <span data-ttu-id="8a24d-223"><sup>2</sup> – K dispozici ve Windows Holographic 21H1 nebo novějším.</span><span class="sxs-lookup"><span data-stu-id="8a24d-223"><sup>2</sup> - Available in Windows Holographic 21H1 or higher.</span></span>


<span data-ttu-id="8a24d-224">Úplný seznam identifikátorů URI Windows 10 najdete v dokumentaci ke [spouštěcím nastavením.](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)</span><span class="sxs-lookup"><span data-stu-id="8a24d-224">For a full list of Windows 10 Settings URIs, please visit the [launch settings](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
