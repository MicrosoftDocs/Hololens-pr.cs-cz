---
title: Vyhledání a uložení souborů na HoloLens
description: Naučte se používat Průzkumník souborů na HoloLens k otevření, zobrazení a správě souborů na zařízení hybridní reality.
keywords: postupy, výběr souborů, soubory, fotky, videa, obrázky, OneDrive, úložiště, Průzkumník souborů, hololens
ms.assetid: 77d2e357-f65f-43c8-b62f-6cd9bf37070a
author: mattzmsft
ms.author: mazeller
manager: v-miegge
ms.reviewer: jarrettrenshaw
ms.date: 12/30/2019
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2d979b2cffd20589ddef7f11db5c7206eaea23cb
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377552"
---
# <a name="find-open-and-save-files-on-hololens"></a>Vyhledání, otevření a uložení souborů v HoloLens

Soubory, které vytvoříte na HoloLens, včetně fotek a videí, se ukládají přímo do zařízení HoloLens. Můžete je zobrazit a spravovat stejným způsobem jako soubory v Windows 10:

- Použití Průzkumník souborů pro přístup k místním složkám.
- V úložišti aplikace.
- Ve speciální složce (například v knihovně videí nebo hudby).
- Použití služby úložiště, která zahrnuje výběr aplikací a souborů (například OneDrive)
- Použití stolního počítače připojeného k HoloLens pomocí kabelu USB s podporou protokolu MTP (Media Transfer Protocol).

## <a name="view-files-on-hololens-using-file-explorer"></a>Zobrazení souborů na HoloLens pomocí Průzkumník souborů

> Platí pro všechna zařízení HoloLens 2 a HoloLens (1. generace) od [Aktualizace Windows 10 z dubna 2018 (RS4) pro HoloLens.](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)

Pomocí Průzkumník souborů na HoloLens můžete zobrazit a spravovat soubory na zařízení, včetně 3D objektů, dokumentů a obrázků. Začněte    >  **tím, že Všechny aplikace**   >  **Průzkumník souborů** startu.

> [!TIP]
> Pokud v seznamu nejsou žádné soubory Průzkumník souborů, vyberte **Toto zařízení** v levém horním podokně.

Pokud v seznamu nevidíte žádné soubory, Průzkumník souborů filtr Poslední (v levém podokně je zvýrazněná ikona hodin). Pokud chcete tento  problém vyřešit, vyberte ikonu Dokument zařízení v levém podokně (pod ikonou hodin) nebo otevřete nabídku a vyberte **This Device (Toto zařízení).**

## <a name="find-and-view-your-photos-and-videos"></a>Vyhledání a zobrazení fotek a videí

[Zachycení hybridní reality](holographic-photos-and-videos.md) umožňuje pořizovat fotky a videa hybridní reality na HoloLens.  Tyto fotky a videa se ukládají do složky Fotoaparát s fotoaparátem v zařízení.

K fotografiím a videím pořízených pomocí HoloLens můžete přistupovat tímto způsobem:

- přistupovat k fotoaparátu přímo prostřednictvím [aplikace Photos.](holographic-photos-and-videos.md)
- nahrání fotek a videí do cloudového úložiště synchronizací fotek a videí do OneDrivu
- pomocí Záznam hybridní reality stránky [Portál zařízení s Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).

### <a name="photos-app"></a>Aplikace Photos

Aplikace Photos je jednou z výchozích aplikací v **nabídce Start** a je integrovaná s HoloLens. Přečtěte si další [informace o použití aplikace Photos k zobrazení obsahu.](holographic-photos-and-videos.md)

Aplikaci [OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) můžete také nainstalovat z webu Microsoft Store synchronizovat fotky s jinými zařízeními.

### <a name="onedrive-app"></a>Aplikace OneDrive

[OneDrive](https://onedrive.live.com/) umožňuje přístup k fotografiím a videím, jejich správu a sdílení s libovolným zařízením a s libovolným uživatelem. Pokud chcete získat přístup k fotografiím a videím zachycených na HoloLens, stáhněte si [aplikaci OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) z Microsoft Store na HoloLens. Po stažení otevřete aplikaci OneDrive, vyberte Nastavení  >  **Nahrání fotoaparátu** a zapněte **Nahrání fotoaparátu.**

### <a name="connect-to-a-pc"></a>Připojení k počítači

Pokud holoLens používá aktualizaci [Windows 10 april 2018](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) nebo novější, můžete holoLens připojit k počítači Windows 10 pomocí kabelu USB a procházet fotky a videa na zařízení pomocí protokolu MTP (media transfer protocol). Pokud máte na zařízení nastavený PIN kód nebo heslo, musíte zajistit odemknutí zařízení, aby bylo možné procházet soubory.  

Pokud jste povolili [Portál zařízení s Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), můžete ho použít k procházení, načítání a správě fotek a videí uložených v zařízení.

## <a name="access-files-within-an-app"></a>Přístup k souborům v rámci aplikace

Pokud aplikace ukládá soubory do zařízení, můžete k nim přistupovat pomocí této aplikace.

### <a name="requesting-files-from-another-app"></a>Vyžádání souborů z jiné aplikace

Aplikace může požádat o uložení souboru nebo otevření souboru z jiné aplikace pomocí [výběrů souborů](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).

### <a name="known-folders"></a>Známé složky

HoloLens podporuje řadu známých [složek,](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) ke které mohou aplikace požádat o oprávnění pro přístup.

## <a name="view-hololens-files-on-your-pc"></a>Zobrazení souborů HoloLens na počítači

Podobně jako u jiných mobilních zařízení připojte HoloLens ke svému stolnímu počítači pomocí protokolu MTP (Media Transfer Protocol) a otevřete na počítači Průzkumník souborů pro přístup k knihovnám HoloLens pro snadný přenos.

Zobrazení souborů HoloLens v Průzkumník souborů počítači:

1. Přihlaste se k HoloLens a pak ho připojte k počítači pomocí kabelu USB, který se dodá s HoloLens.

1. Vyberte **Otevřít zařízení a zobrazte soubory s Průzkumník souborů**, nebo otevřete Průzkumník souborů na počítači a přejděte na zařízení.

Pokud chcete zobrazit informace o holoLensu, klikněte pravým tlačítkem na název zařízení v Průzkumník souborů počítači a pak vyberte **Vlastnosti**.

> [!NOTE]
> HoloLens (1. generace) nepodporuje připojení k externím pevným diskům nebo kartám SD.

## <a name="sync-to-the-cloud"></a>Synchronizace do cloudu

Pokud chcete synchronizovat fotky a další soubory z HoloLens do cloudu, nainstalujte a nastavte OneDrive na HoloLens. OneDrive získáte tak, že ho vyhledáte v Microsoft Store holoLens.

HoloLens nezá zálohuje soubory a data aplikace, takže je vhodné ukládat důležité věci na OneDrive. Pokud tak resetujete zařízení nebo odinstalujete aplikaci, vaše informace se zálohují.
