---
title: HoloLens 2 – řešení potíží se zobrazením
description: zobrazí se očekávání pro HoloLens 2. Pokyny pro konfiguraci displeje pro nejlepší kvalitu obrazu.
author: BrandonBray
ms.author: branbray
ms.date: 8/13/2020
ms.topic: article
keywords: zobrazení, kalibrace, pohodlí, vizuály, kvalita, IPD
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 3567c1f33f10240a9cacbf258669a0e3274f4c6bb3c90fc1317a57a3a415fc7f
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2021
ms.locfileid: "115659941"
---
# <a name="hololens-2-display-troubleshooting"></a>HoloLens 2 – řešení potíží se zobrazením

## <a name="overview"></a>Přehled
displej HoloLens 2 je kombinací projektorů waveguides a light. Uživatelé procházejí waveguides – rozptylová skla v rámci hypervisoru – při používání náhlavní soupravy. Nejsvětlejší projektory jsou uvnitř skříně nad prohlížeč. HoloLens 2 používá laserovou světlo k osvětlení displeje.

## <a name="troubleshooting"></a>Poradce při potížích

Proveďte následující kroky, aby se zajistila nejvyšší vizuální kvalita hologramů zobrazených v zobrazení:

* **Zvyšte jas displeje.** Hologramy vypadají nejlépe, pokud je zobrazení na jeho nejvyšší úrovni. při HoloLens, jsou tlačítka jasu na levé straně rozhraní rozcestníku poblíž temple.
* **Přiblížte rozcestník k vašemu oči.** Přiblíží clonu k nejbližší pozici vašim očí.
* **Rozcestník Shift + šipka dolů** Zkuste prohlížeč panel posunout na Forehead dolů, což způsobí, že se clona posune dolů blíž k vašemu nos.
* **[Spusťte kalibraci očí.](hololens-calibration.md#calibrating-your-hololens-2)** Zobrazení používá interpupillary vzdálenost (IPD) a oka pohledu k optimalizaci obrázků na obrazovce. Pokud nespustíte kalibraci očí, může být kvalita obrázku horší. pokud chcete spustit kalibraci očí, jděte do **Nastavení** kalibrace  >  **systému**  >    >  **spusťte kalibraci očí**.
* **Spustit kalibraci barev displeje** u [Windows holografické verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1) a vyšší můžete pro zobrazení HoloLens 2 **vybrat alternativní barevný profil** . To může mít za přesnější vzhled barev, zejména při nižších úrovních jasu displeje. kalibraci barev displeje lze nalézt v aplikaci **Nastavení** na stránce pro **kalibraci systému >** .

    > [!NOTE]
    > Vzhledem k tomu, že toto nastavení uloží nový profil barev do firmwaru zobrazení, jedná se o nastavení podle zařízení (a není jedinečné pro každý uživatelský účet).

### <a name="how-to-use-display-color-calibration"></a>Jak používat kalibraci barev displeje
1. spusťte aplikaci **Nastavení** a přejděte do části **System > kalibrace**.
1. V části **kalibrace barev displeje** vyberte tlačítko **kalibrace barev displeje spustit** .
1. Spustí se prostředí kalibrace barev displeje a doporuče vám, abyste se ujistili, že je váš hypervisor ve správné pozici.
1. Až budete pokračovat v dialogových oknech instrukce, zobrazí se automaticky ztlumení jasu na 30%.
    > [!TIP]
    > pokud máte potíže se zobrazením neaktivní scény ve vašem prostředí, můžete ručně upravit úroveň jasu HoloLens 2 pomocí tlačítek jasu na levé straně zařízení.
1. Vyberte tlačítka 1-6, abyste si mohli okamžitě vyzkoušet jednotlivé profily barev, a najít jeden, který vypadá nejlépe pro vaši oči. (to obvykle znamená, že profil, který pomáhá scénu, se jeví jako neneutrální, se vzorkem stupňů šedi a tónům skinu, které vypadají podle očekávání.)

    ![Zobrazit scénu kalibrace barev](images/color-cal-ui.png)
    
6. Až budete s vybraným profilem spokojeni, vyberte tlačítko **uložit & tlačítko Storno** .
1. Pokud nechcete provádět změny, vyberte tlačítko **zrušit & ukončení** a změny se vrátí.

> [!TIP]
> Tady jsou některé užitečné tipy, které vám pomůžou při používání nastavení kalibrace barev displeje:
> - můžete znovu spustit kalibraci barev displeje z Nastavení vždy, když chcete
> - pokud někdo na zařízení dřív používal nastavení pro změnu profilů barev, datum a čas poslední změny se projeví na stránce Nastavení.
> - Když znovu spustíte kalibraci barev displeje, bude zvýrazněný profil barev zvýrazněný a profil 0 se nezobrazí (jako profil 0 představuje původní barevný profil displeje).
> - pokud se chcete vrátit k původnímu profilu barev zobrazení, můžete to provést na stránce Nastavení (viz [postup resetování barevného profilu](#how-to-reset-color-profile)).

### <a name="how-to-reset-color-profile"></a>Jak obnovit barevný profil

pokud si nejste spokojeni s vlastním profilem barev uloženým ve vašem HoloLens 2, můžete obnovit původní barevný profil zařízení:
1. spusťte aplikaci **Nastavení** a přejděte do části **System > kalibrace**.
1. V části **kalibrace barev displeje** vyberte tlačítko **Obnovit výchozí barevný profil** .
1. po otevření dialogového okna vyberte **restartovat** , pokud jste připraveni restartovat HoloLens 2 a použít změny.

### <a name="top-display-color-calibration-known-issues"></a>Známé problémy při kalibraci horních displejů

- na stránce Nastavení stavový řetězec, který oznamuje, že se naposledy změnil barevný profil, bude zastaralá, dokud stránku Nastavení znovu nenačtete. 
    - **alternativní řešení**: vyberte jinou Nastavení stránku a pak znovu vyberte stránku kalibrace.
- pokud se při spuštění kalibrace barev displeje HoloLens 2 přepne do režimu spánku, bude později pokračovat na domovskou stránku hybridní reality a vaše úroveň jasu displeje bude stále ztlumená.
- Možná budete muset několikrát zkusit stisknout tlačítka jasu na levé straně zařízení, aby fungovala podle očekávání.
- Lokalizace není dokončena pro všechny trhy.

## <a name="faq"></a>Časté otázky

### <a name="what-are-the-patterns-that-occasionally-flash-in-the-bottom-corners-of-the-display"></a>Jaké jsou vzory, které občas blikají v dolních rozích zobrazení?

v některých případech bude HoloLens 2 zobrazovat různé vzory v levém dolním a pravém rohu displeje. Níže jsou uvedené příklady (animované soubory GIF). tento model je součástí běžné operace zařízení HoloLens 2 k kalibraci displeje pro optimální prostředí.

![Vzor Biphase](./images/DAT-Biphase-Fiducial.gif) ![GEOGRAFICKÝ vzor](./images/DAT-GEO-Fiducial.gif)

### <a name="why-am-i-unable-to-take-an-accurate-photograph-of-my-hololens-2-display"></a>proč mi nejde pořizovat přesnou fotografii mého HoloLens 2?

displej HoloLens 2 je navržený tak, aby si ho mohl prohlédnout lidské oči. Zařízení má aktivní systém korekce barev, který se přizpůsobí oči uživatele. V porovnání s lidským okem kamery vidí v prostředích odlišně a níže je několik faktorů, které mohou mít vliv na nekonzistenci mezi tím, co kamera zachytí a co uživatel uvidí.

* **Pozice oka.** zobrazení HoloLens 2 je navrženo speciálně pro polohu oka uživatele. HoloLens 2 využívá technologii sledování očí, aby se přizpůsobila k umístění očí uživatele. Fotoaparát, který je omylem umístěn v několika milimetrech, může způsobit zkreslení obrazu. Přesné umístění kamery je obtížné a musí odpovídat přesnému místu a přípravku očí, pro které zařízení provádí korekci barev.
* **Pohyb očí.** Zobrazení se přizpůsobí přesunutí oka uživatele, aby bylo možné upravovat barvy. To, co se zobrazuje na displeji, se může lišit v závislosti na tom, jestli se uživatel díváte na střed, okraj nebo na roh zobrazení. Jedna zachytávání imagí může nejlépe zobrazit jenom to, jak vypadá zobrazení pro osu, která odpovídá směru pohledua oka.
* **Binokulární zobrazení.** displej HoloLens 2 je navržený tak, aby se zobrazil s použitím očí. Mozek se přizpůsobí pro zobrazení dvou imagí a pořadí je dohromady. Obrázky pouze jednoho zobrazení ignorují informace z druhého zobrazení.
* **Doba expozice kamery.** Doba expozice kamery musí být přesným násobkem 1/120th sekundy. frekvence snímků pro zobrazení HoloLens je 120 Hz. vzhledem k způsobu, jakým HoloLens 2 kreslí obrázky, se zachytávání jednoho rámce také nestačí, aby se shodoval s vizuálním zážitkem člověka. Ve stejnou chvíli platí, že pokud se zařízení přesune na všechno – dokonce i mikropřesuny – systém reprojektuje image na displeji pro stabilizaci hologramů. zachytávání více rámců a udržování HoloLens přesunu obvykle vyžaduje instalaci v laboratoři.
* **Velikost otvoru kamery** Velikost clony kamery musí být alespoň 3 mm, aby bylo možné zachytit přesnou bitovou kopii. Fotoaparáty na mobilní telefon s malými clonami integrují světlo od menší oblasti, než je lidské oko. Zařízení aplikuje korekci barev pro vzory zjištěné většími otvory. V malých otvorech jsou vzory jednotnosti ostřejší a zůstávají viditelné i navzdory korekci barev používané systémem.
* **Úvodní žákům kamery.** Vchod z vchodu kamery by měl být nejméně 3 mm v průměru, aby bylo možné zachytit přesnou image. V opačném případě fotoaparát zachytí některé modely vysoké frekvence, které nejsou viditelné pro oči. Pozice vchodu na začátku musí být před fotoaparátem a umístěna na dálku, aby nedocházelo k zavlečení aberací a dalším variacím zaznamenané image.
* **Pozice kamery.** kamery, které splňují požadavky pro zobrazení HoloLens 2, jsou větší a je obtížné umístit kameru dostatečně blízko k zobrazení HoloLens 2, aby se zobrazila barva opraveného obrázku. pokud je fotoaparát na špatném místě, může korekce barev negativně ovlivnit zachycení zobrazení HoloLens 2.
* **Korekce obrázku** Typické digitální fotoaparáty a kamery smartphone používají křivku reprodukce tónů (TRC), která zvyšuje kontrast a barvu, aby poskytovala snappier výsledek. při použití na zobrazení HoloLens 2 se tato křivka intonace nestejnoměrně dosadí.

všechny uvedené, je stále možné, aby se specializované průmyslové kamery daly zachytit reprezentativní obrázky ze zobrazení HoloLens 2. Smartphony, spotřebitelské a profesionální fotoaparáty bohužel nezachytí obrázky, které odpovídají tomu, co uživatel vidí na HoloLens 2.

### <a name="what-does-eye-calibration-do-to-display-image-quality"></a>Co dělá pohled na kvalitu obrázku?

Obrazovka HoloLens 2 aktivně opravuje obrázky podle pozice očí uživatele. [Zrak poskytuje](hololens-calibration.md) dva důležité vstupy: (1) interpupilární vzdálenost uživatele (IPD) a (2) směr, který každé oko hledá. Bez zraku se systém standardně zaměřuje na nominální pozici oka bez pohybu očí. Rozdíl mezi aktivní korekcí barev a bez opravy závisí na samotné opravě uživatele. Uživatelům, kteří mají stejnou IPD jako výchozí nastavení systému, se například zobrazí méně vylepšení opravy barev. I když uživatelé, kteří mají mnohem užší nebo širší IPD než výchozí nastavení systému, uvidí více změn v obrázku zobrazení.

Poznámka: Nová funkce v [Windows Holographic verze 20H2](hololens-release-notes.md#windows-holographic-version-20h2) začne automaticky zjišťovat [polohu oka](hololens-calibration.md#auto-eye-position-support). 

### <a name="what-are-the-display-differences-between-hololens-1st-gen-and-hololens-2"></a>Jaké jsou rozdíly zobrazení mezi HoloLens (1. generace) a HoloLens 2?

Mezi hlavní žádosti, které zákazníci dali Microsoftu poté, co HoloLens 1 byl (1), zvýšili zorné pole a (2) zvýšili brightness. Vývoj technologií umožnil Microsoftu vytvořit vlnovce, které zdvojnásobil zorné pole a vytvářely projektory s displejem, který je až třikrát jasnější. Hardware nastaví základ pro základní kompromisy pro kvalitu obrázku displeje: (1) zorné pole, (2) jas a (3) jednotnost barev. Pokračující rozvoj technologií umožňuje vylepšování ve všech oblastech, aniž by bylo zanedbatelné jiné místo. Do této přechodného období stávající technologie nastavuje omezení, která jsou pro tyto kompromisy k dispozici.

### <a name="what-improvements-are-coming-that-will-improve-hololens-2-image-quality"></a>Jaká vylepšení se chystá, aby se zlepšila HoloLens 2 image?

I když probíhá mnoho šetření pro zlepšení kvality obrázků, očekává se, že v nadcházejících aktualizacích dorazí následující oblasti:

* **Automatická pozice oka.** Tato funkce umožní, aby se na pozadí prochytá procedury z pohledu. Aby aktivní oprava barev fungovala, uživatelé už nebudou muset spouštět plynulý pohled. Místo toho bude prostě fungovat.
* **Vylepšení barevného zlepšování** Tato aktualizace se zaměřuje na hodnoty barev s tmavšími barvami (například tmavě šedou). Tlumení barvy teď přechytá červený tón. K tomuto problému dochází také v případě, že je celé zobrazení neaktivní – celý displej vybere červené barvy. Tento problém je výsledkem příliš velké aktivity v červeném barevném kanálu pro tyto tmavší barvy. Pro tyto tlumecí barvy jsme charakterizovali křivku osvětlení a pracujeme na tom, aby uživatelům nabídli proceduru záchytné procedury. Výsledkem bude větší přesnost barev napříč spektrem brightness. Nezmění vzhled bílých pozadí při plném jasu. V aplikacích nadále doporučujeme používat vzory návrhu tmavého režimu.
* **Režim čtení.** Vývojáři aplikací mohou pro dosažení vyššího úhlového rozlišení vyměnit zorné pole. Vývojáři aplikací mohou přepsat projekční matici tak, aby se obsah vykresloval v rozlišení vykreslování na displeji. Výsledkem této funkce je 30% snížení zorné oblasti a odpovídající zvýšení úhlového rozlišení. Pracujeme na zavedení této funkce do [Mixed Reality Toolkit](https://github.com/Microsoft/MixedRealityToolkit-Unity). Pokud je k dispozici, bude režim čtení fungovat v HoloLens operačního systému 2 – nezávisí na aktualizaci operačního systému.

Aktualizace operačního systému se doručují automaticky. Můžete také testovat rané verze vylepšení softwaru prostřednictvím programu Insider Preview.

### <a name="what-guidance-is-available-for-developers-to-apply-dark-mode-design-principles"></a>Jaké pokyny mají vývojáři k dispozici pro použití principů návrhu tmavého režimu?

Uživatelé budou mít nejlepší prostředí, když se vyhnete bílým pozadím. Tmavý režim je princip návrhu, který aplikace používají k používání černé nebo tmavě barevného pozadí. Nastavení systému je ve výchozím nastavení tmavé a můžete ho upravit tak, že Nastavení  >  **Barva**  >  **systému.**

Vývojářům doporučujeme postupovat podle pokynů k návrhu tmavého režimu:

* [Pokyny pro návrh aplikací HoloLens zobrazení](/windows/mixed-reality/designing-content-for-holographic-display#design-guidelines)
* [Doporučené velikosti písem](/windows/mixed-reality/typography#recommended-font-size)

Pokud hologram vyžaduje bílé pozadí, nechte velikost hologramu menší, než je celé zorné pole zobrazení. Tato velikost umožňuje uživatelům umístit hologram do středu displeje.

### <a name="how-do-you-clean-a-hololens-2-display"></a>Jak vyčistíte zobrazení HoloLens 2?

K vymazání zornice použijte mikrovlákno. Pokud chcete vizuátor sanitovat, použijte 70% izoádu k odlehčení zornice a pak ho vymažte. Úplné pokyny najdete v [nejčastějších dotazech HoloLens 2 čištění.](hololens2-maintenance.md)
