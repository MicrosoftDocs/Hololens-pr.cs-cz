---
title: Připojení HoloLens k síti
description: Zjistěte, jak nastavit a připojit se k internetu HoloLens a jak identifikovat IP adresu zařízení.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, wifi, wireless, internet, ip, IP adresa
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: c2a2fe1a20a4e9baa194b1037ccb6649d324b990
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640215"
---
# <a name="connect-hololens-to-a-network"></a><span data-ttu-id="708a2-104">Připojení HoloLens k síti</span><span class="sxs-lookup"><span data-stu-id="708a2-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="708a2-105">Pokud chcete na svém počítači HoloLens, musíte být připojení k síti.</span><span class="sxs-lookup"><span data-stu-id="708a2-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="708a2-106">HoloLens obsahuje přepínač s podporou 802.11ac, 2x2 Wi-Fi a jeho připojení k síti je podobné jako připojení zařízení Windows 10 Desktop nebo Mobile k Wi-Fi síti.</span><span class="sxs-lookup"><span data-stu-id="708a2-106">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio and connecting it to a network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span> <span data-ttu-id="708a2-107">Tato příručka vám pomůže:</span><span class="sxs-lookup"><span data-stu-id="708a2-107">This guide will help you:</span></span>

- <span data-ttu-id="708a2-108">Připojení k síti pomocí Wi-Fi nebo pouze HoloLens 2, Wi-Fi Direct nebo Ethernet přes USB-C</span><span class="sxs-lookup"><span data-stu-id="708a2-108">Connect to a network using Wi-Fi, or for HoloLens 2 only, Wi-Fi Direct or Ethernet over USB-C</span></span>
- <span data-ttu-id="708a2-109">Zakázání a opětovné povolení Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="708a2-109">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="708a2-110">Přečtěte si další [informace o HoloLens offline.](hololens-offline.md)</span><span class="sxs-lookup"><span data-stu-id="708a2-110">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <a name="connecting-for-the-first-time"></a><span data-ttu-id="708a2-111">První připojení</span><span class="sxs-lookup"><span data-stu-id="708a2-111">Connecting for the first time</span></span>

<span data-ttu-id="708a2-112">Při prvním použití HoloLens vás provedeme připojením k Wi-Fi síti.</span><span class="sxs-lookup"><span data-stu-id="708a2-112">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="708a2-113">Pokud máte potíže s připojením Wi-Fi během instalace, ujistěte se, že je vaše síť buď otevřená síť chráněná heslem, nebo místní síť portálu.</span><span class="sxs-lookup"><span data-stu-id="708a2-113">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="708a2-114">Ověřte také, že síť nevyžaduje připojení pomocí certifikátu.</span><span class="sxs-lookup"><span data-stu-id="708a2-114">Also, confirm that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="708a2-115">Po instalaci se můžete připojit k jiným typům Wi-Fi sítí.</span><span class="sxs-lookup"><span data-stu-id="708a2-115">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="708a2-116">Na HoloLens 2 může uživatel použít také adaptér [USB-C na Ethernet](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) pro připojení přímo k Wi-Fi, který vám pomůže s nastavením zařízení.</span><span class="sxs-lookup"><span data-stu-id="708a2-116">On HoloLens 2 devices, a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="708a2-117">Po nastavení zařízení může uživatel adaptér dál používat nebo ho může odpojit od adaptéru a připojit se k [wi-fi po nastavení](hololens-network.md#connecting-to-wi-fi-after-setup).</span><span class="sxs-lookup"><span data-stu-id="708a2-117">Once the device has been set up a user may continue to use the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <a name="connecting-to-wi-fi-after-setup"></a><span data-ttu-id="708a2-118">Připojení k Wi-Fi po nastavení</span><span class="sxs-lookup"><span data-stu-id="708a2-118">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="708a2-119">Předem vytyčte **gesto Spustit** **a vyberte Nastavení**.</span><span class="sxs-lookup"><span data-stu-id="708a2-119">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="708a2-120">Aplikace Nastavení se automaticky umístí před vás.</span><span class="sxs-lookup"><span data-stu-id="708a2-120">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="708a2-121">Vyberte **Network & Internet**  >  **Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="708a2-121">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="708a2-122">Zkontrolujte, jestli je zapnuté Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="708a2-122">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="708a2-123">Pokud síť nevidíte, posuňte se v seznamu dolů.</span><span class="sxs-lookup"><span data-stu-id="708a2-123">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="708a2-124">Vyberte síť a pak vyberte **Připojení**.</span><span class="sxs-lookup"><span data-stu-id="708a2-124">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="708a2-125">Pokud se zobrazí výzva k zadání hesla k síti, zadejte ho a pak vyberte **Další.**</span><span class="sxs-lookup"><span data-stu-id="708a2-125">If you are prompted for a network password type it and then select **Next**.</span></span>

![HoloLens Wi-Fi nastavení](./images/hololens-2-wifi-settings.jpg)

<span data-ttu-id="708a2-127">Pokud chcete ověřit, že jste připojení Wi-Fi síti, zkontrolujte stav Wi-Fi v **nabídce Start:**</span><span class="sxs-lookup"><span data-stu-id="708a2-127">To confirm you are connected to a Wi-Fi network, check the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="708a2-128">Otevřete **nabídku** Start.</span><span class="sxs-lookup"><span data-stu-id="708a2-128">Open the **Start** menu.</span></span>
1. <span data-ttu-id="708a2-129">V levém horním rohu nabídky **Start vyhledejte** Wi-Fi stavu.</span><span class="sxs-lookup"><span data-stu-id="708a2-129">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="708a2-130">Zobrazí se stav Wi-Fi a SSID připojené sítě.</span><span class="sxs-lookup"><span data-stu-id="708a2-130">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

> [!TIP]
> <span data-ttu-id="708a2-131">Pokud Wi-Fi dostupná, můžete se také připojit k mobilním sítím a [sítím 5G.](hololens-cellular.md)</span><span class="sxs-lookup"><span data-stu-id="708a2-131">If Wi-Fi is not available, you can also [connect to Cellular and 5G networks](hololens-cellular.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="708a2-132">Uživatelé nemohou chování roamingu Wi-Fi HoloLens 2 vyladit – jediným způsobem, jak aktualizovat seznam Wi-Fi, je přepnout Wi-Fi vypnout a **zapnout.**</span><span class="sxs-lookup"><span data-stu-id="708a2-132">By design, users cannot fine tune the Wi-Fi roaming behavior of the HoloLens 2 - **the only way to refresh the Wi-Fi list is to toggle the Wi-Fi Off and On**.</span></span> <span data-ttu-id="708a2-133">Zabrání se tak mnoha problémům, jako je například to, že zařízení může zůstat "zablokované" na přístupové bodu, když je mimo rozsah.</span><span class="sxs-lookup"><span data-stu-id="708a2-133">This prevents many issues, like where a device can remain "stuck" to an AP once it is out of range.</span></span>

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a><span data-ttu-id="708a2-134">Připojení HoloLens k Enterprise Wi-Fi network</span><span class="sxs-lookup"><span data-stu-id="708a2-134">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="708a2-135">Enterprise Wi-Fi profily používají k ověřování připojení protokol EAP (Extensible Authentication ProtocolWi-Fi připojení.</span><span class="sxs-lookup"><span data-stu-id="708a2-135">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="708a2-136">HoloLens Enterprise Wi-Fi profil je možné nakonfigurovat prostřednictvím MDM nebo zřizovacího balíčku vytvořeného [Windows Configuration Designeru.](/windows/configuration/provisioning-packages/provisioning-packages)</span><span class="sxs-lookup"><span data-stu-id="708a2-136">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="708a2-137">Pokyny Microsoft Intune spravovaném zařízení [najdete v Intune.](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)</span><span class="sxs-lookup"><span data-stu-id="708a2-137">For Microsoft Intune managed device, refer to [Intune](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="708a2-138">Pokud chcete ve Wi-Fi WCD vytvořit zřizovací balíček, je Wi-Fi nakonfigurovaný soubor .xml profilu.</span><span class="sxs-lookup"><span data-stu-id="708a2-138">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="708a2-139">Tady je ukázkový profil Wi-Fi pro WPA2-Enterprise s ověřováním EAP-TLS:</span><span class="sxs-lookup"><span data-stu-id="708a2-139">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

``` xml
<?xml version="1.0"?> 
<WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1"> 
    <name>SampleEapTlsProfile</name> 
    <SSIDConfig> 
        <SSID> 
            <hex>53616d706c65</hex> 
            <name>Sample</name> 
        </SSID> 
        <nonBroadcast>true</nonBroadcast> 
    </SSIDConfig> 
    <connectionType>ESS</connectionType> 
    <connectionMode>auto</connectionMode> 
    <autoSwitch>false</autoSwitch> 
    <MSM> 
        <security> 
            <authEncryption> 
                <authentication>WPA2</authentication> 
                <encryption>AES</encryption> 
                <useOneX>true</useOneX> 
                <FIPSMode xmlns="http://www.microsoft.com/networking/WLAN/profile/v2">false</FIPSMode> 
            </authEncryption> 
            <PMKCacheMode>disabled</PMKCacheMode> 
            <OneX xmlns="http://www.microsoft.com/networking/OneX/v1"> 
                <authMode>machine</authMode> 
                <EAPConfig> 
                    <EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                        <EapMethod> 
                            <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type> 
                            <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId> 
                            <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType> 
                            <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId> 
                        </EapMethod> 
                        <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                            <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"> 
                                <Type>13</Type> 
                                <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"> 
                                    <CredentialsSource><CertificateStore><SimpleCertSelection>true</SimpleCertSelection> 
                                        </CertificateStore> 
                                    </CredentialsSource> 
                                    <ServerValidation> 
                                        <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation> 
                                        <ServerNames></ServerNames> 
                                        <TrustedRootCA>00 01 02 03 04 05 06 07 08 09 0a 0b 0c 0d 0e 0f 10 11 12 13</TrustedRootCA> 
                                    </ServerValidation> 
                                    <DifferentUsername>false</DifferentUsername> 
                                    <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">true</PerformServerValidation> 
                                    <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName> 
                                </EapType> 
                            </Eap> 
                        </Config> 
                    </EapHostConfig> 
                </EAPConfig> 
            </OneX> 
        </security> 
    </MSM> 
</WLANProfile> 
```


<span data-ttu-id="708a2-140">Certifikát kořenové certifikační autority serveru a klientský certifikát může být potřeba zřídit v zařízení v závislosti na typu protokolu EAP.</span><span class="sxs-lookup"><span data-stu-id="708a2-140">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="708a2-141">Další prostředky:</span><span class="sxs-lookup"><span data-stu-id="708a2-141">Additional resources:</span></span>

- <span data-ttu-id="708a2-142">Schéma WLANv1Profile: [[MS-GPWL]: Profil bezdrátové sítě LAN v1 | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="708a2-142">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="708a2-143">Schéma EAP-TLS: [[MS-GPWL]: Schéma protokolu | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="708a2-143">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

<span data-ttu-id="708a2-144">Pokud máte [problémy](hololens2-enterprise-troubleshooting.md#) s připojením k Wi-Fi, podívejte se na naši stránku řešení potíží.</span><span class="sxs-lookup"><span data-stu-id="708a2-144">Check our [Troubleshooting](hololens2-enterprise-troubleshooting.md#) page if you are having problems connecting to your Wi-Fi.</span></span>

## <a name="configure-network-proxy"></a><span data-ttu-id="708a2-145">Konfigurace síťového proxy serveru</span><span class="sxs-lookup"><span data-stu-id="708a2-145">Configure Network Proxy</span></span>

<span data-ttu-id="708a2-146">Tato část se věnuje proxy serveru sítě pro HoloLens operačního systému a aplikace pro Univerzální Windows platformy (UPW) využívající Windows zásobníku HTTP.</span><span class="sxs-lookup"><span data-stu-id="708a2-146">This section covers network proxy for HoloLens OS and Universal Windows Platform (UWP) Apps using Windows HTTP stack.</span></span> <span data-ttu-id="708a2-147">Aplikace, které používají Windows zásobníku HTTP, mohou mít vlastní konfiguraci a zpracování proxy serveru.</span><span class="sxs-lookup"><span data-stu-id="708a2-147">Applications using non-Windows HTTP stack may have their own proxy configuration and handling.</span></span> 

### <a name="proxy-configurations"></a><span data-ttu-id="708a2-148">Konfigurace proxy serveru</span><span class="sxs-lookup"><span data-stu-id="708a2-148">Proxy Configurations</span></span> 

- <span data-ttu-id="708a2-149">Skript PAC (Proxy Auto-Config): Soubor [PAC](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (otevře web jiné společnosti než Microsoft) obsahuje funkci Jazyka JavaScript FindProxyForURL(adresa URL, hostitel).</span><span class="sxs-lookup"><span data-stu-id="708a2-149">Proxy Auto-Config (PAC) script: a [PAC file](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (opens a non-Microsoft site) contains a JavaScript function FindProxyForURL(url, host).</span></span> 
- <span data-ttu-id="708a2-150">Statický proxy server: ve tvaru Server:Port.</span><span class="sxs-lookup"><span data-stu-id="708a2-150">Static Proxy: in the form of Server:Port.</span></span>  
- <span data-ttu-id="708a2-151">Protokol WPAD (Web Proxy Auto-Discovery Protocol): Zadejte adresu URL konfiguračního souboru proxy serveru prostřednictvím DHCP nebo DNS.</span><span class="sxs-lookup"><span data-stu-id="708a2-151">Web Proxy Auto-Discovery Protocol (WPAD): provide URL of proxy configuration file through DHCP or DNS.</span></span> 

### <a name="proxy-provisioning-methods"></a><span data-ttu-id="708a2-152">Metody zřizování proxy serveru</span><span class="sxs-lookup"><span data-stu-id="708a2-152">Proxy Provisioning Methods</span></span> 
<span data-ttu-id="708a2-153">Existují tři způsoby, jak zřídit proxy:</span><span class="sxs-lookup"><span data-stu-id="708a2-153">There are three ways to provision proxies:</span></span>

 

1.  <span data-ttu-id="708a2-154">**Nastavení Ui:**</span><span class="sxs-lookup"><span data-stu-id="708a2-154">**Settings UI:**</span></span> 
    1. <span data-ttu-id="708a2-155">Proxy pro uživatele (20H2 nebo starší):</span><span class="sxs-lookup"><span data-stu-id="708a2-155">Per-user proxy (20H2 or earlier):</span></span>
        1. <span data-ttu-id="708a2-156">Otevřete nabídka Start a vyberte Nastavení.</span><span class="sxs-lookup"><span data-stu-id="708a2-156">Open the Start menu and select Settings.</span></span>
        2. <span data-ttu-id="708a2-157">Vyberte Network & Internet a pak v nabídce vlevo vyberte Proxy.</span><span class="sxs-lookup"><span data-stu-id="708a2-157">Select Network & Internet and then Proxy on the left menu.</span></span>
        3. <span data-ttu-id="708a2-158">Posuňte se dolů na Manual proxy setup (Ruční nastavení proxy serveru) a přepněte Use a proxy server (Použít proxy server) na On (Zapnout).</span><span class="sxs-lookup"><span data-stu-id="708a2-158">Scroll down to Manual proxy setup and toggle Use a proxy server to On.</span></span>
        4. <span data-ttu-id="708a2-159">Zadejte IP adresu proxy server.</span><span class="sxs-lookup"><span data-stu-id="708a2-159">Enter the IP address of the proxy server.</span></span>
        5. <span data-ttu-id="708a2-160">Zadejte číslo portu.</span><span class="sxs-lookup"><span data-stu-id="708a2-160">Enter the port number.</span></span>
        6. <span data-ttu-id="708a2-161">Klikněte na Uložit.</span><span class="sxs-lookup"><span data-stu-id="708a2-161">Click Save.</span></span>
      1. <span data-ttu-id="708a2-162">Proxy připojení WiFi (21H1 nebo vyšší):</span><span class="sxs-lookup"><span data-stu-id="708a2-162">WiFi proxy (21H1 or higher):</span></span>
          1. <span data-ttu-id="708a2-163">Otevřete nabídka Start a přejděte na stránku Wi-Fi vlastnosti vaší sítě.</span><span class="sxs-lookup"><span data-stu-id="708a2-163">Open the Start menu and go to your Wi-Fi Network’s Properties page.</span></span>
          1. <span data-ttu-id="708a2-164">Posuňte se dolů na Proxy.</span><span class="sxs-lookup"><span data-stu-id="708a2-164">Scroll down to Proxy</span></span>
          1. <span data-ttu-id="708a2-165">Změna na ruční nastavení</span><span class="sxs-lookup"><span data-stu-id="708a2-165">Change to Manual Setup</span></span>
          1. <span data-ttu-id="708a2-166">Zadejte IP adresu proxy server.</span><span class="sxs-lookup"><span data-stu-id="708a2-166">Enter the IP address of the proxy server.</span></span>
          1. <span data-ttu-id="708a2-167">Zadejte číslo portu.</span><span class="sxs-lookup"><span data-stu-id="708a2-167">Enter the port number.</span></span>
          1. <span data-ttu-id="708a2-168">Klikněte na Použít.</span><span class="sxs-lookup"><span data-stu-id="708a2-168">Click Apply.</span></span>
        
 2. <span data-ttu-id="708a2-169">**MDM**</span><span class="sxs-lookup"><span data-stu-id="708a2-169">**MDM**</span></span> 
     1. <span data-ttu-id="708a2-170">Intune – Pomocí těchto [kroků můžete](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) nakonfigurovat proxy server v Intune.</span><span class="sxs-lookup"><span data-stu-id="708a2-170">Intune - Use these [steps](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) to configure proxy in Intune.</span></span> <span data-ttu-id="708a2-171">Budete se muset posunout do dolní části oddílu.</span><span class="sxs-lookup"><span data-stu-id="708a2-171">You will need to scroll to the bottom of the section.</span></span>
     1. <span data-ttu-id="708a2-172">Jiná řešení MDM třetích stran – Použijte [WiFi CSP.](/windows/client-management/mdm/wifi-csp)</span><span class="sxs-lookup"><span data-stu-id="708a2-172">Other 3rd party MDM solutions - Use a [WiFi CSP](/windows/client-management/mdm/wifi-csp).</span></span>

3. <span data-ttu-id="708a2-173">**PPKG**</span><span class="sxs-lookup"><span data-stu-id="708a2-173">**PPKG**</span></span> 
    1. <span data-ttu-id="708a2-174">Otevřete Windows Configuration Designer.</span><span class="sxs-lookup"><span data-stu-id="708a2-174">Open Windows Configuration Designer</span></span>
    1. <span data-ttu-id="708a2-175">Klikněte na Rozšířené zřizování, zadejte název nového virtuálního počítače Project klikněte na Další.</span><span class="sxs-lookup"><span data-stu-id="708a2-175">Click on Advanced Provisioning, enter the name for your new Project and click Next.</span></span>
    1. <span data-ttu-id="708a2-176">Vyberte Windows Holographic (HoloLens 2) a klikněte na Další.</span><span class="sxs-lookup"><span data-stu-id="708a2-176">Select Windows Holographic (HoloLens 2) and click Next.</span></span>
    1. <span data-ttu-id="708a2-177">Importujte PPKG (volitelné) a klikněte na Dokončit.</span><span class="sxs-lookup"><span data-stu-id="708a2-177">Import your PPKG (optional) and click Finish.</span></span>
    1. <span data-ttu-id="708a2-178">Rozbalte položku Nastavení -> Profily připojení -> WLAN -> Proxy WLAN.</span><span class="sxs-lookup"><span data-stu-id="708a2-178">Expand Runtime Settings -> Connectivity Profiles -> WLAN -> WLAN Proxy.</span></span>
    1. <span data-ttu-id="708a2-179">Zadejte SSID vaší Wi-Fi sítě a klikněte na Přidat.</span><span class="sxs-lookup"><span data-stu-id="708a2-179">Enter the SSID of your Wi-Fi network and click Add.</span></span>
    1. <span data-ttu-id="708a2-180">V levém Wi-Fi vyberte svou síť a zadejte požadovaná vlastní nastavení.</span><span class="sxs-lookup"><span data-stu-id="708a2-180">Select your Wi-Fi network in the left window and enter your desired customizations.</span></span> <span data-ttu-id="708a2-181">Povolená vlastní nastavení se v nabídce vlevo zobrazí tučně.</span><span class="sxs-lookup"><span data-stu-id="708a2-181">The enabled customizations will show in bold on the left menu.</span></span>
    1. <span data-ttu-id="708a2-182">Klikněte na Uložit a ukončit.</span><span class="sxs-lookup"><span data-stu-id="708a2-182">Click Save and Exit.</span></span>
    1. <span data-ttu-id="708a2-183">[Použijte](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) zřizovací balíček pro HoloLens.</span><span class="sxs-lookup"><span data-stu-id="708a2-183">[Apply](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) the provisioning package to the HoloLens.</span></span>

<span data-ttu-id="708a2-184">[Poskytovatelé cloudových](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) služeb jsou za mnoha úkoly a zásadami správy pro Windows 10, a to jak v Microsoft Intune, tak u jiných poskytovatelů služeb MDM než Microsoftu.</span><span class="sxs-lookup"><span data-stu-id="708a2-184">[CSPs](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) are behind many of the management tasks and policies for Windows 10, both in Microsoft Intune and in non-Microsoft MDM service providers.</span></span> <span data-ttu-id="708a2-185">Můžete také použít [Windows Configuration Designer](/windows/configuration/provisioning-packages/provisioning-install-icd) a vytvořit [zřizovací](/windows/configuration/provisioning-packages/provisioning-packages) balíček a použít ho na HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="708a2-185">You can also use [Windows Configuration Designer](/windows/configuration/provisioning-packages/provisioning-install-icd) to create a [provisioning package](/windows/configuration/provisioning-packages/provisioning-packages) and apply it to the HoloLens 2.</span></span>
<span data-ttu-id="708a2-186">Nejpravděpodobnějšími csP, které se použijí na HoloLens 2:</span><span class="sxs-lookup"><span data-stu-id="708a2-186">The most likely CSPs that will be applied to your HoloLens 2 are:</span></span>

- <span data-ttu-id="708a2-187">[WiFi CSP:](/windows/client-management/mdm/wifi-csp)proxy server pro Wi-Fi profilu</span><span class="sxs-lookup"><span data-stu-id="708a2-187">[WiFi CSP](/windows/client-management/mdm/wifi-csp): per-profile Wi-Fi proxy</span></span> 

[<span data-ttu-id="708a2-188">Ostatní csP podporovaní v HoloLens zařízeních</span><span class="sxs-lookup"><span data-stu-id="708a2-188">Other CSPs supported in HoloLens devices</span></span>](/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a><span data-ttu-id="708a2-189">Síť VPN</span><span class="sxs-lookup"><span data-stu-id="708a2-189">VPN</span></span>
<span data-ttu-id="708a2-190">Připojení VPN může pomoct zajistit bezpečnější připojení a přístup k firemní síti a internetu.</span><span class="sxs-lookup"><span data-stu-id="708a2-190">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="708a2-191">HoloLens 2 podporuje integrovaného klienta VPN a modul plug-in VPN universal Windows platformy (UPW).</span><span class="sxs-lookup"><span data-stu-id="708a2-191">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="708a2-192">Podporované integrované protokoly VPN:</span><span class="sxs-lookup"><span data-stu-id="708a2-192">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="708a2-193">IKEv2</span><span class="sxs-lookup"><span data-stu-id="708a2-193">IKEv2</span></span>
- <span data-ttu-id="708a2-194">L2TP</span><span class="sxs-lookup"><span data-stu-id="708a2-194">L2TP</span></span>
- <span data-ttu-id="708a2-195">PPTP</span><span class="sxs-lookup"><span data-stu-id="708a2-195">PPTP</span></span>

<span data-ttu-id="708a2-196">Pokud se certifikát používá k ověřování pro integrovaného klienta VPN, je potřeba požadovaný klientský certifikát přidat do úložiště uživatelských certifikátů.</span><span class="sxs-lookup"><span data-stu-id="708a2-196">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="708a2-197">Pokud chcete zjistit, jestli modul plug-in VPN třetí strany podporuje HoloLens 2, přejděte do Storu, vyhledejte aplikaci VPN a zkontrolujte, jestli je HoloLens uvedený jako podporované zařízení, a na stránce Požadavky na systém aplikace podporuje architekturu ARM nebo ARM64.</span><span class="sxs-lookup"><span data-stu-id="708a2-197">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="708a2-198">HoloLens podporuje pouze aplikace univerzální Windows platformy pro síť VPN třetí strany.</span><span class="sxs-lookup"><span data-stu-id="708a2-198">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="708a2-199">Síť VPN je možné spravovat pomocí MDM [Nastavení/AllowVPN](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)a nastavit ji prostřednictvím zásad [Vpnv2-csp.](/windows/client-management/mdm/vpnv2-csp)</span><span class="sxs-lookup"><span data-stu-id="708a2-199">VPN can be managed by MDM via [Settings/AllowVPN](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="708a2-200">Další informace o [konfiguraci sítě VPN najdete v](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) těchto [příručkách.](/windows/security/identity-protection/vpn/vpn-guide)</span><span class="sxs-lookup"><span data-stu-id="708a2-200">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <a name="vpn-via-ui"></a><span data-ttu-id="708a2-201">VPN přes uživatelské rozhraní</span><span class="sxs-lookup"><span data-stu-id="708a2-201">VPN via UI</span></span>

<span data-ttu-id="708a2-202">Síť VPN není ve výchozím nastavení povolená, ale můžete ji povolit ručně tak, že Nastavení aplikaci a přejdete na **Síť & Internet -> VPN.** </span><span class="sxs-lookup"><span data-stu-id="708a2-202">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="708a2-203">Vyberte poskytovatele sítě VPN.</span><span class="sxs-lookup"><span data-stu-id="708a2-203">Select a VPN provider.</span></span>
1. <span data-ttu-id="708a2-204">Vytvořte název připojení.</span><span class="sxs-lookup"><span data-stu-id="708a2-204">Create a connection name.</span></span> 
1. <span data-ttu-id="708a2-205">Zadejte název nebo adresu serveru.</span><span class="sxs-lookup"><span data-stu-id="708a2-205">Enter your server name or address.</span></span>
1. <span data-ttu-id="708a2-206">Vyberte typ sítě VPN.</span><span class="sxs-lookup"><span data-stu-id="708a2-206">Select the VPN type.</span></span>
1. <span data-ttu-id="708a2-207">Vyberte typ přihlašovacích údajů.</span><span class="sxs-lookup"><span data-stu-id="708a2-207">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="708a2-208">Volitelně přidejte uživatelské jméno a heslo.</span><span class="sxs-lookup"><span data-stu-id="708a2-208">Optionally add user name and password.</span></span>
1. <span data-ttu-id="708a2-209">Použijte nastavení sítě VPN.</span><span class="sxs-lookup"><span data-stu-id="708a2-209">Apply the VPN settings.</span></span> 

![HoloLens Nastavení sítě VPN](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a><span data-ttu-id="708a2-211">Síť VPN nastavená prostřednictvím zřizovacího balíčku</span><span class="sxs-lookup"><span data-stu-id="708a2-211">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="708a2-212">V našem Windows Holographic verze 20H2 jsme opravili problém s konfigurací proxy serveru pro připojení VPN.</span><span class="sxs-lookup"><span data-stu-id="708a2-212">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="708a2-213">Pokud chcete tento tok použít, zvažte upgrade zařízení na toto sestavení.</span><span class="sxs-lookup"><span data-stu-id="708a2-213">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="708a2-214">Spusťte Windows Configuration Designer.</span><span class="sxs-lookup"><span data-stu-id="708a2-214">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="708a2-215">Klikněte **na HoloLens zařízení a** pak vyberte cílové zařízení a **Další.**</span><span class="sxs-lookup"><span data-stu-id="708a2-215">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="708a2-216">Zadejte název a cestu balíčku.</span><span class="sxs-lookup"><span data-stu-id="708a2-216">Enter package name and path.</span></span>
1. <span data-ttu-id="708a2-217">Klikněte **na Přepnout do rozšířeného editoru.**</span><span class="sxs-lookup"><span data-stu-id="708a2-217">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="708a2-218">Otevřete **Nastavení modulu runtime**  ->  **PřipojeníProfily** VPN  ->    ->  **VPNNastavení**.</span><span class="sxs-lookup"><span data-stu-id="708a2-218">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="708a2-219">Konfigurace VPNProfileName</span><span class="sxs-lookup"><span data-stu-id="708a2-219">Configure VPNProfileName</span></span>
1. <span data-ttu-id="708a2-220">Vyberte ProfileType (Typ profilu): **Native (Nativní)** **nebo Third Party (Třetí strana).**</span><span class="sxs-lookup"><span data-stu-id="708a2-220">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="708a2-221">V části Nativní profil vyberte **NativeProtocolType** a pak nakonfigurujte server, zásady směrování, typ ověřování a další nastavení.</span><span class="sxs-lookup"><span data-stu-id="708a2-221">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="708a2-222">Pro profil třetí strany nakonfigurujte adresu URL serveru, název skupiny balíčků aplikací modulů plug-in VPN (jenom 3 předdefinované) a vlastní konfigurace.</span><span class="sxs-lookup"><span data-stu-id="708a2-222">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="708a2-223">Exportujte balíček.</span><span class="sxs-lookup"><span data-stu-id="708a2-223">Export your package.</span></span>
1. <span data-ttu-id="708a2-224">Připojení svůj HoloLens a zkopírujte do zařízení soubor .ppkg.</span><span class="sxs-lookup"><span data-stu-id="708a2-224">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="708a2-225">Na HoloLens použijte soubor VPN .ppkg tak, že otevřete **nabídka Start a** vyberete přístup k účtu Nastavení do práce nebo do školy. Přidejte nebo odeberte zřizovací balíček –> Vyberte balíček  ->    ->    ->   VPN.</span><span class="sxs-lookup"><span data-stu-id="708a2-225">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <a name="setting-up-vpn-via-intune"></a><span data-ttu-id="708a2-226">Nastavení sítě VPN přes Intune</span><span class="sxs-lookup"><span data-stu-id="708a2-226">Setting up VPN via Intune</span></span>
<span data-ttu-id="708a2-227">Pokud chcete začít, postupujte podle dokumentů Intune.</span><span class="sxs-lookup"><span data-stu-id="708a2-227">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="708a2-228">Při použití těchto kroků mějte na paměti integrované protokoly VPN, které HoloLens zařízení podporují.</span><span class="sxs-lookup"><span data-stu-id="708a2-228">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="708a2-229">[Vytvořte profily VPN pro připojení k serverům VPN v Intune.](/mem/intune/configuration/vpn-settings-configure)</span><span class="sxs-lookup"><span data-stu-id="708a2-229">[Create VPN profiles to connect to VPN servers in Intune](/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="708a2-230">[Windows 10 a Windows zařízení Holographic přidejte připojení VPN pomocí Intune.](/mem/intune/configuration/vpn-settings-windows-10)</span><span class="sxs-lookup"><span data-stu-id="708a2-230">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="708a2-231">Až to bude hotové, [nezapomeňte profil přiřadit](/mem/intune/configuration/device-profile-assign).</span><span class="sxs-lookup"><span data-stu-id="708a2-231">When done please remember to [assign the profile](/mem/intune/configuration/device-profile-assign).</span></span>

### <a name="vpn-via-3rd-party-mdm-solutions"></a><span data-ttu-id="708a2-232">Síť VPN prostřednictvím řešení MDM třetích stran</span><span class="sxs-lookup"><span data-stu-id="708a2-232">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="708a2-233">Příklad připojení VPN třetí strany:</span><span class="sxs-lookup"><span data-stu-id="708a2-233">3rd party VPN connection example:</span></span>
```xml
<!-- Configure VPN Server Name or Address (PhoneNumber=) [Comma Separated]-->
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/ServerUrlList</LocURI>
          </Target>
          <Data>selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <!-- Configure VPN Plugin AppX Package ID (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/PluginPackageFamilyName</LocURI>
          </Target>
          <Data>TestVpnPluginApp-SL_8wekyb3d8bbwe</Data>
        </Item>
      </Add>

      <!-- Configure Microsoft's Custom XML (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/CustomConfiguration</LocURI>
          </Target>          <Data><pluginschema><ipAddress>auto</ipAddress><port>443</port><networksettings><routes><includev4><route><address>172.10.10.0</address><prefix>24</prefix></route></includev4></routes><namespaces><namespace><space>.vpnbackend.com</space><dnsservers><server>172.10.10.11</server></dnsservers></namespace></namespaces></networksettings></pluginschema></Data>
        </Item>
      </Add>
```

<span data-ttu-id="708a2-234">Příklad nativní sítě IKEv2 VPN:</span><span class="sxs-lookup"><span data-stu-id="708a2-234">Native IKEv2 VPN example:</span></span>
```xml
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Servers</LocURI>
          </Target>
          <Data>Selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/RoutingPolicyType</LocURI>
          </Target>
          <Data>ForceTunnel</Data>
        </Item>
      </Add>

      <!-- Configure VPN Protocol Type (L2tp, Pptp, Ikev2) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/NativeProtocolType</LocURI>
          </Target>
          <Data>Ikev2</Data>
        </Item>
      </Add>

      <!-- Configure VPN User Method (Mschapv2, Eap) -->
      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/UserMethod</LocURI>
          </Target>
          <Data>Eap</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/Eap/Configuration</LocURI>
          </Target>
          <Data>EAP_configuration_xml_content</Data>
        </Item>
      </Add>
```
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a><span data-ttu-id="708a2-235">Zakázání Wi-Fi HoloLens (1. generace)</span><span class="sxs-lookup"><span data-stu-id="708a2-235">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <a name="using-the-settings-app-on-hololens"></a><span data-ttu-id="708a2-236">Použití Nastavení aplikace na HoloLens</span><span class="sxs-lookup"><span data-stu-id="708a2-236">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="708a2-237">Otevřete **nabídku** Start.</span><span class="sxs-lookup"><span data-stu-id="708a2-237">Open the **Start** menu.</span></span>
1. <span data-ttu-id="708a2-238">V **Nastavení** **Start** nebo v seznamu **Všechny** aplikace na pravé straně nabídky Start vyberte **požadovanou aplikaci.**</span><span class="sxs-lookup"><span data-stu-id="708a2-238">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="708a2-239">Aplikace **Nastavení** se automaticky umístí před vás.</span><span class="sxs-lookup"><span data-stu-id="708a2-239">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="708a2-240">Vyberte **Network & Internet**.</span><span class="sxs-lookup"><span data-stu-id="708a2-240">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="708a2-241">Výběrem Wi-Fi posuvníku ho přesuňte do pozice **Vypnuto.**</span><span class="sxs-lookup"><span data-stu-id="708a2-241">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="708a2-242">Tím vypnete součásti RF rádia Wi-Fi a zakážete všechny funkce Wi-Fi na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="708a2-242">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="708a2-243">Pokud je Wi-Fi přepínač vypnutý, HoloLens nebudou moct automaticky načíst [mezery.](hololens-spaces.md)</span><span class="sxs-lookup"><span data-stu-id="708a2-243">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="708a2-244">Přepínač posuvníku přesuňte do **polohy Zap.** a zapněte přepínač Wi-Fi přepínač a obnovte Wi-Fi na Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="708a2-244">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="708a2-245">Vybraný přepínač Wi-Fi (**On** or **Off**) se zachová napříč restartováními.</span><span class="sxs-lookup"><span data-stu-id="708a2-245">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a><span data-ttu-id="708a2-246">Identifikace IP adresy vašeho HoloLens ve Wi-Fi síti</span><span class="sxs-lookup"><span data-stu-id="708a2-246">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <a name="by-using-the-settings-app"></a><span data-ttu-id="708a2-247">Pomocí Nastavení app</span><span class="sxs-lookup"><span data-stu-id="708a2-247">By using the Settings app</span></span>

1. <span data-ttu-id="708a2-248">Otevřete **nabídku** Start.</span><span class="sxs-lookup"><span data-stu-id="708a2-248">Open the **Start** menu.</span></span>
1. <span data-ttu-id="708a2-249">V **Nastavení** **Start** nebo v seznamu **Všechny** aplikace na pravé straně nabídky Start vyberte **požadovanou aplikaci.**</span><span class="sxs-lookup"><span data-stu-id="708a2-249">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="708a2-250">Aplikace **Nastavení** se automaticky umístí před vás.</span><span class="sxs-lookup"><span data-stu-id="708a2-250">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="708a2-251">Vyberte **Network & Internet**.</span><span class="sxs-lookup"><span data-stu-id="708a2-251">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="708a2-252">Posuňte se dolů pod seznam dostupných virtuálních Wi-Fi a vyberte **Hardwarové vlastnosti**.</span><span class="sxs-lookup"><span data-stu-id="708a2-252">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Vlastnosti hardwaru v Wi-Fi hardwaru](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="708a2-254">IP adresa se zobrazí vedle **IPv4 adresy**.</span><span class="sxs-lookup"><span data-stu-id="708a2-254">The IP address appears next to **IPv4 address**.</span></span>

### <a name="by-using-voice-commands"></a><span data-ttu-id="708a2-255">Pomocí hlasových příkazů</span><span class="sxs-lookup"><span data-stu-id="708a2-255">By using voice commands</span></span>

<span data-ttu-id="708a2-256">V závislosti na sestavení zařízení můžete k zobrazení IP adresy použít předdefinované hlasové příkazy nebo Cortana ip adresu.</span><span class="sxs-lookup"><span data-stu-id="708a2-256">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="708a2-257">V buildech po [roce 19041.1103](hololens-release-notes.md#windows-holographic-version-2004) vyslovte "What's my IP address?" (Jaká je moje IP adresa?).</span><span class="sxs-lookup"><span data-stu-id="708a2-257">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="708a2-258">a zobrazí se.</span><span class="sxs-lookup"><span data-stu-id="708a2-258">and it will be displayed.</span></span> <span data-ttu-id="708a2-259">U předchozích buildů nebo HoloLens (1. generace) řekněte "Cortana, jaká je moje IP adresa?"</span><span class="sxs-lookup"><span data-stu-id="708a2-259">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="708a2-260">a Cortana zobrazí a přečte vaši IP adresu.</span><span class="sxs-lookup"><span data-stu-id="708a2-260">and Cortana will display and read out your IP address.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="708a2-261">Pomocí Windows Portál zařízení</span><span class="sxs-lookup"><span data-stu-id="708a2-261">By using Windows Device Portal</span></span>

1. <span data-ttu-id="708a2-262">Ve webovém prohlížeči na počítači otevřete portál [zařízení](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="708a2-262">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="708a2-263">Přejděte do **části** Sítě.</span><span class="sxs-lookup"><span data-stu-id="708a2-263">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="708a2-264">V této části se zobrazí vaše IP adresa a další informace o síti.</span><span class="sxs-lookup"><span data-stu-id="708a2-264">This section displays your IP address and other network information.</span></span> <span data-ttu-id="708a2-265">Pomocí této metody můžete zkopírovat a vložit IP adresu na vývojovém počítači.</span><span class="sxs-lookup"><span data-stu-id="708a2-265">By using this method, you can copy and paste of the IP address on your development PC.</span></span>

## <a name="change-ip-address-to-static-address"></a><span data-ttu-id="708a2-266">Změna IP adresy na statickou adresu</span><span class="sxs-lookup"><span data-stu-id="708a2-266">Change IP Address to static address</span></span>
### <a name="by-using-settings"></a><span data-ttu-id="708a2-267">Pomocí Nastavení</span><span class="sxs-lookup"><span data-stu-id="708a2-267">By using Settings</span></span>
 
1. <span data-ttu-id="708a2-268">Otevřete **nabídku** Start.</span><span class="sxs-lookup"><span data-stu-id="708a2-268">Open the **Start** menu.</span></span>
1. <span data-ttu-id="708a2-269">V **Nastavení** **Start** nebo v seznamu **Všechny** aplikace na pravé straně nabídky Start vyberte **požadovanou aplikaci.**</span><span class="sxs-lookup"><span data-stu-id="708a2-269">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="708a2-270">Aplikace **Nastavení** se automaticky umístí před vás.</span><span class="sxs-lookup"><span data-stu-id="708a2-270">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="708a2-271">Vyberte **Network & Internet**.</span><span class="sxs-lookup"><span data-stu-id="708a2-271">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="708a2-272">Posuňte se dolů pod seznam dostupných virtuálních Wi-Fi a vyberte **Hardwarové vlastnosti**.</span><span class="sxs-lookup"><span data-stu-id="708a2-272">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>
1. <span data-ttu-id="708a2-273">V okně **Upravit nastavení IP** adresy změňte první pole na **Ruční**.</span><span class="sxs-lookup"><span data-stu-id="708a2-273">In the **Edit IP settings** window, change the first field to **Manual**.</span></span>
1. <span data-ttu-id="708a2-274">Do zbývajících polí zadejte požadovanou konfiguraci IP adresy a pak klikněte na **Uložit.**</span><span class="sxs-lookup"><span data-stu-id="708a2-274">Input the desired IP configuration in the remaining fields and then click **Save**.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="708a2-275">Pomocí Windows Portál zařízení</span><span class="sxs-lookup"><span data-stu-id="708a2-275">By using Windows Device Portal</span></span>

1. <span data-ttu-id="708a2-276">Ve webovém prohlížeči na počítači otevřete portál [zařízení](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="708a2-276">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="708a2-277">Přejděte do **části** Sítě.</span><span class="sxs-lookup"><span data-stu-id="708a2-277">Navigate to the **Networking** section.</span></span>
1. <span data-ttu-id="708a2-278">Vyberte tlačítko **Konfigurace IPv4.**</span><span class="sxs-lookup"><span data-stu-id="708a2-278">Select the **IPv4 Configuration** button.</span></span>
1. <span data-ttu-id="708a2-279">Vyberte **Použít následující IP adresu a** zadejte požadovanou konfiguraci protokolu TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="708a2-279">Select **Use the following IP address** and input the desired TCP/IP configuration.</span></span>
1. <span data-ttu-id="708a2-280">Vyberte **Použít následující adresy serveru DNS** a v případě potřeby zadejte adresy upřednostňovaného a alternativního serveru DNS.</span><span class="sxs-lookup"><span data-stu-id="708a2-280">Select **Use the following DNS server addresses** and enter the Preferred and Alternate DNS server addresses, if needed.</span></span>
1. <span data-ttu-id="708a2-281">Klikněte na **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="708a2-281">Click **Save**.</span></span> 
