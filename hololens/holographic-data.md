---
title: Vyhledání a uložení souborů na HoloLens
description: Naučte se používat Průzkumník souborů na HoloLens k otevření, zobrazení a správě souborů na zařízení hybridní reality.
keywords: postupy, výběr souborů, soubory, fotky, videa, obrázky, OneDrive, úložiště, Průzkumník souborů, hololens
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
ms.openlocfilehash: 2d979b2cffd20589ddef7f11db5c7206eaea23cb
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377552"
---
# <a name="find-open-and-save-files-on-hololens"></a><span data-ttu-id="cb655-104">Vyhledání, otevření a uložení souborů v HoloLens</span><span class="sxs-lookup"><span data-stu-id="cb655-104">Find, open, and save files on HoloLens</span></span>

<span data-ttu-id="cb655-105">Soubory, které vytvoříte na HoloLens, včetně fotek a videí, se ukládají přímo do zařízení HoloLens.</span><span class="sxs-lookup"><span data-stu-id="cb655-105">Files you create on HoloLens, including photos and videos, are saved directly to your HoloLens device.</span></span> <span data-ttu-id="cb655-106">Můžete je zobrazit a spravovat stejným způsobem jako soubory v Windows 10:</span><span class="sxs-lookup"><span data-stu-id="cb655-106">View and manage them in the same way you would manage files on Windows 10:</span></span>

- <span data-ttu-id="cb655-107">Použití Průzkumník souborů pro přístup k místním složkám.</span><span class="sxs-lookup"><span data-stu-id="cb655-107">Using the File Explorer app to access local folders.</span></span>
- <span data-ttu-id="cb655-108">V úložišti aplikace.</span><span class="sxs-lookup"><span data-stu-id="cb655-108">Within an app's storage.</span></span>
- <span data-ttu-id="cb655-109">Ve speciální složce (například v knihovně videí nebo hudby).</span><span class="sxs-lookup"><span data-stu-id="cb655-109">In a special folder (such as the video or music library).</span></span>
- <span data-ttu-id="cb655-110">Použití služby úložiště, která zahrnuje výběr aplikací a souborů (například OneDrive)</span><span class="sxs-lookup"><span data-stu-id="cb655-110">Using a storage service that includes an app and file picker (such as OneDrive).</span></span>
- <span data-ttu-id="cb655-111">Použití stolního počítače připojeného k HoloLens pomocí kabelu USB s podporou protokolu MTP (Media Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="cb655-111">Using a desktop PC connected to your HoloLens by using a USB cable, using MTP (Media Transfer Protocol) support.</span></span>

## <a name="view-files-on-hololens-using-file-explorer"></a><span data-ttu-id="cb655-112">Zobrazení souborů na HoloLens pomocí Průzkumník souborů</span><span class="sxs-lookup"><span data-stu-id="cb655-112">View files on HoloLens using File Explorer</span></span>

> <span data-ttu-id="cb655-113">Platí pro všechna zařízení HoloLens 2 a HoloLens (1. generace) od [Aktualizace Windows 10 z dubna 2018 (RS4) pro HoloLens.](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)</span><span class="sxs-lookup"><span data-stu-id="cb655-113">Applies to all HoloLens 2 devices and HoloLens (1st gen) as of the [Windows 10 April 2018 Update (RS4) for HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).</span></span>

<span data-ttu-id="cb655-114">Pomocí Průzkumník souborů na HoloLens můžete zobrazit a spravovat soubory na zařízení, včetně 3D objektů, dokumentů a obrázků.</span><span class="sxs-lookup"><span data-stu-id="cb655-114">Use File Explorer on HoloLens to view and manage files on your device, including 3D objects, documents, and pictures.</span></span> <span data-ttu-id="cb655-115">Začněte    >  **tím, že Všechny aplikace**   >  **Průzkumník souborů** startu.</span><span class="sxs-lookup"><span data-stu-id="cb655-115">Go to **Start**  > **All apps**  > **File Explorer** to get started.</span></span>

> [!TIP]
> <span data-ttu-id="cb655-116">Pokud v seznamu nejsou žádné soubory Průzkumník souborů, vyberte **Toto zařízení** v levém horním podokně.</span><span class="sxs-lookup"><span data-stu-id="cb655-116">If there are no files listed in File Explorer, select **This Device** in the top left pane.</span></span>

<span data-ttu-id="cb655-117">Pokud v seznamu nevidíte žádné soubory, Průzkumník souborů filtr Poslední (v levém podokně je zvýrazněná ikona hodin).</span><span class="sxs-lookup"><span data-stu-id="cb655-117">If you don’t see any files in File Explorer, the "Recent" filter may be active (clock icon is highlighted in left pane).</span></span> <span data-ttu-id="cb655-118">Pokud chcete tento  problém vyřešit, vyberte ikonu Dokument zařízení v levém podokně (pod ikonou hodin) nebo otevřete nabídku a vyberte **This Device (Toto zařízení).**</span><span class="sxs-lookup"><span data-stu-id="cb655-118">To fix this, select the **This Device** document icon in the left pane (beneath the clock icon), or open the menu and select **This Device**.</span></span>

## <a name="find-and-view-your-photos-and-videos"></a><span data-ttu-id="cb655-119">Vyhledání a zobrazení fotek a videí</span><span class="sxs-lookup"><span data-stu-id="cb655-119">Find and view your photos and videos</span></span>

<span data-ttu-id="cb655-120">[Zachycení hybridní reality](holographic-photos-and-videos.md) umožňuje pořizovat fotky a videa hybridní reality na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="cb655-120">[Mixed reality capture](holographic-photos-and-videos.md) lets you take mixed reality photos and videos on HoloLens.</span></span>  <span data-ttu-id="cb655-121">Tyto fotky a videa se ukládají do složky Fotoaparát s fotoaparátem v zařízení.</span><span class="sxs-lookup"><span data-stu-id="cb655-121">These photos and videos are saved to the device's Camera Roll folder.</span></span>

<span data-ttu-id="cb655-122">K fotografiím a videím pořízených pomocí HoloLens můžete přistupovat tímto způsobem:</span><span class="sxs-lookup"><span data-stu-id="cb655-122">You can access photos and videos taken with HoloLens by:</span></span>

- <span data-ttu-id="cb655-123">přistupovat k fotoaparátu přímo prostřednictvím [aplikace Photos.](holographic-photos-and-videos.md)</span><span class="sxs-lookup"><span data-stu-id="cb655-123">accessing the Camera Roll directly through the [Photos app](holographic-photos-and-videos.md).</span></span>
- <span data-ttu-id="cb655-124">nahrání fotek a videí do cloudového úložiště synchronizací fotek a videí do OneDrivu</span><span class="sxs-lookup"><span data-stu-id="cb655-124">uploading photos and videos to cloud storage by syncing your photos and videos to OneDrive.</span></span>
- <span data-ttu-id="cb655-125">pomocí Záznam hybridní reality stránky [Portál zařízení s Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span><span class="sxs-lookup"><span data-stu-id="cb655-125">using the Mixed Reality Capture page of the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span></span>

### <a name="photos-app"></a><span data-ttu-id="cb655-126">Aplikace Photos</span><span class="sxs-lookup"><span data-stu-id="cb655-126">Photos app</span></span>

<span data-ttu-id="cb655-127">Aplikace Photos je jednou z výchozích aplikací v **nabídce Start** a je integrovaná s HoloLens.</span><span class="sxs-lookup"><span data-stu-id="cb655-127">The Photos app is one of the default apps on the **Start** menu, and comes built-in with HoloLens.</span></span> <span data-ttu-id="cb655-128">Přečtěte si další [informace o použití aplikace Photos k zobrazení obsahu.](holographic-photos-and-videos.md)</span><span class="sxs-lookup"><span data-stu-id="cb655-128">Learn more about [using the Photos app to view content](holographic-photos-and-videos.md).</span></span>

<span data-ttu-id="cb655-129">Aplikaci [OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) můžete také nainstalovat z webu Microsoft Store synchronizovat fotky s jinými zařízeními.</span><span class="sxs-lookup"><span data-stu-id="cb655-129">You can also install the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store to sync photos to other devices.</span></span>

### <a name="onedrive-app"></a><span data-ttu-id="cb655-130">Aplikace OneDrive</span><span class="sxs-lookup"><span data-stu-id="cb655-130">OneDrive app</span></span>

<span data-ttu-id="cb655-131">[OneDrive](https://onedrive.live.com/) umožňuje přístup k fotografiím a videím, jejich správu a sdílení s libovolným zařízením a s libovolným uživatelem.</span><span class="sxs-lookup"><span data-stu-id="cb655-131">[OneDrive](https://onedrive.live.com/) lets you access, manage, and share your photos and videos with any device and with any user.</span></span> <span data-ttu-id="cb655-132">Pokud chcete získat přístup k fotografiím a videím zachycených na HoloLens, stáhněte si [aplikaci OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) z Microsoft Store na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="cb655-132">To access the photos and videos captured on HoloLens, download the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store on your HoloLens.</span></span> <span data-ttu-id="cb655-133">Po stažení otevřete aplikaci OneDrive, vyberte Nastavení  >  **Nahrání fotoaparátu** a zapněte **Nahrání fotoaparátu.**</span><span class="sxs-lookup"><span data-stu-id="cb655-133">Once downloaded, open the OneDrive app and select **Settings** > **Camera upload**, and turn on **Camera upload**.</span></span>

### <a name="connect-to-a-pc"></a><span data-ttu-id="cb655-134">Připojení k počítači</span><span class="sxs-lookup"><span data-stu-id="cb655-134">Connect to a PC</span></span>

<span data-ttu-id="cb655-135">Pokud holoLens používá aktualizaci [Windows 10 april 2018](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) nebo novější, můžete holoLens připojit k počítači Windows 10 pomocí kabelu USB a procházet fotky a videa na zařízení pomocí protokolu MTP (media transfer protocol).</span><span class="sxs-lookup"><span data-stu-id="cb655-135">If your HoloLens is running the [Windows 10 April 2018 update](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) or later, you can connect your HoloLens to a Windows 10 PC by using a USB cable to browse photos and videos on the device by using MTP (media transfer protocol).</span></span> <span data-ttu-id="cb655-136">Pokud máte na zařízení nastavený PIN kód nebo heslo, musíte zajistit odemknutí zařízení, aby bylo možné procházet soubory.</span><span class="sxs-lookup"><span data-stu-id="cb655-136">You'll need to make sure the device is unlocked to browse files if you have a PIN or password set up on your device.</span></span>  

<span data-ttu-id="cb655-137">Pokud jste povolili [Portál zařízení s Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), můžete ho použít k procházení, načítání a správě fotek a videí uložených v zařízení.</span><span class="sxs-lookup"><span data-stu-id="cb655-137">If you have enabled the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), you can use it to browse, retrieve, and manage the photos and videos stored on your device.</span></span>

## <a name="access-files-within-an-app"></a><span data-ttu-id="cb655-138">Přístup k souborům v rámci aplikace</span><span class="sxs-lookup"><span data-stu-id="cb655-138">Access files within an app</span></span>

<span data-ttu-id="cb655-139">Pokud aplikace ukládá soubory do zařízení, můžete k nim přistupovat pomocí této aplikace.</span><span class="sxs-lookup"><span data-stu-id="cb655-139">If an application saves files on your device, you can use that application to access them.</span></span>

### <a name="requesting-files-from-another-app"></a><span data-ttu-id="cb655-140">Vyžádání souborů z jiné aplikace</span><span class="sxs-lookup"><span data-stu-id="cb655-140">Requesting files from another app</span></span>

<span data-ttu-id="cb655-141">Aplikace může požádat o uložení souboru nebo otevření souboru z jiné aplikace pomocí [výběrů souborů](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).</span><span class="sxs-lookup"><span data-stu-id="cb655-141">An application can request to save a file or open a file from another app by using [file pickers](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).</span></span>

### <a name="known-folders"></a><span data-ttu-id="cb655-142">Známé složky</span><span class="sxs-lookup"><span data-stu-id="cb655-142">Known folders</span></span>

<span data-ttu-id="cb655-143">HoloLens podporuje řadu známých [složek,](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) ke které mohou aplikace požádat o oprávnění pro přístup.</span><span class="sxs-lookup"><span data-stu-id="cb655-143">HoloLens supports a number of [known folders](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) that apps can request permission to access.</span></span>

## <a name="view-hololens-files-on-your-pc"></a><span data-ttu-id="cb655-144">Zobrazení souborů HoloLens na počítači</span><span class="sxs-lookup"><span data-stu-id="cb655-144">View HoloLens files on your PC</span></span>

<span data-ttu-id="cb655-145">Podobně jako u jiných mobilních zařízení připojte HoloLens ke svému stolnímu počítači pomocí protokolu MTP (Media Transfer Protocol) a otevřete na počítači Průzkumník souborů pro přístup k knihovnám HoloLens pro snadný přenos.</span><span class="sxs-lookup"><span data-stu-id="cb655-145">Similar to other mobile devices, connect HoloLens to your desktop PC using MTP (Media Transfer Protocol) and open File Explorer on the PC to access your HoloLens libraries for easy transfer.</span></span>

<span data-ttu-id="cb655-146">Zobrazení souborů HoloLens v Průzkumník souborů počítači:</span><span class="sxs-lookup"><span data-stu-id="cb655-146">To see your HoloLens files in File Explorer on your PC:</span></span>

1. <span data-ttu-id="cb655-147">Přihlaste se k HoloLens a pak ho připojte k počítači pomocí kabelu USB, který se dodá s HoloLens.</span><span class="sxs-lookup"><span data-stu-id="cb655-147">Sign in to HoloLens, then plug it into the PC using the USB cable that came with the HoloLens.</span></span>

1. <span data-ttu-id="cb655-148">Vyberte **Otevřít zařízení a zobrazte soubory s Průzkumník souborů**, nebo otevřete Průzkumník souborů na počítači a přejděte na zařízení.</span><span class="sxs-lookup"><span data-stu-id="cb655-148">Select **Open Device to view files with File Explorer**, or open File Explorer on the PC and navigate to the device.</span></span>

<span data-ttu-id="cb655-149">Pokud chcete zobrazit informace o holoLensu, klikněte pravým tlačítkem na název zařízení v Průzkumník souborů počítači a pak vyberte **Vlastnosti**.</span><span class="sxs-lookup"><span data-stu-id="cb655-149">To see info about your HoloLens, right-click the device name in File Explorer on your PC, then select **Properties**.</span></span>

> [!NOTE]
> <span data-ttu-id="cb655-150">HoloLens (1. generace) nepodporuje připojení k externím pevným diskům nebo kartám SD.</span><span class="sxs-lookup"><span data-stu-id="cb655-150">HoloLens (1st gen) does not support connecting to external hard drives or SD cards.</span></span>

## <a name="sync-to-the-cloud"></a><span data-ttu-id="cb655-151">Synchronizace do cloudu</span><span class="sxs-lookup"><span data-stu-id="cb655-151">Sync to the cloud</span></span>

<span data-ttu-id="cb655-152">Pokud chcete synchronizovat fotky a další soubory z HoloLens do cloudu, nainstalujte a nastavte OneDrive na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="cb655-152">To sync photos and other files from your HoloLens to the cloud, install and set up OneDrive on HoloLens.</span></span> <span data-ttu-id="cb655-153">OneDrive získáte tak, že ho vyhledáte v Microsoft Store holoLens.</span><span class="sxs-lookup"><span data-stu-id="cb655-153">To get OneDrive, search for it in the Microsoft Store on your HoloLens.</span></span>

<span data-ttu-id="cb655-154">HoloLens nezá zálohuje soubory a data aplikace, takže je vhodné ukládat důležité věci na OneDrive.</span><span class="sxs-lookup"><span data-stu-id="cb655-154">HoloLens doesn't back up app files and data, so it's a good idea to save your important stuff to OneDrive.</span></span> <span data-ttu-id="cb655-155">Pokud tak resetujete zařízení nebo odinstalujete aplikaci, vaše informace se zálohují.</span><span class="sxs-lookup"><span data-stu-id="cb655-155">That way, if you reset your device or uninstall an app, your info will be backed up.</span></span>
