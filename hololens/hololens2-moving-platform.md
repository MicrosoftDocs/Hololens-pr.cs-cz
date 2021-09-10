---
title: HoloLens 2. Režim přesunutí platformy
description: Jak používat HoloLens na mobilních platformách
keywords: moving platforms, dynamic motion, hololens, moving platform mode
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
ms.openlocfilehash: 81b3231827fce9a2ae2d5e3105800685fedb917b
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428689"
---
# <a name="moving-platform-mode-on-low-dynamic-motion-moving-platforms"></a>Přesun režimu platformy na platformách s nízkým dynamickým pohybem

V **buildu Insider 20348.1411** jsme přidali podporu beta verze pro sledování na platformách s pohyblivou nízkou dynamickou pohybu na HoloLens 2. Po instalaci buildu a povolení moving platformového režimu budete moct používat HoloLens 2 v dříve nepřístupných prostředích, jako jsou velké lodi a velké dechy. V současné době je tato funkce zaměřená pouze na povolení těchto konkrétních pohyblivých platforem. I když vám nic nebrání ve pokusu o použití této funkce v jiných prostředích, tato funkce se zaměřuje nejprve na přidání podpory těchto prostředí.

> [!NOTE]
> Tato funkce je aktuálně dostupná pouze prostřednictvím [Windows Insider.](hololens-insider.md)

![Příklad přesunu platformy](./images/mpm-compare.gif)

Tento článek se věnuje:

1. [Proč je přesun platformy nezbytný](#why-moving-platform-mode-is-necessary)
1. [Povolení přesunu režimu platformy](#enabling-moving-platform-mode)

## <a name="why-moving-platform-mode-is-necessary"></a>Proč je nutný přesun režimu platformy

HoloLens být schopni sledovat pozici hlavy s [6](https://en.wikipedia.org/wiki/Six_degrees_of_freedom) stupni volnosti (X, Y, Z, překlad a rolování, sklon, rotace yaw), aby bylo možné zobrazit stabilní hologramy. Za tím HoloLens sleduje dva podobné informace ze dvou samostatných zdrojů:

1. Viditelné světlé kamery – které sledují prostředí, například fyzickou místnost, ve které používáte HoloLens
1. Inerciální měrná jednotka (IMU), která se skládá z akcelerometru,scopeu a nakometru, který sleduje pohyb a orientaci hlavy vzhledem k Zemi

Informace z těchto dvou zdrojů jsou složené, aby bylo možné sledovat vaši pozici hlavy s nízkou latencí a vysokou frekvencí, aby bylo možné vykreslit hladké hologramy.

Tento přístup se ale spoléhá na kritický předpoklad. Prostředí (sledované fotoaparáty) zůstává ve srovnání se Zemí neměnné (vůči kterému může IMU provádět měření). Pokud tomu tak není, mohou být informace z obou zdrojů v konfliktu mezi sebou, podobně jako na tesařce ve vody, a způsobit tak ztrátu sledování. Tento konflikt vede k nesprávným informacím o poloze a vede k hologramům v plaveckých plácích nebo dokonce ke sledování ztráty.

Přesunutí režimu platformy tento problém řeší. Když povolíte režim Moving Platform Mode (Pohyblivá platforma), je to nápověda našeho snímače, že nemůžeme spoléhat na to, že vstupy ze snímačů se navzájem za všech okolností zcela odsouhlasí. Místo toho musíme do značné míry spoléhat na vizuální sledování a rychle identifikovat nekonstrukční inerciální data pohybu a odpovídajícím způsobem je odfiltrovat, než budeme moct použít vstup IMU.

## <a name="supported-environments-and-known-limitations"></a>Podporovaná prostředí a známá omezení

I když byl vývoj režimu moving platformy pro inteligentní zpracování případů inerciálního a vizuálního konfliktu dat, je v současné době vymezený na velké problémy s nízkým dynamickým pohybem. To znamená, že existují určitě omezení a nepodporované scénáře.

### <a name="known-limitations"></a>Známá omezení

- Jedinými podporovanými prostředími pro přesun režimu platformy (MPM) jsou velká prostředí s nízkým dynamickým pohybem. Jinými slovy, řada běžných prostředí/situací se zatím nepodporuje kvůli vysoké frekvenci pohybu a vysoké úrovni zrychlení a [zrychlení.](https://en.wikipedia.org/wiki/Jerk_(physics))  Například: roviny, trénování, auta, kola, auta, auta, malé výtahy, výtahy atd.
- Hologramy povoleném MPM se může mírně zmátnout, zejména pokud je na tekoucí vody.
- Nic nebrání uživatelům v pokusech o použití MPM v nepodporovaných prostředích, ale pokud je zařízení schopné udržovat sledování v nepodporovaném prostoru, může docházet k nežádoucím vedlejším účinkům. Například u MPM mohou uživatelé zjistit, že je možné použít ve výtahu při změně podlaží, zatímco to bylo dříve nemožné. Přestože MPM bohužel umožňuje zařízení udržovat sledování, v tuto chvíli správu map nezvládá. Uživatelé zjistí, že změna podlaží ve výtahu způsobí, že zařízení zmást horní a dolní podlaží a negativně ovlivní kvalitu mapy.

## <a name="prerequisites"></a>Požadavky

Podpora beta verze pro přesun režimu platformy vyžaduje jenom několik požadavků:

1. Nainstalujte build 20348.1411 nebo novější tím, že flash disk s nejnovějšími buildy [Insider](hololens-insider.md#ffu-download-and-flash-directions) sestaví přes ARC nebo zaregistrujete a [aktualizujete zařízení.](hololens-insider.md#start-receiving-insider-builds)

   > [!NOTE]
   > Toto sestavení je aktuálně k dispozici pouze na [vývojářském kanálu Insider.](hololens-insider.md#start-receiving-insider-builds)

2. Povolení [vývojářského režimu a Portál zařízení](/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

## <a name="enabling-moving-platform-mode"></a>Povolení přesunu režimu platformy

Pokud chcete povolit režim Přesunutí platformy, [nejprve povolte Portál zařízení](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).

1. V nabídce **vlevo** vyberte dohodu System (Systém).

   ![První obrázek.](.\images\mpm-01.png)

2. Vyberte stránku **Moving Platform Mode (Režim přesunu** platformy) a zaškrtněte **políčko Moving Platform Mode (Režim přesunu platformy).**

    ![Druhý obrázek.](.\images\mpm-02.png)

3. Po zobrazení výzvy s upozorněním vyberte **OK.**

   ![Třetí obrázek.](.\images\mpm-03.png)

4. Restartujte zařízení. Můžete to udělat buď prostřednictvím nabídky Portál zařízení **Power** v pravém horním rohu, nebo vydáním následujícího hlasového příkazu Restartujte zařízení a &quot; vyberte &quot; &quot; &quot; Ano.

   ![Čtvrtý obrázek.](.\images\mpm-04.png)

Pokud se vám možnost Moving Platform Mode (Režim přesunu platformy) v Portál zařízení, pravděpodobně to znamená, že ještě nejste ve správném sestavení. Viz [část Požadavky.](#prerequisites)

## <a name="reporting-issues"></a>Hlášení problémů

Jak je uvedeno výše, tato funkce je beta verze dostupná jenom v režimu pro vývojáře, což znamená, že může dojít k problémům. Pokud k tomu dojde, můžeme produkt prozkoumat a vylepšit.

1. Nahlásit problém prostřednictvím [Centrum Feedback](hololens-feedback.md) kategorii Přesnost, stabilita **a spolehlivost hologramu a** zahrňte:
    1. Popis problému, včetně očekávaného chování a chování
    1. Záznam Mixed Reality [videa o](holographic-photos-and-videos.md#capture-a-mixed-reality-video) problému
2.  Otevřete případ podpory na adrese a nasdílejte adresu URL Centrum Feedback, abychom se mohli s vámi podělit pro případ, že budeme mít [https://aka.ms/hlsupport](https://aka.ms/hlsupport) následné dotazy.