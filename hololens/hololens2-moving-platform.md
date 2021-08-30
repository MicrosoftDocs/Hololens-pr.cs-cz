---
title: HoloLens 2 přesunutí režimu platformy
description: jak používat HoloLens na přesunu platforem
keywords: Přesun platforem, dynamického pohybu, HoloLens a přesunutí režimu platformy
author: evmill
ms.author: v-evmill
ms.reviewer: yabahman
ms.date: 8/10/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: high
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: a0717524cd1f762c92a5b821ae90acb8474dafd2
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190391"
---
# <a name="moving-platform-mode-on-low-dynamic-motion-moving-platforms"></a>Pohyb režimu platformy na nízkých dynamických pohybových platformách

v programu **Insider build 20348,1411** jsme přidali podporu beta pro sledování na vysoce dynamických pohybových platformách na HoloLens 2. po instalaci buildu a povolení režimu přesunu platforem budete moct použít HoloLens 2 v dříve nepřístupných prostředích, jako jsou velké lodě a velké mořské nádoby. V současné době je tato funkce zaměřená na povolování pouze těchto specifických přenosných platforem. I když vám nic nebrání v pokusu o použití funkce v jiných prostředích, funkce se zaměřuje na přidání podpory pro tato prostředí jako první.

> [!NOTE]
> tato funkce je v tuto chvíli dostupná jenom prostřednictvím [Windows insiders](hololens-insider.md).

![Příklad přesunu platformy.](./images/mpm-compare.gif)

Tento článek popisuje:

1. [Proč je potřeba přesunout platformu](#why-moving-platform-mode-is-necessary)
1. [Povoluje se režim přesunutí platformy.](#enabling-moving-platform-mode)

## <a name="why-moving-platform-mode-is-necessary"></a>Proč je potřeba přesunout režim platformy

aby bylo možné zobrazit stabilní hologramy, HoloLens musí být schopné sledovat polohu hlavní pozice pomocí [6 stupňů volnosti](https://en.wikipedia.org/wiki/Six_degrees_of_freedom) (X, Y, Z, překladu a změn, rozteč, yaw rotace). k tomu HoloLens sleduje dvě podobné informace ze dvou samostatných zdrojů:

1. Viditelné lehké kamery – které sledují prostředí, například fyzickou místnost, ve které používáte HoloLens
1. Inertial měření jednotek (IMU), která se skládá z akcelerometru, vybavený gyroskopem a magnetometer, která sleduje pohyb a orientaci hlav vzhledem k zemi

Informace z těchto dvou zdrojů jsou složené, aby bylo možné sledovat polohu hlavní pozice s nízkou latencí a dostatečně vysokou frekvencí, aby bylo možné vykreslovat hladké hologramy.

Tento přístup ale spoléhá na kritický předpoklad; prostředí (sledované kamerami) zůstává v klidu vzhledem k zemi (na kterou IMU může provádět měření). Pokud to není v takovém případě, jako na člunu ve vodě, mohou být informace z obou zdrojů v konfliktu s jiným zdrojem a způsobit ztrátu tohoto sledovacího procesu. Tento konflikt vytváří nesprávné informace o poloze a vede k Swimmy hologramů nebo dokonce sledování ztrát.

Přemístění tohoto problému pro režim platformy Když povolíte režim přesunutí, který je nápovědou k našemu sledování, které nemůžeme na základě našich vstupů na senzory plně souhlasit. Místo toho je potřeba spoléhat na vizuální sledování a rychle identifikovat incongruous data o pohybu Inertial a vyfiltrovat je, aby bylo možné použít vstup IMU.

## <a name="supported-environments-and-known-limitations"></a>Podporovaná prostředí a známá omezení

Během přesouvání režimu platformy bylo vyvinuto Inteligentní zpracování případů Inertial a vizuálního konfliktu dat. v současné době má velký počet plavidel, u kterých dochází k nedostatečnému dynamickému pohybu. To znamená, že existují omezení na určitě a nepodporované scénáře.

### <a name="known-limitations"></a>Známá omezení

- Jediným podporovaným prostředím pro režim přesouvání platforem (MPM) jsou velké mořské nádoby s nízkým dynamickým pohybem. Jinými slovy, mnoho běžných prostředí/situací **se ještě nepodporuje** kvůli jejich vysoké frekvencí a vysokému množství akcelerace a [Jerk](https://en.wikipedia.org/wiki/Jerk_(physics)). Například: roviny, vlaky, automobily, kola, autobusy, malé čluny, výtahy atd.
- pokud je povolený MPM, může Hologramy wobble mírně, zejména v případě nestabilní vody.
- Nic nebrání uživatelům v pokusu o použití MPM v nepodporovaných prostředích, ale pokud je zařízení schopné udržovat sledování v nepodporovaném prostoru, může docházet k nežádoucím vedlejším účinkům. Například u MPM můžou uživatelé najít možnost použít v výtahu a přitom měnit podlahu, zatímco to bylo předtím nemožné. Ale MPM umožňuje, aby zařízení udržovalo sledování, ale v tuto chvíli nezpracovává správu map. Uživatelé zjistí, že změna podlaží v výtahu způsobí, že zařízení Zaměňujte horní a dolní podlahu a negativně ovlivní kvalitu mapy.

## <a name="prerequisites"></a>Požadavky

Podpora beta verzí pro režim přesunu platforem vyžaduje jenom několik požadavků:

1. Nainstalujte Build 20348,1411 nebo novější [pomocí blikání nejnovějších buildů Insider prostřednictvím ARC](hololens-insider.md#ffu-download-and-flash-directions) nebo [registraci a aktualizace zařízení](hololens-insider.md#start-receiving-insider-builds).

   > [!NOTE]
   > Toto sestavení je v tuto chvíli dostupné jenom na [vývojářském kanálu Insider](hololens-insider.md#start-receiving-insider-builds).

2. Povolit [vývojářský režim a portál zařízení](/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

## <a name="enabling-moving-platform-mode"></a>Povoluje se režim přesunutí platformy.

Pokud chcete povolit režim přesunu platforem, nejdřív [Povolte portál zařízení](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).

1. V nabídce na levé straně vyberte **systém** pro přiznávání.

   ![První obrázek.](.\images\moving-platform-1w.png)

2. Vyberte stránku **režim přesunutí platformy** a zaškrtněte políčko **režim přesunutí platformy** .

    ![Druhý obrázek.](.\images\moving-platform-2z.png)

3. Po zobrazení výzvy s upozorněním vyberte **OK** .

   ![Třetí obrázek.](.\images\moving-platform-3w.png)

4. Restartujte zařízení, což lze provést buď pomocí nabídky **napájení** na portálu zařízení v pravém horním rohu, nebo vyvoláním následujícího hlasového příkazu &quot; restartujte zařízení &quot; a vyberte &quot; Ano &quot; .

   ![Čtvrtý obrázek.](.\images\moving-platform-4z.png)

Pokud nevidíte možnost režimu přesunu platforem na portálu zařízení, pravděpodobně to znamená, že ještě nejste na správném buildu. Přečtěte si část [požadavky](#prerequisites) .

## <a name="reporting-issues"></a>Vytváření sestav – problémy

Jak je uvedeno výše, tato funkce je beta verze dostupná jenom v režimu pro vývojáře, což znamená, že se můžete setkat s problémy. Pokud k tomu dojde, můžeme produkt prozkoumat a vylepšit, prosím

1. Nahlaste problém prostřednictvím [centra Feedback](hololens-feedback.md) v kategorii **přesnost, stabilita a spolehlivost hologramu** a zahrňte:
    1. Popis problému, včetně očekávaného chování a chování
    1. [Video](holographic-photos-and-videos.md#capture-a-mixed-reality-video) o navýšení problému ve smíšené realitě
2.  Otevřete případ podpory [https://aka.ms/hlsupport](https://aka.ms/hlsupport) a sdílejte adresu URL centra zpětné vazby, abychom se mohli obrátit na případ, kdy máme následné otázky.