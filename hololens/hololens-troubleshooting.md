---
title: Řešení potíží se zařízeními HoloLens
description: Aktuální informace o nejběžnějších řešeních problémů se zařízeními HoloLens a jejich řešení
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: issues, bug, troubleshoot, fix, help, support, HoloLens, emulator
ms.openlocfilehash: b69dddf04ac31b69f0b2f8759d095806189f33ab
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924617"
---
# <a name="device-troubleshooting"></a>Řešení potíží se zařízeními

Tento článek popisuje, jak vyřešit několik běžných problémů s HoloLens.

>[!IMPORTANT]
> Než začnete s řešením potíží, ujistěte se, že je vaše zařízení naúčtované **na 20 až 40** % kapacity baterie, pokud je to možné. Indikátory [baterie umístěné](hololens2-setup.md#lights-that-indicate-the-battery-level) pod tlačítkem napájení jsou rychlým způsobem, jak ověřit kapacitu baterie bez přihlášení k zařízení.

<a id="list"></a>

**Známé problémy**
- [Video remote assist se zablokuje po 20 minutách](#remote-assist-video-freezes-after-20-minutes)
- [Automatické přihlášení žádá o přihlášení](#auto-login-asks-for-log-in)
- [Microsoft Edge spuštění se nepovede](#microsoft-edge-fails-to-launch)
- [Klávesnice se přepne na speciální znaky](#keyboard-doesnt-switch-to-special-characters)
- [Při stahování uzamčených souborů se nez zobrazení chyby](#downloading-locked-files-doesnt-error)
- [Portál zařízení nahrání nebo stažení souboru](#device-portal-file-uploaddownload-times-out)
- [Modrá obrazovka po zrušení registrace z insider ve verzi Preview na zařízení blikající sestavením Insider](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [OneDrive automaticky nenahraje obrázky](#onedrive-doesnt-automatically-upload-pictures)

**Obecné**
- [HoloLens nereaguje nebo se nespustí](#hololens-is-unresponsive-or-wont-start)
- [Chyba Nedostatek místa na disku](#low-disk-space-error)
- [Selhání selhání](#calibration-fails)
- [Nemůžu se přihlásit, protože moje HoloLens byla dříve nastavená pro někoho jiného](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [Unity nefunguje](#unity-isnt-working)
- [Portál zařízení s Windows nefunguje správně](#windows-device-portal-isnt-working-correctly)
- [Emulátor HoloLens nefunguje](#the-hololens-emulator-isnt-working)

**Vstup**
- [Nefungují hlasové příkazy](#voice-commands-arent-working)
- [Ruční vstup nefunguje](#hand-input-isnt-working)

**Připojení**
- [Nelze se připojit k Wi-Fi](#cant-connect-to-wi-fi)

**Externí zařízení** 
- [Zařízení Bluetooth se neschová](#bluetooth-devices-arent-pairing)
- [Mikrofon USB-C nefunguje](#usb-c-microphone-isnt-working)
- [Zařízení uvedená jako dostupná v Nastavení nefungují](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>Video remote assist se zablokuje po 20 minutách

> [!NOTE]
> Vzhledem k závažnosti tohoto známého problému jsme v současné době pozastavil dostupnost Windows Holographic verze 21H1. Pokud chcete stále aktualizovat zařízení na 21H1, postupujte podle pokynů v poznámkách k verzi v [horní části stránky.](hololens-release-notes.md)

V nejnovější verzi [Windows Holographic verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1)zaznamenali někteří uživatelé Remote Assistu během volání více než 20 minut zamrznutí videa. Jedná se o **známý problém.**

### <a name="workarounds"></a>Alternativní řešení

#### <a name="restart-in-between-calls"></a>Restartování mezi voláními

Pokud vaše volání přesájí 20 minut a dochází k tomuto problému, zkuste zařízení restartovat. Restartováním zařízení mezi voláními vzdálené pomoci se zařízení aktualizuje a vrátí se do dobrého stavu.

Pokud chcete rychle restartovat zařízení na Zařízení s [Windows Holographic verze 21H1,](hololens-release-notes.md#windows-holographic-version-21h1) otevřete nabídku Start, vyberte ikonu uživatele a pak vyberte **Restartovat.**

#### <a name="revert-to-an-older-build"></a>Návrat ke starší verzi sestavení

Někteří zákazníci zjistili, že při návratu ke starší verzi operačního systému už tento problém nemají. Pokud jste zjistili, že u vašich zařízení dochází k tomuto problému, zkuste následující kroky:


Alternativní řešení:

- Pokud je pro vaši firmu přijatelné, je u uživatelských účtů Microsoft podporováno automatické nahrávání fotoaparátu. K pracovnímu nebo školnímu účtu se účet Microsoft přihlásit i ke svému pracovnímu nebo školnímu účtu (aplikace OneDrive podporuje duální přihlášení). Ve svém účet Microsoft v rámci OneDrivu můžete povolit automatické nahrávání fotoaparátů na pozadí.

- Pokud nemůžete bezpečně používat uživatelský účet účet Microsoft k automatickému nahrávání fotek, můžete fotky z aplikace OneDrive nahrát ručně do svého pracovního nebo školního účtu. Pokud to chcete udělat, ujistěte se, že jste v aplikaci OneDrive přihlášení ke svému pracovnímu nebo školnímu účtu. Vyberte tlačítko **+** a zvolte **Nahrát.** Najděte fotky nebo videa, které chcete nahrát, tak, že přejdete na Obrázky **> fotoaparátu.** Vyberte fotky nebo videa, která chcete nahrát, a pak vyberte **tlačítko** Otevřít.


1. [Stažení buildu pro Windows Holographic verze 20H2 – aktualizace z května 2021](https://aka.ms/hololens2download/10.0.19041.1146)
1. Postupujte podle [pokynů a vraťte se k předchozí verzi operačního systému.](hololens-update-hololens.md#go-back-to-a-previous-version)
1. Aktualizace [operačního systému můžete na zařízení pozastavit ručně](hololens-updates.md#pause-updates-via-device) nebo u mnoha zařízení používat [odložení prostřednictvím MDM.](hololens-updates.md#configure-an-update-deferral-policy)

[Zpět na seznam](#list)

## <a name="auto-login-asks-for-log-in"></a>Automatické přihlášení žádá o přihlášení

Zařízení HoloLens 2 je možné nakonfigurovat tak, aby se automaticky přihlašoval přes Nastavení Účty Možnosti přihlášení -> a v části  ->    ->    Požadováno na hodnotu Nikdy **.** Někteří uživatelé se při aktualizaci zařízení s podstatně velkou aktualizací, jako je třeba aktualizace funkcí, mohou znova přihlásit k zařízení. Jedná se o **známý problém.**

Příklad, kdy k tomu může dojít:

- Aktualizace zařízení z Windows Holographic verze 2004 (build 19041.xxxx) na Windows Holographic verze 21H1 (build 20346.xxxx)
- Aktualizace zařízení tak, aby šouplodou aktualizaci ve stejném hlavním buildu, např. Windows Holographic, verze 2004 na Windows Holographic, verze 20H2
- Aktualizace zařízení z image továrny na nejnovější image

K tomu by nemělo dojít během:

- Zařízení, která mají měsíční servisní aktualizaci

Alternativní metody:

- Metody přihlášení, jako jsou PIN, heslo, Iris, webové ověřování nebo klíče FIDO2.
- Pokud pin kód zařízení nelze zapamatovat a jiné metody ověřování nejsou k dispozici, může uživatel použít režim [ručního lomítka](hololens-recovery.md#manual-procedure).

[Zpět na seznam](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge spuštění se nepovede

> [!NOTE]
> Tento problém byl původně vytvořen s náklady na Microsoft Edge verzí. Tento problém se může vyřešit v [nové Microsoft Edge](hololens-new-edge.md). Pokud ne, zpětnou vazbu nahlaste.

Několik zákazníků nahlásilo problém, kdy Microsoft Edge spuštění. U těchto zákazníků problém přetrvává i po restartování a nevyřeší se aktualizacemi aplikací nebo Windows. Pokud k tomuto problému dochází a potvrdili jste, že [je Windows](hololens-updates.md#manually-check-for-updates)aktuální, zakažte chybu z aplikace [Centrum Feedback](hololens-feedback.md) s následující kategorií a podkate kategorií: Instalace a aktualizace > Stažení, instalace a konfigurace služba Windows Update.

Neexistují žádná známá alternativní řešení, protože zatím jsme nemohli hlavní příčinu problému. S vyšetřováním vám pomůže Centrum Feedback chyb prostřednictvím webu společnosti. Jedná se o **známý problém.**

[Zpět na seznam](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>Klávesnice se přepne na speciální znaky

Při ooBE dochází k problému, kdy se po zvolení pracovního nebo školního účtu a zadání hesla uživatel pokouší přepnout na speciální znaky na klávesnici klepnutím na tlačítko &123, nezmění se na speciální znaky. Jedná se o **známý problém.**

Obchádky:
-   Zavřete klávesnici a znovu ji otevřete klepnutím na textové pole.
-   Nesprávně zadejte heslo. Při příštím spuštění klávesnice bude klávesnice fungovat podle očekávání.
- Webové ověřování, zavřete klávesnici a vyberte **Přihlásit se z jiného zařízení**.
-   Pokud zadáváte jenom čísla, uživatel může stisknutím a podržením určitých kláves otevřít rozbalenou nabídku.
-   Pomocí klávesnice USB.

To nemá vliv na:
- Uživatelé, kteří se rozhodnout použít osobní účet.

[Zpět na seznam](#list)


## <a name="downloading-locked-files-doesnt-error"></a>Při stahování uzamčených souborů se ne zobrazí chyba
> ! POZNÁMKA: Jedná se o **známý problém,** který je opraven Windows Insider buildu verze 20348.1403.


Při pokusu o stažení uzamčeného souboru v předchozích sestaveních Windows Holographic by výsledkem byla chybová stránka HTTP. V aktualizaci Windows holografické verze 21H1, která se pokouší stáhnout uzamčený soubor, by nedocházelo k žádnému zobrazení výsledků, soubor se nestáhne a nebude k dispozici žádná chyba. 

[Zpět na seznam](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Časový limit nahrávání nebo stahování souboru portálu zařízení
> ! Poznámka: Jedná se o **známý problém** , který je opravený v buildu Windows Insider build verze 20348,1403. Pokud jste v rámci alternativního řešení dříve zakázali připojení SSL, důrazně doporučujeme ho znovu povolit.


Někteří zákazníci zjistili, že při pokusu o nahrání nebo stažení souborů se může zdát, že se operace zablokuje a vyprší časový limit nebo není možné ji ještě dokončit. To je oddělené od[známého problému "File Locked"](#downloading-locked-files-doesnt-error) – to má vliv na Windows holografické verze 2004, 20H2 a 21H1 buildů v rámci trhu. Problém byl kořenem způsoben chybou v manipulaci s některými požadavky na portálu zařízení a při použití protokolu HTTPS, který je výchozím nastavením, se obvykle vychází. 

### <a name="workaround"></a>Alternativní řešení

Toto alternativní řešení, které platí stejně jako Wi-Fi a UsbNcm, je zakázat možnost "požadované" v části "připojení SSL". Provedete to tak, že přejdete na portál zařízení, **systém** a vyberete stránku **Předvolby** . V části **zabezpečení zařízení** vyhledejte **připojení SSL** a zrušte kontrolu, aby se vypnulo **povinné**.

Uživatel by pak měl přejít na http://, ne na https://(IP adresa) a funkce, jako je nahrání souboru, a stahování bude fungovat.

[Zpět na seznam](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Modrá obrazovka po odregistraci z programu Insider Preview na zařízení, které se postavilo pomocí buildu Insider

To má vliv na to, že se to týká uživatelů, kteří byli ve buildu Insider Preview, a pak si v programu Insider znovu založili nové sestavení Insider Preview a pak se zruší jeho registrace. Jedná se o **známý problém**.

To nemá vliv na:
- Uživatelé, kteří nejsou zaregistrovaní ve Windows Insider 
- Insider
    - Pokud bylo zařízení zaregistrováno, protože buildy Insider byly verze 18362. x
    - Pokud se v programu Insider nastavila aplikace Insider podepsaná 19041. x a zůstane zaregistrovaná v programu Insider

Práce v tomto okolí: 
- Vyhnout se problému 
    - Zabliká Build bez programu Insider. Jedna z pravidelných měsíčních aktualizací.
    - Zůstat ve verzi Insider Preview
- Rozsvítit zařízení

    1. Vložte [HoloLens 2 do režimu blesku](hololens-recovery.md) ručně, a to tak, že se nepřipojíte. Pak klepněte na tlačítko napájení.
    
    1. Připojte se k počítači a otevřete Průvodce pokročilým obnovením.
    
    1. Zablikají do výchozího buildu HoloLens 2.

[Zpět na seznam](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive neodesílá automaticky obrázky.

Aplikace OneDrive pro HoloLens nepodporuje automatické nahrávání fotoaparátů pro pracovní nebo školní účty. Jedná se o **známý problém**.

Alternativní řešení:

- Pokud je pro vaši firmu životaschopná, je automatické nahrávání kamery podporované u zákaznických účtů Microsoft. Můžete se přihlásit k účet Microsoft kromě pracovního nebo školního účtu (aplikace OneDrive podporuje duální přihlášení). Z profilu účet Microsoft v rámci OneDrivu můžete povolit automatické nahrávání snímků na pozadí.

- Pokud nemůžete bezpečně použít účet Microsoft příjemce k automatickému nahrávání vašich fotografií, můžete fotky do svého pracovního nebo školního účtu ručně nahrát z aplikace OneDrive. Abyste to mohli udělat, ujistěte se, že jste se přihlásili ke svému pracovnímu nebo školnímu účtu v aplikaci OneDrive. Vyberte **+** tlačítko a zvolte **nahrát**. Najděte fotky nebo videa, která chcete nahrát, přechodem na **obrázky >ou kamerou**. Vyberte fotky nebo videa, která chcete nahrát, a pak vyberte tlačítko **otevřít** .

[Zpět na seznam](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens nereaguje nebo se nespustí.

Pokud se váš HoloLens nespustí:

- Pokud se indikátory LED vedle tlačítka napájení nekontrolují, nebo se jenom jeden z nich může krátce rozsvítit, možná budete muset [svůj HoloLens účtovat.](hololens2-charging.md#charging-the-device)
- Pokud při stisknutí tlačítka napájení zhasnou diody LED, ale nevidíte cokoli na zobrazených displejech, [proveďte obnovení zařízení](hololens-recovery.md#hard-reset-procedure).

Pokud vaše HoloLens přestane být zmrazené nebo neodpovídá:

- Vypněte HoloLens tak, že stisknete tlačítko napájení, dokud se všechny pět diod LED nevypne, nebo 15 sekund, pokud indikátory LED nereagují. Chcete-li zahájit HoloLens, stiskněte tlačítko napájení znovu.

Pokud tyto kroky nefungují, můžete zkusit [obnovit zařízení HoloLens 2](hololens-recovery.md) nebo [HoloLens (1. generace).](hololens1-recovery.md)

[Zpět na seznam](#list)

## <a name="low-disk-space-error"></a>Chyba "nedostatek místa na disku"

K uvolnění úložného prostoru budete potřebovat jednu nebo více následujících akcí:

- Odstraňte některé nepoužité mezery. V **Nastavení**  >    >  **prostory** pro systém, vyberte místo, které už nepotřebujete, a pak vyberte **Odebrat**.
- Odeberte některé hologramy, které jste umístili.
- Odstraňte z aplikace Fotky některé obrázky a videa.
- Odinstalujte některé aplikace z HoloLens. V seznamu **všechny aplikace** klepněte na aplikaci, kterou chcete odinstalovat, a pak vyberte **odinstalovat**.

[Zpět na seznam](#list)

## <a name="calibration-fails"></a>Neúspěšná kalibrace

Kalibrace by měla fungovat pro většinu lidí, ale existují případy, kdy se kalibrace nezdařila.
  
Mezi případné důvody pro selhání kalibrace patří:

- Odčítání a nikoli za cíle kalibrace
- Nesprávné umístění zařízení hypervisoru nebo zařízení na začátku
- Nezměněná nebo škrábancová skla
- Určité typy kontaktních skel a brýle (barevná čočka, některá torica kontaktu, poblokovaná brýle, některá brýle s vysokým předpisem, Sunglasses nebo podobné)
- Více vyslovované strukturu a některá rozšíření eyelash
- Chlupy nebo silné eyeglass snímky, pokud si zařízení blokuje zobrazení očí
- Určité Physiology oka, podmínky očí nebo oční chirurgie, jako je úzká oči, Long Eyelashes, amblyopia, nystagmus, některé případy LASIK nebo jiné oči surgeries

Pokud kalibrace neproběhne úspěšně, zkuste:

- Čištění zařízení s clonou
- Čištění vašich brýle
- Co nejblíže vašim očí vám umožní obzradit své zařízení.
- Přesun objektů ve vašem seznamu clony (například vlasy)
- Zapnutí světla v místnosti nebo přemístění přímého slunečního záření

Pokud jste postupovali podle všech pokynů a kalibrace stále selhává, můžete výzvu k kalibraci zakázat v nastavení. Dejte nám taky vědět, že vám zašleme zpětnou vazbu v [centru Feedback](hololens-feedback.md).

Podívejte se také na související informace o [barvě obrázku nebo odstraňování potíží s jasem.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

Nastavení IPD se nedá použít pro HoloLens 2, protože pozice očí jsou vypočítané systémem. 

[Zpět na seznam](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>Nelze se přihlásit, protože byl již dříve nastaven můj HoloLens pro někoho jiného.

Zařízení můžete [Přepnout do **režimu blikání** a obnovit zařízení pomocí pokročilého Průvodce obnovením](hololens-recovery.md#clean-reflash-the-device) .

[Zpět na seznam](#list)


## <a name="unity-isnt-working"></a>Unity nefunguje

- Přečtěte si téma [Instalace nástrojů](/windows/mixed-reality/install-the-tools) pro nejaktuálnější verzi Unity, doporučená pro vývoj pro HoloLens.
- Známé problémy s nástrojem Unity HoloLens Technical Preview jsou popsány ve [fórech Unity pro HoloLens](https://forum.unity3d.com/threads/known-issues.394627/).

[Zpět na seznam](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Portál zařízení s Windows nepracuje správně.

- Funkce Live Preview v rámci hybridního zachycení realit může při latenci vykazovat několik sekund.

- Na stránce virtuálního vstupu nejsou funkční gesta a posuvníky v části virtuální gesta. Jejich použití nebude mít žádný vliv. Virtuální klávesnice na stránce virtuálního vstupu funguje správně.

- Po povolení režimu vývojářů v nastavení může trvat několik sekund, než se zapne přepínač, aby se aktivoval portál zařízení.

[Zpět na seznam](#list)

## <a name="emulator"></a>Emulátor
### <a name="the-hololens-emulator-isnt-working"></a>Emulátor HoloLens nefunguje

Informace o emulátoru HoloLens najdete v naší dokumentaci pro vývojáře.  Přečtěte si další [informace o řešení potíží s emulátorem HoloLens.](/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)


- Ne všechny aplikace v Microsoft Store jsou kompatibilní s emulátorem. Například Young Conker a Fragmenty se v emulátoru nehrají.
- V emulátoru nemůžete použít webovou kameru počítače.
- Funkce Live Preview v Portál zařízení s Windows nefunguje s emulátorem. Stále můžete zachytit Mixed Reality videa a obrázky.

[Zpět na seznam](#list)

## <a name="i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator"></a>Nemůžu najít nebo použít klávesnici k zadání v emulátoru HoloLens 2

*Připravujeme*

[Zpět na seznam](#list)

## <a name="voice-commands-arent-working"></a>Nefungují hlasové příkazy

Pokud Cortana nereaguje na vaše hlasové příkazy, ujistěte se, že je zapnutá Cortana. V seznamu Všechny aplikace poznámkového bloku **nabídky Cortany** proveďte  >    >    >   změny. Další informace o tom, co můžete říct, najdete v [tématu Použití hlasu s HoloLens.](hololens-cortana.md)

V HoloLens (1. generace) není integrované rozpoznávání řeči konfigurovatelné. Vždy je zapnutý. Na HoloLens 2 můžete zvolit, jestli se má při nastavování zařízení zapnout rozpoznávání řeči i Cortana.

Pokud HoloLens 2 nereaguje na váš hlas, ujistěte se, že je zapnuté rozpoznávání řeči. Přejděte na **Start Settings** Privacy Speech  >    >  **(Spustit nastavení ochrany**  >  **osobních údajů) Speech** a zapněte **rozpoznávání řeči.**

[Zpět na seznam](#list)

## <a name="hand-input-isnt-working"></a>Ruční vstup nefunguje

Abyste zajistili, že HoloLens uvidí vaše ruce, musíte je ponechat v snímku gest.  Domovská Mixed Reality poskytuje zpětnou vazbu, která vám dá vědět, kdy jsou vaše ruce sledované.  Názory na různé verze HoloLens se liší:
- V HoloLens (1. generace) se kurzor pohledu změní z tečky na kruh.
- Na HoloLensu 2 se zobrazí kurzor prstu, když je vaše ruce blízko slate, a když jsou břidíčky dále, zobrazí se ruční paprsk.

Řada imerzivních aplikací dodržuje vzory vstupu, které se podobají Mixed Reality Domovské obrazovce.  Přečtěte si další informace o použití ručního vstupu [v HoloLens (1. generace)](hololens1-basic-usage.md#use-hololens-with-your-hands) a [HoloLens 2.](hololens2-basic-usage.md#the-hand-tracking-frame)

Pokud máte problémy s nosem, mějte na vědomí, že některé typy choumů nefungují se sledováním rukou.  Běžným příkladem je černá guma, která obvykle absorbuje infračervené světlo a nenabírá je hloubková kamera.  Pokud vaše práce zahrnuje gumové gumy, doporučujeme, abyste si zkusili světlejší barvu, například modrou nebo šedou.  Dalším příkladem je velká nesrozumilá aplikace, která má tendenci zakrytí tvaru vaší ruky. Pro nejlepší výsledky doporučujeme použít co nejvíce tvarování.

Pokud má váš vizuátor otisky prstů nebo šmouhy, vyčistěte vizuály pomocí mikrovlákna, které jste dodáli s HoloLens.

[Zpět na seznam](#list)

## <a name="cant-connect-to-wi-fi"></a>Nelze se připojit k Wi-Fi

Tady je několik věcí, které můžete vyzkoušet, pokud nemůžete holoLens připojit k Wi-Fi síti:

- Ujistěte se, Wi-Fi je zapnuté. Kontrolu můžete provést pomocí gesta Start a pak vyberte  >  **NastaveníSítě &amp; Internet**  >  **Wi-Fi.** Pokud Wi-Fi, zkuste ho vypnout a znovu zas.
- Přesuňte se blíže ke směrovači nebo přístupovému bodu.
- Restartujte svůj Wi-Fi směrovač a [pak restartujte HoloLens.](hololens-recovery.md) Zkuste se připojit znovu.
- Pokud nic z toho nefunguje, zkontrolujte, že váš směrovač používá nejnovější firmware. Tyto informace najdete na webu výrobce.

[Zpět na seznam](#list)
## <a name="bluetooth-devices-arent-pairing"></a>Zařízení Bluetooth se neschová

Pokud máte problémy s [párování zařízení Bluetooth,](hololens-connect-devices.md)zkuste následující postup:

- Přejděte na **Nastavení** Zařízení a  >  ujistěte se, že je zapnuté Bluetooth. Pokud je, vypněte ho a znovu ho zapněte.
- Ujistěte se, že je vaše zařízení Bluetooth plně nabité nebo je nabité čerstvými bateriemi.
- Pokud se stále nemůžete připojit, [restartujte HoloLens.](hololens-recovery.md)

[Zpět na seznam](#list)

## <a name="usb-c-microphone-isnt-working"></a>Mikrofon USB-C nefunguje
Uvědomte si, že některé mikrofony USB-C se nesprávně hlásí jako *mikrofon* i jako mluvčí. Jedná se o problém s mikrofonem, a ne s HoloLensem. Při připojování jednoho z těchto mikrofonů k HoloLens může dojít ke ztrátě zvuku. Naštěstí existuje jednoduchá oprava.  

V **nastavení**  ->  **Zvuk**  ->  **systému** explicitně nastavte předdefinování **mluvčích (zvukový ovladač analogové funkce)** jako **výchozí zařízení.** HoloLens by si toto nastavení měl zapamatovat, i když se mikrofon později odebere a znovu připojí.

![Řešení potíží s mikrofony USB-C](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>Zařízení uvedená jako dostupná v Nastavení nefungují

HoloLens (1. generace) nepodporuje zvukové profily Bluetooth. Zvuková zařízení Bluetooth, jako jsou mluvčí a náhlavní soupravy, se dají zobrazit jako dostupná v nastavení HoloLens, ale nejsou podporovaná.

HoloLens 2 podporuje zvukový profil Bluetooth A2DP pro stereo přehrávání. Profil Bluetooth Hands Free, který umožňuje zachytávání mikrofonu z periferního zařízení Bluetooth, není na HoloLens 2 podporovaný.

Pokud máte potíže s používáním zařízení Bluetooth, ujistěte se, že se jedná o podporované zařízení. Mezi podporovaná zařízení patří:

- Klávesnice QWERTY bluetooth v anglickém jazyce (můžete je použít kdekoli, kde používáte holografičovou klávesnici).
- Bluetooth mice.
- Kliknutí [na HoloLens](hololens1-clicker.md)

S HoloLens můžete spárovat další zařízení BLUETOOTH HID a PAIR. Je však možné, že budete muset nainstalovat odpovídající doprovodné aplikace z Microsoft Store, aby bylo možné zařízení skutečně používat.

[Zpět na seznam](#list)
