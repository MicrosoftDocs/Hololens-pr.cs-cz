---
title: Připojení HoloLens k síti
description: Naučte se, jak nastavit a připojit se k Internetu pomocí HoloLens a jak identifikovat IP adresu zařízení.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, Wi-Fi, bezdrátové sítě, Internet, IP adresa, IP adresa
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: d68c75dcb2249a67f2e07c77cb1b69997eb0ae72
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379268"
---
# <a name="connect-hololens-to-a-network"></a><span data-ttu-id="a8d10-104">Připojení HoloLens k síti</span><span class="sxs-lookup"><span data-stu-id="a8d10-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="a8d10-105">K provedení většiny věcí v HoloLens musíte být připojeni k síti.</span><span class="sxs-lookup"><span data-stu-id="a8d10-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="a8d10-106">HoloLens obsahuje síť s Wi-Fi podporou standardu standardu 802.11 a připojení k síti je podobná připojení zařízení s Windows 10 Desktop nebo Mobile k síti Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="a8d10-106">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio and connecting it to a network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span> <span data-ttu-id="a8d10-107">Tato příručka vám pomůže:</span><span class="sxs-lookup"><span data-stu-id="a8d10-107">This guide will help you:</span></span>

- <span data-ttu-id="a8d10-108">Připojení k síti pomocí Wi-Fi nebo jenom pro HoloLens 2, Wi-Fi přímé nebo ethernetové přes USB-C</span><span class="sxs-lookup"><span data-stu-id="a8d10-108">Connect to a network using Wi-Fi, or for HoloLens 2 only, Wi-Fi Direct or Ethernet over USB-C</span></span>
- <span data-ttu-id="a8d10-109">Zakázat a znovu povolit Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="a8d10-109">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="a8d10-110">Přečtěte si další informace o [používání HoloLens offline](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="a8d10-110">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <a name="connecting-for-the-first-time"></a><span data-ttu-id="a8d10-111">První připojení</span><span class="sxs-lookup"><span data-stu-id="a8d10-111">Connecting for the first time</span></span>

<span data-ttu-id="a8d10-112">Při prvním použití HoloLens vás provedete připojením k síti Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="a8d10-112">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="a8d10-113">Pokud máte potíže s připojením k Wi-Fi během instalace, ujistěte se, že je vaše síť buď otevřená, chráněná heslem, nebo síť s jedním portálem.</span><span class="sxs-lookup"><span data-stu-id="a8d10-113">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="a8d10-114">Ověřte také, že síť nevyžaduje, abyste k připojení použili certifikát.</span><span class="sxs-lookup"><span data-stu-id="a8d10-114">Also, confirm that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="a8d10-115">Po instalaci se můžete připojit k jiným typům Wi-Fi sítí.</span><span class="sxs-lookup"><span data-stu-id="a8d10-115">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="a8d10-116">Na zařízeních s HoloLens 2 může uživatel k připojení přímo k Wi-Fi [použít také adaptér USB-C pro ethernetové](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) , který vám pomůže při nastavování zařízení.</span><span class="sxs-lookup"><span data-stu-id="a8d10-116">On HoloLens 2 devices, a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="a8d10-117">Jakmile zařízení nastaví uživatel, může ho i nadále používat, jinak může odpojit zařízení od adaptéru a [po nastavení se připojit k síti Wi-Fi](hololens-network.md#connecting-to-wi-fi-after-setup).</span><span class="sxs-lookup"><span data-stu-id="a8d10-117">Once the device has been set up a user may continue to use the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <a name="connecting-to-wi-fi-after-setup"></a><span data-ttu-id="a8d10-118">Připojení k Wi-Fi po instalaci</span><span class="sxs-lookup"><span data-stu-id="a8d10-118">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="a8d10-119">Předformátujte **gesto Start** a vyberte **Nastavení**.</span><span class="sxs-lookup"><span data-stu-id="a8d10-119">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="a8d10-120">Aplikace nastavení se automaticky umístí před vás.</span><span class="sxs-lookup"><span data-stu-id="a8d10-120">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="a8d10-121">Vyberte **Network & Internet**  >  **Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="a8d10-121">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="a8d10-122">Zkontrolujte, jestli je zapnuté Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="a8d10-122">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="a8d10-123">Pokud síť nevidíte, přejděte v seznamu dolů.</span><span class="sxs-lookup"><span data-stu-id="a8d10-123">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="a8d10-124">Vyberte síť a pak vyberte **připojit**.</span><span class="sxs-lookup"><span data-stu-id="a8d10-124">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="a8d10-125">Pokud se zobrazí výzva k zadání hesla k síti, zadejte ho a pak vyberte **Další**.</span><span class="sxs-lookup"><span data-stu-id="a8d10-125">If you are prompted for a network password type it and then select **Next**.</span></span>

![Nastavení Wi-Fi HoloLens](./images/hololens-2-wifi-settings.jpg)

<span data-ttu-id="a8d10-127">Pokud chcete ověřit, že jste připojení k síti Wi-Fi, zkontrolujte stav Wi-Fi v nabídce **Start** :</span><span class="sxs-lookup"><span data-stu-id="a8d10-127">To confirm you are connected to a Wi-Fi network, check the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="a8d10-128">Otevřete nabídku **Start** .</span><span class="sxs-lookup"><span data-stu-id="a8d10-128">Open the **Start** menu.</span></span>
1. <span data-ttu-id="a8d10-129">Podívejte se do levého horního rohu nabídky **Start** pro stav Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="a8d10-129">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="a8d10-130">Zobrazí se stav Wi-Fi a bude zobrazen identifikátor SSID připojené sítě.</span><span class="sxs-lookup"><span data-stu-id="a8d10-130">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

> [!TIP]
> <span data-ttu-id="a8d10-131">Pokud Wi-Fi není k dispozici, můžete [se také připojit k mobilním a 5g sítím](https://docs.microsoft.com/hololens/hololens-cellular).</span><span class="sxs-lookup"><span data-stu-id="a8d10-131">If Wi-Fi is not available, you can also [connect to Cellular and 5G networks](https://docs.microsoft.com/hololens/hololens-cellular).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8d10-132">Podle návrhu uživatelé nemůžou doladit Wi-Fi chování při roamingu HoloLens 2 – **jediným způsobem, jak seznam Wi-Fi aktualizovat, je přepnutí Wi-Fi vypnuto a zapnuto**.</span><span class="sxs-lookup"><span data-stu-id="a8d10-132">By design, users cannot fine tune the Wi-Fi roaming behavior of the HoloLens 2 - **the only way to refresh the Wi-Fi list is to toggle the Wi-Fi Off and On**.</span></span> <span data-ttu-id="a8d10-133">Tím se zabrání hodně problémům, třeba když zařízení zůstane zablokované na přístupový bod, jakmile je mimo rozsah.</span><span class="sxs-lookup"><span data-stu-id="a8d10-133">This prevents many issues, like where a device can remain "stuck" to an AP once it is out of range.</span></span>

## <a name="troubleshooting-your-connection-to-wi-fi"></a><span data-ttu-id="a8d10-134">Řešení potíží s připojením k Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="a8d10-134">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="a8d10-135">Pokud dochází k potížím s připojením k Wi-Fi, Projděte si téma nemůžu [se připojit k Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span><span class="sxs-lookup"><span data-stu-id="a8d10-135">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="a8d10-136">Když se na zařízení přihlašujete k podnikovému nebo organizačnímu účtu, může taky použít zásady správy mobilních zařízení (MDM), pokud je zásada nakonfigurovaná správcem IT.</span><span class="sxs-lookup"><span data-stu-id="a8d10-136">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a><span data-ttu-id="a8d10-137">Připojit HoloLens k podnikové Wi-Fi síti</span><span class="sxs-lookup"><span data-stu-id="a8d10-137">Connect HoloLens to Enterprise Wi-Fi Network</span></span>

<span data-ttu-id="a8d10-138">Podnikové Wi-Fi profily používají k ověřování Wi-Fi připojení protokol EAP (Extensible Authentication Protocol).</span><span class="sxs-lookup"><span data-stu-id="a8d10-138">Enterprise Wi-Fi profiles use Extensible Authentication Protocol (EAP) to authenticate Wi-Fi connections.</span></span> <span data-ttu-id="a8d10-139">Profil pro HoloLens Enterprise Wi-Fi můžete nakonfigurovat prostřednictvím MDM nebo zřizovacího balíčku vytvořeného nástrojem [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span><span class="sxs-lookup"><span data-stu-id="a8d10-139">HoloLens Enterprise Wi-Fi profile can be configured through MDM or provisioning package created by [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).</span></span>

<span data-ttu-id="a8d10-140">Pokud Microsoft Intune spravované zařízení, přečtěte si pokyny pro konfiguraci v [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) .</span><span class="sxs-lookup"><span data-stu-id="a8d10-140">For Microsoft Intune managed device, refer to [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) for configuration instructions.</span></span>

<span data-ttu-id="a8d10-141">Chcete-li vytvořit Wi-Fi zřizovací balíček v WCD, je vyžadován předem nakonfigurovaný Wi-Fi profil .xml souboru.</span><span class="sxs-lookup"><span data-stu-id="a8d10-141">To create a Wi-Fi provisioning package in WCD, a pre-configured Wi-Fi profile .xml file is required.</span></span> <span data-ttu-id="a8d10-142">Tady je ukázkový profil Wi-Fi pro WPA2-Enterprise s ověřováním EAP-TLS:</span><span class="sxs-lookup"><span data-stu-id="a8d10-142">Here is a sample Wi-Fi profile for WPA2-Enterprise with EAP-TLS authentication:</span></span>

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


<span data-ttu-id="a8d10-143">Certifikát kořenové certifikační autority serveru a klientský certifikát může být potřeba v zařízení zřídit v závislosti na typu protokolu EAP.</span><span class="sxs-lookup"><span data-stu-id="a8d10-143">Server root CA certificate and client certificate may need to be provisioned on the device depending on the EAP type.</span></span>

<span data-ttu-id="a8d10-144">Další prostředky:</span><span class="sxs-lookup"><span data-stu-id="a8d10-144">Additional resources:</span></span>

- <span data-ttu-id="a8d10-145">WLANv1Profile schéma: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span><span class="sxs-lookup"><span data-stu-id="a8d10-145">WLANv1Profile Schema: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)</span></span>
- <span data-ttu-id="a8d10-146">EAP-TLS – schéma: [[MS-GPWL]: schéma Microsoft EAP TLS | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span><span class="sxs-lookup"><span data-stu-id="a8d10-146">EAP-TLS Schema: [[MS-GPWL]: Microsoft EAP TLS Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)</span></span>

## <a name="eap-troubleshooting"></a><span data-ttu-id="a8d10-147">Řešení potíží s protokolem EAP</span><span class="sxs-lookup"><span data-stu-id="a8d10-147">EAP Troubleshooting</span></span>
> [!TIP]
> <span data-ttu-id="a8d10-148">Většina potíží se sítí je výsledkem jednoho z následujících 3 nastavení, které je v profilu sítě Wi-FI nesprávné.</span><span class="sxs-lookup"><span data-stu-id="a8d10-148">A majority of network issues are the result of one of the below 3 settings being incorrect in the Wi-FI profile.</span></span> 
1. <span data-ttu-id="a8d10-149">Dvojitá check Wi-Fi profil má správné nastavení:</span><span class="sxs-lookup"><span data-stu-id="a8d10-149">Double check Wi-Fi profile has right settings:</span></span>
   1. <span data-ttu-id="a8d10-150">Typ protokolu EAP je správně nakonfigurovaný, běžné typy protokolu EAP: EAP-TLS (13), EAP-TTLS (21) a PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="a8d10-150">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
   1. <span data-ttu-id="a8d10-151">Název SSID Wi-Fi je vpravo a odpovídá řetězci HEX.</span><span class="sxs-lookup"><span data-stu-id="a8d10-151">Wi-Fi SSID name is right and matches with HEX string.</span></span>
   1. <span data-ttu-id="a8d10-152">Pro EAP-TLS obsahuje TrustedRootCA hodnotu hash SHA-1 certifikátu důvěryhodné kořenové certifikační autority serveru&#39;s.</span><span class="sxs-lookup"><span data-stu-id="a8d10-152">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server&#39;s trusted root CA certificate.</span></span> <span data-ttu-id="a8d10-153">V počítači se systémem Windows &quot;certutil.exe – v \_ příkazu výpis názvu souboru certifikátu \_ &quot; se zobrazí řetězec s hodnotou hash SHA-1&#39;certifikátu.</span><span class="sxs-lookup"><span data-stu-id="a8d10-153">On Windows PC &quot;certutil.exe -dump cert\_file\_name&quot; command will show a certificate&#39;s SHA-1 hash string.</span></span>

2. <span data-ttu-id="a8d10-154">Shromažďovat Zachytávání síťových paketů v protokolech přístupového bodu nebo řadiči serveru AAA, kde zjistíte, kde se relace protokolu EAP nezdařila.</span><span class="sxs-lookup"><span data-stu-id="a8d10-154">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
   1. <span data-ttu-id="a8d10-155">Pokud není očekávána Identita protokolu EAP poskytovaná pomocí HoloLens, ověřte, zda byla identita správně zajištěna prostřednictvím profilu Wi-Fi nebo klientského certifikátu.</span><span class="sxs-lookup"><span data-stu-id="a8d10-155">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
   1. <span data-ttu-id="a8d10-156">Pokud server odmítne klientský certifikát HoloLens, ověřte, jestli je na zařízení požadovaný klientský certifikát zřízený.</span><span class="sxs-lookup"><span data-stu-id="a8d10-156">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
   1. <span data-ttu-id="a8d10-157">Pokud HoloLens odmítne certifikát serveru, ověřte, jestli je certifikát kořenové certifikační autority serveru zřízený na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a8d10-157">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
1. <span data-ttu-id="a8d10-158">Pokud se profil Enterprise zřídí prostřednictvím balíčku pro Wi-Fi zřizování, zvažte použití zřizovacího balíčku na počítači s Windows 10.</span><span class="sxs-lookup"><span data-stu-id="a8d10-158">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="a8d10-159">Pokud se to nepovede i na počítači s Windows 10, postupujte podle [Průvodce odstraňováním potíží s ověřováním klienta ve Windows 802.1 x](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).</span><span class="sxs-lookup"><span data-stu-id="a8d10-159">If it also fails on Windows 10 PC, follow the [Windows client 802.1X authentication troubleshooting guide](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).</span></span>
1. <span data-ttu-id="a8d10-160">Nastavte svou telemetrii na úplnou nebo volitelnou (v závislosti na vašem buildu) a pošlete nám svůj názor prostřednictvím [centra zpětné vazby](https://docs.microsoft.com/hololens/hololens-feedback).</span><span class="sxs-lookup"><span data-stu-id="a8d10-160">Set your telemetry to Full or Optional (depending on your build) and then send us feedback through [Feedback Hub](https://docs.microsoft.com/hololens/hololens-feedback).</span></span>

### <a name="additional-resources"></a><span data-ttu-id="a8d10-161">Další prostředky:</span><span class="sxs-lookup"><span data-stu-id="a8d10-161">Additional resources:</span></span>
- [<span data-ttu-id="a8d10-162">Export nastavení Wi-Fi ze zařízení s Windows</span><span class="sxs-lookup"><span data-stu-id="a8d10-162">Export Wi-Fi settings from a Windows device</span></span>](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1#export-wi-fi-settings-from-a-windows-device)

## <a name="configure-network-proxy"></a><span data-ttu-id="a8d10-163">Konfigurace síťového proxy serveru</span><span class="sxs-lookup"><span data-stu-id="a8d10-163">Configure Network Proxy</span></span>

<span data-ttu-id="a8d10-164">Tato část se zabývá síťovým proxy pro aplikace HoloLens a Univerzální platforma Windows (UWP) pomocí sady Windows HTTP Stack.</span><span class="sxs-lookup"><span data-stu-id="a8d10-164">This section covers network proxy for HoloLens OS and Universal Windows Platform (UWP) Apps using Windows HTTP stack.</span></span> <span data-ttu-id="a8d10-165">Aplikace, které používají jiný zásobník HTTP než Windows, můžou mít svou vlastní konfiguraci a manipulaci s proxy serverem.</span><span class="sxs-lookup"><span data-stu-id="a8d10-165">Applications using non-Windows HTTP stack may have their own proxy configuration and handling.</span></span> 

### <a name="proxy-configurations"></a><span data-ttu-id="a8d10-166">Konfigurace proxy</span><span class="sxs-lookup"><span data-stu-id="a8d10-166">Proxy Configurations</span></span> 

- <span data-ttu-id="a8d10-167">Skript automatické konfigurace proxy serveru (PAC): [soubor PAC](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (otevře se na webu, který není Microsoft) obsahuje funkci JavaScriptu FindProxyForURL (URL, hostitel).</span><span class="sxs-lookup"><span data-stu-id="a8d10-167">Proxy Auto-Config (PAC) script: a [PAC file](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (opens a non-Microsoft site) contains a JavaScript function FindProxyForURL(url, host).</span></span> 
- <span data-ttu-id="a8d10-168">Statický proxy server: ve formě serveru: port.</span><span class="sxs-lookup"><span data-stu-id="a8d10-168">Static Proxy: in the form of Server:Port.</span></span>  
- <span data-ttu-id="a8d10-169">Protokol WPAD (Web Proxy Auto-Discovery Protocol): zadejte adresu URL konfiguračního souboru proxy serveru prostřednictvím protokolu DHCP nebo DNS.</span><span class="sxs-lookup"><span data-stu-id="a8d10-169">Web Proxy Auto-Discovery Protocol (WPAD): provide URL of proxy configuration file through DHCP or DNS.</span></span> 

### <a name="proxy-provisioning-methods"></a><span data-ttu-id="a8d10-170">Metody zřizování proxy</span><span class="sxs-lookup"><span data-stu-id="a8d10-170">Proxy Provisioning Methods</span></span> 
<span data-ttu-id="a8d10-171">Existují tři způsoby, jak zřídit proxy:</span><span class="sxs-lookup"><span data-stu-id="a8d10-171">There are three ways to provision proxies:</span></span>

 

1.  <span data-ttu-id="a8d10-172">**Uživatelské rozhraní nastavení:**</span><span class="sxs-lookup"><span data-stu-id="a8d10-172">**Settings UI:**</span></span> 
    1. <span data-ttu-id="a8d10-173">Proxy pro jednotlivé uživatele (20H2 nebo starší):</span><span class="sxs-lookup"><span data-stu-id="a8d10-173">Per-user proxy (20H2 or earlier):</span></span>
        1. <span data-ttu-id="a8d10-174">Otevřete nabídku Start a vyberte nastavení.</span><span class="sxs-lookup"><span data-stu-id="a8d10-174">Open the Start menu and select Settings.</span></span>
        2. <span data-ttu-id="a8d10-175">V nabídce vlevo vyberte Network & Internet a pak proxy.</span><span class="sxs-lookup"><span data-stu-id="a8d10-175">Select Network & Internet and then Proxy on the left menu.</span></span>
        3. <span data-ttu-id="a8d10-176">Přejděte dolů na ruční nastavení proxy serveru a přepínač použít proxy server na zapnuto.</span><span class="sxs-lookup"><span data-stu-id="a8d10-176">Scroll down to Manual proxy setup and toggle Use a proxy server to On.</span></span>
        4. <span data-ttu-id="a8d10-177">Zadejte IP adresu proxy server.</span><span class="sxs-lookup"><span data-stu-id="a8d10-177">Enter the IP address of the proxy server.</span></span>
        5. <span data-ttu-id="a8d10-178">Zadejte číslo portu.</span><span class="sxs-lookup"><span data-stu-id="a8d10-178">Enter the port number.</span></span>
        6. <span data-ttu-id="a8d10-179">Klikněte na Uložit.</span><span class="sxs-lookup"><span data-stu-id="a8d10-179">Click Save.</span></span>
      1. <span data-ttu-id="a8d10-180">Proxy Wi-Fi (21H1 nebo vyšší):</span><span class="sxs-lookup"><span data-stu-id="a8d10-180">WiFi proxy (21H1 or higher):</span></span>
          1. <span data-ttu-id="a8d10-181">Otevřete nabídku Start a přejděte na stránku vlastností vaší sítě Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="a8d10-181">Open the Start menu and go to your Wi-Fi Network’s Properties page.</span></span>
          1. <span data-ttu-id="a8d10-182">Posunout dolů na proxy</span><span class="sxs-lookup"><span data-stu-id="a8d10-182">Scroll down to Proxy</span></span>
          1. <span data-ttu-id="a8d10-183">Změnit na ruční instalaci</span><span class="sxs-lookup"><span data-stu-id="a8d10-183">Change to Manual Setup</span></span>
          1. <span data-ttu-id="a8d10-184">Zadejte IP adresu proxy server.</span><span class="sxs-lookup"><span data-stu-id="a8d10-184">Enter the IP address of the proxy server.</span></span>
          1. <span data-ttu-id="a8d10-185">Zadejte číslo portu.</span><span class="sxs-lookup"><span data-stu-id="a8d10-185">Enter the port number.</span></span>
          1. <span data-ttu-id="a8d10-186">Klikněte na použít.</span><span class="sxs-lookup"><span data-stu-id="a8d10-186">Click Apply.</span></span>
        
 2. <span data-ttu-id="a8d10-187">**MDM**</span><span class="sxs-lookup"><span data-stu-id="a8d10-187">**MDM**</span></span> 
     1. <span data-ttu-id="a8d10-188">Intune – pomocí těchto [kroků](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) nakonfigurujete proxy server v Intune.</span><span class="sxs-lookup"><span data-stu-id="a8d10-188">Intune - Use these [steps](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) to configure proxy in Intune.</span></span> <span data-ttu-id="a8d10-189">Budete se muset posunout k dolní části oddílu.</span><span class="sxs-lookup"><span data-stu-id="a8d10-189">You will need to scroll to the bottom of the section.</span></span>
     1. <span data-ttu-id="a8d10-190">Další řešení MDM třetí strany – použijte [zprostředkovatele CSP pro Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp).</span><span class="sxs-lookup"><span data-stu-id="a8d10-190">Other 3rd party MDM solutions - Use a [WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp).</span></span>

3. <span data-ttu-id="a8d10-191">**PPKG**</span><span class="sxs-lookup"><span data-stu-id="a8d10-191">**PPKG**</span></span> 
    1. <span data-ttu-id="a8d10-192">Otevřít Windows Configuration Designer</span><span class="sxs-lookup"><span data-stu-id="a8d10-192">Open Windows Configuration Designer</span></span>
    1. <span data-ttu-id="a8d10-193">Klikněte na rozšířené zřizování, zadejte název nového projektu a klikněte na další.</span><span class="sxs-lookup"><span data-stu-id="a8d10-193">Click on Advanced Provisioning, enter the name for your new Project and click Next.</span></span>
    1. <span data-ttu-id="a8d10-194">Vyberte Windows holografické (HoloLens 2) a klikněte na další.</span><span class="sxs-lookup"><span data-stu-id="a8d10-194">Select Windows Holographic (HoloLens 2) and click Next.</span></span>
    1. <span data-ttu-id="a8d10-195">Importujte PPKG (volitelné) a klikněte na Dokončit.</span><span class="sxs-lookup"><span data-stu-id="a8d10-195">Import your PPKG (optional) and click Finish.</span></span>
    1. <span data-ttu-id="a8d10-196">Rozbalte nastavení modulu runtime-> profily připojení – proxy server WLAN > > WLAN.</span><span class="sxs-lookup"><span data-stu-id="a8d10-196">Expand Runtime Settings -> Connectivity Profiles -> WLAN -> WLAN Proxy.</span></span>
    1. <span data-ttu-id="a8d10-197">Zadejte identifikátor SSID vaší Wi-Fi sítě a klikněte na Přidat.</span><span class="sxs-lookup"><span data-stu-id="a8d10-197">Enter the SSID of your Wi-Fi network and click Add.</span></span>
    1. <span data-ttu-id="a8d10-198">V levém okně vyberte svou Wi-Fiovou síť a zadejte požadované vlastní nastavení.</span><span class="sxs-lookup"><span data-stu-id="a8d10-198">Select your Wi-Fi network in the left window and enter your desired customizations.</span></span> <span data-ttu-id="a8d10-199">Povolená přizpůsobení se zobrazí tučně v levé nabídce.</span><span class="sxs-lookup"><span data-stu-id="a8d10-199">The enabled customizations will show in bold on the left menu.</span></span>
    1. <span data-ttu-id="a8d10-200">Klikněte na Uložit a ukončit.</span><span class="sxs-lookup"><span data-stu-id="a8d10-200">Click Save and Exit.</span></span>
    1. <span data-ttu-id="a8d10-201">[Použijte](https://docs.microsoft.com/hololens/hololens-provisioning#applyremove-a-provisioning-package-to-hololens-after-setup) zřizovací balíček pro HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a8d10-201">[Apply](https://docs.microsoft.com/hololens/hololens-provisioning#applyremove-a-provisioning-package-to-hololens-after-setup) the provisioning package to the HoloLens.</span></span>

<span data-ttu-id="a8d10-202">Poskytovatelé [CSP](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) jsou za mnoha úlohami správy a zásadami pro Windows 10, a to jak v Microsoft Intune, tak i v jiných poskytovatelích služeb Microsoft MDM.</span><span class="sxs-lookup"><span data-stu-id="a8d10-202">[CSPs](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) are behind many of the management tasks and policies for Windows 10, both in Microsoft Intune and in non-Microsoft MDM service providers.</span></span> <span data-ttu-id="a8d10-203">Pomocí [nástroje Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) můžete také vytvořit [zřizovací balíček](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) a použít ho pro HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="a8d10-203">You can also use [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) to create a [provisioning package](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) and apply it to the HoloLens 2.</span></span>
<span data-ttu-id="a8d10-204">Nejpravděpodobnějším CSP, které budou aplikovány na HoloLens 2, jsou:</span><span class="sxs-lookup"><span data-stu-id="a8d10-204">The most likely CSPs that will be applied to your HoloLens 2 are:</span></span>

- <span data-ttu-id="a8d10-205">[Zprostředkovatel](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp)připojení k Wi-Fi: pro profil Wi-Fi proxy</span><span class="sxs-lookup"><span data-stu-id="a8d10-205">[WiFi CSP](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp): per-profile Wi-Fi proxy</span></span> 

[<span data-ttu-id="a8d10-206">Další CSP podporované v zařízeních HoloLens</span><span class="sxs-lookup"><span data-stu-id="a8d10-206">Other CSPs supported in HoloLens devices</span></span>](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a><span data-ttu-id="a8d10-207">Síť VPN</span><span class="sxs-lookup"><span data-stu-id="a8d10-207">VPN</span></span>
<span data-ttu-id="a8d10-208">Připojení VPN vám může pomáhat zajistit bezpečnější připojení a přístup k síti vaší společnosti a k Internetu.</span><span class="sxs-lookup"><span data-stu-id="a8d10-208">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="a8d10-209">HoloLens 2 podporuje integrovaný modul plug-in VPN klienta a Univerzální platforma Windows (UWP).</span><span class="sxs-lookup"><span data-stu-id="a8d10-209">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="a8d10-210">Podporované integrované protokoly sítě VPN:</span><span class="sxs-lookup"><span data-stu-id="a8d10-210">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="a8d10-211">IKEv2</span><span class="sxs-lookup"><span data-stu-id="a8d10-211">IKEv2</span></span>
- <span data-ttu-id="a8d10-212">L2TP</span><span class="sxs-lookup"><span data-stu-id="a8d10-212">L2TP</span></span>
- <span data-ttu-id="a8d10-213">PPTP</span><span class="sxs-lookup"><span data-stu-id="a8d10-213">PPTP</span></span>

<span data-ttu-id="a8d10-214">Pokud se certifikát používá k ověřování integrovaného klienta VPN, musí se požadovaný klientský certifikát přidat do úložiště certifikátů uživatele.</span><span class="sxs-lookup"><span data-stu-id="a8d10-214">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="a8d10-215">Pokud chcete zjistit, jestli modul plug-in VPN třetí strany podporuje HoloLens 2, přejděte do Storu a Najděte aplikaci VPN a ověřte, jestli je na stránce požadavky na systém uvedená aplikace, která podporuje architekturu ARM nebo ARM64.</span><span class="sxs-lookup"><span data-stu-id="a8d10-215">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="a8d10-216">HoloLens podporuje jenom Univerzální platforma Windows aplikace pro VPN třetích stran.</span><span class="sxs-lookup"><span data-stu-id="a8d10-216">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

 <span data-ttu-id="a8d10-217">SÍŤ VPN se dá spravovat přes MDM prostřednictvím [Nastavení/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)a nastavuje se prostřednictvím  [zásad podpora vpnv2-CSP](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span><span class="sxs-lookup"><span data-stu-id="a8d10-217">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>

<span data-ttu-id="a8d10-218">Přečtěte si další informace o [tom, jak nakonfigurovat síť VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) pomocí [těchto průvodců](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span><span class="sxs-lookup"><span data-stu-id="a8d10-218">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

### <a name="vpn-via-ui"></a><span data-ttu-id="a8d10-219">VPN prostřednictvím uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="a8d10-219">VPN via UI</span></span>

<span data-ttu-id="a8d10-220">SÍŤ VPN není ve výchozím nastavení povolená, můžete ji ale povolit ručně otevřením **Nastavení** aplikace a přechodem na  **síť & Internet-> VPN**.</span><span class="sxs-lookup"><span data-stu-id="a8d10-220">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span>
1. <span data-ttu-id="a8d10-221">Vyberte poskytovatele sítě VPN.</span><span class="sxs-lookup"><span data-stu-id="a8d10-221">Select a VPN provider.</span></span>
1. <span data-ttu-id="a8d10-222">Vytvořte název připojení.</span><span class="sxs-lookup"><span data-stu-id="a8d10-222">Create a connection name.</span></span> 
1. <span data-ttu-id="a8d10-223">Zadejte název nebo adresu svého serveru.</span><span class="sxs-lookup"><span data-stu-id="a8d10-223">Enter your server name or address.</span></span>
1. <span data-ttu-id="a8d10-224">Vyberte typ sítě VPN.</span><span class="sxs-lookup"><span data-stu-id="a8d10-224">Select the VPN type.</span></span>
1. <span data-ttu-id="a8d10-225">Vyberte typ přihlašovacích údajů.</span><span class="sxs-lookup"><span data-stu-id="a8d10-225">Select type of sign-in info.</span></span> 
1. <span data-ttu-id="a8d10-226">Volitelně můžete přidat uživatelské jméno a heslo.</span><span class="sxs-lookup"><span data-stu-id="a8d10-226">Optionally add user name and password.</span></span>
1. <span data-ttu-id="a8d10-227">Použijte nastavení sítě VPN.</span><span class="sxs-lookup"><span data-stu-id="a8d10-227">Apply the VPN settings.</span></span> 

![Nastavení sítě VPN HoloLens](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a><span data-ttu-id="a8d10-229">Nastavení sítě VPN prostřednictvím zřizovacího balíčku</span><span class="sxs-lookup"><span data-stu-id="a8d10-229">VPN set via Provisioning Package</span></span>

> [!TIP] 
> <span data-ttu-id="a8d10-230">Ve Windows holografické verzi 20H2 jsme vyřešili problém s konfigurací proxy serveru pro připojení k síti VPN.</span><span class="sxs-lookup"><span data-stu-id="a8d10-230">In our Windows Holographic, version 20H2 we fixed a proxy configuration issue for VPN connection.</span></span> <span data-ttu-id="a8d10-231">Pokud máte v úmyslu tento tok používat, zvažte možnost upgradovat zařízení na toto sestavení.</span><span class="sxs-lookup"><span data-stu-id="a8d10-231">Please consider upgrading devices to this build if you intend to use this flow.</span></span>

1. <span data-ttu-id="a8d10-232">Spusťte Windows Configuration Designer.</span><span class="sxs-lookup"><span data-stu-id="a8d10-232">Launch Windows Configuration Designer.</span></span>
1. <span data-ttu-id="a8d10-233">Klikněte na **zřídit zařízení HoloLens** a pak vyberte cílové zařízení a **Další**.</span><span class="sxs-lookup"><span data-stu-id="a8d10-233">Click **Provision HoloLens devices**, then select target device and **Next**.</span></span>
1. <span data-ttu-id="a8d10-234">Zadejte název a cestu balíčku.</span><span class="sxs-lookup"><span data-stu-id="a8d10-234">Enter package name and path.</span></span>
1. <span data-ttu-id="a8d10-235">Klikněte na **Přepnout do rozšířeného editoru**.</span><span class="sxs-lookup"><span data-stu-id="a8d10-235">Click **Switch to advanced editor**.</span></span>
1. <span data-ttu-id="a8d10-236">Otevřete **nastavení modulu runtime**  ->  **ConnectivityProfiles**  ->  **VPN**  ->  **VPNSettings**.</span><span class="sxs-lookup"><span data-stu-id="a8d10-236">Open **Runtime settings** -> **ConnectivityProfiles** -> **VPN** -> **VPNSettings**.</span></span>
1. <span data-ttu-id="a8d10-237">Konfigurace VPNProfileName</span><span class="sxs-lookup"><span data-stu-id="a8d10-237">Configure VPNProfileName</span></span>
1. <span data-ttu-id="a8d10-238">Vyberte typ souboru: **nativní** nebo **třetí strana**.</span><span class="sxs-lookup"><span data-stu-id="a8d10-238">Select ProfileType: **Native** or **Third Party**.</span></span>
    1. <span data-ttu-id="a8d10-239">V případě nativního profilu vyberte **NativeProtocolType** a pak nakonfigurujte server, zásady směrování, typ ověřování a další nastavení.</span><span class="sxs-lookup"><span data-stu-id="a8d10-239">For Native profile, select **NativeProtocolType**, then configure server, routing policy, authentication type and other settings.</span></span>
    1. <span data-ttu-id="a8d10-240">Pro profil třetí strany nakonfigurujte adresu URL serveru, modul plug-in aplikace VPN název sady balíčků (jenom 3 předdefinované) a vlastní konfigurace.</span><span class="sxs-lookup"><span data-stu-id="a8d10-240">For "Third Party" profile, configure server URL, VPN plug-in App package family name (only 3 predefined) and custom configurations.</span></span>
1. <span data-ttu-id="a8d10-241">Exportujte balíček.</span><span class="sxs-lookup"><span data-stu-id="a8d10-241">Export your package.</span></span>
1. <span data-ttu-id="a8d10-242">Připojte HoloLens a zkopírujte soubor. ppkg do zařízení.</span><span class="sxs-lookup"><span data-stu-id="a8d10-242">Connect your HoloLens and copy the .ppkg file to the device.</span></span> 
1. <span data-ttu-id="a8d10-243">V prostředí HoloLens použijte VPN. ppkg tak, že otevřete nabídku Start a vyberete **Nastavení**  ->    ->  **přístup k účtu nebo školu**  ->  **přidáte nebo odeberete zřizovací balíček** – > vybrat balíček VPN.</span><span class="sxs-lookup"><span data-stu-id="a8d10-243">On HoloLens, apply the VPN .ppkg by opening the Start menu and selecting **Settings** -> **Account** -> **Access work or school** -> **Add or remove provisioning package** -> Select your VPN package.</span></span>


### <a name="setting-up-vpn-via-intune"></a><span data-ttu-id="a8d10-244">Nastavení sítě VPN přes Intune</span><span class="sxs-lookup"><span data-stu-id="a8d10-244">Setting up VPN via Intune</span></span>
<span data-ttu-id="a8d10-245">Stačí postupovat podle dokumentů Intune a začít.</span><span class="sxs-lookup"><span data-stu-id="a8d10-245">Just follow the Intune documents to get started.</span></span> <span data-ttu-id="a8d10-246">Pokud budete postupovat podle těchto kroků, pamatujte na integrované protokoly sítě VPN, které podporují zařízení HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a8d10-246">When following these steps please keep in mind the built-in VPN protocols that HoloLens devices support.</span></span> 

<span data-ttu-id="a8d10-247">[Vytvořte profily sítě VPN pro připojení k SERVERŮM VPN v Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="a8d10-247">[Create VPN profiles to connect to VPN servers in Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).</span></span>

<span data-ttu-id="a8d10-248">[Nastavení zařízení s Windows 10 a Windows holografické pro přidání připojení k síti VPN pomocí Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10)</span><span class="sxs-lookup"><span data-stu-id="a8d10-248">[Windows 10 and Windows Holographic device settings to add VPN connections using Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10).</span></span>

<span data-ttu-id="a8d10-249">Po dokončení prosím nezapomeňte [profil přiřadit](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span><span class="sxs-lookup"><span data-stu-id="a8d10-249">When done please remember to [assign the profile](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

### <a name="vpn-via-3rd-party-mdm-solutions"></a><span data-ttu-id="a8d10-250">VPN prostřednictvím řešení MDM jiného výrobce</span><span class="sxs-lookup"><span data-stu-id="a8d10-250">VPN via 3rd party MDM solutions</span></span>
<span data-ttu-id="a8d10-251">Příklad připojení k síti VPN třetí strany:</span><span class="sxs-lookup"><span data-stu-id="a8d10-251">3rd party VPN connection example:</span></span>
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

<span data-ttu-id="a8d10-252">Příklad nativní IKEv2 VPN:</span><span class="sxs-lookup"><span data-stu-id="a8d10-252">Native IKEv2 VPN example:</span></span>
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
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a><span data-ttu-id="a8d10-253">Zakázání Wi-Fi na HoloLens (1. generace)</span><span class="sxs-lookup"><span data-stu-id="a8d10-253">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <a name="using-the-settings-app-on-hololens"></a><span data-ttu-id="a8d10-254">Použití aplikace nastavení na HoloLens</span><span class="sxs-lookup"><span data-stu-id="a8d10-254">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="a8d10-255">Otevřete nabídku **Start** .</span><span class="sxs-lookup"><span data-stu-id="a8d10-255">Open the **Start** menu.</span></span>
1. <span data-ttu-id="a8d10-256">V seznamu **starts** ( **všechny aplikace** ) na pravé straně nabídky **Start** vyberte aplikace **Nastavení** .</span><span class="sxs-lookup"><span data-stu-id="a8d10-256">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="a8d10-257">Aplikace **Nastavení** se automaticky umístí před vás.</span><span class="sxs-lookup"><span data-stu-id="a8d10-257">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="a8d10-258">Vyberte **Network & Internet**.</span><span class="sxs-lookup"><span data-stu-id="a8d10-258">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="a8d10-259">Vyberte přepínač posuvníku Wi-Fi, který chcete přesunout do **vypnuté** pozice.</span><span class="sxs-lookup"><span data-stu-id="a8d10-259">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="a8d10-260">Tato akce vypne součásti RF Wi-Fi přepínači a zakáže všechny Wi-Fi funkce na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a8d10-260">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="a8d10-261">Pokud je přepínač Wi-Fi zakázán, HoloLens nebude moci automaticky načíst vaše [mezery](hololens-spaces.md).</span><span class="sxs-lookup"><span data-stu-id="a8d10-261">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="a8d10-262">Přesunutím posuvníku **na pozici zapněte funkci** Wi-Fi Radio and restore Wi-Fi on Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="a8d10-262">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="a8d10-263">Vybraný stav přepínačů Wi-Fi (**zapnuto** nebo **vypnuto**) bude v průběhu restartování zachován.</span><span class="sxs-lookup"><span data-stu-id="a8d10-263">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a><span data-ttu-id="a8d10-264">Určení IP adresy HoloLens v Wi-Fi síti</span><span class="sxs-lookup"><span data-stu-id="a8d10-264">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <a name="by-using-the-settings-app"></a><span data-ttu-id="a8d10-265">Pomocí aplikace nastavení</span><span class="sxs-lookup"><span data-stu-id="a8d10-265">By using the Settings app</span></span>

1. <span data-ttu-id="a8d10-266">Otevřete nabídku **Start** .</span><span class="sxs-lookup"><span data-stu-id="a8d10-266">Open the **Start** menu.</span></span>
1. <span data-ttu-id="a8d10-267">V seznamu **starts** ( **všechny aplikace** ) na pravé straně nabídky **Start** vyberte aplikace **Nastavení** .</span><span class="sxs-lookup"><span data-stu-id="a8d10-267">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="a8d10-268">Aplikace **Nastavení** se automaticky umístí před vás.</span><span class="sxs-lookup"><span data-stu-id="a8d10-268">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="a8d10-269">Vyberte **Network & Internet**.</span><span class="sxs-lookup"><span data-stu-id="a8d10-269">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="a8d10-270">Posuňte se dolů k seznamu dostupných Wi-Fi sítí a vyberte **vlastnosti hardwaru**.</span><span class="sxs-lookup"><span data-stu-id="a8d10-270">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![Vlastnosti hardwaru v nastaveních Wi-Fi](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="a8d10-272">IP adresa se zobrazí vedle pole **adresa IPv4**.</span><span class="sxs-lookup"><span data-stu-id="a8d10-272">The IP address appears next to **IPv4 address**.</span></span>

### <a name="by-using-voice-commands"></a><span data-ttu-id="a8d10-273">Pomocí hlasových příkazů</span><span class="sxs-lookup"><span data-stu-id="a8d10-273">By using voice commands</span></span>

<span data-ttu-id="a8d10-274">V závislosti na sestaveních vašich zařízení můžete pomocí integrovaných hlasových příkazů nebo Cortany zobrazit vaši IP adresu.</span><span class="sxs-lookup"><span data-stu-id="a8d10-274">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="a8d10-275">Na buildy po [19041,1103](hololens-release-notes.md#windows-holographic-version-2004) mluvit "Co je moje IP adresa?"</span><span class="sxs-lookup"><span data-stu-id="a8d10-275">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="a8d10-276">a zobrazí se.</span><span class="sxs-lookup"><span data-stu-id="a8d10-276">and it will be displayed.</span></span> <span data-ttu-id="a8d10-277">Pro dřívější buildy nebo HoloLens (1. generace) říká "Hey Cortana", kde je moje IP adresa?</span><span class="sxs-lookup"><span data-stu-id="a8d10-277">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="a8d10-278">a Cortana zobrazí a přečte vaši IP adresu.</span><span class="sxs-lookup"><span data-stu-id="a8d10-278">and Cortana will display and read out your IP address.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="a8d10-279">Pomocí portálu zařízení Windows</span><span class="sxs-lookup"><span data-stu-id="a8d10-279">By using Windows Device Portal</span></span>

1. <span data-ttu-id="a8d10-280">Ve webovém prohlížeči na počítači otevřete [portál zařízení](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="a8d10-280">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="a8d10-281">Přejděte do části **sítě** .</span><span class="sxs-lookup"><span data-stu-id="a8d10-281">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="a8d10-282">V této části se zobrazuje vaše IP adresa a další informace o síti.</span><span class="sxs-lookup"><span data-stu-id="a8d10-282">This section displays your IP address and other network information.</span></span> <span data-ttu-id="a8d10-283">Pomocí této metody můžete zkopírovat a vložit IP adresu na svém vývojovém počítači.</span><span class="sxs-lookup"><span data-stu-id="a8d10-283">By using this method, you can copy and paste of the IP address on your development PC.</span></span>

## <a name="change-ip-address-to-static-address"></a><span data-ttu-id="a8d10-284">Změnit IP adresu na statickou adresu</span><span class="sxs-lookup"><span data-stu-id="a8d10-284">Change IP Address to static address</span></span>
### <a name="by-using-settings"></a><span data-ttu-id="a8d10-285">Pomocí nastavení</span><span class="sxs-lookup"><span data-stu-id="a8d10-285">By using Settings</span></span>
 
1. <span data-ttu-id="a8d10-286">Otevřete nabídku **Start** .</span><span class="sxs-lookup"><span data-stu-id="a8d10-286">Open the **Start** menu.</span></span>
1. <span data-ttu-id="a8d10-287">V seznamu **starts** ( **všechny aplikace** ) na pravé straně nabídky **Start** vyberte aplikace **Nastavení** .</span><span class="sxs-lookup"><span data-stu-id="a8d10-287">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="a8d10-288">Aplikace **Nastavení** se automaticky umístí před vás.</span><span class="sxs-lookup"><span data-stu-id="a8d10-288">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="a8d10-289">Vyberte **Network & Internet**.</span><span class="sxs-lookup"><span data-stu-id="a8d10-289">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="a8d10-290">Posuňte se dolů k seznamu dostupných Wi-Fi sítí a vyberte **vlastnosti hardwaru**.</span><span class="sxs-lookup"><span data-stu-id="a8d10-290">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>
1. <span data-ttu-id="a8d10-291">V okně **Upravit nastavení protokolu IP** změňte první pole na **Ruční**.</span><span class="sxs-lookup"><span data-stu-id="a8d10-291">In the **Edit IP settings** window, change the first field to **Manual**.</span></span>
1. <span data-ttu-id="a8d10-292">Do zbývajících polí zadejte požadovanou konfiguraci protokolu IP a pak klikněte na **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="a8d10-292">Input the desired IP configuration in the remaining fields and then click **Save**.</span></span>

### <a name="by-using-windows-device-portal"></a><span data-ttu-id="a8d10-293">Pomocí portálu zařízení Windows</span><span class="sxs-lookup"><span data-stu-id="a8d10-293">By using Windows Device Portal</span></span>

1. <span data-ttu-id="a8d10-294">Ve webovém prohlížeči na počítači otevřete [portál zařízení](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span><span class="sxs-lookup"><span data-stu-id="a8d10-294">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="a8d10-295">Přejděte do části **sítě** .</span><span class="sxs-lookup"><span data-stu-id="a8d10-295">Navigate to the **Networking** section.</span></span>
1. <span data-ttu-id="a8d10-296">Vyberte tlačítko **Konfigurace protokolu IPv4** .</span><span class="sxs-lookup"><span data-stu-id="a8d10-296">Select the **IPv4 Configuration** button.</span></span>
1. <span data-ttu-id="a8d10-297">Vyberte **použít následující IP adresu** a zadejte požadovanou konfiguraci protokolu TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="a8d10-297">Select **Use the following IP address** and input the desired TCP/IP configuration.</span></span>
1. <span data-ttu-id="a8d10-298">Vyberte **použít následující adresy serverů DNS** a v případě potřeby zadejte upřednostňovanou a alternativní adresu serveru DNS.</span><span class="sxs-lookup"><span data-stu-id="a8d10-298">Select **Use the following DNS server addresses** and enter the Preferred and Alternate DNS server addresses, if needed.</span></span>
1. <span data-ttu-id="a8d10-299">Klikněte na **Uložit**.</span><span class="sxs-lookup"><span data-stu-id="a8d10-299">Click **Save**.</span></span> 