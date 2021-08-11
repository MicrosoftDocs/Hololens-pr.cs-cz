---
title: Vylepšení vizuální kvality a pohodlí
description: naučte se, jak kalibrovat interpupillary vzdálenost (IPD), aby se zlepšila kvalita vizuálů na zařízeních HoloLens.
author: Teresa-Motiv
ms.author: xerxesb
ms.date: 9/13/2019
ms.topic: article
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
keywords: kalibrace, pohodlí, vizuály, kvalita, ipd, HoloLens, Windows Mixed Reality, náhlavní souprava VR
ms.openlocfilehash: 5ba00d873b8a42c3397315a62492b14ab04ded367ccdd05af8be4f68c56627e2
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664652"
---
# <a name="improve-visual-quality-and-comfort"></a>Vylepšení vizuální kvality a pohodlí

HoloLens 2 a HoloLens (1. generace) fungují lépe, když jsou kalibrovány na vaše jedinečné oči.

I když se obě zařízení potřebují kalibrovat pro nejlepší možnosti zobrazení hologramu, používají různé technologie kalibrace a techniky.  přejděte na kalibraci [HoloLens 2](#calibrating-your-hololens-2) nebo [HoloLens (1. generace)](#calibrating-your-hololens-1st-gen).

## <a name="calibrating-your-hololens-2"></a>kalibrace HoloLens 2

HoloLens 2 používá technologii pro sledování očí ke zlepšení vašeho zobrazení a interakci s virtuálním prostředím. kalibrace HoloLens 2 znamená, že dokáže přesně sledovat vaše oči (a oči, kdo zařízení používá). Pomůže vám také s pohodlím uživatelů, zarovnáním hologramu a ručním sledováním. Po kalibraci se hologramy zobrazí správně i v případě, že se hypervisory posunou na hlavu.

HoloLens 2 vyzve uživatele k kalibraci zařízení za následujících okolností:

- Uživatel zařízení používá poprvé.
- Uživatel dřív rozhodl z procesu kalibrace.
- Proces kalibrace nebyl úspěšný, když uživatel naposledy použil zařízení.
- Uživatel odstranil svoje profily kalibrace.
- Zařízení se odeberou a navrátí se zpátky a kterákoli z výše uvedených podmínek se použije. 


![Výzva k kalibraci pro úpravu na oči.](./images/07-et-adjust-for-your-eyes.png)

Během tohoto procesu se podíváte na sadu cílů (GEMS). Je to v pořádku, pokud během kalibrace blikáte, ale zkuste se soustředit na Gems místo jiných objektů v místnosti.  zaměření na gems umožňuje HoloLens získat informace o poloze oka a vykreslovat si holografický svět.

![Výzva k kalibraci oznamuje uživateli, aby zachoval hlavu a sledoval tečky s očima.](./images/07-et-hold-head-still.png)

![Výzva k kalibraci s Gem příkladem.](./images/08-et-gems.png)

![Úpravy výzvy k kalibraci.](./images/09-et-adjusting.png)

Pokud byla kalibrace úspěšná, zobrazí se obrazovka úspěšné.  Pokud ne, přečtěte si další informace o [diagnostice selhání kalibrace](hololens2-display.md#troubleshooting).

![Výzva k kalibraci byla úspěšná.](./images/10-et-success.png)

### <a name="calibration-when-sharing-a-device-or-session"></a>Kalibrace při sdílení zařízení nebo relace

více uživatelů může sdílet zařízení HoloLens 2, aniž by museli vyžadovat, aby uživatelé procházeli prostřednictvím nastavení zařízení. když nový uživatel umístí zařízení do svého hlavního panelu poprvé, HoloLens 2 automaticky vyzve uživatele k kalibraci vizuálů. Když uživatel, který má dříve kalibrované vizuály, umístí zařízení na jeho hlavu, displej se bez problémů přizpůsobí kvality a pohodlné zobrazení.  

### <a name="manually-starting-the-calibration-process"></a>Ruční spuštění procesu kalibrace

1. pomocí gesta start otevřete [**nabídka Start**](hololens2-basic-usage.md#start-gesture).
1. pokud Nastavení aplikace není připnuté na **Start**, vyberte **všechny aplikace**.
1. vyberte **Nastavení** a pak vyberte kalibrace kalibrace **systému**–  >    >    >  **kalibrace očí spuštění**.

   ![aplikace Nastavení, která zobrazuje možnosti kalibrace pro spuštění](./images/C-Settings.Calibration.png)

### <a name="auto-eye-position-support"></a>Podpora pozice automatického oka

ve HoloLens 2 se poloha oka povoluje přesnou polohu hologramu, pohodlné zobrazení a vylepšená kvalita zobrazení. Pozice oka se vypočítávají interně jako součást výpočtu sledování očí. To ale vyžaduje, aby každý uživatel přešel přes kalibraci sledování očí, a to i v případě, že prostředí nemusí vyžadovat pohledu.

**Pozice pro automatické oči (AEP)** umožňuje těmto scénářům, které jsou v rámci interakce k dispozici, způsob výpočtu očí pro uživatele. Pozice automatického oka začne pracovat na pozadí automaticky od okamžiku, kdy uživatel do zařízení umístí. Pokud uživatel nemá žádnou předchozí kalibraci sledování očí, začne poloha automatického oka začínat umístěním očí uživatele do zobrazovacího systému po dobu zpracování 20-30 sekund. Uživatelská data se v zařízení neukládají a tento proces se opakuje, pokud se uživatel vypne a přesune zařízení zpátky nebo pokud se zařízení restartuje nebo se probudí z režimu spánku.

K dispozici je několik změn chování systému s funkcí pozice automatického oka, když uživatel do zařízení vloží nekalibrovaného uživatele. V tomto kontextu se nekalibrovaný uživatel odkazuje na někoho, kdo předtím neprošlý procesem kalibrace sledování očí na zařízení.

| Aktivní aplikace | Předchozí chování | chování z Windows holografické verze 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| Aplikace, která není povolená pohledu, nebo holografické prostředí |Zobrazí se dialogové okno výzvy k kalibraci sledování očí. | Nezobrazí se žádná výzva. |
| Aplikace s podporou pohledu | Zobrazí se dialogové okno výzvy k kalibraci sledování očí. | Výzva k kalibraci sledování očí se zobrazí jenom v případě, že aplikace přistupuje ke pohledumu streamu očí. |

Pokud uživatel přejde z aplikace s povoleným pohledu na jednu, která přistupuje k datům pohledu, zobrazí se výzva k kalibraci. 

Všechny ostatní chování systému budou podobné jako v případě, že aktuální uživatel nebude mít aktivní kalibraci sledování očí. Například ruční gesto spuštění nebude povoleno. Při počátečním nastavení se neprojeví žádné změny v prostředí před prvním nastavením.

Pro prostředí, která vyžadují pohledu data nebo přesné umístění na hologram, doporučujeme nekalibrovaným uživatelům spustit kalibraci sledování očí. je přístupná z výzvy k kalibraci sledování očí nebo spuštěním aplikace Nastavení z nabídky start a následným výběrem kalibrace **> systému > kalibraci očí > kalibraci běhu**.

#### <a name="deferred-calibration-prompt"></a>Odložená kalibrace – výzva

V případě pozice automatického oka je dialogové okno výzvy pro kalibraci sledování očí odloženo, dokud aplikace nepožaduje oči pohledu data. Tím se zajistí, že se uživateli nezobrazí žádné výzvy, pokud aktivní aplikace nepotřebuje pohledu. Pokud aplikace vyžaduje data pohledu a aktuální uživatel není kalibrovaný, zobrazí se uživateli výzva k kalibraci. Toto chování se dá použít k zobrazení výzvy kalibrace sledování očí v přiměřené době pro prostředí. Tato metoda se doporučuje z následujících důvodů.

1.  Dialog pro kalibraci sledování očí zobrazuje uživatele s podrobnostmi o tom, proč je sledování očí potřeba.
2.  Prezentuje uživateli způsob, jak odmítnout, aby byly oči kalibrovány.

Pokud se uživatel rozhodne spustit kalibraci sledování očí, po dokončení kalibrace by se měl fokus vrátit do původní aplikace. 

### <a name="calibration-data-and-security"></a>Data kalibrace a zabezpečení

Informace o kalibraci jsou uloženy místně na zařízení a nejsou přidruženy k žádným informacím o účtu. Neexistuje žádný záznam o tom, kdo zařízení použil bez kalibrace. To znamená, že noví uživatelé budou vyzváni k kalibraci vizuálů při prvním použití zařízení a uživatelům, kteří si předtím vyvyjádřili kalibraci, nebo pokud byla kalibrace neúspěšná.

Zařízení může místně ukládat až 50 profilů kalibrací. Po dosažení tohoto počtu zařízení automaticky odstraní nejstarší nepoužitý profil.

informace o kalibraci je možné ze zařízení vždycky odstranit v **Nastavení**  >  **sledování ochrany osobních údajů**  >  .  

### <a name="disable-calibration"></a>Zakázat kalibraci

Můžete také zakázat výzvu k kalibraci pomocí následujících kroků:

1. vyberte **Nastavení**  >    >  **kalibraci** systému.
1. vypnout **, když nová osoba používá tento HoloLens, automaticky požádá o spuštění kalibrace očí**.

   > [!IMPORTANT]
   > Toto nastavení může nepříznivě ovlivnit kvalitu a pohodlí vykreslování hologramů.  Když toto nastavení vypnete, funkce, které závisejí na sledování očí (například posouvání textu), už nebudou fungovat v moderních aplikacích.

> [!NOTE]
> Nastavení přepínač byl odebrán jako Windows holografický, verze 20H2 s [podporou pozice automatického oka](hololens-release-notes.md#auto-eye-position-support). Výzva k kalibraci se automaticky zobrazí jenom v případě, že nekalibrovaný uživatel používá aplikaci s povoleným sledováním očí.

### <a name="hololens-2-eye-tracking-technology"></a>HoloLens 2 – technologie pro sledování očí

Zařízení využívá technologii pro sledování očí ke zlepšení kvality displeje a k zajištění toho, že všechny hologramy jsou umístěné přesně a pohodlné zobrazení v 3D. Vzhledem k tomu, že jako orientačních bodů používá oči, může se zařízení upravit pro každého uživatele a ladit jeho vizuály, protože se mírně posouvá sluchátka.  Veškeré úpravy se probíhají v průběhu bez nutnosti ručního ladění.
> [!NOTE]
> Nastavení IPD se nedá použít pro HoloLens 2, protože pozice očí jsou vypočítané systémem.

HoloLens aplikací pomocí sledování očí sledujete, kde hledáte v reálném čase. Tato funkce umožňuje vývojářům využít k tomu celou novou úroveň kontextu, humánní porozumění a interakce v rámci holografického prostředí. Vývojáři nemusí dělat nic, abyste mohli tuto funkci používat.

## <a name="calibrating-your-hololens-1st-gen"></a>kalibrace HoloLens (1. generace)

HoloLens (1. generace) upravuje hologram displejů podle [interpupillary vzdálenosti](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD). Pokud IPD není přesná, hologramy můžou být v nestabilní nebo nesprávné vzdálenosti. Kvalitu vizuálů můžete zlepšit kalibrací zařízení na interpupillaryou vzdálenost (IPD).

při nastavování HoloLensho zařízení (1. generace) se výzva k kalibraci vizuálů po Cortana zavádí. Doporučuje se dokončit kalibrační krok během této fáze instalace. Můžete ho ale přeskočit tak, že počkáte, Cortana zobrazí výzva a pak se zobrazí "Přeskočit".

Během procesu zpracování vás HoloLens k zarovnaní prstu s řadou šesti cílů na oko. HoloLens pomocí tohoto procesu správně nastaví IPD pro vaše oči.

![Obrazovka pro zarovnání prstu IPD ve druhém kroku](./images/ipd-finger-alignment-300px.jpg)

### <a name="manually-start-the-calibration-process"></a>Ruční spuštění procesu zpracování

Pokud potřebujete upravit úpravy nebo pokud ji nový uživatel potřebuje upravit, můžete kdykoli ručně spustit aplikaci Chystávku. Ve výchozím nastavení je nainstalovaná aplikace Ásek. Můžete k ní získat přístup pomocí nabídky **Start** nebo Nastavení aplikace.

Pokud chcete ke spuštění aplikaceČískat pomocí nabídky **Start,** postupujte takto:

1. Pomocí gesta [bloom](hololens1-basic-usage.md) otevřete **nabídku Start.**
1. Pokud chcete zobrazit všechny aplikace, vyberte **+** .
1. Vyberte **Možnost.**

   ![Přístup k aplikaci pro aplikaci, která se otepřuje z prostředí](./images/calibration-shell.png)

   ![Aplikace, která se zobrazí jako živá datová krychle po spuštění](./images/calibration-livecube-200px.png)

Pokud chcete ke Nastavení aplikaci Promyšl, postupujte takto:

1. Pomocí gesta [bloom](hololens1-basic-usage.md) otevřete **nabídku Start.**
1. Pokud **Nastavení** možnost Start připnutá,  **+** výběrem zobrazíte všechny aplikace.
1. Vyberte **Nastavení**.
1. Vyberte **Systémové nástroje**  >    >  **Otevřítochádka.**

   ![Spuštění aplikace s průvodcem z aplikace nastavení](./images/calibration-settings-500px.jpg)

## <a name="immersive-headsets"></a>Imerzivní náhlavní soupravy

Některé imerzivní náhlavní soupravy umožňují přizpůsobit nastavení IPD. Pokud chcete změnit IPD náhlavní soupravy, otevřete aplikaci Nastavení, vyberte displej náhlavní soupravy **Mixed Reality** a potom  >  přesuňte posuvník. Změny se v reálném čase zobrazí v náhlavní soupravě. Pokud znáte svou IPD adresu, můžete ji zadat také přímo z návštěvu optometristy.

Toto nastavení můžete také upravit na počítači tak, že vyberete **Nastavení**  >  **náhlavní soupravy**  >  **Mixed** Reality.

Pokud náhlavní souprava přizpůsobení IPD nepodporuje, toto nastavení bude zakázané.
