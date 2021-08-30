---
title: Použití domova nabídka Start hybridní reality
description: Naučte se používat nabídku Start, spravovat aplikace a přistupovat k aplikacím a procházet domovskou stránku hybridní reality v HoloLens zařízení.
ms.assetid: 742bc126-7996-4f3a-abb2-cf345dff730c
ms.date: 08/07/2019
keywords: hololens
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
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189167"
---
# <a name="use-the-start-menu-and-mixed-reality-home"></a>Použití domova nabídka Start hybridní reality

Stejně jako Windows počítače začíná desktopem, Windows Holographic na domovském serveru hybridní reality.  Pomocí nabídka Start můžete otevřít a umístit okna aplikací, spouštěče imerzivních aplikací a 3D obsah v domácnosti hybridní reality a jejich umístění ve fyzickém prostoru se zapamatuje.

## <a name="use-the-start-menu"></a>Použití nabídka Start

Na nabídka Start HoloLens můžete otevírat aplikace, zobrazit důležité stavové informace a přistupovat k nástrojům, jako je fotoaparát.

Ať už jste kdekoli HoloLens, můžete kdykoli otevřít nabídka Start pomocí gesta **Start**.  V HoloLens (1. generace) se gesto Start [rozkvétá](https://support.microsoft.com/help/12644/hololens-use-gestures). Na HoloLens 2 gesto [Spustit je](hololens2-basic-usage.md#start-gesture) klepnout na ikonu Start, která se zobrazí na vašem zařízení.  Můžete také otevřít nabídka Start pomocí hlasu tak, že řeknete "Přejít na začátek".

> [!TIP]
> Když je nabídka Start otevřený, pomocí gesta Spustit ho zavřete nebo se podívejte na nabídka Start a řekněte "Zavřít".

V horní části nabídka Start se zobrazí indikátory stavu pro Wi-Fi, baterie, svazek a hodiny. Na HoloLens 2 je také indikátor naslouchání, který ukazuje, jestli je zařízení povolené a jestli naslouchá hlasovým příkazům. V dolní části najdete tlačítka **Photo (Fotografie)** a **Video** (Video), která vám umožní posout fotografie a videozáznamy.  K dispozici je **také tlačítko Připojení,** které umožňuje promítovat to, co vidíte, do jiného zařízení pomocí Miracast.

### <a name="find-apps-on-start-menu"></a>Hledání aplikací na nabídka Start

V nabídka Start seznam **Připnutých** aplikací a seznam **Všechny aplikace** aplikací.

- V **seznamu Připnuté** aplikace se zobrazí připnuté aplikace. Aplikace můžete přidávat a odebírat ze seznamu **Připnuté** aplikace pomocí místní nabídky, která se zobrazí, když vyberete a **podržíte** dlaždici aplikace.

- V **Všechny aplikace** se zobrazí všechny aplikace, které jsou na zařízení nainstalované.  Výběrem **Všechny aplikace** na pravé straně nabídky **Start** se dostanete do seznamu.

V obou seznamech aplikací můžete pomocí tlačítek Page **up** (Stránka nahoru) a **Page down** (O stránku dolů) na pravé straně nabídka Start procházet všechny aplikace v seznamu.  Oba seznamy aplikací se automaticky otevřou na stránce, která se naposledy použila během relace zařízení.

> [!TIP]
> Na HoloLens 2 můžete seznamy aplikací posouvat přímo pomocí ukazováčku. Stačí, když se do seznamu táhnete prstem a přetáhnete ho nahoru nebo dolů.

### <a name="open-apps-from-start-menu"></a>Otevření aplikací z nabídka Start

Pokud chcete otevřít aplikaci z nabídka Start, stačí **vybrat** **dlaždici aplikace.** Můžete také říci název aplikace, kterou chcete otevřít.

Když aplikaci otevřete z webu nabídka Start, stane se v závislosti na tom, jak je aplikace navržená, jedna z následujících akcí:

- Je **umístěno okno** aplikace. Aplikace se pak načte do okna a můžete ji použít jako dotykovou obrazovku.
- Je **umístěný spouštěč 3D** aplikací pro imerzivní aplikaci. Pak musíte vybrat **spouštěč** a otevřít tak imerzivní aplikaci.
- Umístí se okno aplikace, které funguje jako **spouštěč** pro imerzivní aplikaci. Imerzivní aplikace se bude spouštět automaticky.

Okna aplikací a spouštěče aplikací umístěné na domovském serveru hybridní reality zůstanou, dokud se nerozhodníte je odebrat.  Poskytují pohodlnou klávesovou zkratku pro používání těchto oken aplikace nebo spouštění imerzivních aplikací, aniž byste je museli znovu otevírat z nabídka Start. 

> [!NOTE]
>Stejně jako na telefonu se systémové prostředky spravují automaticky na HoloLens.  Když například otevřete novou imerzivní aplikaci, všechny ostatní spuštěné aplikace se okamžitě stanou neaktivními. Není nutné odebírat okna aplikací a spouštěče v domovské službě hybridní reality, aby se uchytly systémové prostředky. 

## <a name="using-apps-on-hololens"></a>Používání aplikací v HoloLens

Aplikace v HoloLens mohou používat zobrazení okna aplikace nebo imerzivní zobrazení. V zobrazení okna aplikace se v aplikaci jednoduše zobrazuje její obsah v okně. Díky imerzivnímu zobrazení vás aplikace odvede ze smíšeného domova, kde pak může zobrazit svůj obsah ve fyzickém prostředí kolem vás. Aplikace se také mohou rozhodnout použít obě zobrazení.

### <a name="use-app-windows"></a>Použití oken aplikací

Na HoloLens (1. generace) se okna aplikací umístí a používají v domovském prostředí hybridní reality, kde je můžete [přesouvat,](hololens1-basic-usage.md#move-resize-and-rotate-apps) měnit jejich velikost a obměna podle vaší velikosti. Kromě používání oken aplikací s pohledem a gesty je můžete použít také s Bluetooth myši a klávesnice.

Na HoloLens 2 můžete kromě použití oken aplikací v domovském prostředí hybridní reality také v imerzivní aplikaci používat současně jedno okno aplikace. Okno aplikace můžete také umístit do **režimu Sledovat** mě, kde bude při obchádování před váma. Když v imerzivní aplikaci otevřete okno aplikace, otevře se automaticky v **režimu** Sledovat mě. Okna aplikace [můžete přesouvat, měnit](hololens2-basic-usage.md#move-resize-and-rotate-holograms) jejich velikost a obměna přímo pomocí rukou v domácnosti hybridní reality i v imerzivní aplikaci.

> [!NOTE]
>
> - V domovském prostředí hybridní reality mohou být najednou aktivní až tři okna aplikací. Můžete otevřít více, ale aktivní zůstanou jenom tři.
> - Pokud okno aplikace není aktivní, zobrazí obsah, který vypadá v porovnání s aktivním oknem ztmavě.  Některé místo jakéhokoli obsahu jednoduše zobrazí ikonu aplikace.  Pokud chcete aktivovat neaktivní okno, stačí **ho** vybrat.
> - Každá otevřená aplikace může mít současně jedno aktivní okno s výjimkou Microsoft Edge, které může mít až tři.

### <a name="close-apps"></a>Zavření aplikací

Pokud chcete zavřít aplikaci, která používá okno aplikace,  jednoduše zavřete okno aplikace tlačítkem Zavřít v záhlaví.  Můžete se také podívat na okno a říci Zavřít.

Pokud chcete ukončit aplikaci, která používá imerzivní zobrazení, pomocí gesta Start zobrazte nabídka Start a pak vyberte tlačítko **domů Hybridní** realita. 

Pokud je imerzivní aplikace v poškozeném stavu a potřebujete ji restartovat, můžete se nejdřív ujistit, že je zcela vypnutá. Zavřete spouštěč v domovském prostředí hybridní reality a pak ji spustíte z nabídka Start.

### <a name="default-app-picker"></a>Výchozí výběr aplikace

Když [u Windows Holographic verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1)aktivujete hypertextový odkaz nebo otevřete typ souboru s více nainstalovanými aplikacemi, které ji podporují, zobrazí se nové okno s výzvou k výběru toho, která nainstalovaná aplikace má soubor nebo typ odkazu zpracovat. V tomto okně se také můžete rozhodnout, že vybraná aplikace zřídí soubor nebo typ odkazu "Jednou" nebo "Vždy".

![Okno pro výběr aplikace.](images/default-app-picker.png)

Pokud zvolíte Možnost Vždy, ale později chcete změnit, která aplikace zpracovává konkrétní soubor nebo typ odkazu, můžete uložené výchozí hodnoty resetovat v Nastavení > **Apps.** Posuňte se do dolní části stránky a vyberte tlačítko **Vymazat** v části Výchozí aplikace pro typy souborů a/nebo Výchozí aplikace pro typy odkazů. Na rozdíl od podobného nastavení na stolních počítačích nemůžete resetovat výchozí nastavení jednotlivých typů souborů.

### <a name="per-app-volume-control"></a>Řízení objemu na aplikaci

Díky [Windows Holographic verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1)uživatel může ručně upravit úroveň svazku každé aplikace. Díky tomu se uživatelé mohou lépe soustředit na aplikace, které potřebují, nebo lépe slyšet při používání více aplikací. Například když potřebujete vypnout objem jedné aplikace a volat jinou osobu kvůli vzdálené pomoci v jiné.

Pokud chcete nastavit svazek jednotlivé aplikace, přejděte na **Nastavení** Zvuk systému a v části Pokročilé možnosti zvuku vyberte Nastavení hlasitosti aplikace a  ->    ->   **předvoleb zařízení.**

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

## <a name="related-info"></a>Související informace

[Vyhledání, instalace a odinstalace aplikací z Microsoft Store](holographic-store-apps.md)
