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
ms.openlocfilehash: c634b90b03468073887397b59f072258ad7a3ccc
ms.sourcegitcommit: 5cb3230e02e703584e50358cb0f0b5f33a51b169
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/13/2021
ms.locfileid: "121858561"
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

- Zavřete klávesnici a znovu ji otevřete klepnutím na textové pole.
- Nesprávně zadejte heslo. Když se při příštím spuštění klávesnice znovu spustí, bude fungovat podle očekávání.
- Webové ověřování, zavřete klávesnici a vyberte **přihlásit z jiného zařízení**.
- Pokud zadáváte jenom čísla, může uživatel stisknout a držet určité klávesy, aby otevřeli rozbalenou nabídku.
- Pomocí klávesnice USB.

To nemá vliv na:

- Uživatelé, kteří se rozhodnou použít osobní účet.

[Zpět na seznam](#list)

## <a name="downloading-locked-files-doesnt-error"></a>Stahování uzamčených souborů nechybí

> [!NOTE]
> jedná se o **známý problém** , který byl vyřešen ve [Windows holografické verzi 21H1-červenec 2021 Update](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update).

v předchozích sestaveních Windows holografické při pokusu o stažení uzamčeného souboru by výsledkem byla chybová stránka HTTP. v Windows holografické 21H1 aktualizace verze, která se pokouší stáhnout uzamčený soubor, by nedocházelo k žádnému zobrazení, soubor se nestáhne a nebude k dispozici žádná chyba.

[Zpět na seznam](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Časový limit nahrávání nebo stahování souboru portálu zařízení
> [!NOTE]
> jedná se o **známý problém** , který byl vyřešen ve [Windows holografické verzi 21H1-červenec 2021 Update](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update). Pokud jste v rámci alternativního řešení dříve zakázali připojení SSL, důrazně doporučujeme ho znovu povolit.

Někteří zákazníci zjistili, že při pokusu o nahrání nebo stažení souborů se může zdát, že se operace zablokuje a vyprší časový limit nebo není možné ji ještě dokončit. to je oddělené od[známého problému "file locked"](#downloading-locked-files-doesnt-error) – to má vliv na Windows holografické verze 2004, 20H2 a 21H1 buildů v rámci trhu. Problém byl kořenem způsoben chybou v manipulaci s některými požadavky na portálu zařízení a při použití protokolu HTTPS, který je výchozím nastavením, se obvykle vychází.

### <a name="workaround"></a>Alternativní řešení

Toto alternativní řešení, které platí stejně jako Wi-Fi a UsbNcm, je zakázat možnost "požadované" v části "připojení SSL". Provedete to tak, že přejdete na portál zařízení, **systém** a vyberete stránku **Předvolby** . V části **zabezpečení zařízení** vyhledejte **připojení SSL** a zrušte kontrolu, aby se vypnulo **povinné**.

Uživatel by pak měl přejít na http://, ne https:// (IP adresa) a funkce, jako je nahrávání a stahování souborů, budou fungovat.

[Zpět na seznam](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Modrá obrazovka po zrušení registrace z insider ve verzi Preview na zařízení blikající sestavením Insider

Jedná se o problém ovlivňující uživatele, kteří byli v buildu Insider ve verzi Preview, odmítnul svou verzi HoloLens 2 novým sestavením Insider Preview a pak zrušit jeho zrušení v programu Insider. Jedná se o **známý problém.**

To nemá vliv na:
- Uživatelé, kteří nejsou zaregistrovaní ve Windows Insider 
- Zasvěcenci:
    - Pokud bylo zařízení zaregistrované od sestavení Insider verze 18362.x
    - Pokud se blikajícím souborem Insider podepsal build 19041.x a zůstane zaregistrovaný v programu Insider

Obchádky: 
- Vyhněte se problému 
    - Flash sestavení, které není uvnitř. Jedna z běžných měsíčních aktualizací.
    - Zůstaňte ve verzi Insider Preview
- Odkazování zařízení

    1. Dejte [HoloLens 2 do režimu blikajícího](hololens-recovery.md) režimu ručním vypnutím, zatímco se nepřipojí. Při podržíte Tlačítko napájení klepněte na tlačítko Napájení.
    
    1. Připojení k počítači a otevřete Doprovodný průvodce pokročilým obnovením.
    
    1. Flash HoloLens 2 do výchozího sestavení.

[Zpět na seznam](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive automaticky nenahraje obrázky

Aplikace OneDrive pro HoloLens nepodporuje automatické nahrávání fotoaparátů pro pracovní nebo školní účty. Jedná se o **známý problém.**

Alternativní řešení:

- Pokud je pro vaši firmu přijatelné, je u uživatelských účtů Microsoft podporováno automatické nahrávání fotoaparátu. K pracovnímu nebo školnímu účtu se účet Microsoft přihlásit i ke svému pracovnímu nebo školnímu účtu (OneDrive podporuje duální přihlašování). Z vašeho účet Microsoft v rámci OneDrive můžete povolit automatické nahrávání fotoaparátů na pozadí.

- Pokud nemůžete bezpečně používat uživatelský účet účet Microsoft automatické nahrávání fotek, můžete fotky ručně nahrát do pracovního nebo školního účtu z OneDrive aplikace. Pokud to chcete udělat, ujistěte se, že jste v aplikaci OneDrive účet. Vyberte tlačítko **+** a zvolte **Upload**. Najděte fotky nebo videa, které chcete nahrát, tak, že přejdete na Obrázky **> fotoaparátu.** Vyberte fotky nebo videa, která chcete nahrát, a pak vyberte **tlačítko** Otevřít.

[Zpět na seznam](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens nereaguje nebo se nespustí

Pokud HoloLens nespustíte:

- Pokud se indikátory LED vedle tlačítka napájení nesvítí nebo krátce blikne jenom jedna dioda LED, možná budete muset zařízení [HoloLens.](hololens2-charging.md#charging-the-device)
- Pokud se LED diody rozsvítí, když stisknete tlačítko napájení, ale na displeji neuvidíte nic, proveďte pevné [resetování zařízení.](hololens-recovery.md#hard-reset-procedure)

Pokud se HoloLens zamrzne nebo přestane reagovat:

- Vypněte svůj HoloLens stisknutím tlačítka napájení, dokud se všechny pět led diod nevypnou, nebo po dobu 15 sekund, pokud diody LED nereagují. Pokud chcete spustit HoloLens, znovu stiskněte tlačítko napájení.

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

- Funkce Live Preview v zachytávání Mixed Reality může vykazovat latenci několik sekund.

- Na stránce Virtuální vstup nejsou ovládací prvky Gesture a Scroll v části Virtuální gesta funkční. Jejich použití nebude mít žádný vliv. Virtuální klávesnice na stránce virtuálního vstupu funguje správně.

- Po povolení režimu pro vývojáře Nastavení může trvat několik sekund, než se přepínač zapne, Portál zařízení povoleno.

[Zpět na seznam](#list)

## <a name="the-hololens-emulator-isnt-working"></a>HoloLens Emulator nefunguje

Informace o emulátoru HoloLens najdete v naší dokumentaci pro vývojáře.  Přečtěte si další [informace o řešení potíží HoloLens emulátoru.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)


- Ne všechny aplikace v Microsoft Store jsou kompatibilní s emulátorem. Například Young Conker a Fragmenty se v emulátoru nehrají.
- V počítači nemůžete použít webovou kameru Emulator.
- Funkce Live Preview v Windows Portál zařízení nefunguje s emulátorem. Stále můžete zachytit Mixed Reality videa a obrázky.

[Zpět na seznam](#list)

## <a name="voice-commands-arent-working"></a>Nefungují hlasové příkazy

Pokud Cortana nereaguje na vaše hlasové příkazy, ujistěte se, Cortana je zapnutá. V seznamu Všechny aplikace vyberte **Poznámkový** blok Cortana nabídky a  >    >    >  **Nastavení** změny. Další informace o tom, co můžete říct, najdete v tématu [Použití hlasu s HoloLens](hololens-cortana.md).

V HoloLens (1. generace) není integrované rozpoznávání řeči konfigurovatelné. Vždy je zapnutý. Na HoloLens 2 můžete zvolit, jestli se má při nastavování zařízení zapnout rozpoznávání Cortana i rozpoznávání řeči.

Pokud váš HoloLens 2 nereaguje na váš hlas, ujistěte se, že je zapnuté rozpoznávání řeči. Přejděte na **Start Nastavení** Privacy Speech a  >    >    >   zapněte **Rozpoznávání řeči.**

[Zpět na seznam](#list)

## <a name="hand-input-isnt-working"></a>Ruční vstup nefunguje

Abyste měli HoloLens vidět ruce, musíte je ponechat v snímku gest.  Domovská Mixed Reality poskytuje zpětnou vazbu, která vám dá vědět, kdy jsou vaše ruce sledované.  Zpětná vazba se liší v různých verzích HoloLens:
- Při HoloLens (1. generace) se kurzor pohledu změní z tečky na kruh.
- Na HoloLens 2 se zobrazí kurzor prstu, když se vaše ruce nachází blízko slate, a když jsou slates dále, zobrazí se ruční paprsk.

Řada imerzivních aplikací dodržuje vzory vstupu, které se podobají Mixed Reality Domovské obrazovce.  Další informace o použití ručního [vstupu v HoloLens (1. generace)](hololens1-basic-usage.md#use-hololens-with-your-hands) a [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Pokud máte problémy s nosem, mějte na vědomí, že některé typy choumů nefungují se sledováním rukou.  Běžným příkladem je černá guma, která obvykle absorbuje infračervené světlo a nenabírá je hloubková kamera.  Pokud vaše práce zahrnuje gumové gumy, doporučujeme, abyste si zkusili světlejší barvu, například modrou nebo šedou.  Dalším příkladem je velká nesrozumilá aplikace, která má tendenci zakrytí tvaru vaší ruky. Pro nejlepší výsledky doporučujeme použít co nejvíce tvarování.

Pokud má váš vizuátor otisky prstů nebo šmouhy, použijte čisticí filtr z mikrovlákna, který se dodá HoloLens vyčistit zorný prostor.

[Zpět na seznam](#list)

## <a name="cant-connect-to-wi-fi"></a>Nelze se připojit k Wi-Fi

Tady je několik věcí, které můžete vyzkoušet, pokud nemůžete připojit HoloLens k Wi-Fi síti:

- Ujistěte se, Wi-Fi je zapnuté. Kontrolu můžete provést pomocí gesta Start a pak **Nastavení**  >  **Internet &amp;**  >  **Wi-Fi sítě Wi-Fi.** Pokud Wi-Fi, zkuste ho vypnout a znovu zas.
- Přesuňte se blíž ke směrovači nebo přístupovému bodu.
- Restartujte svůj Wi-Fi a [pak restartujte HoloLens](hololens-recovery.md). Zkuste se připojit znovu.
- Pokud nic z toho nefunguje, zkontrolujte, že váš směrovač používá nejnovější firmware. Tyto informace najdete na webu výrobce.

[Zpět na seznam](#list)

## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth zařízení se ne párují

Pokud máte problémy s [párem zařízení Bluetooth,](hololens-connect-devices.md)zkuste následující postup:

- Přejděte na **Nastavení** Zařízení a  >  ujistěte se, Bluetooth je zapnutá. Pokud je, vypněte ho a znovu ho zapněte.
- Ujistěte se, že Bluetooth zařízení je plně nabité nebo obsahuje čerstvé baterie.
- Pokud se stále nemůžete připojit, [restartujte HoloLens](hololens-recovery.md).

[Zpět na seznam](#list)

## <a name="usb-c-microphone-isnt-working"></a>Mikrofon USB-C nefunguje
Uvědomte si, že některé mikrofony USB-C se nesprávně hlásí jako *mikrofon* i jako mluvčí. Jedná se o problém s mikrofonem, a ne s HoloLens. Když jeden z těchto mikrofonů zapojíte do HoloLens, může dojít ke ztrátě zvuku. Naštěstí existuje jednoduchá oprava.  

V **Nastavení** System Sound explicitně nastavte vestavěné mluvčí (zvukový ovladač  ->    ->   **analogové funkce)** jako **výchozí zařízení.** HoloLens si toto nastavení zapamatovat, i když se mikrofon později odebere a znovu připojí.

![Řešení potíží s mikrofony USB-C](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>Zařízení uvedená jako dostupná Nastavení nefungují

HoloLens (1. generace) nepodporuje Bluetooth zvukové profily. Bluetooth zvuková zařízení, jako jsou mluvčí a náhlavní soupravy, se dají zobrazit jako dostupná v HoloLens, ale nejsou podporovaná.

HoloLens 2 podporuje Bluetooth zvukového profilu A2DP pro stereo přehrávání. Profil Bluetooth Hands Free, který umožňuje zachytávání mikrofonu z Bluetooth periferního zařízení, se na HoloLens 2 nepodporuje.

Pokud máte potíže s používáním Bluetooth, ujistěte se, že se jedná o podporované zařízení. Mezi podporovaná zařízení patří:

- QWERTY v angličtině Bluetooth klávesnice (můžete je použít kdekoli, kde používáte holografičnou klávesnici).
- Bluetooth mice.
- Na [HoloLens klikněte na .](hololens1-clicker.md)

Můžete spárovat jiná zařízení Bluetooth HID a PAIR s vašimi HoloLens. Je však možné, že budete muset nainstalovat odpovídající doprovodné aplikace z Microsoft Store, aby bylo možné zařízení skutečně používat.

[Zpět na seznam](#list)
