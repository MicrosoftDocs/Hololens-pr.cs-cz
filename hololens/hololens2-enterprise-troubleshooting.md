---
title: HoloLens 2 implementace a řešení potíží se spravovaným zařízením
description: řešení potíží s HoloLens 2 zařízeními v prostředí Enterprise
author: JoyJaz
ms.author: v-jjaswinski
ms.date: 6/22/2021
ms.topic: article
keywords: řešení potíží
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 9f3950de51e4bfa2a76431a2a070d87aa81ed443
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636873"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a><span data-ttu-id="a1223-104">Řešení potíží s implementací a spravovanými zařízeními</span><span class="sxs-lookup"><span data-stu-id="a1223-104">Troubleshooting implementation and managed devices</span></span> 

<span data-ttu-id="a1223-105">tento článek popisuje, jak vyřešit několik problémů nebo odpovědi na otázky týkající se implementace a správy HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="a1223-105">This article describes how to resolve several issues or answer questions regarding implementation and management of HoloLens 2.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="a1223-106">Než začnete s postupem řešení potíží, ujistěte se, že se na zařízení účtuje **20 až 40 procent** kapacity baterie, pokud je to možné.</span><span class="sxs-lookup"><span data-stu-id="a1223-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="a1223-107">[Indikátory baterie](hololens2-setup.md#lights-that-indicate-the-battery-level) umístěné pod tlačítkem napájení jsou rychlým způsobem, jak ověřit kapacitu baterie bez přihlášení do zařízení.</span><span class="sxs-lookup"><span data-stu-id="a1223-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>


<a id="list"></a>
- [<span data-ttu-id="a1223-108">Řešení potíží s protokolem EAP</span><span class="sxs-lookup"><span data-stu-id="a1223-108">EAP Troubleshooting</span></span>](#eap-troubleshooting)
- [<span data-ttu-id="a1223-109">Řešení potíží Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="a1223-109">Wi-Fi Troubleshooting</span></span>](#wi-fi-troubleshooting)
- [<span data-ttu-id="a1223-110">Řešení potíží se sítí</span><span class="sxs-lookup"><span data-stu-id="a1223-110">Network Troubleshooting</span></span>](#network-troubleshooting)
- [<span data-ttu-id="a1223-111">nepovedlo se přihlásit k dřív nastavenému HoloLens zařízení.</span><span class="sxs-lookup"><span data-stu-id="a1223-111">Can't sign in to a previously setup HoloLens device</span></span>](#cant-sign-in-to-a-previously-setup-hololens-device)
- [<span data-ttu-id="a1223-112">po aktualizaci na Windows holografické 21H1 se nedá přihlásit.</span><span class="sxs-lookup"><span data-stu-id="a1223-112">Can't login after updating to Windows Holographic 21H1</span></span>](#cant-login-after-updating-to-windows-holographic-21h1)
- [<span data-ttu-id="a1223-113">Řešení potíží s autopilotem</span><span class="sxs-lookup"><span data-stu-id="a1223-113">Autopilot Troubleshooting</span></span>](#autopilot-troubleshooting)
- [<span data-ttu-id="a1223-114">nejčastější dotazy týkající se spravovaných HoloLens zařízení</span><span class="sxs-lookup"><span data-stu-id="a1223-114">Managed HoloLens Devices FAQs</span></span>](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a><span data-ttu-id="a1223-115">Řešení potíží s protokolem EAP</span><span class="sxs-lookup"><span data-stu-id="a1223-115">EAP Troubleshooting</span></span>
1. <span data-ttu-id="a1223-116">Dvojitá check Wi-Fi profil má správné nastavení:</span><span class="sxs-lookup"><span data-stu-id="a1223-116">Double check Wi-Fi profile has right settings:</span></span>
    - <span data-ttu-id="a1223-117">Typ protokolu EAP je správně nakonfigurovaný, běžné typy protokolu EAP: EAP-TLS (13), EAP-TTLS (21) a PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="a1223-117">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
    - <span data-ttu-id="a1223-118">Název SSID Wi-Fi je vpravo a odpovídá řetězci HEX.</span><span class="sxs-lookup"><span data-stu-id="a1223-118">Wi-Fi SSID name is right and matches with HEX string.</span></span>
    - <span data-ttu-id="a1223-119">Pro EAP-TLS obsahuje TrustedRootCA hodnotu hash SHA-1 certifikátu důvěryhodné kořenové certifikační autority serveru.</span><span class="sxs-lookup"><span data-stu-id="a1223-119">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server's trusted root CA certificate.</span></span> <span data-ttu-id="a1223-120">v Windows počítači "certutil.exe-dump cert_file_name" příkaz zobrazí řetězec hash SHA-1 certifikátu.</span><span class="sxs-lookup"><span data-stu-id="a1223-120">On Windows PC "certutil.exe -dump cert_file_name" command will show a certificate's SHA-1 hash string.</span></span>
2. <span data-ttu-id="a1223-121">Shromažďovat Zachytávání síťových paketů v protokolech přístupového bodu nebo řadiči serveru AAA, kde zjistíte, kde se relace protokolu EAP nezdařila.</span><span class="sxs-lookup"><span data-stu-id="a1223-121">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
    - <span data-ttu-id="a1223-122">pokud se neočekává identita EAP, kterou poskytuje HoloLens, ověřte, jestli se identita správně zřídila prostřednictvím profilu Wi-Fi nebo klientského certifikátu.</span><span class="sxs-lookup"><span data-stu-id="a1223-122">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
    - <span data-ttu-id="a1223-123">pokud server odmítne HoloLens klientský certifikát, ověřte, jestli je na zařízení požadovaný klientský certifikát zřízený.</span><span class="sxs-lookup"><span data-stu-id="a1223-123">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
    - <span data-ttu-id="a1223-124">pokud HoloLens odmítne certifikát serveru, ověřte, zda byl certifikát kořenové certifikační autority serveru zřízený v HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a1223-124">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
3. <span data-ttu-id="a1223-125">pokud se profil rozlehlé sítě zřídí prostřednictvím balíčku pro Wi-Fi zřizování, zvažte použití zřizovacího balíčku na počítači s Windows 10.</span><span class="sxs-lookup"><span data-stu-id="a1223-125">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="a1223-126">pokud se také na Windows 10 počítači nepovede, postupujte podle příručky Windows klienta řešení potíží s ověřováním 802.1 x.</span><span class="sxs-lookup"><span data-stu-id="a1223-126">If it also fails on Windows 10 PC, follow the Windows client 802.1X authentication troubleshooting guide.</span></span>
4. <span data-ttu-id="a1223-127">Pošlete nám svůj názor prostřednictvím centra zpětné vazby.</span><span class="sxs-lookup"><span data-stu-id="a1223-127">Send us feedback through Feedback Hub.</span></span>

[<span data-ttu-id="a1223-128">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="a1223-128">Back to list</span></span>](#list)

## <a name="wi-fi-troubleshooting"></a><span data-ttu-id="a1223-129">Řešení potíží s Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="a1223-129">Wi-Fi Troubleshooting</span></span>

<span data-ttu-id="a1223-130">tady je několik věcí, které můžete vyzkoušet, pokud nemůžete připojit HoloLens k síti Wi-Fi:</span><span class="sxs-lookup"><span data-stu-id="a1223-130">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

1. <span data-ttu-id="a1223-131">Ujistěte se, že je zapnutá Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="a1223-131">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="a1223-132">pokud chcete kontrolu ověřit, použijte gesto Start a pak vyberte Nastavení > síti & Internet > Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="a1223-132">To check, use the Start gesture, then select Settings > Network & Internet > Wi-Fi.</span></span> <span data-ttu-id="a1223-133">Pokud je Wi-Fi zapnutá, zkuste ji vypnout a znovu zapnout.</span><span class="sxs-lookup"><span data-stu-id="a1223-133">If Wi-Fi is on, try turning it off and then on again.</span></span>
2. <span data-ttu-id="a1223-134">Posuňte se blíž ke směrovači nebo přístupovému bodu.</span><span class="sxs-lookup"><span data-stu-id="a1223-134">Move closer to the router or access point.</span></span>
3. <span data-ttu-id="a1223-135">Restartujte směrovač Wi-Fi a pak znovu spusťte HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a1223-135">Restart your Wi-Fi router, then restart HoloLens.</span></span> <span data-ttu-id="a1223-136">Zkuste se znovu připojit.</span><span class="sxs-lookup"><span data-stu-id="a1223-136">Try connecting again.</span></span>
4. <span data-ttu-id="a1223-137">Pokud žádná z těchto věcí nefunguje, zkontrolujte, zda směrovač používá nejnovější firmware.</span><span class="sxs-lookup"><span data-stu-id="a1223-137">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="a1223-138">Tyto informace najdete na webu výrobce.</span><span class="sxs-lookup"><span data-stu-id="a1223-138">You can find this information on the manufacturer website.</span></span>

<span data-ttu-id="a1223-139">Když se na zařízení přihlašujete k podnikovému nebo organizačnímu účtu, může taky použít zásady správy mobilních zařízení (MDM), pokud je zásada nakonfigurovaná správcem IT.</span><span class="sxs-lookup"><span data-stu-id="a1223-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

[<span data-ttu-id="a1223-140">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="a1223-140">Back to list</span></span>](#list)

## <a name="network-troubleshooting"></a><span data-ttu-id="a1223-141">Řešení potíží se sítí</span><span class="sxs-lookup"><span data-stu-id="a1223-141">Network Troubleshooting</span></span>
<span data-ttu-id="a1223-142">pokud jsou problémy se sítí překážkou úspěšného nasazení a používání HoloLens 2 ve vaší organizaci, nakonfigurujte Fiddler a/nebo Wireshark pro zachycení a analýzu přenosů HTTP/HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a1223-142">If network issues are an obstacle to successfully deploying and using HoloLens 2 in your organization, configure Fiddler and/or Wireshark to capture and analyze HTTP/HTTPS traffic.</span></span> 

### <a name="configure-fiddler-to-capture-http-traffic"></a><span data-ttu-id="a1223-143">Konfigurace Fiddler pro zachycení přenosů HTTP</span><span class="sxs-lookup"><span data-stu-id="a1223-143">Configure Fiddler to capture HTTP traffic</span></span>
<span data-ttu-id="a1223-144">Fiddler je webový ladicí proxy server, který se používá k odstraňování potíží s HTTP (S).</span><span class="sxs-lookup"><span data-stu-id="a1223-144">Fiddler is a web debugging proxy and is used to troubleshoot HTTP(S) issues.</span></span> <span data-ttu-id="a1223-145">Zachycuje všechny požadavky HTTP, které počítač provede, a zaznamená všechny přidružené k němu.</span><span class="sxs-lookup"><span data-stu-id="a1223-145">It captures every HTTP request the computer makes and records everything associated with it.</span></span> <span data-ttu-id="a1223-146">řešení potíží s ověřováním koncových uživatelů pro vaše aplikace HTTPS vám umožní lépe zvýšit produktivitu a efektivitu pro cíle HoloLens 2 případy použití.</span><span class="sxs-lookup"><span data-stu-id="a1223-146">Uncovering end-user authentication issues for your HTTPS apps drives better productivity and efficiency for your target HoloLens 2 use cases.</span></span> 

#### <a name="prerequisites"></a><span data-ttu-id="a1223-147">Požadavky</span><span class="sxs-lookup"><span data-stu-id="a1223-147">Prerequisites</span></span>
 
- <span data-ttu-id="a1223-148">zařízení HoloLens 2 a váš počítač musí být ve stejné síti.</span><span class="sxs-lookup"><span data-stu-id="a1223-148">HoloLens 2 devices and your PC must be on the same network</span></span>
- <span data-ttu-id="a1223-149">Poznamenejte si IP adresu vašeho počítače.</span><span class="sxs-lookup"><span data-stu-id="a1223-149">Note the IP address of your PC</span></span>

#### <a name="install-and-configure-fiddler"></a><span data-ttu-id="a1223-150">Instalace a konfigurace Fiddler</span><span class="sxs-lookup"><span data-stu-id="a1223-150">Install and Configure Fiddler</span></span>

1. <span data-ttu-id="a1223-151">Na počítači [nainstalujte](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) a spusťte Fiddler.</span><span class="sxs-lookup"><span data-stu-id="a1223-151">On your PC - [install](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) and start Fiddler.</span></span>  
1. <span data-ttu-id="a1223-152">V počítači nakonfigurujte Fiddler tak, aby umožňovaly připojení vzdálených počítačů.</span><span class="sxs-lookup"><span data-stu-id="a1223-152">On your PC - configure Fiddler to allow remote computers to connect.</span></span>
    1. <span data-ttu-id="a1223-153">přejít na Fiddler Nastavení-> připojení</span><span class="sxs-lookup"><span data-stu-id="a1223-153">Go to Fiddler Settings -> Connections</span></span>
    1. <span data-ttu-id="a1223-154">Všimněte si, že port naslouchání pro Fiddler (výchozí je 8866)</span><span class="sxs-lookup"><span data-stu-id="a1223-154">Note the listening port for Fiddler (default is 8866)</span></span>
    1. <span data-ttu-id="a1223-155">Ověřte, jestli se mají vzdálené počítače připojit.</span><span class="sxs-lookup"><span data-stu-id="a1223-155">Check Allow remote computers to connect</span></span>
    1. <span data-ttu-id="a1223-156">Kliknutí na Uložit</span><span class="sxs-lookup"><span data-stu-id="a1223-156">Click Save</span></span>
3. <span data-ttu-id="a1223-157">v HoloLens 2 – nakonfigurujte Fiddler jako proxy server<sup>1</sup>:</span><span class="sxs-lookup"><span data-stu-id="a1223-157">On your HoloLens 2 – configure Fiddler as the proxy server<sup>1</sup>:</span></span>
    1. <span data-ttu-id="a1223-158">otevřete nabídka Start a vyberte Nastavení</span><span class="sxs-lookup"><span data-stu-id="a1223-158">Open the Start menu and select Settings</span></span>
    1. <span data-ttu-id="a1223-159">V nabídce vlevo vyberte Network & Internet a pak proxy.</span><span class="sxs-lookup"><span data-stu-id="a1223-159">Select Network & Internet and then Proxy on the left menu</span></span>
    1. <span data-ttu-id="a1223-160">Přejděte dolů na ruční nastavení proxy serveru a přepínač použít proxy server na zapnuto.</span><span class="sxs-lookup"><span data-stu-id="a1223-160">Scroll down to Manual proxy setup and toggle Use a proxy server to On</span></span>
    1. <span data-ttu-id="a1223-161">Zadejte IP adresu počítače, kde je nainstalovaný Fiddler.</span><span class="sxs-lookup"><span data-stu-id="a1223-161">Enter the IP address of the PC where Fiddler is installed</span></span>
    1. <span data-ttu-id="a1223-162">Zadejte číslo portu, které jste si poznamenali (výchozí je 8866).</span><span class="sxs-lookup"><span data-stu-id="a1223-162">Enter the port number noted above (default is 8866)</span></span>
    1. <span data-ttu-id="a1223-163">Kliknutí na Uložit</span><span class="sxs-lookup"><span data-stu-id="a1223-163">Click Save</span></span>

<span data-ttu-id="a1223-164"><sup>1</sup> pro sestavení 20279.1006 + (Insiders a nadcházející verze) použijte následující postup ke konfiguraci proxy serveru:</span><span class="sxs-lookup"><span data-stu-id="a1223-164"><sup>1</sup> For builds 20279.1006+ (Insiders and the upcoming release), use the following steps to configure proxy:</span></span>
1. <span data-ttu-id="a1223-165">otevřete nabídka Start a přejít na stránku vlastností vaší Wi-Fi sítě.</span><span class="sxs-lookup"><span data-stu-id="a1223-165">Open the Start menu and go to your Wi-Fi Network’s Properties page</span></span> 
1. <span data-ttu-id="a1223-166">Posunout dolů na proxy</span><span class="sxs-lookup"><span data-stu-id="a1223-166">Scroll down to Proxy</span></span>
1. <span data-ttu-id="a1223-167">Změnit na ruční instalaci</span><span class="sxs-lookup"><span data-stu-id="a1223-167">Change to Manual Setup</span></span>
1. <span data-ttu-id="a1223-168">Zadejte IP adresu počítače, kde je nainstalovaný Fiddler.</span><span class="sxs-lookup"><span data-stu-id="a1223-168">Enter the IP address of the PC where Fiddler is installed</span></span>
1. <span data-ttu-id="a1223-169">Zadejte číslo portu, které jste si poznamenali výše.</span><span class="sxs-lookup"><span data-stu-id="a1223-169">Enter the port number noted above.</span></span> <span data-ttu-id="a1223-170">(výchozí hodnota je 8866)</span><span class="sxs-lookup"><span data-stu-id="a1223-170">(default is 8866)</span></span>
1. <span data-ttu-id="a1223-171">Klikněte na použít.</span><span class="sxs-lookup"><span data-stu-id="a1223-171">Click Apply</span></span>
    
#### <a name="decrypt-https-traffic-from-hololens-2"></a><span data-ttu-id="a1223-172">dešifrování provozu HTTPS z HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="a1223-172">Decrypt HTTPS traffic from HoloLens 2</span></span>

1. <span data-ttu-id="a1223-173">V počítači – exportujte certifikát Fiddler.</span><span class="sxs-lookup"><span data-stu-id="a1223-173">On your PC – export the Fiddler certificate.</span></span>
    1. <span data-ttu-id="a1223-174">přejít na Fiddler Nastavení-> HTTPS a rozšířit upřesnit Nastavení</span><span class="sxs-lookup"><span data-stu-id="a1223-174">Go to Fiddler Settings -> HTTPS and expand Advanced Settings</span></span>
    2. <span data-ttu-id="a1223-175">Klikněte na exportovat certifikát Fiddler.</span><span class="sxs-lookup"><span data-stu-id="a1223-175">Click Export Fiddler certificate.</span></span> <span data-ttu-id="a1223-176">Uloží se na vaši plochu.</span><span class="sxs-lookup"><span data-stu-id="a1223-176">It will save to your desktop</span></span>
    3. <span data-ttu-id="a1223-177">přesuňte certifikát do složky stažené soubory ve vašem HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="a1223-177">Move the certificate over to the Downloads folder on your HoloLens 2</span></span>

2.  <span data-ttu-id="a1223-178">v HoloLens 2 – importujte certifikát Fiddler.</span><span class="sxs-lookup"><span data-stu-id="a1223-178">On your HoloLens 2 - import the Fiddler certificate.</span></span>
    1. <span data-ttu-id="a1223-179">přejít na Nastavení > aktualizace a certifikáty > zabezpečení</span><span class="sxs-lookup"><span data-stu-id="a1223-179">Go to Settings -> Update and Security -> Certificates</span></span>
    2. <span data-ttu-id="a1223-180">Klikněte na nainstalovat certifikát, přejděte do složky Stažené soubory a vyberte certifikát Fiddler.</span><span class="sxs-lookup"><span data-stu-id="a1223-180">Click Install Certificate, browse to the Downloads folder and select the Fiddler certificate</span></span>
    3. <span data-ttu-id="a1223-181">Změnit umístění úložiště na místní počítač</span><span class="sxs-lookup"><span data-stu-id="a1223-181">Change Store Location to Local Machine</span></span>
    4. <span data-ttu-id="a1223-182">Změnit úložiště certifikátů na kořen</span><span class="sxs-lookup"><span data-stu-id="a1223-182">Change Certificate Store to root</span></span>
    5. <span data-ttu-id="a1223-183">Vybrat instalaci</span><span class="sxs-lookup"><span data-stu-id="a1223-183">Select Install</span></span>
    6. <span data-ttu-id="a1223-184">Potvrďte, že se certifikát zobrazuje v seznamu certifikátů.</span><span class="sxs-lookup"><span data-stu-id="a1223-184">Confirm the certificate is showing in the list of certificates.</span></span> <span data-ttu-id="a1223-185">V takovém případě opakujte výše uvedené kroky.</span><span class="sxs-lookup"><span data-stu-id="a1223-185">If not, repeat the above steps</span></span>

#### <a name="inspect-https-sessions"></a><span data-ttu-id="a1223-186">Zkontrolovat relace HTTP (S)</span><span class="sxs-lookup"><span data-stu-id="a1223-186">Inspect HTTP(S) sessions</span></span>

<span data-ttu-id="a1223-187">v počítači se v Fiddler zobrazí relace HTTP (s), které jsou v provozu HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="a1223-187">On your PC, Fiddler will show the HoloLens 2’s live HTTP(S) sessions.</span></span> <span data-ttu-id="a1223-188">Panel inspektorů v Fiddler může v různých zobrazeních zobrazit požadavek nebo odpověď HTTP – například "hrubé" zobrazení zobrazuje nezpracovaný požadavek nebo odpověď v prostém textu.</span><span class="sxs-lookup"><span data-stu-id="a1223-188">The Inspectors panel in Fiddler can show HTTP(S) request/response in different views - for example, the “Raw” view shows the raw request or response in plain text.</span></span> 

### <a name="configure-wireshark-to-capture-network-traffic"></a><span data-ttu-id="a1223-189">Konfigurace Wireshark pro zachycení síťového provozu</span><span class="sxs-lookup"><span data-stu-id="a1223-189">Configure Wireshark to capture network traffic</span></span>
<span data-ttu-id="a1223-190">nástroj Wireshark je analyzátor síťových protokolů a slouží ke kontrole provozu TCP/UDP z a do zařízení HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="a1223-190">Wireshark is a network protocol analyzer and is used to inspect TCP/UDP traffic from and to your HoloLens 2 devices.</span></span> <span data-ttu-id="a1223-191">to usnadňuje identifikaci provozu, který se předává do vaší sítě HoloLens 2, jak často se jedná o četnost latence mezi určitým segmentem směrování a tak dále.</span><span class="sxs-lookup"><span data-stu-id="a1223-191">This makes it easy to identify what traffic is crossing your network to your HoloLens 2, how much of it, how frequently, how much latency there is between certain hops, and so forth.</span></span>

#### <a name="prerequisites"></a><span data-ttu-id="a1223-192">Požadavky:</span><span class="sxs-lookup"><span data-stu-id="a1223-192">Prerequisites:</span></span>
- <span data-ttu-id="a1223-193">POČÍTAČ musí mít přístup k Internetu a podporovat sdílení internetu přes Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="a1223-193">PC must have internet access and support Internet sharing over Wi-Fi</span></span>

#### <a name="install-and-configure-wireshark"></a><span data-ttu-id="a1223-194">Instalace a konfigurace Wireshark</span><span class="sxs-lookup"><span data-stu-id="a1223-194">Install and Configure Wireshark</span></span>
1. <span data-ttu-id="a1223-195">V počítači nainstalujte nástroj [Wireshark](https://www.wireshark.org/#download)</span><span class="sxs-lookup"><span data-stu-id="a1223-195">On your PC - install [Wireshark](https://www.wireshark.org/#download)</span></span> 
1. <span data-ttu-id="a1223-196">Ve vašem počítači – povolte mobilnímu hotspotu sdílení připojení k Internetu z Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="a1223-196">On your PC - enable Mobile hotspot to share your Internet connection from Wi-Fi.</span></span>
1. <span data-ttu-id="a1223-197">Na počítači spusťte Nástroj Wireshark a zachyťte provoz z rozhraní mobilní hotspot.</span><span class="sxs-lookup"><span data-stu-id="a1223-197">On your PC - start Wireshark and capture traffic from the Mobile hotspot interface.</span></span> 
1. <span data-ttu-id="a1223-198">v HoloLens 2 – změňte svou Wi-Fi síť na mobilní hotspot počítače.</span><span class="sxs-lookup"><span data-stu-id="a1223-198">On your HoloLens 2 – change its Wi-Fi network to the PC’s Mobile hotspot.</span></span> <span data-ttu-id="a1223-199">v nástroji Wireshark se zobrazí HoloLens 2 provoz IP.</span><span class="sxs-lookup"><span data-stu-id="a1223-199">HoloLens 2 IP traffic will show up in Wireshark.</span></span>

#### <a name="analyze-wireshark-logs"></a><span data-ttu-id="a1223-200">Analyzovat protokoly Wireshark</span><span class="sxs-lookup"><span data-stu-id="a1223-200">Analyze Wireshark logs</span></span>
<span data-ttu-id="a1223-201">Filtry Wireshark můžou pomoct s filtrováním paketů, které vás zajímají.</span><span class="sxs-lookup"><span data-stu-id="a1223-201">Wireshark filters can help filtering out the packets of interests.</span></span> 

<span data-ttu-id="a1223-202">Podívejte se na původní [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458).</span><span class="sxs-lookup"><span data-stu-id="a1223-202">Check out the original [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458).</span></span>

[<span data-ttu-id="a1223-203">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="a1223-203">Back to list</span></span>](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a><span data-ttu-id="a1223-204">Není možné se přihlásit k dříve vytvořenému HoloLens zařízení</span><span class="sxs-lookup"><span data-stu-id="a1223-204">Can't sign in to a previously setup HoloLens device</span></span>

<span data-ttu-id="a1223-205">Pokud bylo vaše zařízení dříve nastaveno pro někoho jiného, ať už pro klienta nebo pro bývalého zaměstnance, a nemáte [](/intune/remote-actions/devices-wipe) jeho heslo k odemknutí zařízení, můžete k vzdálenému vymazání zařízení použít Intune.</span><span class="sxs-lookup"><span data-stu-id="a1223-205">If your device was previously set up for someone else, either for a client or for a former employee, and you don't have their password to unlock the device, you can use Intune to remotely [wipe](/intune/remote-actions/devices-wipe) the device.</span></span> <span data-ttu-id="a1223-206">Zařízení se pak znovu bliká.</span><span class="sxs-lookup"><span data-stu-id="a1223-206">The device then re-flashes itself.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="a1223-207">Když zařízení vymažete, nezapomeňte nechat nezaškrtnuté políčko Zachovat stav registrace a **uživatelský** účet.</span><span class="sxs-lookup"><span data-stu-id="a1223-207">When you wipe the device, make sure to leave **Retain enrollment state and user account** unchecked.</span></span>

[<span data-ttu-id="a1223-208">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="a1223-208">Back to list</span></span>](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a><span data-ttu-id="a1223-209">Po aktualizaci na Holographic 21H1 se Windows přihlásit</span><span class="sxs-lookup"><span data-stu-id="a1223-209">Can't login after updating to Windows Holographic 21H1</span></span>

### <a name="symptoms"></a><span data-ttu-id="a1223-210">Příznaky</span><span class="sxs-lookup"><span data-stu-id="a1223-210">Symptoms</span></span>
- <span data-ttu-id="a1223-211">Použití kódu PIN k přihlášení selže po zadání správného KÓDU PIN.</span><span class="sxs-lookup"><span data-stu-id="a1223-211">Using PIN to logon will fail after entering the correct PIN.</span></span>
- <span data-ttu-id="a1223-212">Použití metody přihlášení k webu selže po úspěšném přihlášení na webové stránce.</span><span class="sxs-lookup"><span data-stu-id="a1223-212">Using the web logon method will fail after successfully signing in on the web page.</span></span>
- <span data-ttu-id="a1223-213">Zařízení není uvedené v seznamu Připojeno k Azure AD [Azure Portal](https://portal.azure.com/) -> Azure Active Directory -> Devices.</span><span class="sxs-lookup"><span data-stu-id="a1223-213">The device is not listed as “Azure AD joined” in [Azure portal](https://portal.azure.com/) -> Azure Active Directory -> Devices.</span></span>

### <a name="cause"></a><span data-ttu-id="a1223-214">Příčina</span><span class="sxs-lookup"><span data-stu-id="a1223-214">Cause</span></span>
<span data-ttu-id="a1223-215">Ovlivněné zařízení bylo pravděpodobně odstraněno z tenanta Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a1223-215">The impacted device may have been deleted from the Azure AD tenant.</span></span> <span data-ttu-id="a1223-216">K tomu může dojít například z následujícího důvodu:</span><span class="sxs-lookup"><span data-stu-id="a1223-216">For example, this may happen because:</span></span>

- <span data-ttu-id="a1223-217">Správce nebo uživatel odstranil zařízení v Azure Portal nebo pomocí PowerShellu.</span><span class="sxs-lookup"><span data-stu-id="a1223-217">An administrator or user deleted the device in the Azure portal or using PowerShell.</span></span>
- <span data-ttu-id="a1223-218">Zařízení se z tenanta Azure AD odebralo kvůli nečinnosti.</span><span class="sxs-lookup"><span data-stu-id="a1223-218">The device was removed from the Azure AD tenant due to inactivity.</span></span> <span data-ttu-id="a1223-219">V případě efektivně spravovaného prostředí obvykle doporučujeme správcům IT odebrat ze svého tenanta Azure AD zastaralá neaktivní [zařízení.](/azure/active-directory/devices/manage-stale-devices)</span><span class="sxs-lookup"><span data-stu-id="a1223-219">For an efficiently managed environment, we typically recommend IT admins to [remove stale, inactive devices from their Azure AD tenant](/azure/active-directory/devices/manage-stale-devices).</span></span>

<span data-ttu-id="a1223-220">Když se ovlivněné zařízení po odstranění pokusí znovu kontaktovat tenanta Azure AD, ověření ve službě Azure AD se nezdaří.</span><span class="sxs-lookup"><span data-stu-id="a1223-220">When an impacted device attempts to contact the Azure AD tenant again after it has been deleted it will fail to authenticate with Azure AD.</span></span> <span data-ttu-id="a1223-221">Tento účinek je často pro uživatele zařízení neviditelný, protože přihlášení uložené v mezipaměti prostřednictvím kódu PIN bude i nadále umožnovat přihlášení uživatele.</span><span class="sxs-lookup"><span data-stu-id="a1223-221">This effect is often invisible to the user of the device, as cached logon via PIN will continue to allow the user to logon.</span></span>

### <a name="mitigation"></a><span data-ttu-id="a1223-222">Omezení rizik</span><span class="sxs-lookup"><span data-stu-id="a1223-222">Mitigation</span></span>
<span data-ttu-id="a1223-223">V současné době neexistuje způsob, jak přidat odstraněný HoloLens zařízení zpět do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a1223-223">There is currently no way to add a deleted HoloLens device back into Azure AD.</span></span> <span data-ttu-id="a1223-224">Ovlivněná zařízení se musí vyčistit a vyčistit podle pokynů k [kolikoli](hololens-recovery.md#clean-reflash-the-device)z těchto zařízení.</span><span class="sxs-lookup"><span data-stu-id="a1223-224">Affected devices will need to be clean-reflashed by following the instructions on [reflashing their device](hololens-recovery.md#clean-reflash-the-device).</span></span>

[<span data-ttu-id="a1223-225">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="a1223-225">Back to list</span></span>](#list)

## <a name="autopilot-troubleshooting"></a><span data-ttu-id="a1223-226">Řešení potíží s Autopilotem</span><span class="sxs-lookup"><span data-stu-id="a1223-226">Autopilot Troubleshooting</span></span>

<span data-ttu-id="a1223-227">Následující články mohou být užitečným zdrojem dalších informací a řešení potíží s Autopilotem. Mějte ale na paměti, že tyto články jsou založené na Windows 10 Desktopu a ne všechny informace se mohou vztahovat na HoloLens:</span><span class="sxs-lookup"><span data-stu-id="a1223-227">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>

- [<span data-ttu-id="a1223-228">Windows Autopilot – známé problémy</span><span class="sxs-lookup"><span data-stu-id="a1223-228">Windows Autopilot - known issues</span></span>](/mem/autopilot/known-issues)
- [<span data-ttu-id="a1223-229">Řešení Windows problémů s registrací zařízení Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a1223-229">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="a1223-230">Windows Autopilot – Konflikty zásad</span><span class="sxs-lookup"><span data-stu-id="a1223-230">Windows Autopilot - Policy Conflicts</span></span>](/mem/autopilot/policy-conflicts)

[<span data-ttu-id="a1223-231">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="a1223-231">Back to list</span></span>](#list)

## <a name="managed-hololens-devices-faqs"></a><span data-ttu-id="a1223-232">Nejčastější dotazy HoloLens spravovaných zařízeních</span><span class="sxs-lookup"><span data-stu-id="a1223-232">Managed HoloLens Devices FAQs</span></span>

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a><span data-ttu-id="a1223-233">Můžu ke správě System Center Configuration Manager (SCCM) použít HoloLens zařízení?</span><span class="sxs-lookup"><span data-stu-id="a1223-233">Can I use System Center Configuration Manager (SCCM) to manage HoloLens devices?</span></span>

<span data-ttu-id="a1223-234">No.</span><span class="sxs-lookup"><span data-stu-id="a1223-234">No.</span></span> <span data-ttu-id="a1223-235">Systém MDM musíte použít ke správě HoloLens zařízení.</span><span class="sxs-lookup"><span data-stu-id="a1223-235">You have to use an MDM system to manage HoloLens devices.</span></span>

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a><span data-ttu-id="a1223-236">Můžu ke správě Active Directory Domain Services účtů použít HoloLens (AD DS)?</span><span class="sxs-lookup"><span data-stu-id="a1223-236">Can I use Active Directory Domain Services (AD DS) to manage HoloLens user accounts?</span></span>

<span data-ttu-id="a1223-237">No.</span><span class="sxs-lookup"><span data-stu-id="a1223-237">No.</span></span> <span data-ttu-id="a1223-238">Ke správě uživatelských účtů Azure Active Directory zařízení musíte použít Azure AD (HoloLens zařízení.</span><span class="sxs-lookup"><span data-stu-id="a1223-238">You have to use Azure Active Directory (Azure AD) to manage user accounts for HoloLens devices.</span></span>

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a><span data-ttu-id="a1223-239">Je HoloLens automatizovaná registrace systémů pro zachytávání dat (ADCS)?</span><span class="sxs-lookup"><span data-stu-id="a1223-239">Is HoloLens capable of Automated Data Capture Systems (ADCS) auto-enrollment?</span></span>

<span data-ttu-id="a1223-240">No.</span><span class="sxs-lookup"><span data-stu-id="a1223-240">No.</span></span>

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a><span data-ttu-id="a1223-241">Účastnit HoloLens integrovaného ověřování Windows systému?</span><span class="sxs-lookup"><span data-stu-id="a1223-241">Can HoloLens participate in Integrated Windows Authentication?</span></span>

<span data-ttu-id="a1223-242">No.</span><span class="sxs-lookup"><span data-stu-id="a1223-242">No.</span></span>

### <a name="does-hololens-support-branding"></a><span data-ttu-id="a1223-243">Podporuje HoloLens branding?</span><span class="sxs-lookup"><span data-stu-id="a1223-243">Does HoloLens support branding?</span></span>

<span data-ttu-id="a1223-244">No.</span><span class="sxs-lookup"><span data-stu-id="a1223-244">No.</span></span> <span data-ttu-id="a1223-245">Tento problém však můžete obvyřešit pomocí jednoho z následujících přístupů:</span><span class="sxs-lookup"><span data-stu-id="a1223-245">However, you can work around this issue by using one of the following approaches:</span></span>

- <span data-ttu-id="a1223-246">Vytvořte vlastní aplikaci a pak [povolte bezobrazovový režim](hololens-kiosk.md).</span><span class="sxs-lookup"><span data-stu-id="a1223-246">Create a custom app, and then [enable Kiosk mode](hololens-kiosk.md).</span></span> <span data-ttu-id="a1223-247">Vlastní aplikace může mít branding a může spouštět další aplikace (například Remote Assist).</span><span class="sxs-lookup"><span data-stu-id="a1223-247">The custom app can have branding, and can launch other apps (such as Remote Assist).</span></span>  
- <span data-ttu-id="a1223-248">Změňte všechny profilové obrázky uživatelů v Azure AD na logo vaší společnosti.</span><span class="sxs-lookup"><span data-stu-id="a1223-248">Change all of the user profile pictures in Azure AD to your company logo.</span></span> <span data-ttu-id="a1223-249">To však nemusí být žádoucí pro všechny scénáře.</span><span class="sxs-lookup"><span data-stu-id="a1223-249">However, this may not be desirable for all scenarios.</span></span>

### <a name="what-logging-capabilities-does-hololens-2-offer"></a><span data-ttu-id="a1223-250">Jaké možnosti protokolování nabízí HoloLens 2?</span><span class="sxs-lookup"><span data-stu-id="a1223-250">What logging capabilities does HoloLens 2 offer?</span></span>

<span data-ttu-id="a1223-251">Protokolování je omezené na trasování, která je možné zachytit ve scénářích vývoje nebo řešení potíží, nebo telemetrii, kterou zařízení odesílala na servery Microsoftu.</span><span class="sxs-lookup"><span data-stu-id="a1223-251">Logging is limited to traces that can be captured in development or troubleshooting scenarios, or telemetry that the devices send to Microsoft servers.</span></span>

## <a name="questions-about-securing-hololens-devices"></a><span data-ttu-id="a1223-252">Dotazy týkající se zabezpečení HoloLens zařízení</span><span class="sxs-lookup"><span data-stu-id="a1223-252">Questions about securing HoloLens devices</span></span>

<span data-ttu-id="a1223-253">Podívejte [se na HoloLens 2.](security-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a1223-253">See [our HoloLens 2 security information](security-overview.md).</span></span>
<span data-ttu-id="a1223-254">Další HoloLens 1. generace najdete v [nejčastějších dotazech.](hololens1-faq-security.yml)</span><span class="sxs-lookup"><span data-stu-id="a1223-254">For HoloLens 1st Gen devices please review [this FAQ](hololens1-faq-security.yml).</span></span>

[<span data-ttu-id="a1223-255">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="a1223-255">Back to list</span></span>](#list)
