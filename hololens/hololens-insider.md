---
title: Insider preview pro Microsoft HoloLens
description: Zjistěte, jak začít se sestaveními Insider a poskytnout cennou zpětnou vazbu pro naši další velkou aktualizaci operačního systému pro HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: a4949ab68121cb772fdb8a62411ed70868a6ccb6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924362"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="2a68f-103">Insider preview pro Microsoft HoloLens</span><span class="sxs-lookup"><span data-stu-id="2a68f-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="2a68f-104">Vítá vás nejnovější sestavení Insider Preview pro HoloLens!</span><span class="sxs-lookup"><span data-stu-id="2a68f-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="2a68f-105">Začít a poskytnout [cennou zpětnou vazbu](hololens-insider.md#start-receiving-insider-builds) pro naši další velkou aktualizaci operačního systému pro HoloLens je jednoduché.</span><span class="sxs-lookup"><span data-stu-id="2a68f-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="2a68f-106">Windows Insider k vydání verze</span><span class="sxs-lookup"><span data-stu-id="2a68f-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="2a68f-107">S radostí můžeme znovu začít přechádovat nové funkce do programu Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="2a68f-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="2a68f-108">Nové buildy budou uchytát se do kanálů pro vývoj a beta verze a budou dostávat nejnovější aktualizace.</span><span class="sxs-lookup"><span data-stu-id="2a68f-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="2a68f-109">Tuto stránku budeme dál aktualizovat, jakmile do našich buildů přidáme další funkce a Windows Insider aktualizace.</span><span class="sxs-lookup"><span data-stu-id="2a68f-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="2a68f-110">Připravte se na kombinaci těchto aktualizací do vaší reality.</span><span class="sxs-lookup"><span data-stu-id="2a68f-110">Get excited and ready to mix these updates into your reality.</span></span> 

### <a name="csp-changes-on-hololens"></a><span data-ttu-id="2a68f-111">Změny CSP na HoloLens</span><span class="sxs-lookup"><span data-stu-id="2a68f-111">CSP changes on HoloLens</span></span>
 
- <span data-ttu-id="2a68f-112">Zavedeno v Windows Insider buildu, 20348.1403</span><span class="sxs-lookup"><span data-stu-id="2a68f-112">Introduced in Windows Insider build, 20348.1403</span></span>

#### <a name="devdetail-csp"></a><span data-ttu-id="2a68f-113">DevDetail CSP</span><span class="sxs-lookup"><span data-stu-id="2a68f-113">DevDetail CSP</span></span>

<span data-ttu-id="2a68f-114">DevDetail CSP teď také hlásí volné místo úložiště na zařízení HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2a68f-114">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="2a68f-115">Tato hodnota by se měla přibližně shodovat s hodnotou zobrazenou na stránce Úložiště aplikace Nastavení.</span><span class="sxs-lookup"><span data-stu-id="2a68f-115">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="2a68f-116">Následuje konkrétní uzel, který obsahuje tyto informace.</span><span class="sxs-lookup"><span data-stu-id="2a68f-116">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="2a68f-117">./DevDetail/Ext/Microsoft/FreeStorage (pouze operace GET)</span><span class="sxs-lookup"><span data-stu-id="2a68f-117">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp"></a><span data-ttu-id="2a68f-118">DeviceStatus CSP</span><span class="sxs-lookup"><span data-stu-id="2a68f-118">DeviceStatus CSP</span></span>

<span data-ttu-id="2a68f-119">DeviceStatus CSP teď také hlásí SSID a BSSID wi-fi sítě, se kterou je HoloLens aktivně připojený.</span><span class="sxs-lookup"><span data-stu-id="2a68f-119">DeviceStatus CSP now also reports SSID and BSSID of Wifi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="2a68f-120">Níže jsou uvedené konkrétní uzly, které obsahují tyto informace.</span><span class="sxs-lookup"><span data-stu-id="2a68f-120">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="2a68f-121">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*adresa mac Wi-Fi adaptéru*/SSID</span><span class="sxs-lookup"><span data-stu-id="2a68f-121">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="2a68f-122">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*adresa MAC Wi-Fi adaptéru*/BSSID</span><span class="sxs-lookup"><span data-stu-id="2a68f-122">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="2a68f-123">Příklad objektu blob syncml (pro dodavatele MDM) pro dotazování na NetworkIdentifiers</span><span class="sxs-lookup"><span data-stu-id="2a68f-123">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="fixes-and-improvements"></a><span data-ttu-id="2a68f-124">Opravy a vylepšení:</span><span class="sxs-lookup"><span data-stu-id="2a68f-124">Fixes and improvements:</span></span>

- <span data-ttu-id="2a68f-125">Byl opraven známý problém pro Portál zařízení, kdy se při stahování uzamčených souborů nic [nestahuje.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="2a68f-125">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="2a68f-126">Opravili [jsme známý problém s Portál zařízení s časovými limity nahrávání a stahování souborů.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span><span class="sxs-lookup"><span data-stu-id="2a68f-126">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>

## <a name="start-receiving-insider-builds"></a><span data-ttu-id="2a68f-127">Zahájení přijímání sestavení Insider</span><span class="sxs-lookup"><span data-stu-id="2a68f-127">Start receiving Insider builds</span></span>
> [!NOTE]
> <span data-ttu-id="2a68f-128">Pokud jste to ještě neudělali, restartujte zařízení, aktualizujte stav a získejte nejnovější build.</span><span class="sxs-lookup"><span data-stu-id="2a68f-128">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="2a68f-129">Hlasový příkaz Restartovat zařízení funguje dobře.</span><span class="sxs-lookup"><span data-stu-id="2a68f-129">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="2a68f-130">Můžete také zvolit tlačítko restartovat v Nastavení/Program Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="2a68f-130">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="2a68f-131">Na back-endu jsme měli chybu, se kterou jste se mohli setkat, a tím se vrátíte na cestu.</span><span class="sxs-lookup"><span data-stu-id="2a68f-131">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="2a68f-132">Na zařízení HoloLens 2 přejděte na **Nastavení**  >  **Aktualizace & Security**  >  **Program Windows Insider** a vyberte **Začínáme.**</span><span class="sxs-lookup"><span data-stu-id="2a68f-132">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="2a68f-133">Propojte účet, který jste použili k registraci, jako Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="2a68f-133">Link the account you used to register as a Windows Insider.</span></span>
<span data-ttu-id="2a68f-134">Windows Insider se teď přesouvá na Kanály.</span><span class="sxs-lookup"><span data-stu-id="2a68f-134">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="2a68f-135">Kanál **Fast** se stane **vývojový** kanál, kanál **Slow** se stane **kanálem Beta kanál** a kanál release **preview** se stane **kanálem Release Preview**.</span><span class="sxs-lookup"><span data-stu-id="2a68f-135">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="2a68f-136">Toto mapování vypadá takhle: Windows Insider vysvětlení kanálů Další informace najdete v tématu Představení kanálů Windows Insider ![ ](images/WindowsInsiderChannels.png) [na](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) blozích Windows.</span><span class="sxs-lookup"><span data-stu-id="2a68f-136">Here is what that mapping looks like: ![Windows Insider Channels explanation](images/WindowsInsiderChannels.png) For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="2a68f-137">Pak vyberte **Aktivní vývoj Windows,** zvolte, jestli chcete dostávat Dev **Channel** nebo Beta kanál **buildy,** a zkontrolujte podmínky programu.</span><span class="sxs-lookup"><span data-stu-id="2a68f-137">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="2a68f-138">Dokončete **> Potvrdit a** restartovat.</span><span class="sxs-lookup"><span data-stu-id="2a68f-138">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="2a68f-139">Po restartování zařízení přejděte na Nastavení > **Update & Security >** Vyhledejte aktualizace a získejte nejnovější build.</span><span class="sxs-lookup"><span data-stu-id="2a68f-139">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>
### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="2a68f-140">Aktualizace 0x80070490 obchádky</span><span class="sxs-lookup"><span data-stu-id="2a68f-140">Update error 0x80070490 work-around</span></span>
<span data-ttu-id="2a68f-141">Pokud při aktualizaci na kanálu pro 0x80070490 nebo beta verzi dojde k chybě aktualizace, vyzkoušejte následující krátkodobé řešení.</span><span class="sxs-lookup"><span data-stu-id="2a68f-141">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="2a68f-142">Zahrnuje přesunutí kanálu insider, vyzvednutí aktualizace a pak přesunutí kanálu Insider zpět.</span><span class="sxs-lookup"><span data-stu-id="2a68f-142">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>
#### <a name="stage-one---release-preview"></a><span data-ttu-id="2a68f-143">Fáze 1 – Verze Preview</span><span class="sxs-lookup"><span data-stu-id="2a68f-143">Stage one - Release Preview</span></span>
1.  <span data-ttu-id="2a68f-144">Settings, Update & Security, Program Windows Insider vyberte **Release Preview Channel**.</span><span class="sxs-lookup"><span data-stu-id="2a68f-144">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>
2.  <span data-ttu-id="2a68f-145">Settings, Update & Security, služba Windows Update, **Check for updates**.</span><span class="sxs-lookup"><span data-stu-id="2a68f-145">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="2a68f-146">Po aktualizaci pokračujte k fázi 2.</span><span class="sxs-lookup"><span data-stu-id="2a68f-146">After the update, continue on to Stage two.</span></span>
#### <a name="stage-two---dev-channel"></a><span data-ttu-id="2a68f-147">Fáze 2 – Vývojový kanál</span><span class="sxs-lookup"><span data-stu-id="2a68f-147">Stage two - Dev Channel</span></span>
1. <span data-ttu-id="2a68f-148">Settings(Nastavení), Update & Security (Zabezpečení Program Windows Insider) a vyberte **Dev Channel (Vývojový kanál).**</span><span class="sxs-lookup"><span data-stu-id="2a68f-148">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>
2. <span data-ttu-id="2a68f-149">Settings, Update & Security, služba Windows Update, **Check for updates**.</span><span class="sxs-lookup"><span data-stu-id="2a68f-149">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>
## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="2a68f-150">Pokyny ke stažení ffu a flash</span><span class="sxs-lookup"><span data-stu-id="2a68f-150">FFU download and flash directions</span></span>
<span data-ttu-id="2a68f-151">Pokud chcete testovat pomocí ffu podepsaného letem, musíte nejprve letět s odemknutým zařízením před flash flash diskem ffu.</span><span class="sxs-lookup"><span data-stu-id="2a68f-151">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="2a68f-152">Na počítači:</span><span class="sxs-lookup"><span data-stu-id="2a68f-152">On PC:</span></span>
    1. <span data-ttu-id="2a68f-153">Stáhněte si ffu do počítače z [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .</span><span class="sxs-lookup"><span data-stu-id="2a68f-153">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="2a68f-154">Nainstalujte ARC (Advanced Recovery Companion) z Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .</span><span class="sxs-lookup"><span data-stu-id="2a68f-154">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="2a68f-155">Na HoloLens – Letové odemčení: **Otevřete** Nastavení Aktualizace &  >  **Security**  >  **Program Windows Insider** a pak se zaregistrujte a restartujte zařízení.</span><span class="sxs-lookup"><span data-stu-id="2a68f-155">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>
1. <span data-ttu-id="2a68f-156">Flash FFU – Nyní můžete flash diskem podepsaného letem FFU použít ARC.</span><span class="sxs-lookup"><span data-stu-id="2a68f-156">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>
### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="2a68f-157">Poskytnutí zpětné vazby a hlášení problémů</span><span class="sxs-lookup"><span data-stu-id="2a68f-157">Provide feedback and report issues</span></span>
<span data-ttu-id="2a68f-158">Pokud chcete [poskytnout zpětnou vazbu Centrum Feedback nahlásit](hololens-feedback.md) problémy, použijte prosím aplikaci pro Centrum Feedback na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2a68f-158">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="2a68f-159">Pomocí Centrum Feedback zajistíte, že se zahrnou všechny potřebné diagnostické informace, které našim technikům pomůžou rychle ladit a vyřešit problém.</span><span class="sxs-lookup"><span data-stu-id="2a68f-159">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="2a68f-160">Problémy s čínštinou a japonštinou holoLens by se měly hlásit stejným způsobem.</span><span class="sxs-lookup"><span data-stu-id="2a68f-160">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>
> [!NOTE]
> <span data-ttu-id="2a68f-161">Nezapomeňte přijmout výzvu s dotazem, jestli Centrum Feedback přístup ke složce  Dokumenty (po zobrazení výzvy vyberte Ano).</span><span class="sxs-lookup"><span data-stu-id="2a68f-161">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>
## <a name="note-for-developers"></a><span data-ttu-id="2a68f-162">Poznámka pro vývojáře</span><span class="sxs-lookup"><span data-stu-id="2a68f-162">Note for developers</span></span>
<span data-ttu-id="2a68f-163">Vítá vás a doporučujeme, abyste si zkusili vyvíjet aplikace pomocí sestavení Insider pro HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2a68f-163">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="2a68f-164">Pokud chcete začít, podívejte se do dokumentace pro vývojáře [HoloLens.](https://developer.microsoft.com/windows/mixed-reality/development)</span><span class="sxs-lookup"><span data-stu-id="2a68f-164">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="2a68f-165">Stejné pokyny fungují i se sestaveními Insider pro HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2a68f-165">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="2a68f-166">Můžete použít stejná sestavení Unity a Visual Studio, které už používáte pro vývoj pro HoloLens.</span><span class="sxs-lookup"><span data-stu-id="2a68f-166">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>
## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="2a68f-167">Zastavení přijímání sestavení Insider</span><span class="sxs-lookup"><span data-stu-id="2a68f-167">Stop receiving Insider builds</span></span>
<span data-ttu-id="2a68f-168">Pokud už nechcete dostávat buildy Insider systému Windows Holographic, můžete to vyjádřit výslovně, když [](hololens-recovery.md) HoloLens používá produkční build, nebo můžete obnovit zařízení pomocí doplňku Advanced Recovery Companion a obnovit zařízení na verzi Windows Holographic, která není součástí programu Insider.</span><span class="sxs-lookup"><span data-stu-id="2a68f-168">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>
> [!CAUTION]
> <span data-ttu-id="2a68f-169">Existuje známý problém, kdy se uživatelům, kteří po ruční přeinstalaci nové verze Preview buildu ruší registraci ve verzi Insider Preview, zobrazí modrá obrazovka.</span><span class="sxs-lookup"><span data-stu-id="2a68f-169">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="2a68f-170">Potom musí zařízení obnovit ručně.</span><span class="sxs-lookup"><span data-stu-id="2a68f-170">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="2a68f-171">Úplné podrobnosti o tom, jestli by vás to ovlivnilo nebo ne, najdete v části Další informace o tomto [známém problému.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)</span><span class="sxs-lookup"><span data-stu-id="2a68f-171">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>
<span data-ttu-id="2a68f-172">Ověření, že HoloLens používá produkční sestavení:</span><span class="sxs-lookup"><span data-stu-id="2a68f-172">To verify that your HoloLens is running a production build:</span></span>
1. <span data-ttu-id="2a68f-173">Přejděte na **Nastavení > System > About (O aplikaci) a** vyhledejte číslo sestavení.</span><span class="sxs-lookup"><span data-stu-id="2a68f-173">Go to **Settings > System > About**, and find the build number.</span></span>
1. <span data-ttu-id="2a68f-174">[Podívejte se na poznámky k verzi pro čísla produkčních buildů](hololens-release-notes.md).</span><span class="sxs-lookup"><span data-stu-id="2a68f-174">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>
<span data-ttu-id="2a68f-175">Odhlášení sestavení Insider:</span><span class="sxs-lookup"><span data-stu-id="2a68f-175">To opt out of Insider builds:</span></span>
1. <span data-ttu-id="2a68f-176">V HoloLens, na které běží produkční sestavení, přejděte na Nastavení **> Update & Security > Program Windows Insider** a vyberte Zastavit sestavení **Insider.**</span><span class="sxs-lookup"><span data-stu-id="2a68f-176">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>
1. <span data-ttu-id="2a68f-177">Postupujte podle pokynů a odhlásit zařízení.</span><span class="sxs-lookup"><span data-stu-id="2a68f-177">Follow the instructions to opt out your device.</span></span>
