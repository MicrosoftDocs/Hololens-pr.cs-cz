---
title: Implementace HoloLens 2 a řešení potíží se spravovaným zařízením
description: Řešení potíží s zařízeními HoloLens 2 v podnikovém prostředí
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
ms.openlocfilehash: 911e5b9494eae00ace8007ee6a29b30e6aaf98dd
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961634"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a><span data-ttu-id="be058-104">Řešení potíží s implementací a spravovanými zařízeními</span><span class="sxs-lookup"><span data-stu-id="be058-104">Troubleshooting implementation and managed devices</span></span> 

<span data-ttu-id="be058-105">Tento článek popisuje, jak vyřešit několik problémů nebo zodpovědět otázky týkající se implementace a správy HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="be058-105">This article describes how to resolve several issues or answer questions regarding implementation and management of HoloLens 2.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="be058-106">Než začnete s postupem řešení potíží, ujistěte se, že se na zařízení účtuje **20 až 40 procent** kapacity baterie, pokud je to možné.</span><span class="sxs-lookup"><span data-stu-id="be058-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="be058-107">[Indikátory baterie](hololens2-setup.md#lights-that-indicate-the-battery-level) umístěné pod tlačítkem napájení jsou rychlým způsobem, jak ověřit kapacitu baterie bez přihlášení do zařízení.</span><span class="sxs-lookup"><span data-stu-id="be058-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>


<a id="list"></a>
- [<span data-ttu-id="be058-108">Řešení potíží s protokolem EAP</span><span class="sxs-lookup"><span data-stu-id="be058-108">EAP Troubleshooting</span></span>](#eap-troubleshooting)
- [<span data-ttu-id="be058-109">Řešení potíží Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="be058-109">Wi-Fi Troubleshooting</span></span>](#wi-fi-troubleshooting)
- [<span data-ttu-id="be058-110">Řešení potíží se sítí</span><span class="sxs-lookup"><span data-stu-id="be058-110">Network Troubleshooting</span></span>](#network-troubleshooting)
- [<span data-ttu-id="be058-111">Nejde se přihlásit k dřív nastavenému zařízení HoloLens.</span><span class="sxs-lookup"><span data-stu-id="be058-111">Can't sign in to a previously setup HoloLens device</span></span>](#cant-sign-in-to-a-previously-setup-hololens-device)
- [<span data-ttu-id="be058-112">Po aktualizaci na holografickou 21H1 se nedá přihlásit.</span><span class="sxs-lookup"><span data-stu-id="be058-112">Can't login after updating to Windows Holographic 21H1</span></span>](#cant-login-after-updating-to-windows-holographic-21h1)
- [<span data-ttu-id="be058-113">Řešení potíží s autopilotem</span><span class="sxs-lookup"><span data-stu-id="be058-113">Autopilot Troubleshooting</span></span>](#autopilot-troubleshooting)
- [<span data-ttu-id="be058-114">Nejčastější dotazy ke spravovaným zařízením HoloLens</span><span class="sxs-lookup"><span data-stu-id="be058-114">Managed HoloLens Devices FAQs</span></span>](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a><span data-ttu-id="be058-115">Řešení potíží s protokolem EAP</span><span class="sxs-lookup"><span data-stu-id="be058-115">EAP Troubleshooting</span></span>
1. <span data-ttu-id="be058-116">Dvojitá check Wi-Fi profil má správné nastavení:</span><span class="sxs-lookup"><span data-stu-id="be058-116">Double check Wi-Fi profile has right settings:</span></span>
    - <span data-ttu-id="be058-117">Typ protokolu EAP je správně nakonfigurovaný, běžné typy protokolu EAP: EAP-TLS (13), EAP-TTLS (21) a PEAP (25).</span><span class="sxs-lookup"><span data-stu-id="be058-117">EAP type is configured correctly, common EAP types: EAP-TLS (13), EAP-TTLS (21) and PEAP (25).</span></span>
    - <span data-ttu-id="be058-118">Název SSID Wi-Fi je vpravo a odpovídá řetězci HEX.</span><span class="sxs-lookup"><span data-stu-id="be058-118">Wi-Fi SSID name is right and matches with HEX string.</span></span>
    - <span data-ttu-id="be058-119">Pro EAP-TLS obsahuje TrustedRootCA hodnotu hash SHA-1 certifikátu důvěryhodné kořenové certifikační autority serveru.</span><span class="sxs-lookup"><span data-stu-id="be058-119">For EAP-TLS, TrustedRootCA contains the SHA-1 hash of server's trusted root CA certificate.</span></span> <span data-ttu-id="be058-120">V počítači s Windows "certutil.exe-dump cert_file_name" příkaz zobrazí řetězec hash SHA-1 certifikátu.</span><span class="sxs-lookup"><span data-stu-id="be058-120">On Windows PC "certutil.exe -dump cert_file_name" command will show a certificate's SHA-1 hash string.</span></span>
2. <span data-ttu-id="be058-121">Shromažďovat Zachytávání síťových paketů v protokolech přístupového bodu nebo řadiči serveru AAA, kde zjistíte, kde se relace protokolu EAP nezdařila.</span><span class="sxs-lookup"><span data-stu-id="be058-121">Collect network packet capture on the Access Point or Controller or AAA server logs to find out where the EAP session fails.</span></span>
    - <span data-ttu-id="be058-122">Pokud není očekávána Identita protokolu EAP poskytovaná pomocí HoloLens, ověřte, zda byla identita správně zajištěna prostřednictvím profilu Wi-Fi nebo klientského certifikátu.</span><span class="sxs-lookup"><span data-stu-id="be058-122">If the EAP identity provided by HoloLens is not expected, check whether the identity has been correctly provisioned through Wi-Fi profile or client certificate.</span></span>
    - <span data-ttu-id="be058-123">Pokud server odmítne klientský certifikát HoloLens, ověřte, jestli je na zařízení požadovaný klientský certifikát zřízený.</span><span class="sxs-lookup"><span data-stu-id="be058-123">If server rejects HoloLens client certificate, check whether the required client certificate has been provisioned on the device.</span></span>
    - <span data-ttu-id="be058-124">Pokud HoloLens odmítne certifikát serveru, ověřte, jestli je certifikát kořenové certifikační autority serveru zřízený na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="be058-124">If HoloLens rejects server certificate, check if the server root CA certificate has been provisioned on HoloLens.</span></span>
3. <span data-ttu-id="be058-125">Pokud se profil Enterprise zřídí prostřednictvím balíčku pro Wi-Fi zřizování, zvažte použití zřizovacího balíčku na počítači s Windows 10.</span><span class="sxs-lookup"><span data-stu-id="be058-125">If the enterprise profile is provisioned through Wi-Fi provisioning package, consider applying the provisioning package on a Windows 10 PC.</span></span> <span data-ttu-id="be058-126">Pokud se to nepovede i na počítači s Windows 10, postupujte podle Průvodce odstraňováním potíží s ověřováním klienta ve Windows 802.1 X.</span><span class="sxs-lookup"><span data-stu-id="be058-126">If it also fails on Windows 10 PC, follow the Windows client 802.1X authentication troubleshooting guide.</span></span>
4. <span data-ttu-id="be058-127">Pošlete nám svůj názor prostřednictvím centra zpětné vazby.</span><span class="sxs-lookup"><span data-stu-id="be058-127">Send us feedback through Feedback Hub.</span></span>

[<span data-ttu-id="be058-128">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="be058-128">Back to list</span></span>](#list)

## <a name="wi-fi-troubleshooting"></a><span data-ttu-id="be058-129">Řešení potíží s Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="be058-129">Wi-Fi Troubleshooting</span></span>

<span data-ttu-id="be058-130">Tady je několik věcí, které můžete vyzkoušet, pokud nemůžete připojit svoji HoloLens k Wi-Fi síti:</span><span class="sxs-lookup"><span data-stu-id="be058-130">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

1. <span data-ttu-id="be058-131">Ujistěte se, že je zapnutá Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="be058-131">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="be058-132">Chcete-li kontrolu ověřit, použijte gesto Start a pak vyberte nastavení > síť & Internet > Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="be058-132">To check, use the Start gesture, then select Settings > Network & Internet > Wi-Fi.</span></span> <span data-ttu-id="be058-133">Pokud je Wi-Fi zapnutá, zkuste ji vypnout a znovu zapnout.</span><span class="sxs-lookup"><span data-stu-id="be058-133">If Wi-Fi is on, try turning it off and then on again.</span></span>
2. <span data-ttu-id="be058-134">Posuňte se blíž ke směrovači nebo přístupovému bodu.</span><span class="sxs-lookup"><span data-stu-id="be058-134">Move closer to the router or access point.</span></span>
3. <span data-ttu-id="be058-135">Restartujte směrovač Wi-Fi a pak restartujte HoloLens.</span><span class="sxs-lookup"><span data-stu-id="be058-135">Restart your Wi-Fi router, then restart HoloLens.</span></span> <span data-ttu-id="be058-136">Zkuste se znovu připojit.</span><span class="sxs-lookup"><span data-stu-id="be058-136">Try connecting again.</span></span>
4. <span data-ttu-id="be058-137">Pokud žádná z těchto věcí nefunguje, zkontrolujte, zda směrovač používá nejnovější firmware.</span><span class="sxs-lookup"><span data-stu-id="be058-137">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="be058-138">Tyto informace najdete na webu výrobce.</span><span class="sxs-lookup"><span data-stu-id="be058-138">You can find this information on the manufacturer website.</span></span>

<span data-ttu-id="be058-139">Když se na zařízení přihlašujete k podnikovému nebo organizačnímu účtu, může taky použít zásady správy mobilních zařízení (MDM), pokud je zásada nakonfigurovaná správcem IT.</span><span class="sxs-lookup"><span data-stu-id="be058-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <a name="network-troubleshooting"></a><span data-ttu-id="be058-140">Řešení potíží se sítí</span><span class="sxs-lookup"><span data-stu-id="be058-140">Network Troubleshooting</span></span>
<span data-ttu-id="be058-141">Pokud jsou problémy se sítí překážkou úspěšného nasazení a používání HoloLens 2 ve vaší organizaci, přečtěte si, jak vám dva dobře známé nástroje pro diagnostiku sítě, Fiddler a Wireshark můžou pomoci při prohledávání, diagnostice a identifikaci problémů.</span><span class="sxs-lookup"><span data-stu-id="be058-141">If network issues are an obstacle to successfully deploying and using HoloLens 2 in your organization, learn how two well-known network diagnostic tools, Fiddler and Wireshark can help you scan, diagnose, and identify problems.</span></span> <span data-ttu-id="be058-142">Další podrobnosti najdete na tomto [blogu](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) .</span><span class="sxs-lookup"><span data-stu-id="be058-142">Check out this [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) for more details.</span></span>

[<span data-ttu-id="be058-143">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="be058-143">Back to list</span></span>](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a><span data-ttu-id="be058-144">Nejde se přihlásit k dřív nastavenému zařízení HoloLens.</span><span class="sxs-lookup"><span data-stu-id="be058-144">Can't sign in to a previously setup HoloLens device</span></span>

<span data-ttu-id="be058-145">Pokud jste zařízení dříve nastavili pro někoho jiného, buď pro klienta, nebo pro bývalého zaměstnance, a nemáte heslo k odemknutí zařízení, můžete pomocí Intune vzdáleně [Vymazat](https://docs.microsoft.com/intune/remote-actions/devices-wipe) zařízení.</span><span class="sxs-lookup"><span data-stu-id="be058-145">If your device was previously set up for someone else, either for a client or for a former employee, and you don't have their password to unlock the device, you can use Intune to remotely [wipe](https://docs.microsoft.com/intune/remote-actions/devices-wipe) the device.</span></span> <span data-ttu-id="be058-146">Zařízení se pak znovu zabliká.</span><span class="sxs-lookup"><span data-stu-id="be058-146">The device then re-flashes itself.</span></span>  
> [!IMPORTANT]
> <span data-ttu-id="be058-147">Když zařízení vymažete, nezapomeňte ponechat **stav registrace a účet uživatele** nezaškrtnutý.</span><span class="sxs-lookup"><span data-stu-id="be058-147">When you wipe the device, make sure to leave **Retain enrollment state and user account** unchecked.</span></span>
[<span data-ttu-id="be058-148">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="be058-148">Back to list</span></span>](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a><span data-ttu-id="be058-149">Po aktualizaci na holografickou 21H1 se nedá přihlásit.</span><span class="sxs-lookup"><span data-stu-id="be058-149">Can't login after updating to Windows Holographic 21H1</span></span>

### <a name="symptoms"></a><span data-ttu-id="be058-150">Příznaky</span><span class="sxs-lookup"><span data-stu-id="be058-150">Symptoms</span></span>
- <span data-ttu-id="be058-151">Po zadání správného kódu PIN se přihlášení pomocí kódu PIN nezdaří.</span><span class="sxs-lookup"><span data-stu-id="be058-151">Using PIN to logon will fail after entering the correct PIN.</span></span>
- <span data-ttu-id="be058-152">Po úspěšném přihlášení na webové stránce se použití metody přihlášení k webu nezdaří.</span><span class="sxs-lookup"><span data-stu-id="be058-152">Using the web logon method will fail after successfully signing in on the web page.</span></span>
- <span data-ttu-id="be058-153">Zařízení není uvedené jako "Azure AD JOIN" v [Azure Portal](https://portal.azure.com/) > zařízení Azure Active Directory >.</span><span class="sxs-lookup"><span data-stu-id="be058-153">The device is not listed as “Azure AD joined” in [Azure portal](https://portal.azure.com/) -> Azure Active Directory -> Devices.</span></span>

### <a name="cause"></a><span data-ttu-id="be058-154">Příčina</span><span class="sxs-lookup"><span data-stu-id="be058-154">Cause</span></span>
<span data-ttu-id="be058-155">Ovlivněné zařízení mohlo být odstraněno z tenanta Azure AD.</span><span class="sxs-lookup"><span data-stu-id="be058-155">The impacted device may have been deleted from the Azure AD tenant.</span></span> <span data-ttu-id="be058-156">K tomu může dojít například z těchto důvodů:</span><span class="sxs-lookup"><span data-stu-id="be058-156">For example, this may happen because:</span></span>

- <span data-ttu-id="be058-157">Správce nebo uživatel zařízení odstranil v Azure Portal nebo pomocí PowerShellu.</span><span class="sxs-lookup"><span data-stu-id="be058-157">An administrator or user deleted the device in the Azure portal or using PowerShell.</span></span>
- <span data-ttu-id="be058-158">Zařízení se odebralo z tenanta Azure AD kvůli nečinnosti.</span><span class="sxs-lookup"><span data-stu-id="be058-158">The device was removed from the Azure AD tenant due to inactivity.</span></span> <span data-ttu-id="be058-159">Pro efektivní spravované prostředí typicky doporučujeme správcům IT [odebírat ze svého tenanta Azure AD zastaralé neaktivní zařízení](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices).</span><span class="sxs-lookup"><span data-stu-id="be058-159">For an efficiently managed environment, we typically recommend IT admins to [remove stale, inactive devices from their Azure AD tenant](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices).</span></span>

<span data-ttu-id="be058-160">Když se zasažené zařízení pokusí kontaktovat tenanta Azure AD znovu po jeho odstranění, nepodaří se mu ověřit pomocí Azure AD.</span><span class="sxs-lookup"><span data-stu-id="be058-160">When an impacted device attempts to contact the Azure AD tenant again after it has been deleted it will fail to authenticate with Azure AD.</span></span> <span data-ttu-id="be058-161">Tento efekt je často neviditelný pro uživatele zařízení, protože přihlášení do mezipaměti prostřednictvím kódu PIN bude dál umožňovat přihlášení uživatele.</span><span class="sxs-lookup"><span data-stu-id="be058-161">This effect is often invisible to the user of the device, as cached logon via PIN will continue to allow the user to logon.</span></span>

### <a name="mitigation"></a><span data-ttu-id="be058-162">Omezení rizik</span><span class="sxs-lookup"><span data-stu-id="be058-162">Mitigation</span></span>
<span data-ttu-id="be058-163">V současné době neexistuje způsob, jak přidat odstraněné zařízení HoloLens zpátky do služby Azure AD.</span><span class="sxs-lookup"><span data-stu-id="be058-163">There is currently no way to add a deleted HoloLens device back into Azure AD.</span></span> <span data-ttu-id="be058-164">Ovlivněná zařízení bude potřeba vyčistit, a to podle pokynů při [přeblikání zařízení](hololens-recovery.md#clean-reflash-the-device).</span><span class="sxs-lookup"><span data-stu-id="be058-164">Affected devices will need to be clean-reflashed by following the instructions on [reflashing their device](hololens-recovery.md#clean-reflash-the-device).</span></span>

## <a name="autopilot-troubleshooting"></a><span data-ttu-id="be058-165">Řešení potíží s autopilotem</span><span class="sxs-lookup"><span data-stu-id="be058-165">Autopilot Troubleshooting</span></span>

<span data-ttu-id="be058-166">Následující články můžou být užitečným prostředkem, abyste si mohli přečíst další informace a řešit problémy s výkonem pro autopilot, ale pamatujte na to, že tyto články jsou založené na Windows 10 desktopu a ne všechny informace se můžou vztahovat na HoloLens:</span><span class="sxs-lookup"><span data-stu-id="be058-166">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>

- [<span data-ttu-id="be058-167">Windows autopilot – známé problémy</span><span class="sxs-lookup"><span data-stu-id="be058-167">Windows Autopilot - known issues</span></span>](https://docs.microsoft.com/mem/autopilot/known-issues)
- [<span data-ttu-id="be058-168">Řešení potíží s registrací zařízení s Windows v Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="be058-168">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="be058-169">Windows autopilot – konflikty zásad</span><span class="sxs-lookup"><span data-stu-id="be058-169">Windows Autopilot - Policy Conflicts</span></span>](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <a name="managed-hololens-devices-faqs"></a><span data-ttu-id="be058-170">Nejčastější dotazy ke spravovaným zařízením HoloLens</span><span class="sxs-lookup"><span data-stu-id="be058-170">Managed HoloLens Devices FAQs</span></span>

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a><span data-ttu-id="be058-171">Můžu pomocí System Center Configuration Manager (SCCM) spravovat zařízení HoloLens?</span><span class="sxs-lookup"><span data-stu-id="be058-171">Can I use System Center Configuration Manager (SCCM) to manage HoloLens devices?</span></span>

<span data-ttu-id="be058-172">No.</span><span class="sxs-lookup"><span data-stu-id="be058-172">No.</span></span> <span data-ttu-id="be058-173">Ke správě zařízení HoloLens je nutné použít systém MDM.</span><span class="sxs-lookup"><span data-stu-id="be058-173">You have to use an MDM system to manage HoloLens devices.</span></span>

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a><span data-ttu-id="be058-174">Můžu k správě uživatelských účtů HoloLens použít Active Directory Domain Services (služba AD DS)?</span><span class="sxs-lookup"><span data-stu-id="be058-174">Can I use Active Directory Domain Services (AD DS) to manage HoloLens user accounts?</span></span>

<span data-ttu-id="be058-175">No.</span><span class="sxs-lookup"><span data-stu-id="be058-175">No.</span></span> <span data-ttu-id="be058-176">K řízení uživatelských účtů pro zařízení HoloLens je nutné použít Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="be058-176">You have to use Azure Active Directory (Azure AD) to manage user accounts for HoloLens devices.</span></span>

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a><span data-ttu-id="be058-177">Podporuje automatické registrace systému HoloLens (Automated data Capture)?</span><span class="sxs-lookup"><span data-stu-id="be058-177">Is HoloLens capable of Automated Data Capture Systems (ADCS) auto-enrollment?</span></span>

<span data-ttu-id="be058-178">No.</span><span class="sxs-lookup"><span data-stu-id="be058-178">No.</span></span>

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a><span data-ttu-id="be058-179">Je možné použít HoloLens v integrovaném ověřování systému Windows?</span><span class="sxs-lookup"><span data-stu-id="be058-179">Can HoloLens participate in Integrated Windows Authentication?</span></span>

<span data-ttu-id="be058-180">No.</span><span class="sxs-lookup"><span data-stu-id="be058-180">No.</span></span>

### <a name="does-hololens-support-branding"></a><span data-ttu-id="be058-181">Podporuje HoloLens pracovní značku?</span><span class="sxs-lookup"><span data-stu-id="be058-181">Does HoloLens support branding?</span></span>

<span data-ttu-id="be058-182">No.</span><span class="sxs-lookup"><span data-stu-id="be058-182">No.</span></span> <span data-ttu-id="be058-183">Tento problém ale můžete obejít pomocí jednoho z následujících přístupů:</span><span class="sxs-lookup"><span data-stu-id="be058-183">However, you can work around this issue by using one of the following approaches:</span></span>

- <span data-ttu-id="be058-184">Vytvořte vlastní aplikaci a pak [Povolte celoobrazovkový režim](hololens-kiosk.md).</span><span class="sxs-lookup"><span data-stu-id="be058-184">Create a custom app, and then [enable Kiosk mode](hololens-kiosk.md).</span></span> <span data-ttu-id="be058-185">Vlastní aplikace může mít branding a může spouštět jiné aplikace (například vzdálenou pomoc).</span><span class="sxs-lookup"><span data-stu-id="be058-185">The custom app can have branding, and can launch other apps (such as Remote Assist).</span></span>  
- <span data-ttu-id="be058-186">Změňte všechny obrázky profilů uživatelů ve službě Azure AD na logo vaší společnosti.</span><span class="sxs-lookup"><span data-stu-id="be058-186">Change all of the user profile pictures in Azure AD to your company logo.</span></span> <span data-ttu-id="be058-187">To však nemusí být žádoucí pro všechny scénáře.</span><span class="sxs-lookup"><span data-stu-id="be058-187">However, this may not be desirable for all scenarios.</span></span>

### <a name="what-logging-capabilities-does-hololens-2-offer"></a><span data-ttu-id="be058-188">Jaké možnosti protokolování nabízí možnost HoloLens 2?</span><span class="sxs-lookup"><span data-stu-id="be058-188">What logging capabilities does HoloLens 2 offer?</span></span>

<span data-ttu-id="be058-189">Protokolování je omezené na trasování, která se dají zachytit ve scénářích vývoje nebo řešení potíží, nebo telemetrie, kterou zařízení odesílají na servery Microsoftu.</span><span class="sxs-lookup"><span data-stu-id="be058-189">Logging is limited to traces that can be captured in development or troubleshooting scenarios, or telemetry that the devices send to Microsoft servers.</span></span>

## <a name="questions-about-securing-hololens-devices"></a><span data-ttu-id="be058-190">Dotazy týkající se zabezpečení zařízení HoloLens</span><span class="sxs-lookup"><span data-stu-id="be058-190">Questions about securing HoloLens devices</span></span>

<span data-ttu-id="be058-191">Podívejte se na [informace o zabezpečení HoloLens 2](security-overview.md).</span><span class="sxs-lookup"><span data-stu-id="be058-191">See [our HoloLens 2 security information](security-overview.md).</span></span>
<span data-ttu-id="be058-192">V případě HoloLens 1 pro obecné zařízení si přečtěte [Tyto nejčastější dotazy](hololens1-faq-security.md).</span><span class="sxs-lookup"><span data-stu-id="be058-192">For HoloLens 1st Gen devices please review [this FAQ](hololens1-faq-security.md).</span></span>

[<span data-ttu-id="be058-193">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="be058-193">Back to list</span></span>](#list)
