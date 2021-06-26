---
title: Řešení potíží se zařízeními HoloLens
description: Aktuální informace o nejběžnějších řešeních problémů se zařízeními HoloLens a jejich řešení
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: issues, bug, troubleshoot, fix, help, support, HoloLens, emulator
ms.openlocfilehash: b69dddf04ac31b69f0b2f8759d095806189f33ab
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924617"
---
# <a name="device-troubleshooting"></a><span data-ttu-id="6749c-104">Řešení potíží se zařízeními</span><span class="sxs-lookup"><span data-stu-id="6749c-104">Device Troubleshooting</span></span>

<span data-ttu-id="6749c-105">Tento článek popisuje, jak vyřešit několik běžných problémů s HoloLens.</span><span class="sxs-lookup"><span data-stu-id="6749c-105">This article describes how to resolve several common HoloLens issues.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="6749c-106">Než začnete s řešením potíží, ujistěte se, že je vaše zařízení naúčtované **na 20 až 40** % kapacity baterie, pokud je to možné.</span><span class="sxs-lookup"><span data-stu-id="6749c-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="6749c-107">Indikátory [baterie umístěné](hololens2-setup.md#lights-that-indicate-the-battery-level) pod tlačítkem napájení jsou rychlým způsobem, jak ověřit kapacitu baterie bez přihlášení k zařízení.</span><span class="sxs-lookup"><span data-stu-id="6749c-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<a id="list"></a>

<span data-ttu-id="6749c-108">**Známé problémy**</span><span class="sxs-lookup"><span data-stu-id="6749c-108">**Known Issues**</span></span>
- [<span data-ttu-id="6749c-109">Video remote assist se zablokuje po 20 minutách</span><span class="sxs-lookup"><span data-stu-id="6749c-109">Remote Assist video freezes after 20 minutes</span></span>](#remote-assist-video-freezes-after-20-minutes)
- [<span data-ttu-id="6749c-110">Automatické přihlášení žádá o přihlášení</span><span class="sxs-lookup"><span data-stu-id="6749c-110">Auto-login asks for log-in</span></span>](#auto-login-asks-for-log-in)
- [<span data-ttu-id="6749c-111">Microsoft Edge spuštění se nepovede</span><span class="sxs-lookup"><span data-stu-id="6749c-111">Microsoft Edge fails to launch</span></span>](#microsoft-edge-fails-to-launch)
- [<span data-ttu-id="6749c-112">Klávesnice se přepne na speciální znaky</span><span class="sxs-lookup"><span data-stu-id="6749c-112">Keyboard doesn't switch to special characters</span></span>](#keyboard-doesnt-switch-to-special-characters)
- [<span data-ttu-id="6749c-113">Při stahování uzamčených souborů se nez zobrazení chyby</span><span class="sxs-lookup"><span data-stu-id="6749c-113">Downloading locked files doesn't show error</span></span>](#downloading-locked-files-doesnt-error)
- [<span data-ttu-id="6749c-114">Portál zařízení nahrání nebo stažení souboru</span><span class="sxs-lookup"><span data-stu-id="6749c-114">Device Portal file upload/download times out</span></span>](#device-portal-file-uploaddownload-times-out)
- [<span data-ttu-id="6749c-115">Modrá obrazovka po zrušení registrace z insider ve verzi Preview na zařízení blikající sestavením Insider</span><span class="sxs-lookup"><span data-stu-id="6749c-115">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [<span data-ttu-id="6749c-116">OneDrive automaticky nenahraje obrázky</span><span class="sxs-lookup"><span data-stu-id="6749c-116">OneDrive doesn't automatically upload pictures</span></span>](#onedrive-doesnt-automatically-upload-pictures)

<span data-ttu-id="6749c-117">**Obecné**</span><span class="sxs-lookup"><span data-stu-id="6749c-117">**General**</span></span>
- [<span data-ttu-id="6749c-118">HoloLens nereaguje nebo se nespustí</span><span class="sxs-lookup"><span data-stu-id="6749c-118">HoloLens is unresponsive or won't start</span></span>](#hololens-is-unresponsive-or-wont-start)
- [<span data-ttu-id="6749c-119">Chyba Nedostatek místa na disku</span><span class="sxs-lookup"><span data-stu-id="6749c-119">"Low Disk Space" error</span></span>](#low-disk-space-error)
- [<span data-ttu-id="6749c-120">Selhání selhání</span><span class="sxs-lookup"><span data-stu-id="6749c-120">Calibration Fails</span></span>](#calibration-fails)
- [<span data-ttu-id="6749c-121">Nemůžu se přihlásit, protože moje HoloLens byla dříve nastavená pro někoho jiného</span><span class="sxs-lookup"><span data-stu-id="6749c-121">Can't sign in because my HoloLens was previously set up for someone else</span></span>](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [<span data-ttu-id="6749c-122">Unity nefunguje</span><span class="sxs-lookup"><span data-stu-id="6749c-122">Unity isn't working</span></span>](#unity-isnt-working)
- [<span data-ttu-id="6749c-123">Portál zařízení s Windows nefunguje správně</span><span class="sxs-lookup"><span data-stu-id="6749c-123">Windows Device Portal isn't working correctly</span></span>](#windows-device-portal-isnt-working-correctly)
- [<span data-ttu-id="6749c-124">Emulátor HoloLens nefunguje</span><span class="sxs-lookup"><span data-stu-id="6749c-124">The HoloLens Emulator isn't working</span></span>](#the-hololens-emulator-isnt-working)

<span data-ttu-id="6749c-125">**Vstup**</span><span class="sxs-lookup"><span data-stu-id="6749c-125">**Input**</span></span>
- [<span data-ttu-id="6749c-126">Nefungují hlasové příkazy</span><span class="sxs-lookup"><span data-stu-id="6749c-126">Voice commands aren't working</span></span>](#voice-commands-arent-working)
- [<span data-ttu-id="6749c-127">Ruční vstup nefunguje</span><span class="sxs-lookup"><span data-stu-id="6749c-127">Hand input isn't working</span></span>](#hand-input-isnt-working)

<span data-ttu-id="6749c-128">**Připojení**</span><span class="sxs-lookup"><span data-stu-id="6749c-128">**Connectivity**</span></span>
- [<span data-ttu-id="6749c-129">Nelze se připojit k Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="6749c-129">Can't connect to Wi-Fi</span></span>](#cant-connect-to-wi-fi)

<span data-ttu-id="6749c-130">**Externí zařízení**</span><span class="sxs-lookup"><span data-stu-id="6749c-130">**External Devices**</span></span> 
- [<span data-ttu-id="6749c-131">Zařízení Bluetooth se neschová</span><span class="sxs-lookup"><span data-stu-id="6749c-131">Bluetooth devices aren't pairing</span></span>](#bluetooth-devices-arent-pairing)
- [<span data-ttu-id="6749c-132">Mikrofon USB-C nefunguje</span><span class="sxs-lookup"><span data-stu-id="6749c-132">USB-C Microphone isn't working</span></span>](#usb-c-microphone-isnt-working)
- [<span data-ttu-id="6749c-133">Zařízení uvedená jako dostupná v Nastavení nefungují</span><span class="sxs-lookup"><span data-stu-id="6749c-133">Devices listed as available in Settings don't work</span></span>](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a><span data-ttu-id="6749c-134">Video remote assist se zablokuje po 20 minutách</span><span class="sxs-lookup"><span data-stu-id="6749c-134">Remote Assist video freezes after 20 minutes</span></span>

> [!NOTE]
> <span data-ttu-id="6749c-135">Vzhledem k závažnosti tohoto známého problému jsme v současné době pozastavil dostupnost Windows Holographic verze 21H1.</span><span class="sxs-lookup"><span data-stu-id="6749c-135">Due to this Known Issue's severity we have currently paused the availability of Windows Holographic, version 21H1.</span></span> <span data-ttu-id="6749c-136">Pokud chcete stále aktualizovat zařízení na 21H1, postupujte podle pokynů v poznámkách k verzi v [horní části stránky.](hololens-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="6749c-136">If you would like to still update your devices to 21H1, please refer to [the instructions in our release notes at the top of the page.](hololens-release-notes.md)</span></span>

<span data-ttu-id="6749c-137">V nejnovější verzi [Windows Holographic verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1)zaznamenali někteří uživatelé Remote Assistu během volání více než 20 minut zamrznutí videa.</span><span class="sxs-lookup"><span data-stu-id="6749c-137">On the latest release of [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), some users of Remote Assist have experienced video freezing during calls over 20 minutes.</span></span> <span data-ttu-id="6749c-138">Jedná se o **známý problém.**</span><span class="sxs-lookup"><span data-stu-id="6749c-138">This is a **known issue**.</span></span>

### <a name="workarounds"></a><span data-ttu-id="6749c-139">Alternativní řešení</span><span class="sxs-lookup"><span data-stu-id="6749c-139">Workarounds</span></span>

#### <a name="restart-in-between-calls"></a><span data-ttu-id="6749c-140">Restartování mezi voláními</span><span class="sxs-lookup"><span data-stu-id="6749c-140">Restart in between calls</span></span>

<span data-ttu-id="6749c-141">Pokud vaše volání přesájí 20 minut a dochází k tomuto problému, zkuste zařízení restartovat.</span><span class="sxs-lookup"><span data-stu-id="6749c-141">If your calls are going over a length of 20 minutes and you are experiencing this issue, try rebooting your device.</span></span> <span data-ttu-id="6749c-142">Restartováním zařízení mezi voláními vzdálené pomoci se zařízení aktualizuje a vrátí se do dobrého stavu.</span><span class="sxs-lookup"><span data-stu-id="6749c-142">Rebooting your device between Remote Assist calls will refresh your device and put it back into a good state.</span></span>

<span data-ttu-id="6749c-143">Pokud chcete rychle restartovat zařízení na Zařízení s [Windows Holographic verze 21H1,](hololens-release-notes.md#windows-holographic-version-21h1) otevřete nabídku Start, vyberte ikonu uživatele a pak vyberte **Restartovat.**</span><span class="sxs-lookup"><span data-stu-id="6749c-143">To quickly restart a device on [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) open the start menu, and select the user icon, then select **Restart**.</span></span>

#### <a name="revert-to-an-older-build"></a><span data-ttu-id="6749c-144">Návrat ke starší verzi sestavení</span><span class="sxs-lookup"><span data-stu-id="6749c-144">Revert to an older build</span></span>

<span data-ttu-id="6749c-145">Někteří zákazníci zjistili, že při návratu ke starší verzi operačního systému už tento problém nemají.</span><span class="sxs-lookup"><span data-stu-id="6749c-145">Some customers have found that when reverting to an earlier OS version they no longer experience this issue.</span></span> <span data-ttu-id="6749c-146">Pokud jste zjistili, že u vašich zařízení dochází k tomuto problému, zkuste následující kroky:</span><span class="sxs-lookup"><span data-stu-id="6749c-146">If you have found that your devices are experiencing this issue, try these steps:</span></span>


<span data-ttu-id="6749c-147">Alternativní řešení:</span><span class="sxs-lookup"><span data-stu-id="6749c-147">Workarounds:</span></span>

- <span data-ttu-id="6749c-148">Pokud je pro vaši firmu přijatelné, je u uživatelských účtů Microsoft podporováno automatické nahrávání fotoaparátu.</span><span class="sxs-lookup"><span data-stu-id="6749c-148">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="6749c-149">K pracovnímu nebo školnímu účtu se účet Microsoft přihlásit i ke svému pracovnímu nebo školnímu účtu (aplikace OneDrive podporuje duální přihlášení).</span><span class="sxs-lookup"><span data-stu-id="6749c-149">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="6749c-150">Ve svém účet Microsoft v rámci OneDrivu můžete povolit automatické nahrávání fotoaparátů na pozadí.</span><span class="sxs-lookup"><span data-stu-id="6749c-150">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="6749c-151">Pokud nemůžete bezpečně používat uživatelský účet účet Microsoft k automatickému nahrávání fotek, můžete fotky z aplikace OneDrive nahrát ručně do svého pracovního nebo školního účtu.</span><span class="sxs-lookup"><span data-stu-id="6749c-151">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="6749c-152">Pokud to chcete udělat, ujistěte se, že jste v aplikaci OneDrive přihlášení ke svému pracovnímu nebo školnímu účtu.</span><span class="sxs-lookup"><span data-stu-id="6749c-152">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="6749c-153">Vyberte tlačítko **+** a zvolte **Nahrát.**</span><span class="sxs-lookup"><span data-stu-id="6749c-153">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="6749c-154">Najděte fotky nebo videa, které chcete nahrát, tak, že přejdete na Obrázky **> fotoaparátu.**</span><span class="sxs-lookup"><span data-stu-id="6749c-154">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="6749c-155">Vyberte fotky nebo videa, která chcete nahrát, a pak vyberte **tlačítko** Otevřít.</span><span class="sxs-lookup"><span data-stu-id="6749c-155">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>


1. [<span data-ttu-id="6749c-156">Stažení buildu pro Windows Holographic verze 20H2 – aktualizace z května 2021</span><span class="sxs-lookup"><span data-stu-id="6749c-156">Download the build for Windows Holographic, version 20H2 – May 2021 Update</span></span>](https://aka.ms/hololens2download/10.0.19041.1146)
1. <span data-ttu-id="6749c-157">Postupujte podle [pokynů a vraťte se k předchozí verzi operačního systému.](hololens-update-hololens.md#go-back-to-a-previous-version)</span><span class="sxs-lookup"><span data-stu-id="6749c-157">Follow the [instructions return to a previous OS version](hololens-update-hololens.md#go-back-to-a-previous-version)</span></span>
1. <span data-ttu-id="6749c-158">Aktualizace [operačního systému můžete na zařízení pozastavit ručně](hololens-updates.md#pause-updates-via-device) nebo u mnoha zařízení používat [odložení prostřednictvím MDM.](hololens-updates.md#configure-an-update-deferral-policy)</span><span class="sxs-lookup"><span data-stu-id="6749c-158">Either [pause OS updates on the device manually](hololens-updates.md#pause-updates-via-device) or for many devices use [deferral through MDM](hololens-updates.md#configure-an-update-deferral-policy).</span></span>

[<span data-ttu-id="6749c-159">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="6749c-159">Back to list</span></span>](#list)

## <a name="auto-login-asks-for-log-in"></a><span data-ttu-id="6749c-160">Automatické přihlášení žádá o přihlášení</span><span class="sxs-lookup"><span data-stu-id="6749c-160">Auto-login asks for log-in</span></span>

<span data-ttu-id="6749c-161">Zařízení HoloLens 2 je možné nakonfigurovat tak, aby se automaticky přihlašoval přes Nastavení Účty Možnosti přihlášení -> a v části  ->    ->    Požadováno na hodnotu Nikdy **.**</span><span class="sxs-lookup"><span data-stu-id="6749c-161">A HoloLens 2 device can be configured to automatically login in via **Settings** -> **Accounts** -> **Sign-in Options** -> and under **Required** setting the value to **Never**.</span></span> <span data-ttu-id="6749c-162">Někteří uživatelé se při aktualizaci zařízení s podstatně velkou aktualizací, jako je třeba aktualizace funkcí, mohou znova přihlásit k zařízení.</span><span class="sxs-lookup"><span data-stu-id="6749c-162">Some users may be required to log-in to the device again when updating a device with a substantially large update, such as a feature update.</span></span> <span data-ttu-id="6749c-163">Jedná se o **známý problém.**</span><span class="sxs-lookup"><span data-stu-id="6749c-163">This is a **known issue**.</span></span>

<span data-ttu-id="6749c-164">Příklad, kdy k tomu může dojít:</span><span class="sxs-lookup"><span data-stu-id="6749c-164">Example of when this could occur:</span></span>

- <span data-ttu-id="6749c-165">Aktualizace zařízení z Windows Holographic verze 2004 (build 19041.xxxx) na Windows Holographic verze 21H1 (build 20346.xxxx)</span><span class="sxs-lookup"><span data-stu-id="6749c-165">Updating a device from Windows Holographic, version 2004 (Build 19041.xxxx) to Windows Holographic, version 21H1 (Build 20346.xxxx)</span></span>
- <span data-ttu-id="6749c-166">Aktualizace zařízení tak, aby šouplodou aktualizaci ve stejném hlavním buildu, např. Windows Holographic, verze 2004 na Windows Holographic, verze 20H2</span><span class="sxs-lookup"><span data-stu-id="6749c-166">Updating a device to take a large update on the same major build, e.g. Windows Holographic, version 2004 to Windows Holographic, version 20H2</span></span>
- <span data-ttu-id="6749c-167">Aktualizace zařízení z image továrny na nejnovější image</span><span class="sxs-lookup"><span data-stu-id="6749c-167">Updating a device from a factory image to the latest image</span></span>

<span data-ttu-id="6749c-168">K tomu by nemělo dojít během:</span><span class="sxs-lookup"><span data-stu-id="6749c-168">This should not occur during:</span></span>

- <span data-ttu-id="6749c-169">Zařízení, která mají měsíční servisní aktualizaci</span><span class="sxs-lookup"><span data-stu-id="6749c-169">Devices taking a monthly servicing update</span></span>

<span data-ttu-id="6749c-170">Alternativní metody:</span><span class="sxs-lookup"><span data-stu-id="6749c-170">Work around methods:</span></span>

- <span data-ttu-id="6749c-171">Metody přihlášení, jako jsou PIN, heslo, Iris, webové ověřování nebo klíče FIDO2.</span><span class="sxs-lookup"><span data-stu-id="6749c-171">Sign-in methods such as PIN, Password, Iris, Web Authentication, or FIDO2 keys.</span></span>
- <span data-ttu-id="6749c-172">Pokud pin kód zařízení nelze zapamatovat a jiné metody ověřování nejsou k dispozici, může uživatel použít režim [ručního lomítka](hololens-recovery.md#manual-procedure).</span><span class="sxs-lookup"><span data-stu-id="6749c-172">If device PIN cannot be remembered, and other authentication methods are not available, then a user can use [manual reflashing mode](hololens-recovery.md#manual-procedure).</span></span>

[<span data-ttu-id="6749c-173">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="6749c-173">Back to list</span></span>](#list)

## <a name="microsoft-edge-fails-to-launch"></a><span data-ttu-id="6749c-174">Microsoft Edge spuštění se nepovede</span><span class="sxs-lookup"><span data-stu-id="6749c-174">Microsoft Edge fails to launch</span></span>

> [!NOTE]
> <span data-ttu-id="6749c-175">Tento problém byl původně vytvořen s náklady na Microsoft Edge verzí.</span><span class="sxs-lookup"><span data-stu-id="6749c-175">This issue was originally created with the shipping version of Microsoft Edge in-mind.</span></span> <span data-ttu-id="6749c-176">Tento problém se může vyřešit v [nové Microsoft Edge](hololens-new-edge.md).</span><span class="sxs-lookup"><span data-stu-id="6749c-176">This issue may be resolved in the [new Microsoft Edge](hololens-new-edge.md).</span></span> <span data-ttu-id="6749c-177">Pokud ne, zpětnou vazbu nahlaste.</span><span class="sxs-lookup"><span data-stu-id="6749c-177">If it is not, please file feedback.</span></span>

<span data-ttu-id="6749c-178">Několik zákazníků nahlásilo problém, kdy Microsoft Edge spuštění.</span><span class="sxs-lookup"><span data-stu-id="6749c-178">A few customers have reported an issue where Microsoft Edge fails to launch.</span></span> <span data-ttu-id="6749c-179">U těchto zákazníků problém přetrvává i po restartování a nevyřeší se aktualizacemi aplikací nebo Windows.</span><span class="sxs-lookup"><span data-stu-id="6749c-179">For these customers, the issue persists through reboot and is not resolved with Windows or application updates.</span></span> <span data-ttu-id="6749c-180">Pokud k tomuto problému dochází a potvrdili jste, že [je Windows](hololens-updates.md#manually-check-for-updates)aktuální, zakažte chybu z aplikace [Centrum Feedback](hololens-feedback.md) s následující kategorií a podkate kategorií: Instalace a aktualizace > Stažení, instalace a konfigurace služba Windows Update.</span><span class="sxs-lookup"><span data-stu-id="6749c-180">If you're experiencing this issue and you've confirmed [Windows is up-to-date](hololens-updates.md#manually-check-for-updates), please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.</span></span>

<span data-ttu-id="6749c-181">Neexistují žádná známá alternativní řešení, protože zatím jsme nemohli hlavní příčinu problému.</span><span class="sxs-lookup"><span data-stu-id="6749c-181">There are no known workarounds as we've been unable to root cause the issue so far.</span></span> <span data-ttu-id="6749c-182">S vyšetřováním vám pomůže Centrum Feedback chyb prostřednictvím webu společnosti.</span><span class="sxs-lookup"><span data-stu-id="6749c-182">Filing a bug via Feedback Hub will help our investigation!</span></span> <span data-ttu-id="6749c-183">Jedná se o **známý problém.**</span><span class="sxs-lookup"><span data-stu-id="6749c-183">This is a **known issue**.</span></span>

[<span data-ttu-id="6749c-184">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="6749c-184">Back to list</span></span>](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a><span data-ttu-id="6749c-185">Klávesnice se přepne na speciální znaky</span><span class="sxs-lookup"><span data-stu-id="6749c-185">Keyboard doesn't switch to special characters</span></span>

<span data-ttu-id="6749c-186">Při ooBE dochází k problému, kdy se po zvolení pracovního nebo školního účtu a zadání hesla uživatel pokouší přepnout na speciální znaky na klávesnici klepnutím na tlačítko &123, nezmění se na speciální znaky.</span><span class="sxs-lookup"><span data-stu-id="6749c-186">There is an issue during OOBE, where once the user has chosen a work or school account and is entering their password, trying to switch to the special characters on the keyboard by tapping the &123 button does not change to special characters.</span></span> <span data-ttu-id="6749c-187">Jedná se o **známý problém.**</span><span class="sxs-lookup"><span data-stu-id="6749c-187">This is a **known issue**.</span></span>

<span data-ttu-id="6749c-188">Obchádky:</span><span class="sxs-lookup"><span data-stu-id="6749c-188">Work-arounds:</span></span>
-   <span data-ttu-id="6749c-189">Zavřete klávesnici a znovu ji otevřete klepnutím na textové pole.</span><span class="sxs-lookup"><span data-stu-id="6749c-189">Close the keyboard and reopen it by tapping the text field.</span></span>
-   <span data-ttu-id="6749c-190">Nesprávně zadejte heslo.</span><span class="sxs-lookup"><span data-stu-id="6749c-190">Incorrectly enter your password.</span></span> <span data-ttu-id="6749c-191">Při příštím spuštění klávesnice bude klávesnice fungovat podle očekávání.</span><span class="sxs-lookup"><span data-stu-id="6749c-191">When the keyboard is relaunched next time it will then work as expected.</span></span>
- <span data-ttu-id="6749c-192">Webové ověřování, zavřete klávesnici a vyberte **Přihlásit se z jiného zařízení**.</span><span class="sxs-lookup"><span data-stu-id="6749c-192">Web Authentication, close the keyboard and select **Sign in from another device**.</span></span>
-   <span data-ttu-id="6749c-193">Pokud zadáváte jenom čísla, uživatel může stisknutím a podržením určitých kláves otevřít rozbalenou nabídku.</span><span class="sxs-lookup"><span data-stu-id="6749c-193">If entering only numbers, a user may press and hold certain keys to open an expanded menu.</span></span>
-   <span data-ttu-id="6749c-194">Pomocí klávesnice USB.</span><span class="sxs-lookup"><span data-stu-id="6749c-194">Using a USB keyboard.</span></span>

<span data-ttu-id="6749c-195">To nemá vliv na:</span><span class="sxs-lookup"><span data-stu-id="6749c-195">This does not affect:</span></span>
- <span data-ttu-id="6749c-196">Uživatelé, kteří se rozhodnout použít osobní účet.</span><span class="sxs-lookup"><span data-stu-id="6749c-196">Users who choose to use a personal account.</span></span>

[<span data-ttu-id="6749c-197">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="6749c-197">Back to list</span></span>](#list)


## <a name="downloading-locked-files-doesnt-error"></a><span data-ttu-id="6749c-198">Při stahování uzamčených souborů se ne zobrazí chyba</span><span class="sxs-lookup"><span data-stu-id="6749c-198">Downloading locked files doesn't error</span></span>
> <span data-ttu-id="6749c-199">! POZNÁMKA: Jedná se o **známý problém,** který je opraven Windows Insider buildu verze 20348.1403.</span><span class="sxs-lookup"><span data-stu-id="6749c-199">!NOTE This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span>


<span data-ttu-id="6749c-200">Při pokusu o stažení uzamčeného souboru v předchozích sestaveních Windows Holographic by výsledkem byla chybová stránka HTTP.</span><span class="sxs-lookup"><span data-stu-id="6749c-200">In previous builds of Windows Holographic, when attempting to download a locked file, the result would be an HTTP error page.</span></span> <span data-ttu-id="6749c-201">V aktualizaci Windows holografické verze 21H1, která se pokouší stáhnout uzamčený soubor, by nedocházelo k žádnému zobrazení výsledků, soubor se nestáhne a nebude k dispozici žádná chyba.</span><span class="sxs-lookup"><span data-stu-id="6749c-201">In the Windows Holographic, version 21H1 update, trying to download a locked file results in nothing visible happening—the file doesn’t download and there’s no error.</span></span> 

[<span data-ttu-id="6749c-202">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="6749c-202">Back to list</span></span>](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a><span data-ttu-id="6749c-203">Časový limit nahrávání nebo stahování souboru portálu zařízení</span><span class="sxs-lookup"><span data-stu-id="6749c-203">Device Portal file upload/download times out</span></span>
> <span data-ttu-id="6749c-204">! Poznámka: Jedná se o **známý problém** , který je opravený v buildu Windows Insider build verze 20348,1403.</span><span class="sxs-lookup"><span data-stu-id="6749c-204">!NOTE This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span> <span data-ttu-id="6749c-205">Pokud jste v rámci alternativního řešení dříve zakázali připojení SSL, důrazně doporučujeme ho znovu povolit.</span><span class="sxs-lookup"><span data-stu-id="6749c-205">If you previously disabled SSL Connection as part of the workaround, we highly recommend you re-enable it.</span></span>


<span data-ttu-id="6749c-206">Někteří zákazníci zjistili, že při pokusu o nahrání nebo stažení souborů se může zdát, že se operace zablokuje a vyprší časový limit nebo není možné ji ještě dokončit.</span><span class="sxs-lookup"><span data-stu-id="6749c-206">Some customers have found, when attempting to upload or download files, the operation might appear to hang and then time out or never complete.</span></span> <span data-ttu-id="6749c-207">To je oddělené od[známého problému "File Locked"](#downloading-locked-files-doesnt-error) – to má vliv na Windows holografické verze 2004, 20H2 a 21H1 buildů v rámci trhu.</span><span class="sxs-lookup"><span data-stu-id="6749c-207">This is separate from the '[file locked' known issue](#downloading-locked-files-doesnt-error) -- this affects Windows Holographic, versions 2004, 20H2 and 21H1 in-market builds.</span></span> <span data-ttu-id="6749c-208">Problém byl kořenem způsoben chybou v manipulaci s některými požadavky na portálu zařízení a při použití protokolu HTTPS, který je výchozím nastavením, se obvykle vychází.</span><span class="sxs-lookup"><span data-stu-id="6749c-208">The problem has been root caused to a bug in Device Portal's handling of certain requests, and is most consistently hit when using https, which is the default.</span></span> 

### <a name="workaround"></a><span data-ttu-id="6749c-209">Alternativní řešení</span><span class="sxs-lookup"><span data-stu-id="6749c-209">Workaround</span></span>

<span data-ttu-id="6749c-210">Toto alternativní řešení, které platí stejně jako Wi-Fi a UsbNcm, je zakázat možnost "požadované" v části "připojení SSL".</span><span class="sxs-lookup"><span data-stu-id="6749c-210">This workaround, which applies equally to Wi-Fi and UsbNcm, is to disable the "required" option under "SSL Connection".</span></span> <span data-ttu-id="6749c-211">Provedete to tak, že přejdete na portál zařízení, **systém** a vyberete stránku **Předvolby** .</span><span class="sxs-lookup"><span data-stu-id="6749c-211">To do so, navigate to Device Portal, **System**, and select the **Preferences** page.</span></span> <span data-ttu-id="6749c-212">V části **zabezpečení zařízení** vyhledejte **připojení SSL** a zrušte kontrolu, aby se vypnulo **povinné**.</span><span class="sxs-lookup"><span data-stu-id="6749c-212">In the **Device Security** section, locate **SSL Connection**, and uncheck to disable **Required**.</span></span>

<span data-ttu-id="6749c-213">Uživatel by pak měl přejít na http://, ne na https://(IP adresa) a funkce, jako je nahrání souboru, a stahování bude fungovat.</span><span class="sxs-lookup"><span data-stu-id="6749c-213">The user should then go to http://, not https:// (IP address) and features like file upload and download will work.</span></span>

[<span data-ttu-id="6749c-214">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="6749c-214">Back to list</span></span>](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a><span data-ttu-id="6749c-215">Modrá obrazovka po odregistraci z programu Insider Preview na zařízení, které se postavilo pomocí buildu Insider</span><span class="sxs-lookup"><span data-stu-id="6749c-215">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>

<span data-ttu-id="6749c-216">To má vliv na to, že se to týká uživatelů, kteří byli ve buildu Insider Preview, a pak si v programu Insider znovu založili nové sestavení Insider Preview a pak se zruší jeho registrace.</span><span class="sxs-lookup"><span data-stu-id="6749c-216">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span> <span data-ttu-id="6749c-217">Jedná se o **známý problém**.</span><span class="sxs-lookup"><span data-stu-id="6749c-217">This is a **known issue**.</span></span>

<span data-ttu-id="6749c-218">To nemá vliv na:</span><span class="sxs-lookup"><span data-stu-id="6749c-218">This does not affect:</span></span>
- <span data-ttu-id="6749c-219">Uživatelé, kteří nejsou zaregistrovaní ve Windows Insider</span><span class="sxs-lookup"><span data-stu-id="6749c-219">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="6749c-220">Insider</span><span class="sxs-lookup"><span data-stu-id="6749c-220">Insiders:</span></span>
    - <span data-ttu-id="6749c-221">Pokud bylo zařízení zaregistrováno, protože buildy Insider byly verze 18362. x</span><span class="sxs-lookup"><span data-stu-id="6749c-221">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="6749c-222">Pokud se v programu Insider nastavila aplikace Insider podepsaná 19041. x a zůstane zaregistrovaná v programu Insider</span><span class="sxs-lookup"><span data-stu-id="6749c-222">If they flashed an Insider signed 19041.x build AND stay enrolled in the Insider program</span></span>

<span data-ttu-id="6749c-223">Práce v tomto okolí:</span><span class="sxs-lookup"><span data-stu-id="6749c-223">Work-around:</span></span> 
- <span data-ttu-id="6749c-224">Vyhnout se problému</span><span class="sxs-lookup"><span data-stu-id="6749c-224">Avoid the issue</span></span> 
    - <span data-ttu-id="6749c-225">Zabliká Build bez programu Insider.</span><span class="sxs-lookup"><span data-stu-id="6749c-225">Flash a non-insider build.</span></span> <span data-ttu-id="6749c-226">Jedna z pravidelných měsíčních aktualizací.</span><span class="sxs-lookup"><span data-stu-id="6749c-226">One of the regular monthly updates.</span></span>
    - <span data-ttu-id="6749c-227">Zůstat ve verzi Insider Preview</span><span class="sxs-lookup"><span data-stu-id="6749c-227">Stay on Insider Preview</span></span>
- <span data-ttu-id="6749c-228">Rozsvítit zařízení</span><span class="sxs-lookup"><span data-stu-id="6749c-228">Reflash the device</span></span>

    1. <span data-ttu-id="6749c-229">Vložte [HoloLens 2 do režimu blesku](hololens-recovery.md) ručně, a to tak, že se nepřipojíte.</span><span class="sxs-lookup"><span data-stu-id="6749c-229">Put the [HoloLens 2 into flashing mode](hololens-recovery.md) manually by fully powering down while not connect.</span></span> <span data-ttu-id="6749c-230">Pak klepněte na tlačítko napájení.</span><span class="sxs-lookup"><span data-stu-id="6749c-230">Then while holding Volume up, tap the Power button.</span></span>
    
    1. <span data-ttu-id="6749c-231">Připojte se k počítači a otevřete Průvodce pokročilým obnovením.</span><span class="sxs-lookup"><span data-stu-id="6749c-231">Connect to the PC and open Advanced Recovery Companion.</span></span>
    
    1. <span data-ttu-id="6749c-232">Zablikají do výchozího buildu HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="6749c-232">Flash the HoloLens 2 to the default build.</span></span>

[<span data-ttu-id="6749c-233">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="6749c-233">Back to list</span></span>](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a><span data-ttu-id="6749c-234">OneDrive neodesílá automaticky obrázky.</span><span class="sxs-lookup"><span data-stu-id="6749c-234">OneDrive doesn't automatically upload pictures</span></span>

<span data-ttu-id="6749c-235">Aplikace OneDrive pro HoloLens nepodporuje automatické nahrávání fotoaparátů pro pracovní nebo školní účty.</span><span class="sxs-lookup"><span data-stu-id="6749c-235">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span> <span data-ttu-id="6749c-236">Jedná se o **známý problém**.</span><span class="sxs-lookup"><span data-stu-id="6749c-236">This is a **known issue**.</span></span>

<span data-ttu-id="6749c-237">Alternativní řešení:</span><span class="sxs-lookup"><span data-stu-id="6749c-237">Workarounds:</span></span>

- <span data-ttu-id="6749c-238">Pokud je pro vaši firmu životaschopná, je automatické nahrávání kamery podporované u zákaznických účtů Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6749c-238">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="6749c-239">Můžete se přihlásit k účet Microsoft kromě pracovního nebo školního účtu (aplikace OneDrive podporuje duální přihlášení).</span><span class="sxs-lookup"><span data-stu-id="6749c-239">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="6749c-240">Z profilu účet Microsoft v rámci OneDrivu můžete povolit automatické nahrávání snímků na pozadí.</span><span class="sxs-lookup"><span data-stu-id="6749c-240">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="6749c-241">Pokud nemůžete bezpečně použít účet Microsoft příjemce k automatickému nahrávání vašich fotografií, můžete fotky do svého pracovního nebo školního účtu ručně nahrát z aplikace OneDrive.</span><span class="sxs-lookup"><span data-stu-id="6749c-241">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="6749c-242">Abyste to mohli udělat, ujistěte se, že jste se přihlásili ke svému pracovnímu nebo školnímu účtu v aplikaci OneDrive.</span><span class="sxs-lookup"><span data-stu-id="6749c-242">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="6749c-243">Vyberte **+** tlačítko a zvolte **nahrát**.</span><span class="sxs-lookup"><span data-stu-id="6749c-243">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="6749c-244">Najděte fotky nebo videa, která chcete nahrát, přechodem na **obrázky >ou kamerou**.</span><span class="sxs-lookup"><span data-stu-id="6749c-244">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="6749c-245">Vyberte fotky nebo videa, která chcete nahrát, a pak vyberte tlačítko **otevřít** .</span><span class="sxs-lookup"><span data-stu-id="6749c-245">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

[<span data-ttu-id="6749c-246">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="6749c-246">Back to list</span></span>](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a><span data-ttu-id="6749c-247">HoloLens nereaguje nebo se nespustí.</span><span class="sxs-lookup"><span data-stu-id="6749c-247">HoloLens is unresponsive or won't start</span></span>

<span data-ttu-id="6749c-248">Pokud se váš HoloLens nespustí:</span><span class="sxs-lookup"><span data-stu-id="6749c-248">If your HoloLens won't start:</span></span>

- <span data-ttu-id="6749c-249">Pokud se indikátory LED vedle tlačítka napájení nekontrolují, nebo se jenom jeden z nich může krátce rozsvítit, možná budete muset [svůj HoloLens účtovat.](hololens2-charging.md#charging-the-device)</span><span class="sxs-lookup"><span data-stu-id="6749c-249">If the LEDs next to the power button don't light up, or only one LED briefly blinks, you may need to [charge your HoloLens.](hololens2-charging.md#charging-the-device)</span></span>
- <span data-ttu-id="6749c-250">Pokud při stisknutí tlačítka napájení zhasnou diody LED, ale nevidíte cokoli na zobrazených displejech, [proveďte obnovení zařízení](hololens-recovery.md#hard-reset-procedure).</span><span class="sxs-lookup"><span data-stu-id="6749c-250">If the LEDs light up when you press the power button but you can't see anything on the displays, [do a hard reset of the device](hololens-recovery.md#hard-reset-procedure).</span></span>

<span data-ttu-id="6749c-251">Pokud vaše HoloLens přestane být zmrazené nebo neodpovídá:</span><span class="sxs-lookup"><span data-stu-id="6749c-251">If your HoloLens becomes frozen or unresponsive:</span></span>

- <span data-ttu-id="6749c-252">Vypněte HoloLens tak, že stisknete tlačítko napájení, dokud se všechny pět diod LED nevypne, nebo 15 sekund, pokud indikátory LED nereagují.</span><span class="sxs-lookup"><span data-stu-id="6749c-252">Turn off your HoloLens by pressing the power button until all five of the LEDs turn themselves off, or for 15 seconds if the LEDs are unresponsive.</span></span> <span data-ttu-id="6749c-253">Chcete-li zahájit HoloLens, stiskněte tlačítko napájení znovu.</span><span class="sxs-lookup"><span data-stu-id="6749c-253">To start your HoloLens, press the power button again.</span></span>

<span data-ttu-id="6749c-254">Pokud tyto kroky nefungují, můžete zkusit [obnovit zařízení HoloLens 2](hololens-recovery.md) nebo [HoloLens (1. generace).](hololens1-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="6749c-254">If these steps don't work, you can try [recovering your HoloLens 2 device](hololens-recovery.md) or [HoloLens (1st gen) device.](hololens1-recovery.md)</span></span>

[<span data-ttu-id="6749c-255">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="6749c-255">Back to list</span></span>](#list)

## <a name="low-disk-space-error"></a><span data-ttu-id="6749c-256">Chyba "nedostatek místa na disku"</span><span class="sxs-lookup"><span data-stu-id="6749c-256">"Low Disk Space" error</span></span>

<span data-ttu-id="6749c-257">K uvolnění úložného prostoru budete potřebovat jednu nebo více následujících akcí:</span><span class="sxs-lookup"><span data-stu-id="6749c-257">You'll need to free up some storage space by doing one or more of the following:</span></span>

- <span data-ttu-id="6749c-258">Odstraňte některé nepoužité mezery.</span><span class="sxs-lookup"><span data-stu-id="6749c-258">Delete some unused spaces.</span></span> <span data-ttu-id="6749c-259">V **Nastavení**  >    >  **prostory** pro systém, vyberte místo, které už nepotřebujete, a pak vyberte **Odebrat**.</span><span class="sxs-lookup"><span data-stu-id="6749c-259">Go to **Settings** > **System** > **Spaces**, select a space that you no longer need, and then select **Remove**.</span></span>
- <span data-ttu-id="6749c-260">Odeberte některé hologramy, které jste umístili.</span><span class="sxs-lookup"><span data-stu-id="6749c-260">Remove some of the holograms that you've placed.</span></span>
- <span data-ttu-id="6749c-261">Odstraňte z aplikace Fotky některé obrázky a videa.</span><span class="sxs-lookup"><span data-stu-id="6749c-261">Delete some pictures and videos from the Photos app.</span></span>
- <span data-ttu-id="6749c-262">Odinstalujte některé aplikace z HoloLens.</span><span class="sxs-lookup"><span data-stu-id="6749c-262">Uninstall some apps from your HoloLens.</span></span> <span data-ttu-id="6749c-263">V seznamu **všechny aplikace** klepněte na aplikaci, kterou chcete odinstalovat, a pak vyberte **odinstalovat**.</span><span class="sxs-lookup"><span data-stu-id="6749c-263">In the **All apps** list, tap and hold the app you want to uninstall, and then select **Uninstall**.</span></span>

[<span data-ttu-id="6749c-264">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="6749c-264">Back to list</span></span>](#list)

## <a name="calibration-fails"></a><span data-ttu-id="6749c-265">Neúspěšná kalibrace</span><span class="sxs-lookup"><span data-stu-id="6749c-265">Calibration fails</span></span>

<span data-ttu-id="6749c-266">Kalibrace by měla fungovat pro většinu lidí, ale existují případy, kdy se kalibrace nezdařila.</span><span class="sxs-lookup"><span data-stu-id="6749c-266">Calibration should work for most people, but there are cases where calibration fails.</span></span>
  
<span data-ttu-id="6749c-267">Mezi případné důvody pro selhání kalibrace patří:</span><span class="sxs-lookup"><span data-stu-id="6749c-267">Some potential reasons for calibration failure include:</span></span>

- <span data-ttu-id="6749c-268">Odčítání a nikoli za cíle kalibrace</span><span class="sxs-lookup"><span data-stu-id="6749c-268">Getting distracted and not following the calibration targets</span></span>
- <span data-ttu-id="6749c-269">Nesprávné umístění zařízení hypervisoru nebo zařízení na začátku</span><span class="sxs-lookup"><span data-stu-id="6749c-269">Dirty or scratched device visor or device visor not positioned properly</span></span>
- <span data-ttu-id="6749c-270">Nezměněná nebo škrábancová skla</span><span class="sxs-lookup"><span data-stu-id="6749c-270">Dirty or scratched glasses</span></span>
- <span data-ttu-id="6749c-271">Určité typy kontaktních skel a brýle (barevná čočka, některá torica kontaktu, poblokovaná brýle, některá brýle s vysokým předpisem, Sunglasses nebo podobné)</span><span class="sxs-lookup"><span data-stu-id="6749c-271">Certain types of contact lenses and glasses (colored contact lenses, some toric contact lenses, IR blocking glasses, some high prescription glasses, sunglasses, or similar)</span></span>
- <span data-ttu-id="6749c-272">Více vyslovované strukturu a některá rozšíření eyelash</span><span class="sxs-lookup"><span data-stu-id="6749c-272">More-pronounced makeup and some eyelash extensions</span></span>
- <span data-ttu-id="6749c-273">Chlupy nebo silné eyeglass snímky, pokud si zařízení blokuje zobrazení očí</span><span class="sxs-lookup"><span data-stu-id="6749c-273">Hair or thick eyeglass frames if they're blocking the device from seeing your eyes</span></span>
- <span data-ttu-id="6749c-274">Určité Physiology oka, podmínky očí nebo oční chirurgie, jako je úzká oči, Long Eyelashes, amblyopia, nystagmus, některé případy LASIK nebo jiné oči surgeries</span><span class="sxs-lookup"><span data-stu-id="6749c-274">Certain eye physiology, eye conditions, or eye surgery such as narrow eyes, long eyelashes, amblyopia, nystagmus, some cases of LASIK or other eye surgeries</span></span>

<span data-ttu-id="6749c-275">Pokud kalibrace neproběhne úspěšně, zkuste:</span><span class="sxs-lookup"><span data-stu-id="6749c-275">If calibration is unsuccessful try:</span></span>

- <span data-ttu-id="6749c-276">Čištění zařízení s clonou</span><span class="sxs-lookup"><span data-stu-id="6749c-276">Cleaning your device visor</span></span>
- <span data-ttu-id="6749c-277">Čištění vašich brýle</span><span class="sxs-lookup"><span data-stu-id="6749c-277">Cleaning your glasses</span></span>
- <span data-ttu-id="6749c-278">Co nejblíže vašim očí vám umožní obzradit své zařízení.</span><span class="sxs-lookup"><span data-stu-id="6749c-278">Pushing your device visor as close to your eyes as possible</span></span>
- <span data-ttu-id="6749c-279">Přesun objektů ve vašem seznamu clony (například vlasy)</span><span class="sxs-lookup"><span data-stu-id="6749c-279">Moving objects in your visor out of the way (such as hair)</span></span>
- <span data-ttu-id="6749c-280">Zapnutí světla v místnosti nebo přemístění přímého slunečního záření</span><span class="sxs-lookup"><span data-stu-id="6749c-280">Turning on a light in your room or moving out of direct sunlight</span></span>

<span data-ttu-id="6749c-281">Pokud jste postupovali podle všech pokynů a kalibrace stále selhává, můžete výzvu k kalibraci zakázat v nastavení.</span><span class="sxs-lookup"><span data-stu-id="6749c-281">If you followed all guidelines and calibration is still failing, you can disable the calibration prompt in Settings.</span></span> <span data-ttu-id="6749c-282">Dejte nám taky vědět, že vám zašleme zpětnou vazbu v [centru Feedback](hololens-feedback.md).</span><span class="sxs-lookup"><span data-stu-id="6749c-282">Also let us know by filing feedback in [Feedback Hub](hololens-feedback.md).</span></span>

<span data-ttu-id="6749c-283">Podívejte se také na související informace o [barvě obrázku nebo odstraňování potíží s jasem.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span><span class="sxs-lookup"><span data-stu-id="6749c-283">Also see related information for [image color or brightness troubleshooting.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span></span>

<span data-ttu-id="6749c-284">Nastavení IPD se nedá použít pro HoloLens 2, protože pozice očí jsou vypočítané systémem.</span><span class="sxs-lookup"><span data-stu-id="6749c-284">Setting IPD is not applicable for HoloLens 2, since eye positions are computed by the system.</span></span> 

[<span data-ttu-id="6749c-285">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="6749c-285">Back to list</span></span>](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a><span data-ttu-id="6749c-286">Nelze se přihlásit, protože byl již dříve nastaven můj HoloLens pro někoho jiného.</span><span class="sxs-lookup"><span data-stu-id="6749c-286">Can't sign in because my HoloLens was previously set up for someone else</span></span>

<span data-ttu-id="6749c-287">Zařízení můžete [Přepnout do **režimu blikání** a obnovit zařízení pomocí pokročilého Průvodce obnovením](hololens-recovery.md#clean-reflash-the-device) .</span><span class="sxs-lookup"><span data-stu-id="6749c-287">You can [put the device into **Flashing Mode** and use Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device) to recover the device.</span></span>

[<span data-ttu-id="6749c-288">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="6749c-288">Back to list</span></span>](#list)


## <a name="unity-isnt-working"></a><span data-ttu-id="6749c-289">Unity nefunguje</span><span class="sxs-lookup"><span data-stu-id="6749c-289">Unity isn't working</span></span>

- <span data-ttu-id="6749c-290">Přečtěte si téma [Instalace nástrojů](/windows/mixed-reality/install-the-tools) pro nejaktuálnější verzi Unity, doporučená pro vývoj pro HoloLens.</span><span class="sxs-lookup"><span data-stu-id="6749c-290">See [Install the tools](/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="6749c-291">Známé problémy s nástrojem Unity HoloLens Technical Preview jsou popsány ve [fórech Unity pro HoloLens](https://forum.unity3d.com/threads/known-issues.394627/).</span><span class="sxs-lookup"><span data-stu-id="6749c-291">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

[<span data-ttu-id="6749c-292">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="6749c-292">Back to list</span></span>](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a><span data-ttu-id="6749c-293">Portál zařízení s Windows nepracuje správně.</span><span class="sxs-lookup"><span data-stu-id="6749c-293">Windows Device Portal isn't working correctly</span></span>

- <span data-ttu-id="6749c-294">Funkce Live Preview v rámci hybridního zachycení realit může při latenci vykazovat několik sekund.</span><span class="sxs-lookup"><span data-stu-id="6749c-294">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="6749c-295">Na stránce virtuálního vstupu nejsou funkční gesta a posuvníky v části virtuální gesta.</span><span class="sxs-lookup"><span data-stu-id="6749c-295">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="6749c-296">Jejich použití nebude mít žádný vliv.</span><span class="sxs-lookup"><span data-stu-id="6749c-296">Using them will have no effect.</span></span> <span data-ttu-id="6749c-297">Virtuální klávesnice na stránce virtuálního vstupu funguje správně.</span><span class="sxs-lookup"><span data-stu-id="6749c-297">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="6749c-298">Po povolení režimu vývojářů v nastavení může trvat několik sekund, než se zapne přepínač, aby se aktivoval portál zařízení.</span><span class="sxs-lookup"><span data-stu-id="6749c-298">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

[<span data-ttu-id="6749c-299">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="6749c-299">Back to list</span></span>](#list)

## <a name="emulator"></a><span data-ttu-id="6749c-300">Emulátor</span><span class="sxs-lookup"><span data-stu-id="6749c-300">Emulator</span></span>
### <a name="the-hololens-emulator-isnt-working"></a><span data-ttu-id="6749c-301">Emulátor HoloLens nefunguje</span><span class="sxs-lookup"><span data-stu-id="6749c-301">The HoloLens Emulator isn't working</span></span>

<span data-ttu-id="6749c-302">Informace o emulátoru HoloLens najdete v naší dokumentaci pro vývojáře.</span><span class="sxs-lookup"><span data-stu-id="6749c-302">Information about the HoloLens emulator is located in our developer documentation.</span></span>  <span data-ttu-id="6749c-303">Přečtěte si další [informace o řešení potíží s emulátorem HoloLens.](/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="6749c-303">Read more about [troubleshooting the HoloLens emulator](/windows/mixed-reality/using-the-hololens-emulator#troubleshooting).</span></span>


- <span data-ttu-id="6749c-304">Ne všechny aplikace v Microsoft Store jsou kompatibilní s emulátorem.</span><span class="sxs-lookup"><span data-stu-id="6749c-304">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="6749c-305">Například Young Conker a Fragmenty se v emulátoru nehrají.</span><span class="sxs-lookup"><span data-stu-id="6749c-305">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="6749c-306">V emulátoru nemůžete použít webovou kameru počítače.</span><span class="sxs-lookup"><span data-stu-id="6749c-306">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="6749c-307">Funkce Live Preview v Portál zařízení s Windows nefunguje s emulátorem.</span><span class="sxs-lookup"><span data-stu-id="6749c-307">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="6749c-308">Stále můžete zachytit Mixed Reality videa a obrázky.</span><span class="sxs-lookup"><span data-stu-id="6749c-308">You can still capture Mixed Reality videos and images.</span></span>

[<span data-ttu-id="6749c-309">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="6749c-309">Back to list</span></span>](#list)

## <a name="i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator"></a><span data-ttu-id="6749c-310">Nemůžu najít nebo použít klávesnici k zadání v emulátoru HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="6749c-310">I cannot find or use the keyboard to type in the HoloLens 2 Emulator</span></span>

<span data-ttu-id="6749c-311">*Připravujeme*</span><span class="sxs-lookup"><span data-stu-id="6749c-311">*Coming soon*</span></span>

[<span data-ttu-id="6749c-312">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="6749c-312">Back to list</span></span>](#list)

## <a name="voice-commands-arent-working"></a><span data-ttu-id="6749c-313">Nefungují hlasové příkazy</span><span class="sxs-lookup"><span data-stu-id="6749c-313">Voice commands aren't working</span></span>

<span data-ttu-id="6749c-314">Pokud Cortana nereaguje na vaše hlasové příkazy, ujistěte se, že je zapnutá Cortana.</span><span class="sxs-lookup"><span data-stu-id="6749c-314">If Cortana isn't responding to your voice commands, make sure Cortana is turned on.</span></span> <span data-ttu-id="6749c-315">V seznamu Všechny aplikace poznámkového bloku **nabídky Cortany** proveďte  >    >    >   změny.</span><span class="sxs-lookup"><span data-stu-id="6749c-315">On the All apps list, select **Cortana** > **Menu** > **Notebook** > **Settings** to make changes.</span></span> <span data-ttu-id="6749c-316">Další informace o tom, co můžete říct, najdete v [tématu Použití hlasu s HoloLens.](hololens-cortana.md)</span><span class="sxs-lookup"><span data-stu-id="6749c-316">To learn more about what you can say, see [Use your voice with HoloLens](hololens-cortana.md).</span></span>

<span data-ttu-id="6749c-317">V HoloLens (1. generace) není integrované rozpoznávání řeči konfigurovatelné.</span><span class="sxs-lookup"><span data-stu-id="6749c-317">On HoloLens (1st gen), built-in speech recognition is not configurable.</span></span> <span data-ttu-id="6749c-318">Vždy je zapnutý.</span><span class="sxs-lookup"><span data-stu-id="6749c-318">It is always turned on.</span></span> <span data-ttu-id="6749c-319">Na HoloLens 2 můžete zvolit, jestli se má při nastavování zařízení zapnout rozpoznávání řeči i Cortana.</span><span class="sxs-lookup"><span data-stu-id="6749c-319">On HoloLens 2, you can choose whether to turn on both speech recognition and Cortana during device setup.</span></span>

<span data-ttu-id="6749c-320">Pokud HoloLens 2 nereaguje na váš hlas, ujistěte se, že je zapnuté rozpoznávání řeči.</span><span class="sxs-lookup"><span data-stu-id="6749c-320">If your HoloLens 2 is not responding to your voice, make sure Speech recognition is turned on.</span></span> <span data-ttu-id="6749c-321">Přejděte na **Start Settings** Privacy Speech  >    >  **(Spustit nastavení ochrany**  >  **osobních údajů) Speech** a zapněte **rozpoznávání řeči.**</span><span class="sxs-lookup"><span data-stu-id="6749c-321">Go to **Start** > **Settings** > **Privacy** > **Speech** and turn on **Speech recognition**.</span></span>

[<span data-ttu-id="6749c-322">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="6749c-322">Back to list</span></span>](#list)

## <a name="hand-input-isnt-working"></a><span data-ttu-id="6749c-323">Ruční vstup nefunguje</span><span class="sxs-lookup"><span data-stu-id="6749c-323">Hand input isn't working</span></span>

<span data-ttu-id="6749c-324">Abyste zajistili, že HoloLens uvidí vaše ruce, musíte je ponechat v snímku gest.</span><span class="sxs-lookup"><span data-stu-id="6749c-324">To ensure that HoloLens can see your hands, you need to keep them in the gesture frame.</span></span>  <span data-ttu-id="6749c-325">Domovská Mixed Reality poskytuje zpětnou vazbu, která vám dá vědět, kdy jsou vaše ruce sledované.</span><span class="sxs-lookup"><span data-stu-id="6749c-325">The Mixed Reality Home provides feedback that lets you know when your hands are tracked.</span></span>  <span data-ttu-id="6749c-326">Názory na různé verze HoloLens se liší:</span><span class="sxs-lookup"><span data-stu-id="6749c-326">The feedback is different on different versions of HoloLens:</span></span>
- <span data-ttu-id="6749c-327">V HoloLens (1. generace) se kurzor pohledu změní z tečky na kruh.</span><span class="sxs-lookup"><span data-stu-id="6749c-327">On HoloLens (1st gen), the gaze cursor changes from a dot to a ring</span></span>
- <span data-ttu-id="6749c-328">Na HoloLensu 2 se zobrazí kurzor prstu, když je vaše ruce blízko slate, a když jsou břidíčky dále, zobrazí se ruční paprsk.</span><span class="sxs-lookup"><span data-stu-id="6749c-328">On HoloLens 2, a fingertip cursor appears when your hand is close to a slate, and a hand ray appears when slates are further away</span></span>

<span data-ttu-id="6749c-329">Řada imerzivních aplikací dodržuje vzory vstupu, které se podobají Mixed Reality Domovské obrazovce.</span><span class="sxs-lookup"><span data-stu-id="6749c-329">Many immersive apps follow input patterns that are similar to Mixed Reality Home.</span></span>  <span data-ttu-id="6749c-330">Přečtěte si další informace o použití ručního vstupu [v HoloLens (1. generace)](hololens1-basic-usage.md#use-hololens-with-your-hands) a [HoloLens 2.](hololens2-basic-usage.md#the-hand-tracking-frame)</span><span class="sxs-lookup"><span data-stu-id="6749c-330">Learn more about using hand input on [HoloLens (1st gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) and [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span></span>

<span data-ttu-id="6749c-331">Pokud máte problémy s nosem, mějte na vědomí, že některé typy choumů nefungují se sledováním rukou.</span><span class="sxs-lookup"><span data-stu-id="6749c-331">If you are wearing gloves, note that some types of gloves do not work with hand tracking.</span></span>  <span data-ttu-id="6749c-332">Běžným příkladem je černá guma, která obvykle absorbuje infračervené světlo a nenabírá je hloubková kamera.</span><span class="sxs-lookup"><span data-stu-id="6749c-332">A common example is black rubber gloves, which tend to absorb infrared light and are not picked up by the depth camera.</span></span>  <span data-ttu-id="6749c-333">Pokud vaše práce zahrnuje gumové gumy, doporučujeme, abyste si zkusili světlejší barvu, například modrou nebo šedou.</span><span class="sxs-lookup"><span data-stu-id="6749c-333">If your work involves rubber gloves, we recommend trying a lighter color such as blue or gray.</span></span>  <span data-ttu-id="6749c-334">Dalším příkladem je velká nesrozumilá aplikace, která má tendenci zakrytí tvaru vaší ruky.</span><span class="sxs-lookup"><span data-stu-id="6749c-334">Another example is large baggy gloves, which tend to obscure the shape of your hand.</span></span> <span data-ttu-id="6749c-335">Pro nejlepší výsledky doporučujeme použít co nejvíce tvarování.</span><span class="sxs-lookup"><span data-stu-id="6749c-335">We recommend using gloves that are as form-fitting as possible for best results.</span></span>

<span data-ttu-id="6749c-336">Pokud má váš vizuátor otisky prstů nebo šmouhy, vyčistěte vizuály pomocí mikrovlákna, které jste dodáli s HoloLens.</span><span class="sxs-lookup"><span data-stu-id="6749c-336">If your visor has fingerprints or smudges, use the microfiber cleaning cloth that came with the HoloLens to clean your visor gently.</span></span>

[<span data-ttu-id="6749c-337">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="6749c-337">Back to list</span></span>](#list)

## <a name="cant-connect-to-wi-fi"></a><span data-ttu-id="6749c-338">Nelze se připojit k Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="6749c-338">Can't connect to Wi-Fi</span></span>

<span data-ttu-id="6749c-339">Tady je několik věcí, které můžete vyzkoušet, pokud nemůžete holoLens připojit k Wi-Fi síti:</span><span class="sxs-lookup"><span data-stu-id="6749c-339">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

- <span data-ttu-id="6749c-340">Ujistěte se, Wi-Fi je zapnuté.</span><span class="sxs-lookup"><span data-stu-id="6749c-340">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="6749c-341">Kontrolu můžete provést pomocí gesta Start a pak vyberte  >  **NastaveníSítě &amp; Internet**  >  **Wi-Fi.**</span><span class="sxs-lookup"><span data-stu-id="6749c-341">To check, use the Start gesture, then select **Settings** > **Network &amp; Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="6749c-342">Pokud Wi-Fi, zkuste ho vypnout a znovu zas.</span><span class="sxs-lookup"><span data-stu-id="6749c-342">If Wi-Fi is on, try turning it off and then on again.</span></span>
- <span data-ttu-id="6749c-343">Přesuňte se blíže ke směrovači nebo přístupovému bodu.</span><span class="sxs-lookup"><span data-stu-id="6749c-343">Move closer to the router or access point.</span></span>
- <span data-ttu-id="6749c-344">Restartujte svůj Wi-Fi směrovač a [pak restartujte HoloLens.](hololens-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="6749c-344">Restart your Wi-Fi router, then [restart HoloLens](hololens-recovery.md).</span></span> <span data-ttu-id="6749c-345">Zkuste se připojit znovu.</span><span class="sxs-lookup"><span data-stu-id="6749c-345">Try connecting again.</span></span>
- <span data-ttu-id="6749c-346">Pokud nic z toho nefunguje, zkontrolujte, že váš směrovač používá nejnovější firmware.</span><span class="sxs-lookup"><span data-stu-id="6749c-346">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="6749c-347">Tyto informace najdete na webu výrobce.</span><span class="sxs-lookup"><span data-stu-id="6749c-347">You can find this information on the manufacturer website.</span></span>

[<span data-ttu-id="6749c-348">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="6749c-348">Back to list</span></span>](#list)
## <a name="bluetooth-devices-arent-pairing"></a><span data-ttu-id="6749c-349">Zařízení Bluetooth se neschová</span><span class="sxs-lookup"><span data-stu-id="6749c-349">Bluetooth devices aren't pairing</span></span>

<span data-ttu-id="6749c-350">Pokud máte problémy s [párování zařízení Bluetooth,](hololens-connect-devices.md)zkuste následující postup:</span><span class="sxs-lookup"><span data-stu-id="6749c-350">If you're having problems [pairing a Bluetooth device](hololens-connect-devices.md), try the following:</span></span>

- <span data-ttu-id="6749c-351">Přejděte na **Nastavení** Zařízení a  >  ujistěte se, že je zapnuté Bluetooth.</span><span class="sxs-lookup"><span data-stu-id="6749c-351">Go to **Settings** > **Devices**, and make sure that Bluetooth is turned on.</span></span> <span data-ttu-id="6749c-352">Pokud je, vypněte ho a znovu ho zapněte.</span><span class="sxs-lookup"><span data-stu-id="6749c-352">If it is, turn it off and on again.</span></span>
- <span data-ttu-id="6749c-353">Ujistěte se, že je vaše zařízení Bluetooth plně nabité nebo je nabité čerstvými bateriemi.</span><span class="sxs-lookup"><span data-stu-id="6749c-353">Make sure that your Bluetooth device is fully charged or has fresh batteries.</span></span>
- <span data-ttu-id="6749c-354">Pokud se stále nemůžete připojit, [restartujte HoloLens.](hololens-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="6749c-354">If you still can't connect, [restart the HoloLens](hololens-recovery.md).</span></span>

[<span data-ttu-id="6749c-355">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="6749c-355">Back to list</span></span>](#list)

## <a name="usb-c-microphone-isnt-working"></a><span data-ttu-id="6749c-356">Mikrofon USB-C nefunguje</span><span class="sxs-lookup"><span data-stu-id="6749c-356">USB-C Microphone isn't working</span></span>
<span data-ttu-id="6749c-357">Uvědomte si, že některé mikrofony USB-C se nesprávně hlásí jako *mikrofon* i jako mluvčí.</span><span class="sxs-lookup"><span data-stu-id="6749c-357">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="6749c-358">Jedná se o problém s mikrofonem, a ne s HoloLensem.</span><span class="sxs-lookup"><span data-stu-id="6749c-358">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="6749c-359">Při připojování jednoho z těchto mikrofonů k HoloLens může dojít ke ztrátě zvuku.</span><span class="sxs-lookup"><span data-stu-id="6749c-359">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="6749c-360">Naštěstí existuje jednoduchá oprava.</span><span class="sxs-lookup"><span data-stu-id="6749c-360">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="6749c-361">V **nastavení**  ->  **Zvuk**  ->  **systému** explicitně nastavte předdefinování **mluvčích (zvukový ovladač analogové funkce)** jako **výchozí zařízení.**</span><span class="sxs-lookup"><span data-stu-id="6749c-361">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="6749c-362">HoloLens by si toto nastavení měl zapamatovat, i když se mikrofon později odebere a znovu připojí.</span><span class="sxs-lookup"><span data-stu-id="6749c-362">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![Řešení potíží s mikrofony USB-C](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a><span data-ttu-id="6749c-364">Zařízení uvedená jako dostupná v Nastavení nefungují</span><span class="sxs-lookup"><span data-stu-id="6749c-364">Devices listed as available in Settings don't work</span></span>

<span data-ttu-id="6749c-365">HoloLens (1. generace) nepodporuje zvukové profily Bluetooth.</span><span class="sxs-lookup"><span data-stu-id="6749c-365">HoloLens (1st gen) doesn't support Bluetooth audio profiles.</span></span> <span data-ttu-id="6749c-366">Zvuková zařízení Bluetooth, jako jsou mluvčí a náhlavní soupravy, se dají zobrazit jako dostupná v nastavení HoloLens, ale nejsou podporovaná.</span><span class="sxs-lookup"><span data-stu-id="6749c-366">Bluetooth audio devices, such as speakers and headsets, may appear as available in HoloLens settings, but they aren't supported.</span></span>

<span data-ttu-id="6749c-367">HoloLens 2 podporuje zvukový profil Bluetooth A2DP pro stereo přehrávání.</span><span class="sxs-lookup"><span data-stu-id="6749c-367">HoloLens 2 supports the Bluetooth A2DP audio profile for stereo playback.</span></span> <span data-ttu-id="6749c-368">Profil Bluetooth Hands Free, který umožňuje zachytávání mikrofonu z periferního zařízení Bluetooth, není na HoloLens 2 podporovaný.</span><span class="sxs-lookup"><span data-stu-id="6749c-368">The Bluetooth Hands Free profile which enables microphone capture from a Bluetooth peripheral is not supported on HoloLens 2.</span></span>

<span data-ttu-id="6749c-369">Pokud máte potíže s používáním zařízení Bluetooth, ujistěte se, že se jedná o podporované zařízení.</span><span class="sxs-lookup"><span data-stu-id="6749c-369">If you're having trouble using a Bluetooth device, make sure that it's a supported device.</span></span> <span data-ttu-id="6749c-370">Mezi podporovaná zařízení patří:</span><span class="sxs-lookup"><span data-stu-id="6749c-370">Supported devices include the following:</span></span>

- <span data-ttu-id="6749c-371">Klávesnice QWERTY bluetooth v anglickém jazyce (můžete je použít kdekoli, kde používáte holografičovou klávesnici).</span><span class="sxs-lookup"><span data-stu-id="6749c-371">English-language QWERTY Bluetooth keyboards (you can use these anywhere that you use the holographic keyboard).</span></span>
- <span data-ttu-id="6749c-372">Bluetooth mice.</span><span class="sxs-lookup"><span data-stu-id="6749c-372">Bluetooth mice.</span></span>
- <span data-ttu-id="6749c-373">Kliknutí [na HoloLens](hololens1-clicker.md)</span><span class="sxs-lookup"><span data-stu-id="6749c-373">The [HoloLens clicker](hololens1-clicker.md).</span></span>

<span data-ttu-id="6749c-374">S HoloLens můžete spárovat další zařízení BLUETOOTH HID a PAIR.</span><span class="sxs-lookup"><span data-stu-id="6749c-374">You can pair other Bluetooth HID and GATT devices together with your HoloLens.</span></span> <span data-ttu-id="6749c-375">Je však možné, že budete muset nainstalovat odpovídající doprovodné aplikace z Microsoft Store, aby bylo možné zařízení skutečně používat.</span><span class="sxs-lookup"><span data-stu-id="6749c-375">However, you may have to install corresponding companion apps from Microsoft Store to actually use the devices.</span></span>

[<span data-ttu-id="6749c-376">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="6749c-376">Back to list</span></span>](#list)
