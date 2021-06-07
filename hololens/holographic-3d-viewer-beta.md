---
title: Použití 3D prohlížeč Beta na HoloLens (1. generace)
description: Popisuje typy souborů a funkcí, které 3D prohlížeč Beta na HoloLens (1. generace) podporuje, a jak používat a řešit potíže s aplikací.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 10/30/2019
ms.reviewer: scooley
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: f5481d6466459667deb99232fdd67c4491798cbe
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379218"
---
# <a name="using-3d-viewer-beta-on-hololens-1st-gen"></a><span data-ttu-id="83ed7-103">Použití 3D prohlížeč Beta na HoloLens (1. generace)</span><span class="sxs-lookup"><span data-stu-id="83ed7-103">Using 3D Viewer Beta on HoloLens (1st gen)</span></span>

<span data-ttu-id="83ed7-104">3D prohlížeč Beta umožňuje zobrazit 3D modely na HoloLens (1. generace).</span><span class="sxs-lookup"><span data-stu-id="83ed7-104">3D Viewer Beta lets you view 3D models on HoloLens (1st gen).</span></span> <span data-ttu-id="83ed7-105">Podporované soubory .fbx *můžete* otevřít a zobrazit Microsoft Edge, OneDrivu a dalších aplikacích.</span><span class="sxs-lookup"><span data-stu-id="83ed7-105">You can open and view *supported* .fbx files from Microsoft Edge, OneDrive, and other apps.</span></span>

>[!NOTE]
><span data-ttu-id="83ed7-106">Tento článek se týká imerzivní aplikace Unity **3D prohlížeč Beta,** která podporuje soubory .fbx a je dostupná jenom na HoloLens (1. generace).</span><span class="sxs-lookup"><span data-stu-id="83ed7-106">This article applies to the immersive Unity **3D Viewer Beta** app, which supports .fbx files and is only available on HoloLens (1st gen).</span></span> <span data-ttu-id="83ed7-107">Předinstalovaná **aplikace** 3D prohlížeč HoloLens 2 podporuje otevírání vlastních 3D modelů .glb na [](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) domovské stránce hybridní reality (další podrobnosti najdete v tématu Přehled požadavků na prostředky.</span><span class="sxs-lookup"><span data-stu-id="83ed7-107">The pre-installed **3D Viewer** app on HoloLens 2 supports opening custom .glb 3D models in the mixed reality home (see [Asset requirements overview](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) for more details.</span></span>

>[!IMPORTANT]
><span data-ttu-id="83ed7-108">Přestože 3D prohlížeč beta verze může zůstat dostupná v Microsoft Store pro HoloLens (1. generace), už není v aktivním vývoji a už se nepodporuje.</span><span class="sxs-lookup"><span data-stu-id="83ed7-108">While 3D Viewer Beta may remain available in the Microsoft Store for HoloLens (1st gen), it is no longer in active development and is no longer supported.</span></span>

<span data-ttu-id="83ed7-109">Pokud máte potíže s otevřením 3D model ve verzi 3D prohlížeč Beta nebo se některé funkce vašeho 3D model nepodporují, podívejte se níže na specifikace [podporovaného](#supported-content-specifications) obsahu.</span><span class="sxs-lookup"><span data-stu-id="83ed7-109">If you're having trouble opening a 3D model in 3D Viewer Beta, or certain features of your 3D model are unsupported, see [Supported content specifications](#supported-content-specifications) below.</span></span>

<span data-ttu-id="83ed7-110">Pokud chcete vytvářet nebo optimalizovat 3D modely pro použití s 3D prohlížeč Beta, podívejte se níže na článek Optimalizace [3D modelů 3D prohlížeč Beta.](#optimizing-3d-models-for-3d-viewer-beta)</span><span class="sxs-lookup"><span data-stu-id="83ed7-110">To build or optimize 3D models for use with 3D Viewer Beta, see [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta) below.</span></span>

<span data-ttu-id="83ed7-111">Existují dva způsoby, jak otevřít 3D model holoLens.</span><span class="sxs-lookup"><span data-stu-id="83ed7-111">There are two ways to open a 3D model on HoloLens.</span></span> <span data-ttu-id="83ed7-112">Další informace najdete níže v tématu Zobrazení souborů FBX na [HoloLens.](#viewing-fbx-files-on-hololens)</span><span class="sxs-lookup"><span data-stu-id="83ed7-112">See [Viewing FBX files on HoloLens](#viewing-fbx-files-on-hololens) below to learn more.</span></span>

<span data-ttu-id="83ed7-113">Pokud máte po přečtení těchto témat potíže, podívejte se na téma [Řešení potíží](#troubleshooting) níže.</span><span class="sxs-lookup"><span data-stu-id="83ed7-113">If you're having trouble after reading these topics, see [Troubleshooting](#troubleshooting) below.</span></span>

## <a name="supported-content-specifications"></a><span data-ttu-id="83ed7-114">Podporované specifikace obsahu</span><span class="sxs-lookup"><span data-stu-id="83ed7-114">Supported content specifications</span></span>

### <a name="file-format"></a><span data-ttu-id="83ed7-115">Formát souboru</span><span class="sxs-lookup"><span data-stu-id="83ed7-115">File format</span></span>

- <span data-ttu-id="83ed7-116">Formát FBX</span><span class="sxs-lookup"><span data-stu-id="83ed7-116">FBX format</span></span>
- <span data-ttu-id="83ed7-117">Maximální fbx verze 2015.1.0</span><span class="sxs-lookup"><span data-stu-id="83ed7-117">Maximum FBX release 2015.1.0</span></span>

### <a name="file-size"></a><span data-ttu-id="83ed7-118">Velikost souboru</span><span class="sxs-lookup"><span data-stu-id="83ed7-118">File size</span></span>

- <span data-ttu-id="83ed7-119">Minimálně 5 kB</span><span class="sxs-lookup"><span data-stu-id="83ed7-119">Minimum 5 KB</span></span>
- <span data-ttu-id="83ed7-120">Maximálně 500 MB</span><span class="sxs-lookup"><span data-stu-id="83ed7-120">Maximum 500 MB</span></span>

### <a name="geometry"></a><span data-ttu-id="83ed7-121">Geometrie</span><span class="sxs-lookup"><span data-stu-id="83ed7-121">Geometry</span></span>

- <span data-ttu-id="83ed7-122">Pouze mnohoúhelníkové modely.</span><span class="sxs-lookup"><span data-stu-id="83ed7-122">Polygonal models only.</span></span> <span data-ttu-id="83ed7-123">Žádné povrchy dělení aniBS</span><span class="sxs-lookup"><span data-stu-id="83ed7-123">No subdivision surfaces or NURBs</span></span>
- <span data-ttu-id="83ed7-124">Souřadnicový systém spravený doprava</span><span class="sxs-lookup"><span data-stu-id="83ed7-124">Right-handed coordinate system</span></span>
- <span data-ttu-id="83ed7-125">Šmourání v transformačních matricích se nepodporuje.</span><span class="sxs-lookup"><span data-stu-id="83ed7-125">Shear in transformation matrices is not supported</span></span>

### <a name="textures"></a><span data-ttu-id="83ed7-126">Textury</span><span class="sxs-lookup"><span data-stu-id="83ed7-126">Textures</span></span>

- <span data-ttu-id="83ed7-127">Mapy textur musí být vloženy do souboru FBX.</span><span class="sxs-lookup"><span data-stu-id="83ed7-127">Texture maps must be embedded in the FBX file</span></span>
- <span data-ttu-id="83ed7-128">Podporované formáty obrázků</span><span class="sxs-lookup"><span data-stu-id="83ed7-128">Supported image formats</span></span>
  - <span data-ttu-id="83ed7-129">Obrázky JPEG a PNG</span><span class="sxs-lookup"><span data-stu-id="83ed7-129">JPEG and PNG images</span></span>
  - <span data-ttu-id="83ed7-130">Obrázky BMP (24bitová barva true RGB)</span><span class="sxs-lookup"><span data-stu-id="83ed7-130">BMP images (24-bit RGB true-color)</span></span>
  - <span data-ttu-id="83ed7-131">Obrázky TGA (24bitové a 32bitové barvy RGBQ true)</span><span class="sxs-lookup"><span data-stu-id="83ed7-131">TGA images (24-bit RGB and 32-bit RGBQ true-color)</span></span>
- <span data-ttu-id="83ed7-132">Maximální rozlišení textury 2048 × 2048</span><span class="sxs-lookup"><span data-stu-id="83ed7-132">Maximum texture resolution of 2048x2048</span></span>
- <span data-ttu-id="83ed7-133">Maximálně jedna mapová mapa, jedna normální mapa a jedna mapa datové krychle reflexe na jednu síť</span><span class="sxs-lookup"><span data-stu-id="83ed7-133">Maximum of one diffuse map, one normal map, and one reflection cube map per mesh</span></span>
- <span data-ttu-id="83ed7-134">Alfa kanál v texturách tekutých pixelů způsobí zahození pixelů, pokud je nižší než 50 %.</span><span class="sxs-lookup"><span data-stu-id="83ed7-134">Alpha channel in diffuse textures causes pixels to be discarded if below 50%</span></span>

### <a name="animation"></a><span data-ttu-id="83ed7-135">Animace</span><span class="sxs-lookup"><span data-stu-id="83ed7-135">Animation</span></span>

- <span data-ttu-id="83ed7-136">Animace škálování/otočení/posunutí u jednotlivých objektů</span><span class="sxs-lookup"><span data-stu-id="83ed7-136">Scale/rotation/translation animation on individual objects</span></span>
- <span data-ttu-id="83ed7-137">Animace s odřídkanou animací</span><span class="sxs-lookup"><span data-stu-id="83ed7-137">Skeletal (rigged) animation with skinning</span></span>
  - <span data-ttu-id="83ed7-138">Maximálně 4 vlivy na vrchol</span><span class="sxs-lookup"><span data-stu-id="83ed7-138">Maximum of 4 influences per vertex</span></span>

### <a name="materials"></a><span data-ttu-id="83ed7-139">Materiály</span><span class="sxs-lookup"><span data-stu-id="83ed7-139">Materials</span></span>

- <span data-ttu-id="83ed7-140">Podporují se materiály Od s upravitelnými parametry.</span><span class="sxs-lookup"><span data-stu-id="83ed7-140">Lambert and Phong materials are supported, with adjustable parameters</span></span>
- <span data-ttu-id="83ed7-141">Podporované vlastnosti materiálu pro Lambert</span><span class="sxs-lookup"><span data-stu-id="83ed7-141">Supported material properties for Lambert</span></span>
  - <span data-ttu-id="83ed7-142">Hlavní textura (RGB + alfa test)</span><span class="sxs-lookup"><span data-stu-id="83ed7-142">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="83ed7-143">Šmoudlé barvy (RGB)</span><span class="sxs-lookup"><span data-stu-id="83ed7-143">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="83ed7-144">Ambient Color (RGB)</span><span class="sxs-lookup"><span data-stu-id="83ed7-144">Ambient Color (RGB)</span></span>
- <span data-ttu-id="83ed7-145">Podporované vlastnosti materiálu pro Pargs</span><span class="sxs-lookup"><span data-stu-id="83ed7-145">Supported material properties for Phong</span></span>
  - <span data-ttu-id="83ed7-146">Hlavní textura (RGB + alfa test)</span><span class="sxs-lookup"><span data-stu-id="83ed7-146">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="83ed7-147">Šmoudlé barvy (RGB)</span><span class="sxs-lookup"><span data-stu-id="83ed7-147">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="83ed7-148">Ambient Color (RGB)</span><span class="sxs-lookup"><span data-stu-id="83ed7-148">Ambient Color (RGB)</span></span>
  - <span data-ttu-id="83ed7-149">Zrcadlová barva (RGB)</span><span class="sxs-lookup"><span data-stu-id="83ed7-149">Specular Color (RGB)</span></span>
  - <span data-ttu-id="83ed7-150">Šišatost</span><span class="sxs-lookup"><span data-stu-id="83ed7-150">Shininess</span></span>
  - <span data-ttu-id="83ed7-151">Odrazivost</span><span class="sxs-lookup"><span data-stu-id="83ed7-151">Reflectivity</span></span>
- <span data-ttu-id="83ed7-152">Vlastní materiály se nepodporují.</span><span class="sxs-lookup"><span data-stu-id="83ed7-152">Custom materials are not supported</span></span>
- <span data-ttu-id="83ed7-153">Maximálně jeden materiál na síť</span><span class="sxs-lookup"><span data-stu-id="83ed7-153">Maximum of one material per mesh</span></span>
- <span data-ttu-id="83ed7-154">Maximálně jedna vrstva materiálu</span><span class="sxs-lookup"><span data-stu-id="83ed7-154">Maximum of one material layer</span></span>
- <span data-ttu-id="83ed7-155">Maximálně 8 materiálů na soubor</span><span class="sxs-lookup"><span data-stu-id="83ed7-155">Maximum of 8 materials per file</span></span>

### <a name="file-and-model-limitations"></a><span data-ttu-id="83ed7-156">Omezení souborů a modelů</span><span class="sxs-lookup"><span data-stu-id="83ed7-156">File and model limitations</span></span>

<span data-ttu-id="83ed7-157">Velikost souborů a počet modelů, vrcholů a sítí, které mohou být ve verzi beta otevřené současně, jsou 3D prohlížeč limity:</span><span class="sxs-lookup"><span data-stu-id="83ed7-157">There are hard limits on the size of files, as well as the number of models, vertices, and meshes that can be open simultaneously in 3D Viewer Beta:</span></span>

- <span data-ttu-id="83ed7-158">Maximální velikost souboru na model: 500 MB</span><span class="sxs-lookup"><span data-stu-id="83ed7-158">500 MB maximum file size per model</span></span>
- <span data-ttu-id="83ed7-159">Vrcholy: 600 000 kombinovaných ve všech otevřených modelech</span><span class="sxs-lookup"><span data-stu-id="83ed7-159">Vertices: 600,000 combined on all open models</span></span>
- <span data-ttu-id="83ed7-160">Meshes (Sítě): 1 600 kombinovaných ve všech otevřených modelech</span><span class="sxs-lookup"><span data-stu-id="83ed7-160">Meshes: 1,600 combined on all open models</span></span>
- <span data-ttu-id="83ed7-161">Maximálně 40 otevřených modelů najednou</span><span class="sxs-lookup"><span data-stu-id="83ed7-161">Maximum of 40 models open at one time</span></span>

## <a name="optimizing-3d-models-for-3d-viewer-beta"></a><span data-ttu-id="83ed7-162">Optimalizace 3D modelů pro 3D prohlížeč Beta</span><span class="sxs-lookup"><span data-stu-id="83ed7-162">Optimizing 3D models for 3D Viewer Beta</span></span>

### <a name="special-considerations"></a><span data-ttu-id="83ed7-163">Zvláštní aspekty</span><span class="sxs-lookup"><span data-stu-id="83ed7-163">Special considerations</span></span>

- <span data-ttu-id="83ed7-164">Vyhněte se černým materiálům nebo černým oblastem v mapách textur.</span><span class="sxs-lookup"><span data-stu-id="83ed7-164">Avoid black materials or black areas in texture maps.</span></span> <span data-ttu-id="83ed7-165">Hologramy jsou tvořeny světlem, proto se HoloLens vykreslí černě (bez světla) jako průhledné.</span><span class="sxs-lookup"><span data-stu-id="83ed7-165">Holograms are made of light, thus HoloLens renders black (the absence of light) as transparent.</span></span>
- <span data-ttu-id="83ed7-166">Před exportem do FBX z nástroje pro vytváření se ujistěte, že je viditelná a odemknutá veškerá geometrie a že nejsou vypnuté ani šablonované žádné vrstvy obsahující geometrii.</span><span class="sxs-lookup"><span data-stu-id="83ed7-166">Before exporting to FBX from your creation tool, ensure all geometry is visible and unlocked and no layers that contain geometry are turned off or templated.</span></span> <span data-ttu-id="83ed7-167">Viditelnost není respektována.</span><span class="sxs-lookup"><span data-stu-id="83ed7-167">Visibility is not respected.</span></span>
- <span data-ttu-id="83ed7-168">Vyhněte se velmi velkým posunům překladu mezi uzly (například 100 000 jednotek).</span><span class="sxs-lookup"><span data-stu-id="83ed7-168">Avoid very large translation offsets between nodes (for example, 100,000 units).</span></span> <span data-ttu-id="83ed7-169">To může způsobit, že se model během přesunu, škálování nebo otočení bude zachytát.</span><span class="sxs-lookup"><span data-stu-id="83ed7-169">This can cause the model to jitter while being moved/scaled/rotated.</span></span>

### <a name="performance-optimization"></a><span data-ttu-id="83ed7-170">Optimalizace výkonu</span><span class="sxs-lookup"><span data-stu-id="83ed7-170">Performance optimization</span></span>

<span data-ttu-id="83ed7-171">Při vytváření obsahu a ověřování v aplikaci 3D prohlížeč Beta na HoloLens mějte při vytváření obsahu na paměti výkon. Dosáhnete tak nejlepších výsledků.</span><span class="sxs-lookup"><span data-stu-id="83ed7-171">Keep performance in mind while authoring content and validate in the 3D Viewer Beta app on HoloLens during the authoring process for best results.</span></span> <span data-ttu-id="83ed7-172">3D prohlížeč Beta vykresluje obsah v reálném čase a výkon podléhá hardwarovým možnostem HoloLens.</span><span class="sxs-lookup"><span data-stu-id="83ed7-172">3D Viewer Beta renders content real-time and performance is subject to HoloLens hardware capabilities.</span></span>  

<span data-ttu-id="83ed7-173">Existuje mnoho proměnných v 3D model, které mohou mít vliv na výkon.</span><span class="sxs-lookup"><span data-stu-id="83ed7-173">There are many variables in a 3D model that can impact performance.</span></span> <span data-ttu-id="83ed7-174">3D prohlížeč beta verze zobrazí upozornění při zatížení, pokud existuje více než 150 000 vrcholů nebo více než 400 sítí.</span><span class="sxs-lookup"><span data-stu-id="83ed7-174">3D Viewer Beta will show a warning on load if there are more than 150,000 vertices or more than 400 meshes.</span></span> <span data-ttu-id="83ed7-175">Animace mohou mít vliv na výkon jiných otevřených modelů.</span><span class="sxs-lookup"><span data-stu-id="83ed7-175">Animations can have an impact on the performance of other open models.</span></span> <span data-ttu-id="83ed7-176">Existují také pevné limity pro celkové číselné modely, vrcholy a sítě, které lze otevřít současně v 3D prohlížeč Beta (viz Omezení souborů a [modelů).](#file-and-model-limitations)</span><span class="sxs-lookup"><span data-stu-id="83ed7-176">There are also hard limits on the total number models, vertices, and meshes that can be open simultaneously in 3D Viewer Beta (see [File and model limitations](#file-and-model-limitations)).</span></span>  

<span data-ttu-id="83ed7-177">Pokud 3D model dobře nefunguje kvůli složitosti modelu, zvažte následující:</span><span class="sxs-lookup"><span data-stu-id="83ed7-177">If the 3D model isn't running well due to model complexity, consider:</span></span>

- <span data-ttu-id="83ed7-178">Snížení počtu mnohoúhelníků</span><span class="sxs-lookup"><span data-stu-id="83ed7-178">Reducing polygon count</span></span>
- <span data-ttu-id="83ed7-179">Snížení počtu řídce v řídce animaci</span><span class="sxs-lookup"><span data-stu-id="83ed7-179">Reducing number of bones in rigged animation</span></span>
- <span data-ttu-id="83ed7-180">Jak se vyhnout samo okluzi</span><span class="sxs-lookup"><span data-stu-id="83ed7-180">Avoiding self-occlusion</span></span>

<span data-ttu-id="83ed7-181">Vykreslování na dvou stranách se podporuje 3D prohlížeč Beta, i když je ve výchozím nastavení vypnuté z důvodů výkonu.</span><span class="sxs-lookup"><span data-stu-id="83ed7-181">Double-sided rendering is supported in 3D Viewer Beta, although it is turned off by default for performance reasons.</span></span> <span data-ttu-id="83ed7-182">Můžete ji zapnout pomocí tlačítka **s dvojitou stranou** na **stránce Podrobnosti.**</span><span class="sxs-lookup"><span data-stu-id="83ed7-182">This can be turned on via the **Double Sided** button on the **Details** page.</span></span> <span data-ttu-id="83ed7-183">Pokud chcete mít nejlepší výkon, vyhněte se tomu, aby se v obsahu vykresloval na dvou stranách.</span><span class="sxs-lookup"><span data-stu-id="83ed7-183">For best performance, avoid the need for double-sided rendering in your content.</span></span>

### <a name="validating-your-3d-model"></a><span data-ttu-id="83ed7-184">Ověření 3D model</span><span class="sxs-lookup"><span data-stu-id="83ed7-184">Validating your 3D model</span></span>

<span data-ttu-id="83ed7-185">Ověřte model tak, že ho otevřete v 3D prohlížeč Beta na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="83ed7-185">Validate your model by opening it in 3D Viewer Beta on HoloLens.</span></span> <span data-ttu-id="83ed7-186">Výběrem **tlačítka Podrobnosti** zobrazíte charakteristiky a upozornění modelu na nepodporovaný obsah (pokud je k dispozici).</span><span class="sxs-lookup"><span data-stu-id="83ed7-186">Select the **Details** button to view your model's characteristics and warnings of unsupported content (if present).</span></span>

### <a name="rendering-3d-models-with-true-to-life-dimensions"></a><span data-ttu-id="83ed7-187">Vykreslování 3D modelů s skutečnými dimenzemi</span><span class="sxs-lookup"><span data-stu-id="83ed7-187">Rendering 3D models with true-to-life dimensions</span></span>

<span data-ttu-id="83ed7-188">Ve výchozím nastavení 3D prohlížeč beta verze zobrazuje 3D modely v pohodlné velikosti a pozici vzhledem k uživateli.</span><span class="sxs-lookup"><span data-stu-id="83ed7-188">By default, 3D Viewer Beta displays 3D models at a comfortable size and position relative to the user.</span></span> <span data-ttu-id="83ed7-189">Pokud je ale důležité vykreslení 3D model s měřením hodnoty true-to-life (například při vyhodnocování modelů jídel v místnosti), může tvůrce obsahu nastavit příznak v metadatech souboru, aby zabránil změnu velikosti modelu aplikací i uživatelem.</span><span class="sxs-lookup"><span data-stu-id="83ed7-189">However, if rendering a 3D model with true-to-life measurements is important (for example, when evaluating furniture models in a room), the content creator can set a flag within the file's metadata to prevent resizing of that model by both the application and the user.</span></span>

<span data-ttu-id="83ed7-190">Pokud chcete zabránit škálování modelu, přidejte logický vlastní atribut k libovolnému objektu ve scéně s názvem Microsoft_DisableScale a nastavte ho na true.</span><span class="sxs-lookup"><span data-stu-id="83ed7-190">To prevent scaling of the model, add a Boolean custom attribute to any object in the scene named Microsoft_DisableScale and set it to true.</span></span> <span data-ttu-id="83ed7-191">3D prohlížeč Beta pak bude respektovat informace FbxSystemUnit, které jsou v souboru FBX.</span><span class="sxs-lookup"><span data-stu-id="83ed7-191">3D Viewer Beta will then respect the FbxSystemUnit information baked into the FBX file.</span></span> <span data-ttu-id="83ed7-192">Škálování na 3D prohlížeč Beta je 1 měřič na jednotku FBX.</span><span class="sxs-lookup"><span data-stu-id="83ed7-192">Scale in 3D Viewer Beta is 1 meter per FBX unit.</span></span>

## <a name="viewing-fbx-files-on-hololens"></a><span data-ttu-id="83ed7-193">Zobrazení souborů FBX na HoloLens</span><span class="sxs-lookup"><span data-stu-id="83ed7-193">Viewing FBX files on HoloLens</span></span>

### <a name="open-an-fbx-file-from-microsoft-edge"></a><span data-ttu-id="83ed7-194">Otevřete soubor FBX z Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="83ed7-194">Open an FBX file from Microsoft Edge</span></span>

<span data-ttu-id="83ed7-195">Soubory FBX je možné otevřít přímo z webu pomocí Microsoft Edge na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="83ed7-195">FBX files can be opened directly from a website using Microsoft Edge on HoloLens.</span></span>

1. <span data-ttu-id="83ed7-196">V Microsoft Edge přejděte na webovou stránku obsahující soubor FBX, který chcete zobrazit.</span><span class="sxs-lookup"><span data-stu-id="83ed7-196">In Microsoft Edge, navigate to the webpage containing the FBX file you want to view.</span></span>
1. <span data-ttu-id="83ed7-197">Vyberte soubor, který chcete stáhnout.</span><span class="sxs-lookup"><span data-stu-id="83ed7-197">Select the file to download it.</span></span>
1. <span data-ttu-id="83ed7-198">Po dokončení stahování vyberte  tlačítko Otevřít v Microsoft Edge a otevřete soubor v 3D prohlížeč Beta.</span><span class="sxs-lookup"><span data-stu-id="83ed7-198">When the download is complete, select the **Open** button in Microsoft Edge to open the file in 3D Viewer Beta.</span></span>

<span data-ttu-id="83ed7-199">Stažený soubor můžete otevřít a znovu otevřít později pomocí položky Ke stažení v Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="83ed7-199">The downloaded file can be accessed and opened again later by using Downloads in Microsoft Edge.</span></span> <span data-ttu-id="83ed7-200">Pokud chcete uložit 3D model a zajistit pokračování přístupu, stáhněte si soubor do počítače a uložte ho do účtu OneDrivu.</span><span class="sxs-lookup"><span data-stu-id="83ed7-200">To save a 3D model and ensure continued access, download the file on your PC and save it to your OneDrive account.</span></span> <span data-ttu-id="83ed7-201">Soubor se pak dá otevřít z aplikace OneDrive na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="83ed7-201">The file can then be opened from the OneDrive app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="83ed7-202">Některé weby s FBX modely ke stažení je poskytují v komprimovaném formátu ZIP.</span><span class="sxs-lookup"><span data-stu-id="83ed7-202">Some websites with downloadable FBX models provide them in compressed ZIP format.</span></span> <span data-ttu-id="83ed7-203">program 3D Viewer beta nemůže otevřít soubory ZIP přímo.</span><span class="sxs-lookup"><span data-stu-id="83ed7-203">3D Viewer Beta cannot open ZIP files directly.</span></span> <span data-ttu-id="83ed7-204">Místo toho použijte počítač k extrakci souboru FBX a uložte ho na účet OneDrive.</span><span class="sxs-lookup"><span data-stu-id="83ed7-204">Instead, use your PC to extract the FBX file and save it to your OneDrive account.</span></span> <span data-ttu-id="83ed7-205">Soubor se pak dá otevřít z aplikace OneDrive na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="83ed7-205">The file can then be opened from the OneDrive app on HoloLens.</span></span>

### <a name="open-an-fbx-file-from-onedrive"></a><span data-ttu-id="83ed7-206">Otevření souboru FBX z OneDrivu</span><span class="sxs-lookup"><span data-stu-id="83ed7-206">Open an FBX file from OneDrive</span></span>

<span data-ttu-id="83ed7-207">Soubory FBX se dají otevřít z OneDrivu pomocí aplikace OneDrive na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="83ed7-207">FBX files can be opened from OneDrive by using the OneDrive app on HoloLens.</span></span> <span data-ttu-id="83ed7-208">Ujistěte se, že jste nainstalovali OneDrive pomocí Microsoft Store aplikace na HoloLens a že jste už na svém počítači nahráli soubor FBX na OneDrive.</span><span class="sxs-lookup"><span data-stu-id="83ed7-208">Be sure you've installed OneDrive using Microsoft Store app on HoloLens and that you've already uploaded the FBX file to OneDrive on your PC.</span></span>

<span data-ttu-id="83ed7-209">V OneDrivu můžete soubory FBX otevřít na HoloLens pomocí aplikace 3D Viewer beta jedním ze dvou způsobů:</span><span class="sxs-lookup"><span data-stu-id="83ed7-209">Once in OneDrive, FBX files can be opened on HoloLens using 3D Viewer Beta in one of two ways:</span></span>

- <span data-ttu-id="83ed7-210">Spusťte OneDrive na HoloLens a vyberte soubor FBX, který se otevře v aplikaci 3D Viewer beta.</span><span class="sxs-lookup"><span data-stu-id="83ed7-210">Launch OneDrive on HoloLens and select the FBX file to open it in 3D Viewer Beta.</span></span>
- <span data-ttu-id="83ed7-211">Spusťte aplikaci 3D Viewer beta, klepněte na tlačítko Air a zobrazte panel nástrojů a vyberte možnost **otevřít soubor**.</span><span class="sxs-lookup"><span data-stu-id="83ed7-211">Launch 3D Viewer Beta, air tap to show the toolbar, and select **Open File**.</span></span> <span data-ttu-id="83ed7-212">OneDrive se spustí a umožní vám vybrat soubor FBX.</span><span class="sxs-lookup"><span data-stu-id="83ed7-212">OneDrive will launch, allowing you to select an FBX file.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="83ed7-213">Řešení potíží</span><span class="sxs-lookup"><span data-stu-id="83ed7-213">Troubleshooting</span></span>

### <a name="i-see-a-warning-when-i-open-a-3d-model"></a><span data-ttu-id="83ed7-214">Po otevření 3D model se zobrazí upozornění</span><span class="sxs-lookup"><span data-stu-id="83ed7-214">I see a warning when I open a 3D model</span></span>

<span data-ttu-id="83ed7-215">Zobrazí se upozornění, pokud se pokusíte otevřít 3D model, která obsahuje funkce, které nejsou podporovány nástrojem 3D Viewer beta, nebo pokud je model příliš složitý a může být ovlivněn výkon.</span><span class="sxs-lookup"><span data-stu-id="83ed7-215">You will see a warning if you attempt to open a 3D model that contains features that are not supported by 3D Viewer Beta, or if the model is too complex and performance may be affected.</span></span> <span data-ttu-id="83ed7-216">aplikace 3D Viewer beta bude i nadále načítat 3D model, ale může dojít k ohrožení výkonu nebo vizuální věrnosti.</span><span class="sxs-lookup"><span data-stu-id="83ed7-216">3D Viewer Beta will still load the 3D model, but performance or visual fidelity may be compromised.</span></span>

<span data-ttu-id="83ed7-217">Další informace najdete v tématu [podporované specifikace obsahu](#supported-content-specifications) a [Optimalizace 3D modelů pro program 3D Viewer beta](#optimizing-3d-models-for-3d-viewer-beta).</span><span class="sxs-lookup"><span data-stu-id="83ed7-217">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta).</span></span>

### <a name="i-see-a-warning-and-the-3d-model-doesnt-load"></a><span data-ttu-id="83ed7-218">Zobrazuje se upozornění a 3D model se nenačítá</span><span class="sxs-lookup"><span data-stu-id="83ed7-218">I see a warning and the 3D model doesn't load</span></span>

<span data-ttu-id="83ed7-219">Když prostorový Viewer beta nemůže načíst 3D model z důvodu složitosti nebo velikosti souboru nebo pokud je soubor FBX poškozený nebo neplatný, zobrazí se chybová zpráva.</span><span class="sxs-lookup"><span data-stu-id="83ed7-219">You will see an error message when 3D Viewer Beta cannot load a 3D model due to complexity or file size, or if the FBX file is corrupt or invalid.</span></span> <span data-ttu-id="83ed7-220">Chybová zpráva se zobrazí také v případě, že jste dosáhli limitu celkového počtu modelů, vrcholů nebo sítí, které mohou být otevřeny současně.</span><span class="sxs-lookup"><span data-stu-id="83ed7-220">You will also see an error message if you have reached the limit on the total number of models, vertices, or meshes that can be open simultaneously.</span></span>  

<span data-ttu-id="83ed7-221">Další informace najdete v tématech [podporované specifikace obsahu](#supported-content-specifications) a [omezení souborů a modelů](#file-and-model-limitations).</span><span class="sxs-lookup"><span data-stu-id="83ed7-221">For more info, see [Supported content specifications](#supported-content-specifications) and [File and model limitations](#file-and-model-limitations).</span></span>

### <a name="my-3d-model-loads-but-does-not-appear-as-expected"></a><span data-ttu-id="83ed7-222">Moje 3D model načíst, ale nezobrazí se podle očekávání.</span><span class="sxs-lookup"><span data-stu-id="83ed7-222">My 3D model loads, but does not appear as expected</span></span>

<span data-ttu-id="83ed7-223">Pokud vaše 3D model v aplikaci 3D Viewer beta nevypadá podle očekávání, klepněte na tlačítko Air, aby se panel nástrojů zobrazoval a pak vyberte **Podrobnosti**.</span><span class="sxs-lookup"><span data-stu-id="83ed7-223">If your 3D model does not look as expected in 3D Viewer Beta, air tap to show the toolbar, then select **Details**.</span></span> <span data-ttu-id="83ed7-224">Aspekty souboru, které nejsou podporovány aplikací 3D Viewer beta, budou zvýrazněny jako upozornění.</span><span class="sxs-lookup"><span data-stu-id="83ed7-224">Aspects of the file which are not supported by 3D Viewer Beta will be highlighted as warnings.</span></span>

<span data-ttu-id="83ed7-225">Nejběžnější problém, který se může zobrazit, chybí textury, pravděpodobně proto, že nejsou vloženy do souboru FBX.</span><span class="sxs-lookup"><span data-stu-id="83ed7-225">The most common issue you might see is missing textures, likely because they are not embedded in the FBX file.</span></span> <span data-ttu-id="83ed7-226">V takovém případě se model zobrazí jako bílý.</span><span class="sxs-lookup"><span data-stu-id="83ed7-226">In this case, the model will appear white.</span></span> <span data-ttu-id="83ed7-227">Tento problém lze vyřešit tak, že v procesu vytváření exportujete z nástroje pro tvorbu do FBX s vybranou možností vložit textury.</span><span class="sxs-lookup"><span data-stu-id="83ed7-227">This issue can be addressed in the creation process by exporting from your creation tool to FBX with the embed textures option selected.</span></span>

<span data-ttu-id="83ed7-228">Další informace najdete v tématu [podporované specifikace obsahu](#supported-content-specifications) a [Optimalizace 3D modelů pro program 3D Viewer beta](#optimizing-3d-models-for-3d-viewer-beta).</span><span class="sxs-lookup"><span data-stu-id="83ed7-228">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta).</span></span>

### <a name="i-experience-performance-drops-while-viewing-my-3d-model"></a><span data-ttu-id="83ed7-229">Při prohlížení mých 3D model dochází k poklesu výkonu</span><span class="sxs-lookup"><span data-stu-id="83ed7-229">I experience performance drops while viewing my 3D model</span></span>

<span data-ttu-id="83ed7-230">Výkon při načítání a zobrazování 3D model může být ovlivněn složitou složitostí modelu, počtu současně otevřených modelů nebo počtem modelů s aktivními animacemi.</span><span class="sxs-lookup"><span data-stu-id="83ed7-230">Performance when loading and viewing a 3D model can be affected by the complexity of the model, number of models open simultaneously, or number of models with active animations.</span></span>

<span data-ttu-id="83ed7-231">Další informace najdete v tématu [Optimalizace 3D modelů pro 3D Viewer beta](#optimizing-3d-models-for-3d-viewer-beta) a [omezení souborů a modelů](#file-and-model-limitations).</span><span class="sxs-lookup"><span data-stu-id="83ed7-231">For more info, see [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta) and [File and model limitations](#file-and-model-limitations).</span></span>

### <a name="when-i-open-an-fbx-file-on-hololens-it-doesnt-open-in-3d-viewer-beta"></a><span data-ttu-id="83ed7-232">Po otevření souboru FBX na HoloLens se neotevře v programu 3D Viewer beta</span><span class="sxs-lookup"><span data-stu-id="83ed7-232">When I open an FBX file on HoloLens, it doesn't open in 3D Viewer Beta</span></span>

<span data-ttu-id="83ed7-233">Při instalaci aplikace 3D Viewer beta je automaticky přidružena k příponě souboru. FBX.</span><span class="sxs-lookup"><span data-stu-id="83ed7-233">3D Viewer Beta is automatically associated with the .fbx file extension when it is installed.</span></span>

<span data-ttu-id="83ed7-234">Pokud se pokusíte otevřít soubor FBX a zobrazit dialogové okno, které vás přesměruje na Microsoft Store, aktuálně nemáte aplikaci přidruženou k příponě souboru. FBX na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="83ed7-234">If you try to open an FBX file and see a dialog box that directs you to Microsoft Store, you do not currently have an app associated with the .fbx file extension on HoloLens.</span></span>

<span data-ttu-id="83ed7-235">Ověřte, zda je nainstalován nástroj 3D Viewer beta.</span><span class="sxs-lookup"><span data-stu-id="83ed7-235">Verify that 3D Viewer Beta is installed.</span></span> <span data-ttu-id="83ed7-236">Pokud není nainstalovaný, Stáhněte si ho z Microsoft Store na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="83ed7-236">If it is not installed, download it from Microsoft Store on HoloLens.</span></span>

<span data-ttu-id="83ed7-237">Pokud je už nainstalovaný prostorový Viewer beta, spusťte 3D Viewer beta a pak zkuste soubor otevřít znovu.</span><span class="sxs-lookup"><span data-stu-id="83ed7-237">If 3D Viewer Beta is already installed, launch 3D Viewer Beta, then try opening the file again.</span></span> <span data-ttu-id="83ed7-238">Pokud potíže potrvají, odinstalujte a znovu nainstalujte 3D Viewer beta.</span><span class="sxs-lookup"><span data-stu-id="83ed7-238">If the issue persists, uninstall and reinstall 3D Viewer Beta.</span></span> <span data-ttu-id="83ed7-239">Tím se přípona souboru. FBX znovu přidruží k beta verzi aplikace 3D Viewer.</span><span class="sxs-lookup"><span data-stu-id="83ed7-239">This will re-associate the .fbx file extension with 3D Viewer Beta.</span></span>

<span data-ttu-id="83ed7-240">Pokud se při pokusu o otevření souboru FBX otevře jiná aplikace než 3D Viewer beta, tato aplikace se nejspíš nainstalovala po verzi 3D Viewer beta a převzala se přes přidružení s příponou souboru. FBX.</span><span class="sxs-lookup"><span data-stu-id="83ed7-240">If attempting to open an FBX file opens an app other than 3D Viewer Beta, that app was likely installed after 3D Viewer Beta and has taken over association with the .fbx file extension.</span></span> <span data-ttu-id="83ed7-241">Pokud dáváte přednost aplikaci 3D Viewer beta, aby byla přidružena k příponě souboru. FBX, odinstalujte a znovu nainstalujte 3D Viewer beta.</span><span class="sxs-lookup"><span data-stu-id="83ed7-241">If you prefer 3D Viewer Beta to be associated with the .fbx file extension, uninstall and reinstall 3D Viewer Beta.</span></span>

### <a name="the-open-file-button-in-3d-viewer-beta-doesnt-launch-an-app"></a><span data-ttu-id="83ed7-242">Tlačítko otevřít soubor v aplikaci 3D Viewer beta nespustí aplikaci</span><span class="sxs-lookup"><span data-stu-id="83ed7-242">The Open File button in 3D Viewer Beta doesn't launch an app</span></span>

<span data-ttu-id="83ed7-243">Tlačítkem **otevřít soubor** otevřete aplikaci přidruženou k funkci výběr souboru na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="83ed7-243">The **Open File** button will open the app associated with the file picker function on HoloLens.</span></span> <span data-ttu-id="83ed7-244">Pokud je OneDrive nainstalovaný, tlačítko **otevřít soubor** by mělo spustit OneDrive.</span><span class="sxs-lookup"><span data-stu-id="83ed7-244">If OneDrive is installed, the **Open File** button should launch OneDrive.</span></span> <span data-ttu-id="83ed7-245">Pokud ale v tuto chvíli není k dispozici žádná aplikace přidružená k funkci pro výběr souboru nainstalovanou na HoloLens, budete přesměrováni na Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="83ed7-245">However, if there is currently no app associated with the file picker function installed on HoloLens, you will be directed to Microsoft Store.</span></span>

<span data-ttu-id="83ed7-246">Pokud tlačítko **otevřít soubor** spustí jinou aplikaci než OneDrive, tato aplikace se nejspíš nainstalovala po OneDrivu a převzala se přes přidružení pomocí funkce výběru souborů.</span><span class="sxs-lookup"><span data-stu-id="83ed7-246">If the **Open File** button launches an app other than OneDrive, that app was likely installed after OneDrive and has taken over association with the file picker function.</span></span> <span data-ttu-id="83ed7-247">Pokud dáváte přednost spuštění OneDrivu při výběru tlačítka **otevřít soubor** v aplikaci 3D Viewer beta, odinstalujte a znovu nainstalujte OneDrive.</span><span class="sxs-lookup"><span data-stu-id="83ed7-247">If you prefer OneDrive to launch when selecting the **Open File** button in 3D Viewer Beta, uninstall and reinstall OneDrive.</span></span>

<span data-ttu-id="83ed7-248">Pokud není tlačítko **otevřít soubor** aktivní, je možné, že jste dosáhli limitu modelů, které lze v programu 3D Viewer beta otevřít najednou.</span><span class="sxs-lookup"><span data-stu-id="83ed7-248">If the **Open File** button is not active, it's possible that you have reached the limit of models that can be open in 3D Viewer Beta at one time.</span></span> <span data-ttu-id="83ed7-249">Pokud máte modely 40 otevřené v aplikaci 3D Viewer beta, budete je muset zavřít předtím, než budete moct otevřít další modely.</span><span class="sxs-lookup"><span data-stu-id="83ed7-249">If you have 40 models open in 3D Viewer Beta, you will need to close some before you will be able to open additional models.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="83ed7-250">Další zdroje informací</span><span class="sxs-lookup"><span data-stu-id="83ed7-250">Additional resources</span></span>

- <span data-ttu-id="83ed7-251">[Fóra podpory](http://forums.hololens.com/categories/3d-viewer-beta) – jenom pro účely archivace.</span><span class="sxs-lookup"><span data-stu-id="83ed7-251">[Support forums](http://forums.hololens.com/categories/3d-viewer-beta) - For archival purposes only.</span></span> <span data-ttu-id="83ed7-252">Toto fórum už není aktivní.</span><span class="sxs-lookup"><span data-stu-id="83ed7-252">This forum is no longer active.</span></span>
- [<span data-ttu-id="83ed7-253">Oznámení třetích stran</span><span class="sxs-lookup"><span data-stu-id="83ed7-253">Third-party notices</span></span>](https://www.microsoft.com/{lang-locale}/legal/products)
