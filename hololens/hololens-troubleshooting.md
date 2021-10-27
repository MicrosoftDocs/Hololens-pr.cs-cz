---
title: HoloLens Řešení potíží se zařízením
description: udržujte si přehled o nejběžnějších řešeních, abyste HoloLens problémy se zařízením a techniky řešení potíží.
author: evmill
ms.author: v-evmill
ms.date: 10/13/2021
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: ranjibb
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: problémy, chyba, řešení potíží, oprava, pomoc, podpora, HoloLens, emulátor
ms.openlocfilehash: deed0d14b2567ae0a1fb2cde8ad1fbe3dbb20bb3
ms.sourcegitcommit: 73a1555fb8b84f3d20c480282c648d8d800a6c98
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/26/2021
ms.locfileid: "130351761"
---
# <a name="device-troubleshooting"></a>Řešení potíží se zařízením

tento článek popisuje, jak vyřešit několik běžných HoloLens problémů.

>[!IMPORTANT]
> Než začnete s postupem řešení potíží, ujistěte se, že se na zařízení účtuje **20 až 40 procent** kapacity baterie, pokud je to možné. [Indikátory baterie](hololens2-setup.md#lights-that-indicate-the-battery-level) umístěné pod tlačítkem napájení jsou rychlým způsobem, jak ověřit kapacitu baterie bez přihlášení do zařízení.

<a id="list"></a>

**Známé problémy**
- [Oprava programu Insider – při každém přechodu energie na 18% se zařízení náhle automaticky vypne.](#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)
- [OneDrive Aplikace pro UWP nefunguje pro uživatele Azure AD.](#onedrive-uwp-app-doesnt-work-for-azure-ad-users)
- [Proč se při autopilotu zobrazuje 0x80180014?](#why-do-i-see-0x80180014-during-autopilot)
- [kód chyby Microsoft Store 0x80131500](#microsoft-store-error-code-0x80131500)
- [Microsoft Edge se nepodařilo spustit mikrofon.](#microsoft-edge-fails-to-start-the-microphone)
- [**Pevné** – vzdálené video se zablokuje po 20 minutách.](#remote-assist-video-freezes-after-20-minutes)
- [Automatické přihlášení vyžaduje přihlášení.](#auto-login-asks-for-log-in)
- [spuštění Microsoft Edge se nezdařilo.](#microsoft-edge-fails-to-launch)
- [Klávesnice neumožňuje přepnout na speciální znaky.](#keyboard-doesnt-switch-to-special-characters)
- [**Opraveno** – stahování uzamčených souborů nezobrazuje chybu.](#downloading-locked-files-doesnt-error)
- [Časový limit nahrávání nebo stahování souboru portálu **pevného** zařízení](#device-portal-file-uploaddownload-times-out)
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

## <a name="every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically"></a>Pokaždé, když se napájení dosáhne 18%, zařízení se náhle automaticky vypne.

> [!NOTE]
> pro tento problém je k dispozici oprava [Windows insider.](hololens-insider.md)

Máte známý známý problém, když zařízení dosáhne 18% baterie, neočekávaně se vypne. Jedná se o problém se softwarem, nejedná se o problém s hardwarem nebo baterií, proto pro ně nemusíte zařízení vyměnit. Pokud si nejste jistí, jestli váš problém odpovídá této chybě, prosím:

1. Zajistěte, aby na vašich zařízeních byla povolená volitelná Diagnostika.
1. Reprodukování problému
1. Odeslání problému [centra Feedback](hololens-feedback.md)
1. Sdílet adresu URL problému zpětné vazby
1. [Kontaktování podpory](https://aka.ms/hololenssupport)

[Zpět na seznam](#list)

## <a name="onedrive-uwp-app-doesnt-work-for-azure-ad-users"></a>OneDrive Aplikace pro UWP nefunguje pro uživatele Azure AD.

pokud používáte OneDrive pro firmy pomocí účtu Azure AD, možná jste při přihlašování do OneDrive aplikace pro doručenou poštu narazili na chybu. nemůžete se přihlásit k aplikaci OneDrive neovlivní automatická nahrávání obrázků a videí zachycených aplikací kamery. soubory je možné dál ukládat a získávat z OneDrive pro firmy cloudového úložiště. týmy OneDrive a HoloLens na tomto problému pracují.

### <a name="workarounds"></a>Alternativní řešení

předpoklad: zákazníci můžou použít Microsoft Edge a operační systém zařízení se aktualizuje na Windows holografické, 21H1 build nebo novější.

Pokud k tomuto problému dochází, zkuste provést jednu z následujících akcí:

- uživatelé můžou přímo získat přístup k OneDrive pro firmy z Microsoft Edge a pracovat s jejich soubory na webu z prohlížeče.
- uživatelé mohou nainstalovat aplikaci OneDrive PWA do HoloLens stažením ze Microsoft Edge. To umožní uživatelům znovu zobrazit a spravovat soubory v zařízení. přečtěte si následující pokyny a postupujte podle těchto [pokynů pro instalaci aplikace OneDrive PWA na HoloLens.](holographic-store-apps.md#install-microsoft-onedrive-pwa-app)

[Zpět na seznam](#list)

## <a name="why-do-i-see-0x80180014-during-autopilot"></a>Proč se při autopilotu zobrazuje 0x80180014?

k této chybě obvykle dochází během resetování zařízení a opakované použití toků, kdy HoloLens zařízení prošlo pomocí automatického pilotního nasazení alespoň jednou. pokud chcete tento problém vyřešit, odstraňte prosím [zařízení z Microsoft Intune](/mem/autopilot/troubleshoot-device-enrollment#error-code-0x80180014-when-re-enrolling-using-self-deployment-or-pre-provisioning-mode) a znovu ho nastavte, aby se dokončil tok autopilotního nasazení.

Další informace najdete [v postupu řešení potíží na stránce autopilot.](hololens2-autopilot.md#issue---mdm-enrollment-fails-with-error-0x80180014-error-code-during-autopilot)

## <a name="microsoft-store-error-code-0x80131500"></a>kód chyby Microsoft Store 0x80131500

někteří uživatelé můžou zaznamenat Microsoft Store práce nepodle očekávání a zobrazit kód chyby 0x80131500. jedná se o problém způsobený oblastí nastavenou v HoloLens není k dispozici v aplikaci Microsoft Store na HoloLens. Pokud narazíte na 0x80131500 kódu chyby, na alternativní řešení prosím:

1. nastavte Nastavení > čas & jazyka > oblasti > země nebo oblasti na jednu z následujících možností:
    - USA, Japonsko, Čína, Německo, Kanada, Spojené království, Irsko, Francie, Austrálie, Nový Zéland.
1. Restartujte aplikaci ze Storu.
1. Aby se změna projevila u celého zařízení, bude nutné restartovat zařízení.

tým HoloLens pracuje na přidávání podpory pro více oblastí.

pokud si [chcete koupit HoloLens 2,](hololens2-purchase.md) přečtěte si téma pro země.

## <a name="microsoft-edge-fails-to-start-the-microphone"></a>Microsoft Edge se nepodařilo spustit mikrofon.

když uživatelé, kteří používají Microsoft Edge mikrofon, se nemusí podařit spustit, takže nebudete moct pracovat s Edge v HoloLens. tento známý problém se týká verze aplikace Microsoft Edge, nemusíte své zařízení znovu zablikat na starší verzi, protože tento problém nebude vyřešen.

### <a name="who-is-affected"></a>Má to vliv na Kdo?

uživatelé, kteří mají Microsoft Edge verze 93, 94 nebo 95.
pomocí aplikace Microsoft Store můžete zjistit, kterou verzi Microsoft Edge máte, a pak vybrat tlačítko zobrazit další, které představuje **...** a pak vyberte **soubory ke stažení a aktualizace**.

### <a name="work-around"></a>Alternativní řešení

aktuální oprava je ve verzi 96, která je dostupná pro uživatele, kteří se zaregistrovali v Microsoft Edge insiders. to se liší od registrace zařízení jako Windows Insider. Podrobné informace o [tom, jak se zaregistrovat do programu Insider Edge,](hololens-new-edge.md#microsoft-edge-insider-channels) najdete v těchto pokynech.

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
- Pokud se PIN kód zařízení nedá zapamatovat a jiné metody ověřování nejsou k dispozici, může uživatel použít [režim ručního přebliknutí](hololens-recovery.md#manual-flashing-mode-procedure).

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
- Pokud při stisknutí tlačítka napájení zhasnou diody LED, ale nevidíte cokoli na zobrazených displejech, [proveďte obnovení zařízení](hololens-recovery.md#hard-restart-procedure).

pokud bude váš HoloLens zmrazený nebo nereaguje:

- vypněte HoloLens tím, že stisknete tlačítko napájení, dokud se všechny pět diod led nevypne, nebo 15 sekund, pokud indikátory led nereagují. HoloLens spustíte tak, že znovu stisknete tlačítko napájení.

pokud tyto kroky nefungují, můžete zkusit [obnovit zařízení HoloLens 2](hololens-recovery.md) nebo [HoloLens (1. generace).](hololens1-recovery.md)

[Zpět na seznam](#list)

## <a name="low-disk-space-error"></a>Chyba "nedostatek místa na disku"

K uvolnění úložného prostoru budete potřebovat jednu nebo více následujících akcí:

- Odstraňte některé nepoužité mezery. v **Nastavení**  >  **systémových**  >  **prostorech** vyberte místo, které už nepotřebujete, a pak vyberte **odebrat**.
- Odeberte některé hologramy, které jste umístili.
- Odstraňte některé obrázky a videa z aplikace Photos.
- Odinstalujte některé aplikace z HoloLens. V seznamu **Všechny aplikace** klepněte a podržte aplikaci, kterou chcete odinstalovat, a pak vyberte **Odinstalovat.**

[Zpět na seznam](#list)

## <a name="calibration-fails"></a>Selhání selhání

Většina lidí by měla fungovat, ale existují případy, kdy selhání selže.
  
Mezi možné důvody selhání patří:

- Rušivé a nenáschodné cíle
- Nečtený nebo poškemkovaný vizuátor zařízení nebo visor zařízení není správně umístěný
- Vyčištěné nebo poškemlené brýle
- Určité typy kontaktních objektivů a brýlí (barevné kontaktní objektivy, některé toric kontaktní objektivy, IR blokující brýle, některé brýle na předpis, sluneční brýle a podobné)
- Výraznější výrazy a některá rozšíření kolií
- Vousy nebo snímky silných brýlí, pokud blokují, aby zařízení vidělo vaše oči
- Určitá neschopná zraková onemocnění, zrakové stavy nebo operace očí, jako jsou zúžení očí, dlouhá lomítka, amblyopia, nystagmus, některé případy LASIK nebo jiné operace oka

Pokud není neúspěšné pokus o přihlášení:

- Vyčištění visoru zařízení
- Čištění brýlí
- Co možná nejvíce nasazování vizuály zařízení do zornice
- Přesunutí objektů do visoru mimo cestu (například vousy)
- Zapnutí světla v místnosti nebo přesun z přímého světla

Pokud jste postupoval podle všech pokynů a stále selhává, můžete zakázat výzvu k zadání v Nastavení. Dejte nám vědět také vyplněním zpětné vazby [na Centrum Feedback](hololens-feedback.md).

Další informace najdete v souvisejících [informacích o řešení potíží s barvou nebo jasem obrázku.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

Nastavení IPD nelze použít pro HoloLens 2, protože pozice oka jsou vypočítávány systémem. 

[Zpět na seznam](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>Nemůžu se přihlásit, protože moje HoloLens byla dříve nastavená pro někoho jiného

Zařízení můžete [přetát do **režimu blikajícího režimu** a pomocí doprovodné funkce rozšířeného](hololens-recovery.md#clean-reflash-the-device) obnovení zařízení obnovit.

[Zpět na seznam](#list)


## <a name="unity-isnt-working"></a>Unity nefunguje

- Nejnovější [verzi Unity doporučenou](/windows/mixed-reality/install-the-tools) pro vývoj pro HoloLens najdete v tématu Instalace nástrojů.
- Známé problémy s Unity HoloLens Technical Preview jsou dokumentované na fórech [HoloLens Unity.](https://forum.unity3d.com/threads/known-issues.394627/)

[Zpět na seznam](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows Portál zařízení nefunguje správně

- Funkce Live Preview v zachytávání Mixed Reality může vykazovat latenci několik sekund.

- Na stránce Virtuální vstup nejsou ovládací prvky Gesto a Posouvání v části Virtuální gesta funkční. Jejich použití nebude mít žádný vliv. Virtuální klávesnice na virtuální vstupní stránce funguje správně.

- Po povolení vývojářského režimu v Nastavení může trvat několik sekund, než se přepínač zapne a Portál zařízení povolí.

[Zpět na seznam](#list)

## <a name="the-hololens-emulator-isnt-working"></a>HoloLens Emulator nefunguje

Informace o emulátoru HoloLens najdete v naší dokumentaci pro vývojáře.  Přečtěte si další [informace o řešení potíží HoloLens emulátoru.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)


- Ne všechny aplikace v Microsoft Store jsou kompatibilní s emulátorem. Například Young Conker a Fragments se v emulátoru nehrají.
- V počítači nemůžete použít webovou kameru Emulator.
- Funkce Live Preview v Windows Portál zařízení nefunguje s emulátorem. Stále můžete zachytit Mixed Reality videa a obrázky.

[Zpět na seznam](#list)

## <a name="voice-commands-arent-working"></a>Nefungují hlasové příkazy

Pokud Cortana nereaguje na vaše hlasové příkazy, ujistěte se, Cortana je zapnutá. V seznamu Všechny aplikace vyberte **Poznámkový** blok Cortana nabídky Nastavení a  >    >    >   proveďte změny. Další informace o tom, co můžete říct, najdete v tématu [Použití hlasu s HoloLens](hololens-cortana.md).

V HoloLens (1. generace) není integrované rozpoznávání řeči konfigurovatelné. Vždy je zapnutý. Na HoloLens 2 můžete zvolit, jestli se má při nastavování zařízení zapnout rozpoznávání Cortana i rozpoznávání řeči.

Pokud váš HoloLens 2 nereaguje na váš hlas, ujistěte se, že je zapnuté rozpoznávání řeči. Přejděte na **Start Nastavení** Privacy Speech a  >    >    >   zapněte **Rozpoznávání řeči.**

[Zpět na seznam](#list)

## <a name="hand-input-isnt-working"></a>Ruční vstup nefunguje

Aby bylo HoloLens vidět vaše ruce, musíte je ponechat v snímku gest.  Domovská Mixed Reality poskytuje zpětnou vazbu, která vám dá vědět, kdy jsou vaše ruce sledované.  Zpětná vazba se liší v různých verzích HoloLens:

- V HoloLens (1. generace) se kurzor pohledu změní z tečky na kruh.
- Na HoloLens 2 se zobrazí kurzor prstu, když se vaše ruky nachází blízko slate, a když jsou břidíčky dále, zobrazí se ruční paprsk.

Řada imerzivních aplikací dodržuje vzory vstupu, které se podobají Mixed Reality Domovské obrazovce.  Další informace o použití ručního [vstupu v HoloLens (1. generace)](hololens1-basic-usage.md#use-hololens-with-your-hands) a [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).

Pokud máte problémy s chemií, mějte na vědomí, že některé typy choumů nefungují se sledováním rukou.  Běžným příkladem je černá guma, která obvykle absorbuje infračervené světlo a nenabírá je hloubková kamera.  Pokud vaše práce zahrnuje gumové gumy, doporučujeme, abyste si zkusili světlejší barvu, například modrou nebo šedou.  Dalším příkladem je velká nesrozumilá léna, která má tendenci zakrytí tvaru vaší ruky. Pro nejlepší výsledky doporučujeme použít co nejvíce tvarování.

Pokud má váš vizor otisky prstů nebo šmouhy, vyčistěte ji pomocí čisticího mikrovlákna, který se HoloLens vyčistit.

[Zpět na seznam](#list)

## <a name="cant-connect-to-wi-fi"></a>Nelze se připojit k Wi-Fi

Tady je několik věcí, které můžete vyzkoušet, pokud nemůžete připojit HoloLens k Wi-Fi síti:

- Ujistěte se, Wi-Fi je zapnuté. Kontrolu můžete provést pomocí gesta Start a pak **Nastavení**  >  **Network &amp; Internet**  >  **Wi-Fi**. Pokud Wi-Fi, zkuste ho vypnout a znovu zas.
- Přesuňte se blíž ke směrovači nebo přístupovému bodu.
- Restartujte směrovač Wi-Fi a [pak restartujte HoloLens](hololens-recovery.md). Zkuste se připojit znovu.
- Pokud nic z toho nefunguje, ujistěte se, že váš směrovač používá nejnovější firmware. Tyto informace najdete na webu výrobce.

[Zpět na seznam](#list)

## <a name="bluetooth-devices-arent-pairing"></a>Bluetooth zařízení se ne pairují

Pokud máte problémy s [párem zařízení Bluetooth,](hololens-connect-devices.md)zkuste následující postup:

- Přejděte na **Nastavení** Zařízení a  >  ujistěte se, Bluetooth je zapnutá. Pokud je, vypněte ho a znovu zapněte.
- Ujistěte se, že Bluetooth zařízení je plně nabité nebo obsahuje čerstvé baterie.
- Pokud se stále nemůžete připojit, [restartujte HoloLens](hololens-recovery.md).

[Zpět na seznam](#list)

## <a name="usb-c-microphone-isnt-working"></a>Mikrofon USB-C nefunguje

Uvědomte si, že některé mikrofony USB-C se nesprávně hlásí jako *mikrofon* i jako mluvčí. Jedná se o problém s mikrofonem, a ne s HoloLens. Když jeden z těchto mikrofonů zapojíte do HoloLens, může dojít ke ztrátě zvuku. Naštěstí existuje jednoduchá oprava.  

V **Nastavení** System Sound (Zvuk systému) explicitně nastavte integrované mluvčí (zvukový ovladač  ->    ->   **analogové funkce)** jako **výchozí zařízení.** HoloLens byste si toto nastavení měli zapamatovat, i když se mikrofon později odebere a znovu připojí.

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
