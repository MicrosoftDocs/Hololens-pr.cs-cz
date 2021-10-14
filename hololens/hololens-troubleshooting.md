---
title: HoloLens Řešení potíží se zařízeními
description: Získejte aktuální informace o nejběžnějších řešeních pro řešení HoloLens a řešení potíží.
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
keywords: issues, bug, troubleshoot, fix, help, support, HoloLens, emulator
ms.openlocfilehash: 247cf9d34da723e587f6796178ad9a917b93ac08
ms.sourcegitcommit: 39accbc8e35728969c500da052035af4fd317a65
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/13/2021
ms.locfileid: "129964560"
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
- [Microsoft Store kód chyby 0x80131500](#microsoft-store-error-code-0x80131500)
- [Microsoft Edge se nepodařilo spustit mikrofon](#microsoft-edge-fails-to-start-the-microphone)
- [**Opraveno** – video vzdálené pomoci se po 20 minutách zablokuje](#remote-assist-video-freezes-after-20-minutes)
- [Automatické přihlášení žádá o přihlášení](#auto-login-asks-for-log-in)
- [Microsoft Edge spuštění se nepovede](#microsoft-edge-fails-to-launch)
- [Klávesnice se přepíná na speciální znaky](#keyboard-doesnt-switch-to-special-characters)
- [**Opraveno** – Při stahování uzamčených souborů se nez zobrazení chyby](#downloading-locked-files-doesnt-error)
- [**Opraveno** – Portál zařízení nahrání/stažení souboru](#device-portal-file-uploaddownload-times-out)
- [Modrá obrazovka po zrušení registrace z verze Preview insideru na zařízení blikající sestavením Insider](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
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
- [Zařízení uvedená jako dostupná v Nastavení nefungují](#devices-listed-as-available-in-settings-dont-work)

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

## <a name="why-do-i-see-0x80180014-during-autopilot"></a>Proč se během 0x80180014 zobrazí další informace?

K této chybě obvykle dojde při resetování zařízení a opětovném použití toků, kdy HoloLens zařízení alespoň jednou prošlo autopilotem. Pokud chcete tento problém vyřešit, [odstraňte](/mem/autopilot/troubleshoot-device-enrollment#error-code-0x80180014-when-re-enrolling-using-self-deployment-or-pre-provisioning-mode) zařízení z Microsoft Intune a znovu ho resetujte, aby se dokončil tok Autopilotu.

Další informace najdete v postupu při [řešení potíží na stránce Autopilotu.](hololens2-autopilot.md#why-do-i-see-0x80180014-during-autopilot)

## <a name="microsoft-store-error-code-0x80131500"></a>Microsoft Store kód chyby 0x80131500

U některých uživatelů může docházet Microsoft Store, že nefunguje podle očekávání, a zobrazí se vám kód 0x80131500. Jedná se o problém způsobený tím, že oblast nastavená na HoloLens není dostupná v aplikaci Microsoft Store na HoloLens. Pokud narazíte na chybu s 0x80131500, alternativní řešení:

1. Nastavte Nastavení > Time & Language > Region > Country (Země nebo oblast) na jednu z následujících možností:
    - USA, Japonsko, Čína, Německo, Kanada, Spojené království, Irsko, Francie, Austrálie, Nový Zéland.
1. Restartujte aplikaci Store.
1. Aby se změna promítla do celého zařízení, bude potřeba zařízení restartovat.

Tým HoloLens pracuje na přidání podpory pro další oblasti.

Země, [ve které si můžete koupit HoloLens 2, najdete tady.](hololens2-purchase.md)

## <a name="microsoft-edge-fails-to-start-the-microphone"></a>Microsoft Edge se nepodařilo spustit mikrofon

Pokud se Microsoft Edge s mikrofonem spustit, takže nebude možné s Edgem pracovat v HoloLens. Tento známý problém souvisí s verzí aplikace Microsoft Edge. Nepřidáte prosím své zařízení na starší verzi, protože tím se tento problém nevypraví.

### <a name="who-is-affected"></a>Kdo to má vliv?

Uživatelé, kteří Microsoft Edge verze 93, 94 nebo 95.
Pomocí aplikace Microsoft Store můžete zkontrolovat, kterou verzi Microsoft Edge máte, a pak vybrat tlačítko Zobrazit více reprezentované tlačítkem **...** a pak vybrat Položky ke stažení a **aktualizace.**

### <a name="work-around"></a>Obchádky

Aktuální oprava je ve verzi 96, která je dostupná pro uživatele, kteří se zaregistrovali v Microsoft Edge Insider. To se liší od registrace zařízení jako Windows Insider. Přečtěte si tyto [pokyny, kde najdete podrobnosti o tom, jak se](hololens-new-edge.md#microsoft-edge-insider-channels) zaregistrovat do programu Edge insider.

## <a name="remote-assist-video-freezes-after-20-minutes"></a>Video remote assist se zablokuje po 20 minutách

> [!NOTE]
> K dispozici je novější verze vzdáleného nástroje Remote Assist, která obsahuje opravu tohoto problému. Aktualizujte [službu Remote Assist](holographic-store-apps.md#update-apps) na nejnovější verzi, abyste se tomuto problému vyhnuli.

> [!NOTE]
> Kvůli závažnosti tohoto známého problému jsme dočasně pozastavil dostupnost Windows Holographic verze 21H1. Sestavení 21H1 je teď opět k dispozici, takže zařízení je možné znovu aktualizovat na nejnovější build 21H1.

V nejnovější verzi Windows Holographic verze [21H1](hololens-release-notes.md#windows-holographic-version-21h1)zaznamenali někteří uživatelé Vzdálené pomoci zamrznutí videa během 20 minut. Jedná se o **známý problém.**

### <a name="workarounds"></a>Alternativní řešení

Pokud nemůžete aplikaci Remote Assist aktualizovat na novější sestavení, vyzkoušejte následující postup.

#### <a name="restart-in-between-calls"></a>Restartování mezi voláními

Pokud vaše volání přecházují 20 minut a dochází k tomuto problému, zkuste zařízení restartovat. Restartováním zařízení mezi voláními vzdálené pomoci obnovíte zařízení a vrátíte ho do dobrého stavu.

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
> Tento problém byl původně vytvořen s náklady na Microsoft Edge verzí. Tento problém se může vyřešit v [nové Microsoft Edge](hololens-new-edge.md). Pokud ne, zpětnou vazbu nahlaste.

Několik zákazníků nahlásilo problém, kdy Microsoft Edge spuštění. U těchto zákazníků problém přetrvává i po restartování a nevyřeší se Windows aktualizacemi aplikací. Pokud k tomuto problému dochází a potvrdili jste, že [Windows](hololens-updates.md#manually-check-for-updates)je aktuální, zakažte chybu z aplikace [Centrum Feedback](hololens-feedback.md) s následující kategorií a podkate kategorií: Instalace a aktualizace > Stahování, instalace a konfigurace Windows Update.

Neexistují žádná známá alternativní řešení, protože jsme zatím nemohli hlavní příčinu problému. S vyšetřováním vám pomůže Centrum Feedback chyb prostřednictvím tohoto webu. Jedná se o **známý problém.**

[Zpět na seznam](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>Klávesnice se přepne na speciální znaky

Při ooBE dochází k problému, kdy se po zvolení pracovního nebo školního účtu a zadání hesla uživatel pokouší přepnout na speciální znaky na klávesnici klepnutím na tlačítko &123, nezmění se na speciální znaky. Jedná se o **známý problém.**

Obchádky:

- Zavřete klávesnici a znovu ji otevřete klepnutím na textové pole.
- Nesprávně zadejte heslo. Při příštím spuštění klávesnice bude klávesnice fungovat podle očekávání.
- Webové ověřování, zavřete klávesnici a vyberte **Přihlásit se z jiného zařízení**.
- Pokud zadáváte jenom čísla, uživatel může stisknutím a podržením určitých kláves otevřít rozbalenou nabídku.
- Pomocí klávesnice USB.

To nemá vliv na:

- Uživatelé, kteří se rozhodnout použít osobní účet.

[Zpět na seznam](#list)

## <a name="downloading-locked-files-doesnt-error"></a>Při stahování uzamčených souborů se ne zobrazí chyba

> [!NOTE]
> Jedná se o **známý problém,** který byl opraven [Windows Holographic verze 21H1 – aktualizace z července 2021.](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update)

V předchozích sestaveních Windows Holographic by výsledkem pokusu o stažení uzamčeného souboru byla chybová stránka HTTP. V Windows Holographic verze 21H1 při pokusu o stažení uzamčeného souboru se nic nestane – soubor se nestáhne a nezobrazí se žádná chyba.

[Zpět na seznam](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>Portál zařízení nahrání nebo stažení souboru
> [!NOTE]
> Jedná se o **známý problém,** který byl opraven [Windows Holographic verze 21H1 – aktualizace z července 2021.](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update) Pokud jste v rámci tohoto alternativního řešení dříve zakázali připojení SSL, důrazně doporučujeme ho znovu povolit.

Někteří zákazníci zjistili, že při pokusu o nahrání nebo stažení souborů se operace může zdát, že přestane reagovat a pak dojde k časovému limitu nebo se nikdy nedokoncuje. Tento problém je[](#downloading-locked-files-doesnt-error) oddělený od známého problému uzamčeného souboru – to má vliv na sestavení na trhu Windows Holographic, verze 2004, 20H2 a 21H1. Problém byl způsobený chybou při Portál zařízení zpracování určitých požadavků a při použití protokolu https, což je výchozí nastavení, dochází nejčastěji k tomuto problému.

### <a name="workaround"></a>Alternativní řešení

Toto alternativní řešení, které platí stejně pro Wi-Fi a UsbNcm, je zakázat možnost "povinné" v části Připojení SSL. Pokud to chcete udělat, přejděte Portál zařízení, **Systém** a vyberte **stránku** Předvolby. V části **Zabezpečení zařízení** vyhledejte Připojení **SSL a** zrušte zaškrtnutí, pokud chcete zakázat **povinné.**

Uživatel by pak měl přejít na http://, ne https:// (IP adresa) a funkce, jako je nahrávání a stahování souborů, budou fungovat.

[Zpět na seznam](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>Modrá obrazovka po zrušení registrace z insider ve verzi Preview na zařízení blikající sestavením Insider

Jedná se o problém ovlivňující uživatele, kteří byli v buildu Insider ve verzi Preview, odmítal svůj HoloLens 2 novým buildem insider ve verzi Preview a pak zrušit jeho zrušení v programu Insider. Jedná se o **známý problém.**

To nemá vliv na:

- Uživatelé, kteří nejsou zaregistrovaní ve Windows Insider
- Zasvěcenci:
    - Pokud bylo zařízení zaregistrované od sestavení Insider verze 18362.x
    - Pokud se v programu Insider blikal podepsaný build 19041.x a zůstal zaregistrovaný v programu Insider

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

Aplikace OneDrive pro HoloLens nepodporuje automatické nahrávání z fotoaparátu pro pracovní nebo školní účty. Jedná se o **známý problém.**

Alternativní řešení:

- Pokud je pro vaši firmu přijatelné, je u uživatelských účtů Microsoft podporováno automatické nahrávání fotoaparátu. Ke svému pracovnímu nebo školnímu účet Microsoft přihlášení (aplikace OneDrive podporuje duální přihlašování) se můžete přihlásit i ke svému pracovnímu nebo školnímu účtu. Ve svém účet Microsoft v rámci OneDrive můžete povolit automatické nahrávání fotoaparátů na pozadí.

- Pokud nemůžete bezpečně používat uživatelský účet účet Microsoft automatické nahrávání fotek, můžete fotky ručně nahrát do pracovního nebo školního účtu z OneDrive aplikace. Pokud to chcete udělat, ujistěte se, že jste přihlášení ke svému pracovnímu nebo školnímu účtu v OneDrive aplikace. Vyberte tlačítko **+** a zvolte **Upload**. Fotky nebo videa, která chcete nahrát, najdete tak, že přejdete na Obrázky **> fotoaparátu.** Vyberte fotky nebo videa, která chcete nahrát, a pak vyberte **tlačítko** Otevřít.

[Zpět na seznam](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens nereaguje nebo se nespustí

Pokud HoloLens nezačáte:

- Pokud se indikátory LED vedle tlačítka napájení nesvítí nebo krátce blikne jenom jedna dioda LED, možná budete muset zařízení [HoloLens.](hololens2-charging.md#charging-the-device)
- Pokud se LED diody rozsvítí, když stisknete tlačítko napájení, ale na displeji se nic neuvidí, proveďte pevné [resetování zařízení.](hololens-recovery.md#hard-reset-procedure)

Pokud se HoloLens zamrzne nebo přestane reagovat:

- Vypněte svůj HoloLens stisknutím tlačítka napájení, dokud se všechny pěti diody LED nevypnou, nebo po dobu 15 sekund, pokud diody LED nereagují. Pokud chcete spustit HoloLens, znovu stiskněte tlačítko napájení.

Pokud tento postup nefunguje, můžete zkusit obnovit zařízení [HoloLens 2](hololens-recovery.md) nebo [HoloLens (1. generace).](hololens1-recovery.md)

[Zpět na seznam](#list)

## <a name="low-disk-space-error"></a>Chyba Nedostatek místa na disku

Budete muset některé místo úložiště volná jedním nebo více z následujících způsobů:

- Odstraňte některé nepoužívané mezery. Přejděte do **Nastavení**  >    >  **prostorů** systému, vyberte mezeru, kterou už nepotřebujete, a pak vyberte **Odebrat.**
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

HoloLens (1. generace) nepodporuje Bluetooth zvukové profily. Bluetooth se zvuková zařízení, jako jsou mluvčí a náhlavní soupravy, mohou zobrazovat jako dostupná v HoloLens, ale nejsou podporovaná.

HoloLens 2 podporuje Bluetooth zvukového profilu A2DP pro stereo přehrávání. Profil Bluetooth Hands Free, který umožňuje zachytávání mikrofonu z Bluetooth periferního zařízení, se na HoloLens 2 nepodporuje.

Pokud máte potíže s používáním Bluetooth zařízení, ujistěte se, že se jedná o podporované zařízení. Mezi podporovaná zařízení patří:

- QWERTY v angličtině Bluetooth klávesnice (můžete je použít kdekoli, kde používáte holografičnou klávesnici).
- Bluetooth mice.
- Na [HoloLens klikněte na .](hololens1-clicker.md)

Můžete spárovat další Bluetooth hid a zařízení PAIR s vašimi HoloLens. Je však možné, že budete muset nainstalovat odpovídající doprovodné aplikace z Microsoft Store, aby tato zařízení skutečně bylo možné používat.

[Zpět na seznam](#list)
