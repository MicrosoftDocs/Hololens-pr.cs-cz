---
title: představujeme novou aplikaci Nastavení
description: další informace o nové aplikaci Nastavení
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, nastavení, výběr aplikace, svazek
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: bcde697b5887573826a3a1a61e8c3707b4d0337a
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189660"
---
# <a name="new-settings-app"></a>nová aplikace Nastavení

pomocí [Windows holografické verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1)zavádíme novou verzi Nastavení aplikace. nová aplikace Nastavení zahrnuje nové funkce a rozšířené nastavení pro HoloLens 2 v následujících oblastech: zvuk, Power & spánek, síť & Internet, aplikace, účty, usnadnění přístupu a další.

> [!NOTE]
> vzhledem k tomu, že je nová aplikace Nastavení odlišná od starší Nastavení aplikace, všechna Nastaveníná okna, která jste předtím umístili do svého prostředí, budou po aktualizaci odebrána.

![nová domovská stránka aplikace Nastavení.](images/new-settings-app.png)

**Nové funkce a nastavení**
- Nastavení search: vyhledejte nastavení z domovské stránky Nastavení pomocí klíčových slov nebo názvu nastavení.
- Systémová >ová [kalibrace barev](hololens2-display.md#how-to-use-display-color-calibration)
    - vyberte alternativní barevný profil pro zobrazení HoloLens 2.
- Zvuk > systému:
  - vstupní a výstupní zvuková zařízení: nezávisle vyberte vstupní a výstupní zvuková zařízení (například poslech zvuku prostřednictvím Bluetooth sluchátek nebo použití mikrofonu USB-C pro zvukový vstup).
    > [!NOTE]
    > HoloLens 2 nepodporuje Bluetooth mikrotelefonů.
  - Svazek aplikace: nezávisle upravte hlasitost každé aplikace. Zobrazit [Řízení hlasitosti jednotlivých aplikací](holographic-home.md#per-app-volume-control).
- Systém > napájení & režimu spánku: vyberte, kdy se má zařízení po určité době nečinnosti přejít do režimu spánku.
- Systémová > baterie: ručně povolit režim spořiče baterie nebo nastavit prahovou hodnotu baterie, při které se režim spořiče baterie automaticky zapne.
- Zařízení > USB: ve výchozím nastavení můžete připojení USB zakázat.
- & sítě Internet:
  - Adaptéry USB-C Ethernet se nyní zobrazí v síti & Internetu.
  - K dispozici jsou nyní nastavení adaptéru USB-C Ethernet, včetně jeho IP adresy.
  - nyní můžete zapnout režim v letadle HoloLens 2.
- Aplikace: můžete obnovit výchozí aplikace používané pro typy souborů a odkazů. Další informace najdete v tématu věnovaném [výchozím ovládacím prvkům aplikace](holographic-home.md#default-app-picker).
- Účty > jiných uživatelích: vlastníci zařízení můžou přidávat uživatele, upgradovat standardní uživatele na vlastníky zařízení, předowngradovat vlastníky zařízení na standardní uživatele a odebírat uživatele.
- Usnadnění přístupu: Změna velikosti textu a některých vizuálních efektů.

**Známé problémy**
- předchozí umístění, Nastavení windows, bude odebráno (viz poznámku výše).
- v aplikaci Nastavení už nemůžete přejmenovat zařízení. správci IT můžou zařízení přejmenovat pomocí [Windowsho autopilotu pro HoloLens 2 2](hololens2-autopilot.md) nebo v uzlu cloud MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName.
- Na stránce Ethernet se vždy zobrazuje virtuální síť Ethernet (UsbNcm).
- využití baterie pro nový Microsoft Edge nemusí být přesné, vzhledem k jeho povaze jako desktopová aplikace Win32 podporovaná vrstvou adaptéru UWP (zatím se nepředpokládá žádná oprava).

