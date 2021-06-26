---
title: Aspekty prostředí HoloLens
description: Při optimalizaci zařízení pro vaše oči a prostředí získejte nejlepší možné prostředí pomocí HoloLens.
author: dorreneb
ms.author: dobrown
manager: jarrettr
ms.date: 8/29/2019
ms.prod: hololens
ms.topic: article
audience: ITPro
ms.localizationpriority: high
keywords: holographic frame, field of view, fov,ádaný, prostory, prostředí, postupy, HoloLens, hybridní realita, náhlavní soupravy hybridní reality
ms.openlocfilehash: 6976527d759e768fa5da72f96395a8b7b390cefd
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924345"
---
# <a name="hololens-environment-considerations"></a>Aspekty prostředí HoloLens

HoloLens spojuje holographic s "skutečným" světem a umístí hologramy do okolí. Na zdi se "zablokuje" holografické okno aplikace, holografické míče se otáčí na s tabletopu a nad hlavičkou vašeho nevědomého přítele se posadí. Když používáte imerzivní hru nebo aplikaci, holografický svět se rozprostíří, aby vyplnil vaše okolí, ale stále můžete prostor vidět a pohybovat se.

Hologramy, které najdete, zůstanou tam, kam je dáte, i když zařízení vypnete.

## <a name="setting-up-an-environment"></a>Nastavení prostředí

Zařízení HoloLens vědí, jak umístit stabilní a přesné hologramy sledováním *uživatelů* v prostoru. Bez správného sledování zařízení nerozumí prostředí ani uživateli, který je v ní. Hologramy se dají zobrazit na nesprávných místech, nemusí se pokaždé zobrazovat na stejném místě nebo se vůbec nezobrazují. Data používaná ke sledování uživatelů jsou reprezentována v *prostorové mapě*.  

Sledování výkonu je silně ovlivněno prostředím, ve které se uživatel nachází, a ladění prostředí tak, aby vyvolalo stabilní a konzistentní sledování, je spíše umění než věda. Mnoho různých faktorů prostředí je pro sledování směšovaných dohromady, ale jako vývojář Mixed Reality existuje několik faktorů, na které byste měli mít na paměti vyladění prostoru pro lepší sledování.

### <a name="lighting"></a>Osvětlení

Windows Mixed Reality používá vizuální světlo ke sledování polohy uživatele. Pokud je prostředí příliš jasné, mohou se fotoaparáty nasytá a nic se nezůstane vidět. Pokud je prostředí příliš tmavé, fotoaparáty nezískaní dostatek informací a nic se tu nezůstá. Osvětlení by mělo být rovnoměrně a dostatečně jasné, jak může člověk vidět bez námahy, ale ne tak jasné, na které světlo se má dívat.  

Problematické jsou také oblasti s jasným světlem v oblasti celkového tlumení, protože při pohybu mezi jasnými prostory se musí kamera upravit. To může způsobit, že se zařízení "ztratí" a bude si myslet, že změna světla se rovná změně polohy. Stabilní úrovně světla v oblasti povedou k lepšímu sledování.  

Jakékoli venkovní osvětlení může také způsobit nestabilitu ve sledování, protože slunce se může v průběhu času výrazně lišit. Například sledování ve stejném prostoru v letním a ročním období může vést k výrazně odlišným výsledkům, protože druhé světlo mimo oblast může být v různých obdobích roku vyšší.  

Pokud máte seznam, je dobrým místem, kde začít, stabilní 500–1 000 krát.  

#### <a name="types-of-lighting"></a>Typy osvětlení

Sledování mohou ovlivnit také různé typy světla v prostoru. Žárovky prochádí elektřinu ze střídavého napětí – pokud je frekvence střídavého napětí 50 Hz, žárovka se rozsvítí na 50 Hz. Člověk si toho všimne. Tyto změny ale vidí kamera HoloLens 30 fps – některé snímky budou dobře rozsvícené, některé budou špatně rozsvícené a některé budou překryté, když se fotoaparát pokusí kompenzovat světlé impulzy.  

V USA je standard frekvence elektřiny 60 Hz, takže se žárovkové impulzy nasažují pomocí rámové frekvence HoloLens – 60 Hz pulse, které jsou v souladu s rámovkou HoloLens 30 FPS. Mnoho zemí má ale frekvenci ac standardu 50 Hz, což znamená, že některé snímky HoloLens budou pořízeny během impulzu a jiné ne. Konkrétně je známo, že osvětlení v Evropě způsobuje problémy.  

Existuje několik věcí, které můžete zkusit vyřešit při řešení blikajících problémů. Běžnými příčinami blikání teploty, stáří žárovky a zahřejení jsou cykly, které mohou pomoci při nahrazování žárovky. Můžou vám pomoct také zpřísnění žárovky a ujistěte se, že aktuální tahy jsou konstantní.  

### <a name="items-in-a-space"></a>Položky v prostoru

HoloLens používá jedinečné orientační body prostředí, označované také jako funkce *,* k umístění sebe sama v prostoru.  

Zařízení téměř nikdy nemůže sledovat v oblasti s špatnými funkcemi, protože zařízení nemá žádný způsob, jak zjistit, kde se nachází v prostoru. Přidání prvků do zdí prostoru je obvykle dobrým způsobem, jak zlepšit sledování. Pomáhají plakáty, symboly při klepnutí na zeď, rostliny, jedinečné objekty nebo jiné podobné položky. Dobrým příkladem prostředí, které vede k dobrému sledování, je schůdný pracovní prostor – v jedné oblasti je spousta různých funkcí.  

Kromě toho používejte jedinečné funkce ve stejném prostoru. Například stejný plakát, který se několikrát opakuje nad zdí, způsobí zmatky zařízení, protože HoloLens nebude vědět, na který z opakujících se plakátů se dívá. Jedním z běžných možností, jak přidat jedinečné prvky, je použití čar maskovací pásky k vytvoření jedinečných, netýkajících se vzorů podél zdí a podlahy prostoru.  

Dobrá otázka, kterou byste si měli položit: kdybyste viděli jen malé množství scény, mohli byste se v prostoru jedinečného umístění? Pokud ne, bude mít zařízení pravděpodobně také problémy se sledováním.

#### <a name="wormholes"></a>Červí díry

Pokud máte dvě oblasti nebo oblasti, které vypadají stejně, může si sledování myslet, že jsou stejné. To vede k tomu, že se zařízení ošidí, aby si myslelo, že je někde jinde. Těmto typům opakujících se oblastí říkáme *wormholes*.  

Pokud chcete zabránit vzniku wormholů, zkuste zabránit identickým oblastem ve stejném prostoru. Identické oblasti mohou někdy zahrnovat stanice továrny, okna v budově, serverové racky nebo pracovní stanice. Oblasti označování nebo přidávání jedinečných funkcí do každé podobné oblasti můžou pomoct zmírnit wormholy.

### <a name="movement-in-a-space"></a>Pohyb v prostoru

Pokud se vaše prostředí neustále přesouvá a mění, nemá zařízení žádné stabilní funkce, které by bylo možné najít.  

Čím více přesouvaných objektů je v prostoru, včetně lidí, tím jednodušší je ztratit sledování. O přesunu dopravníkových pásů, položek v různých stavech konstrukce a spousty lidí v prostoru je známo, že způsobují problémy se sledováním.

HoloLens se může rychle přizpůsobit těmto změnám, ale jenom v případě, že je tato oblast pro zařízení jasně viditelná. Oblasti, které nejsou tak často vnícené, mohou zaostávat za realitou, což může způsobit chyby v prostorové mapě. Uživatel například prohledá přátele a pak se otočí, zatímco přítel odejde z místnosti. "Stínová" reprezentace přítele se zachová v datech prostorového mapování, dokud uživatel znovu nenaskenuje nyní prázdné místo.

### <a name="proximity-of-the-user-to-items-in-the-space"></a>Blízkost uživatele k položkám v prostoru

Podobně jako se lidé nezostření dobře na objekty blízko očí, HoloLens se potýkají s tím, když jsou objekty blízko kamer. Pokud je objekt příliš blízko k tomu, aby byl vidět u obou fotoaparátů, nebo pokud objekt blokuje jeden fotoaparát, bude mít zařízení mnohem více problémů se sledováním objektu.  

Fotoaparáty neuvidí objekt blíže než 15 cm.

### <a name="surfaces-in-a-space"></a>Povrchy v prostoru

Silně odrazivé povrchy budou pravděpodobně vypadat jinak v závislosti na úhlu, který má vliv na sledování. Představte si zcela nové auto – když se pohybujete kolem něj, světlo se odráží a při pohybu uvidíte na povrchu různé objekty. Pro sledování představují různé objekty na povrchu měnící se prostředí a zařízení ztratí sledování.

Méně blýskaných objektů se snadněji sleduje.

### <a name="wi-fi-fingerprint-considerations"></a>Wi-Fi otisků prstů

Pokud je Wi-Fi povoleno, budou data mapy korelovat s otiskem prstu Wi-Fi, i když nejsou připojená ke skutečné síti nebo směrovači Wi-Fi. Bez Wi-Fi informací může být rozpoznání prostoru a hologramů o něco pomalejší. Pokud se Wi-Fi výrazně změní, může si zařízení myslet, že je zcela v jiném prostoru.

Identifikace sítě (například SSID nebo ADRESA MAC) se microsoftu neposílána a všechny referenční Wi-Fi se na HoloLens uchovávají místně.

## <a name="mapping-new-spaces"></a>Mapování nových prostorů

Když zadáte novou mezeru (nebo načtete existující mezeru), uvidíte, jak se nad prostorem rozprostíří obrázek sítě. To znamená, že vaše zařízení mapovat vaše okolí. Zatímco HoloLens se naučí prostor v průběhu času, existují tipy a triky pro mapování prostorů.

## <a name="environment-management"></a>Správa prostředí

Existují dvě nastavení, která uživatelům umožňují "vyčistit" hologramy a způsobit, že HoloLens "zapomene" prostor. Existují v **hologramech** a prostředích v aplikaci nastavení, druhé  nastavení se také zobrazí v části Ochrana osobních údajů v aplikaci nastavení.  

1. **Odstraňte hologramy v okolí.** Když toto nastavení vyberete, HoloLens vymaže všechny ukotvené hologramy a všechna uložená data mapy pro "aktuální prostor", kde se zařízení nachází. Jakmile se hologramy znovu umístí do stejného prostoru, vytvoří se nový oddíl mapy, který se uloží do databáze pro toto umístění.

1. **Odstraňte všechny hologramy**. Když vyberete toto nastavení, HoloLens vymaže VŠECHNA data mapy a ukotvené hologramy v celých databázích prostorů. Nebudou znovu zjištěny žádné hologramy a všechny hologramy musí být nově umístěny, aby bylo možné znovu ukládat oddíly mapy v databázi.

## <a name="hologram-quality"></a>Kvalita hologramu

Hologramy můžete umístit do celého prostředí – vysoké, nízké a kolem vás – ale uvidíte je prostřednictvím [holografického](/windows/mixed-reality/holographic-frame) rámečku, který se nachází před vašimi pohledy. Pokud chcete získat nejlepší zobrazení, nezapomeňte upravit zařízení, abyste viděli celý snímek. A neváhejte procházet vaše prostředí a zkoumat je!

Aby [vaše hologramy](/windows/mixed-reality/hologram) vypadaly nesvěceně, jasně a stabilní, musí být holoLens nakalibrován právě pro vás. Při prvním nastavení HoloLens vás tento proces provede. Později, pokud hologramy nevypadá správně nebo dochází k mnoha chybám, můžete provést úpravy.

Pokud máte potíže s mapováním prostorů, zkuste odstranit hologramy v okolí a přemapovat prostor.

### <a name="calibration"></a>Kalibrace

Pokud hologramy vypadají zašiměvěně nebo roztřásněně, nebo pokud máte potíže s umístěním hologramů, je první věcí, kterou je třeba vyzkoušet, [aplikaceČísi.](hololens-calibration.md) Tato aplikace může také pomoci, pokud při používání HoloLens máte nějaký nepohodlí.

Pokud se chcete dostat do aplikace pro kalibraci, použijte **Nastavení**  >  **systémové**  >  **nástroje**. Vyberte **otevřít kalibraci** a postupujte podle pokynů.

Pokud bude vaše HoloLens používat někdo jiný, musí nejdřív spustit aplikaci pro kalibraci, aby bylo zařízení pro ně správně nastavené.

## <a name="temperature-and-regulatory-information"></a>Informace o teplotě a regulativních informacích

[Informace o legislativních zákonech](https://support.microsoft.com/en-us/help/13761/hololens-regulatory-information): obsahuje informace o teplotním rozsahu, vyřazení, přepínači a porušování TV a dalších.

Podívejte se na podrobnosti o "HoloLens" v [materiálech a látkách](https://www.microsoft.com/legal/compliance/materials-substances) > dosahuje článku 33 informace o dodržování předpisů v oblasti životního prostředí (PDF).

Tady jsou některé pokyny, jak při používání zařízení použít:

1. Uložení zařízení v prostředí v rozmezí teplot (v úsporném režimu nebo vypnuto) po hodinu, než se zařízení použije.
1. Použití zařízení v prostředí v rozmezí teplot.
1. Použijte dvířka zařízení.
1. Používat zařízení ve stínovém nádechu; i nedvířka zabraňují přímému slunečnímu záření, i když se jedná o Windows nebo světlíky.
1. Pokud budete postupovat podle výše uvedených pokynů, ale dojde k neočekávaným potížím s přehříváním, postupujte podle následujících kroků pro odeslání [zpětné vazby](hololens-feedback.md). 
    1. Ujistěte se, že je v zařízení povolená **plná** nebo **volitelná** telemetrie. Pokud tomu tak není, povolte ji. 
    >[!CAUTION]
    > Telemetrii není zpětně dostupná pro tepelné události – musí být povolená během přehřívání nebo nebudou zachycena požadovaná data.
    
    2. Reprodukování problému s vyhříváním
    3. Uveďte datum a čas, kdy došlo k přehřívání.
    4. Odeslat [názor](hololens-feedback.md).

## <a name="see-also"></a>Viz také

- [Návrh prostorového mapování](/windows/mixed-reality/spatial-mapping)
- [Hologramy](/windows/mixed-reality/hologram)
