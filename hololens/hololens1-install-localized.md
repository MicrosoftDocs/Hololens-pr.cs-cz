---
title: Instalace lokalizovaných verzí HoloLens
description: Zjistěte, jak nainstalovat lokalizované verze HoloLens (1. generace), včetně čínštiny a japonštiny.
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
ms.openlocfilehash: fe29e4ed611f86764f0db576b1a8794fa0ceec3047cadd26f502209faadea8b0
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661822"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a>Instalace lokalizovaných verzí HoloLens (1. generace)

Pokud chcete přepnout na čínštinu nebo japonštinu služby HoloLens, budete muset pomocí nástroje WDRT (Windows Device Recovery Tool) stáhnout sestavení pro jazyk na počítači a pak ho nainstalovat do HoloLens.

> [!IMPORTANT]
> Pomocí nástroje WDRT nainstalujte sestavení pro čínštinu nebo japonštinu HoloLens odstraní existující data, jako jsou osobní soubory a nastavení, z vaší HoloLens. 

1. Na svém počítači stáhněte a [nainstalujte Windows Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379)
1. Stáhněte si balíček pro jazyk, který chcete mít na počítači:  [Zjednodušená čínština](https://aka.ms/hololensdownload-ch) nebo [japonština](https://aka.ms/hololensdownload-jp).
1. Po dokončení stahování vyberte **Průzkumník souborů**  >  **Stažené soubory.** Klikněte pravým tlačítkem na složku zip, kterou jste právě stáhli, a rozbalte ji výběrem **možnosti Extrahovat** vše  >   extrahovat.
1. Připojení připojte HoloLens k počítači pomocí kabelu s mikro USB, který jste dodali. (I v případě, že pro připojení svého zařízení používáte HoloLens kabely, funguje to nejlépe.)
1. Jakmile nástroj automaticky zjistí vaši HoloLens, vyberte dlaždici Microsoft HoloLens.
1. Na další obrazovce vyberte **Ruční výběr** balíčku a vyberte instalační soubor, který se nachází ve složce, kterou   jste rozbalili v kroku 4. (Vyhledejte soubor s příponou ".ffu".) 
1. Vyberte **Nainstalovat software a** postupujte podle pokynů. 
1. Po instalaci sestavení HoloLens automaticky. Dejte na zařízení a postupujte podle pokynů k nastavení. 

Až budete s instalací hotovi, přejděte na **Nastavení** Update & Security Windows Insider Program a zkontrolujte, že jste nakonfigurovaní pro příjem nejnovějších sestavení  >    >  Ve verzi Preview. Podobně jako u sestavení v anglické verzi Preview Windows Insider Program nejnovější verze Preview jsou v HoloLens a japonské verze aktuální.

> [!NOTE]
>  
> - Ke změně jazyka systému mezi angličtinou, japonštinou a čínštinou nemůžete použít aplikaci Nastavení. Jediným podporovaným způsobem, jak změnit jazyk systému zařízení, je blikající nové sestavení.
> - K zadání textu v čínštině nebo japonštině můžete použít klávesnici Pinyin na obrazovce, ale použití hardwarové klávesnice Bluetooth k zadání textu zjednodušená čínština nebo japonština se v tuto chvíli nepodporuje.  V čínštině nebo japonštině HoloLens ale můžete dál používat klávesnici Bluetooth k psaní v angličtině (pokud chcete přepnout hardwarovou klávesnici tak, aby nastiskla v angličtině, stiskněte klávesu ~).
