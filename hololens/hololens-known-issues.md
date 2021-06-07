---
title: Známé problémy pro HoloLens
description: Seznam známých problémů a alternativních řešení, která mohou ovlivnit zákazníky a vývojáře HoloLens využívající Unity a Portál zařízení s Windows.
keywords: řešení potíží, známý problém, nápověda
author: mattzmsft
ms.author: mazeller
ms.date: 11/30/2020
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
- HoloLens 2
ms.openlocfilehash: bc1d399a07a6a0622c953178cad7be1b8a018fdb
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111377649"
---
# <a name="known-issues-for-hololens"></a>Známé problémy pro HoloLens

Tady je aktuální seznam známých problémů pro zařízení HoloLens. Nejprve zkontrolujte, jestli se vám nesnídí chování. Tento seznam se bude aktualizovat při zjištěných nebo nahlášených nových problémech nebo při řešení problémů v budoucích aktualizacích softwaru HoloLens.

>[!NOTE]
> - Pokud zjistíte problém, který neblokuje, nahlásit ho prosím na svém zařízení HoloLens přes [Centrum Feedback](hololens-feedback.md).
> - Pokud vás váš problém blokuje, kromě vyplnění zpětné vazby uveďte také žádost [o podporu.](https://aka.ms/hlsupport)

- [Známé problémy pro všechny generace HoloLens](#known-issues-for-all-hololens-generations)
- [Známé problémy pro zařízení HoloLens 2](#known-issues-for-hololens-2-devices)
- [Známé problémy s HoloLens (1. generace)](#known-issues-for-hololens-1st-gen)
- [Známé problémy s emulátorem HoloLens](#known-issues-for-hololens-emulator)

## <a name="known-issues-for-all-hololens-generations"></a>Známé problémy pro všechny generace HoloLens

### <a name="unity"></a>Unity

- Nejnovější [verzi Unity doporučenou](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) pro vývoj pro HoloLens najdete v tématu Instalace nástrojů.
- Známé problémy s Unity HoloLens Technical Preview jsou dokumentované na fórech [HoloLens Unity.](https://forum.unity3d.com/threads/known-issues.394627/)

### <a name="windows-device-portal"></a>Portál zařízení s Windows

- Funkce Live Preview v Mixed Reality může vykazovat latenci několik sekund.

- Na stránce Virtuální vstup nejsou ovládací prvky Gesture a Scroll v části Virtuální gesta funkční. Jejich použití nebude mít žádný vliv. Virtuální klávesnice na stránce virtuálního vstupu funguje správně.

- Po povolení režimu pro vývojáře v Nastavení může trvat několik sekund, než se přepínač zapne, Portál zařízení povoleno.

### <a name="onedrive-camera-upload"></a>Nahrání fotoaparátu na OneDrive

Aplikace OneDrive pro HoloLens nepodporuje automatické nahrávání z fotoaparátu pro pracovní nebo školní účty.

Alternativní řešení:

- Pokud je pro vaši firmu přijatelné, je u uživatelských účtů Microsoft podporováno automatické nahrávání fotoaparátu. K pracovnímu nebo školnímu účtu se účet Microsoft přihlásit i ke svému pracovnímu nebo školnímu účtu (aplikace OneDrive podporuje duální přihlášení). Ve svém účet Microsoft v rámci OneDrivu můžete povolit automatické nahrávání fotoaparátů na pozadí.

- Pokud nemůžete bezpečně používat uživatelský účet účet Microsoft k automatickému nahrávání fotek, můžete fotky z aplikace OneDrive nahrát ručně do svého pracovního nebo školního účtu. Pokud to chcete udělat, ujistěte se, že jste v aplikaci OneDrive přihlášení ke svému pracovnímu nebo školnímu účtu. Vyberte tlačítko **+** a zvolte **Nahrát.** Najděte fotky nebo videa, které chcete nahrát, tak, že přejdete na Obrázky **> fotoaparátu.** Vyberte fotky nebo videa, která chcete nahrát, a pak vyberte **tlačítko** Otevřít.

## <a name="known-issues-for-hololens-2-devices"></a>Známé problémy pro zařízení HoloLens 2

### <a name="device-using-auto-login-asks-for-log-in"></a>Zařízení s využitím automatického přihlášení žádá o přihlášení

Zařízení HoloLens 2 je možné nakonfigurovat tak, aby se automaticky přihlašoval přes Nastavení Účty Možnosti přihlášení -> a v části  ->    ->    Požadováno na hodnotu Nikdy **.** Někteří uživatelé se při aktualizaci zařízení s podstatně velkou aktualizací, jako je třeba aktualizace funkcí, mohou znova přihlásit k zařízení.

Příklad, kdy k tomu může dojít:

- Aktualizace zařízení z Windows Holographic verze 2004 (build 19041.xxxx) na Windows Holographic verze 21H1 (build 20346.xxxx)
- Aktualizace zařízení tak, aby šouplodou aktualizaci ve stejném hlavním buildu, např. Windows Holographic, verze 2004 na Windows Holographic, verze 20H2
- Aktualizace zařízení z image továrny na nejnovější image

K tomu by nemělo dojít během těchto období:

- Zařízení, která mají měsíční servisní aktualizaci

Alternativní metody:

- Metody přihlášení, jako jsou PIN, heslo, Iris, webové ověřování nebo klíče FIDO2.
- Pokud pin kód zařízení nelze zapamatovat a jiné metody ověřování nejsou k dispozici, může uživatel použít režim [ručního lomítka](hololens-recovery.md#manual-procedure).

### <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge spuštění se nepovede

> [!NOTE]
> Tento problém byl původně vytvořen s náklady na Microsoft Edge verzí. Tento problém se může vyřešit v [nové Microsoft Edge](hololens-new-edge.md). Pokud ne, zpětnou vazbu nahlaste.

Několik zákazníků nahlásilo problém, kdy Microsoft Edge spuštění. U těchto zákazníků problém přetrvává i po restartování a nevyřeší se aktualizacemi aplikací nebo Windows. Pokud k tomuto problému dochází a potvrdili jste, že [je Windows](hololens-updates.md#manually-check-for-updates)aktuální, zakažte chybu z aplikace [Centrum Feedback](hololens-feedback.md) s následující kategorií a podkate kategorií: Instalace a aktualizace > Stažení, instalace a konfigurace služba Windows Update.

Neexistují žádná známá alternativní řešení, protože jsme zatím nemohli hlavní příčinu problému. S vyšetřováním vám pomůže Centrum Feedback chyb prostřednictvím webu společnosti.

### <a name="keyboard-does-not-switch-to-special-characters"></a>Klávesnice nepřekašuje na speciální znaky

Při ooBE dochází k problému, kdy se po zvolení pracovního nebo školního účtu a zadání hesla uživatel pokouší přepnout na speciální znaky na klávesnici klepnutím na tlačítko &123, nezmění se na speciální znaky.

Obchádky:
-   Zavřete klávesnici a znovu ji otevřete klepnutím na textové pole.
-   Nesprávně zadejte heslo. Při příštím spuštění klávesnice bude klávesnice fungovat podle očekávání.
- Webové ověřování, zavřete klávesnici a vyberte **Přihlásit se z jiného zařízení**.
-   Pokud zadáváte jenom čísla, uživatel může stisknutím a podržením určitých kláves otevřít rozbalenou nabídku.
-   Pomocí klávesnice USB.

To nemá vliv na:
- Uživatelé, kteří se rozhodnout použít osobní účet.

### <a name="blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-an-insider-build"></a>Modrá obrazovka se zobrazí po zrušení registrace v buildech Insider Preview na zařízení, které je v souladu se sestavením Insider.

Jedná se o problém ovlivňující uživatele, kteří byli v buildu Insider ve verzi Preview, odmítnul HoloLens 2 novým buildem insider ve verzi Preview a pak zrušit jeho zrušení v programu Insider.

To nemá vliv na:
- Uživatelé, kteří nejsou zaregistrovaní v Windows Insider 
- Zasvěcenci:
    - Pokud bylo zařízení zaregistrované od sestavení Insider verze 18362.x
    - Pokud se v programu Insider blikal podepsaný build 19041.x a zůstal zaregistrovaný v programu Insider

Obchádky: 
- Vyhněte se problému 
    - Flash sestavení, které není zevnitř. Jedna z běžných měsíčních aktualizací.
    - Zůstaňte ve verzi Insider Preview
- Odkazování zařízení

    1. Dejte [HoloLens 2 do režimu blikajícího](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) režimu ručně úplným vypnutím, zatímco se nepřipojí. Při podržíte Tlačítko napájení klepněte na tlačítko Napájení.
    
    1. Připojte se k počítači a otevřete Doprovodný průvodce pokročilým obnovením.
    
    1. Flash disk HoloLens 2 do výchozího sestavení.

## <a name="known-issues-for-hololens-1st-gen"></a>Známé problémy s HoloLens (1. generace)

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>Nelze se připojit a nasadit do HoloLens prostřednictvím Visual Studio

> [!NOTE]
> Poslední aktualizace: 8/8 @ 17:11 – Visual Studio vydala VS 2019 verze 16.2, která zahrnuje opravu tohoto problému. Doporučujeme provést aktualizaci na tuto nejnovější verzi, abyste se vyhnuli této chybě.

Visual Studio vydali VS 2019 verze 16.2, která zahrnuje opravu tohoto problému. Doporučujeme provést aktualizaci na tuto nejnovější verzi, abyste se vyhnuli této chybě.

Hlavní příčina problému: Uživatelé, kteří použili Visual Studio 2015 nebo dřívější verze Visual Studio 2017 k nasazení a ladění aplikací na zařízení HoloLens a následně použili nejnovější verze Visual Studio 2017 nebo Visual Studio 2019 se stejným HoloLensem, budou ovlivněni. Novější verze Visual Studio nasadí novou verzi komponenty, ale soubory ze starší verze zůstanou na zařízení, což způsobí selhání novější verze.  To způsobí následující chybovou zprávu: DEP0100: Ujistěte se, že cílové zařízení má povolený vývojářský režim. Nelze získat vývojářské licence pro \<ip\> kvůli chybě 80004005.

#### <a name="workaround"></a>Alternativní řešení

Náš tým aktuálně pracuje na opravě. Do té doby můžete pomocí následujících kroků problém obvyřešit a odblokovat nasazení a ladění:  

1. Otevřete sadu Visual Studio.

1. Vyberte **File** New Project  >  **(Soubor nového**  >  **projektu).**

1. Vyberte **Visual C#**  >  **Desktopová**  >  **konzolová aplikace windows (.NET Framework).**

1. Dejte projektu název (například HoloLensDeploymentFix) a ujistěte se, že je rozhraní nastavené alespoň na .NET Framework 4.5, a pak vyberte **OK.**

1. Klikněte pravým tlačítkem **na** uzel Odkazy v Průzkumník řešení přidejte následující odkazy (vyberte v části **Procházet** a vyberte **Procházet**):

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > Pokud nemáte nainstalovanou verzi 10.0.18362.0, použijte nejnovější verzi, kterou máte. 

1. Klikněte pravým tlačítkem na projekt v Průzkumník řešení **a vyberte Přidat** existující  >  **položku**.

1. Přejděte do složky C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 a změňte filtr na **Všechny soubory ( . \* \* ).**

1. Vyberte SirepClient.dll i SshClient.dll a vyberte **Přidat.**

1. Vyhledejte a vyberte oba soubory v Průzkumník řešení (měly by být v dolní  části seznamu souborů) a změňte Kopírovat do výstupního adresáře v okně Vlastnosti na **Kopírovat vždy**. 

1. Na začátek souboru přidejte následující kód do existujícího seznamu `using` příkazů:

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. Do `static void Main(...)` souboru přidejte následující kód:

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. Vyberte **Build**  >  **Build Solution (Sestavit řešení sestavení).**

1. Otevřete okno příkazového řádku a cd do složky, která obsahuje zkompilovaný soubor .exe (například C:\MyProjects\HoloLensDeploymentFix\bin\Debug).

1. Spusťte spustitelný soubor a jako argument příkazového řádku zadejte IP adresu zařízení. (Pokud jste připojení pomocí USB, můžete použít 127.0.0.1, jinak použijte IP adresu zařízení Wi-Fi ip adresu.)  Například HoloLensDeploymentFix 127.0.0.1.

1. Jakmile se nástroj ukončí bez jakýchkoli zpráv (mělo by to trvat jen pár sekund), budete moct nasadit a ladit z Visual Studio 2017 nebo novější verze.  Průběžné používání nástroje není nutné.

Jakmile budou k dispozici, budeme poskytovat další aktualizace.

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>Problémy se spouštěním Microsoft Store a aplikací na HoloLens

> [!NOTE]
> Poslední aktualizace: 4/2 @ 10:00 – Problém se vyřešil.

Při pokusu o spuštění aplikace a Microsoft Store na HoloLens může docházet k problémům. Zjistili jsme, že k problému dochází, když aktualizace aplikací na pozadí nasadí novější verzi balíčků architektury v určitých sekvencích, zatímco jedna nebo více jejich závislých aplikací stále běží. Automatická aktualizace aplikace v tomto případě doručila novou verzi rozhraní .NET Native Framework (verze 10.0.25531 až 10.0.27413), která způsobila, že se aplikace, které běží, správně ne aktualizují pro všechny spuštěné aplikace využívající předchozí verzi rozhraní.  Postup aktualizace architektury je následující:

1. Nový balíček architektury se stáhne z úložiště a nainstaluje.

1. Všechny aplikace starší rozhraní jsou "aktualizované" tak, aby se používá novější verze.

Pokud se krok 2 přeruší před dokončením, nespustí se z nabídky Start žádné aplikace, pro které se novější rozhraní nezaregistruje.  Věříme, že tento problém může mít vliv na libovolnou aplikaci v HoloLens.

Někteří uživatelé oznámili, že problém vyřeší zavření zamykacích aplikací a spuštění jiných aplikací, jako jsou Centrum Feedback, 3D prohlížeč nebo Fotky, ale ve 100 % případů to nefunguje.

Root způsobil, že tento problém nez způsoboval samotnou aktualizaci, ale chybu v operačním systému, která způsobila nesprávnou .NET Native rozhraní. S radostí oznamujeme, že jsme zjistili opravu a vydali jsme aktualizaci (operační systém verze 17763.380), která obsahuje opravu.  

Pokud chcete zjistit, jestli vaše zařízení může aktualizaci přijmout:

1. Přejděte do aplikace Nastavení a otevřete **Update & Security**.

1. Vyberte **Zkontrolovat aktualizace.**

1. Pokud je k dispozici aktualizace na 17763.380, aktualizujte na toto sestavení, abyste obdrželi opravu chyby Zablokuje aplikaci.

1. Po aktualizaci na tuto verzi operačního systému by aplikace měly fungovat podle očekávání.

Stejně jako u každé verze operačního systému HoloLens jsme image FFU také zveřejnili na [webu Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380).

Pokud 29. 3. 2019 2019 vezměme aktualizaci, vydali jsme novou verzi aplikace Microsoft Store UPW. Po aktualizaci verze Storu:

1. Otevřete Store a potvrďte, že se načte.
1. Pomocí gesta bloom otevřete nabídku.
1. Pokuste se otevřít dříve poškozené aplikace.
1. Pokud se pořád nespustila, klepněte a podržte ikonu poškozené aplikace a vyberte odinstalovat.
1. Přeinstalujte tyto aplikace ze Storu.

Pokud se vašemu zařízení pořád nedaří načíst aplikace, můžete pomocí následujícího postupu nainstalovat verzi .NET Native Framework a Runtime přes download center:

1. Stáhněte [si tento soubor ZIP](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) z webu Microsoft Download Center. Při rozbalení se vytvoří dva soubory.  technologie Microsoft .NET.Native.Runtime.1.7.appx a technologie Microsoft .NET.Native.Framework.1.7.appx.

1. Ověřte, že je vaše zařízení odemknuté.  Pokud jste to ještě neudělali, přečtěte si pokyny v [Portál zařízení s Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) článku.

1. Pak se chcete dostat do Portál zařízení s Windows. Doporučujeme to provést přes USB, a to zadáním do http://127.0.0.1:10080 prohlížeče.

1. Jakmile budete mít Portál zařízení s Windows, potřebujeme, abyste tyto dva soubory, které jste stáhli, načtěte bokem. K tomu je potřeba přejít na boční panel vlevo, dokud se dostanete do **části Aplikace** a nevyberte **Aplikace.**

1. Zobrazí se obrazovka podobná následující.  Chcete přejít do části Instalace  aplikace a přejít do místa, kde jste tyto dva soubory APPX rozbalili. Můžete provést pouze jednu po jedné, takže po výběru první z nich klikněte na Přejít v části Nasadit. Pak to proveďte pro druhý soubor APPX.

   ![Portál zařízení s Windows instalace Side-Loaded aplikace](images/20190322-DevicePortal.png)
   
1. V tuto chvíli věříme, že vaše aplikace by měly znovu fungovat a že se můžete dostat také do Storu.

1. V některých případech je nutné před spuštěním ovlivněných aplikací spustit další krok spuštění 3D prohlížeč aplikace. 

Vážíme si vaší trpělivosti, protože jsme tento problém vyřešili, a těšíme se, že ve spolupráci s naší komunitou vytvoříme Mixed Reality prostředí.

### <a name="device-update"></a>Aktualizace zařízení

- 30 sekund po nové aktualizaci může prostředí jednou zmizet. Proveďte gesto **bloomu** a obnovte relaci.

### <a name="visual-studio"></a>Visual Studio

- V [článku Instalace nástrojů](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) najdete nejnovější verzi Visual Studio která se doporučuje pro vývoj pro HoloLens.

- Při nasazování aplikace z Visual Studio do HoloLens se může zobrazit chyba: Požadovanou operaci nelze provést u souboru s otevřeným oddílem **mapovaným uživatelem. (Výjimka na hodnoty HRESULT: 0x800704C8)**. Pokud k tomu dojde, zkuste to znovu a vaše nasazení bude obecně úspěšné.

### <a name="api"></a>rozhraní API

- Pokud aplikace nastaví zaměřovací [bod](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) za uživatelem nebo normální hodnotu na fotoaparát.forward, hologramy se nezobrazí na Záznam hybridní reality fotografiích nebo videích. Dokud se tato chyba ve Windows nevyřešila, pokud aplikace aktivně nastavují fokus, měly by zajistit, aby byla normální rovina nastavená opačně (například normální = -camera.forward). [](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity)

### <a name="xbox-wireless-controller"></a>Bezdrátový ovladač pro Xbox

- Před použitím bezdrátového ovladače Xbox S s HoloLens je nutné ho aktualizovat. Před [pokusem o spárování](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) kontroleru s HoloLens se ujistěte, že jste aktuální.

- Pokud zařízení HoloLens restartujete, když je bezdrátový ovladač pro Xbox připojený, kontroler se automaticky znovu nepřipojí k HoloLens. Světlo tlačítka Průvodce bude pomalu blikat, dokud se kontroler po 3 minutách nesmaří. Pokud chcete kontroler okamžitě znovu připojit, vypněte ho tak, že podržíte tlačítko Guide (Průvodce), dokud se světlo nevypíná. Po opětovném zapnutí kontroleru se kontroler znovu připojí k HoloLens.

- Pokud holoLens vstoupí do pohotovostního režimu, zatímco je bezdrátový ovladač pro Xbox připojený, všechny vstupy na kontroleru probudí HoloLens. Tomu můžete zabránit vypnutím kontroleru, jakmile ho budete používat.

## <a name="known-issues-for-hololens-emulator"></a>Známé problémy s emulátorem HoloLens

- Ne všechny aplikace v Microsoft Store jsou kompatibilní s emulátorem. Například Young Conker a Fragments se v emulátoru nehrají.
- V emulátoru nemůžete použít webovou kameru počítače.
- Funkce Live Preview v Portál zařízení s Windows nefunguje s emulátorem. Stále můžete zachytit Mixed Reality videa a obrázky.
