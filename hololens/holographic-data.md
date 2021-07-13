---
title: Hledání a ukládání souborů na HoloLens
description: naučte se používat průzkumníka souborů v HoloLens k otevření, zobrazení a správě souborů na zařízení se smíšenými realitami.
keywords: postupy, výběr souborů, soubory, fotky, videa, obrázky, OneDrive, úložiště, průzkumník souborů, hololens
ms.assetid: 77d2e357-f65f-43c8-b62f-6cd9bf37070a
author: mattzmsft
ms.author: mazeller
manager: v-miegge
ms.reviewer: jarrettrenshaw
ms.date: 12/30/2019
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 18dc962b869dafaea9ff9c605eef51fcbb35bfb2
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636176"
---
# <a name="find-open-and-save-files-on-hololens"></a><span data-ttu-id="55620-104">Hledání, otevírání a ukládání souborů na HoloLens</span><span class="sxs-lookup"><span data-stu-id="55620-104">Find, open, and save files on HoloLens</span></span>

<span data-ttu-id="55620-105">soubory, které vytvoříte v HoloLens, včetně fotek a videí, se ukládají přímo do vašeho zařízení HoloLens.</span><span class="sxs-lookup"><span data-stu-id="55620-105">Files you create on HoloLens, including photos and videos, are saved directly to your HoloLens device.</span></span> <span data-ttu-id="55620-106">Můžete je zobrazit a spravovat stejným způsobem, jakým byste mohli spravovat soubory na Windows 10:</span><span class="sxs-lookup"><span data-stu-id="55620-106">View and manage them in the same way you would manage files on Windows 10:</span></span>

- <span data-ttu-id="55620-107">Přístup k místním složkám pomocí aplikace Průzkumník souborů</span><span class="sxs-lookup"><span data-stu-id="55620-107">Using the File Explorer app to access local folders.</span></span>
- <span data-ttu-id="55620-108">V rámci úložiště aplikace.</span><span class="sxs-lookup"><span data-stu-id="55620-108">Within an app's storage.</span></span>
- <span data-ttu-id="55620-109">Ve speciální složce (například v knihovně video nebo hudba).</span><span class="sxs-lookup"><span data-stu-id="55620-109">In a special folder (such as the video or music library).</span></span>
- <span data-ttu-id="55620-110">Používání služby úložiště, která zahrnuje výběr aplikace a souboru (například OneDrive).</span><span class="sxs-lookup"><span data-stu-id="55620-110">Using a storage service that includes an app and file picker (such as OneDrive).</span></span>
- <span data-ttu-id="55620-111">použití stolního počítače připojeného k vašemu HoloLens pomocí kabelu USB pomocí podpory MTP (Media Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="55620-111">Using a desktop PC connected to your HoloLens by using a USB cable, using MTP (Media Transfer Protocol) support.</span></span>

## <a name="view-files-on-hololens-using-file-explorer"></a><span data-ttu-id="55620-112">zobrazení souborů v HoloLens pomocí průzkumníka souborů</span><span class="sxs-lookup"><span data-stu-id="55620-112">View files on HoloLens using File Explorer</span></span>

> <span data-ttu-id="55620-113">platí pro všechna zařízení HoloLens 2 a HoloLens (1. generace) Windows 10 od [dubna 2018 Update (RS4) pro HoloLens](/windows/mixed-reality/release-notes-april-2018).</span><span class="sxs-lookup"><span data-stu-id="55620-113">Applies to all HoloLens 2 devices and HoloLens (1st gen) as of the [Windows 10 April 2018 Update (RS4) for HoloLens](/windows/mixed-reality/release-notes-april-2018).</span></span>

<span data-ttu-id="55620-114">pomocí průzkumníka souborů v HoloLens můžete zobrazit a spravovat soubory v zařízení, včetně 3d objektů, dokumentů a obrázků.</span><span class="sxs-lookup"><span data-stu-id="55620-114">Use File Explorer on HoloLens to view and manage files on your device, including 3D objects, documents, and pictures.</span></span> <span data-ttu-id="55620-115">Začněte tím, že přejdete na **Start**   >  **All apps**   >  **Průzkumník souborů** .</span><span class="sxs-lookup"><span data-stu-id="55620-115">Go to **Start**  > **All apps**  > **File Explorer** to get started.</span></span>

> [!TIP]
> <span data-ttu-id="55620-116">Pokud v Průzkumníkovi souborů nejsou uvedené žádné soubory, vyberte v levém horním podokně **Toto zařízení** .</span><span class="sxs-lookup"><span data-stu-id="55620-116">If there are no files listed in File Explorer, select **This Device** in the top left pane.</span></span>

<span data-ttu-id="55620-117">Pokud v Průzkumníkovi souborů nevidíte žádné soubory, může být filtr "poslední" aktivní (v levém podokně je zvýrazněna ikona hodiny).</span><span class="sxs-lookup"><span data-stu-id="55620-117">If you don’t see any files in File Explorer, the "Recent" filter may be active (clock icon is highlighted in left pane).</span></span> <span data-ttu-id="55620-118">Pokud to chcete opravit, vyberte ikonu dokumentu **Tento zařízení** v levém podokně (pod ikonou hodin), nebo otevřete nabídku a vyberte **Toto zařízení**.</span><span class="sxs-lookup"><span data-stu-id="55620-118">To fix this, select the **This Device** document icon in the left pane (beneath the clock icon), or open the menu and select **This Device**.</span></span>

## <a name="find-and-view-your-photos-and-videos"></a><span data-ttu-id="55620-119">Hledání a zobrazování fotek a videí</span><span class="sxs-lookup"><span data-stu-id="55620-119">Find and view your photos and videos</span></span>

<span data-ttu-id="55620-120">[Hybridní zachycení realit](holographic-photos-and-videos.md) umožňuje využívat fotky a videa ze směsi realit na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="55620-120">[Mixed reality capture](holographic-photos-and-videos.md) lets you take mixed reality photos and videos on HoloLens.</span></span>  <span data-ttu-id="55620-121">Tyto fotky a videa se uloží do složky pro fotoaparát zařízení.</span><span class="sxs-lookup"><span data-stu-id="55620-121">These photos and videos are saved to the device's Camera Roll folder.</span></span>

<span data-ttu-id="55620-122">k fotografiím a videím pořízeným pomocí HoloLens můžete získat následující:</span><span class="sxs-lookup"><span data-stu-id="55620-122">You can access photos and videos taken with HoloLens by:</span></span>

- <span data-ttu-id="55620-123">přístup ke kameře přímo přes [aplikaci Photos](holographic-photos-and-videos.md).</span><span class="sxs-lookup"><span data-stu-id="55620-123">accessing the Camera Roll directly through the [Photos app](holographic-photos-and-videos.md).</span></span>
- <span data-ttu-id="55620-124">nahrávají se fotky a videa do cloudového úložiště díky synchronizaci fotek a videí s OneDrive.</span><span class="sxs-lookup"><span data-stu-id="55620-124">uploading photos and videos to cloud storage by syncing your photos and videos to OneDrive.</span></span>
- <span data-ttu-id="55620-125">pomocí stránky zachycení hybridních realit na [portálu zařízení Windows](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span><span class="sxs-lookup"><span data-stu-id="55620-125">using the Mixed Reality Capture page of the [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span></span>

### <a name="photos-app"></a><span data-ttu-id="55620-126">Aplikace Fotky</span><span class="sxs-lookup"><span data-stu-id="55620-126">Photos app</span></span>

<span data-ttu-id="55620-127">Aplikace Photos je jedna z výchozích aplikací v nabídce **Start** a integrovaná s HoloLens.</span><span class="sxs-lookup"><span data-stu-id="55620-127">The Photos app is one of the default apps on the **Start** menu, and comes built-in with HoloLens.</span></span> <span data-ttu-id="55620-128">Přečtěte si další informace o [používání aplikace fotky k zobrazení obsahu](holographic-photos-and-videos.md).</span><span class="sxs-lookup"><span data-stu-id="55620-128">Learn more about [using the Photos app to view content](holographic-photos-and-videos.md).</span></span>

<span data-ttu-id="55620-129">můžete taky nainstalovat [aplikaci OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) z Microsoft Store a synchronizovat fotky s ostatními zařízeními.</span><span class="sxs-lookup"><span data-stu-id="55620-129">You can also install the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store to sync photos to other devices.</span></span>

### <a name="onedrive-app"></a><span data-ttu-id="55620-130">aplikace OneDrive</span><span class="sxs-lookup"><span data-stu-id="55620-130">OneDrive app</span></span>

<span data-ttu-id="55620-131">[OneDrive](https://onedrive.live.com/) vám umožní přístup, správu a sdílení fotek a videí pomocí libovolného zařízení a libovolného uživatele.</span><span class="sxs-lookup"><span data-stu-id="55620-131">[OneDrive](https://onedrive.live.com/) lets you access, manage, and share your photos and videos with any device and with any user.</span></span> <span data-ttu-id="55620-132">pokud chcete získat přístup k fotografiím a videím zachyceným na HoloLens, stáhněte [OneDrive aplikaci](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) z Microsoft Store na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="55620-132">To access the photos and videos captured on HoloLens, download the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store on your HoloLens.</span></span> <span data-ttu-id="55620-133">po stažení otevřete aplikaci OneDrive a vyberte **Nastavení**  >  **nahrávání kamery** a zapněte **nahrávání kamery**.</span><span class="sxs-lookup"><span data-stu-id="55620-133">Once downloaded, open the OneDrive app and select **Settings** > **Camera upload**, and turn on **Camera upload**.</span></span>

### <a name="connect-to-a-pc"></a><span data-ttu-id="55620-134">Připojení k počítači</span><span class="sxs-lookup"><span data-stu-id="55620-134">Connect to a PC</span></span>

<span data-ttu-id="55620-135">pokud na vašem HoloLens běží [Windows 10 aktualizace z dubna 2018](/windows/mixed-reality/release-notes-april-2018) nebo novější, můžete své HoloLens připojit k Windows 10 počítači pomocí kabelu USB a procházet fotky a videa na zařízení pomocí protokolu MTP (media transfer protocol).</span><span class="sxs-lookup"><span data-stu-id="55620-135">If your HoloLens is running the [Windows 10 April 2018 update](/windows/mixed-reality/release-notes-april-2018) or later, you can connect your HoloLens to a Windows 10 PC by using a USB cable to browse photos and videos on the device by using MTP (media transfer protocol).</span></span> <span data-ttu-id="55620-136">Pokud máte na svém zařízení nastavené PIN nebo heslo, budete se muset ujistit, že je zařízení odemčené pro procházení souborů.</span><span class="sxs-lookup"><span data-stu-id="55620-136">You'll need to make sure the device is unlocked to browse files if you have a PIN or password set up on your device.</span></span>  

<span data-ttu-id="55620-137">pokud jste povolili [Windows portál zařízení](/windows/mixed-reality/using-the-windows-device-portal), můžete ho použít k procházení, načítání a správě fotografií a videí uložených v zařízení.</span><span class="sxs-lookup"><span data-stu-id="55620-137">If you have enabled the [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal), you can use it to browse, retrieve, and manage the photos and videos stored on your device.</span></span>

## <a name="access-files-within-an-app"></a><span data-ttu-id="55620-138">Přístup k souborům v rámci aplikace</span><span class="sxs-lookup"><span data-stu-id="55620-138">Access files within an app</span></span>

<span data-ttu-id="55620-139">Pokud aplikace ukládá soubory do zařízení, můžete k nim přistupovat pomocí této aplikace.</span><span class="sxs-lookup"><span data-stu-id="55620-139">If an application saves files on your device, you can use that application to access them.</span></span>

### <a name="requesting-files-from-another-app"></a><span data-ttu-id="55620-140">Vyžádání souborů z jiné aplikace</span><span class="sxs-lookup"><span data-stu-id="55620-140">Requesting files from another app</span></span>

<span data-ttu-id="55620-141">Aplikace může požádat o uložení souboru nebo otevření souboru z jiné aplikace pomocí [výběrů souborů](/windows/mixed-reality/app-model#file-pickers).</span><span class="sxs-lookup"><span data-stu-id="55620-141">An application can request to save a file or open a file from another app by using [file pickers](/windows/mixed-reality/app-model#file-pickers).</span></span>

### <a name="known-folders"></a><span data-ttu-id="55620-142">Známé složky</span><span class="sxs-lookup"><span data-stu-id="55620-142">Known folders</span></span>

<span data-ttu-id="55620-143">HoloLens podporuje několik [známých složek](/windows/mixed-reality/app-model#known-folders) , které můžou aplikace požádat o oprávnění k přístupu.</span><span class="sxs-lookup"><span data-stu-id="55620-143">HoloLens supports a number of [known folders](/windows/mixed-reality/app-model#known-folders) that apps can request permission to access.</span></span>

## <a name="view-hololens-files-on-your-pc"></a><span data-ttu-id="55620-144">zobrazit HoloLens soubory na počítači</span><span class="sxs-lookup"><span data-stu-id="55620-144">View HoloLens files on your PC</span></span>

<span data-ttu-id="55620-145">podobně jako u jiných mobilních zařízení připojte HoloLens k stolnímu počítači pomocí MTP (Media Transfer Protocol) a otevřete průzkumníka souborů na počítači, abyste měli přístup k vašim HoloLensm knihovnám za účelem snadného přenosu.</span><span class="sxs-lookup"><span data-stu-id="55620-145">Similar to other mobile devices, connect HoloLens to your desktop PC using MTP (Media Transfer Protocol) and open File Explorer on the PC to access your HoloLens libraries for easy transfer.</span></span>

<span data-ttu-id="55620-146">chcete-li zobrazit soubory HoloLens v průzkumníkovi souborů na vašem počítači:</span><span class="sxs-lookup"><span data-stu-id="55620-146">To see your HoloLens files in File Explorer on your PC:</span></span>

1. <span data-ttu-id="55620-147">přihlaste se k HoloLens a pak ho připojte k počítači pomocí kabelu USB, který jste dostali s HoloLens.</span><span class="sxs-lookup"><span data-stu-id="55620-147">Sign in to HoloLens, then plug it into the PC using the USB cable that came with the HoloLens.</span></span>

1. <span data-ttu-id="55620-148">Vyberte **otevřít zařízení a zobrazte si soubory pomocí Průzkumníka souborů** nebo otevřete Průzkumníka souborů na počítači a přejděte k zařízení.</span><span class="sxs-lookup"><span data-stu-id="55620-148">Select **Open Device to view files with File Explorer**, or open File Explorer on the PC and navigate to the device.</span></span>

<span data-ttu-id="55620-149">pokud chcete zobrazit informace o vašem HoloLens, klikněte pravým tlačítkem myši na název zařízení v průzkumníkovi souborů na počítači a pak vyberte **vlastnosti**.</span><span class="sxs-lookup"><span data-stu-id="55620-149">To see info about your HoloLens, right-click the device name in File Explorer on your PC, then select **Properties**.</span></span>

> [!NOTE]
> <span data-ttu-id="55620-150">HoloLens (1. generace) nepodporuje připojení k externím pevným diskům nebo SD kartám.</span><span class="sxs-lookup"><span data-stu-id="55620-150">HoloLens (1st gen) does not support connecting to external hard drives or SD cards.</span></span>

## <a name="sync-to-the-cloud"></a><span data-ttu-id="55620-151">Synchronizace s cloudem</span><span class="sxs-lookup"><span data-stu-id="55620-151">Sync to the cloud</span></span>

<span data-ttu-id="55620-152">pokud chcete synchronizovat fotky a jiné soubory z HoloLens do cloudu, nainstalujte a nastavte OneDrive na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="55620-152">To sync photos and other files from your HoloLens to the cloud, install and set up OneDrive on HoloLens.</span></span> <span data-ttu-id="55620-153">pokud chcete OneDrive získat, vyhledejte ho v Microsoft Store na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="55620-153">To get OneDrive, search for it in the Microsoft Store on your HoloLens.</span></span>

<span data-ttu-id="55620-154">HoloLens nezálohují soubory a data aplikací, takže je vhodné, abyste si ušetřili důležité věci, které byste měli OneDrive.</span><span class="sxs-lookup"><span data-stu-id="55620-154">HoloLens doesn't back up app files and data, so it's a good idea to save your important stuff to OneDrive.</span></span> <span data-ttu-id="55620-155">Tímto způsobem, pokud resetujete zařízení nebo odinstalujete aplikaci, vaše informace se zálohují.</span><span class="sxs-lookup"><span data-stu-id="55620-155">That way, if you reset your device or uninstall an app, your info will be backed up.</span></span>
