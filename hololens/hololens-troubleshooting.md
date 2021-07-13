---
title: HoloLens Řešení potíží se zařízeními
description: Získejte aktuální informace o nejběžnějších řešeních pro HoloLens a řešení potíží.
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
ms.openlocfilehash: b07514e73e43d267aa856c0fb9a256448e565000
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635445"
---
# <a name="device-troubleshooting"></a>Řešení potíží se zařízeními

Tento článek popisuje, jak vyřešit několik běžných HoloLens problémů.

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
- [Windows Portál zařízení nefunguje správně](#windows-device-portal-isnt-working-correctly)
- [HoloLens Emulator nefunguje](#the-hololens-emulator-isnt-working)

**Vstup**
- [Nefungují hlasové příkazy](#voice-commands-arent-working)
- [Ruční vstup nefunguje](#hand-input-isnt-working)

**Připojení**
- [Nelze se připojit k Wi-Fi](#cant-connect-to-wi-fi)

**Externí zařízení** 
- [Bluetooth zařízení se ne párují](#bluetooth-devices-arent-pairing)
- [Mikrofon USB-C nefunguje](#usb-c-microphone-isnt-working)
- [Zařízení uvedená jako dostupná v Nastavení nefungují](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>Video remote assist se zablokuje po 20 minutách

> [!NOTE]
> K dispozici je novější verze vzdáleného nástroje Remote Assist, která obsahuje opravu tohoto problému. Aktualizujte [službu Remote Assist](holographic-store-apps.md#update-apps) na nejnovější verzi, abyste se tomuto problému vyhnuli.

> [!NOTE]
> Vzhledem k závažnosti tohoto známého problému jsme dočasně pozastavil dostupnost Windows Holographic verze 21H1. Sestavení 21H1 je teď opět k dispozici, takže zařízení je možné znovu aktualizovat na nejnovější build 21H1.

V nejnovější verzi [Windows Holographic verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1)zaznamenali někteří uživatelé Vzdálené pomoci zamrznutí videa během 20 minut. Jedná se o **známý problém.**

### <a name="workarounds"></a>Alternativní řešení

Pokud nemůžete aplikaci Remote Assist aktualizovat na novější sestavení, vyzkoušejte následující postup.

#### <a name="restart-in-between-calls"></a>Restartování mezi voláními

Pokud vaše volání přesájí 20 minut a dochází k tomuto problému, zkuste zařízení restartovat. Restartováním zařízení mezi voláními vzdálené pomoci obnovíte zařízení a vrátíte ho do dobrého stavu.

Pokud chcete rychle restartovat zařízení na Windows Holographic, otevřete nabídku Start verze [21H1,](hololens-release-notes.md#windows-holographic-version-21h1) vyberte ikonu uživatele a pak vyberte **Restartovat.**

[Zpět na seznam](#list)

## <a name="auto-login-asks-for-log-in"></a>Automatické přihlášení žádá o přihlášení

Zařízení HoloLens 2 je možné nakonfigurovat tak, aby se automaticky přihlašuje přes **možnosti** přihlášení k účtům Nastavení -> a v části Povinné nastavovat hodnotu  ->    ->   **na Nikdy.**  Někteří uživatelé se při aktualizaci zařízení s podstatně velkou aktualizací, jako je třeba aktualizace funkcí, mohou znova přihlásit k zařízení. Jedná se o **známý problém.**

Příklad, kdy k tomu může dojít:

- Aktualizace zařízení z Windows Holographic verze 2004 (build 19041.xxxx) na Windows Holographic verze 21H1 (build 20346.xxxx)
- Aktualizace zařízení tak, aby se ve stejném hlavním buildu, např. Windows Holographic, verze 2004, Windows Holographic, verze 20H2
- Aktualizace zařízení z image továrny na nejnovější image

K tomu by nemělo dojít během těchto období:

- Zařízení, která mají měsíční servisní aktualizaci

Alternativní metody:

- Metody přihlášení, jako jsou PIN, heslo, Iris, webové ověřování nebo klíče FIDO2.
- Pokud pin kód zařízení nelze zapamatovat a jiné metody ověřování nejsou k dispozici, může uživatel použít režim [ručního lomítka](hololens-recovery.md#manual-procedure).

[Zpět na seznam](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge spuštění se nepovede

> [!NOTE]
> Tento problém byl původně vytvořen s Microsoft Edge verzí. Tento problém se může vyřešit v [nové Microsoft Edge](hololens-new-edge.md). Pokud ne, zpětnou vazbu nahlaste.

Několik zákazníků nahlásilo problém, kdy Microsoft Edge spuštění. U těchto zákazníků problém přetrvává i po restartování a nevyřeší se Windows aktualizacemi aplikací. Pokud k tomuto problému dochází a potvrdili jste, že Windows je [aktuální,](hololens-updates.md#manually-check-for-updates)zakažte chybu z aplikace [Centrum Feedback](hololens-feedback.md) s následující kategorií a podkate kategorií: Instalace a aktualizace > Stahování, instalace a konfigurace Windows Update.

Neexistují žádná známá alternativní řešení, protože zatím jsme nemohli hlavní příčinu problému. S vyšetřováním vám pomůže Centrum Feedback chyb prostřednictvím webu společnosti. Jedná se o **známý problém.**

[Zpět na seznam](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>Klávesnice se přepne na speciální znaky

Při ooBE dochází k problému, kdy se po zvolení pracovního nebo školního účtu a zadání hesla uživatel pokouší přepnout na speciální znaky na klávesnici klepnutím na tlačítko &123, se nezmění na speciální znaky. Jedná se o **známý problém.**

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

> [!NOTE]
> Jedná se o **známý problém,** který je opraven Windows Insider verze 20348.1403.

V předchozích sestaveních Windows Holographic by výsledkem pokusu o stažení uzamčeného souboru byla chybová stránka HTTP. Při pokusu Windows Holographic verze 21H1 se při pokusu o stažení uzamčeného souboru nic nestane – soubor se nestáhne a nezobrazí se žádná chyba.

[Zpět na seznam](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Portál zařízení nahrání nebo stažení souboru
> [!NOTE]
> Jedná se o **známý problém,** který je opraven Windows Insider verze 20348.1403. Pokud jste v rámci tohoto alternativního řešení dříve zakázali připojení SSL, důrazně doporučujeme ho znovu povolit.


Někteří zákazníci zjistili, že při pokusu o nahrání nebo stažení souborů se operace může zdát, že přestane reagovat a pak dojde k časovému limitu nebo se nikdy nedokoncuje. Tento problém je[](#downloading-locked-files-doesnt-error) oddělený od známého problému uzamčeného souboru – to má vliv na sestavení na trhu Windows Holographic, verze 2004, 20H2 a 21H1. Problém byl způsobený chybou při Portál zařízení zpracování určitých požadavků a při použití protokolu https, což je výchozí nastavení, dochází nejčastěji k tomuto problému. 

### <a name="workaround"></a>Alternativní řešení

Toto alternativní řešení, které platí stejně pro Wi-Fi a UsbNcm, je zakázat možnost "povinné" v části Připojení SSL. Pokud to chcete udělat, přejděte Portál zařízení, **Systém** a vyberte **stránku** Předvolby. V části **Zabezpečení zařízení** vyhledejte Připojení **SSL a** zrušte zaškrtnutí, pokud chcete zakázat **povinné.**

Uživatel by pak měl přejít na http://, ne na https://(IP adresa) a funkce, jako je nahrání souboru, a stahování bude fungovat.

[Zpět na seznam](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Modrá obrazovka po odregistraci z programu Insider Preview na zařízení, které se postavilo pomocí buildu Insider

to má vliv na to, co se týká uživatelů, kteří byli ve buildu insider preview, ve HoloLens 2 se znovu dokončí novému buildu insider preview a pak se zruší jeho registrace v programu insider. Jedná se o **známý problém**.

To nemá vliv na:
- uživatelé, kteří nejsou zaregistrovaní v programu Windows Insider 
- Insider
    - Pokud bylo zařízení zaregistrováno, protože buildy Insider byly verze 18362. x
    - Pokud se v programu Insider nastavila aplikace Insider podepsaná 19041. x a zůstane zaregistrovaná v programu Insider

Práce v tomto okolí: 
- Vyhnout se problému 
    - Zabliká Build bez programu Insider. Jedna z pravidelných měsíčních aktualizací.
    - Zůstat ve verzi Insider Preview
- Rozsvítit zařízení

    1. [HoloLens 2 vložte do režimu blesku](hololens-recovery.md) ručně, a to tak, že se nepřipojíte. Pak klepněte na tlačítko napájení.
    
    1. Připojení k počítači a otevřete průvodce pokročilým obnovením.
    
    1. zabliká HoloLens 2 do výchozího buildu.

[Zpět na seznam](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive neodesílá automaticky obrázky

aplikace OneDrive pro HoloLens nepodporuje automatické nahrávání fotoaparátů pro pracovní nebo školní účty. Jedná se o **známý problém**.

Alternativní řešení:

- Pokud je pro vaši firmu životaschopná, je automatické nahrávání kamery podporované u zákaznických účtů Microsoft. k vašemu účet Microsoft se můžete přihlásit navíc k pracovnímu nebo školnímu účtu (aplikace OneDrive podporuje duální přihlášení). z profilu účet Microsoft v rámci OneDrive můžete povolit automatické nahrávání snímků na pozadí.

- pokud nemůžete bezpečně použít účet Microsoft příjemce k automatickému nahrávání vašich fotografií, můžete fotky z OneDrive aplikace nahrát ručně do svého pracovního nebo školního účtu. abyste to mohli udělat, ujistěte se, že jste se přihlásili ke svému pracovnímu nebo školnímu účtu v aplikaci OneDrive. Vyberte **+** tlačítko a zvolte **Upload**. Najděte fotky nebo videa, která chcete nahrát, přechodem na **obrázky >ou kamerou**. Vyberte fotky nebo videa, která chcete nahrát, a pak vyberte tlačítko **otevřít** .

[Zpět na seznam](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens nereaguje nebo se nespustí

pokud se HoloLens nespustí:

- Pokud se indikátory LED vedle tlačítka napájení nesvítí nebo se jenom jeden z nich může krátce rozsvítit, možná budete muset [účtovat HoloLens.](hololens2-charging.md#charging-the-device)
- Pokud při stisknutí tlačítka napájení zhasnou diody LED, ale nevidíte cokoli na zobrazených displejech, [proveďte obnovení zařízení](hololens-recovery.md#hard-reset-procedure).

pokud bude váš HoloLens zmrazený nebo nereaguje:

- vypněte HoloLens tím, že stisknete tlačítko napájení, dokud se všechny pět diod led nevypne, nebo 15 sekund, pokud indikátory led nereagují. HoloLens spustíte tak, že znovu stisknete tlačítko napájení.

pokud tyto kroky nefungují, můžete zkusit [obnovit zařízení HoloLens 2](hololens-recovery.md) nebo [HoloLens (1. generace).](hololens1-recovery.md)

[Zpět na seznam](#list)

## <a name="low-disk-space-error"></a>Chyba "nedostatek místa na disku"

K uvolnění úložného prostoru budete potřebovat jednu nebo více následujících akcí:

- Odstraňte některé nepoužité mezery. v **Nastavení**  >  **systémových**  >  **prostorech** vyberte místo, které už nepotřebujete, a pak vyberte **odebrat**.
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

pokud jste postupovali podle všech pokynů a kalibrace stále selhává, můžete zakázat výzvu k kalibraci v Nastavení. Dejte nám taky vědět, že vám zašleme zpětnou vazbu v [centru Feedback](hololens-feedback.md).

Podívejte se také na související informace o [barvě obrázku nebo odstraňování potíží s jasem.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

nastavení IPD nelze použít pro HoloLens 2, protože pozice očí jsou vypočítány systémem. 

[Zpět na seznam](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>nejde se přihlásit, protože můj HoloLens byl dřív nastavený pro někoho jiného.

Zařízení můžete [Přepnout do **režimu blikání** a obnovit zařízení pomocí pokročilého Průvodce obnovením](hololens-recovery.md#clean-reflash-the-device) .

[Zpět na seznam](#list)


## <a name="unity-isnt-working"></a>Unity nefunguje

- přečtěte si téma [instalace nástrojů](/windows/mixed-reality/install-the-tools) pro nejaktuálnější verzi Unity doporučenou pro HoloLens vývoj.
- známé problémy se službou unity HoloLens Technical Preview jsou popsány ve [HoloLens fórech unity](https://forum.unity3d.com/threads/known-issues.394627/).

[Zpět na seznam](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows Portál zařízení nepracuje správně.

- Funkce Live Preview v rámci hybridního zachycení realit může při latenci vykazovat několik sekund.

- Na stránce virtuálního vstupu nejsou funkční gesta a posuvníky v části virtuální gesta. Jejich použití nebude mít žádný vliv. Virtuální klávesnice na stránce virtuálního vstupu funguje správně.

- po povolení režimu vývojářů v Nastavení může trvat několik sekund, než se zapne přepínač, aby se aktivoval portál zařízení.

[Zpět na seznam](#list)

## <a name="the-hololens-emulator-isnt-working"></a>Emulator HoloLens nefunguje

informace o emulátoru HoloLens najdete v naší dokumentaci pro vývojáře.  přečtěte si další informace o [řešení potíží s emulátorem HoloLens](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting).


- ne všechny aplikace v Microsoft Store jsou kompatibilní s emulátorem. Například mladí conker a fragmenty nefungují na emulátoru.
- V Emulator nemůžete použít webovou kameru počítače.
- funkce Live Preview portálu zařízení Windows nefunguje s emulátorem. Pořád můžete zachytit hybridní videa a obrázky.

[Zpět na seznam](#list)

## <a name="voice-commands-arent-working"></a>Hlasové příkazy nefungují.

pokud Cortana nereaguje na hlasové příkazy, ujistěte se, že je Cortana zapnutý. v seznamu všechny aplikace vyberte **Cortana**  >    >  **poznámkový blok** nabídky  >  **Nastavení** a proveďte změny. Další informace o tom, co můžete vyslovit, najdete v tématu [použití hlasu s HoloLens](hololens-cortana.md).

V HoloLens (1. generace) není integrované rozpoznávání řeči konfigurovatelné. Vždy je zapnutý. Na HoloLens 2 můžete zvolit, jestli se má při nastavování zařízení zapnout rozpoznávání Cortana i rozpoznávání řeči.

Pokud váš HoloLens 2 nereaguje na váš hlas, ujistěte se, že je zapnuté rozpoznávání řeči. Přejděte na **Start Nastavení** Privacy Speech a  >    >    >   zapněte **Rozpoznávání řeči.**

[Zpět na seznam](#list)

## <a name="hand-input-isnt-working"></a>Ruční vstup nefunguje

Aby bylo HoloLens vidět vaše ruce, musíte je ponechat v snímku gest.  Domovská Mixed Reality poskytuje zpětnou vazbu, která vám dá vědět, kdy jsou vaše ruce sledované.  Zpětná vazba se liší v různých verzích HoloLens:
- V HoloLens (1. generace) se kurzor pohledu změní z tečky na kruh.
- Na HoloLens 2 se zobrazí kurzor prstu, když se vaše ruce nachází blízko slate, a když jsou břidíčky dále, zobrazí se ruční paprsk.

Řada imerzivních aplikací dodržuje vzory vstupu, které se podobají Mixed Reality Domovské obrazovce.  Další informace o použití ručního [vstupu v HoloLens (1. generace)](hololens1-basic-usage.md#use-hololens-with-your-hands) a [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Pokud máte problémy s chemií, mějte na vědomí, že některé typy choumů nefungují se sledováním rukou.  Běžným příkladem je černá guma, která obvykle absorbuje infračervené světlo a nenabírá je hloubková kamera.  Pokud vaše práce zahrnuje gumové gumy, doporučujeme, abyste si zkusili světlejší barvu, například modrou nebo šedou.  Dalším příkladem je velká nesrozumilá aplikace, která má tendenci zakrytí tvaru vaší ruky. Pro nejlepší výsledky doporučujeme použít co nejvíce tvarování.

Pokud má váš vizor otisky prstů nebo smyšlené údaje, vyčistěte ji pomocí čisticího mikrovlákna, který byl HoloLens s filtrem.

[Zpět na seznam](#list)

## <a name="cant-connect-to-wi-fi"></a>Nelze se připojit k Wi-Fi

Tady je několik věcí, které můžete vyzkoušet, pokud nemůžete připojit HoloLens k Wi-Fi síti:

- Ujistěte se, Wi-Fi je zapnuté. Kontrolu můžete provést pomocí gesta Start a pak **Nastavení**  >  **Network &amp; Internet**  >  **Wi-Fi**. Pokud Wi-Fi, zkuste ho vypnout a znovu zas.
- Přesuňte se blíže ke směrovači nebo přístupovému bodu.
- Restartujte směrovač Wi-Fi a pak [restartujte HoloLens](hololens-recovery.md). Zkuste se připojit znovu.
- Pokud nic z toho nefunguje, zkontrolujte, že váš směrovač používá nejnovější firmware. Tyto informace najdete na webu výrobce.

[Zpět na seznam](#list)

## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth zařízení se ne pairují

Pokud máte problémy s [párem zařízení Bluetooth,](hololens-connect-devices.md)zkuste následující postup:

- Přejděte na **Nastavení** Zařízení a  >  ujistěte se, Bluetooth je zapnutá. Pokud je, vypněte ho a znovu zapněte.
- Ujistěte se, že Bluetooth zařízení je plně nabité nebo obsahuje čerstvé baterie.
- Pokud se stále nemůžete připojit, [restartujte HoloLens](hololens-recovery.md).

[Zpět na seznam](#list)

## <a name="usb-c-microphone-isnt-working"></a>Mikrofon USB-C nefunguje
Uvědomte si, že některé mikrofony USB-C se nesprávně hlásí jako *mikrofon* i jako mluvčí. Jedná se o problém s mikrofonem, a ne s HoloLens. Když jeden z těchto mikrofonů zapojíte do HoloLens, může dojít ke ztrátě zvuku. Naštěstí existuje jednoduchá oprava.  

V **Nastavení** System Sound (Zvuk systému) explicitně nastavte integrované mluvčí (zvukový ovladač  ->    ->   **analogové funkce)** jako **výchozí zařízení.** HoloLens si toto nastavení zapamatovat, i když se mikrofon později odebere a znovu připojí.

![Řešení potíží s mikrofony USB-C](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>Zařízení uvedená jako dostupná v Nastavení nefungují

HoloLens (1. generace) nepodporuje Bluetooth zvukové profily. Bluetooth se zvuková zařízení, jako jsou mluvčí a náhlavní soupravy, mohou zobrazovat jako dostupná v HoloLens, ale nejsou podporovaná.

HoloLens 2 podporuje zvukový profil Bluetooth A2DP pro stereo přehrávání. Profil Bluetooth Hands Free, který umožňuje zachytávání mikrofonu z Bluetooth periferního zařízení, se v HoloLens 2 nepodporuje.

Pokud máte potíže s používáním Bluetooth, ujistěte se, že se jedná o podporované zařízení. Mezi podporovaná zařízení patří:

- QWERTY v angličtině Bluetooth klávesnice (můžete je použít kdekoli, kde používáte holografičnou klávesnici).
- Bluetooth mice.
- Na [HoloLens klikněte na .](hololens1-clicker.md)

Můžete spárovat jiná zařízení Bluetooth HID a PAIR s vašimi HoloLens. Je však možné, že budete muset nainstalovat odpovídající doprovodné aplikace z Microsoft Store, aby bylo možné zařízení skutečně používat.

[Zpět na seznam](#list)
