---
title: Nejčastější dotazy k zařízením HoloLens a hologramům
description: Máte rychlý dotaz na HoloLens nebo interakci s hologramy?  Tento článek poskytuje rychlou odpověď a další prostředky.
keywords: HoloLens, nejčastější dotazy, známý problém, help
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 02/27/2020
ms.reviewer: ''
ms.custom:
- CI 114606
- CSSTroubleshooting
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ae44ae1d9a2e088a1ef746f4e929e8fae73880bf
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924022"
---
# <a name="holograms-and-interactions-troubleshooting"></a>Řešení potíží s hologramy a interakcemi

Tento článek řeší problémy při umísťování hologramů, práci s prostory a hlášení problémů s hologramy.

Kdykoli máte problémy, ujistěte se, že:
- Zkuste [to znovu, abyste viděli, jestli](hololens-restart-recover.md) opravuje nějaké věci.
- Před řešením potíží se ujistěte, že se na HoloLens [účtuje](hololens2-charging.md) (účtuje se aspoň za hodinu). 


Pokud nám chcete poslat informace o problému, použijte prosím aplikaci Feedback. V [nabídce **Start**](holographic-home.md)najdete aplikaci Feedback. 

Tipy, jak nosit HoloLens, najdete v tématu [přizpůsobení přizpůsobení](hololens2-setup.md#adjust-fit).

<a id="list"></a>
- [Nelze vytvořit nové prostory](#new-spaces-cant-be-created)
- [Mezery se nedají identifikovat ani načíst.](#spaces-cant-be-identified-or-loaded)
- [Návody odstranit všechny mezery?](#how-do-i-delete-all-spaces)
- [Hologramy nevypadají správně nebo se pohybují](#holograms-dont-look-right-or-are-moving-around)
- [Zpráva hledání prostoru](#finding-your-space-message)
- [Očekávané hologramy nejsou zobrazeny v mém prostoru](#expected-holograms-arent-showing-in-my-space)
- [Nelze umístit hologramy nebo zobrazit dříve umístěné hologramy.](#cant-place-holograms-or-see-previously-placed-holograms)
- [Hologramy zmizí nebo jsou encasedy jinými hologramy nebo objekty.](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [Hologramy se zobrazují na druhé straně zdi.](#holograms-are-appearing-on-the-other-side-of-a-wall)
- [Po umístění hologramu na zeď se zdá být plovoucí](#after-placing-a-hologram-on-a-wall-it-seems-to-float)
- [Po přesunutí se aplikace zobrazují příliš blízko.](#apps-appear-too-close-after-moving-them)
- [Hlášení problémů s nestabilními nebo nepřesnými hologramy](#reporting-issues-with-unstable-or-inexact-holograms)

## <a name="new-spaces-cant-be-created"></a>Nelze vytvořit nové prostory

Nejpravděpodobnějším problémem je, že dochází místo v úložišti. [Uvolněte místo na disku](hololens-troubleshooting.md#low-disk-space-error) a pak to zkuste znovu.

[Zpět na seznam](#list)

## <a name="spaces-cant-be-identified-or-loaded"></a>Mezery se nedají identifikovat ani načíst.

Pokud vaše HoloLens nemůže identifikovat a načíst prostor, který se nachází automaticky, Projděte si následující faktory:

- Ujistěte se, že jste připojení k Wi-Fi
- Ujistěte se, že je v místnosti dostatek světla.
- Ujistěte se, že nedošlo k žádným podstatným změnám v okolí.

Místo toho můžete ručně načíst mezeru nebo spravovat své prostory, a to tak, že kliknete na **Nastavení**  >  **systémové**  >  **prostory**.

[Zpět na seznam](#list)

## <a name="how-do-i-delete-all-spaces"></a>Návody odstranit všechny mezery?

*Již brzy*

[Zpět na seznam](#list)

## <a name="holograms-dont-look-right-or-are-moving-around"></a>Hologramy nevypadají správně nebo se pohybují

Pokud vaše hologramy nevypadají správně (například se kolísáním nebo potřesem nebo se nad nimi zobrazují černé opravy), zkuste jednu z těchto oprav:

- [Vyčistěte hypervisor zařízení](hololens1-hardware.md#care-and-cleaning) a ujistěte se, že senzory neblokují nic.
- Ujistěte se, že jste ve dobře osvětlené místnosti, která nemá velký přímý sluneční světlo.
- Zkuste se podívat, co se gazing, a Prohlédněte si své okolí, aby HoloLens mohli provést jejich kompletní kontrolu.
- Pokud jste umístili spoustu hologramů, zkuste některé z nich odebrat.

Pokud máte potíže i nadále, zkuste spustit aplikaci kalibrace. Tato aplikace kalibruje váš HoloLens jenom za vás, aby vám pomohli lépe sledovat vaše hologramy. Provedete to tak, že přejdete na **Nastavení**  >  **systémové**  >  **nástroje**. V části **kalibrace** vyberte **otevřít kalibraci**.

[Zpět na seznam](#list)

## <a name="finding-your-space-message"></a>Zpráva hledání prostoru

Když HoloLens zajímá nebo načítá mezeru, může se zobrazit Stručná zpráva s informacemi o tom, jak místo vyhledat. Pokud se tato zpráva zobrazí déle než několik sekund, v nabídce Start se zobrazí další zpráva s informacemi o tom, že se vaše místo pořád hledá.

Tyto zprávy znamenají, že HoloLens má potíže s mapováním vašeho prostoru. Pokud k tomu dojde, můžete otevřít aplikace, ale do svého prostředí nemůžete umístit hologramy.

Pokud se tyto zprávy zobrazí často, zkuste jednu nebo více z následujících oprav:

- Ujistěte se, že jste ve dobře osvětlené místnosti, která nemá velký přímý sluneční světlo.
- Ujistěte se, že je zařízení vyčištěné. [Naučte se vyčistit své Rozcestníky](hololens1-hardware.md#care-and-cleaning).
- Ujistěte se, že máte signál silného Wi-Fi. Pokud zadáte nové prostředí, které nemá Wi-Fi, nebo slabý Wi-Fi signál, HoloLens nebude moci najít váš prostor. Kliknutím na **Nastavení**  >  **síť &amp; Internet**  >  **Wi-Fi** ověřte Wi-Fi připojení.
- Zkuste se pomaleji přesunout.

[Zpět na seznam](#list)

## <a name="expected-holograms-arent-showing-in-my-space"></a>Očekávané hologramy nejsou zobrazeny v mém prostoru

Pokud nevidíte hologramy, které jste umístili, nebo pokud vidíte některé, které neočekáváte, zkuste jednu nebo více z následujících oprav:

- Zapněte některé světla. HoloLens funguje nejlépe v dobře osvětleném prostoru.
- Odstraňte hologramy, které nepotřebujete, a to tak, že v **Nastavení**  >  **systémových**  >  **hologramů**  >  **odeberete okolní hologramy**. V případě potřeby vyberte možnost **Odebrat všechny hologramy**.

  > [!NOTE]
  > Pokud se změní rozložení nebo osvětlení v prostoru významně, vaše zařízení může mít potíže s určením vašeho prostoru a zobrazování vašich hologramů.

[Zpět na seznam](#list)

## <a name="cant-place-holograms-or-see-previously-placed-holograms"></a>Nelze umístit hologramy nebo zobrazit dříve umístěné hologramy.

Pokud HoloLens nemůže namapovat nebo načíst vaše místo, přejde do omezeného režimu a nebudete moci umístit hologramy nebo zobrazit hologramy, které jste umístili. Vyzkoušejte něco z tohoto:

- Ujistěte se, že je ve vašem prostředí dostatečné světlo, aby HoloLens mohl vidět a namapovat prostor.
- Stojan mezi jedním a třemi měřiči, ze kterých se snažíte umístit hologram
- Neumísťujte hologramy na černé nebo odrážetelné povrchy.
- Ujistěte se, že jste připojení k síti Wi-Fi. Pokud nejste připojení k Wi-Fi, HoloLens nemůže identifikovat a načíst známé místo.
- Projděte si místnosti, aby HoloLens mohli znovu prohledat vaše okolí. Chcete-li zjistit, co již bylo prohledáno, klepněte na tlačítko Air pro zobrazení mapy mřížky mapování.
- Pokud potřebujete vytvořit nové místo, připojte se k Wi-Fi a restartujte HoloLens.
- Chcete-li zjistit, zda je správné místo aktivní, nebo ručně načíst mezeru, přejděte do části **Nastavení**  >  **systémové**  >  **prostory**.
- Pokud je načteno správné místo a stále dochází k problémům, je možné, že je místo poškozeno. Pokud chcete tento problém vyřešit, vyberte požadované místo a pak vyberte **Odebrat**. Po odebrání prostoru HoloLens začne namapovat okolí a vytvořit nové místo.

[Zpět na seznam](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a>Hologramy zmizí nebo jsou encasedy jinými hologramy nebo objekty.

Pokud se zobrazí příliš blízko hologramu, bude dočasně zmizet z tohoto &mdash; hologramu, stačí opustit ho. I když jste umístili několik hologramů blízko sebe, některé z nich mohou zmizet. Zkuste odebrat pár.

Hologramy můžou být taky blokované nebo encased jinými hologramy nebo objekty, jako jsou zdi. Pokud k tomu dojde, zkuste jednu z následujících oprav:

- Pokud je hologram encased na jiném hologramu, přesuňte hologram encased do jiného umístění. Provedete to tak, že vyberete **Upravit** a pak klepnete a podržíte umístění.
- Pokud je hologram encased na stěně, vyberte **přizpůsobit**, potom na zeď, dokud se nezobrazí hologram. Klepněte a podržte ho a pak Stáhněte si hologram na zeď.
- Pokud nemůžu přesunout hologram pomocí gest, odeberte ho pomocí hlasu. Pohledu na hologramu a pak vyslovit "odebrat." Pak otevřete hologram a vložte ho do nového umístění.

[Zpět na seznam](#list)

## <a name="holograms-are-appearing-on-the-other-side-of-a-wall"></a>Hologramy se zobrazují na druhé straně zdi.

Pokud máte na stěnu hodně blízko, nebo pokud jste zeď ještě nezkontrolovali, můžete zobrazit hologramy, které jsou v další místnosti. Pokud chcete prověřit zeď, je nutné mít na stěně jeden a tři měřiče a pohledu.

Černý nebo odrazný objekt (například černý Couch nebo chladnička z korozivzdorné oceli) poblíž zdi může způsobit problémy při pokusu o skenování na zeď. Pokud nějaký objekt existuje, naskenováním na druhé straně zdi.

[Zpět na seznam](#list)

## <a name="after-placing-a-hologram-on-a-wall-it-seems-to-float"></a>Po umístění hologramu na zeď se zdá být plovoucí

Hologram, který umístíte na zeď, se obvykle jeví jako 15palcový nebo mimo zeď. Pokud se zdá, že bude větší, zkuste jednu nebo více z následujících oprav:

- Když umístíte hologram na zeď, podržíte jeden a tři měřiče od stěny a plošku na stěně rovnou.
- Po klepnutí na zeď se zobrazí bublina s mapováním obrázku. Ujistěte se, že je síť zarovnána se stěnou. Pokud ne, vyjměte hologram, znovu prohledejte zeď a potom to zkuste znovu.
- Pokud se problém opakuje, spusťte aplikaci kalibrace. Najdete ho v **Nastavení**  >  **systémové**  >  **nástroje**.

[Zpět na seznam](#list)

## <a name="apps-appear-too-close-after-moving-them"></a>Po přesunutí se aplikace zobrazují příliš blízko.

Zkuste si prohledat a podívat se na oblast, do které aplikaci umísťujete, aby HoloLens prohledala oblast z různých úhlů. Může také pomáhat [Vyčištění zařízení v rozcestníku](hololens1-hardware.md#care-and-cleaning) .

[Zpět na seznam](#list)

## <a name="reporting-issues-with-unstable-or-inexact-holograms"></a>Hlášení problémů s nestabilními nebo nepřesnými hologramy
 
1. Zaznamenejte si a podívejte se na [video s zachycenými hybridními realitami](holographic-photos-and-videos.md#capture-a-mixed-reality-video) . Toto video se dá později nahrát prostřednictvím centra zpětné vazby jako přiloženého souboru.  
1. Povolení úplné telemetrie prostřednictvím **Nastavení** aplikace – > Diagnostika **ochrany osobních údajů**  ->  **& zpětná vazba** a v části **volitelná diagnostická data** zajistěte, aby byl přepínač nastaven na **zapnuto**
1. Získejte nejnovější hologram a opravy stability pomocí aktualizace na nejnovější [holografický operační systém Windows (20H2 nebo vyšší)](hololens-release-notes.md#windows-holographic-version-20h2). Po dokončení aktualizace proveďte následující:
    1. Odebrat všechny hologramy prostřednictvím **Nastavení** aplikace-> **systémových**  ->  **hologramů** – > pak vyberte **Odebrat všechny hologramy** a začít s čerstvou mapou.
    1. Vytvořte novou mapu svého prostoru pomocí HoloLens a Prohlédněte si svou místnost a Prohlédněte si všechny oblasti a plochy v prostoru. To proveďte po 2-3 minut.
    1. Proveďte kalibraci IPD. Přejít na **Nastavení**  >  **systémové**  >  **nástroje**. V části **kalibrace** vyberte **otevřít kalibraci**.
    1. Otestujte scénář znovu a zkontrolujte, zda stále přetrvává.
1. Pokud aktualizace problém neopraví, zajistěte prosím [problém centra zpětné vazby](hololens-feedback.md). Po vyplňování zpětné vazby můžete použít tlačítko **sdílet** a vytvořit snadno propojený odkaz, který se dá odeslat při kontaktování podpory.

[Zpět na seznam](#list)