---
title: Představujeme novou aplikaci nastavení
description: Další informace o nové aplikaci nastavení
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, nastavení, výběr aplikace, svazek
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: bf1a2080c15346843b9ea9b2d0dc93154e185107
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379338"
---
# <a name="new-settings-app"></a>Nová aplikace nastavení

S [Windows holografickou verzí 21H1](hololens-release-notes.md#windows-holographic-version-21h1)zavádíme novou verzi aplikace nastavení. Nová aplikace nastavení zahrnuje nové funkce a rozšířené nastavení pro HoloLens 2 v následujících oblastech: zvuk, Power & režim spánku, síť & Internetu, aplikace, účty, usnadnění přístupu a další.

> [!NOTE]
> Vzhledem k tomu, že je nová aplikace nastavení odlišná od aplikace se staršími nastaveními, všechna nastavení, která jste předtím umístili do prostředí, se po aktualizaci odeberou.

![Domovská stránka nové aplikace nastavení](images/new-settings-app.png)

**Nové funkce a nastavení**
- Hledání nastavení: Vyhledejte nastavení z domovské stránky nastavení pomocí klíčových slov nebo názvu nastavení.
- Systémová >ová [kalibrace barev](hololens2-display.md#how-to-use-display-color-calibration)
    - Vyberte alternativní barevný profil pro displej HoloLens 2.
- Zvuk > systému:
  - Vstupní a výstupní zvuková zařízení: nezávisle vyberte vstupní a výstupní zvuková zařízení (například poslech zvuku přes sluchátka Bluetooth nebo použití mikrofonu USB-C pro zvukový vstup).
    > [!NOTE]
    > Technologie HoloLens 2 nepodporuje mikrofony Bluetooth.
  - Svazek aplikace: nezávisle upravte hlasitost každé aplikace. Zobrazit [Řízení hlasitosti jednotlivých aplikací](holographic-home.md#per-app-volume-control).
- Systém > napájení & režimu spánku: vyberte, kdy se má zařízení po určité době nečinnosti přejít do režimu spánku.
- Systémová > baterie: ručně povolit režim spořiče baterie nebo nastavit prahovou hodnotu baterie, při které se režim spořiče baterie automaticky zapne.
- Zařízení > USB: ve výchozím nastavení můžete připojení USB zakázat.
- & sítě Internet:
  - Adaptéry USB-C Ethernet se nyní zobrazí v síti & Internetu.
  - K dispozici jsou nyní nastavení adaptéru USB-C Ethernet, včetně jeho IP adresy.
  - Nyní můžete zapnout režim v letadle na HoloLens 2.
- Aplikace: můžete obnovit výchozí aplikace používané pro typy souborů a odkazů. Další informace najdete v tématu věnovaném [výchozím ovládacím prvkům aplikace](holographic-home.md#default-app-picker).
- Účty > jiných uživatelích: vlastníci zařízení můžou přidávat uživatele, upgradovat standardní uživatele na vlastníky zařízení, předowngradovat vlastníky zařízení na standardní uživatele a odebírat uživatele.
- Usnadnění přístupu: Změna velikosti textu a některých vizuálních efektů.

**Známé problémy**
- Okna dříve umístěná nastavení se odeberou (viz poznámku výše).
- Zařízení už nemůžete přejmenovat pomocí aplikace nastavení. Správci IT můžou zařízení přejmenovat pomocí šablony [Windows autopilot pro název zařízení HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) nebo uzlu MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) EXT/Microsoft/DNSComputerName.
- Na stránce Ethernet se vždy zobrazuje virtuální síť Ethernet (UsbNcm).
- Využití baterie pro nové Microsoft Edge nemusí být přesné, vzhledem k jeho povaze jako desktopová aplikace Win32 podporovaná vrstvou adaptéru UWP (zatím se nepředpokládá žádná oprava).

