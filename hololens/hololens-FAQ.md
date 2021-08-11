---
title: Nejčastější dotazy týkající se HoloLens zařízení a hologramů
description: Máte rychlý dotaz ohledně HoloLens s hologramy?  Tento článek poskytuje rychlou odpověď a další zdroje informací.
keywords: hololens, nejčastější dotazy, známý problém, nápověda
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
ms.openlocfilehash: b20e5784711fdbae0602943cbad35a37f5be72fdd2a709ec8c04d95b05e75ada
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664617"
---
# <a name="holograms-and-interactions-troubleshooting"></a>Hologramy a interakce

Tento článek popisuje řešení potíží s umístěním hologramů, prací s prostory a hlášením problémů s hologramy.

Vždy, když máte problémy, ujistěte se, že:
- Zkuste [ho restartovat,](hololens-restart-recover.md) abyste viděli, jestli se tím něco opraví.
- Před řešením potíží se ujistěte, HoloLens [se účtují](hololens2-charging.md) poplatky (účtují se nejméně za hodinu). 


Pomocí aplikace Feedback nám pošlete informace o problému. Aplikaci Feedback najdete v nabídce [ **Start**](holographic-home.md). 

Tipy k ošitřování vašeho HoloLens najdete v [tématu Úprava fitování.](hololens2-setup.md#adjust-fit)

<a id="list"></a>
- [Není možné vytvořit nové mezery.](#new-spaces-cant-be-created)
- [Prostory nelze identifikovat ani načíst.](#spaces-cant-be-identified-or-loaded)
- [Návody odstranit všechny mezery?](#how-do-i-delete-all-spaces)
- [Hologramy, že nevypadáte správně nebo se pohybujete](#holograms-dont-look-right-or-are-moving-around)
- [Zpráva "Finding your space" (Vyhledání místa)](#finding-your-space-message)
- [Očekávané hologramy se v mém prostoru nezobrazují](#expected-holograms-arent-showing-in-my-space)
- [Nelze umístit hologramy nebo zobrazit dříve umístěné hologramy.](#cant-place-holograms-or-see-previously-placed-holograms)
- [Hologramy nebo jsou zachované v jiných hologramech nebo objektech](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [Hologramy se zobrazují na druhé straně zdi](#holograms-are-appearing-on-the-other-side-of-a-wall)
- [Po umístění hologramu na zeď se zdá, že plová](#after-placing-a-hologram-on-a-wall-it-seems-to-float)
- [Aplikace se po přesunutí zobrazují příliš blízko](#apps-appear-too-close-after-moving-them)
- [Hlášení problémů s nestabilními nebo neexaktními hologramy](#reporting-issues-with-unstable-or-inexact-holograms)

## <a name="new-spaces-cant-be-created"></a>Není možné vytvořit nové mezery.

Nejpravděpodobnějším problémem je nedostatek úložného prostoru. [Volná místa na disku a](hololens-troubleshooting.md#low-disk-space-error) zkuste to znovu.

[Zpět na seznam](#list)

## <a name="spaces-cant-be-identified-or-loaded"></a>Prostory není možné identifikovat ani načíst

Pokud váš HoloLens nemůže automaticky identifikovat a načíst prostor, ve které se nacházíte, zkontrolujte následující faktory:

- Ujistěte se, že jste připojeni k Wi-Fi
- Ujistěte se, že je v místnosti spousta světla.
- Ujistěte se, že v okolí nebyly žádné zásadní změny.

Prostor můžete také načíst ručně nebo můžete prostory spravovat tak, že Nastavení  >  **systémové**  >  **prostory.**

[Zpět na seznam](#list)

## <a name="how-do-i-delete-all-spaces"></a>Návody odstranit všechny mezery?

*Připravujeme*

[Zpět na seznam](#list)

## <a name="holograms-dont-look-right-or-are-moving-around"></a>Hologramy, že nevypadáte správně nebo se pohybujete

Pokud vaše hologramy nevypadnou správně (jsou například zamyšlné nebo nesvědčí nebo nad nimi vidíte černé opravy), vyzkoušejte jednu z těchto oprav:

- [Vyčistěte visor zařízení a](hololens1-hardware.md#care-and-cleaning) ujistěte se, že žádné senzory neblokuje.
- Ujistěte se, že jste v dobře zasněcené místnosti, která nemá velké množství přímého osvětlení.
- Zkuste se po okolí koukat a dívat se na okolí, abyste HoloLens mohli naskenovat úplněji.
- Pokud jste umístili velké množství hologramů, zkuste některé z těchto hologramů odebrat.

Pokud máte problémy i nadále, pokuste se o spuštění aplikace Uchem. Tato aplikace nakalibruje HoloLens jen pro vás, abyste hologramům pomohli, aby vaše hologramy hledaly co nejlépe. Pokud to chcete udělat, přejděte **na Nastavení**  >  **nástroje**  >  . V části Chysoce vyberte **Open Uchovat.** 

[Zpět na seznam](#list)

## <a name="finding-your-space-message"></a>Zpráva "Finding your space" (Vyhledání místa)

Když HoloLens učí nebo načítá prostor, může se zobrazit krátká zpráva s textem "Vyhledání místa". Pokud se tato zpráva zobrazí déle než několik sekund, zobrazí se pod nabídka Start zpráva "Stále hledáte místo".

Tyto zprávy znamenají, že HoloLens potíže s mapováním vašeho prostoru. Když k tomu dojde, můžete aplikace otevřít, ale nemůžete hologramy umístit do svého prostředí.

Pokud se tyto zprávy často zobrazí, vyzkoušejte jednu nebo několik následujících oprav:

- Ujistěte se, že jste v dobře zasněcené místnosti, která nemá velké množství přímého osvětlení.
- Ujistěte se, že je váš vizuátor zařízení čistý. [Zjistěte, jak vyčistit zorník.](hololens1-hardware.md#care-and-cleaning)
- Ujistěte se, že máte silný Wi-Fi signál. Pokud zadáte nové prostředí, které nemá žádný Wi-Fi nebo slabý Wi-Fi, HoloLens prostor nenajde. Zkontrolujte připojení Wi-Fi tak, že **Nastavení**  >  **Network &amp; Internet**  >  **Wi-Fi.**
- Zkuste se pohybovat pomaleji.

[Zpět na seznam](#list)

## <a name="expected-holograms-arent-showing-in-my-space"></a>Očekávané hologramy se v mém prostoru nezobrazují

Pokud nevidíte hologramy, které jste umístili, nebo pokud vidíte některé, které neočekáváte, vyzkoušejte jednu nebo několik následujících oprav:

- Zapněte nějaká světla. HoloLens funguje nejlépe v dobře zazářeném prostoru.
- Hologramy, které nepotřebujete, odeberte tak, že v Nastavení  >  **System**  >  **Hologramy**  >  **Odebrat hologramy** v okolí. Nebo v případě potřeby vyberte **Odebrat všechny hologramy**.

  > [!NOTE]
  > Pokud se rozložení nebo osvětlení vašeho prostoru výrazně změní, může mít zařízení potíže s identifikací místa a zobrazením hologramů.

[Zpět na seznam](#list)

## <a name="cant-place-holograms-or-see-previously-placed-holograms"></a>Nelze umístit hologramy nebo zobrazit dříve umístěné hologramy.

Pokud HoloLens prostor namapovat ani načíst, vstoupí do omezeného režimu a nebudete moct umístit hologramy ani zobrazit hologramy, které jste umístili. Vyzkoušejte něco z tohoto:

- Ujistěte se, že je ve vašem prostředí dostatek světla, aby HoloLens mohli prostor zobrazit a namapovat.
- Stojí mezi jedním a třemi metry od místa, kam se pokoušíte hologram umístit.
- Hologramy neposínejte na černé nebo odrazivé povrchy.
- Ujistěte se, že jste připojeni k Wi-Fi síti. Pokud nejste připojení k Wi-Fi, HoloLens nemůžete identifikovat a načíst známé místo.
- Projděte si místnosti, abyste HoloLens mohli znovu prohledat vaše okolí. Pokud chcete zobrazit, co už je naskenované, klepnutím ve vzduchu zobrazte grafiku mapovací sítě.
- Pokud potřebujete vytvořit nové místo, připojte se k Wi-Fi a restartujte HoloLens.
- Pokud chcete zobrazit, jestli je aktivní správné místo, nebo pokud chcete mezeru načíst ručně, přejděte **Nastavení**  >  **systémové**  >  **prostory**.
- Pokud je načteno správné místo a stále máte problémy, může být prostor poškozený. Pokud chcete tento problém vyřešit, vyberte místo a pak vyberte **Odebrat.** Jakmile prostor odeberete, HoloLens namapovat okolí a vytvořit nový prostor.

[Zpět na seznam](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a>Hologramy nebo jsou zachované v jiných hologramech nebo objektech

Pokud se k hologramu dostanete příliš blízko, dočasně zmizí a hologram obnoví, stačí se od něj &mdash; přesunout. Pokud jste společně umístili několik hologramů, některé mohou také zmizet. Zkuste jich několik odebrat.

Hologramy mohou být zablokovány nebo zachytány jinými hologramy nebo objekty, jako jsou zdi. Pokud k tomu dojde, zkuste jednu z následujících oprav:

- Pokud je hologram zaháněn jiným hologramem, přesuňte hologram zaháněný do jiného umístění. Pokud to chcete udělat, vyberte **Upravit** a potom klepnutím a podržením ji umístěte.
- Pokud je hologram zachovaný na zdi, vyberte Upravit a pak ke zdi přichyste, dokud se hologram nezobrazí. Klepněte a podržte a potom vytáhněte hologram dopředu a z zdi.
- Pokud hologram nemůžete přesunout pomocí gest, pomocí hlasu ho odeberte. Pohled na hologram a potom řekněte "Odebrat". Pak hologram znovu otevřete a umístěte ho na nové místo.

[Zpět na seznam](#list)

## <a name="holograms-are-appearing-on-the-other-side-of-a-wall"></a>Hologramy se zobrazují na druhé straně zdi.

pokud máte na stěnu hodně blízko, nebo pokud HoloLens tuto stěnu ještě neskenoval, můžete zobrazit hologramy, které jsou v další místnosti. Pokud chcete prověřit zeď, je nutné mít na stěně jeden a tři měřiče a pohledu.

černý nebo odrazný objekt (například černý couch nebo chladnička z korozivzdorné oceli) poblíž zdi může způsobit problémy, když se HoloLens pokusí zkontrolovat zeď. Pokud nějaký objekt existuje, naskenováním na druhé straně zdi.

[Zpět na seznam](#list)

## <a name="after-placing-a-hologram-on-a-wall-it-seems-to-float"></a>Po umístění hologramu na zeď se zdá být plovoucí

Hologram, který umístíte na zeď, se obvykle jeví jako 15palcový nebo mimo zeď. Pokud se zdá, že bude větší, zkuste jednu nebo více z následujících oprav:

- Když umístíte hologram na zeď, podržíte jeden a tři měřiče od stěny a plošku na stěně rovnou.
- Po klepnutí na zeď se zobrazí bublina s mapováním obrázku. Ujistěte se, že je síť zarovnána se stěnou. Pokud ne, vyjměte hologram, znovu prohledejte zeď a potom to zkuste znovu.
- Pokud se problém opakuje, spusťte aplikaci kalibrace. najdete ho v **Nastavení**  >  **systémových**  >  **nástrojích**.

[Zpět na seznam](#list)

## <a name="apps-appear-too-close-after-moving-them"></a>Po přesunutí se aplikace zobrazují příliš blízko.

zkuste se podívat na oblast, do které aplikaci umísťujete, a podívejte se, jak HoloLens prohlíží oblast z různých úhlů. Může také pomáhat [Vyčištění zařízení v rozcestníku](hololens1-hardware.md#care-and-cleaning) .

[Zpět na seznam](#list)

## <a name="reporting-issues-with-unstable-or-inexact-holograms"></a>Hlášení problémů s nestabilními nebo nepřesnými hologramy
 
1. Zaznamenejte si a podívejte se na [video s zachycenými hybridními realitami](holographic-photos-and-videos.md#capture-a-mixed-reality-video) . Toto video se dá později nahrát prostřednictvím centra zpětné vazby jako přiloženého souboru.  
1. povolení úplné telemetrie prostřednictvím aplikace **Nastavení** > **ochrany osobních údajů**  ->  **& zpětná vazba** a v části **nepovinná diagnostická data** zajistěte, aby byl přepínač nastaven na **zapnuto** .
1. získejte nejnovější hologram a opravy stability díky aktualizaci na nejnovější [Windows holografický operační systém (20H2 nebo vyšší)](hololens-release-notes.md#windows-holographic-version-20h2). Po dokončení aktualizace proveďte následující:
    1. odebrat všechny Hologramy přes **Nastavení** > **systému**  ->  **Hologramy** -> vyberte **odebrat všechny hologramy** a začněte s čerstvou mapou.
    1. vytvořte novou mapu svého prostoru pomocí HoloLens a prohlédněte si svou místnost a prohlédněte si oblast a plochy v prostoru. To proveďte po 2-3 minut.
    1. Proveďte kalibraci IPD. přejít na **Nastavení**  >  **systémové**  >  **nástroje**. V části **kalibrace** vyberte **otevřít kalibraci**.
    1. Otestujte scénář znovu a zkontrolujte, zda stále přetrvává.
1. Pokud aktualizace problém neopraví, zajistěte prosím [problém centra zpětné vazby](hololens-feedback.md). Po vyplňování zpětné vazby můžete použít tlačítko **sdílet** a vytvořit snadno propojený odkaz, který se dá odeslat při kontaktování podpory.

[Zpět na seznam](#list)