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
# <a name="install-localized-versions-of-hololens-1st-gen"></a>Nainstalovat lokalizované verze HoloLens (1. generace)

Aby bylo možné přepnout na čínskou nebo japonskou verzi HoloLens, budete muset použít nástroj pro obnovení zařízení (WDRT) pro Windows ke stažení sestavení pro jazyk na počítači a pak ho nainstalovat na HoloLens.

> [!IMPORTANT]
> Použití WDRT k instalaci čínských nebo japonských buildů HoloLens odstraní existující data, jako jsou osobní soubory a nastavení, z HoloLens. 

1. Na počítači stáhněte a nainstalujte [Nástroj Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).
1. Stáhněte si balíček pro jazyk, který chcete do počítače:  [zjednodušená čínština](https://aka.ms/hololensdownload-ch) nebo [japonština](https://aka.ms/hololensdownload-jp).
1. Po dokončení stahování vyberte **Průzkumník souborů**  >  **soubory ke stažení**. Klikněte pravým tlačítkem na složku zip, kterou jste právě stáhli, a vyberte **extrahovat všechny**  >  **extrakce** , které chcete rozbalit.
1. Připojte HoloLens k počítači pomocí kabelu mikrosběrnice USB, který dodal. (I v případě, že jste k připojení HoloLens používali jiné kabely, tato funkce funguje nejlépe.)
1. Jakmile nástroj automaticky rozpozná HoloLens, vyberte dlaždici Microsoft HoloLens.
1. Na další obrazovce vyberte možnost **Manuální výběr balíčku**   a vyberte instalační soubor, který se nachází ve složce, kterou jste rozbalíte v kroku 4. (Vyhledejte soubor s příponou ". FFU".) 
1. Vyberte **instalovat software** a postupujte podle pokynů. 
1. Po instalaci sestavení se automaticky spustí instalační program HoloLens. Umístěte zařízení a postupujte podle pokynů k instalaci. 

Až budete s instalací hotovi, v části **Nastavení**  >  **aktualizovat & zabezpečení**  >  **programu Windows Insider** a ověřte, že jste nakonfigurovali, abyste získali nejnovější buildy Preview. Stejně jako anglické verze Preview sestaví program Windows Insider čínské a japonské verze HoloLens s nejnovějšími buildy Preview.

> [!NOTE]
>  
> - Aplikaci nastavení nemůžete použít ke změně systémového jazyka mezi angličtinu, japonštinou a čínštinou. Jediným podporovaným způsobem, jak změnit jazyk systému zařízení, je blikání nového sestavení.
> - I když můžete použít klávesnici s pchin-jin na obrazovce k zadání zjednodušeného čínského nebo japonského textu, není v tuto chvíli podporována použití hardwarové klávesnice Bluetooth k zadání zjednodušeného čínského nebo japonského textu.  V čínštině nebo v japonštině HoloLens můžete ale i nadále používat klávesnici Bluetooth k psaní angličtiny (Pokud chcete přepnout hardwarovou klávesnici na typ v angličtině, stiskněte klávesu ~).
