---
title: Známé problémy pro HoloLens
description: Seznam známých problémů a alternativních řešení, která mohou ovlivnit zákazníky a vývojáře HoloLens využívající Unity a Portál zařízení s Windows.
keywords: řešení potíží, známý problém, nápověda
author: mattzmsft
ms.author: mazeller
ms.date: 11/30/2020
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
- HoloLens 2
ms.openlocfilehash: bc1d399a07a6a0622c953178cad7be1b8a018fdb
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111377649"
---
# <a name="known-issues-for-hololens"></a><span data-ttu-id="7644d-104">Známé problémy pro HoloLens</span><span class="sxs-lookup"><span data-stu-id="7644d-104">Known issues for HoloLens</span></span>

<span data-ttu-id="7644d-105">Tady je aktuální seznam známých problémů pro zařízení HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7644d-105">Here is the current list of known issues for HoloLens devices.</span></span> <span data-ttu-id="7644d-106">Nejprve zkontrolujte, jestli se vám nesnídí chování.</span><span class="sxs-lookup"><span data-stu-id="7644d-106">Check here first if you are seeing an odd behavior.</span></span> <span data-ttu-id="7644d-107">Tento seznam se bude aktualizovat při zjištěných nebo nahlášených nových problémech nebo při řešení problémů v budoucích aktualizacích softwaru HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7644d-107">This list will be kept updated as new issues are discovered or reported, or as issues are addressed in future HoloLens software updates.</span></span>

>[!NOTE]
> - <span data-ttu-id="7644d-108">Pokud zjistíte problém, který neblokuje, nahlásit ho prosím na svém zařízení HoloLens přes [Centrum Feedback](hololens-feedback.md).</span><span class="sxs-lookup"><span data-stu-id="7644d-108">If you discover an issue that is not blocking you please report it on your HoloLens device via [Feedback Hub](hololens-feedback.md).</span></span>
> - <span data-ttu-id="7644d-109">Pokud vás váš problém blokuje, kromě vyplnění zpětné vazby uveďte také žádost [o podporu.](https://aka.ms/hlsupport)</span><span class="sxs-lookup"><span data-stu-id="7644d-109">If the issue you are facing is blocking you, in addition to filing feedback, please [file a support request](https://aka.ms/hlsupport).</span></span>

- [<span data-ttu-id="7644d-110">Známé problémy pro všechny generace HoloLens</span><span class="sxs-lookup"><span data-stu-id="7644d-110">Known issues for all HoloLens generations</span></span>](#known-issues-for-all-hololens-generations)
- [<span data-ttu-id="7644d-111">Známé problémy pro zařízení HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="7644d-111">Known issues for HoloLens 2 devices</span></span>](#known-issues-for-hololens-2-devices)
- [<span data-ttu-id="7644d-112">Známé problémy s HoloLens (1. generace)</span><span class="sxs-lookup"><span data-stu-id="7644d-112">Known issues for HoloLens (1st Gen)</span></span>](#known-issues-for-hololens-1st-gen)
- [<span data-ttu-id="7644d-113">Známé problémy s emulátorem HoloLens</span><span class="sxs-lookup"><span data-stu-id="7644d-113">Known issues for HoloLens emulator</span></span>](#known-issues-for-hololens-emulator)

## <a name="known-issues-for-all-hololens-generations"></a><span data-ttu-id="7644d-114">Známé problémy pro všechny generace HoloLens</span><span class="sxs-lookup"><span data-stu-id="7644d-114">Known issues for all HoloLens generations</span></span>

### <a name="unity"></a><span data-ttu-id="7644d-115">Unity</span><span class="sxs-lookup"><span data-stu-id="7644d-115">Unity</span></span>

- <span data-ttu-id="7644d-116">Nejnovější [verzi Unity doporučenou](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) pro vývoj pro HoloLens najdete v tématu Instalace nástrojů.</span><span class="sxs-lookup"><span data-stu-id="7644d-116">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="7644d-117">Známé problémy s Unity HoloLens Technical Preview jsou dokumentované na fórech [HoloLens Unity.](https://forum.unity3d.com/threads/known-issues.394627/)</span><span class="sxs-lookup"><span data-stu-id="7644d-117">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

### <a name="windows-device-portal"></a><span data-ttu-id="7644d-118">Portál zařízení s Windows</span><span class="sxs-lookup"><span data-stu-id="7644d-118">Windows Device Portal</span></span>

- <span data-ttu-id="7644d-119">Funkce Live Preview v Mixed Reality může vykazovat latenci několik sekund.</span><span class="sxs-lookup"><span data-stu-id="7644d-119">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="7644d-120">Na stránce Virtuální vstup nejsou ovládací prvky Gesture a Scroll v části Virtuální gesta funkční.</span><span class="sxs-lookup"><span data-stu-id="7644d-120">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="7644d-121">Jejich použití nebude mít žádný vliv.</span><span class="sxs-lookup"><span data-stu-id="7644d-121">Using them will have no effect.</span></span> <span data-ttu-id="7644d-122">Virtuální klávesnice na stránce virtuálního vstupu funguje správně.</span><span class="sxs-lookup"><span data-stu-id="7644d-122">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="7644d-123">Po povolení režimu pro vývojáře v Nastavení může trvat několik sekund, než se přepínač zapne, Portál zařízení povoleno.</span><span class="sxs-lookup"><span data-stu-id="7644d-123">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

### <a name="onedrive-camera-upload"></a><span data-ttu-id="7644d-124">Nahrání fotoaparátu na OneDrive</span><span class="sxs-lookup"><span data-stu-id="7644d-124">OneDrive camera upload</span></span>

<span data-ttu-id="7644d-125">Aplikace OneDrive pro HoloLens nepodporuje automatické nahrávání z fotoaparátu pro pracovní nebo školní účty.</span><span class="sxs-lookup"><span data-stu-id="7644d-125">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span>

<span data-ttu-id="7644d-126">Alternativní řešení:</span><span class="sxs-lookup"><span data-stu-id="7644d-126">Workarounds:</span></span>

- <span data-ttu-id="7644d-127">Pokud je pro vaši firmu přijatelné, je u uživatelských účtů Microsoft podporováno automatické nahrávání fotoaparátu.</span><span class="sxs-lookup"><span data-stu-id="7644d-127">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="7644d-128">K pracovnímu nebo školnímu účtu se účet Microsoft přihlásit i ke svému pracovnímu nebo školnímu účtu (aplikace OneDrive podporuje duální přihlášení).</span><span class="sxs-lookup"><span data-stu-id="7644d-128">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="7644d-129">Ve svém účet Microsoft v rámci OneDrivu můžete povolit automatické nahrávání fotoaparátů na pozadí.</span><span class="sxs-lookup"><span data-stu-id="7644d-129">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="7644d-130">Pokud nemůžete bezpečně používat uživatelský účet účet Microsoft k automatickému nahrávání fotek, můžete fotky z aplikace OneDrive nahrát ručně do svého pracovního nebo školního účtu.</span><span class="sxs-lookup"><span data-stu-id="7644d-130">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="7644d-131">Pokud to chcete udělat, ujistěte se, že jste v aplikaci OneDrive přihlášení ke svému pracovnímu nebo školnímu účtu.</span><span class="sxs-lookup"><span data-stu-id="7644d-131">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="7644d-132">Vyberte tlačítko **+** a zvolte **Nahrát.**</span><span class="sxs-lookup"><span data-stu-id="7644d-132">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="7644d-133">Najděte fotky nebo videa, které chcete nahrát, tak, že přejdete na Obrázky **> fotoaparátu.**</span><span class="sxs-lookup"><span data-stu-id="7644d-133">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="7644d-134">Vyberte fotky nebo videa, která chcete nahrát, a pak vyberte **tlačítko** Otevřít.</span><span class="sxs-lookup"><span data-stu-id="7644d-134">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

## <a name="known-issues-for-hololens-2-devices"></a><span data-ttu-id="7644d-135">Známé problémy pro zařízení HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="7644d-135">Known issues for HoloLens 2 devices</span></span>

### <a name="device-using-auto-login-asks-for-log-in"></a><span data-ttu-id="7644d-136">Zařízení s využitím automatického přihlášení žádá o přihlášení</span><span class="sxs-lookup"><span data-stu-id="7644d-136">Device using Auto-login asks for log-in</span></span>

<span data-ttu-id="7644d-137">Zařízení HoloLens 2 je možné nakonfigurovat tak, aby se automaticky přihlašoval přes Nastavení Účty Možnosti přihlášení -> a v části  ->    ->    Požadováno na hodnotu Nikdy **.**</span><span class="sxs-lookup"><span data-stu-id="7644d-137">A HoloLens 2 device can be configured to automatically login in via **Settings** -> **Accounts** -> **Sign-in Options** -> and under **Required** setting the value to **Never**.</span></span> <span data-ttu-id="7644d-138">Někteří uživatelé se při aktualizaci zařízení s podstatně velkou aktualizací, jako je třeba aktualizace funkcí, mohou znova přihlásit k zařízení.</span><span class="sxs-lookup"><span data-stu-id="7644d-138">Some users may be required to log-in to the device again when updating a device with a substantially large update, such as a feature update.</span></span>

<span data-ttu-id="7644d-139">Příklad, kdy k tomu může dojít:</span><span class="sxs-lookup"><span data-stu-id="7644d-139">Example of when this could occur:</span></span>

- <span data-ttu-id="7644d-140">Aktualizace zařízení z Windows Holographic verze 2004 (build 19041.xxxx) na Windows Holographic verze 21H1 (build 20346.xxxx)</span><span class="sxs-lookup"><span data-stu-id="7644d-140">Updating a device from Windows Holographic, version 2004 (Build 19041.xxxx) to Windows Holographic, version 21H1 (Build 20346.xxxx)</span></span>
- <span data-ttu-id="7644d-141">Aktualizace zařízení tak, aby šouplodou aktualizaci ve stejném hlavním buildu, např. Windows Holographic, verze 2004 na Windows Holographic, verze 20H2</span><span class="sxs-lookup"><span data-stu-id="7644d-141">Updating a device to take a large update on the same major build, e.g. Windows Holographic, version 2004 to Windows Holographic, version 20H2</span></span>
- <span data-ttu-id="7644d-142">Aktualizace zařízení z image továrny na nejnovější image</span><span class="sxs-lookup"><span data-stu-id="7644d-142">Updating a device from a factory image to the latest image</span></span>

<span data-ttu-id="7644d-143">K tomu by nemělo dojít během těchto období:</span><span class="sxs-lookup"><span data-stu-id="7644d-143">This should not occur during:</span></span>

- <span data-ttu-id="7644d-144">Zařízení, která mají měsíční servisní aktualizaci</span><span class="sxs-lookup"><span data-stu-id="7644d-144">Devices taking a monthly servicing update</span></span>

<span data-ttu-id="7644d-145">Alternativní metody:</span><span class="sxs-lookup"><span data-stu-id="7644d-145">Work around methods:</span></span>

- <span data-ttu-id="7644d-146">Metody přihlášení, jako jsou PIN, heslo, Iris, webové ověřování nebo klíče FIDO2.</span><span class="sxs-lookup"><span data-stu-id="7644d-146">Sign-in methods such as PIN, Password, Iris, Web Authentication, or FIDO2 keys.</span></span>
- <span data-ttu-id="7644d-147">Pokud pin kód zařízení nelze zapamatovat a jiné metody ověřování nejsou k dispozici, může uživatel použít režim [ručního lomítka](hololens-recovery.md#manual-procedure).</span><span class="sxs-lookup"><span data-stu-id="7644d-147">If device PIN cannot be remembered, and other authentication methods are not available, then a user can use [manual reflashing mode](hololens-recovery.md#manual-procedure).</span></span>

### <a name="microsoft-edge-fails-to-launch"></a><span data-ttu-id="7644d-148">Microsoft Edge spuštění se nepovede</span><span class="sxs-lookup"><span data-stu-id="7644d-148">Microsoft Edge fails to launch</span></span>

> [!NOTE]
> <span data-ttu-id="7644d-149">Tento problém byl původně vytvořen s náklady na Microsoft Edge verzí.</span><span class="sxs-lookup"><span data-stu-id="7644d-149">This issue was originally created with the shipping version of Microsoft Edge in-mind.</span></span> <span data-ttu-id="7644d-150">Tento problém se může vyřešit v [nové Microsoft Edge](hololens-new-edge.md).</span><span class="sxs-lookup"><span data-stu-id="7644d-150">This issue may be resolved in the [new Microsoft Edge](hololens-new-edge.md).</span></span> <span data-ttu-id="7644d-151">Pokud ne, zpětnou vazbu nahlaste.</span><span class="sxs-lookup"><span data-stu-id="7644d-151">If it is not, please file feedback.</span></span>

<span data-ttu-id="7644d-152">Několik zákazníků nahlásilo problém, kdy Microsoft Edge spuštění.</span><span class="sxs-lookup"><span data-stu-id="7644d-152">A few customers have reported an issue where Microsoft Edge fails to launch.</span></span> <span data-ttu-id="7644d-153">U těchto zákazníků problém přetrvává i po restartování a nevyřeší se aktualizacemi aplikací nebo Windows.</span><span class="sxs-lookup"><span data-stu-id="7644d-153">For these customers, the issue persists through reboot and is not resolved with Windows or application updates.</span></span> <span data-ttu-id="7644d-154">Pokud k tomuto problému dochází a potvrdili jste, že [je Windows](hololens-updates.md#manually-check-for-updates)aktuální, zakažte chybu z aplikace [Centrum Feedback](hololens-feedback.md) s následující kategorií a podkate kategorií: Instalace a aktualizace > Stažení, instalace a konfigurace služba Windows Update.</span><span class="sxs-lookup"><span data-stu-id="7644d-154">If you're experiencing this issue and you've confirmed [Windows is up-to-date](hololens-updates.md#manually-check-for-updates), please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.</span></span>

<span data-ttu-id="7644d-155">Neexistují žádná známá alternativní řešení, protože jsme zatím nemohli hlavní příčinu problému.</span><span class="sxs-lookup"><span data-stu-id="7644d-155">There are no known workarounds as we've been unable to root cause the issue so far.</span></span> <span data-ttu-id="7644d-156">S vyšetřováním vám pomůže Centrum Feedback chyb prostřednictvím webu společnosti.</span><span class="sxs-lookup"><span data-stu-id="7644d-156">Filing a bug via Feedback Hub will help our investigation!</span></span>

### <a name="keyboard-does-not-switch-to-special-characters"></a><span data-ttu-id="7644d-157">Klávesnice nepřekašuje na speciální znaky</span><span class="sxs-lookup"><span data-stu-id="7644d-157">Keyboard does not switch to special characters</span></span>

<span data-ttu-id="7644d-158">Při ooBE dochází k problému, kdy se po zvolení pracovního nebo školního účtu a zadání hesla uživatel pokouší přepnout na speciální znaky na klávesnici klepnutím na tlačítko &123, nezmění se na speciální znaky.</span><span class="sxs-lookup"><span data-stu-id="7644d-158">There is an issue during OOBE, where once the user has chosen a work or school account and is entering their password, trying to switch to the special characters on the keyboard by tapping the &123 button does not change to special characters.</span></span>

<span data-ttu-id="7644d-159">Obchádky:</span><span class="sxs-lookup"><span data-stu-id="7644d-159">Work-arounds:</span></span>
-   <span data-ttu-id="7644d-160">Zavřete klávesnici a znovu ji otevřete klepnutím na textové pole.</span><span class="sxs-lookup"><span data-stu-id="7644d-160">Close the keyboard and reopen it by tapping the text field.</span></span>
-   <span data-ttu-id="7644d-161">Nesprávně zadejte heslo.</span><span class="sxs-lookup"><span data-stu-id="7644d-161">Incorrectly enter your password.</span></span> <span data-ttu-id="7644d-162">Při příštím spuštění klávesnice bude klávesnice fungovat podle očekávání.</span><span class="sxs-lookup"><span data-stu-id="7644d-162">When the keyboard is relaunched next time it will then work as expected.</span></span>
- <span data-ttu-id="7644d-163">Webové ověřování, zavřete klávesnici a vyberte **Přihlásit se z jiného zařízení**.</span><span class="sxs-lookup"><span data-stu-id="7644d-163">Web Authentication, close the keyboard and select **Sign in from another device**.</span></span>
-   <span data-ttu-id="7644d-164">Pokud zadáváte jenom čísla, uživatel může stisknutím a podržením určitých kláves otevřít rozbalenou nabídku.</span><span class="sxs-lookup"><span data-stu-id="7644d-164">If entering only numbers, a user may press and hold certain keys to open an expanded menu.</span></span>
-   <span data-ttu-id="7644d-165">Pomocí klávesnice USB.</span><span class="sxs-lookup"><span data-stu-id="7644d-165">Using a USB keyboard.</span></span>

<span data-ttu-id="7644d-166">To nemá vliv na:</span><span class="sxs-lookup"><span data-stu-id="7644d-166">This does not affect:</span></span>
- <span data-ttu-id="7644d-167">Uživatelé, kteří se rozhodnout použít osobní účet.</span><span class="sxs-lookup"><span data-stu-id="7644d-167">Users who choose to use a personal account.</span></span>

### <a name="blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-an-insider-build"></a><span data-ttu-id="7644d-168">Modrá obrazovka se zobrazí po zrušení registrace v buildech Insider Preview na zařízení, které je v souladu se sestavením Insider.</span><span class="sxs-lookup"><span data-stu-id="7644d-168">Blue screen is shown after unenrolling from Insider preview builds on a device reflashed with an Insider build</span></span>

<span data-ttu-id="7644d-169">Jedná se o problém ovlivňující uživatele, kteří byli v buildu Insider ve verzi Preview, odmítnul HoloLens 2 novým buildem insider ve verzi Preview a pak zrušit jeho zrušení v programu Insider.</span><span class="sxs-lookup"><span data-stu-id="7644d-169">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span>

<span data-ttu-id="7644d-170">To nemá vliv na:</span><span class="sxs-lookup"><span data-stu-id="7644d-170">This does not affect:</span></span>
- <span data-ttu-id="7644d-171">Uživatelé, kteří nejsou zaregistrovaní v Windows Insider</span><span class="sxs-lookup"><span data-stu-id="7644d-171">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="7644d-172">Zasvěcenci:</span><span class="sxs-lookup"><span data-stu-id="7644d-172">Insiders:</span></span>
    - <span data-ttu-id="7644d-173">Pokud bylo zařízení zaregistrované od sestavení Insider verze 18362.x</span><span class="sxs-lookup"><span data-stu-id="7644d-173">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="7644d-174">Pokud se v programu Insider blikal podepsaný build 19041.x a zůstal zaregistrovaný v programu Insider</span><span class="sxs-lookup"><span data-stu-id="7644d-174">If they flashed an Insider signed 19041.x build AND stay enrolled in the Insider program</span></span>

<span data-ttu-id="7644d-175">Obchádky:</span><span class="sxs-lookup"><span data-stu-id="7644d-175">Work-around:</span></span> 
- <span data-ttu-id="7644d-176">Vyhněte se problému</span><span class="sxs-lookup"><span data-stu-id="7644d-176">Avoid the issue</span></span> 
    - <span data-ttu-id="7644d-177">Flash sestavení, které není zevnitř.</span><span class="sxs-lookup"><span data-stu-id="7644d-177">Flash a non-insider build.</span></span> <span data-ttu-id="7644d-178">Jedna z běžných měsíčních aktualizací.</span><span class="sxs-lookup"><span data-stu-id="7644d-178">One of the regular monthly updates.</span></span>
    - <span data-ttu-id="7644d-179">Zůstaňte ve verzi Insider Preview</span><span class="sxs-lookup"><span data-stu-id="7644d-179">Stay on Insider Preview</span></span>
- <span data-ttu-id="7644d-180">Odkazování zařízení</span><span class="sxs-lookup"><span data-stu-id="7644d-180">Reflash the device</span></span>

    1. <span data-ttu-id="7644d-181">Dejte [HoloLens 2 do režimu blikajícího](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) režimu ručně úplným vypnutím, zatímco se nepřipojí.</span><span class="sxs-lookup"><span data-stu-id="7644d-181">Put the [HoloLens 2 into flashing mode](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) manually by fully powering down while not connect.</span></span> <span data-ttu-id="7644d-182">Při podržíte Tlačítko napájení klepněte na tlačítko Napájení.</span><span class="sxs-lookup"><span data-stu-id="7644d-182">Then while holding Volume up, tap the Power button.</span></span>
    
    1. <span data-ttu-id="7644d-183">Připojte se k počítači a otevřete Doprovodný průvodce pokročilým obnovením.</span><span class="sxs-lookup"><span data-stu-id="7644d-183">Connect to the PC and open Advanced Recovery Companion.</span></span>
    
    1. <span data-ttu-id="7644d-184">Flash disk HoloLens 2 do výchozího sestavení.</span><span class="sxs-lookup"><span data-stu-id="7644d-184">Flash the HoloLens 2 to the default build.</span></span>

## <a name="known-issues-for-hololens-1st-gen"></a><span data-ttu-id="7644d-185">Známé problémy s HoloLens (1. generace)</span><span class="sxs-lookup"><span data-stu-id="7644d-185">Known issues for HoloLens (1st Gen)</span></span>

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a><span data-ttu-id="7644d-186">Nelze se připojit a nasadit do HoloLens prostřednictvím Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7644d-186">Unable to connect and deploy to HoloLens through Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="7644d-187">Poslední aktualizace: 8/8 @ 17:11 – Visual Studio vydala VS 2019 verze 16.2, která zahrnuje opravu tohoto problému.</span><span class="sxs-lookup"><span data-stu-id="7644d-187">Last Update: 8/8 @ 5:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="7644d-188">Doporučujeme provést aktualizaci na tuto nejnovější verzi, abyste se vyhnuli této chybě.</span><span class="sxs-lookup"><span data-stu-id="7644d-188">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="7644d-189">Visual Studio vydali VS 2019 verze 16.2, která zahrnuje opravu tohoto problému.</span><span class="sxs-lookup"><span data-stu-id="7644d-189">Visual Studio has released VS 2019 Version 16.2, which includes a fix to this issue.</span></span> <span data-ttu-id="7644d-190">Doporučujeme provést aktualizaci na tuto nejnovější verzi, abyste se vyhnuli této chybě.</span><span class="sxs-lookup"><span data-stu-id="7644d-190">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="7644d-191">Hlavní příčina problému: Uživatelé, kteří použili Visual Studio 2015 nebo dřívější verze Visual Studio 2017 k nasazení a ladění aplikací na zařízení HoloLens a následně použili nejnovější verze Visual Studio 2017 nebo Visual Studio 2019 se stejným HoloLensem, budou ovlivněni.</span><span class="sxs-lookup"><span data-stu-id="7644d-191">Issue root-cause: Users who used Visual Studio 2015 or early releases of Visual Studio 2017 to deploy and debug applications on their HoloLens and then subsequently used the latest versions of Visual Studio 2017 or Visual Studio 2019 with the same HoloLens will be affected.</span></span> <span data-ttu-id="7644d-192">Novější verze Visual Studio nasadí novou verzi komponenty, ale soubory ze starší verze zůstanou na zařízení, což způsobí selhání novější verze.</span><span class="sxs-lookup"><span data-stu-id="7644d-192">The newer releases of Visual Studio deploy a new version of a component, but files from the older version are left over on the device, causing the newer version to fail.</span></span>  <span data-ttu-id="7644d-193">To způsobí následující chybovou zprávu: DEP0100: Ujistěte se, že cílové zařízení má povolený vývojářský režim.</span><span class="sxs-lookup"><span data-stu-id="7644d-193">This causes the following error message: DEP0100: Ensure that target device has developer mode enabled.</span></span> <span data-ttu-id="7644d-194">Nelze získat vývojářské licence pro \<ip\> kvůli chybě 80004005.</span><span class="sxs-lookup"><span data-stu-id="7644d-194">Could not obtain a developer license on \<ip\> due to error 80004005.</span></span>

#### <a name="workaround"></a><span data-ttu-id="7644d-195">Alternativní řešení</span><span class="sxs-lookup"><span data-stu-id="7644d-195">Workaround</span></span>

<span data-ttu-id="7644d-196">Náš tým aktuálně pracuje na opravě.</span><span class="sxs-lookup"><span data-stu-id="7644d-196">Our team is currently working on a fix.</span></span> <span data-ttu-id="7644d-197">Do té doby můžete pomocí následujících kroků problém obvyřešit a odblokovat nasazení a ladění:</span><span class="sxs-lookup"><span data-stu-id="7644d-197">In the meantime, you can use the following steps to work around the issue and help unblock deployment and debugging:</span></span>  

1. <span data-ttu-id="7644d-198">Otevřete sadu Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7644d-198">Open Visual Studio.</span></span>

1. <span data-ttu-id="7644d-199">Vyberte **File** New Project  >  **(Soubor nového**  >  **projektu).**</span><span class="sxs-lookup"><span data-stu-id="7644d-199">Select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="7644d-200">Vyberte **Visual C#**  >  **Desktopová**  >  **konzolová aplikace windows (.NET Framework).**</span><span class="sxs-lookup"><span data-stu-id="7644d-200">Select **Visual C#** > **Windows Desktop** > **Console App (.NET Framework)**.</span></span>

1. <span data-ttu-id="7644d-201">Dejte projektu název (například HoloLensDeploymentFix) a ujistěte se, že je rozhraní nastavené alespoň na .NET Framework 4.5, a pak vyberte **OK.**</span><span class="sxs-lookup"><span data-stu-id="7644d-201">Give the project a name (such as "HoloLensDeploymentFix") and make sure the Framework is set to at least .NET Framework 4.5, then Select **OK**.</span></span>

1. <span data-ttu-id="7644d-202">Klikněte pravým tlačítkem **na** uzel Odkazy v Průzkumník řešení přidejte následující odkazy (vyberte v části **Procházet** a vyberte **Procházet**):</span><span class="sxs-lookup"><span data-stu-id="7644d-202">Right-click the **References** node in Solution Explorer and add the following references (select to the **Browse** section and select **Browse**):</span></span>

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > <span data-ttu-id="7644d-203">Pokud nemáte nainstalovanou verzi 10.0.18362.0, použijte nejnovější verzi, kterou máte.</span><span class="sxs-lookup"><span data-stu-id="7644d-203">If you don't have 10.0.18362.0 installed, use the most recent version that you have.</span></span> 

1. <span data-ttu-id="7644d-204">Klikněte pravým tlačítkem na projekt v Průzkumník řešení **a vyberte Přidat** existující  >  **položku**.</span><span class="sxs-lookup"><span data-stu-id="7644d-204">Right-click on the project in Solution Explorer and select **Add** > **Existing Item**.</span></span>

1. <span data-ttu-id="7644d-205">Přejděte do složky C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 a změňte filtr na **Všechny soubory ( . \* \* ).**</span><span class="sxs-lookup"><span data-stu-id="7644d-205">Browse to C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 and change the filter to **All Files (\*.\*)**.</span></span>

1. <span data-ttu-id="7644d-206">Vyberte SirepClient.dll i SshClient.dll a vyberte **Přidat.**</span><span class="sxs-lookup"><span data-stu-id="7644d-206">Select both SirepClient.dll and SshClient.dll, and Select **Add**.</span></span>

1. <span data-ttu-id="7644d-207">Vyhledejte a vyberte oba soubory v Průzkumník řešení (měly by být v dolní  části seznamu souborů) a změňte Kopírovat do výstupního adresáře v okně Vlastnosti na **Kopírovat vždy**. </span><span class="sxs-lookup"><span data-stu-id="7644d-207">Locate and select both files in Solution Explorer (they should be at the bottom of the list of files) and change **Copy to Output Directory** in the **Properties** window to **Copy always**.</span></span>

1. <span data-ttu-id="7644d-208">Na začátek souboru přidejte následující kód do existujícího seznamu `using` příkazů:</span><span class="sxs-lookup"><span data-stu-id="7644d-208">At the top of the file, add the following to the existing list of `using` statements:</span></span>

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. <span data-ttu-id="7644d-209">Do `static void Main(...)` souboru přidejte následující kód:</span><span class="sxs-lookup"><span data-stu-id="7644d-209">Inside of `static void Main(...)`, add the following code:</span></span>

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. <span data-ttu-id="7644d-210">Vyberte **Build**  >  **Build Solution (Sestavit řešení sestavení).**</span><span class="sxs-lookup"><span data-stu-id="7644d-210">Select **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="7644d-211">Otevřete okno příkazového řádku a cd do složky, která obsahuje zkompilovaný soubor .exe (například C:\MyProjects\HoloLensDeploymentFix\bin\Debug).</span><span class="sxs-lookup"><span data-stu-id="7644d-211">Open a Command Prompt Window and cd to the folder that contains the compiled .exe file (for example, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).</span></span>

1. <span data-ttu-id="7644d-212">Spusťte spustitelný soubor a jako argument příkazového řádku zadejte IP adresu zařízení.</span><span class="sxs-lookup"><span data-stu-id="7644d-212">Run the executable and provide the device's IP address as a command-line argument.</span></span> <span data-ttu-id="7644d-213">(Pokud jste připojení pomocí USB, můžete použít 127.0.0.1, jinak použijte IP adresu zařízení Wi-Fi ip adresu.)  Například HoloLensDeploymentFix 127.0.0.1.</span><span class="sxs-lookup"><span data-stu-id="7644d-213">(If connected using USB, you can use 127.0.0.1, otherwise use the device's Wi-Fi IP address.)  For example, "HoloLensDeploymentFix 127.0.0.1".</span></span>

1. <span data-ttu-id="7644d-214">Jakmile se nástroj ukončí bez jakýchkoli zpráv (mělo by to trvat jen pár sekund), budete moct nasadit a ladit z Visual Studio 2017 nebo novější verze.</span><span class="sxs-lookup"><span data-stu-id="7644d-214">After the tool has exited without any messages (this should only take a few seconds), you will now be able to deploy and debug from Visual Studio 2017 or newer.</span></span>  <span data-ttu-id="7644d-215">Průběžné používání nástroje není nutné.</span><span class="sxs-lookup"><span data-stu-id="7644d-215">Continued use of the tool is not necessary.</span></span>

<span data-ttu-id="7644d-216">Jakmile budou k dispozici, budeme poskytovat další aktualizace.</span><span class="sxs-lookup"><span data-stu-id="7644d-216">We will provide further updates as they become available.</span></span>

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a><span data-ttu-id="7644d-217">Problémy se spouštěním Microsoft Store a aplikací na HoloLens</span><span class="sxs-lookup"><span data-stu-id="7644d-217">Issues launching the Microsoft Store and apps on HoloLens</span></span>

> [!NOTE]
> <span data-ttu-id="7644d-218">Poslední aktualizace: 4/2 @ 10:00 – Problém se vyřešil.</span><span class="sxs-lookup"><span data-stu-id="7644d-218">Last Update: 4/2 @ 10 AM - Issue resolved.</span></span>

<span data-ttu-id="7644d-219">Při pokusu o spuštění aplikace a Microsoft Store na HoloLens může docházet k problémům.</span><span class="sxs-lookup"><span data-stu-id="7644d-219">You may experience issues when trying to launch the Microsoft Store and apps on HoloLens.</span></span> <span data-ttu-id="7644d-220">Zjistili jsme, že k problému dochází, když aktualizace aplikací na pozadí nasadí novější verzi balíčků architektury v určitých sekvencích, zatímco jedna nebo více jejich závislých aplikací stále běží.</span><span class="sxs-lookup"><span data-stu-id="7644d-220">We've determined that the issue occurs when background app updates deploy a newer version of framework packages in specific sequences while one or more of their dependent apps are still running.</span></span> <span data-ttu-id="7644d-221">Automatická aktualizace aplikace v tomto případě doručila novou verzi rozhraní .NET Native Framework (verze 10.0.25531 až 10.0.27413), která způsobila, že se aplikace, které běží, správně ne aktualizují pro všechny spuštěné aplikace využívající předchozí verzi rozhraní.</span><span class="sxs-lookup"><span data-stu-id="7644d-221">In this case,  an automatic app update delivered a new version of the .NET Native Framework (version 10.0.25531 to 10.0.27413) caused the apps that are running to not correctly update for all running apps consuming the prior version of the framework.</span></span>  <span data-ttu-id="7644d-222">Postup aktualizace architektury je následující:</span><span class="sxs-lookup"><span data-stu-id="7644d-222">The flow for framework update is as follows:</span></span>

1. <span data-ttu-id="7644d-223">Nový balíček architektury se stáhne z úložiště a nainstaluje.</span><span class="sxs-lookup"><span data-stu-id="7644d-223">The new framework package is downloaded from the store and installed.</span></span>

1. <span data-ttu-id="7644d-224">Všechny aplikace starší rozhraní jsou "aktualizované" tak, aby se používá novější verze.</span><span class="sxs-lookup"><span data-stu-id="7644d-224">All apps using the older framework are 'updated' to use the newer version.</span></span>

<span data-ttu-id="7644d-225">Pokud se krok 2 přeruší před dokončením, nespustí se z nabídky Start žádné aplikace, pro které se novější rozhraní nezaregistruje.</span><span class="sxs-lookup"><span data-stu-id="7644d-225">If step 2 is interrupted before completion, then any apps for which the newer framework wasn't registered will fail to launch from the start menu.</span></span>  <span data-ttu-id="7644d-226">Věříme, že tento problém může mít vliv na libovolnou aplikaci v HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7644d-226">We believe any app on HoloLens could be affected by this issue.</span></span>

<span data-ttu-id="7644d-227">Někteří uživatelé oznámili, že problém vyřeší zavření zamykacích aplikací a spuštění jiných aplikací, jako jsou Centrum Feedback, 3D prohlížeč nebo Fotky, ale ve 100 % případů to nefunguje.</span><span class="sxs-lookup"><span data-stu-id="7644d-227">Some users have reported that closing hung apps and launching other apps such as Feedback Hub, 3D Viewer or Photos resolves the issue for them - however, this does not work 100% of the time.</span></span>

<span data-ttu-id="7644d-228">Root způsobil, že tento problém nez způsoboval samotnou aktualizaci, ale chybu v operačním systému, která způsobila nesprávnou .NET Native rozhraní.</span><span class="sxs-lookup"><span data-stu-id="7644d-228">We have root caused that this issue was not caused the update itself, but a bug in the OS that resulted in the .NET Native framework update being handled incorrectly.</span></span> <span data-ttu-id="7644d-229">S radostí oznamujeme, že jsme zjistili opravu a vydali jsme aktualizaci (operační systém verze 17763.380), která obsahuje opravu.</span><span class="sxs-lookup"><span data-stu-id="7644d-229">We are pleased to announce that we have identified a fix and have released an update (OS version 17763.380) containing the fix.</span></span>  

<span data-ttu-id="7644d-230">Pokud chcete zjistit, jestli vaše zařízení může aktualizaci přijmout:</span><span class="sxs-lookup"><span data-stu-id="7644d-230">To see if your device can take the update:</span></span>

1. <span data-ttu-id="7644d-231">Přejděte do aplikace Nastavení a otevřete **Update & Security**.</span><span class="sxs-lookup"><span data-stu-id="7644d-231">Go to the Settings app and open **Update & Security**.</span></span>

1. <span data-ttu-id="7644d-232">Vyberte **Zkontrolovat aktualizace.**</span><span class="sxs-lookup"><span data-stu-id="7644d-232">Select **Check for Updates**.</span></span>

1. <span data-ttu-id="7644d-233">Pokud je k dispozici aktualizace na 17763.380, aktualizujte na toto sestavení, abyste obdrželi opravu chyby Zablokuje aplikaci.</span><span class="sxs-lookup"><span data-stu-id="7644d-233">If update to 17763.380 is available, please update to this build to receive the fix for the App Hang bug.</span></span>

1. <span data-ttu-id="7644d-234">Po aktualizaci na tuto verzi operačního systému by aplikace měly fungovat podle očekávání.</span><span class="sxs-lookup"><span data-stu-id="7644d-234">Upon updating to this version of the OS, the Apps should work as expected.</span></span>

<span data-ttu-id="7644d-235">Stejně jako u každé verze operačního systému HoloLens jsme image FFU také zveřejnili na [webu Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380).</span><span class="sxs-lookup"><span data-stu-id="7644d-235">Additionally, as we do with every HoloLens OS release, we have posted the FFU image to the [Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380).</span></span>

<span data-ttu-id="7644d-236">Pokud 29. 3. 2019 2019 vezměme aktualizaci, vydali jsme novou verzi aplikace Microsoft Store UPW.</span><span class="sxs-lookup"><span data-stu-id="7644d-236">If you would not like to take the update, we have released a new version of the Microsoft Store UWP app as of 3/29.</span></span> <span data-ttu-id="7644d-237">Po aktualizaci verze Storu:</span><span class="sxs-lookup"><span data-stu-id="7644d-237">After you have the updated version of the Store:</span></span>

1. <span data-ttu-id="7644d-238">Otevřete Store a potvrďte, že se načte.</span><span class="sxs-lookup"><span data-stu-id="7644d-238">Open the Store and confirm that it loads.</span></span>
1. <span data-ttu-id="7644d-239">Pomocí gesta bloom otevřete nabídku.</span><span class="sxs-lookup"><span data-stu-id="7644d-239">Use the bloom gesture to open the menu.</span></span>
1. <span data-ttu-id="7644d-240">Pokuste se otevřít dříve poškozené aplikace.</span><span class="sxs-lookup"><span data-stu-id="7644d-240">Attempt to open previously broken apps.</span></span>
1. <span data-ttu-id="7644d-241">Pokud se pořád nespustila, klepněte a podržte ikonu poškozené aplikace a vyberte odinstalovat.</span><span class="sxs-lookup"><span data-stu-id="7644d-241">If it still cannot be launched, tap and hold the icon of the broken app and select uninstall.</span></span>
1. <span data-ttu-id="7644d-242">Přeinstalujte tyto aplikace ze Storu.</span><span class="sxs-lookup"><span data-stu-id="7644d-242">Reinstall these apps from the store.</span></span>

<span data-ttu-id="7644d-243">Pokud se vašemu zařízení pořád nedaří načíst aplikace, můžete pomocí následujícího postupu nainstalovat verzi .NET Native Framework a Runtime přes download center:</span><span class="sxs-lookup"><span data-stu-id="7644d-243">If your device is still unable to load apps, you can sideload a version of the .NET Native Framework and Runtime through the download center by following these steps:</span></span>

1. <span data-ttu-id="7644d-244">Stáhněte [si tento soubor ZIP](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) z webu Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="7644d-244">Please download [this zip file](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) from the Microsoft Download Center.</span></span> <span data-ttu-id="7644d-245">Při rozbalení se vytvoří dva soubory.</span><span class="sxs-lookup"><span data-stu-id="7644d-245">Unzipping will produce two files.</span></span>  <span data-ttu-id="7644d-246">technologie Microsoft .NET.Native.Runtime.1.7.appx a technologie Microsoft .NET.Native.Framework.1.7.appx.</span><span class="sxs-lookup"><span data-stu-id="7644d-246">Microsoft.NET.Native.Runtime.1.7.appx and Microsoft.NET.Native.Framework.1.7.appx.</span></span>

1. <span data-ttu-id="7644d-247">Ověřte, že je vaše zařízení odemknuté.</span><span class="sxs-lookup"><span data-stu-id="7644d-247">Please verify that your device is dev unlocked.</span></span>  <span data-ttu-id="7644d-248">Pokud jste to ještě neudělali, přečtěte si pokyny v [Portál zařízení s Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) článku.</span><span class="sxs-lookup"><span data-stu-id="7644d-248">If you haven't done that before, see [Using the Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) for instructions.</span></span>

1. <span data-ttu-id="7644d-249">Pak se chcete dostat do Portál zařízení s Windows.</span><span class="sxs-lookup"><span data-stu-id="7644d-249">You then want to get into the Windows Device Portal.</span></span> <span data-ttu-id="7644d-250">Doporučujeme to provést přes USB, a to zadáním do http://127.0.0.1:10080 prohlížeče.</span><span class="sxs-lookup"><span data-stu-id="7644d-250">Our recommendation is to do this over USB and you would do that by typing http://127.0.0.1:10080 into your browser.</span></span>

1. <span data-ttu-id="7644d-251">Jakmile budete mít Portál zařízení s Windows, potřebujeme, abyste tyto dva soubory, které jste stáhli, načtěte bokem.</span><span class="sxs-lookup"><span data-stu-id="7644d-251">After you have the Windows Device Portal up we need you to "side load" the two files that you downloaded.</span></span> <span data-ttu-id="7644d-252">K tomu je potřeba přejít na boční panel vlevo, dokud se dostanete do **části Aplikace** a nevyberte **Aplikace.**</span><span class="sxs-lookup"><span data-stu-id="7644d-252">To do that you need to go down the left side bar until you get to the **Apps** section and select **Apps**.</span></span>

1. <span data-ttu-id="7644d-253">Zobrazí se obrazovka podobná následující.</span><span class="sxs-lookup"><span data-stu-id="7644d-253">You will then see a screen that is similar to the below.</span></span>  <span data-ttu-id="7644d-254">Chcete přejít do části Instalace  aplikace a přejít do místa, kde jste tyto dva soubory APPX rozbalili.</span><span class="sxs-lookup"><span data-stu-id="7644d-254">You want to go to the section that says **Install App** and browse to where you unzipped those two APPX files.</span></span> <span data-ttu-id="7644d-255">Můžete provést pouze jednu po jedné, takže po výběru první z nich klikněte na Přejít v části Nasadit.</span><span class="sxs-lookup"><span data-stu-id="7644d-255">You can only do one at a time, so after you select the first one, then click on "Go" under the Deploy section.</span></span> <span data-ttu-id="7644d-256">Pak to proveďte pro druhý soubor APPX.</span><span class="sxs-lookup"><span data-stu-id="7644d-256">Then do this for the second APPX file.</span></span>

   ![Portál zařízení s Windows instalace Side-Loaded aplikace](images/20190322-DevicePortal.png)
   
1. <span data-ttu-id="7644d-258">V tuto chvíli věříme, že vaše aplikace by měly znovu fungovat a že se můžete dostat také do Storu.</span><span class="sxs-lookup"><span data-stu-id="7644d-258">At this point we believe your applications should start working again and that you can also get to the Store.</span></span>

1. <span data-ttu-id="7644d-259">V některých případech je nutné před spuštěním ovlivněných aplikací spustit další krok spuštění 3D prohlížeč aplikace.</span><span class="sxs-lookup"><span data-stu-id="7644d-259">In some cases, it is necessary run the additional step of launching the 3D Viewer app before affected apps will launch.</span></span> 

<span data-ttu-id="7644d-260">Vážíme si vaší trpělivosti, protože jsme tento problém vyřešili, a těšíme se, že ve spolupráci s naší komunitou vytvoříme Mixed Reality prostředí.</span><span class="sxs-lookup"><span data-stu-id="7644d-260">We appreciate your patience as we have gone through the process to get this issue resolved, and we look forward to continued working with our community to create successful Mixed Reality experiences.</span></span>

### <a name="device-update"></a><span data-ttu-id="7644d-261">Aktualizace zařízení</span><span class="sxs-lookup"><span data-stu-id="7644d-261">Device Update</span></span>

- <span data-ttu-id="7644d-262">30 sekund po nové aktualizaci může prostředí jednou zmizet.</span><span class="sxs-lookup"><span data-stu-id="7644d-262">30 seconds after a new update, the shell may disappear one time.</span></span> <span data-ttu-id="7644d-263">Proveďte gesto **bloomu** a obnovte relaci.</span><span class="sxs-lookup"><span data-stu-id="7644d-263">Please perform the **bloom** gesture to resume your session.</span></span>

### <a name="visual-studio"></a><span data-ttu-id="7644d-264">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7644d-264">Visual Studio</span></span>

- <span data-ttu-id="7644d-265">V [článku Instalace nástrojů](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) najdete nejnovější verzi Visual Studio která se doporučuje pro vývoj pro HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7644d-265">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Visual Studio that is recommended for HoloLens development.</span></span>

- <span data-ttu-id="7644d-266">Při nasazování aplikace z Visual Studio do HoloLens se může zobrazit chyba: Požadovanou operaci nelze provést u souboru s otevřeným oddílem **mapovaným uživatelem. (Výjimka na hodnoty HRESULT: 0x800704C8)**.</span><span class="sxs-lookup"><span data-stu-id="7644d-266">When deploying an app from Visual Studio to your HoloLens, you may see the error: **The requested operation cannot be performed on a file with a user-mapped section open. (Exception from HRESULT: 0x800704C8)**.</span></span> <span data-ttu-id="7644d-267">Pokud k tomu dojde, zkuste to znovu a vaše nasazení bude obecně úspěšné.</span><span class="sxs-lookup"><span data-stu-id="7644d-267">If this happens, try again and your deployment will generally succeed.</span></span>

### <a name="api"></a><span data-ttu-id="7644d-268">rozhraní API</span><span class="sxs-lookup"><span data-stu-id="7644d-268">API</span></span>

- <span data-ttu-id="7644d-269">Pokud aplikace nastaví zaměřovací [bod](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) za uživatelem nebo normální hodnotu na fotoaparát.forward, hologramy se nezobrazí na Záznam hybridní reality fotografiích nebo videích.</span><span class="sxs-lookup"><span data-stu-id="7644d-269">If the application sets the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) behind the user or the normal to camera.forward, holograms will not appear in Mixed Reality Capture photos or videos.</span></span> <span data-ttu-id="7644d-270">Dokud se tato chyba ve Windows nevyřešila, pokud aplikace aktivně nastavují fokus, měly by zajistit, aby byla normální rovina nastavená opačně (například normální = -camera.forward). [](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity)</span><span class="sxs-lookup"><span data-stu-id="7644d-270">Until this bug is fixed in Windows, if applications actively set the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) they should ensure the plane normal is set opposite camera-forward (for example, normal = -camera.forward).</span></span>

### <a name="xbox-wireless-controller"></a><span data-ttu-id="7644d-271">Bezdrátový ovladač pro Xbox</span><span class="sxs-lookup"><span data-stu-id="7644d-271">Xbox Wireless Controller</span></span>

- <span data-ttu-id="7644d-272">Před použitím bezdrátového ovladače Xbox S s HoloLens je nutné ho aktualizovat.</span><span class="sxs-lookup"><span data-stu-id="7644d-272">Xbox Wireless Controller S must be updated before it can be used with HoloLens.</span></span> <span data-ttu-id="7644d-273">Před [pokusem o spárování](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) kontroleru s HoloLens se ujistěte, že jste aktuální.</span><span class="sxs-lookup"><span data-stu-id="7644d-273">Ensure you are [up to date](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) before attempting to pair your controller with a HoloLens.</span></span>

- <span data-ttu-id="7644d-274">Pokud zařízení HoloLens restartujete, když je bezdrátový ovladač pro Xbox připojený, kontroler se automaticky znovu nepřipojí k HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7644d-274">If you reboot your HoloLens while the Xbox Wireless Controller is connected, the controller will not automatically reconnect to HoloLens.</span></span> <span data-ttu-id="7644d-275">Světlo tlačítka Průvodce bude pomalu blikat, dokud se kontroler po 3 minutách nesmaří.</span><span class="sxs-lookup"><span data-stu-id="7644d-275">The Guide button light will flash slowly until the controller powers off after 3 minutes.</span></span> <span data-ttu-id="7644d-276">Pokud chcete kontroler okamžitě znovu připojit, vypněte ho tak, že podržíte tlačítko Guide (Průvodce), dokud se světlo nevypíná.</span><span class="sxs-lookup"><span data-stu-id="7644d-276">To reconnect your controller immediately, power off the controller by holding the Guide button until the light turns off.</span></span> <span data-ttu-id="7644d-277">Po opětovném zapnutí kontroleru se kontroler znovu připojí k HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7644d-277">When you power your controller on again, it will reconnect to HoloLens.</span></span>

- <span data-ttu-id="7644d-278">Pokud holoLens vstoupí do pohotovostního režimu, zatímco je bezdrátový ovladač pro Xbox připojený, všechny vstupy na kontroleru probudí HoloLens.</span><span class="sxs-lookup"><span data-stu-id="7644d-278">If your HoloLens enters standby while the Xbox Wireless Controller is connected, any input on the controller will wake the HoloLens.</span></span> <span data-ttu-id="7644d-279">Tomu můžete zabránit vypnutím kontroleru, jakmile ho budete používat.</span><span class="sxs-lookup"><span data-stu-id="7644d-279">You can prevent this by powering off your controller when you are done using it.</span></span>

## <a name="known-issues-for-hololens-emulator"></a><span data-ttu-id="7644d-280">Známé problémy s emulátorem HoloLens</span><span class="sxs-lookup"><span data-stu-id="7644d-280">Known issues for HoloLens emulator</span></span>

- <span data-ttu-id="7644d-281">Ne všechny aplikace v Microsoft Store jsou kompatibilní s emulátorem.</span><span class="sxs-lookup"><span data-stu-id="7644d-281">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="7644d-282">Například Young Conker a Fragments se v emulátoru nehrají.</span><span class="sxs-lookup"><span data-stu-id="7644d-282">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="7644d-283">V emulátoru nemůžete použít webovou kameru počítače.</span><span class="sxs-lookup"><span data-stu-id="7644d-283">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="7644d-284">Funkce Live Preview v Portál zařízení s Windows nefunguje s emulátorem.</span><span class="sxs-lookup"><span data-stu-id="7644d-284">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="7644d-285">Stále můžete zachytit Mixed Reality videa a obrázky.</span><span class="sxs-lookup"><span data-stu-id="7644d-285">You can still capture Mixed Reality videos and images.</span></span>
