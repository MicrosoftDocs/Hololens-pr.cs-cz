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
ms.openlocfilehash: 5ac3ff27085fd2f7c5bc1de0e461079a673bbb23
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637162"
---
# <a name="page-settings-visibility"></a><span data-ttu-id="3f08a-104">Nastavení viditelnost stránky</span><span class="sxs-lookup"><span data-stu-id="3f08a-104">Page Settings Visibility</span></span>

<span data-ttu-id="3f08a-105">jedna z spravovatelných funkcí pro HoloLens zařízení používá [zásady Nastavení/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) k omezení stránek zobrazených v rámci aplikace Nastavení.</span><span class="sxs-lookup"><span data-stu-id="3f08a-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="3f08a-106">PageVisibilityList je zásada, která správcům IT umožňuje zabránit tomu, aby určité stránky v systémové Nastavení aplikaci byly viditelné nebo přístupné, nebo aby tak učinily pro všechny stránky kromě těch, které jsou uvedené.</span><span class="sxs-lookup"><span data-stu-id="3f08a-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="3f08a-107">tato funkce je dostupné jenom v [Windows holografická, verze 20H2](hololens-release-notes.md#windows-holographic-version-20h2) nebo vyšší pro zařízení HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="3f08a-107">This feature is only avalible in [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) or higher for HoloLens 2 devices.</span></span> <span data-ttu-id="3f08a-108">Ujistěte se, že zařízení, která hodláte použít, se aktualizují.</span><span class="sxs-lookup"><span data-stu-id="3f08a-108">Please ensure devices you intend to use this for are updated.</span></span>


## <a name="examples"></a><span data-ttu-id="3f08a-109">Příklady</span><span class="sxs-lookup"><span data-stu-id="3f08a-109">Examples</span></span>
<span data-ttu-id="3f08a-110">Stránky jsou označeny zkrácenou verzí publikovaných identifikátorů URI, což je identifikátor URI mínus předpona MS-Settings:.</span><span class="sxs-lookup"><span data-stu-id="3f08a-110">Pages are identified by a shortened version of the published URIs, which is the URI minus the "ms-settings:" prefix.</span></span>

<span data-ttu-id="3f08a-111">Následující příklad ilustruje zásadu, která by povolovala přístup jenom na stránky o technologii Bluetooth, které mají identifikátor URI "síť-WiFi" a "Bluetooth":</span><span class="sxs-lookup"><span data-stu-id="3f08a-111">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "network-wifi" and "bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="3f08a-112">Následující příklad ilustruje zásadu, která by mohla skrýt stránku pro obnovení operačního systému:</span><span class="sxs-lookup"><span data-stu-id="3f08a-112">The following example illustrates a policy that would hide the OS Reset page:</span></span>
- `hide:reset`


## <a name="deploying-this-policy-via-intune"></a><span data-ttu-id="3f08a-113">Nasazení této zásady prostřednictvím Intune</span><span class="sxs-lookup"><span data-stu-id="3f08a-113">Deploying this policy via Intune</span></span>

<span data-ttu-id="3f08a-114">Jedná se o konfigurační hodnoty, které se dodávají do Intune:</span><span class="sxs-lookup"><span data-stu-id="3f08a-114">These are the configuration values that will be supplied to Intune:</span></span>

- <span data-ttu-id="3f08a-115">**Název:** Zobrazovaný název preferovaného správce pro profil.</span><span class="sxs-lookup"><span data-stu-id="3f08a-115">**Name:** An admin preferred display name for the profile.</span></span>
- <span data-ttu-id="3f08a-116">**OMA-URI:** Plně kvalifikovaný identifikátor URI stránky nastavení, včetně jejího [oboru](/windows/client-management/mdm/policy-configuration-service-provider).</span><span class="sxs-lookup"><span data-stu-id="3f08a-116">**OMA-URI:** The fully qualified URI of the setting page including its [scope](/windows/client-management/mdm/policy-configuration-service-provider).</span></span> <span data-ttu-id="3f08a-117">Tento příklad na této stránce používá `./Device` obor.</span><span class="sxs-lookup"><span data-stu-id="3f08a-117">This examples on this page are using the `./Device` scope.</span></span>
- <span data-ttu-id="3f08a-118">**Hodnota:** Řetězcová hodnota, která označuje, zda se mají skrýt nebo zobrazit *pouze* zadané stránky.</span><span class="sxs-lookup"><span data-stu-id="3f08a-118">**Value:** A string value that indicates whether to hide or show *only* the specified pages.</span></span> <span data-ttu-id="3f08a-119">Možné hodnoty jsou `hide:<pagename>` a `showonly:<pagename>` .</span><span class="sxs-lookup"><span data-stu-id="3f08a-119">Possible values are `hide:<pagename>` and `showonly:<pagename>`.</span></span> 
 
<span data-ttu-id="3f08a-120">Více stránek je možné zadat tak, že je oddělíte středníkem, a seznam běžných stránek najdete níže.</span><span class="sxs-lookup"><span data-stu-id="3f08a-120">Multiple pages can be specified by separating them with a semicolon, and a listing of common pages can be found below.</span></span>

1. <span data-ttu-id="3f08a-121">Vytvořte **vlastní zásadu**.</span><span class="sxs-lookup"><span data-stu-id="3f08a-121">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="3f08a-122">Při nastavování **OMA-URI** zadejte plně vymezený identifikátor URI.</span><span class="sxs-lookup"><span data-stu-id="3f08a-122">When setting the **OMA-URI** enter the fully scoped URI.</span></span> <span data-ttu-id="3f08a-123">Například: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span><span class="sxs-lookup"><span data-stu-id="3f08a-123">For example: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="3f08a-124">Když vybíráte výběr dat, zvolte: **řetězec** .</span><span class="sxs-lookup"><span data-stu-id="3f08a-124">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="3f08a-125">Při zadávání **hodnoty** použijte pokyny výše.</span><span class="sxs-lookup"><span data-stu-id="3f08a-125">When specifying **Value** use the guidance above.</span></span> <span data-ttu-id="3f08a-126">Například: **`showonly:network-wifi;network-proxy;bluetooth`** nebo **`hide:reset`**</span><span class="sxs-lookup"><span data-stu-id="3f08a-126">For example: **`showonly:network-wifi;network-proxy;bluetooth`** or **`hide:reset`**</span></span> 
> [!IMPORTANT]
> <span data-ttu-id="3f08a-127">Ujistěte se, že jste přidělili vlastní konfiguraci zařízení skupině, na kterou má zařízení nacházet.</span><span class="sxs-lookup"><span data-stu-id="3f08a-127">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span> <span data-ttu-id="3f08a-128">Pokud tento krok není proveden, zásada bude vložena, ale nebude použita.</span><span class="sxs-lookup"><span data-stu-id="3f08a-128">If this step is not performed, the policy will be pushed but won't be applied.</span></span>

<span data-ttu-id="3f08a-129">další informace o skupinách a konfiguracích zařízení služby intune najdete v tématu [HoloLens konfigurace MDM](hololens-mdm-configure.md) .</span><span class="sxs-lookup"><span data-stu-id="3f08a-129">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>


## <a name="deploying-this-policy-via-a-provisioning-package"></a><span data-ttu-id="3f08a-130">Nasazení této zásady prostřednictvím zřizovacího balíčku</span><span class="sxs-lookup"><span data-stu-id="3f08a-130">Deploying this policy via a Provisioning Package</span></span>

<span data-ttu-id="3f08a-131">jedná se o konfigurační hodnoty, které budou zadány v nástroji Windows configuration Designer:</span><span class="sxs-lookup"><span data-stu-id="3f08a-131">These are the configuration values that will be specified in Windows Configuration Designer:</span></span>

<span data-ttu-id="3f08a-132">**Hodnota:** Řetězcová hodnota, která označuje, zda se mají skrýt nebo zobrazit *pouze* zadané stránky.</span><span class="sxs-lookup"><span data-stu-id="3f08a-132">**Value:** A string value that indicates whether to hide or show *only* the specified pages.</span></span> <span data-ttu-id="3f08a-133">Možné hodnoty jsou `hide:<pagename>` a `showonly:<pagename>` .</span><span class="sxs-lookup"><span data-stu-id="3f08a-133">Possible values are `hide:<pagename>` and `showonly:<pagename>`.</span></span> <span data-ttu-id="3f08a-134">Více stránek je možné zadat tak, že je oddělíte středníkem, a seznam běžných stránek najdete níže.</span><span class="sxs-lookup"><span data-stu-id="3f08a-134">Multiple pages can be specified by separating them with a semicolon, and a listing of common pages can be found below.</span></span>


1. <span data-ttu-id="3f08a-135">při vytváření balíčku v návrháři konfigurace Windows přejděte na **zásady > Nastavení > PageVisibilityList**</span><span class="sxs-lookup"><span data-stu-id="3f08a-135">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="3f08a-136">Zadejte řetězec: **`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="3f08a-136">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="3f08a-137">Exportujte zřizovací balíček.</span><span class="sxs-lookup"><span data-stu-id="3f08a-137">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="3f08a-138">Použijte balíček pro vaše zařízení.</span><span class="sxs-lookup"><span data-stu-id="3f08a-138">Apply the package to your device.</span></span>
<span data-ttu-id="3f08a-139">úplné informace o tom, jak vytvořit a použít zřizovací balíček, najdete [na stránce věnovaném zřizování HoloLens](hololens-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="3f08a-139">For full details on how to create and apply a provisioning package visit [the HoloLens provisioning page](hololens-provisioning.md).</span></span>


<span data-ttu-id="3f08a-140">bez ohledu na zvolenou metodu by vaše zařízení nyní mělo přijímat změny a uživatelům se zobrazí následující aplikace Nastavení.</span><span class="sxs-lookup"><span data-stu-id="3f08a-140">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![snímek obrazovky s aktivními hodinami upravovanými v aplikaci Nastavení](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="3f08a-142">pokud chcete nakonfigurovat stránky aplikace Nastavení tak, aby zobrazovaly nebo skryly vlastní výběr stránek, podívejte se na Nastavení identifikátory uri, které jsou k dispozici na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3f08a-142">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <a name="settings-uris"></a><span data-ttu-id="3f08a-143">Nastavení Identifikátory URI</span><span class="sxs-lookup"><span data-stu-id="3f08a-143">Settings URIs</span></span>

<span data-ttu-id="3f08a-144">HoloLens zařízení a Windows 10 zařízení mají v rámci aplikace Nastavení jinou možnost výběru stránek.</span><span class="sxs-lookup"><span data-stu-id="3f08a-144">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="3f08a-145">Na této stránce najdete pouze nastavení, která existují na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="3f08a-145">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <a name="accounts"></a><span data-ttu-id="3f08a-146">Účty</span><span class="sxs-lookup"><span data-stu-id="3f08a-146">Accounts</span></span>
| <span data-ttu-id="3f08a-147">Stránka Nastavení</span><span class="sxs-lookup"><span data-stu-id="3f08a-147">Settings page</span></span>           | <span data-ttu-id="3f08a-148">Identifikátor URI</span><span class="sxs-lookup"><span data-stu-id="3f08a-148">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="3f08a-149">Přístup do práce nebo do školy</span><span class="sxs-lookup"><span data-stu-id="3f08a-149">Access work or school</span></span> | `workplace`                         |
| <span data-ttu-id="3f08a-150">Registrace Iris</span><span class="sxs-lookup"><span data-stu-id="3f08a-150">Iris Enrollment</span></span>       | `signinoptions-launchirisenrollment` |
| <span data-ttu-id="3f08a-151">Možnosti přihlášení</span><span class="sxs-lookup"><span data-stu-id="3f08a-151">Sign In Options</span></span>         | ` signinoptions `                   |

### <a name="apps"></a><span data-ttu-id="3f08a-152">Aplikace</span><span class="sxs-lookup"><span data-stu-id="3f08a-152">Apps</span></span>
| <span data-ttu-id="3f08a-153">Stránka Nastavení</span><span class="sxs-lookup"><span data-stu-id="3f08a-153">Settings page</span></span> | <span data-ttu-id="3f08a-154">Identifikátor URI</span><span class="sxs-lookup"><span data-stu-id="3f08a-154">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="3f08a-155">Aplikace & funkce <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3f08a-155">Apps & features <sup>2</sup></span></span>     | `appsfeatures` <br> |
| <span data-ttu-id="3f08a-156">Aplikace & funkce > pokročilé možnosti <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3f08a-156">Apps & features > Advanced Options <sup>2</sup></span></span>     | `appsfeatures-app` <br> |
| <span data-ttu-id="3f08a-157">aplikace & funkce > Offline Mapy <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3f08a-157">Apps & features > Offline Maps <sup>2</sup></span></span>     | `maps-maps` <br> |
| <span data-ttu-id="3f08a-158">aplikace & funkce > Offline Mapy > stáhnout mapy <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3f08a-158">Apps & features > Offline Maps > Download maps <sup>2</sup></span></span>     | `maps-downloadmaps` <br> |

### <a name="devices"></a><span data-ttu-id="3f08a-159">Zařízení</span><span class="sxs-lookup"><span data-stu-id="3f08a-159">Devices</span></span>
| <span data-ttu-id="3f08a-160">Stránka Nastavení</span><span class="sxs-lookup"><span data-stu-id="3f08a-160">Settings page</span></span> | <span data-ttu-id="3f08a-161">Identifikátor URI</span><span class="sxs-lookup"><span data-stu-id="3f08a-161">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="3f08a-162">Bluetooth</span><span class="sxs-lookup"><span data-stu-id="3f08a-162">Bluetooth</span></span>     | `bluetooth` <br> `connecteddevices` |
| <span data-ttu-id="3f08a-163">Myš <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3f08a-163">Mouse <sup>2</sup></span></span>      | `mouse` <br>  |
| <span data-ttu-id="3f08a-164">USB <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3f08a-164">USB <sup>2</sup></span></span>      | `usb` <br>  |

### <a name="privacy"></a><span data-ttu-id="3f08a-165">Ochrana osobních údajů</span><span class="sxs-lookup"><span data-stu-id="3f08a-165">Privacy</span></span>
| <span data-ttu-id="3f08a-166">Stránka Nastavení</span><span class="sxs-lookup"><span data-stu-id="3f08a-166">Settings page</span></span>            | <span data-ttu-id="3f08a-167">Identifikátor URI</span><span class="sxs-lookup"><span data-stu-id="3f08a-167">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="3f08a-168">Informace o účtu</span><span class="sxs-lookup"><span data-stu-id="3f08a-168">Account Info</span></span>             | `privacy-accountinfo`              |
| <span data-ttu-id="3f08a-169">Diagnostika aplikací</span><span class="sxs-lookup"><span data-stu-id="3f08a-169">App Diagnostics</span></span>        | `privacy-appdiagnostics`              |
| <span data-ttu-id="3f08a-170">Aplikace na pozadí</span><span class="sxs-lookup"><span data-stu-id="3f08a-170">Background Apps</span></span>        | `privacy-backgroundapps`              |
| <span data-ttu-id="3f08a-171">Kalendář</span><span class="sxs-lookup"><span data-stu-id="3f08a-171">Calendar</span></span>                 | `privacy-calendar`                    |
| <span data-ttu-id="3f08a-172">Historie volání</span><span class="sxs-lookup"><span data-stu-id="3f08a-172">Call History</span></span>             | `privacy-callhistory`                 |
| <span data-ttu-id="3f08a-173">Camera</span><span class="sxs-lookup"><span data-stu-id="3f08a-173">Camera</span></span>                   | `privacy-webcam`                      |
| <span data-ttu-id="3f08a-174">Kontakty</span><span class="sxs-lookup"><span data-stu-id="3f08a-174">Contacts</span></span>                 | `privacy-contacts`                    |
| <span data-ttu-id="3f08a-175">Diagnostika & zpětná vazba</span><span class="sxs-lookup"><span data-stu-id="3f08a-175">Diagnostics & Feedback</span></span> | `privacy-feedback`                    |
| <span data-ttu-id="3f08a-176">dokumenty.</span><span class="sxs-lookup"><span data-stu-id="3f08a-176">Documents</span></span>                | `privacy-documents`                   |
| <span data-ttu-id="3f08a-177">E-mail</span><span class="sxs-lookup"><span data-stu-id="3f08a-177">Email</span></span>                    | `privacy-email`                       |
| <span data-ttu-id="3f08a-178">Systém souborů</span><span class="sxs-lookup"><span data-stu-id="3f08a-178">File system</span></span>              | `privacy-broadfilesystemaccess`       |
| <span data-ttu-id="3f08a-179">Obecné <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3f08a-179">General <sup>2</sup></span></span>             | `privacy-general`       |
| <span data-ttu-id="3f08a-180">Ink & – přizpůsobení textu <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3f08a-180">Ink & typing personalization <sup>2</sup></span></span>             | `privacy-speechtyping`       |
| <span data-ttu-id="3f08a-181">Umístění</span><span class="sxs-lookup"><span data-stu-id="3f08a-181">Location</span></span>                 | `privacy-location`                    |
| <span data-ttu-id="3f08a-182">Zasílání zpráv</span><span class="sxs-lookup"><span data-stu-id="3f08a-182">Messaging</span></span>                | `privacy-messaging`                   |
| <span data-ttu-id="3f08a-183">Mikrofon</span><span class="sxs-lookup"><span data-stu-id="3f08a-183">Microphone</span></span>               | `privacy-microphone`                  |
| <span data-ttu-id="3f08a-184">Pohyb <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3f08a-184">Motion <sup>2</sup></span></span>               | `privacy-motion`                  |
| <span data-ttu-id="3f08a-185">Oznámení</span><span class="sxs-lookup"><span data-stu-id="3f08a-185">Notifications</span></span>            | `privacy-notifications`               |
| <span data-ttu-id="3f08a-186">Jiná zařízení</span><span class="sxs-lookup"><span data-stu-id="3f08a-186">Other devices</span></span>            | `privacy-customdevices`               |
| <span data-ttu-id="3f08a-187">Obrázky</span><span class="sxs-lookup"><span data-stu-id="3f08a-187">Pictures</span></span>                 | `privacy-pictures`                    |
| <span data-ttu-id="3f08a-188">Radiostanicím</span><span class="sxs-lookup"><span data-stu-id="3f08a-188">Radios</span></span>                   | `privacy-radios`                      |
| <span data-ttu-id="3f08a-189">Snímek obrazovky s ohraničením <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3f08a-189">Screenshot borders <sup>2</sup></span></span>             | `privacy-graphicsCaptureWithoutBorder`       |
| <span data-ttu-id="3f08a-190">Snímky obrazovky a aplikace <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3f08a-190">Screenshots and apps <sup>2</sup></span></span>             | `privacy-graphicsCaptureProgrammatic`       |
| <span data-ttu-id="3f08a-191">Řeč</span><span class="sxs-lookup"><span data-stu-id="3f08a-191">Speech</span></span>                   | `privacy-speech`                      |
| <span data-ttu-id="3f08a-192">Úkoly</span><span class="sxs-lookup"><span data-stu-id="3f08a-192">Tasks</span></span>                    | `privacy-tasks`                       |
| <span data-ttu-id="3f08a-193">Pohyby uživatelů</span><span class="sxs-lookup"><span data-stu-id="3f08a-193">User movements</span></span>           | `privacy-backgroundspatialperception` |
| <span data-ttu-id="3f08a-194">Videa</span><span class="sxs-lookup"><span data-stu-id="3f08a-194">Videos</span></span>                   | `privacy-videos`                      |
| <span data-ttu-id="3f08a-195">Aktivace hlasu</span><span class="sxs-lookup"><span data-stu-id="3f08a-195">Voice Activation</span></span>       | `privacy-voiceactivation`             |

### <a name="network--internet"></a><span data-ttu-id="3f08a-196">Síť a internet</span><span class="sxs-lookup"><span data-stu-id="3f08a-196">Network & Internet</span></span>
| <span data-ttu-id="3f08a-197">Stránka Nastavení</span><span class="sxs-lookup"><span data-stu-id="3f08a-197">Settings page</span></span> | <span data-ttu-id="3f08a-198">Identifikátor URI</span><span class="sxs-lookup"><span data-stu-id="3f08a-198">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="3f08a-199">Režim v letadle <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3f08a-199">Airplane Mode <sup>2</sup></span></span> | `network-airplanemode`        |
| <span data-ttu-id="3f08a-200">Proxy server</span><span class="sxs-lookup"><span data-stu-id="3f08a-200">Proxy</span></span> | `network-proxy`        |
| <span data-ttu-id="3f08a-201">Síť VPN</span><span class="sxs-lookup"><span data-stu-id="3f08a-201">VPN</span></span>   | `network-vpn`          |
| <span data-ttu-id="3f08a-202">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="3f08a-202">Wi-Fi</span></span>  | `network-wifi`<br>`network-wifisettings`<br>`network-status`<br>`wifi-provisioning`    |



### <a name="system"></a><span data-ttu-id="3f08a-203">Systémový</span><span class="sxs-lookup"><span data-stu-id="3f08a-203">System</span></span>
| <span data-ttu-id="3f08a-204">Stránka Nastavení</span><span class="sxs-lookup"><span data-stu-id="3f08a-204">Settings page</span></span>      | <span data-ttu-id="3f08a-205">Identifikátor URI</span><span class="sxs-lookup"><span data-stu-id="3f08a-205">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="3f08a-206">Baterie <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3f08a-206">Battery <sup>2</sup></span></span>           | `batterysaver`<br>|
| <span data-ttu-id="3f08a-207">Baterie <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3f08a-207">Battery <sup>2</sup></span></span>           | `batterysaver-settings`<br>|
| <span data-ttu-id="3f08a-208">Barvy</span><span class="sxs-lookup"><span data-stu-id="3f08a-208">Colors</span></span>             | `colors`<br>`personalization-colors` |
| <span data-ttu-id="3f08a-209">Hologramy <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3f08a-209">Holograms <sup>2</sup></span></span>  |  `holograms`  |
| <span data-ttu-id="3f08a-210"><sup>Uchýlovací 2</sup></span><span class="sxs-lookup"><span data-stu-id="3f08a-210">Calibration <sup>2</sup></span></span> |  `calibration` |
| <span data-ttu-id="3f08a-211">Oznámení & akcích</span><span class="sxs-lookup"><span data-stu-id="3f08a-211">Notifications & actions</span></span>  | `notifications`          |
| <span data-ttu-id="3f08a-212">Sdílená prostředí</span><span class="sxs-lookup"><span data-stu-id="3f08a-212">Shared Experiences</span></span> | `crossdevice` 
| <span data-ttu-id="3f08a-213">Zvuk <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3f08a-213">Sound <sup>2</sup></span></span>           | `sound`<br>|
| <span data-ttu-id="3f08a-214">Zvuk > Svazek aplikace a předvolba zařízení <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3f08a-214">Sound > App volume and device preference <sup>2</sup></span></span>           | `apps-volume`<br>|
| <span data-ttu-id="3f08a-215">Sound > Správa zvukových zařízení <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3f08a-215">Sound > Manage sound devices <sup>2</sup></span></span>           | `sound-devices`<br>|
| <span data-ttu-id="3f08a-216">Storage</span><span class="sxs-lookup"><span data-stu-id="3f08a-216">Storage</span></span>            | `storagesense`           |
| <span data-ttu-id="3f08a-217">Storage > konfigurace Storage Sense <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3f08a-217">Storage > Configure Storage Sense <sup>2</sup></span></span>           | `storagepolicies`<br>|

### <a name="time--language"></a><span data-ttu-id="3f08a-218">Time & Language</span><span class="sxs-lookup"><span data-stu-id="3f08a-218">Time & Language</span></span>
| <span data-ttu-id="3f08a-219">Stránka Nastavení</span><span class="sxs-lookup"><span data-stu-id="3f08a-219">Settings page</span></span> | <span data-ttu-id="3f08a-220">Identifikátor URI</span><span class="sxs-lookup"><span data-stu-id="3f08a-220">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="3f08a-221">Datum & čas <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3f08a-221">Date & time <sup>2</sup></span></span> | `dateandtime`                  |
| <span data-ttu-id="3f08a-222">Klávesnice <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3f08a-222">Keyboard <sup>2</sup></span></span> | `keyboard`                  |
| <span data-ttu-id="3f08a-223">Jazyk <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3f08a-223">Language <sup>2</sup></span></span> | `language`                  |
| <span data-ttu-id="3f08a-224">Jazyk <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3f08a-224">Language <sup>2</sup></span></span> | `regionlanguage-languageoptions`                  |
| <span data-ttu-id="3f08a-225">Jazyk</span><span class="sxs-lookup"><span data-stu-id="3f08a-225">Language</span></span>      | `regionlanguage`<br>`regionlanguage-adddisplaylanguage`<br>`regionlanguage-setdisplaylanguage` |
| <span data-ttu-id="3f08a-226">Oblast</span><span class="sxs-lookup"><span data-stu-id="3f08a-226">Region</span></span>        | `regionformatting`                  |

### <a name="update--security"></a><span data-ttu-id="3f08a-227">Zabezpečení & aktualizací</span><span class="sxs-lookup"><span data-stu-id="3f08a-227">Update & Security</span></span>
| <span data-ttu-id="3f08a-228">Stránka Nastavení</span><span class="sxs-lookup"><span data-stu-id="3f08a-228">Settings page</span></span>                         | <span data-ttu-id="3f08a-229">Identifikátor URI</span><span class="sxs-lookup"><span data-stu-id="3f08a-229">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="3f08a-230">Rozšířené možnosti</span><span class="sxs-lookup"><span data-stu-id="3f08a-230">Advanced Options</span></span>                    | `windowsupdate-options`         |
| <span data-ttu-id="3f08a-231">Obnovení & obnovení <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="3f08a-231">Reset & Recovery <sup>2</sup></span></span>      | `reset`         |
| <span data-ttu-id="3f08a-232">Program Windows Insider</span><span class="sxs-lookup"><span data-stu-id="3f08a-232">Windows Insider Program</span></span>               | `windowsinsider` <br>`windowsinsider-optin`          |
| <span data-ttu-id="3f08a-233">Windows Update</span><span class="sxs-lookup"><span data-stu-id="3f08a-233">Windows Update</span></span>                        | `windowsupdate`<br> `windowsupdate-activehours`  <br> `windowsupdate-history` <br> `windowsupdate-optionalupdates` <br><span data-ttu-id="3f08a-234"><sup>1</sup>`windowsupdate-options`</span><span class="sxs-lookup"><span data-stu-id="3f08a-234"><sup>1</sup>`windowsupdate-options`</span></span><br><span data-ttu-id="3f08a-235"><sup>1</sup>`windowsupdate-restartoptions`</span><span class="sxs-lookup"><span data-stu-id="3f08a-235"><sup>1</sup>`windowsupdate-restartoptions`</span></span> |
| <span data-ttu-id="3f08a-236">Windows Aktualizace – kontroluje aktualizace.</span><span class="sxs-lookup"><span data-stu-id="3f08a-236">Windows Update - Checks for updates</span></span> | `windowsupdate-action`          |


- <span data-ttu-id="3f08a-237"><sup>1</sup> – Ve verzích starších než Windows Holographic verze 21H1 vás následující dvě  identifikátory URI ve skutečnosti nesmídí na stránky Upřesnit možnosti nebo **Možnosti.** Zablokují nebo zobrazí jenom hlavní stránku Windows Aktualizace.</span><span class="sxs-lookup"><span data-stu-id="3f08a-237"><sup>1</sup> - For versions prior to Windows Holographic, version 21H1, the following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
  -  <span data-ttu-id="3f08a-238">windowsupdate-options</span><span class="sxs-lookup"><span data-stu-id="3f08a-238">windowsupdate-options</span></span>
  -  <span data-ttu-id="3f08a-239">windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="3f08a-239">windowsupdate-restartoptions</span></span>

- <span data-ttu-id="3f08a-240"><sup>2</sup> – K dispozici Windows Holographic 21H1 nebo novějším.</span><span class="sxs-lookup"><span data-stu-id="3f08a-240"><sup>2</sup> - Available in Windows Holographic 21H1 or higher.</span></span>


<span data-ttu-id="3f08a-241">Úplný seznam identifikátorů URI Windows 10 Nastavení najdete v dokumentaci [ke spouštěcím nastavením.](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)</span><span class="sxs-lookup"><span data-stu-id="3f08a-241">For a full list of Windows 10 Settings URIs, please visit the [launch settings](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
