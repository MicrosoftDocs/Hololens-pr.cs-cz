---
title: Namapujte fyzické mezery pomocí HoloLens
description: HoloLens se dozvíte, co v průběhu času vypadá prostor. uživatelé můžou tento proces usnadnit přesunutím HoloLens určitým způsobem prostřednictvím prostoru.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: hololens, Windows Mixed Reality, návrh, prostorové mapování, HoloLens, rekonstrukce povrchu, síť, sledování hlav, mapování
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: b8bda049f0ef4610dcf0ca6fe81d89dd5a316e3e
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428827"
---
# <a name="map-physical-spaces-with-hololens"></a>Namapujte fyzické mezery pomocí HoloLens

HoloLens blendy s vaším fyzickým světem. aby to bylo možné, HoloLens se musí dozvědět o fyzickém světě kolem vás a zapamatovat si, kam umístíte hologramy v daném prostoru.

v průběhu času HoloLens vytvoří *prostorovou mapu* prostředí, které viděli.  HoloLens aktualizuje mapu jako změny prostředí. pokud jste přihlášeni a zařízení je zapnuté, HoloLens vytvoří a aktualizuje vaše prostorové mapy. pokud zařízení s kamerami v prostoru podržíte nebo ho chcete používat, HoloLens se pokusí tuto oblast namapovat. i když se HoloLens učí prostor přirozeně v průběhu času, existují způsoby, jak můžete HoloLens lépe namapovat prostor rychleji a efektivně.  

> [!NOTE]
> pokud vaše HoloLens nemůže namapovat váš prostor nebo se nejedná o kalibraci, HoloLens může vstoupit do omezeného režimu. V omezeném režimu nebudete moci do okolí umístit hologramy.

tento článek vysvětluje, jak HoloLens mapuje prostory, jak vylepšit prostorové mapování a jak spravovat prostorová data, která HoloLens shromažďuje.

## <a name="choosing-and-setting-up-and-your-space"></a>Výběr a nastavení prostoru

funkce ve vašem prostředí můžou ztížit HoloLens interpretovat místo. světlé úrovně, materiály v prostoru, rozložení objektů a další mohou mít vliv na to, jak HoloLens mapují oblast.

HoloLens nejlépe funguje v určitých druzích prostředí. Chcete-li vytvořit nejlepší prostorovou mapu, vyberte místnost, která má adekvátní světlo a dostatek místa. Vyhněte se tmavém prostorům a místnostem, které mají hodně tmavé, lesklé nebo průsvitné povrchy (např. zrcadle nebo gauzy Curtains).

HoloLens je optimalizovaná pro použití v interiéru. Prostorové mapování také funguje nejlépe, když je zapnuto Wi-Fi, i když není nutné ho připojit k síti. HoloLens může získat Wi-Fi přístupových bodů i v případě, že není připojený nebo ověřený. funkce HoloLens nemění, jestli jsou přístupové body jenom připojené k internetu nebo intranet/místní.

používejte HoloLens jenom na bezpečných místech bez nebezpečí tripí. [Další informace o zabezpečení](https://support.microsoft.com/help/4023454/safety-information).

## <a name="mapping-your-space"></a>Mapování prostoru

Teď jste připraveni začít s mapováním svého náhradního.  když HoloLens začne namapovat okolí, uvidíte, že se v prostoru rozprostře obrázek.  Na domovské stránce hybridní reality můžete aktivovat mapu, která se zobrazí, když vyberete namapovanou plochu.

Tady jsou pokyny pro vytvoření Skvělé prostorové mapy.

### <a name="understand-the-scenarios-for-the-area"></a>Pochopení scénářů oblasti

je důležité strávit to nejvíce času, kdy budete HoloLens používat, aby byla mapa relevantní a kompletní. pokud například scénář pro uživatele pro HoloLens zahrnuje přesun z bodu a do bodu B, projde se cesta dvě až třikrát a při přesunu se hledají všechny směry.  

### <a name="walk-slowly-around-the-space"></a>Pomaleji kolem prostoru

pokud procházíte příliš rychle kolem oblasti, je pravděpodobný, že HoloLens nepřijde o oblasti mapování. Projděte si pomalu kolem prostoru a zastavte se každých 5-8 metrů, abyste se mohli podívat do okolí.  

plynulé pohyby také pomůžou mapu HoloLens efektivněji.

### <a name="look-in-all-directions"></a>Prohlédněte si všechny směry

při namapování prostoru je HoloLens více dat, kde jsou vzájemně relativní.  

pokud nenajdete například HoloLens nemusí znát, kde je strop v místnosti.  

Nezapomeňte se podívat na podlahu při mapování prostoru.

### <a name="cover-key-areas-multiple-times"></a>Přikrýt klíčové oblasti několikrát

Pohyb přes oblast několikrát pomůže vybrat funkce, které se vám v prvním návodu nemusely vystavit. Chcete-li vytvořit ideální mapu, zkuste přesměrovat oblast dvě na třikrát.

Pokud je to možné, při opakování těchto přesunů tráví čas procházením oblasti v jednom směru a pak se přepíná a vrátí zpět způsob, jakým jste dostali.

### <a name="take-your-time-mapping-the-area"></a>Pořídit čas mapování oblasti

může trvat 15 až 20 minut, než se HoloLens plně namapuje a upraví na jeho okolí. pokud máte prostor, ve kterém plánujete použít HoloLens často, zajistěte, aby tento čas ještě před tím, než bude možné problémy, nedocházelo k problémům později.  

## <a name="possible-errors-in-the-spatial-map"></a>Možné chyby v prostorové mapě

Chyby v prostorových mapováních dat spadají do několika kategorií:

- *Díry*: reálné povrchy chybí v datech prostorového mapování.
- *Hallucinations*: povrchy existují v datech prostorového mapování, která neexistují v reálném světě.
- *červi děr*: HoloLens ztratí část prostorové mapy tím, že je v jiné části mapy, než je ve skutečnosti.
- *Bias*: povrchy v datech mapování prostorových dat jsou nedokonalé zarovnané na reálné plochy, ať už jsou, nebo jsou připravené.

Pokud se zobrazí některá z těchto chyb, pošlete nám svůj názor pomocí [FeedbackHub](hololens-feedback.md) .

## <a name="security-and-storage-for-spatial-data"></a>Zabezpečení a úložiště pro prostorová data

Windows 10 aktualizace verze 1803 pro Microsoft HoloLens a novější ukládá data mapování v místní databázi (v zařízení).

HoloLens uživatelé nemají přímý přístup k databázi map, i když je zařízení zapojené do počítače nebo při použití aplikace průzkumník souborů. když je na HoloLens povolený BitLocker, uložená data mapy se taky šifrují spolu s celým svazkem.

### <a name="remove-map-data-and-known-spaces-from-hololens"></a>Odebrat data mapy a známé mezery z HoloLens

existují dvě možnosti odstranění dat mapy v **Nastavení > systému > Hologramy**:

- Pokud chcete odstranit okolní hologramy, vyberte **Odebrat okolní hologramy**. Tento příkaz vymaže data mapy a ukotvené hologramy pro aktuální prostor. Pokud zařízení budete nadále používat ve stejném prostoru, vytvoří a uloží značku nové mapy, která nahradí odstraněné informace.

   > [!NOTE]
   > "Okolní" hologramy jsou hologramy, které jsou ukotveny v rámci stejné části mapy v aktuálním prostoru.

   Tuto možnost můžete například použít k vymazání dat mapy, která se vztahují k práci bez vlivu na data map v domácnosti.

- Pokud chcete odstranit všechny hologramy, vyberte **Odebrat všechny hologramy**. Tento příkaz vymaže všechna data mapy, která jsou uložená v zařízení, i všechny ukotvené hologramy. Budete muset explicitně umístit všechny hologramy. Nebudete moct znovu zjistit dříve umístěné hologramy.

> [!NOTE]
> po odebrání okolních nebo všech hologramů HoloLens hned spustit skenování a mapování aktuálního místa.

### <a name="wi-fi-data-in-spatial-maps"></a>Data Wi-Fi v prostorových mapách

HoloLens ukládá Wi-Fi charakteristiky, které vám pomůžou korelovat umístění a mapy na hologramech, které jsou uložené v databázi HoloLens se známými prostory. Informace o vlastnostech Wi-Fi nejsou dostupné pro uživatele a neodesílají se do Microsoftu pomocí cloudu nebo pomocí telemetrie.

pokud je povolená Wi-Fi, HoloLens koreluje data map s okolními Wi-Fi přístupovými body. Neexistují žádné rozdíly v chování, ať už je síť připojená nebo jenom zjištěná v blízkosti. pokud je Wi-Fi zakázané, HoloLens pořád vyhledává místo. HoloLens ale musí vyhledat více dat mapy v rámci databáze prostorů a může pro hledání hologramů potřebovat více času. bez Wi-Fi informací musí HoloLens porovnat aktivní kontroly se všemi hologramy na hologramech a mapovat oddíly, které jsou uložené na zařízení, aby bylo možné najít správnou část mapy.

## <a name="related-topics"></a>Související témata

- [Návrh prostorového mapování](/windows/mixed-reality/spatial-mapping)
