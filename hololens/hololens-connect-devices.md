---
title: Připojení k zařízením Bluetooth a USB-C
description: Začněte s připojením k zařízením Bluetooth a USB-C a příslušenstvím ze zařízení s technologií HoloLens hybridních realit.
ms.assetid: 01af0848-3b36-4c13-b797-f38ad3977e30
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 03/11/2020
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ffae65a6e1c096242ae7a28c488896c65df1c62d
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379283"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>Připojení k zařízením Bluetooth a USB-C

## <a name="pair-bluetooth-devices"></a>Párování zařízení Bluetooth

HoloLens 2 podporuje následující třídy zařízení Bluetooth:

- [HID](https://docs.microsoft.com/windows-hardware/drivers/hid/):
    - Myš
    - Klávesnice
- Výstupní zvukové zařízení (A2DP)

HoloLens 2 podporuje následující rozhraní API Bluetooth:
- [Server](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-server) a [klient](https://docs.microsoft.com/windows/uwp/devices-sensors/gatt-client) GATT
- [RFCOMM](https://docs.microsoft.com/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> Možná budete muset nainstalovat odpovídající doprovodné aplikace z Microsoft Store ke skutečnému používání zařízení se standardem HID a GATT.

HoloLens (1. generace) podporuje následující třídy zařízení Bluetooth:

- Myš
- Klávesnice
- [HoloLens (1. generace) – kliknutí](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> Další typy zařízení Bluetooth, jako jsou například reproduktory, sluchátka s mikrofony, smartphony a Game pad, mohou být v nastaveních HoloLens uvedeny jako dostupné. Tato zařízení ale nejsou podporovaná na HoloLens (1. generace). Další informace najdete v tématu [Nastavení HoloLens seznam zařízení, která jsou k dispozici, ale zařízení nefungují](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>Párování klávesnice nebo myši Bluetooth

1. Zapněte klávesnici nebo myš a nastavte ji jako zjistitelnou. Pokud se chcete dozvědět, jak zařízení zjistit, vyhledejte informace na zařízení (nebo jeho dokumentaci) nebo navštivte web výrobce.

1. Použijte gesto Bloom (HoloLens (1. gen)) nebo gesto Start (HoloLens 2), abyste mohli přejít na **Start** a pak vybrat **Nastavení**.

1. Vyberte **zařízení** a ujistěte se, že je Bluetooth zapnuté.  

1. Když se zobrazí název zařízení, vyberte **spárovat** a pak postupujte podle pokynů.

## <a name="disable-bluetooth"></a>Zakázat Bluetooth

Tento postup vypne součásti RF v přepínači Bluetooth a zakáže všechny funkce Bluetooth na Microsoft HoloLens.

1. Použijte gesto Bloom (HoloLens (1. generace)) nebo gesto Start (HoloLens 2), abyste mohli přejít na **Start** a pak vybrat **Nastavení**  >  **zařízení**.

1. Přesuňte přepínač posuvníku pro **Bluetooth** do **vypnuté** polohy.

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2: připojení zařízení USB-C

HoloLens 2 podporuje následující třídy zařízení USB-C:

- Velkokapacitní úložná zařízení (například jednotky s palec)
- Adaptéry sítě Ethernet (včetně zpoplatnění Ethernet Plus)
- Digitální zvukové adaptéry USB-C-do-3.5 mm
- Sluchátka s digitálním zvukem USB-C (včetně adaptérů sluchátek a zpoplatnění)
- Externí mikrotelefony USB-C ([Windows holografick, verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1) a vyšší)
- Kabelová myš
- Drátová klávesnice
- Kombinovaná centra PD (USB A Plus PD zpoplatněná)


> [!NOTE]
> V reakci na zpětnou vazbu od zákazníků jsme povolili omezené podpory pro mobilní připojení, které jsou připojené přímo k HoloLens přes USB-C. Další informace najdete v tématu [připojení k mobilním a 5g](hololens-cellular.md) .

### <a name="usb-c-external-microphone-support"></a>Podpora externích mikrofonů USB-C

> [!IMPORTANT]
> Zapojení do **USB MIC se automaticky nenastaví jako vstupní zařízení**. Při zapojení do sady sluchátek USB-C se uživatelům zobrazí, že se zvuk z sluchátka automaticky přesměruje na sluchátka, ale operační systém HoloLens nastaví prioritu interního pole mikrofonu nad jakékoli jiné vstupní zařízení. **Pokud chcete použít mikrofon USB-C, postupujte podle následujících kroků.**

> [!NOTE]
> Externí mikrotelefony nejde v buildech použít před [Windows holografickou verzí 21H1](hololens-release-notes.md#windows-holographic-version-21h1) a vyšší. 

Uživatelé můžou pomocí panelu nastavení **zvuku** vybrat připojení externích mikrofonů USB-C. Mikrofony USB-C lze použít pro volání, záznam atd.

Otevřete aplikaci **Nastavení** a vyberte **systémové**  >  **zvuky**.

![Nastavení zvuku](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Pokud chcete používat externí mikrotelefony s nástrojem **Remote Assist**, uživatelé budou muset kliknout na hypertextový odkaz Spravovat zvuková zařízení.
>
> Pak použijte rozevírací **nabídku a nastavte** externí mikrofon jako výchozí nebo **komunikační výchozí.** Volba **výchozí** znamená, že se externí mikrofon bude používat všude.
>
> Zvolíte-li možnost **komunikace výchozí** , znamená to, že se externí mikrofon bude používat ve vzdálené pomoci a v dalších komunikačních aplikacích, ale pro jiné úkoly se může používat i pole mikrofonu HoloLens.

![Správa zvukových zařízení](images/usbc-mic-2.png)

<br>

![Nastavit výchozí mikrofon](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>Co je podpora mikrofonu Bluetooth?

Technologie HoloLens 2 bohužel v současné době nepodporuje mikrofony Bluetooth.

#### <a name="troubleshooting-usb-c-microphones"></a>Řešení potíží s mikrofony USB-C

Uvědomte si, že někteří mikrotelefony USB-C nesprávně hlásí jako mikrofon *i* mluvčí. Jedná se o problém s mikrofonem a ne s HoloLens. Při zapojení jednoho z těchto mikrofonů do HoloLens může dojít ke ztrátě zvuku. Naštěstí je jednoduchá oprava.  

V **Nastavení**  ->    ->  **zvuk** systému explicitně nastavte Vestavěné reproduktory **(zvukový ovladač analogové funkce)** jako **výchozí zařízení**. HoloLens by si mělo pamatovat toto nastavení i v případě, že mikrofon odeberete a znovu připojíte později.

![Řešení potíží s mikrofony USB-C](images/usbc-mic-4.png)
### <a name="usb-c-hubs"></a>Rozbočovače USB-C

Někteří uživatelé možná potřebují připojit více zařízení najednou. Pro uživatele, kteří chtějí používat [mikrofon USB-c](#usb-c-external-microphone-support) spolu s jiným připojeným zařízením, můžou rozbočovače USB-c odpovídat potřebám zákazníka. Společnost Microsoft tato zařízení netestovala, a proto nemůžeme doporučit žádné konkrétní značky.

**Požadavky na rozbočovač USB-C a připojená zařízení:**

- Připojená zařízení nesmí vyžadovat instalaci ovladače.
- Celkový výkon vykreslování všech připojených zařízení musí být nižší než 4,5 wattů.

## <a name="connect-to-miracast"></a>Připojení k Miracast

Chcete-li použít Miracast, postupujte podle následujících kroků:

1. Proveďte některou z následujících akcí:  

   - Otevřete nabídku **Start** a vyberte ikonu **Zobrazit** .
   - Řekněme, že při pohledui v nabídce **Start** Vydáte "připojit".  

1. V seznamu zařízení, která se zobrazí, vyberte dostupné zařízení.

1. Zahajte párování pro zahájení projekce.
