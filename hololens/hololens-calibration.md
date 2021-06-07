---
title: Vylepšení vizuální kvality a komfortu
description: Zjistěte, jak nakalibrovat vzdálenost mezi aplikacemi (IPD), abyste zlepšili kvalitu vizuálů na zařízeních HoloLens.
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
keywords: konektor, komfort, vizuály, kvalita, ipd, HoloLens, Windows Mixed Reality, náhlavní soupravy VR
ms.openlocfilehash: e975e2ccd978d4ec6b5331af0ae566af116711c5
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379203"
---
# <a name="improve-visual-quality-and-comfort"></a>Vylepšení vizuální kvality a komfortu

HoloLens 2 a HoloLens (1. generace) fungují lépe, když jsou nakalibrovány na vaše jedinečné pohledy.

I když se obě zařízení musí nakalibrovat, aby bylo zobrazení hologramu co nejlepší, používají různé technologie a techniky pro práci s hologramy.  Přeskočte [na holoLens 2 nebo](#calibrating-your-hololens-2) na [holoLens (1. generace)](#calibrating-your-hololens-1st-gen)– vychytávku.

## <a name="calibrating-your-hololens-2"></a>Nakalibrování HoloLens 2

HoloLens 2 využívá technologii sledování očí k vylepšení vašich zkušeností se sledováním virtuálního prostředí a interakcí s ním. Přikalibrování HoloLens 2 zajistí, že dokáže přesně sledovat vaše oči (a pohledy kohokoli jiného, kdo zařízení používá). Pomáhá také s komfortem uživatelů, zarovnáním hologramu a sledováním rukou. Po dokončení se hologramy zobrazí správně, i když se visor posune na vaší hlavy.

HoloLens 2 vyzve uživatele ke zkalibraci zařízení za následujících okolností:

- Uživatel používá zařízení poprvé.
- Uživatel se dříve odhlásit z procesu zpracování
- Proces zpracování nebyl úspěšný při posledním použití zařízení uživatelem.
- Uživatel odstranil profily profilů uživatelů.
- Zařízení se vypne a znovu zasune a platí jakákoli z výše uvedených okolností. 


![Výzva k úpravě očí.](./images/07-et-adjust-for-your-eyes.png)

Během tohoto procesu se podíváte na sadu cílů (gemy). Je v pořádku, pokud během průběhu blikání blikáte, ale snažte se soustředit na gemy místo na jiné objekty v místnosti.  Když se zaměříte na gemy, umožníte holoLens získat informace o vaší pozici v kůlu a vykreslit holografický svět.

![Výzva k zadání výzvy uživateli, aby si udrželi hlavičku a sledovali tečky pohledem.](./images/07-et-hold-head-still.png)

![Ukázka výzvy k zadání gemu](./images/08-et-gems.png)

![Úprava výzvy k zadání oprávnění](./images/09-et-adjusting.png)

Pokud byla úspěšná, zobrazí se obrazovka s úspěchem.  Pokud ne, přečtěte si další informace [o diagnostice selhání onemocnění.](#troubleshooting-hololens-2-calibration)

![Výzva k úspěšnému zadání](./images/10-et-success.png)

### <a name="calibration-when-sharing-a-device-or-session"></a>Narušení při sdílení zařízení nebo relace

Zařízení HoloLens 2 může sdílet více uživatelů, aniž by pokaždé řešte nastavení zařízení. Když nový uživatel zařízení poprvé vhodí na hlavičku, HoloLens 2 automaticky vyzve uživatele ke ke zkalibraci vizuálů. Když si uživatel, který dříve nakalibroval vizuály, nasaží zařízení na hlavičku, displej se bezproblémově přizpůsobí z pohledu kvality a pohodlného zobrazení.  

### <a name="manually-starting-the-calibration-process"></a>Ruční spuštění procesu zpracování

1. Pomocí gesta spuštění otevřete [ **nabídku Start**](hololens2-basic-usage.md#start-gesture).
1. Pokud aplikace Nastavení není připnutá na **Start,** vyberte **Všechny aplikace.**
1. Vyberte **Settings (Nastavení)** a pak **vyberte System**  >  **Zdůchlovací**  >  **pohled** na  >  **zrak.**

   ![Aplikace Nastavení zobrazující možnost spuštění oka](./images/C-Settings.Calibration.png)

### <a name="auto-eye-position-support"></a>Podpora funkce Auto Eye Position

Pozice očí v HoloLens 2 umožňují přesné umístění hologramu, pohodlné sledování a vylepšenou kvalitu zobrazení. Pozice očí se vypočítává interně jako součást výpočtu sledování očí. To ale vyžaduje, aby každý uživatel prošel sledováním očí, a to i v případě, že prostředí nemusí vyžadovat pohled na pohled.

**AEP (Auto Eye Position)** umožňuje tyto scénáře s bez interakcí vypočítat pozice oka pro uživatele. Funkce Auto Eye Position začne automaticky pracovat na pozadí od okamžiku, kdy uživatel na zařízení nasádá. Pokud uživatel nemá předchozí sledování očí, funkce Auto Eye Position začne poskytovat uživatelům pohled na zobrazovací systém po 20 až 30 sekundách. Uživatelská data se v zařízení neuchová a tento proces se opakuje, pokud se uživatel zasepne a zařízení znovu zapíná nebo pokud se zařízení restartuje nebo vzbudí ze spánku.

Když na zařízení nasádá nezabý uživatel, existuje několik změn chování systému pomocí funkce Automatické umístění oka. V tomto kontextu necibrovaný uživatel odkazuje na někoho, kdo ještě neprošel procesem sledování zraku na zařízení dříve.

| Aktivní aplikace | Předchozí chování | Chování z Windows Holographic, verze 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| Aplikace bez pohledu nebo Holographic Shell |Zobrazí se dialogové okno příkazového řádku sledování očí. | Nezobrazí se žádná výzva. |
| Aplikace s podporou pohledu | Zobrazí se dialogové okno příkazového řádku sledování očí. | Výzva ke sledování očí se zobrazí jenom v případě, že aplikace přistupuje ke streamu pohledu do oka. |

Pokud uživatel přechází z aplikace, která není pohledem povolená, na aplikaci, která přistupuje k pohledným datům, zobrazí se výzva k zadání hledaní. 

Veškeré ostatní chování systému bude podobné, jako když aktuální uživatel nemá aktivní sledování očí. Například gesto Jednoručné spuštění nebude povolené. Při počátečním nastavení se prostředí prvního spuštění nezmění.

Pro prostředí, která vyžadují pohledová data nebo přesné umístění hologramu, doporučujeme necibrovaným uživatelům spustit sledování očí. Je přístupný z příkazového řádku pro sledování očí nebo tak, že v nabídce Start spustíte aplikaci Nastavení a pak vyberete System > Nespouštět > Eye **>** Spuštění oka.

#### <a name="deferred-calibration-prompt"></a>Odložená výzva k odložení aktualizace

Při použití funkce Auto Eye Position se dialog s výzvou k zadání údajů o sledování očí odkládá, dokud aplikace nepožádá o data z pohledu očí. Tím se zajistí, že uživatel nebude vyzván k zobrazení výzvy, když aktivní aplikace nevyžaduje pohled. Pokud aplikace vyžaduje pohled na data a aktuální uživatel není nakalibrován, zobrazí se uživateli výzva k zadání údajů. Toto chování by se mohlo použít k zobrazení výzvy k zadání informací o sledování očí ve vhodnou dobu pro tuto zkušenost. Tato metoda se doporučuje z následujících důvodů:

1.  V dialogovém okně Eye Tracking Prompt se uživateli zobrazí podrobnosti o tom, proč je sledování očí potřeba.
2.  Nabízí uživateli způsob, jak odmítnout zkalibrování očí.

Pokud se uživatel rozhodne spustit sledování očí, měl by se po dokončení instalace vrátit do původní aplikace. 

### <a name="troubleshooting-hololens-2-calibration"></a>Řešení potíží s chybou HoloLens 2

Většina lidí by měla fungovat, ale existují případy, kdy selhání selže.
  
Mezi potenciální důvody selhání patří:

- Rušivé a nenáschodné cíle
- Nečtený nebo poškemkovaný vizuátor zařízení nebo visor zařízení není správně umístěný
- Ušpiněné nebo poškemlené brýle
- Určité typy kontaktních objektivů a brýlí (barevné kontaktní objektivy, některé toric kontaktní objektivy, IR blokující brýle, některé brýle na předpis, sluneční brýle a podobné)
- Výraznější výrazy a některá rozšíření kolií
- Vousy nebo snímky silných brýlí, pokud blokují, aby zařízení vidělo vaše oči
- Určitá neschopná zraková onemocnění, zrakové stavy nebo operace očí, jako jsou zúžení očí, dlouhá lomítka, amblyopia, nystagmus, některé případy LASIK nebo jiné návazné operace oka

Pokud není neúspěšné pokus o přihlášení:

- Vyčištění visoru zařízení
- Čištění brýlí
- Co možná nejvíce nasazování vizuály zařízení do zornice
- Přesunutí objektů do visoru mimo cestu (například vousy)
- Zapnutí světla v místnosti nebo přesun z přímého světla

Pokud jste postupoval podle všech pokynů a stále selhává, můžete výzvu k zadání zakázat v Nastavení. Dejte nám vědět také vyplněním zpětné vazby [na Centrum Feedback](hololens-feedback.md).

Další informace najdete v souvisejících informacích [o řešení potíží s barvou nebo jasem obrázku.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

Nastavení IPD nelze použít pro HoloLens 2, protože pozice oka jsou vypočítávány systémem. 

### <a name="calibration-data-and-security"></a>Údaje a zabezpečení dat

Informace o vývěsce se ukládají místně v zařízení a nejsou přidružené k žádným informacím o účtu. Neexistuje žádný záznam o tom, kdo zařízení použil bez předchozího souhlasu. To znamená, že noví uživatelé budou při prvním použití zařízení vyzváni ke ke zkalibrování vizuálů a uživatelům, kteří se dříve odhodí odhlásit z odběru nebo v případě neúspěšného pokusu o výpadek.

Zařízení může místně ukládat až 50 profilů. Po dosažení tohoto čísla zařízení automaticky odstraní nejstarší nepoužívaný profil.

Informace o ochraně osobních údajů je možné ze zařízení vždy odstranit v   >  **nastaveníChcete-li**  >  **sledovat sledování oka.**  

### <a name="disable-calibration"></a>Zákaz zákazu

Příkazový řádek můžete také zakázat pomocí následujících kroků:

1. Vyberte **Nastavení**  >    >  **kalibrace** systému.
1. Vypnout **, když nová osoba používá tento HoloLens, automaticky požádá o spuštění kalibrace očí**.

> [!IMPORTANT]
> Toto nastavení může nepříznivě ovlivnit kvalitu a pohodlí vykreslování hologramů.  Když toto nastavení vypnete, funkce, které závisejí na sledování očí (například posouvání textu), už nebudou fungovat v moderních aplikacích.

### <a name="hololens-2-eye-tracking-technology"></a>Technologie HoloLens 2 pro sledování očí

Zařízení využívá technologii pro sledování očí ke zlepšení kvality displeje a k zajištění toho, že všechny hologramy jsou umístěné přesně a pohodlné zobrazení v 3D. Vzhledem k tomu, že jako orientačních bodů používá oči, může se zařízení upravit pro každého uživatele a ladit jeho vizuály, protože se mírně posouvá sluchátka.  Veškeré úpravy se probíhají v průběhu bez nutnosti ručního ladění.
> [!NOTE]
> Nastavení IPD se nedá použít pro HoloLens 2, protože pozice očí jsou vypočítané systémem.

Aplikace HoloLens používají sledování očí ke sledování, kde hledáte v reálném čase. Tato funkce umožňuje vývojářům využít k tomu celou novou úroveň kontextu, humánní porozumění a interakce v rámci holografického prostředí. Vývojáři nemusí dělat nic, abyste mohli tuto funkci používat.

## <a name="calibrating-your-hololens-1st-gen"></a>Kalibrace HoloLens (1. generace)

HoloLens (1. generace) upravuje hologram displejů podle [interpupillary vzdálenosti](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD). Pokud IPD není přesná, hologramy můžou být v nestabilní nebo nesprávné vzdálenosti. Kvalitu vizuálů můžete zlepšit kalibrací zařízení na interpupillaryou vzdálenost (IPD).

Když nastavíte zařízení HoloLens (1. gen), zobrazí se výzva k kalibraci vizuálů po dokončení Cortany. Doporučuje se dokončit kalibrační krok během této fáze instalace. Můžete ji ale přeskočit tím, že počkáte, dokud Cortana nevyzve a pak říká "Skip".

Během procesu kalibrace se zaměřuje na to, abyste prst mohli zarovnávat s řadou šesti cílů na oči. HoloLens pomocí tohoto procesu nastavuje IPD správně pro vaše oči.

![IPD prst – obrazovka zarovnání v druhém kroku](./images/ipd-finger-alignment-300px.jpg)

### <a name="manually-start-the-calibration-process"></a>Ruční spuštění procesu kalibrace

Pokud potřebujete aktualizovat kalibraci nebo pokud ji nový uživatel potřebuje upravit, můžete aplikaci pro kalibraci spustit kdykoli ručně. Aplikace kalibrace se nainstaluje ve výchozím nastavení. K němu můžete přistupovat buď pomocí nabídky **Start** , nebo pomocí aplikace nastavení.

Chcete-li použít nabídku **Start** ke spuštění aplikace kalibrace, postupujte podle následujících kroků:

1. Pomocí gesta [Bloom](hololens1-basic-usage.md) otevřete nabídku **Start** .
1. Pokud chcete zobrazit všechny aplikace, vyberte **+** .
1. Vyberte **kalibraci**.

![Přístup k aplikaci kalibrace z prostředí](./images/calibration-shell.png)

![Aplikace kalibrace zobrazená jako živá krychle po spuštění](./images/calibration-livecube-200px.png)

Chcete-li použít aplikaci nastavení ke spuštění aplikace kalibrace, postupujte podle následujících kroků:

1. Pomocí gesta [Bloom](hololens1-basic-usage.md) otevřete nabídku **Start** .
1. Pokud není **Nastavení** připnuté na **Start**, vyberte možnost **+** Zobrazit všechny aplikace.
1. Vyberte **Nastavení**.
1. Vyberte možnost **systémové**  >  **nástroje**  >  **otevřít kalibraci**.

![Spuštění aplikace kalibrace z aplikace nastavení](./images/calibration-settings-500px.jpg)

## <a name="immersive-headsets"></a>Moderní sluchátka

Některé moderní sluchátka poskytují možnost přizpůsobení nastavení IPD. Pokud chcete změnit IPD pro vaši náhlavní soupravu, otevřete aplikaci nastavení a vyberte displej se **smíšenými** možnostmi  >  **sluchátek** a pak přesuňte ovládací prvek posuvníku. Změny se zobrazí v reálném čase v rámci svých sluchátek. Pokud víte, že jste IPD, možná jste navštívili optometrist, můžete ho zadat také přímo.

Toto nastavení můžete na svém počítači upravit i tak, že vyberete **Nastavení**  >  displeje se zobrazením náhlavní soupravy ve **smíšeném realitu**  >  .

Pokud vaše náhlavní souprava nepodporuje přizpůsobení IPD, toto nastavení se zakáže.
