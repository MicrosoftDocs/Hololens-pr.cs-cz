---
title: Předpoklady pro prostředí HoloLens
description: Když optimalizujete zařízení pro vaše oči a prostředí, získáte nejlepší možné prostředí pomocí HoloLens.
author: dorreneb
ms.author: dobrown
manager: jarrettr
ms.date: 8/29/2019
ms.prod: hololens
ms.topic: article
audience: ITPro
ms.localizationpriority: high
keywords: holografický rámec, pole zobrazení, FOV, kalibrace, mezery, prostředí, postupy, HoloLens, hybridní realita, náhlavní souprava Mixed reality
ms.openlocfilehash: f4d3feb379a1f9815b940614fcd4b29b062f5cdc
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379278"
---
# <a name="hololens-environment-considerations"></a>Předpoklady pro prostředí HoloLens

HoloLens se smíchá s hologramem "reálného" světa a dává na svém okolí své hologramy. Okno holografické aplikace "přestane reagovat" na stěně, holografické Ballerina se na Tabletop, Bunny EARS, na hlavní straně vašeho přítele v věděl. Pokud používáte moderní hru nebo aplikaci, bude se v holografickém světě rozložit na vaše okolí, ale pořád se můžete podívat a pohybovat kolem místa.

Hologramy, které zadáte, zůstanou tam, kde je umístíte, a to i v případě, že zařízení vypnete.

## <a name="setting-up-an-environment"></a>Nastavení prostředí

Zařízení HoloLens vědí, jak umístit stabilní a přesné hologramy díky *sledování* uživatelů v prostoru. Bez správného sledování zařízení nerozumí prostředí nebo uživateli v něm. Hologramy se můžou zobrazit na nesprávných místech, neobjeví se na stejném místě, pokaždé, když se neobjeví vůbec. Data použitá ke sledování uživatelů jsou reprezentována v *prostorové mapě*.  

Sledování výkonu je silně ovlivněno prostředím, ve kterém se uživatel nachází, a laděním prostředí pro podnět stabilního a konzistentního sledování je obrázek, nikoli vědy. K dispozici je celá řada různých faktorů prostředí, které umožňují sledování, ale jako vývojář hybridních realit, je k dispozici několik faktorů, které vám pomohou s vyladěním prostoru pro lepší sledování.

### <a name="lighting"></a>Osvětlení

Windows Mixed reality používá ke sledování umístění uživatele vizuální světlo. Když je prostředí moc jasné, můžou se kamery nasycené a nic se nezobrazuje. Pokud je prostředí moc tmavé, kamery nemůžou vyzvednout dostatek informací a nic se nezobrazuje. Osvětlení by mělo být rovnoměrné i dostatečně jasné, co člověk uvidí bez úsilí, ale ne tak jasné, že se bolestivý podívat na.  

V oblastech, kde jsou body jasně světla v celkové plošné oblasti, patří také problematické, protože fotoaparát je potřeba upravit při přesunu do a z jasných prostorů. To může způsobit ztrátu zařízení a zamyslete se nad tím, že se změna rozsvítí na změnu umístění. Stabilní světlé úrovně v oblasti budou mít za následek lepší sledování.  

Jakékoli osvětlení venku může také způsobit nestabilitu v rámci sledování, protože slunce se v průběhu času může značně lišit. Například sledování ve stejném prostoru v letním a zimním prostředí může způsobit drastické odlišné výsledky, protože druhá svítilna mimo jiné může být vyšší v různých časech roku.  

Pokud máte luxmeter, je vhodné začít na stabilní 500-1000 Lux.  

#### <a name="types-of-lighting"></a>Typy osvětlení

Sledování různých typů světla v prostoru může také ovlivnit. Žárovky se pulzují s elektrickou elektřinou běžící přes ni – Pokud je frekvence AC 50 Hz, pak se světelný impuls na 50 Hz. Pro člověka se tato pohonné aplikace nevšimla. Ale HoloLens "30 snímků na více než se tyto změny projeví – některé snímky budou dobře osvětleny, některé z nich budou špatně osvětlené a některé budou vystaveny dál, jako se kamera snaží kompenzovat světla.  

V USA je standardem frekvence elektřiny 60 Hz, takže žárovky v podžárovkách jsou harmonizovány pomocí snímkového kmitočtu HoloLens-60 Hz v souladu s snímkovým snímkem s frekvencí "30 FPS". Řada zemí ale má kmitočet standardu 50 Hz, což znamená, že se některé snímky HoloLens budou považovat za Pulse a jiné ne. Zejména bylo známo, že na fluorescenční osvětlení v Evropě došlo k potížím.  

Můžete zkusit vyřešit problémy s blikáním několika věcí. Teplota, věk žárovky a zahřívání cykly jsou běžné příčiny fluorescenčního blikání a nahrazení cibulí může pomáhat. Může také pomáhat posílit žárovky a zajistit, aby aktuální kreslení byly konstantní.  

### <a name="items-in-a-space"></a>Položky v prostoru

HoloLens používá jedinečné orientačních bodů, označované také jako *funkce*, aby je bylo možné najít v prostoru.  

Zařízení může téměř nikdy sledovat v nedostatečné oblasti funkcí, protože zařízení nemá žádný způsob, jak zjistit místo, kde se nachází. Přidávání funkcí do zdí prostoru je obvykle dobrým způsobem, jak vylepšit sledování. Plakáty, symboly pásky na zeď, rostliny, jedinečné objekty nebo jiné podobné položky. Pracovní stůl je dobrým příkladem prostředí, které vede k dobrému sledování – existuje spousta různých funkcí v jedné oblasti.  

Kromě toho používejte jedinečné funkce ve stejném prostoru. Stejný plakátový obraz se na zdi několikrát opakuje, například způsobí, že se zařízení nemění, protože HoloLens neví, na které z opakujících se plakátů prohlíží. Jedním z běžných způsobů přidávání jedinečných funkcí je použití čar maskování pásky k vytváření jedinečných, neopakujících se vzorů podél stěn a patra prostoru.  

Dobré dotazování: Pokud jste viděli jenom malou velikost scény, mohli byste jednoznačně najít v prostoru? V takovém případě bude pravděpodobně u zařízení i sledování problémů.

#### <a name="wormholes"></a>Červi děr

Pokud máte dvě oblasti nebo oblasti, které vypadají stejně, může se stát, že bude sledovat stejné. Výsledkem je, že se zařízení bude přesvědčit, že je někde jinde. Říkáme tyto typy opakovaných oblastí *èerví díry*.  

Chcete-li zabránit v červech děr, zkuste zabránit identickým oblastem ve stejném prostoru. Stejné oblasti můžou někdy zahrnovat produkční stanice, Windows na sestavách, skříních na serverech nebo pracovních stanicích. Používání popisků oblastí nebo přidávání jedinečných funkcí do jednotlivých oblastí s podobným zobrazením může přispět k zmírnění červů děr.

### <a name="movement-in-a-space"></a>Pohyb v prostoru

Pokud se vaše prostředí neustále přesouvá a mění, nemá zařízení stabilní funkce, které by bylo možné najít.  

Víc přesunů objektů, které jsou v prostoru, včetně lidí, usnadňuje ztrátu sledování. U pohybů dopravníkových pásů, položek v různých stavech konstrukce a hodně lidí v prostoru bylo známo, že způsobují problémy se sledováním.

HoloLens se může rychle přizpůsobit těmto změnám, ale jenom v případě, že je tato oblast pro zařízení zřetelně viditelná. Oblasti, které se nezobrazují jako často, můžou mít prodlevu za realitou, což může způsobit chyby v prostorové mapě. Uživatel například vyhledá přítele a pak se znovu vypíná, zatímco přítel opustí místnost. Reprezentace typu Ghost se zachová v datech prostorového mapování, dokud uživatel znovu neprojde prázdné místo.

### <a name="proximity-of-the-user-to-items-in-the-space"></a>Blízkost uživatele k položkám v prostoru

Podobně jako v případě, že se člověk nemůže dobře soustředit na objekty blízko očí, potýká HoloLens, když jsou objekty blízko svých kamer. Pokud je objekt příliš blízko, aby se zobrazil na obou fotoaparátech, nebo pokud objekt blokuje jeden fotoaparát, bude mít zařízení mnohem více problémů se sledováním objektu.  

Kamery uvidí od objektu méně než 15 cm.

### <a name="surfaces-in-a-space"></a>Povrchy v prostoru

Silně reflektované povrchy se nejspíš budou lišit v závislosti na úhlu, který má vliv na sledování. Zamyslete se na značku nového auta – při přesunu se světlo odrazí a při přesunu se na povrchu zobrazí různé objekty. Do sledování se různé objekty, které se projeví na povrchu, reprezentují měnící se prostředí a zařízení ztratí sledování.

Méně lesklých objektů je snazší sledovat.

### <a name="wi-fi-fingerprint-considerations"></a>Wi-Fi posouzení otisků prstů

Pokud je povolená Wi-Fi, data mapy se budou korelovat otiskem Wi-Fi, a to i v případě, že se nepřipojí ke skutečné síti Wi-Fi nebo směrovači. Bez Wi-Fi informací může být prostor a hologramy trochu pomalejší, než je rozpozná. Pokud se Wi-Fi výrazně změní, může se stát, že se zařízení bude zcela nabývat jiným místem.

Identifikace sítě (například SSID nebo adresa MAC) se neposílá společnosti Microsoft a všechny Wi-Fi odkazy jsou v HoloLens místní.

## <a name="mapping-new-spaces"></a>Mapování nových mezer

Když zadáte nové místo (nebo nahrajete stávající), zobrazí se v něm rozprostřený obrázek v prostoru. To znamená, že vaše zařízení mapuje vaše okolí. Zatímco HoloLens se v průběhu času učí místo, jsou k dispozici tipy a triky pro mapování prostorů.

## <a name="environment-management"></a>Správa prostředí

K dispozici jsou dvě nastavení, která uživatelům umožňují "vyčistit" hologramy a způsobit, že HoloLens zapomenou místo. Existují na **hologramech a prostředích** v aplikaci nastavení. druhé nastavení se taky zobrazuje v části **Ochrana osobních údajů** v aplikaci nastavení.  

1. **Odstraňte okolní hologramy**. Když vyberete toto nastavení, HoloLens smaže všechny ukotvené hologramy a veškerá uložená data map pro aktuální prostor, kde se zařízení nachází. Nový oddíl mapy se vytvoří a uloží v databázi pro toto umístění, jakmile budou hologramy znovu umístěné do stejného místa.

1. **Odstraňte všechny hologramy**. Když vyberete toto nastavení, HoloLens smaže všechna data mapy a ukotvené hologramy v celých databázích prostorů. Nebudou se znovu zjišťovat žádné hologramy a všechny hologramy je potřeba nově umístit, aby se v databázi znovu ukládaly části map.

## <a name="hologram-quality"></a>Kvalita hologramu

Hologramy můžete umístit do celého prostředí – vysoká, nízká a vše, ale uvidíte je na [holografickém snímku](/windows/mixed-reality/holographic-frame) , který se nachází před očima. Chcete-li získat nejlepší pohled, nezapomeňte upravit zařízení, abyste viděli celý rámec. A váhají se na vaše prostředí a prozkoumejte ho.

Aby vám vaše [hologramy](/windows/mixed-reality/hologram) vypadaly na ostrých, jasných a stabilních, musí být váš HoloLens kalibrovaný jenom za vás. Při prvním nastavení HoloLens vás provedete tímto procesem. Pokud se rozhodnete, že hologramy nevypadají správně nebo vidíte mnoho chyb, můžete provést úpravy.

Pokud máte potíže s mapováním prostorů, zkuste odstranit okolní hologramy a přemapováním prostoru.

### <a name="calibration"></a>Kalibrace

Pokud vaše hologramy vypadají se kolísáním nebo protřepáním nebo pokud máte potíže s umísťováním hologramů, je první věc, kterou je třeba vyzkoušet, [aplikace pro kalibraci](hololens-calibration.md). Tato aplikace může také pomoci, pokud při používání HoloLens máte nějaký nepohodlí.

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
1. Pokud budete postupovat podle výše uvedených pokynů, ale dojde k neočekávaným potížím s přehříváním, před odesláním [zpětné vazby](hololens-feedback.md)zajistěte, aby byla povolená K prozkoumání případných problémů s naplněním bude potřeba povinná nebo volitelná telemetrie.

## <a name="see-also"></a>Viz také

- [Návrh prostorového mapování](/windows/mixed-reality/spatial-mapping)
- [Hologramy](/windows/mixed-reality/hologram)
