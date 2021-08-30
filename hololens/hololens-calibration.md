---
title: Vylepšení vizuální kvality a komfortu
description: Zjistěte, jak nakalibrovat vzdálenost mezi aplikacemi (IPD), abyste zlepšili kvalitu vizuálů na HoloLens zařízeních.
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
keywords: ádna, komfort, vizuály, kvalita, IPD, HoloLens, Windows Mixed Reality, náhlavní soupravy VR
ms.openlocfilehash: b3d917c71ac7441aeaf8dcbc25748ee07b9fbfa3
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189201"
---
# <a name="improve-visual-quality-and-comfort"></a>Vylepšení vizuální kvality a komfortu

HoloLens 2 a HoloLens (1. generace) fungují lépe, když jsou nakalibrovány na vaše jedinečné pohledy.

I když se obě zařízení musí nakalibrovat, aby bylo zobrazení hologramu co nejlepší, používají různé technologie a techniky pro práci s hologramy.  Přeskočte [na HoloLens 2](#calibrating-your-hololens-2) nebo [HoloLens (1. generace).](#calibrating-your-hololens-1st-gen)

## <a name="calibrating-your-hololens-2"></a>Nakalibrování HoloLens 2

HoloLens 2 využívá technologii sledování očí k vylepšení vašich zkušeností se sledováním virtuálního prostředí a interakcí s ním. Nakalibrování HoloLens 2 zajistí, že dokáže přesně sledovat vaše oči (a pohledy kohokoli jiného, kdo zařízení používá). Pomáhá také s komfortem uživatele, zarovnáním hologramu a sledováním rukou. Po dokončení se hologramy zobrazí správně, i když se visor posune na vaší hlavy.

HoloLens 2 vyzve uživatele ke zkalibraci zařízení za následujících okolností:

- Uživatel používá zařízení poprvé.
- Uživatel se dříve odhlásit z procesu zpracování
- Proces zpracování nebyl úspěšný při posledním použití zařízení uživatelem.
- Uživatel odstranil profily profilů uživatelů.
- Zařízení se vypne a znovu zasune a platí jakákoli z výše uvedených okolností. 


![Výzva k úpravě očí.](./images/07-et-adjust-for-your-eyes.png)

Během tohoto procesu se podíváte na sadu cílů (gemy). Je v pořádku, pokud blikáte během průběhu průběhu, ale snažte se soustředit na gemy místo na jiné objekty v místnosti.  Když se zaměříte na gemy, HoloLens získat informace o vaší pozici v kůlu k vykreslení holografického světa.

![Výzva k zadání výzvy uživateli, aby si udrželi hlavičku a sledovali tečky pohledem.](./images/07-et-hold-head-still.png)

![Ukázka výzvy k zadání gemu](./images/08-et-gems.png)

![Úprava výzvy k zadání oprávnění](./images/09-et-adjusting.png)

Pokud byla úspěšná, zobrazí se obrazovka s úspěchem.  Pokud ne, přečtěte si další informace [o diagnostice selhání onemocnění.](hololens2-display.md#troubleshooting)

![Výzva k úspěšnému zadání](./images/10-et-success.png)

### <a name="calibration-when-sharing-a-device-or-session"></a>Narušení při sdílení zařízení nebo relace

Více uživatelů může sdílet HoloLens 2 zařízení, aniž by pokaždé šoul k nastavení zařízení. Když nový uživatel poprvé vhodí zařízení na hlavičku, HoloLens 2 automaticky vyzve uživatele ke ke zkalibraci vizuálů. Když si uživatel, který předtím nakalibroval vizuály, nasaží zařízení na hlavičku, displej se bezproblémově přizpůsobí kvalitě a pohodlnému prostředí pro sledování.  

### <a name="manually-starting-the-calibration-process"></a>Ruční spuštění procesu zpracování

1. Pomocí gesta spuštění otevřete [**nabídka Start**](hololens2-basic-usage.md#start-gesture).
1. Pokud Nastavení aplikace není připnutá na **Start,** vyberte **Všechny aplikace.**
1. Vyberte **Nastavení** a pak vyberte **System**  >  **Chemimho**  >  **pohledu** na  >  **pohyb oka.**

   ![Aplikace Nastavení, která zobrazuje možnost spuštění oka.](./images/C-Settings.Calibration.png)

### <a name="auto-eye-position-support"></a>Podpora funkce Auto Eye Position

Ve HoloLens 2 umožňují pozice očí přesné umístění hologramu, pohodlné sledování a vylepšenou kvalitu zobrazení. Pozice očí se vypočítává interně jako součást výpočtu sledování očí. To ale vyžaduje, aby každý uživatel prošel sledováním očí, a to i v případě, že prostředí nemusí vyžadovat pohled na pohled.

**Funkce Auto Eye Position (AEP)** umožňuje tyto scénáře s bez interakcí vypočítat pozice oka pro uživatele. Funkce Auto Eye Position začne automaticky pracovat na pozadí od okamžiku, kdy uživatel na zařízení nasádá. Pokud uživatel nemá předchozí sledování očí, funkce Auto Eye Position začne poskytovat uživateli pohled na zobrazovací systém po 20 až 30 sekundách. Uživatelská data se v zařízení neuchová a tento proces se opakuje, pokud uživatel zařízení vypne a znovu zapíná nebo pokud se zařízení restartuje nebo vzbudí ze spánku.

Když na zařízení nasadí neomezaný uživatel, existuje několik změn chování systému pomocí funkce Automatické umístění oka. V tomto kontextu necibrovaný uživatel odkazuje na někoho, kdo ještě neprošel procesem sledování zraku na zařízení dříve.

| Aktivní aplikace | Předchozí chování | Chování z Windows Holographic, verze 20H2 Update |
|:-------------------|:-----------------|:-----------------------------------|
| Aplikace bez pohledu nebo Holographic Shell |Zobrazí se dialogové okno příkazového řádku sledování očí. | Nezobrazí se žádná výzva. |
| Aplikace s podporou pohledu | Zobrazí se dialogové okno příkazového řádku sledování očí. | Výzva ke sledování očí se zobrazí jenom v případě, že aplikace přistupuje ke streamu pohledu do oka. |

Pokud uživatel přechází z aplikace, která není pohledem povolená, na aplikaci, která přistupuje k pohledným datům, zobrazí se výzva k přihlášení. 

Veškeré ostatní chování systému bude podobné, jako když aktuální uživatel nemá aktivní sledování očí. Například gesto Jednoručné spuštění nebude povolené. Při počátečním nastavení se prostředí prvního spuštění nezmění.

Pro prostředí, která vyžadují pohledová data nebo přesné umístění hologramu, doporučujeme necibrovaným uživatelům spustit sledování očí. Je přístupná z příkazového řádku sledování očí nebo spuštěním aplikace Nastavení z nabídky Start a výběrem možnosti System > Átestečka > **Eye átečka**> Spuštění oka.

#### <a name="deferred-calibration-prompt"></a>Odložená výzva k odložení aktualizace

Při použití funkce Auto Eye Position se dialog s výzvou k zadání údajů o sledování očí odkládá, dokud aplikace nepožádá o data z pohledu oka. Tím se zajistí, že uživatel nebude vyzván k zobrazení výzvy, když aktivní aplikace nevyžaduje pohled. Pokud aplikace vyžaduje pohled na data a aktuální uživatel není nakalibrován, zobrazí se uživateli výzva k zadání údajů. Toto chování by se mohlo použít k zobrazení výzvy k zadání informací o sledování očí ve vhodnou dobu pro tuto zkušenost. Tato metoda se doporučuje z následujících důvodů:

1.  V dialogovém okně Prompt pro sledování očí se uživateli zobrazí podrobnosti o tom, proč je sledování očí potřeba.
2.  Nabízí uživateli způsob, jak odmítne zkalibrovat oči.

Pokud se uživatel rozhodne spustit sledování očí, měl by se po dokončení instalace vrátit do původní aplikace. 

### <a name="calibration-data-and-security"></a>Údaje a zabezpečení dat

Informace o vývěsce se ukládají místně v zařízení a nejsou přidružené k žádným informacím o účtu. Neexistuje žádný záznam o tom, kdo zařízení použil bez předchozího souhlasu. To znamená, že noví uživatelé budou při prvním použití zařízení vyzváni ke zkalibrování vizuálů a uživatelé, kteří se dříve odhlásit z odběru nebo v případě neúspěšného pokusu o výpadek.

Zařízení může místně ukládat až 50 profilů. Po dosažení tohoto čísla zařízení automaticky odstraní nejstarší nepoužívaný profil.

Informace o ochraně osobních údajů je možné ze zařízení vždy Nastavení  >    >  **sledováním soukromí.**  

### <a name="disable-calibration"></a>Zákaz zákazu

Příkazový řádek můžete také zakázat pomocí následujících kroků:

1. Vyberte **Nastavení**  >  **SystemChemeate.**  >  
1. Vypnout **Když nový člověk používá tento HoloLens, automaticky požádejte, aby spouštěl zrak.**

   > [!IMPORTANT]
   > Toto nastavení může negativně ovlivnit kvalitu a komfort vykreslování hologramu.  Když toto nastavení vypnete, funkce, které závisí na sledování očí (například posouvání textu), už nebudou fungovat v imerzivních aplikacích.

> [!NOTE]
> Od Nastavení holografické verze 20H2 jsme odebrali přepínač Windows s podporou automatické [pozice oka.](hololens-release-notes.md#auto-eye-position-support) Výzva k přihlášení se automaticky zobrazí pouze v případě, že nezabý uživatel používá aplikaci s podporou sledování očí.

### <a name="hololens-2-eye-tracking-technology"></a>HoloLens 2 technologie sledování očí

Zařízení využívá technologii sledování očí ke zlepšení kvality zobrazení a k zajištění toho, aby všechny hologramy byly přesně a pohodlně zobrazeny ve 3D. Vzhledem k tomu, že zařízení používá oči jako orientační body, může se přizpůsobit pro každého uživatele a vyladit své vizuály, když se náhlavní souprava posouvá poněkud během používání.  K veškerým úpravám dochází za běhu bez nutnosti ručního ladění.
> [!NOTE]
> Nastavení IPD nelze použít pro Hololens 2, protože pozice oka se počítají systémem.

HoloLens aplikace používají sledování očí ke sledování toho, kde v reálném čase hledáte. Toto jsou hlavní funkce, které vývojáři mohou využít k tomu, aby v holografickém prostředí umožnili zcela novou úroveň kontextu, porozumění člověku a interakci. Vývojáři nemusí k používání této funkce nic dělat.

## <a name="calibrating-your-hololens-1st-gen"></a>Calibrating your HoloLens (1. generace)

HoloLens (1. generace) upraví zobrazení hologramu podle [vaší interpupilární vzdálenosti](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD). Pokud IPD není přesné, hologramy se mohou jeví jako nestabilní nebo v nesprávné vzdálenosti. Kvalitu vizuálů můžete vylepšit tím, že zařízení nakalibrujete na vzdálenost mezi sítěmi (IPD).

Při nastavení zařízení HoloLens (1. generace) se po zavedení vizuálů zobrazí výzva ke Cortana vizualizaci. Během této fáze nastavení se doporučuje dokončit tento krok instalace. Můžete ho ale přeskočit tak, že počkáte, Cortana se zobrazí výzva a pak se zobrazí "Přeskočit".

Během procesu zpracování vás HoloLens, abyste si zarovnaní prst s řadou šesti cílů na oko. HoloLens tento proces používá ke správnému nastavení IPD pro vaše oči.

![Obrazovka pro zarovnání prstu s IPD ve druhém kroku.](./images/ipd-finger-alignment-300px.jpg)

### <a name="manually-start-the-calibration-process"></a>Ruční spuštění procesu zpracování

Pokud potřebujete upravit úpravy nebo pokud ji nový uživatel potřebuje upravit, můžete kdykoli ručně spustit aplikaci Chystávku. Ve výchozím nastavení je nainstalovaná aplikace Ásek. Můžete k ní získat přístup pomocí nabídky **Start** nebo Nastavení aplikace.

Pokud chcete ke spuštění aplikaceČískat pomocí nabídky **Start,** postupujte takto:

1. Pomocí gesta [bloom](hololens1-basic-usage.md) otevřete **nabídku Start.**
1. Pokud chcete zobrazit všechny aplikace, vyberte **+** .
1. Vyberte **Možnost.**

   ![Přístup k aplikaci, která se nasaží z prostředí.](./images/calibration-shell.png)

   ![Aplikace, která se zobrazí jako živá datová krychle po spuštění.](./images/calibration-livecube-200px.png)

Pokud chcete ke Nastavení aplikaci Promyšl, postupujte takto:

1. Pomocí gesta [bloom](hololens1-basic-usage.md) otevřete **nabídku Start.**
1. Pokud **Nastavení** možnost Start připnutá,  **+** výběrem zobrazíte všechny aplikace.
1. Vyberte **Nastavení**.
1. Vyberte **System**  >  **Utilities**  >  **OpenÁvna**.

   ![Spuštění aplikace pro aplikaci nastavení](./images/calibration-settings-500px.jpg)

## <a name="immersive-headsets"></a>Imerzivní náhlavní soupravy

Některé imerzivní náhlavní soupravy umožňují přizpůsobit nastavení IPD. Pokud chcete změnit IPD náhlavní soupravy, otevřete aplikaci Nastavení, vyberte displej náhlavní soupravy **Mixed Reality** a potom  >  přesuňte posuvník. Změny se v reálném čase zobrazí v náhlavní soupravě. Pokud znáte svou IPD adresu, můžete ji zadat také přímo z návštěvu optometristy.

Toto nastavení můžete také upravit na počítači tak, že **vyberete** Nastavení  >  **náhlavní soupravy Mixed Reality.**  >  

Pokud náhlavní souprava přizpůsobení IPD nepodporuje, toto nastavení bude zakázané.
