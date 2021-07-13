---
title: Použití 3D prohlížeč Beta na HoloLens (1. generace)
description: Popisuje typy souborů a funkcí, které 3D prohlížeč beta verze HoloLens (1. generace) podporuje, a způsob použití aplikace a řešení potíží.
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
ms.openlocfilehash: 00e99d3f67e9e4371da12612b9b01c3ce58e71bd
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635479"
---
# <a name="using-3d-viewer-beta-on-hololens-1st-gen"></a><span data-ttu-id="0caf4-103">Použití 3D prohlížeč Beta na HoloLens (1. generace)</span><span class="sxs-lookup"><span data-stu-id="0caf4-103">Using 3D Viewer Beta on HoloLens (1st gen)</span></span>

<span data-ttu-id="0caf4-104">3D prohlížeč Beta umožňuje zobrazit 3D modely na HoloLens (1. generace).</span><span class="sxs-lookup"><span data-stu-id="0caf4-104">3D Viewer Beta lets you view 3D models on HoloLens (1st gen).</span></span> <span data-ttu-id="0caf4-105">Podporované soubory .fbx *můžete* otevřít a zobrazit z Microsoft Edge, OneDrive a dalších aplikací.</span><span class="sxs-lookup"><span data-stu-id="0caf4-105">You can open and view *supported* .fbx files from Microsoft Edge, OneDrive, and other apps.</span></span>

>[!NOTE]
><span data-ttu-id="0caf4-106">Tento článek se týká imerzivní aplikace Unity **3D prohlížeč Beta,** která podporuje soubory .fbx a je k dispozici pouze HoloLens (1. generace).</span><span class="sxs-lookup"><span data-stu-id="0caf4-106">This article applies to the immersive Unity **3D Viewer Beta** app, which supports .fbx files and is only available on HoloLens (1st gen).</span></span> <span data-ttu-id="0caf4-107">Předinstalovaná **aplikace** 3D prohlížeč ve verzi HoloLens 2 podporuje otevírání vlastních 3D modelů .glb [](/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) na domovské stránce hybridní reality (další podrobnosti najdete v tématu Přehled požadavků na prostředky.</span><span class="sxs-lookup"><span data-stu-id="0caf4-107">The pre-installed **3D Viewer** app on HoloLens 2 supports opening custom .glb 3D models in the mixed reality home (see [Asset requirements overview](/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) for more details.</span></span>

>[!IMPORTANT]
><span data-ttu-id="0caf4-108">Přestože 3D prohlížeč beta verze může zůstat dostupná v Microsoft Store pro HoloLens (1. generace), už není v aktivním vývoji a už se nepodporuje.</span><span class="sxs-lookup"><span data-stu-id="0caf4-108">While 3D Viewer Beta may remain available in the Microsoft Store for HoloLens (1st gen), it is no longer in active development and is no longer supported.</span></span>

<span data-ttu-id="0caf4-109">Pokud máte potíže s otevřením 3D model ve verzi 3D prohlížeč Beta nebo se některé funkce vašeho 3D model nepodporují, podívejte se níže na specifikace [podporovaného](#supported-content-specifications) obsahu.</span><span class="sxs-lookup"><span data-stu-id="0caf4-109">If you're having trouble opening a 3D model in 3D Viewer Beta, or certain features of your 3D model are unsupported, see [Supported content specifications](#supported-content-specifications) below.</span></span>

<span data-ttu-id="0caf4-110">Pokud chcete vytvářet nebo optimalizovat 3D modely pro použití s 3D prohlížeč Beta, podívejte se níže na článek Optimalizace [3D modelů 3D prohlížeč Beta.](#optimizing-3d-models-for-3d-viewer-beta)</span><span class="sxs-lookup"><span data-stu-id="0caf4-110">To build or optimize 3D models for use with 3D Viewer Beta, see [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta) below.</span></span>

<span data-ttu-id="0caf4-111">Existují dva způsoby, jak otevřít 3D model na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0caf4-111">There are two ways to open a 3D model on HoloLens.</span></span> <span data-ttu-id="0caf4-112">Další [informace najdete v tématu Zobrazení souborů FBX HoloLens](#viewing-fbx-files-on-hololens) níže.</span><span class="sxs-lookup"><span data-stu-id="0caf4-112">See [Viewing FBX files on HoloLens](#viewing-fbx-files-on-hololens) below to learn more.</span></span>

<span data-ttu-id="0caf4-113">Pokud máte po přečtení těchto témat potíže, podívejte se na téma [Řešení potíží](#troubleshooting) níže.</span><span class="sxs-lookup"><span data-stu-id="0caf4-113">If you're having trouble after reading these topics, see [Troubleshooting](#troubleshooting) below.</span></span>

## <a name="supported-content-specifications"></a><span data-ttu-id="0caf4-114">Podporované specifikace obsahu</span><span class="sxs-lookup"><span data-stu-id="0caf4-114">Supported content specifications</span></span>

### <a name="file-format"></a><span data-ttu-id="0caf4-115">Formát souboru</span><span class="sxs-lookup"><span data-stu-id="0caf4-115">File format</span></span>

- <span data-ttu-id="0caf4-116">Formát FBX</span><span class="sxs-lookup"><span data-stu-id="0caf4-116">FBX format</span></span>
- <span data-ttu-id="0caf4-117">Maximální fbx verze 2015.1.0</span><span class="sxs-lookup"><span data-stu-id="0caf4-117">Maximum FBX release 2015.1.0</span></span>

### <a name="file-size"></a><span data-ttu-id="0caf4-118">Velikost souboru</span><span class="sxs-lookup"><span data-stu-id="0caf4-118">File size</span></span>

- <span data-ttu-id="0caf4-119">Minimálně 5 kB</span><span class="sxs-lookup"><span data-stu-id="0caf4-119">Minimum 5 KB</span></span>
- <span data-ttu-id="0caf4-120">Maximálně 500 MB</span><span class="sxs-lookup"><span data-stu-id="0caf4-120">Maximum 500 MB</span></span>

### <a name="geometry"></a><span data-ttu-id="0caf4-121">Geometrie</span><span class="sxs-lookup"><span data-stu-id="0caf4-121">Geometry</span></span>

- <span data-ttu-id="0caf4-122">Pouze mnohoúhelníkové modely.</span><span class="sxs-lookup"><span data-stu-id="0caf4-122">Polygonal models only.</span></span> <span data-ttu-id="0caf4-123">Žádné povrchy dělení aniBS</span><span class="sxs-lookup"><span data-stu-id="0caf4-123">No subdivision surfaces or NURBs</span></span>
- <span data-ttu-id="0caf4-124">Souřadnicový systém spravně</span><span class="sxs-lookup"><span data-stu-id="0caf4-124">Right-handed coordinate system</span></span>
- <span data-ttu-id="0caf4-125">Zásměk v transformačních matricích se nepodporuje</span><span class="sxs-lookup"><span data-stu-id="0caf4-125">Shear in transformation matrices is not supported</span></span>

### <a name="textures"></a><span data-ttu-id="0caf4-126">Textury</span><span class="sxs-lookup"><span data-stu-id="0caf4-126">Textures</span></span>

- <span data-ttu-id="0caf4-127">Mapy textur musí být vloženy do souboru FBX.</span><span class="sxs-lookup"><span data-stu-id="0caf4-127">Texture maps must be embedded in the FBX file</span></span>
- <span data-ttu-id="0caf4-128">Podporované formáty obrázků</span><span class="sxs-lookup"><span data-stu-id="0caf4-128">Supported image formats</span></span>
  - <span data-ttu-id="0caf4-129">Obrázky JPEG a PNG</span><span class="sxs-lookup"><span data-stu-id="0caf4-129">JPEG and PNG images</span></span>
  - <span data-ttu-id="0caf4-130">Obrázky BMP (24bitová barva true RGB)</span><span class="sxs-lookup"><span data-stu-id="0caf4-130">BMP images (24-bit RGB true-color)</span></span>
  - <span data-ttu-id="0caf4-131">Obrázky TGA (24bitové a 32bitové barvy RGBQ true)</span><span class="sxs-lookup"><span data-stu-id="0caf4-131">TGA images (24-bit RGB and 32-bit RGBQ true-color)</span></span>
- <span data-ttu-id="0caf4-132">Maximální rozlišení textury 2048 × 2048</span><span class="sxs-lookup"><span data-stu-id="0caf4-132">Maximum texture resolution of 2048x2048</span></span>
- <span data-ttu-id="0caf4-133">Maximálně jedna mapová mapa, jedna normální mapa a jedna mapa datové krychle reflexe na jednu síť</span><span class="sxs-lookup"><span data-stu-id="0caf4-133">Maximum of one diffuse map, one normal map, and one reflection cube map per mesh</span></span>
- <span data-ttu-id="0caf4-134">Alfa kanál v texturách tekutých pixelů způsobí zahození pixelů, pokud je hodnota nižší než 50 %.</span><span class="sxs-lookup"><span data-stu-id="0caf4-134">Alpha channel in diffuse textures causes pixels to be discarded if below 50%</span></span>

### <a name="animation"></a><span data-ttu-id="0caf4-135">Animace</span><span class="sxs-lookup"><span data-stu-id="0caf4-135">Animation</span></span>

- <span data-ttu-id="0caf4-136">Animace škálování,otočení/posunutí u jednotlivých objektů</span><span class="sxs-lookup"><span data-stu-id="0caf4-136">Scale/rotation/translation animation on individual objects</span></span>
- <span data-ttu-id="0caf4-137">Animace s odřídkanou animací</span><span class="sxs-lookup"><span data-stu-id="0caf4-137">Skeletal (rigged) animation with skinning</span></span>
  - <span data-ttu-id="0caf4-138">Maximálně 4 vlivy na vrchol</span><span class="sxs-lookup"><span data-stu-id="0caf4-138">Maximum of 4 influences per vertex</span></span>

### <a name="materials"></a><span data-ttu-id="0caf4-139">Materiály</span><span class="sxs-lookup"><span data-stu-id="0caf4-139">Materials</span></span>

- <span data-ttu-id="0caf4-140">Podporují se materiály Od s upravitelnými parametry.</span><span class="sxs-lookup"><span data-stu-id="0caf4-140">Lambert and Phong materials are supported, with adjustable parameters</span></span>
- <span data-ttu-id="0caf4-141">Podporované vlastnosti materiálu pro Lambert</span><span class="sxs-lookup"><span data-stu-id="0caf4-141">Supported material properties for Lambert</span></span>
  - <span data-ttu-id="0caf4-142">Hlavní textura (RGB + alfa test)</span><span class="sxs-lookup"><span data-stu-id="0caf4-142">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="0caf4-143">Šmoudlé barvy (RGB)</span><span class="sxs-lookup"><span data-stu-id="0caf4-143">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="0caf4-144">Ambient Color (RGB)</span><span class="sxs-lookup"><span data-stu-id="0caf4-144">Ambient Color (RGB)</span></span>
- <span data-ttu-id="0caf4-145">Podporované vlastnosti materiálu pro Pargs</span><span class="sxs-lookup"><span data-stu-id="0caf4-145">Supported material properties for Phong</span></span>
  - <span data-ttu-id="0caf4-146">Hlavní textura (RGB + alfa test)</span><span class="sxs-lookup"><span data-stu-id="0caf4-146">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="0caf4-147">Šmoudlé barvy (RGB)</span><span class="sxs-lookup"><span data-stu-id="0caf4-147">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="0caf4-148">Ambient Color (RGB)</span><span class="sxs-lookup"><span data-stu-id="0caf4-148">Ambient Color (RGB)</span></span>
  - <span data-ttu-id="0caf4-149">Zrcadlová barva (RGB)</span><span class="sxs-lookup"><span data-stu-id="0caf4-149">Specular Color (RGB)</span></span>
  - <span data-ttu-id="0caf4-150">Šišatost</span><span class="sxs-lookup"><span data-stu-id="0caf4-150">Shininess</span></span>
  - <span data-ttu-id="0caf4-151">Odrazivost</span><span class="sxs-lookup"><span data-stu-id="0caf4-151">Reflectivity</span></span>
- <span data-ttu-id="0caf4-152">Vlastní materiály se nepodporují.</span><span class="sxs-lookup"><span data-stu-id="0caf4-152">Custom materials are not supported</span></span>
- <span data-ttu-id="0caf4-153">Maximálně jeden materiál na síť</span><span class="sxs-lookup"><span data-stu-id="0caf4-153">Maximum of one material per mesh</span></span>
- <span data-ttu-id="0caf4-154">Maximálně jedna vrstva materiálu</span><span class="sxs-lookup"><span data-stu-id="0caf4-154">Maximum of one material layer</span></span>
- <span data-ttu-id="0caf4-155">Maximálně 8 materiálů na soubor</span><span class="sxs-lookup"><span data-stu-id="0caf4-155">Maximum of 8 materials per file</span></span>

### <a name="file-and-model-limitations"></a><span data-ttu-id="0caf4-156">Omezení souborů a modelů</span><span class="sxs-lookup"><span data-stu-id="0caf4-156">File and model limitations</span></span>

<span data-ttu-id="0caf4-157">Velikost souborů a počet modelů, vrcholů a sítí, které mohou být v beta verzi otevřené současně, 3D prohlížeč pevných prvků:</span><span class="sxs-lookup"><span data-stu-id="0caf4-157">There are hard limits on the size of files, as well as the number of models, vertices, and meshes that can be open simultaneously in 3D Viewer Beta:</span></span>

- <span data-ttu-id="0caf4-158">Maximální velikost souboru na model: 500 MB</span><span class="sxs-lookup"><span data-stu-id="0caf4-158">500 MB maximum file size per model</span></span>
- <span data-ttu-id="0caf4-159">Vrcholy: 600 000 kombinovaných ve všech otevřených modelech</span><span class="sxs-lookup"><span data-stu-id="0caf4-159">Vertices: 600,000 combined on all open models</span></span>
- <span data-ttu-id="0caf4-160">Meshes (Sítě): 1 600 kombinovaných ve všech otevřených modelech</span><span class="sxs-lookup"><span data-stu-id="0caf4-160">Meshes: 1,600 combined on all open models</span></span>
- <span data-ttu-id="0caf4-161">Maximálně 40 otevřených modelů najednou</span><span class="sxs-lookup"><span data-stu-id="0caf4-161">Maximum of 40 models open at one time</span></span>

## <a name="optimizing-3d-models-for-3d-viewer-beta"></a><span data-ttu-id="0caf4-162">Optimalizace 3D modelů pro 3D prohlížeč Beta</span><span class="sxs-lookup"><span data-stu-id="0caf4-162">Optimizing 3D models for 3D Viewer Beta</span></span>

### <a name="special-considerations"></a><span data-ttu-id="0caf4-163">Zvláštní aspekty</span><span class="sxs-lookup"><span data-stu-id="0caf4-163">Special considerations</span></span>

- <span data-ttu-id="0caf4-164">Vyhněte se černým materiálům nebo černým oblastem v mapách textur.</span><span class="sxs-lookup"><span data-stu-id="0caf4-164">Avoid black materials or black areas in texture maps.</span></span> <span data-ttu-id="0caf4-165">Hologramy jsou tvořeny světlem, HoloLens se černě (bez světla) jako průhledné.</span><span class="sxs-lookup"><span data-stu-id="0caf4-165">Holograms are made of light, thus HoloLens renders black (the absence of light) as transparent.</span></span>
- <span data-ttu-id="0caf4-166">Před exportem do FBX z nástroje pro vytváření se ujistěte, že je viditelná a odemknutá veškerá geometrie a že nejsou vypnuté ani šablonované žádné vrstvy obsahující geometrii.</span><span class="sxs-lookup"><span data-stu-id="0caf4-166">Before exporting to FBX from your creation tool, ensure all geometry is visible and unlocked and no layers that contain geometry are turned off or templated.</span></span> <span data-ttu-id="0caf4-167">Viditelnost není respektována.</span><span class="sxs-lookup"><span data-stu-id="0caf4-167">Visibility is not respected.</span></span>
- <span data-ttu-id="0caf4-168">Vyhněte se velmi velkým posunům překladu mezi uzly (například 100 000 jednotek).</span><span class="sxs-lookup"><span data-stu-id="0caf4-168">Avoid very large translation offsets between nodes (for example, 100,000 units).</span></span> <span data-ttu-id="0caf4-169">To může způsobit, že se model během přesunu, škálování nebo otočení bude zachytovat.</span><span class="sxs-lookup"><span data-stu-id="0caf4-169">This can cause the model to jitter while being moved/scaled/rotated.</span></span>

### <a name="performance-optimization"></a><span data-ttu-id="0caf4-170">Optimalizace výkonu</span><span class="sxs-lookup"><span data-stu-id="0caf4-170">Performance optimization</span></span>

<span data-ttu-id="0caf4-171">Při vytváření obsahu mějte na paměti výkon a ověřte 3D prohlížeč beta verzi HoloLens během procesu vytváření obsahu, aby se vám to nejlépe posouvání.</span><span class="sxs-lookup"><span data-stu-id="0caf4-171">Keep performance in mind while authoring content and validate in the 3D Viewer Beta app on HoloLens during the authoring process for best results.</span></span> <span data-ttu-id="0caf4-172">3D prohlížeč Beta vykresluje obsah v reálném čase a výkon podléhá HoloLens hardwarových funkcí.</span><span class="sxs-lookup"><span data-stu-id="0caf4-172">3D Viewer Beta renders content real-time and performance is subject to HoloLens hardware capabilities.</span></span>  

<span data-ttu-id="0caf4-173">Existuje mnoho proměnných v 3D model, které mohou mít vliv na výkon.</span><span class="sxs-lookup"><span data-stu-id="0caf4-173">There are many variables in a 3D model that can impact performance.</span></span> <span data-ttu-id="0caf4-174">3D prohlížeč beta verze zobrazí upozornění při zatížení, pokud existuje více než 150 000 vrcholů nebo více než 400 sítí.</span><span class="sxs-lookup"><span data-stu-id="0caf4-174">3D Viewer Beta will show a warning on load if there are more than 150,000 vertices or more than 400 meshes.</span></span> <span data-ttu-id="0caf4-175">Animace mohou mít vliv na výkon jiných otevřených modelů.</span><span class="sxs-lookup"><span data-stu-id="0caf4-175">Animations can have an impact on the performance of other open models.</span></span> <span data-ttu-id="0caf4-176">Existují také pevné limity pro celkové číselné modely, vrcholy a sítě, které lze otevřít současně v 3D prohlížeč Beta (viz Omezení souborů a [modelů).](#file-and-model-limitations)</span><span class="sxs-lookup"><span data-stu-id="0caf4-176">There are also hard limits on the total number models, vertices, and meshes that can be open simultaneously in 3D Viewer Beta (see [File and model limitations](#file-and-model-limitations)).</span></span>  

<span data-ttu-id="0caf4-177">Pokud 3D model dobře nefunguje kvůli složitosti modelu, zvažte následující:</span><span class="sxs-lookup"><span data-stu-id="0caf4-177">If the 3D model isn't running well due to model complexity, consider:</span></span>

- <span data-ttu-id="0caf4-178">Snížení počtu mnohoúhelníků</span><span class="sxs-lookup"><span data-stu-id="0caf4-178">Reducing polygon count</span></span>
- <span data-ttu-id="0caf4-179">Snížení počtu řídce v řídce animaci</span><span class="sxs-lookup"><span data-stu-id="0caf4-179">Reducing number of bones in rigged animation</span></span>
- <span data-ttu-id="0caf4-180">Jak se vyhnout samo okluzi</span><span class="sxs-lookup"><span data-stu-id="0caf4-180">Avoiding self-occlusion</span></span>

<span data-ttu-id="0caf4-181">Vykreslování na dvou stranách se podporuje 3D prohlížeč Beta, i když je ve výchozím nastavení vypnuté z důvodů výkonu.</span><span class="sxs-lookup"><span data-stu-id="0caf4-181">Double-sided rendering is supported in 3D Viewer Beta, although it is turned off by default for performance reasons.</span></span> <span data-ttu-id="0caf4-182">Můžete ji zapnout pomocí tlačítka **s dvojitou stranou** na **stránce Podrobnosti.**</span><span class="sxs-lookup"><span data-stu-id="0caf4-182">This can be turned on via the **Double Sided** button on the **Details** page.</span></span> <span data-ttu-id="0caf4-183">Pokud chcete mít nejlepší výkon, vyhněte se tomu, aby se v obsahu vykresloval na dvou stranách.</span><span class="sxs-lookup"><span data-stu-id="0caf4-183">For best performance, avoid the need for double-sided rendering in your content.</span></span>

### <a name="validating-your-3d-model"></a><span data-ttu-id="0caf4-184">Ověření 3D model</span><span class="sxs-lookup"><span data-stu-id="0caf4-184">Validating your 3D model</span></span>

<span data-ttu-id="0caf4-185">Ověřte model tak, že ho otevřete v 3D prohlížeč Beta na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0caf4-185">Validate your model by opening it in 3D Viewer Beta on HoloLens.</span></span> <span data-ttu-id="0caf4-186">Výběrem **tlačítka Podrobnosti** zobrazíte charakteristiky a upozornění modelu na nepodporovaný obsah (pokud je k dispozici).</span><span class="sxs-lookup"><span data-stu-id="0caf4-186">Select the **Details** button to view your model's characteristics and warnings of unsupported content (if present).</span></span>

### <a name="rendering-3d-models-with-true-to-life-dimensions"></a><span data-ttu-id="0caf4-187">Vykreslování 3D modelů s skutečnými dimenzemi</span><span class="sxs-lookup"><span data-stu-id="0caf4-187">Rendering 3D models with true-to-life dimensions</span></span>

<span data-ttu-id="0caf4-188">Ve výchozím nastavení 3D prohlížeč Beta zobrazuje 3D modely v pohodlné velikosti a pozici vzhledem k uživateli.</span><span class="sxs-lookup"><span data-stu-id="0caf4-188">By default, 3D Viewer Beta displays 3D models at a comfortable size and position relative to the user.</span></span> <span data-ttu-id="0caf4-189">Pokud je ale důležité vykreslení 3D model s měřením hodnoty true-to-life (například při vyhodnocování modelů jídel v místnosti), může tvůrce obsahu nastavit příznak v metadatech souboru, aby zabránil změnu velikosti modelu aplikací i uživatelem.</span><span class="sxs-lookup"><span data-stu-id="0caf4-189">However, if rendering a 3D model with true-to-life measurements is important (for example, when evaluating furniture models in a room), the content creator can set a flag within the file's metadata to prevent resizing of that model by both the application and the user.</span></span>

<span data-ttu-id="0caf4-190">Pokud chcete zabránit škálování modelu, přidejte logický vlastní atribut k libovolnému objektu ve scéně s názvem Microsoft_DisableScale a nastavte ho na true.</span><span class="sxs-lookup"><span data-stu-id="0caf4-190">To prevent scaling of the model, add a Boolean custom attribute to any object in the scene named Microsoft_DisableScale and set it to true.</span></span> <span data-ttu-id="0caf4-191">3D prohlížeč Beta pak bude respektovat informace FbxSystemUnit, které jsou v souboru FBX.</span><span class="sxs-lookup"><span data-stu-id="0caf4-191">3D Viewer Beta will then respect the FbxSystemUnit information baked into the FBX file.</span></span> <span data-ttu-id="0caf4-192">Škálování na 3D prohlížeč Beta je 1 měřič na jednotku FBX.</span><span class="sxs-lookup"><span data-stu-id="0caf4-192">Scale in 3D Viewer Beta is 1 meter per FBX unit.</span></span>

## <a name="viewing-fbx-files-on-hololens"></a><span data-ttu-id="0caf4-193">Zobrazení souborů FBX na HoloLens</span><span class="sxs-lookup"><span data-stu-id="0caf4-193">Viewing FBX files on HoloLens</span></span>

### <a name="open-an-fbx-file-from-microsoft-edge"></a><span data-ttu-id="0caf4-194">Otevřete soubor FBX z Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0caf4-194">Open an FBX file from Microsoft Edge</span></span>

<span data-ttu-id="0caf4-195">Soubory FBX je možné otevřít přímo z webu pomocí Microsoft Edge na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0caf4-195">FBX files can be opened directly from a website using Microsoft Edge on HoloLens.</span></span>

1. <span data-ttu-id="0caf4-196">V Microsoft Edge přejděte na webovou stránku obsahující soubor FBX, který chcete zobrazit.</span><span class="sxs-lookup"><span data-stu-id="0caf4-196">In Microsoft Edge, navigate to the webpage containing the FBX file you want to view.</span></span>
1. <span data-ttu-id="0caf4-197">Vyberte soubor, který chcete stáhnout.</span><span class="sxs-lookup"><span data-stu-id="0caf4-197">Select the file to download it.</span></span>
1. <span data-ttu-id="0caf4-198">Po dokončení stahování vyberte  tlačítko Otevřít v Microsoft Edge a otevřete soubor ve verzi 3D prohlížeč Beta.</span><span class="sxs-lookup"><span data-stu-id="0caf4-198">When the download is complete, select the **Open** button in Microsoft Edge to open the file in 3D Viewer Beta.</span></span>

<span data-ttu-id="0caf4-199">Stažený soubor můžete otevřít a znovu otevřít později pomocí položky Ke stažení v Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="0caf4-199">The downloaded file can be accessed and opened again later by using Downloads in Microsoft Edge.</span></span> <span data-ttu-id="0caf4-200">Pokud chcete uložit 3D model a zajistit trvalý přístup, stáhněte si soubor do počítače a uložte ho do OneDrive účtu.</span><span class="sxs-lookup"><span data-stu-id="0caf4-200">To save a 3D model and ensure continued access, download the file on your PC and save it to your OneDrive account.</span></span> <span data-ttu-id="0caf4-201">Soubor pak můžete otevřít z aplikace OneDrive na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0caf4-201">The file can then be opened from the OneDrive app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="0caf4-202">Některé weby s modely FBX ke stažení je poskytují v komprimovaném formátu ZIP.</span><span class="sxs-lookup"><span data-stu-id="0caf4-202">Some websites with downloadable FBX models provide them in compressed ZIP format.</span></span> <span data-ttu-id="0caf4-203">3D prohlížeč Beta nemůže otevřít soubory ZIP přímo.</span><span class="sxs-lookup"><span data-stu-id="0caf4-203">3D Viewer Beta cannot open ZIP files directly.</span></span> <span data-ttu-id="0caf4-204">Místo toho pomocí počítače extrahujte soubor FBX a uložte ho do OneDrive účtu.</span><span class="sxs-lookup"><span data-stu-id="0caf4-204">Instead, use your PC to extract the FBX file and save it to your OneDrive account.</span></span> <span data-ttu-id="0caf4-205">Soubor pak můžete otevřít z aplikace OneDrive na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0caf4-205">The file can then be opened from the OneDrive app on HoloLens.</span></span>

### <a name="open-an-fbx-file-from-onedrive"></a><span data-ttu-id="0caf4-206">Otevřete soubor FBX z OneDrive</span><span class="sxs-lookup"><span data-stu-id="0caf4-206">Open an FBX file from OneDrive</span></span>

<span data-ttu-id="0caf4-207">Soubory FBX je možné otevřít OneDrive pomocí OneDrive aplikace na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0caf4-207">FBX files can be opened from OneDrive by using the OneDrive app on HoloLens.</span></span> <span data-ttu-id="0caf4-208">Ujistěte se, že jste OneDrive Microsoft Store aplikaci na HoloLens a že jste soubor FBX už nahráli do OneDrive počítače.</span><span class="sxs-lookup"><span data-stu-id="0caf4-208">Be sure you've installed OneDrive using Microsoft Store app on HoloLens and that you've already uploaded the FBX file to OneDrive on your PC.</span></span>

<span data-ttu-id="0caf4-209">Jakmile jsou OneDrive, můžete soubory FBX otevřít na HoloLens pomocí 3D prohlížeč Beta jedním ze dvou způsobů:</span><span class="sxs-lookup"><span data-stu-id="0caf4-209">Once in OneDrive, FBX files can be opened on HoloLens using 3D Viewer Beta in one of two ways:</span></span>

- <span data-ttu-id="0caf4-210">Spusťte OneDrive na HoloLens a výběrem souboru FBX ho otevřete v 3D prohlížeč Beta.</span><span class="sxs-lookup"><span data-stu-id="0caf4-210">Launch OneDrive on HoloLens and select the FBX file to open it in 3D Viewer Beta.</span></span>
- <span data-ttu-id="0caf4-211">Spusťte 3D prohlížeč Beta, klepnutím ve vzduchu zobrazte panel nástrojů a vyberte **Otevřít soubor.**</span><span class="sxs-lookup"><span data-stu-id="0caf4-211">Launch 3D Viewer Beta, air tap to show the toolbar, and select **Open File**.</span></span> <span data-ttu-id="0caf4-212">OneDrive se spustí , což vám umožní vybrat soubor FBX.</span><span class="sxs-lookup"><span data-stu-id="0caf4-212">OneDrive will launch, allowing you to select an FBX file.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="0caf4-213">Poradce při potížích</span><span class="sxs-lookup"><span data-stu-id="0caf4-213">Troubleshooting</span></span>

### <a name="i-see-a-warning-when-i-open-a-3d-model"></a><span data-ttu-id="0caf4-214">Při otevření aplikace se 3D model</span><span class="sxs-lookup"><span data-stu-id="0caf4-214">I see a warning when I open a 3D model</span></span>

<span data-ttu-id="0caf4-215">Pokud se pokusíte otevřít 3D model obsahující funkce, které 3D prohlížeč Beta nepodporuje, nebo pokud je model příliš složitý a může to mít vliv na výkon, zobrazí se upozornění.</span><span class="sxs-lookup"><span data-stu-id="0caf4-215">You will see a warning if you attempt to open a 3D model that contains features that are not supported by 3D Viewer Beta, or if the model is too complex and performance may be affected.</span></span> <span data-ttu-id="0caf4-216">3D prohlížeč Beta bude nadále načítat 3D model, ale může dojít k ohrožení výkonu nebo vizuální věrnosti.</span><span class="sxs-lookup"><span data-stu-id="0caf4-216">3D Viewer Beta will still load the 3D model, but performance or visual fidelity may be compromised.</span></span>

<span data-ttu-id="0caf4-217">Další informace najdete v tématu [Podporované specifikace obsahu](#supported-content-specifications) a Optimalizace [3D modelů pro 3D prohlížeč Beta.](#optimizing-3d-models-for-3d-viewer-beta)</span><span class="sxs-lookup"><span data-stu-id="0caf4-217">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta).</span></span>

### <a name="i-see-a-warning-and-the-3d-model-doesnt-load"></a><span data-ttu-id="0caf4-218">Zobrazí se upozornění a 3D model se nenačte</span><span class="sxs-lookup"><span data-stu-id="0caf4-218">I see a warning and the 3D model doesn't load</span></span>

<span data-ttu-id="0caf4-219">Chybová zpráva se zobrazí, když 3D prohlížeč beta verze nemůže načíst 3D model kvůli složitosti nebo velikosti souboru nebo pokud je soubor FBX poškozený nebo neplatný.</span><span class="sxs-lookup"><span data-stu-id="0caf4-219">You will see an error message when 3D Viewer Beta cannot load a 3D model due to complexity or file size, or if the FBX file is corrupt or invalid.</span></span> <span data-ttu-id="0caf4-220">Pokud jste dosáhli limitu celkového počtu modelů, vrcholů nebo sítí, které mohou být současně otevřené, zobrazí se také chybová zpráva.</span><span class="sxs-lookup"><span data-stu-id="0caf4-220">You will also see an error message if you have reached the limit on the total number of models, vertices, or meshes that can be open simultaneously.</span></span>  

<span data-ttu-id="0caf4-221">Další informace najdete v tématu [Podporované specifikace obsahu](#supported-content-specifications) a Omezení souborů a [modelů.](#file-and-model-limitations)</span><span class="sxs-lookup"><span data-stu-id="0caf4-221">For more info, see [Supported content specifications](#supported-content-specifications) and [File and model limitations](#file-and-model-limitations).</span></span>

### <a name="my-3d-model-loads-but-does-not-appear-as-expected"></a><span data-ttu-id="0caf4-222">Moje 3D model se načítá, ale nezobrazuje se podle očekávání</span><span class="sxs-lookup"><span data-stu-id="0caf4-222">My 3D model loads, but does not appear as expected</span></span>

<span data-ttu-id="0caf4-223">Pokud vaše 3D model ve verzi beta 3D prohlížeč očekávaným způsobem, klepnutím ve vzduchu zobrazte panel nástrojů a pak vyberte **Podrobnosti.**</span><span class="sxs-lookup"><span data-stu-id="0caf4-223">If your 3D model does not look as expected in 3D Viewer Beta, air tap to show the toolbar, then select **Details**.</span></span> <span data-ttu-id="0caf4-224">Aspekty souboru, které nejsou podporované 3D prohlížeč beta verze, se zvýrazní jako upozornění.</span><span class="sxs-lookup"><span data-stu-id="0caf4-224">Aspects of the file which are not supported by 3D Viewer Beta will be highlighted as warnings.</span></span>

<span data-ttu-id="0caf4-225">Nejběžnějším problémem, který se může zobrazit, jsou chybějící textury, pravděpodobně proto, že nejsou vložené do souboru FBX.</span><span class="sxs-lookup"><span data-stu-id="0caf4-225">The most common issue you might see is missing textures, likely because they are not embedded in the FBX file.</span></span> <span data-ttu-id="0caf4-226">V tomto případě se model zobrazí jako bílý.</span><span class="sxs-lookup"><span data-stu-id="0caf4-226">In this case, the model will appear white.</span></span> <span data-ttu-id="0caf4-227">Tento problém je možné vyřešit při vytváření exportem z nástroje pro vytváření do FBX s vybranou možností textury vložení.</span><span class="sxs-lookup"><span data-stu-id="0caf4-227">This issue can be addressed in the creation process by exporting from your creation tool to FBX with the embed textures option selected.</span></span>

<span data-ttu-id="0caf4-228">Další informace najdete v tématu [Podporované specifikace obsahu](#supported-content-specifications) a Optimalizace [3D modelů pro 3D prohlížeč Beta.](#optimizing-3d-models-for-3d-viewer-beta)</span><span class="sxs-lookup"><span data-stu-id="0caf4-228">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta).</span></span>

### <a name="i-experience-performance-drops-while-viewing-my-3d-model"></a><span data-ttu-id="0caf4-229">Při prohlížení obrazovky u mě docházet k poklesu výkonu 3D model</span><span class="sxs-lookup"><span data-stu-id="0caf4-229">I experience performance drops while viewing my 3D model</span></span>

<span data-ttu-id="0caf4-230">Výkon při načítání a zobrazování 3D model může ovlivnit složitost modelu, počet současně otevřených modelů nebo počet modelů s aktivními animacemi.</span><span class="sxs-lookup"><span data-stu-id="0caf4-230">Performance when loading and viewing a 3D model can be affected by the complexity of the model, number of models open simultaneously, or number of models with active animations.</span></span>

<span data-ttu-id="0caf4-231">Další informace najdete v tématu [Optimalizace 3D modelů pro 3D prohlížeč beta verze](#optimizing-3d-models-for-3d-viewer-beta) a omezení souborů a [modelů.](#file-and-model-limitations)</span><span class="sxs-lookup"><span data-stu-id="0caf4-231">For more info, see [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta) and [File and model limitations](#file-and-model-limitations).</span></span>

### <a name="when-i-open-an-fbx-file-on-hololens-it-doesnt-open-in-3d-viewer-beta"></a><span data-ttu-id="0caf4-232">Když otevřete soubor FBX na HoloLens, neotevře se ve verzi 3D prohlížeč Beta.</span><span class="sxs-lookup"><span data-stu-id="0caf4-232">When I open an FBX file on HoloLens, it doesn't open in 3D Viewer Beta</span></span>

<span data-ttu-id="0caf4-233">3D prohlížeč beta verze je automaticky přidružena k příponě souboru .fbx při instalaci.</span><span class="sxs-lookup"><span data-stu-id="0caf4-233">3D Viewer Beta is automatically associated with the .fbx file extension when it is installed.</span></span>

<span data-ttu-id="0caf4-234">Pokud se pokusíte otevřít soubor FBX a zobrazí se dialogové okno, které vás přesměruje na Microsoft Store, v současné době nemáte k příponě souboru .fbx přidruženou HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0caf4-234">If you try to open an FBX file and see a dialog box that directs you to Microsoft Store, you do not currently have an app associated with the .fbx file extension on HoloLens.</span></span>

<span data-ttu-id="0caf4-235">Ověřte, 3D prohlížeč je nainstalovaná beta verze.</span><span class="sxs-lookup"><span data-stu-id="0caf4-235">Verify that 3D Viewer Beta is installed.</span></span> <span data-ttu-id="0caf4-236">Pokud není nainstalovaný, stáhněte si ho z Microsoft Store na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0caf4-236">If it is not installed, download it from Microsoft Store on HoloLens.</span></span>

<span data-ttu-id="0caf4-237">Pokud 3D prohlížeč nainstalovaná beta verze, spusťte 3D prohlížeč Beta a pak zkuste soubor otevřít znovu.</span><span class="sxs-lookup"><span data-stu-id="0caf4-237">If 3D Viewer Beta is already installed, launch 3D Viewer Beta, then try opening the file again.</span></span> <span data-ttu-id="0caf4-238">Pokud problém přetrvává, odinstalujte a znovu nainstalujte 3D prohlížeč Beta.</span><span class="sxs-lookup"><span data-stu-id="0caf4-238">If the issue persists, uninstall and reinstall 3D Viewer Beta.</span></span> <span data-ttu-id="0caf4-239">Tím se znovu přidruží přípona souboru .fbx k 3D prohlížeč Beta.</span><span class="sxs-lookup"><span data-stu-id="0caf4-239">This will re-associate the .fbx file extension with 3D Viewer Beta.</span></span>

<span data-ttu-id="0caf4-240">Pokud se pokusíte otevřít soubor FBX, otevře se jiná aplikace než 3D prohlížeč Beta, tato aplikace se pravděpodobně nainstalovala po 3D prohlížeč Beta a převzala přidružení k příponě souboru .fbx.</span><span class="sxs-lookup"><span data-stu-id="0caf4-240">If attempting to open an FBX file opens an app other than 3D Viewer Beta, that app was likely installed after 3D Viewer Beta and has taken over association with the .fbx file extension.</span></span> <span data-ttu-id="0caf4-241">Pokud dáváte přednost 3D prohlížeč beta verzi, aby byla přidružená k příponě souboru .fbx, odinstalujte a znovu 3D prohlížeč Beta.</span><span class="sxs-lookup"><span data-stu-id="0caf4-241">If you prefer 3D Viewer Beta to be associated with the .fbx file extension, uninstall and reinstall 3D Viewer Beta.</span></span>

### <a name="the-open-file-button-in-3d-viewer-beta-doesnt-launch-an-app"></a><span data-ttu-id="0caf4-242">Tlačítko Otevřít soubor v 3D prohlížeč Beta aplikaci nespuštěné</span><span class="sxs-lookup"><span data-stu-id="0caf4-242">The Open File button in 3D Viewer Beta doesn't launch an app</span></span>

<span data-ttu-id="0caf4-243">Tlačítko **Otevřít soubor** otevře aplikaci přidruženou k funkci výběru souborů na HoloLens.</span><span class="sxs-lookup"><span data-stu-id="0caf4-243">The **Open File** button will open the app associated with the file picker function on HoloLens.</span></span> <span data-ttu-id="0caf4-244">Pokud OneDrive nainstalovaná, mělo **by se tlačítko Otevřít soubor** spustit OneDrive.</span><span class="sxs-lookup"><span data-stu-id="0caf4-244">If OneDrive is installed, the **Open File** button should launch OneDrive.</span></span> <span data-ttu-id="0caf4-245">Pokud ale v tuto chvíli není k funkci výběru souborů nainstalovaná žádná aplikace, HoloLens, budete přesměrováni na Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="0caf4-245">However, if there is currently no app associated with the file picker function installed on HoloLens, you will be directed to Microsoft Store.</span></span>

<span data-ttu-id="0caf4-246">Pokud **tlačítko Otevřít soubor** spustí jinou aplikaci než OneDrive, tato aplikace se pravděpodobně nainstalovala po OneDrive a převzala přidružení k funkci výběru souborů.</span><span class="sxs-lookup"><span data-stu-id="0caf4-246">If the **Open File** button launches an app other than OneDrive, that app was likely installed after OneDrive and has taken over association with the file picker function.</span></span> <span data-ttu-id="0caf4-247">Pokud dáváte přednost OneDrive spustit při výběru tlačítka **Otevřít** soubor v 3D prohlížeč Beta, odinstalujte a znovu nainstalujte OneDrive.</span><span class="sxs-lookup"><span data-stu-id="0caf4-247">If you prefer OneDrive to launch when selecting the **Open File** button in 3D Viewer Beta, uninstall and reinstall OneDrive.</span></span>

<span data-ttu-id="0caf4-248">Pokud **tlačítko Otevřít soubor** není aktivní, je možné, že jste dosáhli limitu modelů, které je možné otevřít v 3D prohlížeč Beta najednou.</span><span class="sxs-lookup"><span data-stu-id="0caf4-248">If the **Open File** button is not active, it's possible that you have reached the limit of models that can be open in 3D Viewer Beta at one time.</span></span> <span data-ttu-id="0caf4-249">Pokud máte v beta verzi 3D prohlížeč 40 modelů, budete muset některé modely zavřít, abyste mohli otevřít další modely.</span><span class="sxs-lookup"><span data-stu-id="0caf4-249">If you have 40 models open in 3D Viewer Beta, you will need to close some before you will be able to open additional models.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0caf4-250">Další zdroje informací</span><span class="sxs-lookup"><span data-stu-id="0caf4-250">Additional resources</span></span>

- <span data-ttu-id="0caf4-251">[Fóra podpory](http://forums.hololens.com/categories/3d-viewer-beta) – jenom pro archivní účely.</span><span class="sxs-lookup"><span data-stu-id="0caf4-251">[Support forums](http://forums.hololens.com/categories/3d-viewer-beta) - For archival purposes only.</span></span> <span data-ttu-id="0caf4-252">Toto fórum už není aktivní.</span><span class="sxs-lookup"><span data-stu-id="0caf4-252">This forum is no longer active.</span></span>
- [<span data-ttu-id="0caf4-253">Oznámení třetích stran</span><span class="sxs-lookup"><span data-stu-id="0caf4-253">Third-party notices</span></span>](https://www.microsoft.com/{lang-locale}/legal/products)
