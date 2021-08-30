---
title: Připojení Bluetooth a zařízení USB-C
description: začněte s připojením Bluetooth a zařízení USB a příslušenství z vašich HoloLensch zařízení se smíšenými realitami.
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
ms.openlocfilehash: d9c8b813ba54edbcfef8d1a32e641dad39a7f193
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189082"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>Připojení Bluetooth a zařízení USB-C

## <a name="pair-bluetooth-devices"></a>párové Bluetooth zařízení

HoloLens 2 podporuje následující třídy Bluetoothch zařízení:

- [HID](/windows-hardware/drivers/hid/):
    - Myš
    - Klávesnice
- Výstupní zvukové zařízení (A2DP)

HoloLens 2 podporuje následující rozhraní api Bluetooth:
- [Server](/windows/uwp/devices-sensors/gatt-server) a [klient](/windows/uwp/devices-sensors/gatt-client) GATT
- [RFCOMM](/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> možná budete muset nainstalovat odpovídající doprovodné aplikace z Microsoft Store ke skutečnému používání zařízení se standardem HID a GATT.

HoloLens (1. generace) podporuje následující třídy Bluetoothch zařízení:

- Myš
- Klávesnice
- [HoloLens (1. generace) – kliknutí](hololens1-clicker.md)

> [!NOTE]
> další typy zařízení Bluetooth, jako jsou například reproduktory, sluchátka s mikrofony, smartphony a game pad, mohou být v nastaveních HoloLens uvedeny jako dostupné. tato zařízení ale nejsou podporovaná na HoloLens (1. generace). další informace najdete v tématu [HoloLens Nastavení seznam zařízení, která jsou k dispozici, ale zařízení nefungují](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work).

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>párování Bluetooth klávesnice nebo myši

1. Zapněte klávesnici nebo myš a nastavte ji jako zjistitelnou. Pokud se chcete dozvědět, jak zařízení zjistit, vyhledejte informace na zařízení (nebo jeho dokumentaci) nebo navštivte web výrobce.

1. použijte gesto bloom (HoloLens (1. generace)) nebo gesto start (HoloLens 2), abyste mohli přejít na **start** a pak vybrat **Nastavení**.

1. vyberte **zařízení** a ujistěte se, že je zapnutá Bluetooth.  

1. Když se zobrazí název zařízení, vyberte **spárovat** a pak postupujte podle pokynů.

## <a name="disable-bluetooth"></a>Zakázat Bluetooth

tento postup vypne součásti RF v Bluetooth přepínači a zakáže všechny funkce Bluetooth na Microsoft HoloLens.

1. použijte gesto bloom (HoloLens (1. generace)) nebo gesto start (HoloLens 2), abyste mohli přejít na **start** a pak vybrat **Nastavení**  >  **zařízení**.

1. přesuňte přepínač posuvníku pro **Bluetooth** na **vypnutou** pozici.

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2: Připojení zařízení USB-C

HoloLens 2 podporuje následující třídy zařízení USB-C:

- Velkokapacitní úložná zařízení (například jednotky s palec)
- Adaptéry sítě Ethernet (včetně zpoplatnění Ethernet Plus)
- Digitální zvukové adaptéry USB-C-do-3.5 mm
- Sluchátka s digitálním zvukem USB-C (včetně adaptérů sluchátek a zpoplatnění)
- externí mikrotelefony USB-C ([Windows holografické, verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1) a vyšší)
- Kabelová myš
- Drátová klávesnice
- Kombinovaná centra PD (USB A Plus PD zpoplatněná)


> [!NOTE]
> v reakci na zpětnou vazbu od zákazníků jsme povolili omezené podpory pro mobilní připojení, které jsou připojené přímo k HoloLens přes USB-C. další informace najdete v tématu [Připojení na mobilní a 5G](hololens-cellular.md) .

### <a name="usb-c-external-microphone-support"></a>Podpora externích mikrofonů USB-C

> [!IMPORTANT]
> Zapojení do **USB MIC se automaticky nenastaví jako vstupní zařízení**. při zapojení do sady sluchátek USB-C se uživatelům zobrazí, že se zvuk z sluchátka automaticky přesměruje na sluchátka, ale HoloLens operační systém nastaví prioritu interního pole mikrofonu nad jakékoli jiné vstupní zařízení. **Pokud chcete použít mikrofon USB-C, postupujte podle následujících kroků.**

> [!NOTE]
> externí mikrotelefony nejde v sestaveních použít před [Windows holografickou 21H1](hololens-release-notes.md#windows-holographic-version-21h1) a vyšší verzí. 

Uživatelé můžou pomocí panelu nastavení **zvuku** vybrat připojení externích mikrofonů USB-C. Mikrofony USB-C lze použít pro volání, záznam atd.

otevřete aplikaci **Nastavení** a vyberte **systémový**  >  **zvuk**.

![zvukový Nastavení.](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Pokud chcete používat externí mikrotelefony s nástrojem **Remote Assist**, uživatelé budou muset kliknout na hypertextový odkaz Spravovat zvuková zařízení.
>
> Pak použijte rozevírací **nabídku a nastavte** externí mikrofon jako výchozí nebo **komunikační výchozí.** Volba **výchozí** znamená, že se externí mikrofon bude používat všude.
>
> zvolíte-li možnost **komunikace výchozí** , znamená to, že se externí mikrofon bude používat ve vzdálené pomoci a dalších komunikačních aplikacích, ale pole HoloLensho mikrofonu se může používat i pro jiné úkoly.

![Správa zvukových zařízení.](images/usbc-mic-2.png)

<br>

![Nastavte výchozí mikrofon.](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>co Bluetooth podpora mikrofonu?

v HoloLens 2 bohužel Bluetooth mikrofony stále nejsou podporovány.

### <a name="usb-c-hubs"></a>Rozbočovače USB-C

Někteří uživatelé možná potřebují připojit více zařízení najednou. Pro uživatele, kteří chtějí používat [mikrofon USB-c](#usb-c-external-microphone-support) spolu s jiným připojeným zařízením, můžou rozbočovače USB-c odpovídat potřebám zákazníka. Společnost Microsoft tato zařízení netestovala, a proto nemůžeme doporučit žádné konkrétní značky.

**Požadavky na rozbočovač USB-C a připojená zařízení:**

- Připojená zařízení nesmí vyžadovat instalaci ovladače.
- Celkový výkon vykreslování všech připojených zařízení musí být nižší než 4,5 wattů.

## <a name="connect-to-miracast"></a>Připojení Miracast

pokud chcete použít Miracast, postupujte podle těchto kroků:

1. Proveďte některou z následujících akcí:  

   - Otevřete nabídku **Start** a vyberte ikonu **Zobrazit** .
   - řekněme, že při pohledu v nabídce **Start** vydáte "Připojení".  

1. V seznamu zařízení, která se zobrazí, vyberte dostupné zařízení.

1. Zahajte párování pro zahájení projekce.
