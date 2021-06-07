---
title: Nainstalovat lokalizované verze HoloLens
description: Naučte se instalovat lokalizované verze HoloLens (1. generace), včetně čínských a japonských verzí.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 74eb003aafd23218b90988abe113d35f1fc3035a
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377749"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a><span data-ttu-id="f4c6c-103">Nainstalovat lokalizované verze HoloLens (1. generace)</span><span class="sxs-lookup"><span data-stu-id="f4c6c-103">Install localized versions of HoloLens (1st gen)</span></span>

<span data-ttu-id="f4c6c-104">Aby bylo možné přepnout na čínskou nebo japonskou verzi HoloLens, budete muset použít nástroj pro obnovení zařízení (WDRT) pro Windows ke stažení sestavení pro jazyk na počítači a pak ho nainstalovat na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f4c6c-104">In order to switch to the Chinese or Japanese version of HoloLens, you’ll need to use the Windows Device Recovery Tool (WDRT) to download the build for the language on a PC and then install it on your HoloLens.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f4c6c-105">Použití WDRT k instalaci čínských nebo japonských buildů HoloLens odstraní existující data, jako jsou osobní soubory a nastavení, z HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f4c6c-105">Using WDRT to install the Chinese or Japanese builds of HoloLens deletes existing data, such as personal files and settings, from your HoloLens.</span></span> 

1. <span data-ttu-id="f4c6c-106">Na počítači stáhněte a nainstalujte [Nástroj Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span><span class="sxs-lookup"><span data-stu-id="f4c6c-106">On your PC, download and install [the Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="f4c6c-107">Stáhněte si balíček pro jazyk, který chcete do počítače:  [zjednodušená čínština](https://aka.ms/hololensdownload-ch) nebo [japonština](https://aka.ms/hololensdownload-jp).</span><span class="sxs-lookup"><span data-stu-id="f4c6c-107">Download the package for the language you want to your PC:  [Simplified Chinese](https://aka.ms/hololensdownload-ch) or [Japanese](https://aka.ms/hololensdownload-jp).</span></span>
1. <span data-ttu-id="f4c6c-108">Po dokončení stahování vyberte **Průzkumník souborů**  >  **soubory ke stažení**.</span><span class="sxs-lookup"><span data-stu-id="f4c6c-108">When the download finishes, select **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="f4c6c-109">Klikněte pravým tlačítkem na složku zip, kterou jste právě stáhli, a vyberte **extrahovat všechny**  >  **extrakce** , které chcete rozbalit.</span><span class="sxs-lookup"><span data-stu-id="f4c6c-109">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="f4c6c-110">Připojte HoloLens k počítači pomocí kabelu mikrosběrnice USB, který dodal.</span><span class="sxs-lookup"><span data-stu-id="f4c6c-110">Connect your HoloLens to your PC using the micro-USB cable that it shipped with.</span></span> <span data-ttu-id="f4c6c-111">(I v případě, že jste k připojení HoloLens používali jiné kabely, tato funkce funguje nejlépe.)</span><span class="sxs-lookup"><span data-stu-id="f4c6c-111">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="f4c6c-112">Jakmile nástroj automaticky rozpozná HoloLens, vyberte dlaždici Microsoft HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f4c6c-112">After the tool automatically detects your HoloLens, select the Microsoft HoloLens tile.</span></span>
1. <span data-ttu-id="f4c6c-113">Na další obrazovce vyberte možnost **Manuální výběr balíčku**   a vyberte instalační soubor, který se nachází ve složce, kterou jste rozbalíte v kroku 4.</span><span class="sxs-lookup"><span data-stu-id="f4c6c-113">On the next screen, select **Manual package selection** and select the installation file that resides in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="f4c6c-114">(Vyhledejte soubor s příponou ". FFU".)</span><span class="sxs-lookup"><span data-stu-id="f4c6c-114">(Look for a file that has the extension “.ffu”.)</span></span> 
1. <span data-ttu-id="f4c6c-115">Vyberte **instalovat software** a postupujte podle pokynů.</span><span class="sxs-lookup"><span data-stu-id="f4c6c-115">Select **Install software** and follow the instructions.</span></span> 
1. <span data-ttu-id="f4c6c-116">Po instalaci sestavení se automaticky spustí instalační program HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f4c6c-116">After the build installs, HoloLens setup automatically starts.</span></span> <span data-ttu-id="f4c6c-117">Umístěte zařízení a postupujte podle pokynů k instalaci.</span><span class="sxs-lookup"><span data-stu-id="f4c6c-117">Put on the device and follow the setup directions.</span></span> 

<span data-ttu-id="f4c6c-118">Až budete s instalací hotovi, v části **Nastavení**  >  **aktualizovat & zabezpečení**  >  **programu Windows Insider** a ověřte, že jste nakonfigurovali, abyste získali nejnovější buildy Preview.</span><span class="sxs-lookup"><span data-stu-id="f4c6c-118">When you’re done with setup, go to **Settings** > **Update & Security** > **Windows Insider Program**, and check that you’re configured to receive the latest preview builds.</span></span> <span data-ttu-id="f4c6c-119">Stejně jako anglické verze Preview sestaví program Windows Insider čínské a japonské verze HoloLens s nejnovějšími buildy Preview.</span><span class="sxs-lookup"><span data-stu-id="f4c6c-119">Like the English preview builds, the Windows Insider Program keeps the Chinese and Japanese versions of HoloLens up-to-date with the latest preview builds.</span></span>

> [!NOTE]
>  
> - <span data-ttu-id="f4c6c-120">Aplikaci nastavení nemůžete použít ke změně systémového jazyka mezi angličtinu, japonštinou a čínštinou.</span><span class="sxs-lookup"><span data-stu-id="f4c6c-120">You can’t use the Settings app to change the system language between English, Japanese, and Chinese.</span></span> <span data-ttu-id="f4c6c-121">Jediným podporovaným způsobem, jak změnit jazyk systému zařízení, je blikání nového sestavení.</span><span class="sxs-lookup"><span data-stu-id="f4c6c-121">Flashing a new build is the only supported way to change the device system language.</span></span>
> - <span data-ttu-id="f4c6c-122">I když můžete použít klávesnici s pchin-jin na obrazovce k zadání zjednodušeného čínského nebo japonského textu, není v tuto chvíli podporována použití hardwarové klávesnice Bluetooth k zadání zjednodušeného čínského nebo japonského textu.</span><span class="sxs-lookup"><span data-stu-id="f4c6c-122">While you can use the on-screen Pinyin keyboard to enter Simplified Chinese or Japanese text, using a Bluetooth hardware keyboard to type Simplified Chinese or Japanese text is not supported at this time.</span></span>  <span data-ttu-id="f4c6c-123">V čínštině nebo v japonštině HoloLens můžete ale i nadále používat klávesnici Bluetooth k psaní angličtiny (Pokud chcete přepnout hardwarovou klávesnici na typ v angličtině, stiskněte klávesu ~).</span><span class="sxs-lookup"><span data-stu-id="f4c6c-123">However, on Chinese or Japanese HoloLens, you can continue to use a Bluetooth keyboard to type in English (to toggle a hardware keyboard to type in English, press the ~ key).</span></span>
