---
title: Hledání a ukládání souborů na HoloLens
description: naučte se používat průzkumníka souborů v HoloLens k otevření, zobrazení a správě souborů na zařízení se smíšenými realitami.
keywords: postupy, výběr souborů, soubory, fotky, videa, obrázky, OneDrive, úložiště, průzkumník souborů, hololens
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
ms.openlocfilehash: 18dc962b869dafaea9ff9c605eef51fcbb35bfb2
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032239"
---
# <a name="find-open-and-save-files-on-hololens"></a>Hledání, otevírání a ukládání souborů na HoloLens

soubory, které vytvoříte v HoloLens, včetně fotek a videí, se ukládají přímo do vašeho zařízení HoloLens. Můžete je zobrazit a spravovat stejným způsobem, jakým byste mohli spravovat soubory na Windows 10:

- Přístup k místním složkám pomocí aplikace Průzkumník souborů
- V rámci úložiště aplikace.
- Ve speciální složce (například v knihovně video nebo hudba).
- Používání služby úložiště, která zahrnuje výběr aplikace a souboru (například OneDrive).
- použití stolního počítače připojeného k vašemu HoloLens pomocí kabelu USB pomocí podpory MTP (Media Transfer Protocol).

## <a name="view-files-on-hololens-using-file-explorer"></a>zobrazení souborů v HoloLens pomocí průzkumníka souborů

> platí pro všechna zařízení HoloLens 2 a HoloLens (1. generace) Windows 10 od [dubna 2018 Update (RS4) pro HoloLens](/windows/mixed-reality/release-notes-april-2018).

pomocí průzkumníka souborů v HoloLens můžete zobrazit a spravovat soubory v zařízení, včetně 3d objektů, dokumentů a obrázků. Začněte tím, že přejdete na **Start**   >  **All apps**   >  **Průzkumník souborů** .

> [!TIP]
> Pokud v Průzkumníkovi souborů nejsou uvedené žádné soubory, vyberte v levém horním podokně **Toto zařízení** .

Pokud v Průzkumníkovi souborů nevidíte žádné soubory, může být filtr "poslední" aktivní (v levém podokně je zvýrazněna ikona hodiny). Pokud to chcete opravit, vyberte ikonu dokumentu **Tento zařízení** v levém podokně (pod ikonou hodin), nebo otevřete nabídku a vyberte **Toto zařízení**.

## <a name="find-and-view-your-photos-and-videos"></a>Hledání a zobrazování fotek a videí

[Hybridní zachycení realit](holographic-photos-and-videos.md) umožňuje využívat fotky a videa ze směsi realit na HoloLens.  Tyto fotky a videa se uloží do složky pro fotoaparát zařízení.

k fotografiím a videím pořízeným pomocí HoloLens můžete získat následující:

- přístup ke kameře přímo přes [aplikaci Photos](holographic-photos-and-videos.md).
- nahrávají se fotky a videa do cloudového úložiště díky synchronizaci fotek a videí s OneDrive.
- pomocí stránky zachycení hybridních realit na [portálu zařízení Windows](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).

### <a name="photos-app"></a>Aplikace Fotky

Aplikace Photos je jedna z výchozích aplikací v nabídce **Start** a integrovaná s HoloLens. Přečtěte si další informace o [používání aplikace fotky k zobrazení obsahu](holographic-photos-and-videos.md).

můžete taky nainstalovat [aplikaci OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) z Microsoft Store a synchronizovat fotky s ostatními zařízeními.

### <a name="onedrive-app"></a>aplikace OneDrive

[OneDrive](https://onedrive.live.com/) vám umožní přístup, správu a sdílení fotek a videí pomocí libovolného zařízení a libovolného uživatele. pokud chcete získat přístup k fotografiím a videím zachyceným na HoloLens, stáhněte [OneDrive aplikaci](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) z Microsoft Store na HoloLens. po stažení otevřete aplikaci OneDrive a vyberte **Nastavení**  >  **nahrávání kamery** a zapněte **nahrávání kamery**.

### <a name="connect-to-a-pc"></a>Připojení k počítači

pokud na vašem HoloLens běží [Windows 10 aktualizace z dubna 2018](/windows/mixed-reality/release-notes-april-2018) nebo novější, můžete své HoloLens připojit k Windows 10 počítači pomocí kabelu USB a procházet fotky a videa na zařízení pomocí protokolu MTP (media transfer protocol). Pokud máte na svém zařízení nastavené PIN nebo heslo, budete se muset ujistit, že je zařízení odemčené pro procházení souborů.  

pokud jste povolili [Windows portál zařízení](/windows/mixed-reality/using-the-windows-device-portal), můžete ho použít k procházení, načítání a správě fotografií a videí uložených v zařízení.

## <a name="access-files-within-an-app"></a>Přístup k souborům v rámci aplikace

Pokud aplikace ukládá soubory do zařízení, můžete k nim přistupovat pomocí této aplikace.

### <a name="requesting-files-from-another-app"></a>Vyžádání souborů z jiné aplikace

Aplikace může požádat o uložení souboru nebo otevření souboru z jiné aplikace pomocí [výběrů souborů](/windows/mixed-reality/app-model#file-pickers).

### <a name="known-folders"></a>Známé složky

HoloLens podporuje několik [známých složek](/windows/mixed-reality/app-model#known-folders) , které můžou aplikace požádat o oprávnění k přístupu.

## <a name="view-hololens-files-on-your-pc"></a>zobrazit HoloLens soubory na počítači

podobně jako u jiných mobilních zařízení připojte HoloLens k stolnímu počítači pomocí MTP (Media Transfer Protocol) a otevřete průzkumníka souborů na počítači, abyste měli přístup k vašim HoloLensm knihovnám za účelem snadného přenosu.

chcete-li zobrazit soubory HoloLens v průzkumníkovi souborů na vašem počítači:

1. přihlaste se k HoloLens a pak ho připojte k počítači pomocí kabelu USB, který jste dostali s HoloLens.

1. Vyberte **otevřít zařízení a zobrazte si soubory pomocí Průzkumníka souborů** nebo otevřete Průzkumníka souborů na počítači a přejděte k zařízení.

pokud chcete zobrazit informace o vašem HoloLens, klikněte pravým tlačítkem myši na název zařízení v průzkumníkovi souborů na počítači a pak vyberte **vlastnosti**.

> [!NOTE]
> HoloLens (1. generace) nepodporuje připojení k externím pevným diskům nebo SD kartám.

## <a name="sync-to-the-cloud"></a>Synchronizace s cloudem

pokud chcete synchronizovat fotky a jiné soubory z HoloLens do cloudu, nainstalujte a nastavte OneDrive na HoloLens. pokud chcete OneDrive získat, vyhledejte ho v Microsoft Store na HoloLens.

HoloLens nezálohují soubory a data aplikací, takže je vhodné, abyste si ušetřili důležité věci, které byste měli OneDrive. Tímto způsobem, pokud resetujete zařízení nebo odinstalujete aplikaci, vaše informace se zálohují.
