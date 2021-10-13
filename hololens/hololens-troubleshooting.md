---
title: HoloLens Řešení potíží se zařízeními
description: Získejte aktuální informace o nejběžnějších řešeních pro řešení HoloLens a řešení potíží.
author: evmill
ms.author: v-evmill
ms.date: 10/7/2021
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: ranjibb
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: issues, bug, troubleshoot, fix, help, support, HoloLens, emulator
ms.openlocfilehash: afbbc1ab0e018f668381137849738ec7d274fe37
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924374"
---
# <a name="device-troubleshooting"></a>Řešení potíží se zařízeními

Tento článek popisuje, jak vyřešit několik běžných HoloLens problémů.

>[!IMPORTANT]
> Než začnete s řešením potíží, ujistěte se, že je vaše zařízení naúčtované **na 20 až 40** % kapacity baterie, pokud je to možné. Indikátory [baterie umístěné](hololens2-setup.md#lights-that-indicate-the-battery-level) pod tlačítkem napájení jsou rychlým způsobem, jak ověřit kapacitu baterie bez přihlášení k zařízení.

<a id="list"></a>

**Známé problémy**
- [Pokaždé, když energie stojde na 18 procent, zařízení se najednou automaticky vypne.](#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)
- [OneDrive Aplikace pro UPW nefunguje pro uživatele Azure AD](#onedrive-uwp-app-doesnt-work-for-azure-ad-users)
- [Proč se během 0x80180014 zobrazí?](#why-do-i-see-0x80180014-during-autopilot)
- [Video remote assist se zablokuje po 20 minutách](#remote-assist-video-freezes-after-20-minutes)
- [Automatické přihlášení žádá o přihlášení](#auto-login-asks-for-log-in)
- [Microsoft Edge spuštění se nepovede](#microsoft-edge-fails-to-launch)
- [Klávesnice se přepíná na speciální znaky](#keyboard-doesnt-switch-to-special-characters)
- [Při stahování uzamčených souborů se nez zobrazení chyby](#downloading-locked-files-doesnt-error)
- [Portál zařízení nahrání nebo stažení souboru](#device-portal-file-uploaddownload-times-out)
- [Modrá obrazovka po zrušení registrace z insider ve verzi Preview na zařízení blikající sestavením Insider](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [OneDrive automaticky nenahraje obrázky](#onedrive-doesnt-automatically-upload-pictures)

**Obecné**
- [HoloLens nereaguje nebo se nespustí](#hololens-is-unresponsive-or-wont-start)
- [Chyba Nedostatek místa na disku](#low-disk-space-error)
- [Selhání selhání](#calibration-fails)
- [Nemůžu se přihlásit, protože HoloLens aplikace byla dříve nastavená pro někoho jiného](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
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
- [Zařízení uvedená jako dostupná Nastavení nefungují](#devices-listed-as-available-in-settings-dont-work)

## <a name="every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically"></a>Pokaždé, když energie stojde na 18 procent, zařízení se najednou automaticky vypne.

Existuje známý problém, kdy když zařízení dosáhne 18% baterie, neočekávaně se vypne. Jedná se o problém se softwarem, ne s hardwarem nebo bateriemi, proto za to zařízení neměňte. Pokud si nejste jistí, jestli váš problém odpovídá této chybě, postupujte prosím:

1. Ujistěte se, že jsou na zařízeních povolená volitelná diagnostika.
1. Reprodukování problému
1. Odeslání [Centrum Feedback](hololens-feedback.md) problému
1. Sdílejte adresu URL problému se zpětnou vazbou.
1. [Kontaktování podpory](https://aka.ms/hololenssupport)

[Zpět na seznam](#list)

## <a name="onedrive-uwp-app-doesnt-work-for-azure-ad-users"></a>OneDrive Aplikace pro UPW nefunguje pro uživatele Azure AD

Pokud používáte OneDrive Pro firmy pomocí účtu Azure AD, při přihlášení k vaší doručené poště nebo aplikaci OneDrive došlo k chybě. Není možné se přihlásit k aplikaci OneDrive nemá vliv na automatické nahrávání obrázků a videí zachycených aplikací Fotoaparát. Soubory je stále možné ukládat a přistupovat k nim OneDrive pro firmy cloudovém úložišti. Tým OneDrive a HoloLens na tomto problému pracují.

### <a name="workarounds"></a>Alternativní řešení

Požadavek: Zákazníci mohou použít Microsoft Edge a operační systém zařízení je aktualizován na Windows Holographic, 21H1 build nebo novější.

Pokud k tomuto problému dochází, zkuste jednu z následujících možností:

- Uživatelé mají přímý přístup OneDrive For Business z Microsoft Edge a pracovat se soubory na webu ze svého prohlížeče.
- Uživatelé si mohou OneDrive PWA aplikaci nainstalovat HoloLens stažením z Microsoft Edge. To uživatelům umožní znovu zobrazit a spravovat soubory v zařízení. Přečtěte si tyto [pokyny a postupujte podle OneDrive PWA aplikace na HoloLens.](holographic-store-apps.md#install-microsoft-onedrive-pwa-app)

[Zpět na seznam](#list)

## <a name="why-do-i-see-0x80180014-during-autopilot"></a>Proč se během 0x80180014 zobrazí?

K této chybě obvykle dojde při resetování zařízení a opětovném použití toků, kdy HoloLens zařízení alespoň jednou prošlo autopilotem. Pokud chcete tento problém vyřešit, [odstraňte](/mem/autopilot/troubleshoot-device-enrollment#error-code-0x80180014-when-re-enrolling-using-self-deployment-or-pre-provisioning-mode) zařízení z Microsoft Intune a znovu ho resetujte, aby se dokončil tok Autopilotu.

Další informace najdete v postupu při [řešení potíží na stránce Autopilotu.](hololens2-autopilot.md#why-do-i-see-0x80180014-during-autopilot)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>Video remote assist se zablokuje po 20 minutách

> [!NOTE]
> K dispozici je novější verze vzdáleného nástroje Remote Assist, která obsahuje opravu tohoto problému. Aktualizujte [službu Remote Assist](holographic-store-apps.md#update-apps) na nejnovější verzi, abyste se tomuto problému vyhnuli.

> [!NOTE]
> Kvůli závažnosti tohoto známého problému jsme dočasně pozastavil dostupnost Windows Holographic verze 21H1. Sestavení 21H1 je teď opět k dispozici, takže zařízení je možné znovu aktualizovat na nejnovější build 21H1.

V nejnovější verzi [Windows Holographic verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1)zaznamenali někteří uživatelé Remote Assistu během volání přes 20 minut zamrznutí videa. Jedná se o **známý problém.**

### <a name="workarounds"></a>Alternativní řešení

Pokud nemůžete aplikaci Remote Assist aktualizovat na novější sestavení, vyzkoušejte následující postup.

#### <a name="restart-in-between-calls"></a>Restartování mezi voláními

Pokud vaše volání přecházují 20 minut a dochází k tomuto problému, zkuste zařízení restartovat. Restartováním zařízení mezi voláními vzdálené pomoci obnovíte zařízení a vrátíte ho do dobrého stavu.

Pokud chcete rychle restartovat zařízení na Windows Holographic, otevřete nabídku Start verze [21H1,](hololens-release-notes.md#windows-holographic-version-21h1) vyberte ikonu uživatele a pak vyberte **Restartovat.**

[Zpět na seznam](#list)

## <a name="auto-login-asks-for-log-in"></a>Automatické přihlášení žádá o přihlášení

Zařízení HoloLens 2 je možné nakonfigurovat tak, aby se automaticky přihlašoval přes **možnosti** přihlášení k účtům Nastavení -> a v části Povinné nastavovat hodnotu  ->    ->   **Na nikdy.**  Někteří uživatelé se při aktualizaci zařízení s podstatně velkou aktualizací, jako je třeba aktualizace funkcí, mohou znova přihlásit k zařízení. Jedná se o **známý problém.**

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

Několik zákazníků nahlásilo problém, kdy Microsoft Edge spuštění. U těchto zákazníků problém přetrvává i po restartování a nevyřeší se Windows aktualizacemi aplikací. Pokud k tomuto problému dochází a potvrdili jste, že [Windows](hololens-updates.md#manually-check-for-updates)je aktuální, zakažte chybu z aplikace [Centrum Feedback](hololens-feedback.md) s následující kategorií a podkate kategorií: Instalace a aktualizace > Stahování, instalace a konfigurace Windows Update.

Neexistují žádná známá alternativní řešení, protože jsme zatím nemohli hlavní příčinu problému. S vyšetřováním vám pomůže Centrum Feedback chyb prostřednictvím webu společnosti. Jedná se o **známý problém**.

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
- Restartujte směrovač Wi-Fi a pak [znovu spusťte HoloLens](hololens-recovery.md). Zkuste se připojit znovu.
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

![Řešení potíží s mikrofony USB-C.](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>zařízení uvedená jako dostupná v Nastavení nefungují

HoloLens (1. generace) nepodporuje profily Bluetooth zvuku. Bluetooth zvuková zařízení, jako jsou například mluvčí a sluchátka, se můžou zobrazovat jako dostupná v nastaveních HoloLens, ale nejsou podporovaná.

HoloLens 2 podporuje zvukový profil Bluetooth A2DP pro přehrávání stereo. v Bluetooth je k dispozici bezplatný profil, který umožňuje zachytávání mikrofonu od Bluetooth periferního zařízení není v HoloLens 2 podporováno.

pokud máte potíže s používáním Bluetooth zařízení, ujistěte se, že se jedná o podporované zařízení. Mezi podporovaná zařízení patří následující:

- jazykové verze pro angličtinu – Bluetooth klávesnice (můžete je použít kdekoli, kde používáte holografickou klávesnici).
- Bluetooth myši.
- [HoloLens click](hololens1-clicker.md).

další Bluetooth zařízení HID a GATT můžete párovat spolu s HoloLens. je ale možné, že budete muset nainstalovat odpovídající doprovodné aplikace z Microsoft Store ke skutečnému používání těchto zařízení.

[Zpět na seznam](#list)
