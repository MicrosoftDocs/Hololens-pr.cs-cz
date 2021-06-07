---
title: HoloLens 2 Displays
description: Zobrazí se očekávání pro HoloLens 2. Pokyny ke konfiguraci zobrazení pro zajištění nejlepší kvality obrázků
author: BrandonBray
ms.author: branbray
ms.date: 8/13/2020
ms.topic: article
keywords: display, utěšování, komfort, vizuály, kvalita, IPD
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 71dff00ff75feea4408979d2ce69fb14bf9bf3b7
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379305"
---
# <a name="hololens-2-display"></a>HoloLens 2 Display

Displej HoloLens 2 je kombinací vlnovek a projektorů. Uživatelé při používání náhlavní soupravy prohledali vlnovkou ( objektivy uvnitř visoru). Projektory jsou uvnitř skříně nad brow. HoloLens 2 používá k osvětlení displeje žárovku.

## <a name="troubleshooting"></a>Řešení potíží

V případě HoloLens 2 postupujte následovně, abyste zajistili nejvyšší vizuální kvalitu hologramů prezentovaných na displejích:

* **Zvyšte jas displeje.** Hologramy vypadají nejlépe, když je zobrazení na nejjasnější úrovni.
* **Přiblížte si zorník k zoru.** Umístěte zorník dolů na nejbližší pozici k zoru.
* **Posun visoru dolů** Zkuste si zorný panel na čediči hýbat dolů, což bude mít za následek, že se zorný objekt posune blíž k nosu.
* **Pouštět zrak.** K optimalizaci obrázků na displeji se na displeji používá vaše interpupilární vzdálenost (IPD) a pohled do očí. Pokud nezadáte zrak, může se kvalita obrázku ještě zhoršit. Pokud chcete spustit zrak, přejděte do části **Nastavení**  >  **Systém**  >  **Propouštění**  >  **zraku.**
* **Spusťte zobrazení barevného pozadí.** Na [Windows Holographic verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1) **a** novější můžete vybrat alternativní profil barev pro zobrazení HoloLens 2. Barvy se tak můžou zdát přesnější, zejména při nižších úrovních jasu zobrazení. Informace o zobrazení barev najdete v aplikaci **Nastavení** na stránce **System > Ádro.**

    > [!NOTE]
    > Vzhledem k tomu, že toto nastavení ukládá nový profil barev do firmwaru zobrazení, jedná se o nastavení pro jednotlivá zařízení (a není jedinečné pro každý uživatelský účet).

### <a name="how-to-use-display-color-calibration"></a>Jak používat barvu zobrazení
1. Spusťte aplikaci **Settings (Nastavení)** a přejděte **na System > Uchovat.**
1. V **části Zobrazit barevné pozadí** vyberte tlačítko Spustit barvu pro **zobrazení.**
1. Spustí se prostředí zobrazení barev a budete se muset ujistit, že je zorník ve správné pozici.
1. Po pokračování v dialogových oknech s pokyny se vaše zobrazení automaticky ztmaní na 30% jas.
    > [!TIP]
    > Pokud máte potíže se zobrazením tlumené scény ve vašem prostředí, můžete ručně upravit úroveň jasu HoloLens 2 pomocí tlačítek brightness na levé straně zařízení.
1. Výběrem tlačítek 1–6 můžete okamžitě vyzkoušet každý profil barev a najít ten, který vám vypadá nejlépe do očí (obvykle to znamená profil, který pomáhá scéně zdát se nejneužívnější, se vzorem stupňů šedé a barevnými odstíny, které vypadají podle očekávání).)

    ![Zobrazení scény barevného pozadí](images/color-cal-ui.png)
    
6. Až budete s vybraným profilem spokojeni, vyberte tlačítko **Save & Exit (Uložit** a ukončit).
1. Pokud nechcete provádět změny, vyberte tlačítko **Zrušit & Ukončit** a změny se vrátí zpět.

> [!TIP]
> Tady je několik užitečných tipů, které je dobré mít na paměti při používání nastavení barev zobrazení:
> - Kdykoli budete chtít, můžete v Nastavení znovu spustit barevné zobrazování.
> - Pokud někdo v zařízení dříve použil nastavení ke změně profilů barev, datum a čas poslední změny se projeví na stránce Nastavení.
> - Když znovu spustíte barevné zvýraznění zobrazení, profil barev, který byl dříve uložen, se zvýrazní a profil 0 se nezobrazí (protože Profil 0 představuje původní profil barvy zobrazení).
> - Pokud se chcete vrátit k původnímu profilu barev zobrazení, můžete to udělat na stránce Nastavení (viz postup [resetování profilu barev).](#how-to-reset-color-profile)

### <a name="how-to-reset-color-profile"></a>Resetování profilu barev

Pokud nejste spokojeni s vlastním profilem barev uloženým v HoloLens 2, můžete obnovit původní profil barvy zařízení:
1. Spusťte aplikaci **Settings (Nastavení)** a přejděte **na System > Uchovat.**
1. V **části Zobrazit barevné pozadí** vyberte tlačítko Obnovit výchozí **profil** barev.
1. Po otevření dialogového okna vyberte **Restartovat,** pokud jste připraveni restartovat HoloLens 2 a použít změny.

### <a name="top-display-color-calibration-known-issues"></a>Známé problémy s nejvyšším zobrazováním barev

- Na stránce Nastavení bude stavový řetězec, který vás informuje o tom, kdy byl profil barev naposledy změněn, aktuální, dokud tuto stránku Nastavení znovu nenačtete. 
    - **Alternativní** řešení: Vyberte jinou stránku Nastavení a pak znovu vyberte stránku Uchovat.
- Pokud holoLens 2 přejde do režimu spánku při spuštění barevného pozadí displeje, později se obnoví do domova hybridní reality a úroveň jasu displeje bude stále tlumená.
- Možná budete muset několikrát vyzkoušet stisknutí tlačítek brightness na levé straně zařízení nahoru nebo dolů, než budou fungovat podle očekávání.
- Lokalizace není dokončená pro všechny trhy

## <a name="faq"></a>Časté otázky

### <a name="what-are-the-patterns-that-occasionally-flash-in-the-bottom-corners-of-the-display"></a>Jaké vzory občas blikají v dolních rozích displeje?

V některých případech bude HoloLens 2 zobrazovat různé vzory v levém dolním a pravém rohu obrazovky. Příklady jsou uvedeny níže (animované GIFy). Tento vzor je součástí normálního provozu zařízení HoloLens 2 ke zkalibrování displeje za účelem optimálního prostředí.

![Vzor biphase](./images/DAT-Biphase-Fiducial.gif) ![Geografický model](./images/DAT-GEO-Fiducial.gif)

### <a name="why-am-i-unable-to-take-an-accurate-photograph-of-my-hololens-2-display"></a>Proč nemůžu pofotografovat přesnou fotografii displeje HoloLens 2?

Displej HoloLens 2 je navržený tak, aby ho bylo možné zobrazit lidským okem. Zařízení má aktivní systém opravy barev, který se přizpůsobuje pohledu uživatele. V porovnání s lidským okem fotoaparáty vidí prostředí odlišně a níže jsou některé faktory, které mohou ovlivnit jakoukoli nekonzistence mezi tím, co fotoaparát zachycuje a co vidí uživatel.

* **Pozice oka.** Displej HoloLens 2 je navržený speciálně pro pozici uživatele. HoloLens 2 využívá technologii sledování očí, aby se přizpůsobily pozici uživatele. Kamera, která je přemístěná o několik milimetrů, může vést k poruchám obrázků. Přesné umístění fotoaparátu je obtížné a musí přesně odpovídat poloze a odlehčení zraku, pro které zařízení provádí opravu barev.
* **Pohyb oka.** Zobrazení se přizpůsobí pohybu oka uživatele, aby se upravily barvy. To, co se zobrazuje na displeji, se může lišit v závislosti na tom, jestli se uživatel dívá na střed, okraj nebo roh displeje. Při jednom zachytávání obrázků by se v nejlepším případě mohlo zobrazit jen to, jak zobrazení vypadá pro osu, která odpovídá směru pohledu oka.
* **Binocular viewing.** Displej HoloLens 2 je navržený tak, aby ho bylo možné zobrazit oběma pohledy. Mozek se přizpůsobuje zobrazení dvou obrázků a spojuje je dohromady. Obrázky pouze jednoho zobrazení ignorují informace z druhého zobrazení.
* **Doba vystavení kamery.** Doba vystavení kamery musí být přesně násobek 1/120 sekundy. HoloLens zobrazuje snímkovou frekvenci 120 Hz. Vzhledem ke způsobu, jakým HoloLens 2 nakreslí obrázky, nestačí zachytit jeden snímek, aby odpovídal vizuálnímu prostředí člověka. Zároveň platí, že pokud se zařízení vůbec přesune – i mikromovements – systém přeprojektuje obrázek na displeji, aby se hologramy stabilizoval. Zachycení více snímků při zachování pohybu zařízení HoloLens obvykle vyžaduje laboratorní nastavení.
* **Velikost apertury fotoaparátu.** Aby bylo možné zachytit přesný obrázek, musí mít velikost clony fotoaparátu alespoň 3 mm. Fotoaparáty mobilních telefonů s malými clonami integrují světlo z menší oblasti než lidské oko. Zařízení aplikuje barevné opravy pro vzory pozorované většími clonami. V malých aperturech jsou vzory jednotnosti ostřejší a zůstávají viditelné i přes barevné opravy, které systém používá.
* **Vstup do kamery.** Vstup do kamery by měl mít průměr alespoň 3 mm, aby se zachytil přesný obrázek. Jinak fotoaparát zaznamená některé vzory s vysokou frekvencí, které nejsou viditelné pro oko. Pozice vstupního zornice musí být před kamerou a musí být umístěná v odlehčení oka, aby nedocházelo ke vzniku aberací a dalších variací zachyceného obrázku.
* **Pozice kamery.** Kamery, které splňují požadavky na zobrazení displeje HoloLens 2, jsou větší a je obtížné umístit fotoaparát dostatečně blízko k displeji HoloLens 2, aby bylo možné sledovat obrázek opravený barvou. Pokud je kamera na nesprávném místě, může oprava barev negativně ovlivnit zachycení obrazovky HoloLens 2.
* **Oprava obrázku.** Typické digitální fotoaparáty a fotoaparáty na smartphonech používají křivku pro reprodukci tónu (TRC), která zvyšuje kontrast a barvu a poskytuje lepší výsledek. Při použití na zobrazení HoloLens 2 tato tonusová křivka zesílí nejednotnosti.

Přesto je stále možné, aby specializované průmyslové kamery zachytily reprezentativní obrázky z displeje HoloLens 2. Smartphony, spotřebitelské a profesionální fotoaparáty bohužel nezachytí obrázky, které odpovídají tomu, co uživatel vidí na HoloLens 2.

### <a name="what-does-eye-calibration-do-to-display-image-quality"></a>Co dělá pohled na kvalitu obrázku?

Funkce HoloLens 2 zobrazuje aktivně barevně barvy obrázků na základě pozice oči uživatele. [Kalibrace očí](hololens-calibration.md) nabízí dva důležité vstupy: (1) interpupillary vzdálenost uživatele (IPD) a (2) směr hledání každého oka. Bez kalibrace očí systém standardně vyhodnotí jmenovitou polohu očí bez nutnosti přesunu očí. Rozdíl mezi aktivní korekcí barvy a bez korekce závisí na Physiology uživatele. Například uživatelé, kteří mají stejné IPD jako výchozí systém, uvidí méně vylepšení barev. Zatímco uživatelé, kteří mají mnohem užší nebo širší IPD než výchozí systém, uvidí další změny zobrazení obrázku.

Poznámka: nové funkce ve [Windows holografické verzi 20H2](hololens-release-notes.md#windows-holographic-version-20h2) začnou [automaticky detekovat polohu oka](hololens-calibration.md#auto-eye-position-support). 

### <a name="what-are-the-display-differences-between-hololens-1st-gen-and-hololens-2"></a>Jaké jsou rozdíly v zobrazení mezi HoloLens (1. gen) a HoloLens 2?

V rámci hlavních požadavků, které zákazníci uvedli od "HoloLens 1", zvýšil (a) zvýšení jasu a (2) zvyšuje jas. Technologický vývoj povolil Microsoftu vytvářet waveguidesy, které se zdvojnásobují v oblasti zobrazení a vytvářejí lehké projektory se zobrazením, které je až třikrát jasnější. Hardware nastaví standardní hodnotu pro trojice kompromisů pro zobrazení kvalita obrázku: (1) zobrazení, (2) jas a (3) zastejnoměrnost barev. Pokračování technologického postupu umožňuje vylepšení ve všech oblastech bez obětování jiné oblasti. V provizorním případě existující technologie nastaví omezení pro tyto kompromisy.

### <a name="what-improvements-are-coming-that-will-improve-hololens-2-image-quality"></a>Jaká vylepšení připravujeme, aby se zlepšila kvalita obrazu HoloLens 2?

I když máme spoustu šetření na zlepšení kvality obrazu, očekává se, že následující oblasti dorazí do nadcházejících aktualizací:

* **Automatické umístění očí.** Tato funkce umožní, aby byly na pozadí provedeny kroky kalibrace oka. Uživatelé už nebudou muset spouštět kalibraci očí, aby fungovala aktivní korekce barev. Místo toho bude fungovat jenom.
* **Vylepšení kalibrace barev** Tato aktualizace se zaměřuje na barevné hodnoty tmavších barev (například tmavě šedá). V současné době DIMM barvy vyberou červený tón. K tomuto problému dochází také v případě, že celý displej je ztlumený – celý displej zobrazuje červené barvy. Tento problém je výsledkem příliš velkého množství aktivit v kanálu červené barvy pro tyto tmavší barvy. Na tyto barvy ztlumení jsme označili křivky laserového osvětlení a pracujeme na tom, aby nabízela postup kalibrace uživatelů. Výsledkem bude přesnější přesnost barev v rámci spektra jasu. Nezmění se tím vzhled bílých pozadí při plném jasu. V aplikacích pokračujeme v používání vzorů návrhu pro tmavé režimy.
* **Režim čtení.** Vývojáři aplikací můžou navýšit zobrazení pole zobrazení, aby bylo možné dosáhnout vyššího úhlu rozlišení. Vývojáři aplikací můžou matrici projekce přepsat tak, aby se obsah vykreslil při vykreslování zobrazení. Výsledkem této funkce je 30% snížení v poli-zobrazení a odpovídající nárůst v úhlovém rozlišení. Práce se zavede k zavedení této možnosti do sady [nástrojů Mixed reality](https://github.com/Microsoft/MixedRealityToolkit-Unity). Pokud je k dispozici, režim čtení bude fungovat na jakémkoli operačním systému HoloLens 2 – není závislý na aktualizaci operačního systému.

Aktualizace operačního systému se doručují automaticky. V programu Insider Preview si můžete vyzkoušet také předčasné vydání vylepšení softwaru.

### <a name="what-guidance-is-available-for-developers-to-apply-dark-mode-design-principles"></a>Jaké doprovodné materiály můžou vývojáři použít pro návrh tmavého režimu.

Uživatelé budou mít k dispozici nejlepší možnosti při předcházení bílým pozadím. Tmavý režim je princip návrhu, který aplikace používá k použití černého nebo tmavého barevného pozadí. Nastavení systému je ve výchozím nastavení nastavené na tmavé a dá se upravit tak, že se vrátíte do **Nastavení**  >  **systém**  >  **Barva**.

Vývojářům doporučujeme postupovat podle pokynů pro návrh tmavého režimu:

* [Pokyny k návrhu pro vývojáře pro displeje HoloLens](https://docs.microsoft.com/windows/mixed-reality/designing-content-for-holographic-display#design-guidelines)
* [Doporučené velikosti písem](https://docs.microsoft.com/windows/mixed-reality/typography#recommended-font-size)

Pokud hologram vyžaduje bílé pozadí, ponechte velikost tohoto hologramu menší, než je celé pole zobrazení. Tato velikost umožňuje uživatelům umístit hologram do středu displeje.

### <a name="how-do-you-clean-a-hololens-2-display"></a>Jak vyčistíte displej HoloLens 2?

K mírnému vymazání clony použijte microfiberou tkaninu. K upravování hypervisoru použijte 70% isopropyl alkoholu, aby se lehce moistená tkanina, a pak vymažte clonu. Přečtěte si úplné pokyny v [části Nejčastější dotazy k čištění HoloLens 2](hololens2-maintenance.md).
