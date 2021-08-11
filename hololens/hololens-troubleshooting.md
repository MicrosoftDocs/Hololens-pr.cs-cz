---
title: HoloLens Řešení potíží se zařízením
description: udržujte si přehled o nejběžnějších řešeních, abyste HoloLens problémy se zařízením a techniky řešení potíží.
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
keywords: problémy, chyba, řešení potíží, oprava, pomoc, podpora, HoloLens, emulátor
ms.openlocfilehash: 5501e036b5852833b7ff26445a98c3378ae6963c96114e26bf588eb33a56f6f0
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662854"
---
# <a name="device-troubleshooting"></a>Řešení potíží se zařízením

tento článek popisuje, jak vyřešit několik běžných HoloLens problémů.

>[!IMPORTANT]
> Než začnete s postupem řešení potíží, ujistěte se, že se na zařízení účtuje **20 až 40 procent** kapacity baterie, pokud je to možné. [Indikátory baterie](hololens2-setup.md#lights-that-indicate-the-battery-level) umístěné pod tlačítkem napájení jsou rychlým způsobem, jak ověřit kapacitu baterie bez přihlášení do zařízení.

<a id="list"></a>

**Známé problémy**
- [Po 20 minutách se zablokuje video vzdálené pomoci.](#remote-assist-video-freezes-after-20-minutes)
- [Automatické přihlášení vyžaduje přihlášení.](#auto-login-asks-for-log-in)
- [spuštění Microsoft Edge se nezdařilo.](#microsoft-edge-fails-to-launch)
- [Klávesnice neumožňuje přepnout na speciální znaky.](#keyboard-doesnt-switch-to-special-characters)
- [Stahování uzamčených souborů nezobrazuje chybu](#downloading-locked-files-doesnt-error)
- [Časový limit nahrávání nebo stahování souboru portálu zařízení](#device-portal-file-uploaddownload-times-out)
- [Modrá obrazovka po odregistraci z programu Insider Preview na zařízení, které se postavilo pomocí buildu Insider](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [OneDrive neodesílá automaticky obrázky](#onedrive-doesnt-automatically-upload-pictures)

**Obecné**
- [HoloLens nereaguje nebo se nespustí](#hololens-is-unresponsive-or-wont-start)
- [Chyba "nedostatek místa na disku"](#low-disk-space-error)
- [Neúspěšná kalibrace](#calibration-fails)
- [nejde se přihlásit, protože můj HoloLens byl dřív nastavený pro někoho jiného.](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [Unity nefunguje](#unity-isnt-working)
- [Windows Portál zařízení nepracuje správně.](#windows-device-portal-isnt-working-correctly)
- [Emulator HoloLens nefunguje](#the-hololens-emulator-isnt-working)

**Vstup**
- [Hlasové příkazy nefungují.](#voice-commands-arent-working)
- [Ruční vstup nefunguje.](#hand-input-isnt-working)

**Připojení**
- [Nejde se připojit k Wi-Fi](#cant-connect-to-wi-fi)

**Externí zařízení** 
- [nepárování zařízení Bluetooth](#bluetooth-devices-arent-pairing)
- [Mikrofon USB-C nefunguje](#usb-c-microphone-isnt-working)
- [zařízení uvedená jako dostupná v Nastavení nefungují](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>Po 20 minutách se zablokuje video vzdálené pomoci.

> [!NOTE]
> Je k dispozici novější verze vzdálené pomoci, která obsahuje opravu tohoto problému. Pokud se chcete tomuto problému vyhnout, [Aktualizujte prosím vzdálenou pomoc](holographic-store-apps.md#update-apps) na nejnovější verzi.

> [!NOTE]
> kvůli této závažnosti známého problému jsme dočasně pozastavili dostupnost Windows holografické verze 21H1. 21H1 Build je teď znovu dostupný, takže zařízení se možná znovu aktualizují na nejnovější sestavení 21H1.

v nejnovější verzi [Windows holografické 21H1 verze](hololens-release-notes.md#windows-holographic-version-21h1), někteří uživatelé programu Remote Assist při volání po dobu 20 minut nastali zamrznutím videa. Jedná se o **známý problém**.

### <a name="workarounds"></a>Alternativní řešení

Pokud nemůžete aktualizovat vzdálenou pomoc na novější Build, zkuste následující postup vyřešit.

#### <a name="restart-in-between-calls"></a>Restartování během mezi voláními

Pokud vaše volání překročí délku 20 minut a dochází k tomuto problému, zkuste zařízení restartovat. Restartování zařízení mezi voláními vzdálené pomoci aktualizuje vaše zařízení a uloží ho zpátky do dobrého stavu.

pokud chcete zařízení rychle restartovat v [Windows holografické 21H1,](hololens-release-notes.md#windows-holographic-version-21h1) otevřete nabídku start a vyberte ikonu uživatele a pak vyberte **restartovat**.

[Zpět na seznam](#list)

## <a name="auto-login-asks-for-log-in"></a>Automatické přihlášení vyžaduje přihlášení.

zařízení HoloLens 2 lze nakonfigurovat tak, aby se automaticky   ->    ->  **přihlásilo prostřednictvím možností přihlášení** Nastavení účty – > a v části **požadováno** nastavení hodnoty na hodnotu **ne**. Někteří uživatelé se můžou po aktualizaci zařízení s podstatně velkou aktualizací, jako je třeba aktualizace funkcí, přihlašovat znovu k zařízení. Jedná se o **známý problém**.

Příklad, kdy by k tomu mohlo dojít:

- aktualizace zařízení z Windows holografické verze 2004 (build 19041. xxxx) na Windows holografická verze 21H1 (build 20346. xxxx)
- aktualizace zařízení, aby se mohla provést velká aktualizace na stejném hlavním buildu, např. Windows holografická verze 2004, Windows holografická verze 20H2
- Aktualizace zařízení z image továrny na nejnovější obrázek

K tomu by nemělo dojít během:

- Zařízení s měsíční aktualizací pro údržbu

Řešení metod:

- Metody přihlašování, jako je PIN kód, heslo, Iris, webové ověřování nebo FIDO2 klíče.
- Pokud se PIN kód zařízení nedá zapamatovat a jiné metody ověřování nejsou k dispozici, může uživatel použít [režim ručního přebliknutí](hololens-recovery.md#manual-procedure).

[Zpět na seznam](#list)

## <a name="microsoft-edge-fails-to-launch"></a>spuštění Microsoft Edge se nezdařilo.

> [!NOTE]
> tento problém byl původně vytvořen v rámci dodací verze Microsoft Edge na mysli. Tento problém se dá vyřešit v [novém Microsoft Edge](hololens-new-edge.md). Pokud ne, pošlete nám svůj názor.

několik zákazníků oznámilo problém, kdy se Microsoft Edge nepodařilo spustit. pro tyto zákazníky se problém opakuje po restartování a nebude vyřešen pomocí Windows nebo aktualizací aplikace. pokud máte tento problém a potvrzujete, že [Windows je aktuální](hololens-updates.md#manually-check-for-updates), zaznamenejte prosím chybu z [aplikace centrum zpětné vazby](hololens-feedback.md) pomocí následující kategorie a podkategorie: nainstalujte a aktualizujte > stahování, instalace a konfigurace web Windows Update.

Neexistují žádná známá řešení, protože se nám nepovedlo hlavní příčinu problému. Podání chyby prostřednictvím centra Feedback vám pomůže s šetřením! Jedná se o **známý problém**.

[Zpět na seznam](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>Klávesnice neumožňuje přepnout na speciální znaky.

Při spuštění OOBE došlo k potížím, kdy uživatel zvolil pracovní nebo školní účet a zadává heslo, a snaží se přepnout na speciální znaky na klávesnici klepnutím na tlačítko &123 se nezmění na speciální znaky. Jedná se o **známý problém**.

Mezipracovaná řešení:
-   Zavřete klávesnici a znovu ji otevřete klepnutím na textové pole.
-   Nesprávně zadejte heslo. Když se při příštím spuštění klávesnice znovu spustí, bude fungovat podle očekávání.
- Webové ověřování, zavřete klávesnici a vyberte **přihlásit z jiného zařízení**.
-   Pokud zadáváte jenom čísla, může uživatel stisknout a držet určité klávesy, aby otevřeli rozbalenou nabídku.
-   Pomocí klávesnice USB.

To nemá vliv na:
- Uživatelé, kteří se rozhodnou použít osobní účet.

[Zpět na seznam](#list)

## <a name="downloading-locked-files-doesnt-error"></a>Stahování uzamčených souborů nechybí

> [!NOTE]
> jedná se o **známý problém** , který je opraven v Windows build Insider verze 20348,1403.

v předchozích sestaveních Windows holografické při pokusu o stažení uzamčeného souboru by výsledkem byla chybová stránka HTTP. v Windows holografické 21H1 aktualizace verze, která se pokouší stáhnout uzamčený soubor, by nedocházelo k žádnému zobrazení, soubor se nestáhne a nebude k dispozici žádná chyba.

[Zpět na seznam](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Časový limit nahrávání nebo stahování souboru portálu zařízení
> [!NOTE]
> jedná se o **známý problém** , který je opraven v Windows build Insider verze 20348,1403. Pokud jste v rámci alternativního řešení dříve zakázali připojení SSL, důrazně doporučujeme ho znovu povolit.


Někteří zákazníci zjistili, že při pokusu o nahrání nebo stažení souborů se může zdát, že se operace zablokuje a vyprší časový limit nebo není možné ji ještě dokončit. to je oddělené od[známého problému "file locked"](#downloading-locked-files-doesnt-error) – to má vliv na Windows holografické verze 2004, 20H2 a 21H1 buildů v rámci trhu. Problém byl kořenem způsoben chybou v manipulaci s některými požadavky na portálu zařízení a při použití protokolu HTTPS, který je výchozím nastavením, se obvykle vychází. 

### <a name="workaround"></a>Alternativní řešení

Toto alternativní řešení, které platí stejně jako Wi-Fi a UsbNcm, je zakázat možnost "požadované" v části "připojení SSL". Provedete to tak, že přejdete na portál zařízení, **systém** a vyberete stránku **Předvolby** . V části **zabezpečení zařízení** vyhledejte **připojení SSL** a zrušte kontrolu, aby se vypnulo **povinné**.

Uživatel by pak měl přejít na http://, ne https:// (IP adresa) a funkce, jako je nahrávání a stahování souborů, budou fungovat.

[Zpět na seznam](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Modrá obrazovka po zrušení registrace z insider ve verzi Preview na zařízení blikající sestavením Insider

Jedná se o problém ovlivňující uživatele, kteří byli v buildu Insider ve verzi Preview, namítli svůj HoloLens 2 novým sestavením insider ve verzi Preview a pak zrušení jeho zaregistrovaní v programu Insider. Jedná se o **známý problém.**

To nemá vliv na:
- Uživatelé, kteří nejsou zaregistrovaní ve Windows Insider 
- Zasvěcenci:
    - Pokud bylo zařízení zaregistrované od sestavení Insider verze 18362.x
    - Pokud se v programu Insider blikal podepsaný build 19041.x a zůstal zaregistrovaný v programu Insider

Obchádky: 
- Vyhněte se problému 
    - Flash sestavení, které není zevnitř. Jedna z běžných měsíčních aktualizací.
    - Zůstaňte ve verzi Insider Preview
- Odkazování zařízení

    1. Dejte [HoloLens 2 do režimu blikajícího](hololens-recovery.md) režimu ručně tím, že úplné vypnutí, zatímco se nepřipojí. Při podržíte Tlačítko napájení klepněte na tlačítko Napájení.
    
    1. Připojení k počítači a otevřete Doprovodný průvodce pokročilým obnovením.
    
    1. Flash disk HoloLens 2 na výchozí sestavení.

[Zpět na seznam](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive automaticky nenahraje obrázky

Aplikace OneDrive pro HoloLens nepodporuje automatické nahrávání fotoaparátu pro pracovní nebo školní účty. Jedná se o **známý problém.**

Alternativní řešení:

- Pokud je pro vaši firmu přijatelné, je u uživatelských účtů Microsoft podporováno automatické nahrávání fotoaparátu. K pracovnímu nebo školnímu účet Microsoft přihlášení se můžete přihlásit i ke svému pracovnímu nebo školnímu účtu (OneDrive podporuje duální přihlašování). Ve svém účet Microsoft v rámci OneDrive můžete povolit automatické nahrávání fotoaparátů na pozadí.

- Pokud nemůžete bezpečně používat uživatelský účet účet Microsoft automatické nahrávání fotek, můžete fotky ručně nahrát do pracovního nebo školního účtu z OneDrive aplikace. Pokud to chcete udělat, ujistěte se, že jste přihlášení ke svému pracovnímu nebo školnímu účtu v OneDrive aplikace. Vyberte tlačítko **+** a zvolte **Upload**. Najděte fotky nebo videa, které chcete nahrát, tak, že přejdete na Obrázky **> fotoaparátu.** Vyberte fotky nebo videa, která chcete nahrát, a pak vyberte **tlačítko** Otevřít.

[Zpět na seznam](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens nereaguje nebo se nespustí

Pokud HoloLens nespustíte:

- Pokud se indikátory LED vedle tlačítka napájení nesvítí nebo krátce blikne jenom jedna dioda LED, možná budete muset zařízení [HoloLens.](hololens2-charging.md#charging-the-device)
- Pokud se LED diody rozsvítí, když stisknete tlačítko napájení, ale na displeji se nic neuvidí, proveďte pevné [resetování zařízení.](hololens-recovery.md#hard-reset-procedure)

Pokud se HoloLens zamrzne nebo přestane reagovat:

- Vypněte svůj HoloLens stisknutím tlačítka napájení, dokud se všech pět LED diod nevypne, nebo po dobu 15 sekund, pokud diody LED nereagují. Pokud chcete spustit HoloLens, znovu stiskněte tlačítko napájení.

Pokud tento postup nefunguje, můžete zkusit obnovit zařízení [HoloLens 2](hololens-recovery.md) nebo HoloLens [(1. generace).](hololens1-recovery.md)

[Zpět na seznam](#list)

## <a name="low-disk-space-error"></a>Chyba Nedostatek místa na disku

Budete muset některé místo úložiště volná jedním nebo více z následujících způsobů:

- Odstraňte některé nepoužívané mezery. Přejděte do **Nastavení**  >    >  **prostorů** systému, vyberte mezeru, kterou už nepotřebujete, a pak vyberte **Odebrat.**
- Odeberte některé hologramy, které jste umístili.
- Odstraňte některé obrázky a videa z aplikace Photos.
- Odinstalujte některé aplikace z HoloLens. V seznamu **Všechny aplikace** klepněte a podržte aplikaci, kterou chcete odinstalovat, a pak vyberte **Odinstalovat.**

[Zpět na seznam](#list)

## <a name="calibration-fails"></a>Selhání selhání

Většina lidí by měla fungovat, ale existují případy, kdy selhání selže.
  
Mezi možné důvody selhání patří:

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

Pokud jste postupoval podle všech pokynů a stále selhává, můžete zakázat výzvu k zadání této Nastavení. Dejte nám vědět také vyplněním zpětné vazby [na Centrum Feedback](hololens-feedback.md).

Další informace najdete v souvisejících informacích [o řešení potíží s barvou nebo jasem obrázku.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

Nastavení IPD nelze použít pro HoloLens 2, protože pozice oka jsou vypočítávány systémem. 

[Zpět na seznam](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>Nemůžu se přihlásit, protože moje HoloLens byla dříve nastavená pro někoho jiného

Zařízení můžete [přetát do **režimu blikajícího režimu**](hololens-recovery.md#clean-reflash-the-device) a pomocí doprovodné funkce rozšířeného obnovení zařízení obnovit.

[Zpět na seznam](#list)


## <a name="unity-isnt-working"></a>Unity nefunguje

- Nejnovější [verzi Unity doporučenou](/windows/mixed-reality/install-the-tools) pro vývoj pro HoloLens najdete v tématu Instalace nástrojů.
- Známé problémy s Unity HoloLens Technical Preview jsou dokumentované na fórech [HoloLens Unity.](https://forum.unity3d.com/threads/known-issues.394627/)

[Zpět na seznam](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows Portál zařízení nefunguje správně

- Funkce Live Preview v Mixed Reality může vykazovat latenci několik sekund.

- Na stránce Virtuální vstup nejsou ovládací prvky Gesture a Scroll v části Virtuální gesta funkční. Jejich použití nebude mít žádný vliv. Virtuální klávesnice na stránce virtuálního vstupu funguje správně.

- Po povolení režimu pro vývojáře Nastavení může trvat několik sekund, než se přepínač zapne, Portál zařízení povoleno.

[Zpět na seznam](#list)

## <a name="the-hololens-emulator-isnt-working"></a>Tento HoloLens Emulator nefunguje

Informace o emulátoru HoloLens najdete v naší dokumentaci pro vývojáře.  Přečtěte si další [informace o řešení potíží HoloLens emulátoru.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)


- Ne všechny aplikace v Microsoft Store jsou kompatibilní s emulátorem. Například Young Conker a Fragmenty se v emulátoru nehrají.
- V počítači nemůžete použít webovou kameru Emulator.
- Funkce Live Preview v Windows Portál zařízení nefunguje s emulátorem. Stále můžete zachytit Mixed Reality videa a obrázky.

[Zpět na seznam](#list)

## <a name="voice-commands-arent-working"></a>Nefungují hlasové příkazy

Pokud Cortana nereaguje na vaše hlasové příkazy, ujistěte se, Cortana je zapnutá. V seznamu Všechny aplikace vyberte Poznámkový blok **Cortana** nabídky a  >    >    >  **Nastavení** proveďte změny. Další informace o tom, co můžete říct, najdete v tématu Použití [hlasu s HoloLens](hololens-cortana.md).

v HoloLens (1. generace) se integrované rozpoznávání řeči nedá konfigurovat. Je vždycky zapnutý. v HoloLens 2 se můžete rozhodnout, jestli při instalaci zařízení zapnout rozpoznávání řeči i Cortana.

pokud váš HoloLens 2 nereaguje na váš hlas, ujistěte se, že je zapnuté rozpoznávání řeči. přejít na **začátek**  >  **Nastavení**  >  **ochrany osobních údajů** na  >  **řeč** a zapnout **rozpoznávání řeči**

[Zpět na seznam](#list)

## <a name="hand-input-isnt-working"></a>Ruční vstup nefunguje.

aby se zajistilo, že HoloLens uvidí vaše ruce, je potřeba je zachovat v rámečku gesta.  Domovská stránka smíšené reality poskytuje zpětnou vazbu, která vám umožní vědět, kdy jsou vaše rukou sledovány.  Zpětná vazba je odlišná na různých verzích HoloLens:
- na HoloLens (1. generace) se ukazatel pohledu změní z tečky na prstenec.
- na HoloLens 2 se zobrazí ukazatel myši, když se vaše ruka blíží k slat, a když se objeví až slat, zobrazí se po ruce.

Mnoho moderních aplikací se řídí vstupními vzory, které se podobají domácím realitám.  přečtěte si další informace o použití ručního vstupu na [HoloLens (1. generace)](hololens1-basic-usage.md#use-hololens-with-your-hands) a [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Pokud máte ochranné rukavice, pamatujte, že některé typy rukavic nefungují s ručním sledováním.  Běžným příkladem jsou černé Pryžové rukavice, které mají za následek absorpci infračerveného světla a nejsou vyzvednuty hloubkovou kamerou.  Pokud vaše práce zahrnuje Pryžové rukavice, doporučujeme vyzkoušet světlejší barvu, jako je například modrá nebo šedá.  Dalším příkladem jsou velké zavazadlové rukavice, které mají za následek překrytí tvaru ruky. Pro dosažení nejlepších výsledků doporučujeme používat rukavice, které jsou jako přizpůsobení formulářů.

pokud vaše clona obsahuje otisky prstů nebo rozmazává, použijte čisticí látku microfiber, která byla dodávána se HoloLens k vyčištění hypervisoru v mírném případě.

[Zpět na seznam](#list)

## <a name="cant-connect-to-wi-fi"></a>Nejde se připojit k Wi-Fi

tady je několik věcí, které můžete vyzkoušet, pokud nemůžete připojit HoloLens k síti Wi-Fi:

- Ujistěte se, že je zapnutá Wi-Fi. pokud chcete kontrolu ověřit, použijte gesto Start a pak vyberte **Nastavení**  >  **síť &amp; Internet**  >  **Wi-Fi**. Pokud je Wi-Fi zapnutá, zkuste ji vypnout a znovu zapnout.
- Posuňte se blíž ke směrovači nebo přístupovému bodu.
- Restartujte směrovač Wi-Fi a pak [znovu spusťte HoloLens](hololens-recovery.md). Zkuste se znovu připojit.
- Pokud žádná z těchto věcí nefunguje, zkontrolujte, zda směrovač používá nejnovější firmware. Tyto informace najdete na webu výrobce.

[Zpět na seznam](#list)

## <a name="bluetooth-devices-arent-pairing"></a>nepárování zařízení Bluetooth

pokud máte problémy [spárované Bluetooth zařízení](hololens-connect-devices.md), zkuste následující:

- přejít na **Nastavení**  >  **zařízení** a ujistěte se, že je zapnutá Bluetooth. Pokud je, vypněte ho a znovu ho zapněte.
- ujistěte se, že se zařízení Bluetooth plně účtuje nebo má vybité baterie.
- Pokud se stále nemůžete připojit, [restartujte HoloLens](hololens-recovery.md).

[Zpět na seznam](#list)

## <a name="usb-c-microphone-isnt-working"></a>Mikrofon USB-C nefunguje
Uvědomte si, že někteří mikrotelefony USB-C nesprávně hlásí jako mikrofon *i* mluvčí. Jedná se o problém s mikrofonem a nikoli s HoloLens. při zapojení jednoho z těchto telefonů do HoloLens může dojít ke ztrátě zvuku. Naštěstí je jednoduchá oprava.  

v **Nastavení**  ->  **systémový**  ->  **zvuk** explicitně nastavte integrované reproduktory **(zvukový ovladač analogických funkcí)** jako **výchozí zařízení**. HoloLens by si toto nastavení měli pamatovat i v případě, že mikrofon odeberete a znovu připojíte později.

![Řešení potíží s mikrofony USB-C](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>zařízení uvedená jako dostupná v Nastavení nefungují

HoloLens (1. generace) nepodporuje profily Bluetooth zvuku. Bluetooth zvuková zařízení, jako jsou například mluvčí a sluchátka, se můžou zobrazovat jako dostupná v nastaveních HoloLens, ale nejsou podporovaná.

HoloLens 2 podporuje zvukový profil Bluetooth A2DP pro přehrávání stereo. v Bluetooth je k dispozici bezplatný profil, který umožňuje zachytávání mikrofonu od Bluetooth periferního zařízení není v HoloLens 2 podporováno.

pokud máte potíže s používáním Bluetooth zařízení, ujistěte se, že se jedná o podporované zařízení. Mezi podporovaná zařízení patří následující:

- jazykové verze pro angličtinu – Bluetooth klávesnice (můžete je použít kdekoli, kde používáte holografickou klávesnici).
- Bluetooth myši.
- [HoloLens click](hololens1-clicker.md).

další Bluetooth zařízení HID a GATT můžete párovat spolu s HoloLens. je ale možné, že budete muset nainstalovat odpovídající doprovodné aplikace z Microsoft Store ke skutečnému používání těchto zařízení.

[Zpět na seznam](#list)
