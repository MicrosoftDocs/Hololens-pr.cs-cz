---
title: Představení nové Nastavení aplikace
description: Další informace o nové Nastavení aplikací
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, nastavení, výběr aplikace, svazek
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: e6da84c180ef596b63b6d41229bd094354ab1221
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640164"
---
# <a name="new-settings-app"></a>Nová Nastavení aplikace

S [Windows Holographic verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1)představujeme novou verzi Nastavení aplikace. Nová aplikace Nastavení obsahuje nové funkce a rozšířená nastavení pro HoloLens 2 v následujících oblastech: Zvuk, Power & režim spánku, Síť & Internet, Aplikace, Účty, Usnadnění přístupu a další.

> [!NOTE]
> Vzhledem k tomu, Nastavení nová aplikace se liší od starší Nastavení aplikace, při aktualizaci se Nastavení okna, která jste předtím umístili kolem svého prostředí.

![Domovská stránka Nastavení nové aplikace](images/new-settings-app.png)

**Nové funkce a nastavení**
- Nastavení: Na domovské stránce Nastavení pomocí klíčových slov nebo názvu nastavení vyhledejte nastavení.
- System > [Color](hololens2-display.md#how-to-use-display-color-calibration)
    - Vyberte alternativní profil barev pro váš HoloLens 2.
- System > Sound:
  - Vstupní a výstupní zvuková zařízení: Nezávisle zvolte vstupní a výstupní zvuková zařízení (například naslouchejte zvuku prostřednictvím Bluetooth nebo použijte mikrofon USB-C pro zvukový vstup).
    > [!NOTE]
    > Bluetooth 2 nepodporuje HoloLens mikrofony.
  - Objem aplikace: Nezávisle upravte objem každé aplikace. Viz [řízení objemu na aplikaci.](holographic-home.md#per-app-volume-control)
- System > Power & režim spánku: Zvolte, kdy má zařízení po určité době nečinnosti přejít do režimu spánku.
- Baterie >: Ručně povolte režim spořič baterie nebo nastavte prahovou hodnotu baterie, po spořič baterie režim zapne automaticky.
- Zařízení > USB: Ve výchozím nastavení můžete zakázat připojení USB.
- Network & Internet:
  - Ethernetové adaptéry USB-C se teď zobrazí v části Síťová & internetu.
  - K dispozici jsou teď nastavení ethernetového adaptéru USB-C, včetně jeho IP adresy.
  - Režim v letadle teď můžete povolit na HoloLens 2.
- Aplikace: Můžete resetovat výchozí aplikace používané pro typy souborů a odkazů. Další informace najdete v tématu [Výběr výchozí aplikace.](holographic-home.md#default-app-picker)
- Účty > Ostatní uživatelé: Vlastníci zařízení mohou přidávat uživatele, upgradovat standardní uživatele na vlastníky zařízení, downgradovat vlastníky zařízení na standardní uživatele a odebírat uživatele.
- Usnadnění přístupu: Změna velikosti textu a některých vizuálních efektů

**Známé problémy**
- Dříve umístěná Nastavení okna budou odebrána (viz poznámka výše).
- Zařízení už nemůžete přejmenovat pomocí Nastavení aplikace. Správci IT mohou zařízení přejmenovat pomocí šablony [Windows Autopilot pro název](hololens2-autopilot.md) zařízení HoloLens 2 nebo uzlu MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName.
- Na stránce Ethernet se za všech okolností zobrazuje virtuální ethernetové zařízení (UsbNcm).
- Využití baterie pro nové Microsoft Edge nemusí být přesné, protože je povaha desktopové aplikace Win32 podporované vrstvou adaptéru UPW (brzy se neočekává žádná oprava).

