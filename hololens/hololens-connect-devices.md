---
title: Připojení k Bluetooth a zařízení USB-C
description: Začínáme s připojování Bluetooth zařízeními USB a USB-C a příslušenstvím z HoloLens hybridní realitou.
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
ms.openlocfilehash: 5fed56d7a0beeda0a0d96eddc63aaee872f3e52d
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639093"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>Připojení k Bluetooth a zařízení USB-C

## <a name="pair-bluetooth-devices"></a>Párování Bluetooth zařízení

HoloLens 2 podporuje následující třídy Bluetooth zařízení:

- [HID:](/windows-hardware/drivers/hid/)
    - Myš
    - Klávesnice
- Výstupní zvuková zařízení (A2DP)

HoloLens 2 podporuje následující Bluetooth API:
- Server [a klient](/windows/uwp/devices-sensors/gatt-server) [POS](/windows/uwp/devices-sensors/gatt-client)
- [RFCOMM](/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> Možná budete muset nainstalovat odpovídající doprovodné aplikace z Microsoft Store, aby bylo možné skutečně používat zařízení HID a

HoloLens (1. generace) podporuje následující třídy Bluetooth zařízení:

- Myš
- Klávesnice
- [HoloLens (1. generace)](hololens1-clicker.md)

> [!NOTE]
> Další typy zařízení Bluetooth, jako jsou mluvčí, náhlavní soupravy, smartphony a herní pady, mohou být uvedené jako dostupné v HoloLens zařízení. Tato zařízení ale nejsou podporovaná v HoloLens (1. generace). Další informace najdete v [HoloLens Nastavení uvádí zařízení jako dostupná,](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work)ale zařízení nefungují.

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>Spárování Bluetooth klávesnice nebo myši

1. Zapněte klávesnici nebo myš a zajistěte, aby byla zjistitelná. Pokud chcete zjistit, jak zajistit, aby bylo zařízení zjistitelné, vyhledejte informace o zařízení (nebo jeho dokumentaci) nebo navštivte web výrobce.

1. Pomocí gesta bloom (HoloLens (1. generace)) nebo počátečního gesta (HoloLens 2) přejděte na **Start** a pak vyberte **Nastavení**.

1. Vyberte **Zařízení** a ujistěte se, Bluetooth je tato možnost nastavená.  

1. Až se zobrazí název zařízení, vyberte **Spárovat** a postupujte podle pokynů.

## <a name="disable-bluetooth"></a>Zakázání Bluetooth

Tento postup vypne komponenty RF rádia Bluetooth a zakáže všechny funkce Bluetooth na Microsoft HoloLens.

1. Pomocí gesta bloom (HoloLens (1. generace)) nebo gesta spuštění (HoloLens 2) přejděte na **Start** a pak vyberte **Nastavení**  >  **Devices (Zařízení).**

1. Přesuňte posuvník **pro** Bluetooth do pozice **Vypnuto.**

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2: Připojení zařízení USB-C

HoloLens 2 podporuje následující třídy zařízení USB-C:

- Velkokapamová úložná zařízení (například kryptografický disk)
- Ethernetové adaptéry (včetně ethernetového a zpoplatnění)
- Digitální zvukové adaptéry USB-C-to-3,5mm
- Digitální zvukové náhlavní soupravy USB-C (včetně adaptérů náhlavní soupravy a zpoplatnění)
- Externí mikrofony USB-C ([Windows Holographic verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1) a vyšší)
- Drátová myš
- Drátová klávesnice
- Kombinované rozbočovače PD (USB A a PD)


> [!NOTE]
> V reakci na zpětnou vazbu od zákazníků jsme povolili omezenou podporu mobilního připojení, které je připojeno přímo HoloLens přes USB-C. Další informace Připojení v tématu Připojení k mobilní síti a [5G.](hololens-cellular.md)

### <a name="usb-c-external-microphone-support"></a>Podpora externího mikrofonu USB-C

> [!IMPORTANT]
> Když zapojíte mikrofon USB, nenastaví **se automaticky jako vstupní zařízení.** Při zapojení do sady konektorů USB-C uživatelé pozorují, že zvuk zařízení se automaticky přesměruje na mikrofony, ale operační systém HoloLens upřednostňuje interní mikrofonní pole nad jiným vstupním zařízením. **Pokud chcete použít mikrofon USB-C, postupujte podle následujících kroků.**

> [!NOTE]
> Externí mikrofony není možné používat v buildech před [Windows Holographic verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1) a vyšší. 

Uživatelé mohou vybrat externí mikrofony připojené přes USB-C pomocí panelu **nastavení** Zvuk. Mikrofony USB-C je možné použít k volání, nahrávání atd.

Otevřete aplikaci **Nastavení** a vyberte **Systémový**  >  **zvuk.**

![Sound Nastavení](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> Pokud uživatelé budou s remote **assistem** používat externí mikrofony, budou muset kliknout na hypertextový odkaz Spravovat zvuková zařízení.
>
> Potom pomocí rozevíracího seznamu nastavte externí mikrofon na **Výchozí** nebo **Výchozí komunikace.** Volba Výchozí **znamená,** že externí mikrofon se bude používat všude.
>
> Volba Výchozí **komunikace** znamená, že externí mikrofon se použije ve vzdáleném asistenci a dalších komunikačních aplikacích, ale pole mikrofonu HoloLens mikrofonu se stále může používat pro jiné úlohy.

![Správa zvukových zařízení](images/usbc-mic-2.png)

<br>

![Nastavení výchozího nastavení mikrofonu](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>A co Bluetooth mikrofonu?

V Bluetooth 2 se bohužel stále nepodporují HoloLens mikrofony.

### <a name="usb-c-hubs"></a>Rozbočovače USB-C

Někteří uživatelé možná budou muset připojit více zařízení najednou. Pro uživatele, kteří chtějí používat mikrofon [USB-C](#usb-c-external-microphone-support) společně s jiným připojeným zařízením, mohou být rozbočovače USB-C vhodné pro potřeby zákazníka. Microsoft tato zařízení netestoval, ani nemůžeme doporučit konkrétní značky.

**Požadavky na rozbočovač USB-C a připojená zařízení:**

- Připojená zařízení nesmí vyžadovat instalaci ovladače.
- Celkový příkon všech připojených zařízení musí být nižší než 4,5 W.

## <a name="connect-to-miracast"></a>Připojení na Miracast

Pokud chcete Miracast, postupujte takto:

1. Proveďte některou z následujících akcí:  

   - Otevřete **nabídku Start** a vyberte **ikonu** Zobrazit.
   - Při pohledu Připojení Start řekněte **"Připojení".**  

1. V seznamu zařízení, která se zobrazí, vyberte dostupné zařízení.

1. Dokončete párování a zahajte projektování.
