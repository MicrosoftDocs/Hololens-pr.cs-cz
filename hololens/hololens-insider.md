---
title: Insider Preview pro Microsoft HoloLens
description: Naučte se, jak začít se sestavami Insider a poskytnout cennou zpětnou vazbu k naší další hlavní aktualizaci operačního systému pro HoloLens.
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
ms.openlocfilehash: 8b8c3c26ff743a4df0010110d0fe6e2930646c86
ms.sourcegitcommit: add53aa73588986a3430cdc0310af7665a038cfc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/26/2021
ms.locfileid: "112977223"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="1a8d9-103">Insider Preview pro Microsoft HoloLens</span><span class="sxs-lookup"><span data-stu-id="1a8d9-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="1a8d9-104">Vítejte v nejnovějších buildech Insider Preview pro HoloLens!</span><span class="sxs-lookup"><span data-stu-id="1a8d9-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="1a8d9-105">Je jednoduché začít a poskytnout cennou zpětnou [vazbu k naší](hololens-insider.md#start-receiving-insider-builds) další hlavní aktualizaci operačního systému pro HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="1a8d9-106">Poznámky k verzi Windows Insider</span><span class="sxs-lookup"><span data-stu-id="1a8d9-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="1a8d9-107">S radostí začneme znovu začínat nové funkce pro Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="1a8d9-108">Pro nejnovější aktualizace budou nové buildy zacházet s kanály pro vývoj a beta verze.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="1a8d9-109">Tuto stránku budeme dál aktualizovat, protože přidáváme další funkce a aktualizace našich buildů Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="1a8d9-110">Využijte rádi a připravte se na tyto aktualizace ke své realitě.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-110">Get excited and ready to mix these updates into your reality.</span></span>

| <span data-ttu-id="1a8d9-111">Funkce</span><span class="sxs-lookup"><span data-stu-id="1a8d9-111">Feature</span></span>                 | <span data-ttu-id="1a8d9-112">Popis</span><span class="sxs-lookup"><span data-stu-id="1a8d9-112">Description</span></span>                | <span data-ttu-id="1a8d9-113">Cíloví uživatelé</span><span class="sxs-lookup"><span data-stu-id="1a8d9-113">Target Users</span></span> | <span data-ttu-id="1a8d9-114">Sestavení představeno</span><span class="sxs-lookup"><span data-stu-id="1a8d9-114">Build introduced</span></span> |
|-------------------------|----------------------------|--------------|------------------|
| <span data-ttu-id="1a8d9-115">Změny CSP na HoloLens</span><span class="sxs-lookup"><span data-stu-id="1a8d9-115">CSP Changes on HoloLens</span></span> | <span data-ttu-id="1a8d9-116">Noví poskytovatelé CSP pro k dotazování na data</span><span class="sxs-lookup"><span data-stu-id="1a8d9-116">New CSPs for to query data</span></span> | <span data-ttu-id="1a8d9-117">Správci IT</span><span class="sxs-lookup"><span data-stu-id="1a8d9-117">IT Admins</span></span>    | <span data-ttu-id="1a8d9-118">20348,1403</span><span class="sxs-lookup"><span data-stu-id="1a8d9-118">20348.1403</span></span>                 |

### <a name="csp-changes-on-hololens"></a><span data-ttu-id="1a8d9-119">Změny CSP na HoloLens</span><span class="sxs-lookup"><span data-stu-id="1a8d9-119">CSP changes on HoloLens</span></span>

- <span data-ttu-id="1a8d9-120">Představeno v buildu Windows Insider, 20348,1403</span><span class="sxs-lookup"><span data-stu-id="1a8d9-120">Introduced in Windows Insider build, 20348.1403</span></span>

#### <a name="devdetail-csp"></a><span data-ttu-id="1a8d9-121">DevDetail CSP</span><span class="sxs-lookup"><span data-stu-id="1a8d9-121">DevDetail CSP</span></span>

<span data-ttu-id="1a8d9-122">DevDetail CSP teď také oznamuje volné místo v úložišti na zařízení HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-122">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="1a8d9-123">To by mělo odpovídat hodnotě zobrazené na stránce nastavení úložiště aplikace.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-123">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="1a8d9-124">Následuje konkrétní uzel, který obsahuje tyto informace.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-124">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="1a8d9-125">./DevDetail/Ext/Microsoft/FreeStorage (pouze operace GET)</span><span class="sxs-lookup"><span data-stu-id="1a8d9-125">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp"></a><span data-ttu-id="1a8d9-126">DeviceStatus CSP</span><span class="sxs-lookup"><span data-stu-id="1a8d9-126">DeviceStatus CSP</span></span>

<span data-ttu-id="1a8d9-127">DeviceStatus CSP teď také hlásí identifikátory SSID a BSSID sítě Wi-Fi, se kterými je síť HoloLens aktivně připojená.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-127">DeviceStatus CSP now also reports SSID and BSSID of Wifi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="1a8d9-128">Níže jsou uvedené konkrétní uzly, které obsahují tyto informace.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-128">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="1a8d9-129">*Adresa MAC adaptéru Wi-Fi*/SSID/Vendor/MSFT/DeviceStatus/NetworkIdentifiers/</span><span class="sxs-lookup"><span data-stu-id="1a8d9-129">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="1a8d9-130">*Adresa MAC adaptéru Wi-Fi*/BSSID/Vendor/MSFT/DeviceStatus/NetworkIdentifiers/</span><span class="sxs-lookup"><span data-stu-id="1a8d9-130">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="1a8d9-131">Příklad objektu BLOB SyncML (pro dodavatele MDM) pro dotazování na NetworkIdentifiers</span><span class="sxs-lookup"><span data-stu-id="1a8d9-131">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

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

### <a name="fixes-and-improvements"></a><span data-ttu-id="1a8d9-132">Opravy a vylepšení:</span><span class="sxs-lookup"><span data-stu-id="1a8d9-132">Fixes and improvements:</span></span>

- <span data-ttu-id="1a8d9-133">Opravili [jsme známý problém s portálem zařízení, kde se nestáhly uzamčené soubory.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="1a8d9-133">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="1a8d9-134">Opravili jsme [známý problém s portálem zařízení s časovým limitem nahrávání a stahování souborů.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span><span class="sxs-lookup"><span data-stu-id="1a8d9-134">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>

## <a name="start-receiving-insider-builds"></a><span data-ttu-id="1a8d9-135">Zahájit přijímání buildů Insider</span><span class="sxs-lookup"><span data-stu-id="1a8d9-135">Start receiving Insider builds</span></span>
> [!NOTE]
> <span data-ttu-id="1a8d9-136">Pokud jste se neaktualizovali v poslední době, restartujte prosím své zařízení, aby se aktualizovaly stav, a získejte nejnovější Build.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-136">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="1a8d9-137">Hlasový příkaz "restartovat zařízení" dobře funguje.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-137">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="1a8d9-138">V nastavení/programu Windows Insider můžete také zvolit tlačítko restartovat.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-138">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="1a8d9-139">Na back-endu jsme narazili na chybu, která se vám mohla vyskytnout, a získáte zpět sledování.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-139">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="1a8d9-140">V zařízení HoloLens 2 přejít na **Nastavení**  >  **aktualizace & zabezpečení**  >  **Windows Insider program** a vyberte Začínáme .</span><span class="sxs-lookup"><span data-stu-id="1a8d9-140">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="1a8d9-141">Propojte účet, který jste použili k registraci jako Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-141">Link the account you used to register as a Windows Insider.</span></span>
<span data-ttu-id="1a8d9-142">Windows Insider se teď přesouvá na kanály.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-142">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="1a8d9-143">**Rychlý** prstenec se stane **kanálem pro vývoj**, **pomalé** vyzvánění se stane **kanálem beta verze** a prstenec **verze Preview** se stane **kanálem verze Preview**.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-143">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="1a8d9-144">Toto mapování vypadá takto: ![ vysvětlení kanálů Windows Insider ](images/WindowsInsiderChannels.png) pro další informace najdete v tématu [představení kanálů Windows Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) na blogu Windows.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-144">Here is what that mapping looks like: ![Windows Insider Channels explanation](images/WindowsInsiderChannels.png) For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="1a8d9-145">Pak vyberte **aktivní vývoj oken**, zvolte, jestli chcete dostávat buildy pro **vývoj** nebo **beta kanál** , a zkontrolujte, jaké jsou tyto programy.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-145">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="1a8d9-146">Kliknutím na tlačítko **potvrdit > restartovat nyní** dokončete instalaci.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-146">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="1a8d9-147">Po restartování zařízení přejít na **nastavení > Update & Security > vyhledat aktualizace** a získat nejnovější Build.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-147">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>
### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="1a8d9-148">Chyba aktualizace 0x80070490 práce</span><span class="sxs-lookup"><span data-stu-id="1a8d9-148">Update error 0x80070490 work-around</span></span>
<span data-ttu-id="1a8d9-149">Pokud narazíte na chybu aktualizace 0x80070490 při aktualizaci na vývojovém nebo beta kanálu, zkuste následující krátkodobé řešení.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-149">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="1a8d9-150">Zahrnuje přesun kanálu služby Insider, aktualizaci a přesun kanálu Insider zpátky.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-150">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>
#### <a name="stage-one---release-preview"></a><span data-ttu-id="1a8d9-151">Fáze verze Preview 1</span><span class="sxs-lookup"><span data-stu-id="1a8d9-151">Stage one - Release Preview</span></span>
1.  <span data-ttu-id="1a8d9-152">Nastavení, aktualizace & zabezpečení, program Windows Insider, výběr **kanálu verze Preview**.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-152">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>
2.  <span data-ttu-id="1a8d9-153">Nastavení, aktualizace & zabezpečení web Windows Update, **Vyhledat aktualizace**.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-153">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="1a8d9-154">Po aktualizaci pokračujte do fáze 2.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-154">After the update, continue on to Stage two.</span></span>
#### <a name="stage-two---dev-channel"></a><span data-ttu-id="1a8d9-155">Fáze – dva vývojové kanály</span><span class="sxs-lookup"><span data-stu-id="1a8d9-155">Stage two - Dev Channel</span></span>
1. <span data-ttu-id="1a8d9-156">Nastavení, aktualizace & zabezpečení, program Windows Insider, výběr **vývojového kanálu**.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-156">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>
2. <span data-ttu-id="1a8d9-157">Nastavení, aktualizace & zabezpečení web Windows Update, **Vyhledat aktualizace**.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-157">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>
## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="1a8d9-158">FFU stažení a pokyny pro Flash</span><span class="sxs-lookup"><span data-stu-id="1a8d9-158">FFU download and flash directions</span></span>
<span data-ttu-id="1a8d9-159">Pokud chcete otestovat ffuem podepsaným letem, musíte nejdřív zařízení odemknout a před zavedením ffuého letu podepsaného.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-159">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="1a8d9-160">V počítači:</span><span class="sxs-lookup"><span data-stu-id="1a8d9-160">On PC:</span></span>
    1. <span data-ttu-id="1a8d9-161">Stáhněte si FFU do počítače z [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .</span><span class="sxs-lookup"><span data-stu-id="1a8d9-161">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="1a8d9-162">Nainstalujte oblouk (Průvodce pokročilým obnovením) z Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .</span><span class="sxs-lookup"><span data-stu-id="1a8d9-162">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="1a8d9-163">Při zablokování HoloLens: Otevřete **Nastavení**  >  **aktualizovat & zabezpečení**  >  **program Windows Insider** a potom se zaregistrujte a restartujte zařízení.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-163">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>
1. <span data-ttu-id="1a8d9-164">FFU Flash – nyní můžete FFU podepsaný pro let pomocí ARC.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-164">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>
### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="1a8d9-165">Poskytněte zpětnou vazbu a nahlásit problémy</span><span class="sxs-lookup"><span data-stu-id="1a8d9-165">Provide feedback and report issues</span></span>
<span data-ttu-id="1a8d9-166">K poskytnutí zpětné vazby a hlášení problémů použijte prosím [aplikaci centra Feedback](hololens-feedback.md) na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-166">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="1a8d9-167">Pomocí centra Feedback zajišťujeme, aby byly k dispozici všechny potřebné diagnostické informace, které nám pomohly rychle ladit a řešit potíže.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-167">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="1a8d9-168">Problémy s čínskou a japonskou verzí HoloLens by měly být hlášeny stejným způsobem.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-168">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>
> [!NOTE]
> <span data-ttu-id="1a8d9-169">Nezapomeňte přijmout výzvu s dotazem, jestli chcete, aby měl centrum zpětné vazby přístup ke složce dokumentů (po zobrazení výzvy vyberte **Ano** ).</span><span class="sxs-lookup"><span data-stu-id="1a8d9-169">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>
## <a name="note-for-developers"></a><span data-ttu-id="1a8d9-170">Poznámka pro vývojáře</span><span class="sxs-lookup"><span data-stu-id="1a8d9-170">Note for developers</span></span>
<span data-ttu-id="1a8d9-171">Jste připraveni a doporučujeme vyzkoušet vývoj vašich aplikací pomocí buildů Insider pro HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-171">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="1a8d9-172">Začněte tím, že si Projděte [dokumentaci pro vývojáře HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) .</span><span class="sxs-lookup"><span data-stu-id="1a8d9-172">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="1a8d9-173">Stejné pokyny fungují s buildy pro práci s buildem HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-173">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="1a8d9-174">Můžete použít stejné sestavení Unity a Visual Studio, které už používáte pro vývoj na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-174">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>
## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="1a8d9-175">Zastavit příjem buildů Insider</span><span class="sxs-lookup"><span data-stu-id="1a8d9-175">Stop receiving Insider builds</span></span>
<span data-ttu-id="1a8d9-176">Pokud už nechcete dostávat buildy Insider pro Windows holografické, můžete se odhlásit, když na HoloLens běží výrobní sestavení, nebo můžete [zařízení obnovit](hololens-recovery.md) pomocí Průvodce pokročilým obnovením a obnovit zařízení do verze Windows holografického v jiné verzi než Insider.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-176">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>
> [!CAUTION]
> <span data-ttu-id="1a8d9-177">Došlo k známému problému, při kterém se uživatelé, kteří zruší registraci v buildu Insider Preview po ruční instalaci nového buildu Preview, zobrazí modrá obrazovka.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-177">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="1a8d9-178">Potom musí zařízení ručně obnovit.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-178">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="1a8d9-179">Podrobné informace o tom, jestli by se to ovlivnilo, najdete v tomto [známém problému](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span><span class="sxs-lookup"><span data-stu-id="1a8d9-179">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>
<span data-ttu-id="1a8d9-180">Chcete-li ověřit, zda je na HoloLens spuštěno výrobní sestavení:</span><span class="sxs-lookup"><span data-stu-id="1a8d9-180">To verify that your HoloLens is running a production build:</span></span>
1. <span data-ttu-id="1a8d9-181">Přejít na **nastavení > systémové > o produktu** a najít číslo buildu.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-181">Go to **Settings > System > About**, and find the build number.</span></span>
1. <span data-ttu-id="1a8d9-182">[Přečtěte si poznámky k verzi pro výrobní čísla buildu](hololens-release-notes.md).</span><span class="sxs-lookup"><span data-stu-id="1a8d9-182">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>
<span data-ttu-id="1a8d9-183">Odhlášení od buildů Insider:</span><span class="sxs-lookup"><span data-stu-id="1a8d9-183">To opt out of Insider builds:</span></span>
1. <span data-ttu-id="1a8d9-184">Na HoloLens, na kterém běží výrobní sestavení, klikněte na **nastavení > Update & Security > program Windows Insider** a vyberte **Zastavit buildy Insider**.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-184">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>
1. <span data-ttu-id="1a8d9-185">Pokud chcete zařízení odhlásit, postupujte podle pokynů.</span><span class="sxs-lookup"><span data-stu-id="1a8d9-185">Follow the instructions to opt out your device.</span></span>
