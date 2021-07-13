---
title: HoloLens Řešení potíží se zařízeními
description: Získejte aktuální informace o nejběžnějších řešeních pro HoloLens a řešení potíží.
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
ms.openlocfilehash: b07514e73e43d267aa856c0fb9a256448e565000
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635445"
---
# <a name="device-troubleshooting"></a><span data-ttu-id="e3277-104">Řešení potíží se zařízeními</span><span class="sxs-lookup"><span data-stu-id="e3277-104">Device Troubleshooting</span></span>

<span data-ttu-id="e3277-105">Tento článek popisuje, jak vyřešit několik běžných HoloLens problémů.</span><span class="sxs-lookup"><span data-stu-id="e3277-105">This article describes how to resolve several common HoloLens issues.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="e3277-106">Než začnete s řešením potíží, ujistěte se, že je vaše zařízení naúčtované **na 20 až 40** % kapacity baterie, pokud je to možné.</span><span class="sxs-lookup"><span data-stu-id="e3277-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="e3277-107">Indikátory [baterie umístěné](hololens2-setup.md#lights-that-indicate-the-battery-level) pod tlačítkem napájení jsou rychlým způsobem, jak ověřit kapacitu baterie bez přihlášení k zařízení.</span><span class="sxs-lookup"><span data-stu-id="e3277-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<a id="list"></a>

<span data-ttu-id="e3277-108">**Známé problémy**</span><span class="sxs-lookup"><span data-stu-id="e3277-108">**Known Issues**</span></span>
- [<span data-ttu-id="e3277-109">Video remote assist se zablokuje po 20 minutách</span><span class="sxs-lookup"><span data-stu-id="e3277-109">Remote Assist video freezes after 20 minutes</span></span>](#remote-assist-video-freezes-after-20-minutes)
- [<span data-ttu-id="e3277-110">Automatické přihlášení žádá o přihlášení</span><span class="sxs-lookup"><span data-stu-id="e3277-110">Auto-login asks for log-in</span></span>](#auto-login-asks-for-log-in)
- [<span data-ttu-id="e3277-111">Microsoft Edge spuštění se nepovede</span><span class="sxs-lookup"><span data-stu-id="e3277-111">Microsoft Edge fails to launch</span></span>](#microsoft-edge-fails-to-launch)
- [<span data-ttu-id="e3277-112">Klávesnice se přepne na speciální znaky</span><span class="sxs-lookup"><span data-stu-id="e3277-112">Keyboard doesn't switch to special characters</span></span>](#keyboard-doesnt-switch-to-special-characters)
- [<span data-ttu-id="e3277-113">Při stahování uzamčených souborů se nez zobrazení chyby</span><span class="sxs-lookup"><span data-stu-id="e3277-113">Downloading locked files doesn't show error</span></span>](#downloading-locked-files-doesnt-error)
- [<span data-ttu-id="e3277-114">Portál zařízení nahrání nebo stažení souboru</span><span class="sxs-lookup"><span data-stu-id="e3277-114">Device Portal file upload/download times out</span></span>](#device-portal-file-uploaddownload-times-out)
- [<span data-ttu-id="e3277-115">Modrá obrazovka po zrušení registrace z insider ve verzi Preview na zařízení blikající sestavením Insider</span><span class="sxs-lookup"><span data-stu-id="e3277-115">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [<span data-ttu-id="e3277-116">OneDrive automaticky nenahraje obrázky</span><span class="sxs-lookup"><span data-stu-id="e3277-116">OneDrive doesn't automatically upload pictures</span></span>](#onedrive-doesnt-automatically-upload-pictures)

<span data-ttu-id="e3277-117">**Obecné**</span><span class="sxs-lookup"><span data-stu-id="e3277-117">**General**</span></span>
- [<span data-ttu-id="e3277-118">HoloLens nereaguje nebo se nespustí</span><span class="sxs-lookup"><span data-stu-id="e3277-118">HoloLens is unresponsive or won't start</span></span>](#hololens-is-unresponsive-or-wont-start)
- [<span data-ttu-id="e3277-119">Chyba Nedostatek místa na disku</span><span class="sxs-lookup"><span data-stu-id="e3277-119">"Low Disk Space" error</span></span>](#low-disk-space-error)
- [<span data-ttu-id="e3277-120">Selhání selhání</span><span class="sxs-lookup"><span data-stu-id="e3277-120">Calibration Fails</span></span>](#calibration-fails)
- [<span data-ttu-id="e3277-121">Nemůžu se přihlásit, protože moje HoloLens byla dříve nastavená pro někoho jiného</span><span class="sxs-lookup"><span data-stu-id="e3277-121">Can't sign in because my HoloLens was previously set up for someone else</span></span>](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [<span data-ttu-id="e3277-122">Unity nefunguje</span><span class="sxs-lookup"><span data-stu-id="e3277-122">Unity isn't working</span></span>](#unity-isnt-working)
- [<span data-ttu-id="e3277-123">Windows Portál zařízení nefunguje správně</span><span class="sxs-lookup"><span data-stu-id="e3277-123">Windows Device Portal isn't working correctly</span></span>](#windows-device-portal-isnt-working-correctly)
- [<span data-ttu-id="e3277-124">HoloLens Emulator nefunguje</span><span class="sxs-lookup"><span data-stu-id="e3277-124">The HoloLens Emulator isn't working</span></span>](#the-hololens-emulator-isnt-working)

<span data-ttu-id="e3277-125">**Vstup**</span><span class="sxs-lookup"><span data-stu-id="e3277-125">**Input**</span></span>
- [<span data-ttu-id="e3277-126">Nefungují hlasové příkazy</span><span class="sxs-lookup"><span data-stu-id="e3277-126">Voice commands aren't working</span></span>](#voice-commands-arent-working)
- [<span data-ttu-id="e3277-127">Ruční vstup nefunguje</span><span class="sxs-lookup"><span data-stu-id="e3277-127">Hand input isn't working</span></span>](#hand-input-isnt-working)

<span data-ttu-id="e3277-128">**Připojení**</span><span class="sxs-lookup"><span data-stu-id="e3277-128">**Connectivity**</span></span>
- [<span data-ttu-id="e3277-129">Nelze se připojit k Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="e3277-129">Can't connect to Wi-Fi</span></span>](#cant-connect-to-wi-fi)

<span data-ttu-id="e3277-130">**Externí zařízení**</span><span class="sxs-lookup"><span data-stu-id="e3277-130">**External Devices**</span></span> 
- [<span data-ttu-id="e3277-131">Bluetooth zařízení se ne párují</span><span class="sxs-lookup"><span data-stu-id="e3277-131">Bluetooth devices aren't pairing</span></span>](#bluetooth-devices-arent-pairing)
- [<span data-ttu-id="e3277-132">Mikrofon USB-C nefunguje</span><span class="sxs-lookup"><span data-stu-id="e3277-132">USB-C Microphone isn't working</span></span>](#usb-c-microphone-isnt-working)
- [<span data-ttu-id="e3277-133">Zařízení uvedená jako dostupná v Nastavení nefungují</span><span class="sxs-lookup"><span data-stu-id="e3277-133">Devices listed as available in Settings don't work</span></span>](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a><span data-ttu-id="e3277-134">Video remote assist se zablokuje po 20 minutách</span><span class="sxs-lookup"><span data-stu-id="e3277-134">Remote Assist video freezes after 20 minutes</span></span>

> [!NOTE]
> <span data-ttu-id="e3277-135">K dispozici je novější verze vzdáleného nástroje Remote Assist, která obsahuje opravu tohoto problému.</span><span class="sxs-lookup"><span data-stu-id="e3277-135">There is a newer version of Remote Assist which has a fix for this issue.</span></span> <span data-ttu-id="e3277-136">Aktualizujte [službu Remote Assist](holographic-store-apps.md#update-apps) na nejnovější verzi, abyste se tomuto problému vyhnuli.</span><span class="sxs-lookup"><span data-stu-id="e3277-136">Please [update Remote Assist](holographic-store-apps.md#update-apps) to the latest version to avoid this issue.</span></span>

> [!NOTE]
> <span data-ttu-id="e3277-137">Vzhledem k závažnosti tohoto známého problému jsme dočasně pozastavil dostupnost Windows Holographic verze 21H1.</span><span class="sxs-lookup"><span data-stu-id="e3277-137">Due to this Known Issue's severity we had temporarily paused the availability of Windows Holographic, version 21H1.</span></span> <span data-ttu-id="e3277-138">Sestavení 21H1 je teď opět k dispozici, takže zařízení je možné znovu aktualizovat na nejnovější build 21H1.</span><span class="sxs-lookup"><span data-stu-id="e3277-138">The 21H1 build is now available again, so devices may once again be updated to the latest 21H1 build.</span></span>

<span data-ttu-id="e3277-139">V nejnovější verzi [Windows Holographic verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1)zaznamenali někteří uživatelé Vzdálené pomoci zamrznutí videa během 20 minut.</span><span class="sxs-lookup"><span data-stu-id="e3277-139">On the latest release of [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), some users of Remote Assist have experienced video freezing during calls over 20 minutes.</span></span> <span data-ttu-id="e3277-140">Jedná se o **známý problém.**</span><span class="sxs-lookup"><span data-stu-id="e3277-140">This is a **known issue**.</span></span>

### <a name="workarounds"></a><span data-ttu-id="e3277-141">Alternativní řešení</span><span class="sxs-lookup"><span data-stu-id="e3277-141">Workarounds</span></span>

<span data-ttu-id="e3277-142">Pokud nemůžete aplikaci Remote Assist aktualizovat na novější sestavení, vyzkoušejte následující postup.</span><span class="sxs-lookup"><span data-stu-id="e3277-142">If you are unable to update Remote Assist to a newer build try the following work around.</span></span>

#### <a name="restart-in-between-calls"></a><span data-ttu-id="e3277-143">Restartování mezi voláními</span><span class="sxs-lookup"><span data-stu-id="e3277-143">Restart in between calls</span></span>

<span data-ttu-id="e3277-144">Pokud vaše volání přesájí 20 minut a dochází k tomuto problému, zkuste zařízení restartovat.</span><span class="sxs-lookup"><span data-stu-id="e3277-144">If your calls are going over a length of 20 minutes and you are experiencing this issue, try rebooting your device.</span></span> <span data-ttu-id="e3277-145">Restartováním zařízení mezi voláními vzdálené pomoci obnovíte zařízení a vrátíte ho do dobrého stavu.</span><span class="sxs-lookup"><span data-stu-id="e3277-145">Rebooting your device between Remote Assist calls will refresh your device and put it back into a good state.</span></span>

<span data-ttu-id="e3277-146">Pokud chcete rychle restartovat zařízení na Windows Holographic, otevřete nabídku Start verze [21H1,](hololens-release-notes.md#windows-holographic-version-21h1) vyberte ikonu uživatele a pak vyberte **Restartovat.**</span><span class="sxs-lookup"><span data-stu-id="e3277-146">To quickly restart a device on [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) open the start menu, and select the user icon, then select **Restart**.</span></span>

[<span data-ttu-id="e3277-147">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="e3277-147">Back to list</span></span>](#list)

## <a name="auto-login-asks-for-log-in"></a><span data-ttu-id="e3277-148">Automatické přihlášení žádá o přihlášení</span><span class="sxs-lookup"><span data-stu-id="e3277-148">Auto-login asks for log-in</span></span>

<span data-ttu-id="e3277-149">Zařízení HoloLens 2 je možné nakonfigurovat tak, aby se automaticky přihlašuje přes **možnosti** přihlášení k účtům Nastavení -> a v části Povinné nastavovat hodnotu  ->    ->   **na Nikdy.** </span><span class="sxs-lookup"><span data-stu-id="e3277-149">A HoloLens 2 device can be configured to automatically login in via **Settings** -> **Accounts** -> **Sign-in Options** -> and under **Required** setting the value to **Never**.</span></span> <span data-ttu-id="e3277-150">Někteří uživatelé se při aktualizaci zařízení s podstatně velkou aktualizací, jako je třeba aktualizace funkcí, mohou znova přihlásit k zařízení.</span><span class="sxs-lookup"><span data-stu-id="e3277-150">Some users may be required to log-in to the device again when updating a device with a substantially large update, such as a feature update.</span></span> <span data-ttu-id="e3277-151">Jedná se o **známý problém.**</span><span class="sxs-lookup"><span data-stu-id="e3277-151">This is a **known issue**.</span></span>

<span data-ttu-id="e3277-152">Příklad, kdy k tomu může dojít:</span><span class="sxs-lookup"><span data-stu-id="e3277-152">Example of when this could occur:</span></span>

- <span data-ttu-id="e3277-153">Aktualizace zařízení z Windows Holographic verze 2004 (build 19041.xxxx) na Windows Holographic verze 21H1 (build 20346.xxxx)</span><span class="sxs-lookup"><span data-stu-id="e3277-153">Updating a device from Windows Holographic, version 2004 (Build 19041.xxxx) to Windows Holographic, version 21H1 (Build 20346.xxxx)</span></span>
- <span data-ttu-id="e3277-154">Aktualizace zařízení tak, aby se ve stejném hlavním buildu, např. Windows Holographic, verze 2004, Windows Holographic, verze 20H2</span><span class="sxs-lookup"><span data-stu-id="e3277-154">Updating a device to take a large update on the same major build, e.g. Windows Holographic, version 2004 to Windows Holographic, version 20H2</span></span>
- <span data-ttu-id="e3277-155">Aktualizace zařízení z image továrny na nejnovější image</span><span class="sxs-lookup"><span data-stu-id="e3277-155">Updating a device from a factory image to the latest image</span></span>

<span data-ttu-id="e3277-156">K tomu by nemělo dojít během těchto období:</span><span class="sxs-lookup"><span data-stu-id="e3277-156">This should not occur during:</span></span>

- <span data-ttu-id="e3277-157">Zařízení, která mají měsíční servisní aktualizaci</span><span class="sxs-lookup"><span data-stu-id="e3277-157">Devices taking a monthly servicing update</span></span>

<span data-ttu-id="e3277-158">Alternativní metody:</span><span class="sxs-lookup"><span data-stu-id="e3277-158">Work around methods:</span></span>

- <span data-ttu-id="e3277-159">Metody přihlášení, jako jsou PIN, heslo, Iris, webové ověřování nebo klíče FIDO2.</span><span class="sxs-lookup"><span data-stu-id="e3277-159">Sign-in methods such as PIN, Password, Iris, Web Authentication, or FIDO2 keys.</span></span>
- <span data-ttu-id="e3277-160">Pokud pin kód zařízení nelze zapamatovat a jiné metody ověřování nejsou k dispozici, může uživatel použít režim [ručního lomítka](hololens-recovery.md#manual-procedure).</span><span class="sxs-lookup"><span data-stu-id="e3277-160">If device PIN cannot be remembered, and other authentication methods are not available, then a user can use [manual reflashing mode](hololens-recovery.md#manual-procedure).</span></span>

[<span data-ttu-id="e3277-161">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="e3277-161">Back to list</span></span>](#list)

## <a name="microsoft-edge-fails-to-launch"></a><span data-ttu-id="e3277-162">Microsoft Edge spuštění se nepovede</span><span class="sxs-lookup"><span data-stu-id="e3277-162">Microsoft Edge fails to launch</span></span>

> [!NOTE]
> <span data-ttu-id="e3277-163">Tento problém byl původně vytvořen s Microsoft Edge verzí.</span><span class="sxs-lookup"><span data-stu-id="e3277-163">This issue was originally created with the shipping version of Microsoft Edge in-mind.</span></span> <span data-ttu-id="e3277-164">Tento problém se může vyřešit v [nové Microsoft Edge](hololens-new-edge.md).</span><span class="sxs-lookup"><span data-stu-id="e3277-164">This issue may be resolved in the [new Microsoft Edge](hololens-new-edge.md).</span></span> <span data-ttu-id="e3277-165">Pokud ne, zpětnou vazbu nahlaste.</span><span class="sxs-lookup"><span data-stu-id="e3277-165">If it is not, please file feedback.</span></span>

<span data-ttu-id="e3277-166">Několik zákazníků nahlásilo problém, kdy Microsoft Edge spuštění.</span><span class="sxs-lookup"><span data-stu-id="e3277-166">A few customers have reported an issue where Microsoft Edge fails to launch.</span></span> <span data-ttu-id="e3277-167">U těchto zákazníků problém přetrvává i po restartování a nevyřeší se Windows aktualizacemi aplikací.</span><span class="sxs-lookup"><span data-stu-id="e3277-167">For these customers, the issue persists through reboot and is not resolved with Windows or application updates.</span></span> <span data-ttu-id="e3277-168">Pokud k tomuto problému dochází a potvrdili jste, že Windows je [aktuální,](hololens-updates.md#manually-check-for-updates)zakažte chybu z aplikace [Centrum Feedback](hololens-feedback.md) s následující kategorií a podkate kategorií: Instalace a aktualizace > Stahování, instalace a konfigurace Windows Update.</span><span class="sxs-lookup"><span data-stu-id="e3277-168">If you're experiencing this issue and you've confirmed [Windows is up-to-date](hololens-updates.md#manually-check-for-updates), please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.</span></span>

<span data-ttu-id="e3277-169">Neexistují žádná známá alternativní řešení, protože zatím jsme nemohli hlavní příčinu problému.</span><span class="sxs-lookup"><span data-stu-id="e3277-169">There are no known workarounds as we've been unable to root cause the issue so far.</span></span> <span data-ttu-id="e3277-170">S vyšetřováním vám pomůže Centrum Feedback chyb prostřednictvím webu společnosti.</span><span class="sxs-lookup"><span data-stu-id="e3277-170">Filing a bug via Feedback Hub will help our investigation!</span></span> <span data-ttu-id="e3277-171">Jedná se o **známý problém.**</span><span class="sxs-lookup"><span data-stu-id="e3277-171">This is a **known issue**.</span></span>

[<span data-ttu-id="e3277-172">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="e3277-172">Back to list</span></span>](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a><span data-ttu-id="e3277-173">Klávesnice se přepne na speciální znaky</span><span class="sxs-lookup"><span data-stu-id="e3277-173">Keyboard doesn't switch to special characters</span></span>

<span data-ttu-id="e3277-174">Při ooBE dochází k problému, kdy se po zvolení pracovního nebo školního účtu a zadání hesla uživatel pokouší přepnout na speciální znaky na klávesnici klepnutím na tlačítko &123, se nezmění na speciální znaky.</span><span class="sxs-lookup"><span data-stu-id="e3277-174">There is an issue during OOBE, where once the user has chosen a work or school account and is entering their password, trying to switch to the special characters on the keyboard by tapping the &123 button does not change to special characters.</span></span> <span data-ttu-id="e3277-175">Jedná se o **známý problém.**</span><span class="sxs-lookup"><span data-stu-id="e3277-175">This is a **known issue**.</span></span>

<span data-ttu-id="e3277-176">Obchádky:</span><span class="sxs-lookup"><span data-stu-id="e3277-176">Work-arounds:</span></span>
-   <span data-ttu-id="e3277-177">Zavřete klávesnici a znovu ji otevřete klepnutím na textové pole.</span><span class="sxs-lookup"><span data-stu-id="e3277-177">Close the keyboard and reopen it by tapping the text field.</span></span>
-   <span data-ttu-id="e3277-178">Nesprávně zadejte heslo.</span><span class="sxs-lookup"><span data-stu-id="e3277-178">Incorrectly enter your password.</span></span> <span data-ttu-id="e3277-179">Při příštím spuštění klávesnice bude klávesnice fungovat podle očekávání.</span><span class="sxs-lookup"><span data-stu-id="e3277-179">When the keyboard is relaunched next time it will then work as expected.</span></span>
- <span data-ttu-id="e3277-180">Webové ověřování, zavřete klávesnici a vyberte **Přihlásit se z jiného zařízení**.</span><span class="sxs-lookup"><span data-stu-id="e3277-180">Web Authentication, close the keyboard and select **Sign in from another device**.</span></span>
-   <span data-ttu-id="e3277-181">Pokud zadáváte jenom čísla, uživatel může stisknutím a podržením určitých kláves otevřít rozbalenou nabídku.</span><span class="sxs-lookup"><span data-stu-id="e3277-181">If entering only numbers, a user may press and hold certain keys to open an expanded menu.</span></span>
-   <span data-ttu-id="e3277-182">Pomocí klávesnice USB.</span><span class="sxs-lookup"><span data-stu-id="e3277-182">Using a USB keyboard.</span></span>

<span data-ttu-id="e3277-183">To nemá vliv na:</span><span class="sxs-lookup"><span data-stu-id="e3277-183">This does not affect:</span></span>
- <span data-ttu-id="e3277-184">Uživatelé, kteří se rozhodnout použít osobní účet.</span><span class="sxs-lookup"><span data-stu-id="e3277-184">Users who choose to use a personal account.</span></span>

[<span data-ttu-id="e3277-185">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="e3277-185">Back to list</span></span>](#list)

## <a name="downloading-locked-files-doesnt-error"></a><span data-ttu-id="e3277-186">Při stahování uzamčených souborů se ne zobrazí chyba</span><span class="sxs-lookup"><span data-stu-id="e3277-186">Downloading locked files doesn't error</span></span>

> [!NOTE]
> <span data-ttu-id="e3277-187">Jedná se o **známý problém,** který je opraven Windows Insider verze 20348.1403.</span><span class="sxs-lookup"><span data-stu-id="e3277-187">This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span>

<span data-ttu-id="e3277-188">V předchozích sestaveních Windows Holographic by výsledkem pokusu o stažení uzamčeného souboru byla chybová stránka HTTP.</span><span class="sxs-lookup"><span data-stu-id="e3277-188">In previous builds of Windows Holographic, when attempting to download a locked file, the result would be an HTTP error page.</span></span> <span data-ttu-id="e3277-189">Při pokusu Windows Holographic verze 21H1 se při pokusu o stažení uzamčeného souboru nic nestane – soubor se nestáhne a nezobrazí se žádná chyba.</span><span class="sxs-lookup"><span data-stu-id="e3277-189">In the Windows Holographic, version 21H1 update, trying to download a locked file results in nothing visible happening—the file doesn’t download and there’s no error.</span></span>

[<span data-ttu-id="e3277-190">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="e3277-190">Back to list</span></span>](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a><span data-ttu-id="e3277-191">Portál zařízení nahrání nebo stažení souboru</span><span class="sxs-lookup"><span data-stu-id="e3277-191">Device Portal file upload/download times out</span></span>
> [!NOTE]
> <span data-ttu-id="e3277-192">Jedná se o **známý problém,** který je opraven Windows Insider verze 20348.1403.</span><span class="sxs-lookup"><span data-stu-id="e3277-192">This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span> <span data-ttu-id="e3277-193">Pokud jste v rámci tohoto alternativního řešení dříve zakázali připojení SSL, důrazně doporučujeme ho znovu povolit.</span><span class="sxs-lookup"><span data-stu-id="e3277-193">If you previously disabled SSL Connection as part of the workaround, we highly recommend you re-enable it.</span></span>


<span data-ttu-id="e3277-194">Někteří zákazníci zjistili, že při pokusu o nahrání nebo stažení souborů se operace může zdát, že přestane reagovat a pak dojde k časovému limitu nebo se nikdy nedokoncuje.</span><span class="sxs-lookup"><span data-stu-id="e3277-194">Some customers have found, when attempting to upload or download files, the operation might appear to hang and then time out or never complete.</span></span> <span data-ttu-id="e3277-195">Tento problém je[](#downloading-locked-files-doesnt-error) oddělený od známého problému uzamčeného souboru – to má vliv na sestavení na trhu Windows Holographic, verze 2004, 20H2 a 21H1.</span><span class="sxs-lookup"><span data-stu-id="e3277-195">This is separate from the '[file locked' known issue](#downloading-locked-files-doesnt-error) -- this affects Windows Holographic, versions 2004, 20H2 and 21H1 in-market builds.</span></span> <span data-ttu-id="e3277-196">Problém byl způsobený chybou při Portál zařízení zpracování určitých požadavků a při použití protokolu https, což je výchozí nastavení, dochází nejčastěji k tomuto problému.</span><span class="sxs-lookup"><span data-stu-id="e3277-196">The problem has been root caused to a bug in Device Portal's handling of certain requests, and is most consistently hit when using https, which is the default.</span></span> 

### <a name="workaround"></a><span data-ttu-id="e3277-197">Alternativní řešení</span><span class="sxs-lookup"><span data-stu-id="e3277-197">Workaround</span></span>

<span data-ttu-id="e3277-198">Toto alternativní řešení, které platí stejně pro Wi-Fi a UsbNcm, je zakázat možnost "povinné" v části Připojení SSL.</span><span class="sxs-lookup"><span data-stu-id="e3277-198">This workaround, which applies equally to Wi-Fi and UsbNcm, is to disable the "required" option under "SSL Connection".</span></span> <span data-ttu-id="e3277-199">Pokud to chcete udělat, přejděte Portál zařízení, **Systém** a vyberte **stránku** Předvolby.</span><span class="sxs-lookup"><span data-stu-id="e3277-199">To do so, navigate to Device Portal, **System**, and select the **Preferences** page.</span></span> <span data-ttu-id="e3277-200">V části **Zabezpečení zařízení** vyhledejte Připojení **SSL a** zrušte zaškrtnutí, pokud chcete zakázat **povinné.**</span><span class="sxs-lookup"><span data-stu-id="e3277-200">In the **Device Security** section, locate **SSL Connection**, and uncheck to disable **Required**.</span></span>

<span data-ttu-id="e3277-201">Uživatel by pak měl přejít na http://, ne na https://(IP adresa) a funkce, jako je nahrání souboru, a stahování bude fungovat.</span><span class="sxs-lookup"><span data-stu-id="e3277-201">The user should then go to http://, not https:// (IP address) and features like file upload and download will work.</span></span>

[<span data-ttu-id="e3277-202">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="e3277-202">Back to list</span></span>](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a><span data-ttu-id="e3277-203">Modrá obrazovka po odregistraci z programu Insider Preview na zařízení, které se postavilo pomocí buildu Insider</span><span class="sxs-lookup"><span data-stu-id="e3277-203">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>

<span data-ttu-id="e3277-204">to má vliv na to, co se týká uživatelů, kteří byli ve buildu insider preview, ve HoloLens 2 se znovu dokončí novému buildu insider preview a pak se zruší jeho registrace v programu insider.</span><span class="sxs-lookup"><span data-stu-id="e3277-204">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span> <span data-ttu-id="e3277-205">Jedná se o **známý problém**.</span><span class="sxs-lookup"><span data-stu-id="e3277-205">This is a **known issue**.</span></span>

<span data-ttu-id="e3277-206">To nemá vliv na:</span><span class="sxs-lookup"><span data-stu-id="e3277-206">This does not affect:</span></span>
- <span data-ttu-id="e3277-207">uživatelé, kteří nejsou zaregistrovaní v programu Windows Insider</span><span class="sxs-lookup"><span data-stu-id="e3277-207">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="e3277-208">Insider</span><span class="sxs-lookup"><span data-stu-id="e3277-208">Insiders:</span></span>
    - <span data-ttu-id="e3277-209">Pokud bylo zařízení zaregistrováno, protože buildy Insider byly verze 18362. x</span><span class="sxs-lookup"><span data-stu-id="e3277-209">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="e3277-210">Pokud se v programu Insider nastavila aplikace Insider podepsaná 19041. x a zůstane zaregistrovaná v programu Insider</span><span class="sxs-lookup"><span data-stu-id="e3277-210">If they flashed an Insider signed 19041.x build AND stay enrolled in the Insider program</span></span>

<span data-ttu-id="e3277-211">Práce v tomto okolí:</span><span class="sxs-lookup"><span data-stu-id="e3277-211">Work-around:</span></span> 
- <span data-ttu-id="e3277-212">Vyhnout se problému</span><span class="sxs-lookup"><span data-stu-id="e3277-212">Avoid the issue</span></span> 
    - <span data-ttu-id="e3277-213">Zabliká Build bez programu Insider.</span><span class="sxs-lookup"><span data-stu-id="e3277-213">Flash a non-insider build.</span></span> <span data-ttu-id="e3277-214">Jedna z pravidelných měsíčních aktualizací.</span><span class="sxs-lookup"><span data-stu-id="e3277-214">One of the regular monthly updates.</span></span>
    - <span data-ttu-id="e3277-215">Zůstat ve verzi Insider Preview</span><span class="sxs-lookup"><span data-stu-id="e3277-215">Stay on Insider Preview</span></span>
- <span data-ttu-id="e3277-216">Rozsvítit zařízení</span><span class="sxs-lookup"><span data-stu-id="e3277-216">Reflash the device</span></span>

    1. <span data-ttu-id="e3277-217">[HoloLens 2 vložte do režimu blesku](hololens-recovery.md) ručně, a to tak, že se nepřipojíte.</span><span class="sxs-lookup"><span data-stu-id="e3277-217">Put the [HoloLens 2 into flashing mode](hololens-recovery.md) manually by fully powering down while not connect.</span></span> <span data-ttu-id="e3277-218">Pak klepněte na tlačítko napájení.</span><span class="sxs-lookup"><span data-stu-id="e3277-218">Then while holding Volume up, tap the Power button.</span></span>
    
    1. <span data-ttu-id="e3277-219">Připojení k počítači a otevřete průvodce pokročilým obnovením.</span><span class="sxs-lookup"><span data-stu-id="e3277-219">Connect to the PC and open Advanced Recovery Companion.</span></span>
    
    1. <span data-ttu-id="e3277-220">zabliká HoloLens 2 do výchozího buildu.</span><span class="sxs-lookup"><span data-stu-id="e3277-220">Flash the HoloLens 2 to the default build.</span></span>

[<span data-ttu-id="e3277-221">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="e3277-221">Back to list</span></span>](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a><span data-ttu-id="e3277-222">OneDrive neodesílá automaticky obrázky</span><span class="sxs-lookup"><span data-stu-id="e3277-222">OneDrive doesn't automatically upload pictures</span></span>

<span data-ttu-id="e3277-223">aplikace OneDrive pro HoloLens nepodporuje automatické nahrávání fotoaparátů pro pracovní nebo školní účty.</span><span class="sxs-lookup"><span data-stu-id="e3277-223">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span> <span data-ttu-id="e3277-224">Jedná se o **známý problém**.</span><span class="sxs-lookup"><span data-stu-id="e3277-224">This is a **known issue**.</span></span>

<span data-ttu-id="e3277-225">Alternativní řešení:</span><span class="sxs-lookup"><span data-stu-id="e3277-225">Workarounds:</span></span>

- <span data-ttu-id="e3277-226">Pokud je pro vaši firmu životaschopná, je automatické nahrávání kamery podporované u zákaznických účtů Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e3277-226">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="e3277-227">k vašemu účet Microsoft se můžete přihlásit navíc k pracovnímu nebo školnímu účtu (aplikace OneDrive podporuje duální přihlášení).</span><span class="sxs-lookup"><span data-stu-id="e3277-227">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="e3277-228">z profilu účet Microsoft v rámci OneDrive můžete povolit automatické nahrávání snímků na pozadí.</span><span class="sxs-lookup"><span data-stu-id="e3277-228">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="e3277-229">pokud nemůžete bezpečně použít účet Microsoft příjemce k automatickému nahrávání vašich fotografií, můžete fotky z OneDrive aplikace nahrát ručně do svého pracovního nebo školního účtu.</span><span class="sxs-lookup"><span data-stu-id="e3277-229">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="e3277-230">abyste to mohli udělat, ujistěte se, že jste se přihlásili ke svému pracovnímu nebo školnímu účtu v aplikaci OneDrive.</span><span class="sxs-lookup"><span data-stu-id="e3277-230">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="e3277-231">Vyberte **+** tlačítko a zvolte **Upload**.</span><span class="sxs-lookup"><span data-stu-id="e3277-231">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="e3277-232">Najděte fotky nebo videa, která chcete nahrát, přechodem na **obrázky >ou kamerou**.</span><span class="sxs-lookup"><span data-stu-id="e3277-232">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="e3277-233">Vyberte fotky nebo videa, která chcete nahrát, a pak vyberte tlačítko **otevřít** .</span><span class="sxs-lookup"><span data-stu-id="e3277-233">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

[<span data-ttu-id="e3277-234">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="e3277-234">Back to list</span></span>](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a><span data-ttu-id="e3277-235">HoloLens nereaguje nebo se nespustí</span><span class="sxs-lookup"><span data-stu-id="e3277-235">HoloLens is unresponsive or won't start</span></span>

<span data-ttu-id="e3277-236">pokud se HoloLens nespustí:</span><span class="sxs-lookup"><span data-stu-id="e3277-236">If your HoloLens won't start:</span></span>

- <span data-ttu-id="e3277-237">Pokud se indikátory LED vedle tlačítka napájení nesvítí nebo se jenom jeden z nich může krátce rozsvítit, možná budete muset [účtovat HoloLens.](hololens2-charging.md#charging-the-device)</span><span class="sxs-lookup"><span data-stu-id="e3277-237">If the LEDs next to the power button don't light up, or only one LED briefly blinks, you may need to [charge your HoloLens.](hololens2-charging.md#charging-the-device)</span></span>
- <span data-ttu-id="e3277-238">Pokud při stisknutí tlačítka napájení zhasnou diody LED, ale nevidíte cokoli na zobrazených displejech, [proveďte obnovení zařízení](hololens-recovery.md#hard-reset-procedure).</span><span class="sxs-lookup"><span data-stu-id="e3277-238">If the LEDs light up when you press the power button but you can't see anything on the displays, [do a hard reset of the device](hololens-recovery.md#hard-reset-procedure).</span></span>

<span data-ttu-id="e3277-239">pokud bude váš HoloLens zmrazený nebo nereaguje:</span><span class="sxs-lookup"><span data-stu-id="e3277-239">If your HoloLens becomes frozen or unresponsive:</span></span>

- <span data-ttu-id="e3277-240">vypněte HoloLens tím, že stisknete tlačítko napájení, dokud se všechny pět diod led nevypne, nebo 15 sekund, pokud indikátory led nereagují.</span><span class="sxs-lookup"><span data-stu-id="e3277-240">Turn off your HoloLens by pressing the power button until all five of the LEDs turn themselves off, or for 15 seconds if the LEDs are unresponsive.</span></span> <span data-ttu-id="e3277-241">HoloLens spustíte tak, že znovu stisknete tlačítko napájení.</span><span class="sxs-lookup"><span data-stu-id="e3277-241">To start your HoloLens, press the power button again.</span></span>

<span data-ttu-id="e3277-242">pokud tyto kroky nefungují, můžete zkusit [obnovit zařízení HoloLens 2](hololens-recovery.md) nebo [HoloLens (1. generace).](hololens1-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="e3277-242">If these steps don't work, you can try [recovering your HoloLens 2 device](hololens-recovery.md) or [HoloLens (1st gen) device.](hololens1-recovery.md)</span></span>

[<span data-ttu-id="e3277-243">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="e3277-243">Back to list</span></span>](#list)

## <a name="low-disk-space-error"></a><span data-ttu-id="e3277-244">Chyba "nedostatek místa na disku"</span><span class="sxs-lookup"><span data-stu-id="e3277-244">"Low Disk Space" error</span></span>

<span data-ttu-id="e3277-245">K uvolnění úložného prostoru budete potřebovat jednu nebo více následujících akcí:</span><span class="sxs-lookup"><span data-stu-id="e3277-245">You'll need to free up some storage space by doing one or more of the following:</span></span>

- <span data-ttu-id="e3277-246">Odstraňte některé nepoužité mezery.</span><span class="sxs-lookup"><span data-stu-id="e3277-246">Delete some unused spaces.</span></span> <span data-ttu-id="e3277-247">v **Nastavení**  >  **systémových**  >  **prostorech** vyberte místo, které už nepotřebujete, a pak vyberte **odebrat**.</span><span class="sxs-lookup"><span data-stu-id="e3277-247">Go to **Settings** > **System** > **Spaces**, select a space that you no longer need, and then select **Remove**.</span></span>
- <span data-ttu-id="e3277-248">Odeberte některé hologramy, které jste umístili.</span><span class="sxs-lookup"><span data-stu-id="e3277-248">Remove some of the holograms that you've placed.</span></span>
- <span data-ttu-id="e3277-249">Odstraňte z aplikace Fotky některé obrázky a videa.</span><span class="sxs-lookup"><span data-stu-id="e3277-249">Delete some pictures and videos from the Photos app.</span></span>
- <span data-ttu-id="e3277-250">Odinstalujte některé aplikace z HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e3277-250">Uninstall some apps from your HoloLens.</span></span> <span data-ttu-id="e3277-251">V seznamu **všechny aplikace** klepněte na aplikaci, kterou chcete odinstalovat, a pak vyberte **odinstalovat**.</span><span class="sxs-lookup"><span data-stu-id="e3277-251">In the **All apps** list, tap and hold the app you want to uninstall, and then select **Uninstall**.</span></span>

[<span data-ttu-id="e3277-252">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="e3277-252">Back to list</span></span>](#list)

## <a name="calibration-fails"></a><span data-ttu-id="e3277-253">Neúspěšná kalibrace</span><span class="sxs-lookup"><span data-stu-id="e3277-253">Calibration fails</span></span>

<span data-ttu-id="e3277-254">Kalibrace by měla fungovat pro většinu lidí, ale existují případy, kdy se kalibrace nezdařila.</span><span class="sxs-lookup"><span data-stu-id="e3277-254">Calibration should work for most people, but there are cases where calibration fails.</span></span>
  
<span data-ttu-id="e3277-255">Mezi případné důvody pro selhání kalibrace patří:</span><span class="sxs-lookup"><span data-stu-id="e3277-255">Some potential reasons for calibration failure include:</span></span>

- <span data-ttu-id="e3277-256">Odčítání a nikoli za cíle kalibrace</span><span class="sxs-lookup"><span data-stu-id="e3277-256">Getting distracted and not following the calibration targets</span></span>
- <span data-ttu-id="e3277-257">Nesprávné umístění zařízení hypervisoru nebo zařízení na začátku</span><span class="sxs-lookup"><span data-stu-id="e3277-257">Dirty or scratched device visor or device visor not positioned properly</span></span>
- <span data-ttu-id="e3277-258">Nezměněná nebo škrábancová skla</span><span class="sxs-lookup"><span data-stu-id="e3277-258">Dirty or scratched glasses</span></span>
- <span data-ttu-id="e3277-259">Určité typy kontaktních skel a brýle (barevná čočka, některá torica kontaktu, poblokovaná brýle, některá brýle s vysokým předpisem, Sunglasses nebo podobné)</span><span class="sxs-lookup"><span data-stu-id="e3277-259">Certain types of contact lenses and glasses (colored contact lenses, some toric contact lenses, IR blocking glasses, some high prescription glasses, sunglasses, or similar)</span></span>
- <span data-ttu-id="e3277-260">Více vyslovované strukturu a některá rozšíření eyelash</span><span class="sxs-lookup"><span data-stu-id="e3277-260">More-pronounced makeup and some eyelash extensions</span></span>
- <span data-ttu-id="e3277-261">Chlupy nebo silné eyeglass snímky, pokud si zařízení blokuje zobrazení očí</span><span class="sxs-lookup"><span data-stu-id="e3277-261">Hair or thick eyeglass frames if they're blocking the device from seeing your eyes</span></span>
- <span data-ttu-id="e3277-262">Určité Physiology oka, podmínky očí nebo oční chirurgie, jako je úzká oči, Long Eyelashes, amblyopia, nystagmus, některé případy LASIK nebo jiné oči surgeries</span><span class="sxs-lookup"><span data-stu-id="e3277-262">Certain eye physiology, eye conditions, or eye surgery such as narrow eyes, long eyelashes, amblyopia, nystagmus, some cases of LASIK or other eye surgeries</span></span>

<span data-ttu-id="e3277-263">Pokud kalibrace neproběhne úspěšně, zkuste:</span><span class="sxs-lookup"><span data-stu-id="e3277-263">If calibration is unsuccessful try:</span></span>

- <span data-ttu-id="e3277-264">Čištění zařízení s clonou</span><span class="sxs-lookup"><span data-stu-id="e3277-264">Cleaning your device visor</span></span>
- <span data-ttu-id="e3277-265">Čištění vašich brýle</span><span class="sxs-lookup"><span data-stu-id="e3277-265">Cleaning your glasses</span></span>
- <span data-ttu-id="e3277-266">Co nejblíže vašim očí vám umožní obzradit své zařízení.</span><span class="sxs-lookup"><span data-stu-id="e3277-266">Pushing your device visor as close to your eyes as possible</span></span>
- <span data-ttu-id="e3277-267">Přesun objektů ve vašem seznamu clony (například vlasy)</span><span class="sxs-lookup"><span data-stu-id="e3277-267">Moving objects in your visor out of the way (such as hair)</span></span>
- <span data-ttu-id="e3277-268">Zapnutí světla v místnosti nebo přemístění přímého slunečního záření</span><span class="sxs-lookup"><span data-stu-id="e3277-268">Turning on a light in your room or moving out of direct sunlight</span></span>

<span data-ttu-id="e3277-269">pokud jste postupovali podle všech pokynů a kalibrace stále selhává, můžete zakázat výzvu k kalibraci v Nastavení.</span><span class="sxs-lookup"><span data-stu-id="e3277-269">If you followed all guidelines and calibration is still failing, you can disable the calibration prompt in Settings.</span></span> <span data-ttu-id="e3277-270">Dejte nám taky vědět, že vám zašleme zpětnou vazbu v [centru Feedback](hololens-feedback.md).</span><span class="sxs-lookup"><span data-stu-id="e3277-270">Also let us know by filing feedback in [Feedback Hub](hololens-feedback.md).</span></span>

<span data-ttu-id="e3277-271">Podívejte se také na související informace o [barvě obrázku nebo odstraňování potíží s jasem.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span><span class="sxs-lookup"><span data-stu-id="e3277-271">Also see related information for [image color or brightness troubleshooting.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span></span>

<span data-ttu-id="e3277-272">nastavení IPD nelze použít pro HoloLens 2, protože pozice očí jsou vypočítány systémem.</span><span class="sxs-lookup"><span data-stu-id="e3277-272">Setting IPD is not applicable for HoloLens 2, since eye positions are computed by the system.</span></span> 

[<span data-ttu-id="e3277-273">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="e3277-273">Back to list</span></span>](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a><span data-ttu-id="e3277-274">nejde se přihlásit, protože můj HoloLens byl dřív nastavený pro někoho jiného.</span><span class="sxs-lookup"><span data-stu-id="e3277-274">Can't sign in because my HoloLens was previously set up for someone else</span></span>

<span data-ttu-id="e3277-275">Zařízení můžete [Přepnout do **režimu blikání** a obnovit zařízení pomocí pokročilého Průvodce obnovením](hololens-recovery.md#clean-reflash-the-device) .</span><span class="sxs-lookup"><span data-stu-id="e3277-275">You can [put the device into **Flashing Mode** and use Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device) to recover the device.</span></span>

[<span data-ttu-id="e3277-276">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="e3277-276">Back to list</span></span>](#list)


## <a name="unity-isnt-working"></a><span data-ttu-id="e3277-277">Unity nefunguje</span><span class="sxs-lookup"><span data-stu-id="e3277-277">Unity isn't working</span></span>

- <span data-ttu-id="e3277-278">přečtěte si téma [instalace nástrojů](/windows/mixed-reality/install-the-tools) pro nejaktuálnější verzi Unity doporučenou pro HoloLens vývoj.</span><span class="sxs-lookup"><span data-stu-id="e3277-278">See [Install the tools](/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="e3277-279">známé problémy se službou unity HoloLens Technical Preview jsou popsány ve [HoloLens fórech unity](https://forum.unity3d.com/threads/known-issues.394627/).</span><span class="sxs-lookup"><span data-stu-id="e3277-279">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

[<span data-ttu-id="e3277-280">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="e3277-280">Back to list</span></span>](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a><span data-ttu-id="e3277-281">Windows Portál zařízení nepracuje správně.</span><span class="sxs-lookup"><span data-stu-id="e3277-281">Windows Device Portal isn't working correctly</span></span>

- <span data-ttu-id="e3277-282">Funkce Live Preview v rámci hybridního zachycení realit může při latenci vykazovat několik sekund.</span><span class="sxs-lookup"><span data-stu-id="e3277-282">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="e3277-283">Na stránce virtuálního vstupu nejsou funkční gesta a posuvníky v části virtuální gesta.</span><span class="sxs-lookup"><span data-stu-id="e3277-283">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="e3277-284">Jejich použití nebude mít žádný vliv.</span><span class="sxs-lookup"><span data-stu-id="e3277-284">Using them will have no effect.</span></span> <span data-ttu-id="e3277-285">Virtuální klávesnice na stránce virtuálního vstupu funguje správně.</span><span class="sxs-lookup"><span data-stu-id="e3277-285">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="e3277-286">po povolení režimu vývojářů v Nastavení může trvat několik sekund, než se zapne přepínač, aby se aktivoval portál zařízení.</span><span class="sxs-lookup"><span data-stu-id="e3277-286">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

[<span data-ttu-id="e3277-287">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="e3277-287">Back to list</span></span>](#list)

## <a name="the-hololens-emulator-isnt-working"></a><span data-ttu-id="e3277-288">Emulator HoloLens nefunguje</span><span class="sxs-lookup"><span data-stu-id="e3277-288">The HoloLens Emulator isn't working</span></span>

<span data-ttu-id="e3277-289">informace o emulátoru HoloLens najdete v naší dokumentaci pro vývojáře.</span><span class="sxs-lookup"><span data-stu-id="e3277-289">Information about the HoloLens emulator is located in our developer documentation.</span></span>  <span data-ttu-id="e3277-290">přečtěte si další informace o [řešení potíží s emulátorem HoloLens](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="e3277-290">Read more about [troubleshooting the HoloLens emulator](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting).</span></span>


- <span data-ttu-id="e3277-291">ne všechny aplikace v Microsoft Store jsou kompatibilní s emulátorem.</span><span class="sxs-lookup"><span data-stu-id="e3277-291">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="e3277-292">Například mladí conker a fragmenty nefungují na emulátoru.</span><span class="sxs-lookup"><span data-stu-id="e3277-292">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="e3277-293">V Emulator nemůžete použít webovou kameru počítače.</span><span class="sxs-lookup"><span data-stu-id="e3277-293">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="e3277-294">funkce Live Preview portálu zařízení Windows nefunguje s emulátorem.</span><span class="sxs-lookup"><span data-stu-id="e3277-294">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="e3277-295">Pořád můžete zachytit hybridní videa a obrázky.</span><span class="sxs-lookup"><span data-stu-id="e3277-295">You can still capture Mixed Reality videos and images.</span></span>

[<span data-ttu-id="e3277-296">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="e3277-296">Back to list</span></span>](#list)

## <a name="voice-commands-arent-working"></a><span data-ttu-id="e3277-297">Hlasové příkazy nefungují.</span><span class="sxs-lookup"><span data-stu-id="e3277-297">Voice commands aren't working</span></span>

<span data-ttu-id="e3277-298">pokud Cortana nereaguje na hlasové příkazy, ujistěte se, že je Cortana zapnutý.</span><span class="sxs-lookup"><span data-stu-id="e3277-298">If Cortana isn't responding to your voice commands, make sure Cortana is turned on.</span></span> <span data-ttu-id="e3277-299">v seznamu všechny aplikace vyberte **Cortana**  >    >  **poznámkový blok** nabídky  >  **Nastavení** a proveďte změny.</span><span class="sxs-lookup"><span data-stu-id="e3277-299">On the All apps list, select **Cortana** > **Menu** > **Notebook** > **Settings** to make changes.</span></span> <span data-ttu-id="e3277-300">Další informace o tom, co můžete vyslovit, najdete v tématu [použití hlasu s HoloLens](hololens-cortana.md).</span><span class="sxs-lookup"><span data-stu-id="e3277-300">To learn more about what you can say, see [Use your voice with HoloLens](hololens-cortana.md).</span></span>

<span data-ttu-id="e3277-301">V HoloLens (1. generace) není integrované rozpoznávání řeči konfigurovatelné.</span><span class="sxs-lookup"><span data-stu-id="e3277-301">On HoloLens (1st gen), built-in speech recognition is not configurable.</span></span> <span data-ttu-id="e3277-302">Vždy je zapnutý.</span><span class="sxs-lookup"><span data-stu-id="e3277-302">It is always turned on.</span></span> <span data-ttu-id="e3277-303">Na HoloLens 2 můžete zvolit, jestli se má při nastavování zařízení zapnout rozpoznávání Cortana i rozpoznávání řeči.</span><span class="sxs-lookup"><span data-stu-id="e3277-303">On HoloLens 2, you can choose whether to turn on both speech recognition and Cortana during device setup.</span></span>

<span data-ttu-id="e3277-304">Pokud váš HoloLens 2 nereaguje na váš hlas, ujistěte se, že je zapnuté rozpoznávání řeči.</span><span class="sxs-lookup"><span data-stu-id="e3277-304">If your HoloLens 2 is not responding to your voice, make sure Speech recognition is turned on.</span></span> <span data-ttu-id="e3277-305">Přejděte na **Start Nastavení** Privacy Speech a  >    >    >   zapněte **Rozpoznávání řeči.**</span><span class="sxs-lookup"><span data-stu-id="e3277-305">Go to **Start** > **Settings** > **Privacy** > **Speech** and turn on **Speech recognition**.</span></span>

[<span data-ttu-id="e3277-306">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="e3277-306">Back to list</span></span>](#list)

## <a name="hand-input-isnt-working"></a><span data-ttu-id="e3277-307">Ruční vstup nefunguje</span><span class="sxs-lookup"><span data-stu-id="e3277-307">Hand input isn't working</span></span>

<span data-ttu-id="e3277-308">Aby bylo HoloLens vidět vaše ruce, musíte je ponechat v snímku gest.</span><span class="sxs-lookup"><span data-stu-id="e3277-308">To ensure that HoloLens can see your hands, you need to keep them in the gesture frame.</span></span>  <span data-ttu-id="e3277-309">Domovská Mixed Reality poskytuje zpětnou vazbu, která vám dá vědět, kdy jsou vaše ruce sledované.</span><span class="sxs-lookup"><span data-stu-id="e3277-309">The Mixed Reality Home provides feedback that lets you know when your hands are tracked.</span></span>  <span data-ttu-id="e3277-310">Zpětná vazba se liší v různých verzích HoloLens:</span><span class="sxs-lookup"><span data-stu-id="e3277-310">The feedback is different on different versions of HoloLens:</span></span>
- <span data-ttu-id="e3277-311">V HoloLens (1. generace) se kurzor pohledu změní z tečky na kruh.</span><span class="sxs-lookup"><span data-stu-id="e3277-311">On HoloLens (1st gen), the gaze cursor changes from a dot to a ring</span></span>
- <span data-ttu-id="e3277-312">Na HoloLens 2 se zobrazí kurzor prstu, když se vaše ruce nachází blízko slate, a když jsou břidíčky dále, zobrazí se ruční paprsk.</span><span class="sxs-lookup"><span data-stu-id="e3277-312">On HoloLens 2, a fingertip cursor appears when your hand is close to a slate, and a hand ray appears when slates are further away</span></span>

<span data-ttu-id="e3277-313">Řada imerzivních aplikací dodržuje vzory vstupu, které se podobají Mixed Reality Domovské obrazovce.</span><span class="sxs-lookup"><span data-stu-id="e3277-313">Many immersive apps follow input patterns that are similar to Mixed Reality Home.</span></span>  <span data-ttu-id="e3277-314">Další informace o použití ručního [vstupu v HoloLens (1. generace)](hololens1-basic-usage.md#use-hololens-with-your-hands) a [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span><span class="sxs-lookup"><span data-stu-id="e3277-314">Learn more about using hand input on [HoloLens (1st gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) and [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span></span>

<span data-ttu-id="e3277-315">Pokud máte problémy s chemií, mějte na vědomí, že některé typy choumů nefungují se sledováním rukou.</span><span class="sxs-lookup"><span data-stu-id="e3277-315">If you are wearing gloves, note that some types of gloves do not work with hand tracking.</span></span>  <span data-ttu-id="e3277-316">Běžným příkladem je černá guma, která obvykle absorbuje infračervené světlo a nenabírá je hloubková kamera.</span><span class="sxs-lookup"><span data-stu-id="e3277-316">A common example is black rubber gloves, which tend to absorb infrared light and are not picked up by the depth camera.</span></span>  <span data-ttu-id="e3277-317">Pokud vaše práce zahrnuje gumové gumy, doporučujeme, abyste si zkusili světlejší barvu, například modrou nebo šedou.</span><span class="sxs-lookup"><span data-stu-id="e3277-317">If your work involves rubber gloves, we recommend trying a lighter color such as blue or gray.</span></span>  <span data-ttu-id="e3277-318">Dalším příkladem je velká nesrozumilá aplikace, která má tendenci zakrytí tvaru vaší ruky.</span><span class="sxs-lookup"><span data-stu-id="e3277-318">Another example is large baggy gloves, which tend to obscure the shape of your hand.</span></span> <span data-ttu-id="e3277-319">Pro nejlepší výsledky doporučujeme použít co nejvíce tvarování.</span><span class="sxs-lookup"><span data-stu-id="e3277-319">We recommend using gloves that are as form-fitting as possible for best results.</span></span>

<span data-ttu-id="e3277-320">Pokud má váš vizor otisky prstů nebo smyšlené údaje, vyčistěte ji pomocí čisticího mikrovlákna, který byl HoloLens s filtrem.</span><span class="sxs-lookup"><span data-stu-id="e3277-320">If your visor has fingerprints or smudges, use the microfiber cleaning cloth that came with the HoloLens to clean your visor gently.</span></span>

[<span data-ttu-id="e3277-321">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="e3277-321">Back to list</span></span>](#list)

## <a name="cant-connect-to-wi-fi"></a><span data-ttu-id="e3277-322">Nelze se připojit k Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="e3277-322">Can't connect to Wi-Fi</span></span>

<span data-ttu-id="e3277-323">Tady je několik věcí, které můžete vyzkoušet, pokud nemůžete připojit HoloLens k Wi-Fi síti:</span><span class="sxs-lookup"><span data-stu-id="e3277-323">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

- <span data-ttu-id="e3277-324">Ujistěte se, Wi-Fi je zapnuté.</span><span class="sxs-lookup"><span data-stu-id="e3277-324">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="e3277-325">Kontrolu můžete provést pomocí gesta Start a pak **Nastavení**  >  **Network &amp; Internet**  >  **Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="e3277-325">To check, use the Start gesture, then select **Settings** > **Network &amp; Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="e3277-326">Pokud Wi-Fi, zkuste ho vypnout a znovu zas.</span><span class="sxs-lookup"><span data-stu-id="e3277-326">If Wi-Fi is on, try turning it off and then on again.</span></span>
- <span data-ttu-id="e3277-327">Přesuňte se blíže ke směrovači nebo přístupovému bodu.</span><span class="sxs-lookup"><span data-stu-id="e3277-327">Move closer to the router or access point.</span></span>
- <span data-ttu-id="e3277-328">Restartujte směrovač Wi-Fi a pak [restartujte HoloLens](hololens-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="e3277-328">Restart your Wi-Fi router, then [restart HoloLens](hololens-recovery.md).</span></span> <span data-ttu-id="e3277-329">Zkuste se připojit znovu.</span><span class="sxs-lookup"><span data-stu-id="e3277-329">Try connecting again.</span></span>
- <span data-ttu-id="e3277-330">Pokud nic z toho nefunguje, zkontrolujte, že váš směrovač používá nejnovější firmware.</span><span class="sxs-lookup"><span data-stu-id="e3277-330">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="e3277-331">Tyto informace najdete na webu výrobce.</span><span class="sxs-lookup"><span data-stu-id="e3277-331">You can find this information on the manufacturer website.</span></span>

[<span data-ttu-id="e3277-332">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="e3277-332">Back to list</span></span>](#list)

## <a name="bluetooth-devices-arent-pairing"></a><span data-ttu-id="e3277-333">Bluetooth zařízení se ne pairují</span><span class="sxs-lookup"><span data-stu-id="e3277-333">Bluetooth devices aren't pairing</span></span>

<span data-ttu-id="e3277-334">Pokud máte problémy s [párem zařízení Bluetooth,](hololens-connect-devices.md)zkuste následující postup:</span><span class="sxs-lookup"><span data-stu-id="e3277-334">If you're having problems [pairing a Bluetooth device](hololens-connect-devices.md), try the following:</span></span>

- <span data-ttu-id="e3277-335">Přejděte na **Nastavení** Zařízení a  >  ujistěte se, Bluetooth je zapnutá.</span><span class="sxs-lookup"><span data-stu-id="e3277-335">Go to **Settings** > **Devices**, and make sure that Bluetooth is turned on.</span></span> <span data-ttu-id="e3277-336">Pokud je, vypněte ho a znovu zapněte.</span><span class="sxs-lookup"><span data-stu-id="e3277-336">If it is, turn it off and on again.</span></span>
- <span data-ttu-id="e3277-337">Ujistěte se, že Bluetooth zařízení je plně nabité nebo obsahuje čerstvé baterie.</span><span class="sxs-lookup"><span data-stu-id="e3277-337">Make sure that your Bluetooth device is fully charged or has fresh batteries.</span></span>
- <span data-ttu-id="e3277-338">Pokud se stále nemůžete připojit, [restartujte HoloLens](hololens-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="e3277-338">If you still can't connect, [restart the HoloLens](hololens-recovery.md).</span></span>

[<span data-ttu-id="e3277-339">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="e3277-339">Back to list</span></span>](#list)

## <a name="usb-c-microphone-isnt-working"></a><span data-ttu-id="e3277-340">Mikrofon USB-C nefunguje</span><span class="sxs-lookup"><span data-stu-id="e3277-340">USB-C Microphone isn't working</span></span>
<span data-ttu-id="e3277-341">Uvědomte si, že některé mikrofony USB-C se nesprávně hlásí jako *mikrofon* i jako mluvčí.</span><span class="sxs-lookup"><span data-stu-id="e3277-341">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="e3277-342">Jedná se o problém s mikrofonem, a ne s HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e3277-342">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="e3277-343">Když jeden z těchto mikrofonů zapojíte do HoloLens, může dojít ke ztrátě zvuku.</span><span class="sxs-lookup"><span data-stu-id="e3277-343">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="e3277-344">Naštěstí existuje jednoduchá oprava.</span><span class="sxs-lookup"><span data-stu-id="e3277-344">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="e3277-345">V **Nastavení** System Sound (Zvuk systému) explicitně nastavte integrované mluvčí (zvukový ovladač  ->    ->   **analogové funkce)** jako **výchozí zařízení.**</span><span class="sxs-lookup"><span data-stu-id="e3277-345">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="e3277-346">HoloLens si toto nastavení zapamatovat, i když se mikrofon později odebere a znovu připojí.</span><span class="sxs-lookup"><span data-stu-id="e3277-346">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![Řešení potíží s mikrofony USB-C](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a><span data-ttu-id="e3277-348">Zařízení uvedená jako dostupná v Nastavení nefungují</span><span class="sxs-lookup"><span data-stu-id="e3277-348">Devices listed as available in Settings don't work</span></span>

<span data-ttu-id="e3277-349">HoloLens (1. generace) nepodporuje Bluetooth zvukové profily.</span><span class="sxs-lookup"><span data-stu-id="e3277-349">HoloLens (1st gen) doesn't support Bluetooth audio profiles.</span></span> <span data-ttu-id="e3277-350">Bluetooth se zvuková zařízení, jako jsou mluvčí a náhlavní soupravy, mohou zobrazovat jako dostupná v HoloLens, ale nejsou podporovaná.</span><span class="sxs-lookup"><span data-stu-id="e3277-350">Bluetooth audio devices, such as speakers and headsets, may appear as available in HoloLens settings, but they aren't supported.</span></span>

<span data-ttu-id="e3277-351">HoloLens 2 podporuje zvukový profil Bluetooth A2DP pro stereo přehrávání.</span><span class="sxs-lookup"><span data-stu-id="e3277-351">HoloLens 2 supports the Bluetooth A2DP audio profile for stereo playback.</span></span> <span data-ttu-id="e3277-352">Profil Bluetooth Hands Free, který umožňuje zachytávání mikrofonu z Bluetooth periferního zařízení, se v HoloLens 2 nepodporuje.</span><span class="sxs-lookup"><span data-stu-id="e3277-352">The Bluetooth Hands Free profile which enables microphone capture from a Bluetooth peripheral is not supported on HoloLens 2.</span></span>

<span data-ttu-id="e3277-353">Pokud máte potíže s používáním Bluetooth, ujistěte se, že se jedná o podporované zařízení.</span><span class="sxs-lookup"><span data-stu-id="e3277-353">If you're having trouble using a Bluetooth device, make sure that it's a supported device.</span></span> <span data-ttu-id="e3277-354">Mezi podporovaná zařízení patří:</span><span class="sxs-lookup"><span data-stu-id="e3277-354">Supported devices include the following:</span></span>

- <span data-ttu-id="e3277-355">QWERTY v angličtině Bluetooth klávesnice (můžete je použít kdekoli, kde používáte holografičnou klávesnici).</span><span class="sxs-lookup"><span data-stu-id="e3277-355">English-language QWERTY Bluetooth keyboards (you can use these anywhere that you use the holographic keyboard).</span></span>
- <span data-ttu-id="e3277-356">Bluetooth mice.</span><span class="sxs-lookup"><span data-stu-id="e3277-356">Bluetooth mice.</span></span>
- <span data-ttu-id="e3277-357">Na [HoloLens klikněte na .](hololens1-clicker.md)</span><span class="sxs-lookup"><span data-stu-id="e3277-357">The [HoloLens clicker](hololens1-clicker.md).</span></span>

<span data-ttu-id="e3277-358">Můžete spárovat jiná zařízení Bluetooth HID a PAIR s vašimi HoloLens.</span><span class="sxs-lookup"><span data-stu-id="e3277-358">You can pair other Bluetooth HID and GATT devices together with your HoloLens.</span></span> <span data-ttu-id="e3277-359">Je však možné, že budete muset nainstalovat odpovídající doprovodné aplikace z Microsoft Store, aby bylo možné zařízení skutečně používat.</span><span class="sxs-lookup"><span data-stu-id="e3277-359">However, you may have to install corresponding companion apps from Microsoft Store to actually use the devices.</span></span>

[<span data-ttu-id="e3277-360">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="e3277-360">Back to list</span></span>](#list)
