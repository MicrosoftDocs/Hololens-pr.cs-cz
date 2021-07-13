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
# <a name="using-3d-viewer-beta-on-hololens-1st-gen"></a>Použití 3D prohlížeč Beta na HoloLens (1. generace)

3D prohlížeč Beta umožňuje zobrazit 3D modely na HoloLens (1. generace). Podporované soubory .fbx *můžete* otevřít a zobrazit z Microsoft Edge, OneDrive a dalších aplikací.

>[!NOTE]
>Tento článek se týká imerzivní aplikace Unity **3D prohlížeč Beta,** která podporuje soubory .fbx a je k dispozici pouze HoloLens (1. generace). Předinstalovaná **aplikace** 3D prohlížeč ve verzi HoloLens 2 podporuje otevírání vlastních 3D modelů .glb [](/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) na domovské stránce hybridní reality (další podrobnosti najdete v tématu Přehled požadavků na prostředky.

>[!IMPORTANT]
>Přestože 3D prohlížeč beta verze může zůstat dostupná v Microsoft Store pro HoloLens (1. generace), už není v aktivním vývoji a už se nepodporuje.

Pokud máte potíže s otevřením 3D model ve verzi 3D prohlížeč Beta nebo se některé funkce vašeho 3D model nepodporují, podívejte se níže na specifikace [podporovaného](#supported-content-specifications) obsahu.

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
  - Obrázky TGA (24bitové a 32bitové barvy RGBQ true)
- Maximální rozlišení textury 2048 × 2048
- Maximálně jedna mapová mapa, jedna normální mapa a jedna mapa datové krychle reflexe na jednu síť
- Alfa kanál v texturách tekutých pixelů způsobí zahození pixelů, pokud je hodnota nižší než 50 %.

### <a name="animation"></a>Animace

- Animace škálování,otočení/posunutí u jednotlivých objektů
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

Velikost souborů a počet modelů, vrcholů a sítí, které mohou být v beta verzi otevřené současně, 3D prohlížeč pevných prvků:

- Maximální velikost souboru na model: 500 MB
- Vrcholy: 600 000 kombinovaných ve všech otevřených modelech
- Meshes (Sítě): 1 600 kombinovaných ve všech otevřených modelech
- Maximálně 40 otevřených modelů najednou

## <a name="optimizing-3d-models-for-3d-viewer-beta"></a>Optimalizace 3D modelů pro 3D prohlížeč Beta

### <a name="special-considerations"></a>Zvláštní aspekty

- Vyhněte se černým materiálům nebo černým oblastem v mapách textur. Hologramy jsou tvořeny světlem, HoloLens se černě (bez světla) jako průhledné.
- Před exportem do FBX z nástroje pro vytváření se ujistěte, že je viditelná a odemknutá veškerá geometrie a že nejsou vypnuté ani šablonované žádné vrstvy obsahující geometrii. Viditelnost není respektována.
- Vyhněte se velmi velkým posunům překladu mezi uzly (například 100 000 jednotek). To může způsobit, že se model během přesunu, škálování nebo otočení bude zachytovat.

### <a name="performance-optimization"></a>Optimalizace výkonu

Při vytváření obsahu mějte na paměti výkon a ověřte 3D prohlížeč beta verzi HoloLens během procesu vytváření obsahu, aby se vám to nejlépe posouvání. 3D prohlížeč Beta vykresluje obsah v reálném čase a výkon podléhá HoloLens hardwarových funkcí.  

Existuje mnoho proměnných v 3D model, které mohou mít vliv na výkon. 3D prohlížeč beta verze zobrazí upozornění při zatížení, pokud existuje více než 150 000 vrcholů nebo více než 400 sítí. Animace mohou mít vliv na výkon jiných otevřených modelů. Existují také pevné limity pro celkové číselné modely, vrcholy a sítě, které lze otevřít současně v 3D prohlížeč Beta (viz Omezení souborů a [modelů).](#file-and-model-limitations)  

Pokud 3D model dobře nefunguje kvůli složitosti modelu, zvažte následující:

- Snížení počtu mnohoúhelníků
- Snížení počtu řídce v řídce animaci
- Jak se vyhnout samo okluzi

Vykreslování na dvou stranách se podporuje 3D prohlížeč Beta, i když je ve výchozím nastavení vypnuté z důvodů výkonu. Můžete ji zapnout pomocí tlačítka **s dvojitou stranou** na **stránce Podrobnosti.** Pokud chcete mít nejlepší výkon, vyhněte se tomu, aby se v obsahu vykresloval na dvou stranách.

### <a name="validating-your-3d-model"></a>Ověření 3D model

Ověřte model tak, že ho otevřete v 3D prohlížeč Beta na HoloLens. Výběrem **tlačítka Podrobnosti** zobrazíte charakteristiky a upozornění modelu na nepodporovaný obsah (pokud je k dispozici).

### <a name="rendering-3d-models-with-true-to-life-dimensions"></a>Vykreslování 3D modelů s skutečnými dimenzemi

Ve výchozím nastavení 3D prohlížeč Beta zobrazuje 3D modely v pohodlné velikosti a pozici vzhledem k uživateli. Pokud je ale důležité vykreslení 3D model s měřením hodnoty true-to-life (například při vyhodnocování modelů jídel v místnosti), může tvůrce obsahu nastavit příznak v metadatech souboru, aby zabránil změnu velikosti modelu aplikací i uživatelem.

Pokud chcete zabránit škálování modelu, přidejte logický vlastní atribut k libovolnému objektu ve scéně s názvem Microsoft_DisableScale a nastavte ho na true. 3D prohlížeč Beta pak bude respektovat informace FbxSystemUnit, které jsou v souboru FBX. Škálování na 3D prohlížeč Beta je 1 měřič na jednotku FBX.

## <a name="viewing-fbx-files-on-hololens"></a>Zobrazení souborů FBX na HoloLens

### <a name="open-an-fbx-file-from-microsoft-edge"></a>Otevřete soubor FBX z Microsoft Edge

Soubory FBX je možné otevřít přímo z webu pomocí Microsoft Edge na HoloLens.

1. V Microsoft Edge přejděte na webovou stránku obsahující soubor FBX, který chcete zobrazit.
1. Vyberte soubor, který chcete stáhnout.
1. Po dokončení stahování vyberte  tlačítko Otevřít v Microsoft Edge a otevřete soubor ve verzi 3D prohlížeč Beta.

Stažený soubor můžete otevřít a znovu otevřít později pomocí položky Ke stažení v Microsoft Edge. Pokud chcete uložit 3D model a zajistit trvalý přístup, stáhněte si soubor do počítače a uložte ho do OneDrive účtu. Soubor pak můžete otevřít z aplikace OneDrive na HoloLens.

> [!NOTE]
> Některé weby s modely FBX ke stažení je poskytují v komprimovaném formátu ZIP. 3D prohlížeč Beta nemůže otevřít soubory ZIP přímo. Místo toho pomocí počítače extrahujte soubor FBX a uložte ho do OneDrive účtu. Soubor pak můžete otevřít z aplikace OneDrive na HoloLens.

### <a name="open-an-fbx-file-from-onedrive"></a>Otevřete soubor FBX z OneDrive

Soubory FBX je možné otevřít OneDrive pomocí OneDrive aplikace na HoloLens. Ujistěte se, že jste OneDrive Microsoft Store aplikaci na HoloLens a že jste soubor FBX už nahráli do OneDrive počítače.

Jakmile jsou OneDrive, můžete soubory FBX otevřít na HoloLens pomocí 3D prohlížeč Beta jedním ze dvou způsobů:

- Spusťte OneDrive na HoloLens a výběrem souboru FBX ho otevřete v 3D prohlížeč Beta.
- Spusťte 3D prohlížeč Beta, klepnutím ve vzduchu zobrazte panel nástrojů a vyberte **Otevřít soubor.** OneDrive se spustí , což vám umožní vybrat soubor FBX.

## <a name="troubleshooting"></a>Poradce při potížích

### <a name="i-see-a-warning-when-i-open-a-3d-model"></a>Při otevření aplikace se 3D model

Pokud se pokusíte otevřít 3D model obsahující funkce, které 3D prohlížeč Beta nepodporuje, nebo pokud je model příliš složitý a může to mít vliv na výkon, zobrazí se upozornění. 3D prohlížeč Beta bude nadále načítat 3D model, ale může dojít k ohrožení výkonu nebo vizuální věrnosti.

Další informace najdete v tématu [Podporované specifikace obsahu](#supported-content-specifications) a Optimalizace [3D modelů pro 3D prohlížeč Beta.](#optimizing-3d-models-for-3d-viewer-beta)

### <a name="i-see-a-warning-and-the-3d-model-doesnt-load"></a>Zobrazí se upozornění a 3D model se nenačte

Chybová zpráva se zobrazí, když 3D prohlížeč beta verze nemůže načíst 3D model kvůli složitosti nebo velikosti souboru nebo pokud je soubor FBX poškozený nebo neplatný. Pokud jste dosáhli limitu celkového počtu modelů, vrcholů nebo sítí, které mohou být současně otevřené, zobrazí se také chybová zpráva.  

Další informace najdete v tématu [Podporované specifikace obsahu](#supported-content-specifications) a Omezení souborů a [modelů.](#file-and-model-limitations)

### <a name="my-3d-model-loads-but-does-not-appear-as-expected"></a>Moje 3D model se načítá, ale nezobrazuje se podle očekávání

Pokud vaše 3D model ve verzi beta 3D prohlížeč očekávaným způsobem, klepnutím ve vzduchu zobrazte panel nástrojů a pak vyberte **Podrobnosti.** Aspekty souboru, které nejsou podporované 3D prohlížeč beta verze, se zvýrazní jako upozornění.

Nejběžnějším problémem, který se může zobrazit, jsou chybějící textury, pravděpodobně proto, že nejsou vložené do souboru FBX. V tomto případě se model zobrazí jako bílý. Tento problém je možné vyřešit při vytváření exportem z nástroje pro vytváření do FBX s vybranou možností textury vložení.

Další informace najdete v tématu [Podporované specifikace obsahu](#supported-content-specifications) a Optimalizace [3D modelů pro 3D prohlížeč Beta.](#optimizing-3d-models-for-3d-viewer-beta)

### <a name="i-experience-performance-drops-while-viewing-my-3d-model"></a>Při prohlížení obrazovky u mě docházet k poklesu výkonu 3D model

Výkon při načítání a zobrazování 3D model může ovlivnit složitost modelu, počet současně otevřených modelů nebo počet modelů s aktivními animacemi.

Další informace najdete v tématu [Optimalizace 3D modelů pro 3D prohlížeč beta verze](#optimizing-3d-models-for-3d-viewer-beta) a omezení souborů a [modelů.](#file-and-model-limitations)

### <a name="when-i-open-an-fbx-file-on-hololens-it-doesnt-open-in-3d-viewer-beta"></a>Když otevřete soubor FBX na HoloLens, neotevře se ve verzi 3D prohlížeč Beta.

3D prohlížeč beta verze je automaticky přidružena k příponě souboru .fbx při instalaci.

Pokud se pokusíte otevřít soubor FBX a zobrazí se dialogové okno, které vás přesměruje na Microsoft Store, v současné době nemáte k příponě souboru .fbx přidruženou HoloLens.

Ověřte, 3D prohlížeč je nainstalovaná beta verze. Pokud není nainstalovaný, stáhněte si ho z Microsoft Store na HoloLens.

Pokud 3D prohlížeč nainstalovaná beta verze, spusťte 3D prohlížeč Beta a pak zkuste soubor otevřít znovu. Pokud problém přetrvává, odinstalujte a znovu nainstalujte 3D prohlížeč Beta. Tím se znovu přidruží přípona souboru .fbx k 3D prohlížeč Beta.

Pokud se pokusíte otevřít soubor FBX, otevře se jiná aplikace než 3D prohlížeč Beta, tato aplikace se pravděpodobně nainstalovala po 3D prohlížeč Beta a převzala přidružení k příponě souboru .fbx. Pokud dáváte přednost 3D prohlížeč beta verzi, aby byla přidružená k příponě souboru .fbx, odinstalujte a znovu 3D prohlížeč Beta.

### <a name="the-open-file-button-in-3d-viewer-beta-doesnt-launch-an-app"></a>Tlačítko Otevřít soubor v 3D prohlížeč Beta aplikaci nespuštěné

Tlačítko **Otevřít soubor** otevře aplikaci přidruženou k funkci výběru souborů na HoloLens. Pokud OneDrive nainstalovaná, mělo **by se tlačítko Otevřít soubor** spustit OneDrive. Pokud ale v tuto chvíli není k funkci výběru souborů nainstalovaná žádná aplikace, HoloLens, budete přesměrováni na Microsoft Store.

Pokud **tlačítko Otevřít soubor** spustí jinou aplikaci než OneDrive, tato aplikace se pravděpodobně nainstalovala po OneDrive a převzala přidružení k funkci výběru souborů. Pokud dáváte přednost OneDrive spustit při výběru tlačítka **Otevřít** soubor v 3D prohlížeč Beta, odinstalujte a znovu nainstalujte OneDrive.

Pokud **tlačítko Otevřít soubor** není aktivní, je možné, že jste dosáhli limitu modelů, které je možné otevřít v 3D prohlížeč Beta najednou. Pokud máte v beta verzi 3D prohlížeč 40 modelů, budete muset některé modely zavřít, abyste mohli otevřít další modely.

## <a name="additional-resources"></a>Další zdroje informací

- [Fóra podpory](http://forums.hololens.com/categories/3d-viewer-beta) – jenom pro archivní účely. Toto fórum už není aktivní.
- [Oznámení třetích stran](https://www.microsoft.com/{lang-locale}/legal/products)
