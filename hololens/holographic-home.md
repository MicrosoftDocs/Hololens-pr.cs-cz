---
title: použití domovské stránky nabídka Start a smíšené reality
description: naučte se používat nabídku start, spravovat aplikace a přistupovat k nim a v zařízeních HoloLens navigovat domácí realitu.
ms.assetid: 742bc126-7996-4f3a-abb2-cf345dff730c
ms.date: 08/07/2019
keywords: HoloLens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f9a6f1692df05e5fd8faec3da07cc85f7c6a32c7
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126035993"
---
# <a name="use-the-start-menu-and-mixed-reality-home"></a>použití domovské stránky nabídka Start a smíšené reality

stejně jako Windows prostředí pro počítač se spouští s plochou, Windows holografický start se smíšeným domovem reality.  pomocí nabídka Start můžete otevřít a umístit okna aplikací, moderní spouštěče aplikací a 3d obsah na domácí realitě a jejich umístění ve fyzickém prostoru bude zapamatovatelné.

## <a name="use-the-start-menu"></a>použití nabídka Start

nabídka Start v HoloLens je místo, kde budete otevírat aplikace, informace o důležitých stavech a přístup k nástrojům jako fotoaparát.

ať už jste v HoloLens, můžete nabídka Start vždy otevřít pomocí **gesta Start**.  v HoloLens (1. generace) je gesto Start [bloom](https://support.microsoft.com/help/12644/hololens-use-gestures). v HoloLens 2 se [spustí gesto pro spuštění](hololens2-basic-usage.md#start-gesture) , ve kterém se zobrazí ikona start, která se zobrazuje na zápěstí.  k otevření nabídka Start můžete také použít svůj hlas vyslovením příkazu "přejít na začátek".

> [!TIP]
> když je nabídka Start otevřené, zavřete ho pomocí gesta Start, nebo se podívejte na nabídka Start a řekněte "close".

v horní části nabídka Start uvidíte indikátory stavu pro Wi-Fi, baterii, svazek a hodiny. v HoloLens 2 existuje také indikátor poslouchání, který ukazuje, zda je zařízení zapnuté rozpoznávání řeči a naslouchá hlasovým příkazům. V dolní části najdete tlačítka pro **fotografii** a **videa** , která vám umožní pořizovat fotky a videozáznamy.  k dispozici je také tlačítko **Připojení** , které vám umožní promítnout, co vidíte na jiném zařízení pomocí Miracast.

### <a name="find-apps-on-start-menu"></a>hledání aplikací na nabídka Start

nabídka Start má seznam **připnutých aplikací** a seznam **všech aplikací** .

- Seznam **připnutých aplikací** zobrazuje připnuté aplikace. Můžete přidávat a odebírat aplikace ze seznamu **připnutých aplikací** pomocí kontextové nabídky, která se zobrazí při **výběru a blokování** na dlaždici aplikace.

- Seznam **všechny aplikace** zobrazuje všechny aplikace, které jsou v zařízení nainstalované.  Do seznamu se dostanete tak, že vyberete tlačítko **všechny aplikace** na pravé straně nabídky **Start** .

v seznamech aplikací použijte tlačítka **page up** a **page down** na pravé straně nabídka Start ke stránkám přes všechny aplikace v seznamu.  Oba seznamy aplikací se automaticky otevřou na stránce, která se naposledy používala během relace zařízení.

> [!TIP]
> v HoloLens 2 můžete v seznamech aplikací přímo přejít pomocí prstu pro index. Stačí se dotknout seznamu s tipem prstem a přetáhnout nahoru nebo dolů.

### <a name="open-apps-from-start-menu"></a>otevřít aplikace z nabídka Start

pokud chcete aplikaci otevřít z nabídka Start, stačí **vybrat** **dlaždici aplikace**. Můžete také vyslovit název aplikace a otevřít ji.

při otevření aplikace z nabídka Start dojde k jednomu z následujících postupů v závislosti na tom, jak je aplikace navržena:

- Je umístěno **okno aplikace** . Aplikace se pak načte do okna a můžete ji použít jako dotykovou obrazovku.
- Pro moderní aplikaci se umístí **spouštěč 3D aplikace** . Pro otevření moderní aplikace je nutné **Vybrat** spouštěč.
- Je umístěno okno aplikace, které funguje jako **spouštěč** pro moderní aplikace. Moderní aplikace bude pokračovat v automatickém spuštění.

Okna aplikace a spuštění aplikací umístěné na domácím světě realit budou zůstat v ne, dokud se nerozhodnete je odebrat.  poskytují vám pohodlný zástupce v celém světě, aby mohli používat tato okna aplikací, nebo spouštět moderní aplikace bez nutnosti jejich opětovného otevření z nabídka Start. 

> [!NOTE]
>Podobně jako na telefonu se systémové prostředky spravují automaticky na HoloLens.  Když například otevřete novou moderní aplikaci, všechny ostatní běžící aplikace se okamžitě stanou neaktivní. Aby bylo možné uvolnit systémové prostředky, není nutné odebírat okna aplikací a spouštěcích programů na hybridním domácím realitě. 

## <a name="using-apps-on-hololens"></a>Používání aplikací v HoloLens

aplikace v HoloLens můžou používat zobrazení okna aplikace nebo moderní zobrazení. V zobrazení okna aplikace aplikace jednoduše zobrazuje obsah v rámci okna. Díky modernímu zobrazení vám aplikace přebírá od smíšené Realty domů, kde si pak může zobrazit obsah ve fyzickém prostředí od sebe. Aplikace se také můžou rozhodnout použít obě zobrazení.

### <a name="use-app-windows"></a>Použití oken aplikací

v HoloLens (1. generace) jsou okna aplikací umístěná a používaná v hybridním domácím realitě, kde je můžete [přesouvat, měnit jejich velikost a otáčet](hololens1-basic-usage.md#move-resize-and-rotate-apps) je, jak budete chtít. kromě používání oken aplikací pomocí pohledu a gesta je můžete také použít s Bluetooth připojenou myší a klávesnicí.

na HoloLens 2, kromě používání oken aplikací na domovské stránce hybridní reality, můžete také použít jedno okno aplikace v době uvnitř moderní aplikace. Můžete také umístit okno aplikace do režimu **povedené** akce, kde zůstane před tím, než začnete. Když otevřete okno aplikace, které je uvnitř moderní aplikace, otevře se v režimu **pořídit** automaticky. Okna aplikací můžete [přesouvat, měnit jejich velikost a střídat](hololens2-basic-usage.md#move-resize-and-rotate-holograms) je přímo na domovské stránce hybridní reality i uvnitř moderní aplikace.

> [!NOTE]
>
> - Až tři okna aplikací můžou být aktivní doma ve smíšené realitě. Můžete otevřít více, ale aktivní budou jenom tři.
> - Pokud není okno aplikace aktivní, zobrazí se v porovnání s aktivním oknem obsah, který bude tmavší.  Některé budou jednoduše zobrazovat ikonu aplikace namísto jakéhokoli obsahu.  Pokud chcete aktivovat neaktivní okno, stačí ho **Vybrat** .
> - každá otevřená aplikace může mít jedno aktivní okno v čase, s výjimkou Microsoft Edge, která může obsahovat až tři.

### <a name="close-apps"></a>Zavřít aplikace

Chcete-li zavřít aplikaci, která používá okno aplikace, jednoduše zavřete okno aplikace s tlačítkem **Zavřít** v záhlaví.  Můžete se také podívat na okno a vyslovit "Zavřít".

pokud chcete aplikaci, která používá moderní zobrazení, ukončit, použijte gesto Start, aby se **nabídka Start**, a pak vyberte tlačítko **domů ve smíšené realitě** .

pokud je moderní aplikace v nefunkčním stavu a musíte ji restartovat, můžete zajistit, aby se aplikace nejdřív ukončila tím, že ukončí její spouštěč na domovské stránce hybridní reality a pak ji spouští z nabídka Start.

### <a name="default-app-picker"></a>Výchozí výběr aplikace

při [Windows holografické 21H1 verze](hololens-release-notes.md#windows-holographic-version-21h1), když aktivujete hypertextový odkaz nebo otevřete typ souboru s více než jednou nainstalovanou aplikací, která ho podporuje, se otevře nové okno s výzvou, abyste vybrali, kterou aplikaci by měl zpracovat soubor nebo typ odkazu. V tomto okně můžete také zvolit, aby vybraná aplikace zpracovala soubor nebo typ odkazu "jednou" nebo "Always".

![Okno pro výběr aplikace](images/default-app-picker.png)

pokud zvolíte "vždycky", ale později chcete změnit, která aplikace zpracovává určitý typ souboru nebo propojení, můžete obnovit uložené výchozí hodnoty v **Nastavení > aplikacích**. Posuňte se do dolní části stránky a v části výchozí aplikace pro typy souborů nebo výchozí aplikace pro typy odkazů vyberte tlačítko **Vymazat** . Na rozdíl od podobných nastavení na stolních počítačích nemůžete resetovat jednotlivé výchozí hodnoty typu souboru.

### <a name="per-app-volume-control"></a>Řízení hlasitosti na aplikaci

pomocí [Windows holografické verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1)můžou uživatelé ručně upravovat úroveň hlasitosti každé aplikace. To uživatelům umožňuje lépe se zaměřit na aplikace, které potřebují, nebo lépe slyšet při používání více aplikací. Například nutnost vypnout objem jedné aplikace a zavolat jiné osobě na vzdálenou pomoc v jiném.

pokud chcete nastavit hlasitost jednotlivé aplikace, přejděte na **Nastavení**  ->  **systémový**  ->  **zvuk** a v části pokročilé možnosti zvuku vyberte **předvolby aplikace a hlasitost zařízení**.

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

## <a name="related-info"></a>Související informace

[Hledání, instalace a odinstalace aplikací z Microsoft Store](holographic-store-apps.md)
