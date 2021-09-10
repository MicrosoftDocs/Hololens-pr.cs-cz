---
title: Instalace lokalizovaných verzí HoloLens
description: Zjistěte, jak nainstalovat lokalizované verze HoloLens (1. generace), včetně čínských a japonskéch verzí.
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
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428546"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a>Instalace lokalizovaných verzí HoloLens (1. generace)

Pokud chcete přepnout na čínštinu nebo japonštinu služby HoloLens, budete muset pomocí nástroje WDRT (Windows Device Recovery Tool) stáhnout sestavení pro jazyk na počítači a pak ho nainstalovat na HoloLens.

> [!IMPORTANT]
> Pomocí nástroje WDRT nainstalujte sestavení pro čínštinu nebo japonštinu HoloLens odstraní existující data, jako jsou osobní soubory a nastavení, z vaší HoloLens. 

1. Na svém počítači stáhněte a [nainstalujte Windows Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379)
1. Stáhněte si balíček pro jazyk, který chcete mít na počítači:  [Zjednodušená čínština](https://aka.ms/hololensdownload-ch) nebo [japonština](https://aka.ms/hololensdownload-jp).
1. Po dokončení stahování vyberte **Průzkumník souborů**  >  **Stažené soubory.** Klikněte pravým tlačítkem na složku zip, kterou jste právě stáhli, a rozbalte ji výběrem **možnosti Extrahovat** vše  >   extrahovat.
1. Připojení HoloLens k počítači pomocí kabelu mikro USB, který dodal. (I v případě, že pro připojení svého zařízení používáte HoloLens kabely, funguje to nejlépe.)
1. Jakmile nástroj automaticky zjistí vaši HoloLens, vyberte dlaždici Microsoft HoloLens.
1. Na další obrazovce vyberte **Ruční výběr** balíčku a vyberte instalační soubor, který se nachází ve složce, kterou   jste rozbalili v kroku 4. (Vyhledejte soubor s příponou ".ffu".) 
1. Vyberte **Nainstalovat software a** postupujte podle pokynů. 
1. Po instalaci sestavení HoloLens automaticky. Dejte na zařízení a postupujte podle pokynů k nastavení. 

Až s nastavením skončíte, přejděte na **Nastavení** Update & Security Windows Insider Program a zkontrolujte, že jste nakonfigurovaní tak, aby přijímal  >    >  nejnovější buildy ve verzi Preview. Stejně jako u sestavení v anglické verzi Preview je Windows Insider Program a japonské verze HoloLens aktuální díky nejnovějším buildům ve verzi Preview.

> [!NOTE]
>  
> - Ke změně systémového jazyka mezi angličtinou, japonštinou a čínštinou nemůžete použít aplikaci Nastavení. Jediným podporovaným způsobem, jak změnit jazyk systému zařízení, je blikající nové sestavení.
> - K zadání textu v čínštině nebo japonštině můžete použít klávesnici Pinyin na obrazovce, ale použití hardwarové klávesnice Bluetooth k zadání textu zjednodušená čínština nebo japonština se v tuto chvíli nepodporuje.  V čínštině nebo japonštině HoloLens můžete dál používat klávesnici Bluetooth k psaní v angličtině (pokud chcete přepnout hardwarovou klávesnici tak, aby zadat angličtinu, stiskněte klávesu ~).
