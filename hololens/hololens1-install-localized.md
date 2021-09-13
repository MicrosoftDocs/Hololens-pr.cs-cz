---
title: Nainstalovat lokalizované verze HoloLens
description: naučte se instalovat lokalizované verze HoloLens (1. generace), včetně čínských a japonských verzí.
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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032352"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a>nainstalovat lokalizované verze HoloLens (1. generace)

chcete-li přepnout na čínskou nebo japonskou verzi HoloLens, je nutné použít nástroj pro obnovení Windows (WDRT) ke stažení sestavení pro jazyk na počítači a pak jej nainstalovat na HoloLens.

> [!IMPORTANT]
> použití WDRT k instalaci čínských nebo japonských buildů HoloLens z HoloLens odstraní existující data, jako jsou osobní soubory a nastavení. 

1. na počítači stáhněte a nainstalujte [nástroj Windows pro obnovení zařízení (WDRT)](https://support.microsoft.com/help/12379).
1. Stáhněte si balíček pro jazyk, který chcete do počítače:  [zjednodušená čínština](https://aka.ms/hololensdownload-ch) nebo [japonština](https://aka.ms/hololensdownload-jp).
1. Po dokončení stahování vyberte **Průzkumník souborů**  >  **soubory ke stažení**. Klikněte pravým tlačítkem na složku zip, kterou jste právě stáhli, a vyberte **extrahovat všechny**  >  **extrakce** , které chcete rozbalit.
1. Připojení své HoloLens do svého počítače pomocí kabelu mikrosběrnice USB, který dodal. (i když používáte k připojení HoloLens jiné kabely, tato funkce funguje nejlépe.)
1. jakmile nástroj automaticky rozpozná HoloLens, vyberte dlaždici Microsoft HoloLens.
1. Na další obrazovce vyberte možnost **Manuální výběr balíčku**   a vyberte instalační soubor, který se nachází ve složce, kterou jste rozbalíte v kroku 4. (Vyhledejte soubor s příponou ". FFU".) 
1. Vyberte **instalovat software** a postupujte podle pokynů. 
1. po nainstalování sestavení se automaticky spustí instalační program HoloLens. Umístěte zařízení a postupujte podle pokynů k instalaci. 

až budete s instalačním programem hotovi, přejdete na **Nastavení**  >  **Update & Security**  >  **Windows programu Insider** a ověřte, že jste nakonfigurovali, abyste získali nejnovější buildy preview. stejně jako anglické verze preview sestaví Windows programu Insider čínské a japonské verze HoloLens aktuální s nejnovějšími buildy preview.

> [!NOTE]
>  
> - nemůžete použít aplikaci Nastavení ke změně systémového jazyka mezi angličtinu, japonštinou a čínštinou. Jediným podporovaným způsobem, jak změnit jazyk systému zařízení, je blikání nového sestavení.
> - i když můžete použít klávesnici s pchin-jin na obrazovce k zadání zjednodušeného čínského nebo japonského textu, pomocí Bluetooth hardwarové klávesnice pro psaní zjednodušeného čínského nebo japonského textu se v tuto chvíli nepodporuje.  v čínštině nebo v japonštině ale HoloLens můžete i nadále používat Bluetoothovou klávesnici k psaní angličtiny (pokud chcete přepnout hardwarovou klávesnici na typ v angličtině, stiskněte klávesu ~).
