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
ms.openlocfilehash: 00e99d3f67e9e4371da12612b9b01c3ce58e71bd
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428929"
---
# <a name="using-3d-viewer-beta-on-hololens-1st-gen"></a>Použití 3D prohlížeč Beta na HoloLens (1. generace)

3D prohlížeč Beta umožňuje zobrazit 3D modely na HoloLens (1. generace). Podporované soubory .fbx *můžete* otevřít a zobrazit z Microsoft Edge, OneDrive a dalších aplikací.

>[!NOTE]
>Tento článek se týká imerzivní aplikace Unity **3D prohlížeč Beta,** která podporuje soubory .fbx a je k dispozici pouze HoloLens (1. generace). Předinstalovaná aplikace **3D prohlížeč** ve verzi HoloLens 2 podporuje otevírání vlastních 3D modelů .glb [](/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) na domovské stránce hybridní reality (další podrobnosti najdete v tématu Přehled požadavků na prostředky.

>[!IMPORTANT]
>I 3D prohlížeč beta verze může zůstat dostupná v Microsoft Store pro HoloLens (1. generace), už není v aktivním vývoji a už se nepodporuje.

Pokud máte potíže s otevřením 3D model 3D prohlížeč beta verze nebo se některé funkce vašeho 3D model nepodporují, podívejte se níže na specifikace podporovaného [obsahu.](#supported-content-specifications)

Pokud chcete vytvářet nebo optimalizovat 3D modely pro použití s 3D prohlížeč Beta, podívejte se níže na článek Optimalizace [3D modelů 3D prohlížeč Beta.](#optimizing-3d-models-for-3d-viewer-beta)

Existují dva způsoby, jak otevřít 3D model na HoloLens. Další [informace najdete v tématu Zobrazení souborů FBX HoloLens](#viewing-fbx-files-on-hololens) níže.

Pokud máte po přečtení těchto témat potíže, podívejte se na téma [Řešení potíží](#troubleshooting) níže.

## <a name="supported-content-specifications"></a>Podporované specifikace obsahu

### <a name="file-format"></a>Formát souboru

- Formát FBX
- Maximální fbx verze 2015.1.0

### <a name="file-size"></a>Velikost souboru

- Minimálně 5 kB
- Maximálně 500 MB

### <a name="geometry"></a>Geometrie

- Pouze mnohoúhelníkové modely. Žádné povrchy dělení aniBS
- Souřadnicový systém spravně
- Zásměk v transformačních matricích se nepodporuje

### <a name="textures"></a>Textury

- Mapy textur musí být vloženy do souboru FBX.
- Podporované formáty obrázků
  - Obrázky JPEG a PNG
  - Obrázky BMP (24bitová barva true RGB)
  - Obrázky TGA (24bitové RGB a 32bitové barvy RGBQ true)
- Maximální rozlišení textury 2048 × 2048
- Maximálně jedna mapová mapa, jedna normální mapa a jedna mapa datové krychle reflexe na jednu síť
- Alfa kanál v texturách tekutých pixelů způsobí zahození pixelů, pokud je hodnota nižší než 50 %.

### <a name="animation"></a>Animace

- Animace škálování/otočení/posunutí u jednotlivých objektů
- Animace s odřídkanou animací
  - Maximálně 4 vlivy na vrchol

### <a name="materials"></a>Materiály

- Podporují se materiály Od s upravitelnými parametry.
- Podporované vlastnosti materiálu pro Lambert
  - Hlavní textura (RGB + alfa test)
  - Šmoudlé barvy (RGB)
  - Ambient Color (RGB)
- Podporované vlastnosti materiálu pro Pargs
  - Hlavní textura (RGB + alfa test)
  - Šmoudlé barvy (RGB)
  - Ambient Color (RGB)
  - Zrcadlová barva (RGB)
  - Šišatost
  - Odrazivost
- Vlastní materiály se nepodporují.
- Maximálně jeden materiál na síť
- Maximálně jedna vrstva materiálu
- Maximálně 8 materiálů na soubor

### <a name="file-and-model-limitations"></a>Omezení souborů a modelů

Velikost souborů a také počet modelů, vrcholů a sítí, které mohou být v beta verzi otevřené současně, 3D prohlížeč omezení:

- Maximální velikost souboru na model: 500 MB
- Vrcholy: 600 000 kombinovaných ve všech otevřených modelech
- Meshes (Sítě): 1 600 kombinovaných ve všech otevřených modelech
- Maximálně 40 otevřených modelů najednou

## <a name="optimizing-3d-models-for-3d-viewer-beta"></a>Optimalizace 3D modelů pro 3D prohlížeč Beta

### <a name="special-considerations"></a>Zvláštní aspekty

- Vyhněte se černým materiálům nebo černým oblastem v mapách textur. Hologramy jsou tvořeny světlem, HoloLens se černě (bez světla) jako průhledné.
- Před exportem do FBX z nástroje pro vytváření se ujistěte, že je viditelná a odemknutá veškerá geometrie a že nejsou vypnuté ani šablonované žádné vrstvy obsahující geometrii. Viditelnost není respektována.
- Vyhněte se velmi velkým posunům překladu mezi uzly (například 100 000 jednotek). To může způsobit, že se model během přesunu, škálování nebo obměna modelu zatočí.

### <a name="performance-optimization"></a>Optimalizace výkonu

Při vytváření obsahu a ověřování v aplikaci 3D prohlížeč Beta na webu HoloLens při vytváření obsahu mějte na paměti výkon. 3D prohlížeč Beta vykresluje obsah v reálném čase a výkon podléhá HoloLens hardwarových funkcí.  

Existuje mnoho proměnných v 3D model, které mohou mít vliv na výkon. 3D prohlížeč beta verze zobrazí upozornění při zatížení, pokud existuje více než 150 000 vrcholů nebo více než 400 sítí. Animace mohou mít vliv na výkon jiných otevřených modelů. Existují také pevné limity pro celkové číselné modely, vrcholy a sítě, které lze otevřít současně v 3D prohlížeč Beta (viz Omezení souborů a [modelů).](#file-and-model-limitations)  

Pokud 3D model dobře nefunguje kvůli složitosti modelu, zvažte následující:

- Snížení počtu mnohoúhelníků
- Snížení počtu řídce v řídce animaci
- Jak se vyhnout samo okluzi

Oboustranné vykreslování je podporováno ve verzi 3D prohlížeč Beta, i když je ve výchozím nastavení vypnuté z důvodů výkonu. Můžete ji zapnout pomocí tlačítka **s dvojitou stranou** na **stránce Podrobnosti.** Pokud chcete mít nejlepší výkon, vyhněte se tomu, aby se v obsahu vykresloval na dvou stranách.

### <a name="validating-your-3d-model"></a>Ověření 3D model

Ověřte svůj model tak, že ho otevřete v 3D prohlížeč Beta na HoloLens. Výběrem **tlačítka Podrobnosti** zobrazíte charakteristiky a upozornění modelu na nepodporovaný obsah (pokud je k dispozici).

### <a name="rendering-3d-models-with-true-to-life-dimensions"></a>Vykreslování 3D modelů s skutečnými dimenzemi

Ve výchozím nastavení 3D prohlížeč Beta zobrazuje 3D modely v pohodlné velikosti a pozici vzhledem k uživateli. Pokud je ale důležité vykreslování 3D model s měřením hodnoty true-to-life (například při vyhodnocování modelů jídel v místnosti), může tvůrce obsahu nastavit příznak v metadatech souboru, aby zabránil změnu velikosti modelu aplikací i uživatelem.

Pokud chcete zabránit škálování modelu, přidejte logický vlastní atribut k libovolnému objektu ve scéně s názvem Microsoft_DisableScale a nastavte ho na true. 3D prohlížeč Beta pak bude respektovat informace FbxSystemUnit, které jsou v souboru FBX. Škálování na 3D prohlížeč Beta je 1 měřič na jednotku FBX.

## <a name="viewing-fbx-files-on-hololens"></a>Zobrazení souborů FBX na HoloLens

### <a name="open-an-fbx-file-from-microsoft-edge"></a>Otevřete soubor FBX z Microsoft Edge

Soubory FBX je možné otevřít přímo z webu pomocí Microsoft Edge na HoloLens.

1. V Microsoft Edge přejděte na webovou stránku obsahující soubor FBX, který chcete zobrazit.
1. Vyberte soubor, který chcete stáhnout.
1. Po dokončení stahování vyberte  tlačítko Otevřít v Microsoft Edge a otevřete soubor v 3D prohlížeč Beta.

Stažený soubor bude později přístupný a znovu otevřen pomocí položky Ke stažení v Microsoft Edge. Pokud chcete uložit 3D model a zajistit trvalý přístup, stáhněte si soubor do počítače a uložte ho do OneDrive účtu. soubor je pak možné otevřít z aplikace OneDrive v HoloLens.

> [!NOTE]
> Některé weby s FBX modely ke stažení je poskytují v komprimovaném formátu ZIP. program 3D Viewer beta nemůže otevřít soubory ZIP přímo. místo toho použijte počítač k extrakci souboru FBX a uložte ho do účtu OneDrive. soubor je pak možné otevřít z aplikace OneDrive v HoloLens.

### <a name="open-an-fbx-file-from-onedrive"></a>Otevřete soubor FBX z OneDrive

soubory FBX se dají otevřít z OneDrive pomocí OneDrive aplikace na HoloLens. ujistěte se, že jste nainstalovali OneDrive pomocí Microsoft Store aplikace na HoloLens a že jste už soubor FBX nahráli do OneDrive na svém počítači.

po OneDrive lze soubory FBX otevřít v HoloLens pomocí aplikace 3d Viewer Beta jedním ze dvou způsobů:

- spusťte OneDrive na HoloLens a vyberte soubor FBX, který chcete otevřít v aplikaci 3d Viewer Beta.
- Spusťte aplikaci 3D Viewer beta, klepněte na tlačítko Air a zobrazte panel nástrojů a vyberte možnost **otevřít soubor**. OneDrive se spustí, což vám umožní vybrat soubor FBX.

## <a name="troubleshooting"></a>Řešení potíží

### <a name="i-see-a-warning-when-i-open-a-3d-model"></a>Po otevření 3D model se zobrazí upozornění

Zobrazí se upozornění, pokud se pokusíte otevřít 3D model, která obsahuje funkce, které nejsou podporovány nástrojem 3D Viewer beta, nebo pokud je model příliš složitý a může být ovlivněn výkon. aplikace 3D Viewer beta bude i nadále načítat 3D model, ale může dojít k ohrožení výkonu nebo vizuální věrnosti.

Další informace najdete v tématu [podporované specifikace obsahu](#supported-content-specifications) a [Optimalizace 3D modelů pro program 3D Viewer beta](#optimizing-3d-models-for-3d-viewer-beta).

### <a name="i-see-a-warning-and-the-3d-model-doesnt-load"></a>Zobrazuje se upozornění a 3D model se nenačítá

Když prostorový Viewer beta nemůže načíst 3D model z důvodu složitosti nebo velikosti souboru nebo pokud je soubor FBX poškozený nebo neplatný, zobrazí se chybová zpráva. Chybová zpráva se zobrazí také v případě, že jste dosáhli limitu celkového počtu modelů, vrcholů nebo sítí, které mohou být otevřeny současně.  

Další informace najdete v tématech [podporované specifikace obsahu](#supported-content-specifications) a [omezení souborů a modelů](#file-and-model-limitations).

### <a name="my-3d-model-loads-but-does-not-appear-as-expected"></a>Moje 3D model načíst, ale nezobrazí se podle očekávání.

Pokud vaše 3D model v aplikaci 3D Viewer beta nevypadá podle očekávání, klepněte na tlačítko Air, aby se panel nástrojů zobrazoval a pak vyberte **Podrobnosti**. Aspekty souboru, které nejsou podporovány aplikací 3D Viewer beta, budou zvýrazněny jako upozornění.

Nejběžnější problém, který se může zobrazit, chybí textury, pravděpodobně proto, že nejsou vloženy do souboru FBX. V takovém případě se model zobrazí jako bílý. Tento problém lze vyřešit tak, že v procesu vytváření exportujete z nástroje pro tvorbu do FBX s vybranou možností vložit textury.

Další informace najdete v tématu [podporované specifikace obsahu](#supported-content-specifications) a [Optimalizace 3D modelů pro program 3D Viewer beta](#optimizing-3d-models-for-3d-viewer-beta).

### <a name="i-experience-performance-drops-while-viewing-my-3d-model"></a>Při prohlížení mých 3D model dochází k poklesu výkonu

Výkon při načítání a zobrazování 3D model může být ovlivněn složitou složitostí modelu, počtu současně otevřených modelů nebo počtem modelů s aktivními animacemi.

Další informace najdete v tématu [Optimalizace 3D modelů pro 3D Viewer beta](#optimizing-3d-models-for-3d-viewer-beta) a [omezení souborů a modelů](#file-and-model-limitations).

### <a name="when-i-open-an-fbx-file-on-hololens-it-doesnt-open-in-3d-viewer-beta"></a>když otevřu soubor FBX na HoloLens, neotevře se v programu 3d Viewer Beta

Při instalaci aplikace 3D Viewer beta je automaticky přidružena k příponě souboru. FBX.

pokud se pokusíte otevřít soubor FBX a zobrazit dialogové okno, které vás přesměruje na Microsoft Store, aktuálně nemáte aplikaci přidruženou k příponě souboru. FBX v HoloLens.

Ověřte, zda je nainstalován nástroj 3D Viewer beta. pokud není nainstalovaný, stáhněte si ho z Microsoft Store HoloLens.

Pokud je už nainstalovaný prostorový Viewer beta, spusťte 3D Viewer beta a pak zkuste soubor otevřít znovu. Pokud potíže potrvají, odinstalujte a znovu nainstalujte 3D Viewer beta. Tím se přípona souboru. FBX znovu přidruží k beta verzi aplikace 3D Viewer.

Pokud se při pokusu o otevření souboru FBX otevře jiná aplikace než 3D Viewer beta, tato aplikace se nejspíš nainstalovala po verzi 3D Viewer beta a převzala se přes přidružení s příponou souboru. FBX. Pokud dáváte přednost aplikaci 3D Viewer beta, aby byla přidružena k příponě souboru. FBX, odinstalujte a znovu nainstalujte 3D Viewer beta.

### <a name="the-open-file-button-in-3d-viewer-beta-doesnt-launch-an-app"></a>Tlačítko otevřít soubor v aplikaci 3D Viewer beta nespustí aplikaci

Tlačítkem **otevřít soubor** otevřete aplikaci přidruženou k funkci výběr souboru na HoloLens. je-li nainstalován OneDrive, tlačítko **otevřít soubor** by mělo OneDrive spustit. pokud ale v tuto chvíli není k dispozici žádná aplikace přidružená k funkci pro výběr souboru nainstalovanou na HoloLens, budete přesměrováni na Microsoft Store.

pokud tlačítko **otevřít soubor** spustí jinou aplikaci než OneDrive, tato aplikace se nejspíš nainstalovala po OneDrive a převzala se přes přidružení pomocí funkce výběr souboru. pokud dáváte přednost OneDrive spustit při výběru tlačítka **otevřít soubor** v aplikaci 3d Viewer Beta, odinstalujte a znovu nainstalujte OneDrive.

Pokud není tlačítko **otevřít soubor** aktivní, je možné, že jste dosáhli limitu modelů, které lze v programu 3D Viewer beta otevřít najednou. Pokud máte modely 40 otevřené v aplikaci 3D Viewer beta, budete je muset zavřít předtím, než budete moct otevřít další modely.

## <a name="additional-resources"></a>Další zdroje informací

- [Fóra podpory](http://forums.hololens.com/categories/3d-viewer-beta) – jenom pro účely archivace. Toto fórum už není aktivní.
- [Oznámení třetích stran](https://www.microsoft.com/{lang-locale}/legal/products)
