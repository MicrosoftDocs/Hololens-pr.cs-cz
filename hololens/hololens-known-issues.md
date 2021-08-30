---
title: Známé problémy HoloLens (1. generace)
description: Udržujte si přehled o našem seznamu známých problémů a alternativních řešení, která mohou ovlivnit HoloLens a vývojáře používající Unity a Windows Portál zařízení.
keywords: řešení potíží, známý problém, nápověda
author: mattzmsft
ms.author: mazeller
ms.date: 6/15/2021
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
ms.openlocfilehash: 5c942bae91c7684f2c2d36aca6ace6306b5fed54
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189286"
---
# <a name="known-issues-for-hololens-1st-gen"></a>Známé problémy HoloLens (1. generace)

Tady je aktuální seznam známých problémů s HoloLens zařízeními. Nejprve zkontrolujte, jestli se vám nesnídí chování. Tento seznam se bude aktualizovat při zjištěných nebo nahlášených nových problémech nebo při řešení problémů v budoucnu HoloLens aktualizací softwaru.

>[!NOTE]
> - Pokud zjistíte problém, který neblokuje, nahlásit ho na svém HoloLens zařízení přes [Centrum Feedback](hololens-feedback.md).
> - Pokud vás váš problém blokuje, kromě vyplnění zpětné vazby uveďte také žádost [o podporu.](https://aka.ms/hlsupport)


- [Známé problémy pro všechny HoloLens generace](#known-issues-for-all-hololens-generations)
- [Známé problémy HoloLens (1. generace)](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a>Známé problémy pro všechny HoloLens generace

### <a name="unity"></a>Unity

- Nejnovější [verzi Unity doporučenou](/windows/mixed-reality/install-the-tools) pro vývoj pro HoloLens najdete v tématu Instalace nástrojů.
- Známé problémy s Unity HoloLens Technical Preview jsou zdokumentované na fórech [HoloLens Unity.](https://forum.unity3d.com/threads/known-issues.394627/)

### <a name="windows-device-portal"></a>Windows Portál zařízení

- Funkce Live Preview v zachytávání Mixed Reality může vykazovat latenci několik sekund.

- Na stránce Virtuální vstup nejsou ovládací prvky Gesture a Scroll v části Virtuální gesta funkční. Jejich použití nebude mít žádný vliv. Virtuální klávesnice na stránce virtuálního vstupu funguje správně.

- Po povolení režimu pro vývojáře Nastavení může trvat několik sekund, než se přepínač zapne, Portál zařízení povoleno.

### <a name="onedrive-camera-upload"></a>OneDrive nahrání fotoaparátu

Aplikace OneDrive pro HoloLens nepodporuje automatické nahrávání z fotoaparátu pro pracovní nebo školní účty.

Alternativní řešení:

- Pokud je pro vaši firmu přijatelné, je u uživatelských účtů Microsoft podporováno automatické nahrávání fotoaparátu. Ke svému pracovnímu nebo školnímu účet Microsoft přihlášení (aplikace OneDrive podporuje duální přihlášení) se můžete přihlásit ke svému pracovnímu nebo školnímu účtu. V profilu účet Microsoft v rámci OneDrive můžete povolit automatické nahrávání fotoaparátů na pozadí.

- Pokud nemůžete bezpečně používat uživatelský účet účet Microsoft automatické nahrávání fotek, můžete fotky ručně nahrát do pracovního nebo školního účtu z OneDrive aplikace. Pokud to chcete udělat, ujistěte se, že jste v aplikaci OneDrive účet. Vyberte tlačítko **+** a zvolte **Upload**. Fotky nebo videa, která chcete nahrát, najdete tak, že přejdete na Obrázky **> fotoaparátu.** Vyberte fotky nebo videa, která chcete nahrát, a pak vyberte **tlačítko** Otevřít.

## <a name="known-issues-for-hololens-1st-gen"></a>Známé problémy HoloLens (1. generace)

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>Nelze se připojit a nasadit do HoloLens prostřednictvím Visual Studio

> [!NOTE]
> Poslední aktualizace: 8/8 @ 17:11 – Visual Studio vydala VS 2019 verze 16.2, která zahrnuje opravu tohoto problému. Doporučujeme provést aktualizaci na tuto nejnovější verzi, abyste se vyhnuli této chybě.

Visual Studio vydali VS 2019 verze 16.2, která zahrnuje opravu tohoto problému. Doporučujeme provést aktualizaci na tuto nejnovější verzi, abyste se vyhnuli této chybě.

Hlavní příčina problému: Uživatelé, kteří použili Visual Studio 2015 nebo dřívější verze Visual Studio 2017 k nasazení a ladění aplikací ve svém HoloLens a následně použili nejnovější verze Visual Studio 2017 nebo Visual Studio 2019 se stejným HoloLens, budou ovlivněni. Novější verze Visual Studio nasadí novou verzi komponenty, ale soubory ze starší verze zůstanou na zařízení, což způsobí selhání novější verze.  To způsobí následující chybovou zprávu: DEP0100: Ujistěte se, že cílové zařízení má povolený vývojářský režim. Nelze získat vývojářské licence ke službě kvůli \<ip\> chybě 80004005.

#### <a name="workaround"></a>Alternativní řešení

Náš tým aktuálně pracuje na opravě. Do té doby můžete pomocí následujících kroků problém obvyřešit a odblokovat nasazení a ladění:  

1. Otevřete sadu Visual Studio.

1. Vyberte **Soubor**  >  **Nový**  >  **Project**.

1. Vyberte **Visual C#**  >  **Windows Desktop Console** App  >  **(.NET Framework)**.

1. Zadejte název projektu (například HoloLensDeploymentFix) a ujistěte se, že je rozhraní nastavené alespoň na .NET Framework 4.5, a pak vyberte **OK.**

1. Klikněte pravým tlačítkem **na** uzel Odkazy v Průzkumník řešení přidejte následující odkazy (vyberte v části **Procházet** a vyberte **Procházet**):

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > Pokud nemáte nainstalovanou verzi 10.0.18362.0, použijte nejnovější verzi, kterou máte.

1. Klikněte pravým tlačítkem na projekt v Průzkumník řešení **a vyberte Přidat** existující  >  **položku.**

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

1. Otevřete okno příkazového řádku a příkaz cd do složky, která obsahuje zkompilovaný soubor .exe (například C:\MyProjects\HoloLensDeploymentFix\bin\Debug).

1. Spusťte spustitelný soubor a jako argument příkazového řádku zadejte IP adresu zařízení. (Pokud jste připojení pomocí USB, můžete použít adresu 127.0.0.1, jinak použijte IP adresu Wi-Fi zařízení.)  Například HoloLensDeploymentFix 127.0.0.1.

1. Jakmile se nástroj ukončí bez jakýchkoli zpráv (mělo by to trvat jenom pár sekund), budete moct nasadit a ladit z Visual Studio 2017 nebo novější verze.  Průběžné používání nástroje není nutné.

Jakmile budou k dispozici, budeme poskytovat další aktualizace.

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>Problémy se spouštěním Microsoft Store a aplikací v HoloLens

> [!NOTE]
> Poslední aktualizace: 4/2 @ 10:00 – Problém se vyřešil.

Při pokusu o spuštění aplikace a Microsoft Store v HoloLens může docházet k problémům. Zjistili jsme, že k problému dochází, když aktualizace aplikací na pozadí nasadí novější verzi balíčků architektury v určitých sekvencích, zatímco jedna nebo více jejich závislých aplikací stále běží. V tomto případě automatická aktualizace aplikace doručila novou verzi rozhraní .NET Native Framework (verze 10.0.25531 až 10.0.27413) způsobila, že aplikace, které běží, se správně ne aktualizují pro všechny spuštěné aplikace využívající předchozí verzi rozhraní.  Postup aktualizace architektury je následující:

1. Nový balíček architektury se stáhne z úložiště a nainstaluje.

1. Všechny aplikace starší architektury jsou "aktualizované" tak, aby se používá novější verze.

Pokud se krok 2 před dokončením přeruší, nespustí se z nabídky Start žádné aplikace, pro které se novější rozhraní nezaregistruje.  Věříme, že tento problém může HoloLens všechny aplikace v této oblasti.

Někteří uživatelé oznámili, že zavírat zamkřené aplikace a spustit jiné aplikace, jako jsou Centrum Feedback, 3D prohlížeč nebo Fotky, problém vyřeší. To ale ve 100 % případů nefunguje.

Root způsobil, že tento problém nez způsoboval samotnou aktualizaci, ale chybu v operačním systému, která způsobila nesprávnou .NET Native rozhraní. S radostí oznamujeme, že jsme zjistili opravu a vydali jsme aktualizaci (operační systém verze 17763.380), která obsahuje opravu.  

Pokud chcete zjistit, jestli vaše zařízení může aktualizaci přijmout:

1. Přejděte do aplikace Nastavení a **otevřete Update & Security**.

1. Vyberte **Zkontrolovat aktualizace.**

1. Pokud je k dispozici aktualizace na 17763.380, aktualizujte na toto sestavení, abyste obdrželi opravu chyby app hang.

1. Po aktualizaci na tuto verzi operačního systému by aplikace měly fungovat podle očekávání.

Kromě toho jsme stejně jako u každé HoloLens operačního systému zveřejnili image FFU na [webu Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380).

Pokud 29. 3. 2019 2019 2019 chystetá verze aplikace pro UPW, kterou jsme Microsoft Store 29. 2019. Po aktualizaci verze Storu:

1. Otevřete Store a potvrďte, že se načte.
1. Pomocí gesta bloom otevřete nabídku.
1. Pokuste se otevřít dříve poškozené aplikace.
1. Pokud se pořád nespustila, klepněte a podržte ikonu poškozené aplikace a vyberte odinstalovat.
1. Přeinstalujte tyto aplikace ze Storu.

Pokud se vašemu zařízení pořád nedaří načíst aplikace, můžete pomocí následujícího postupu nainstalovat verzi rozhraní .NET Native Framework a Modulu runtime prostřednictvím služby Stažení softwaru:

1. Stáhněte [si tento soubor ZIP](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) z webu Microsoft Download Center. Při rozbalení se vytvoří dva soubory.  technologie Microsoft .NET.Native.Runtime.1.7.appx a technologie Microsoft .NET.Native.Framework.1.7.appx.

1. Ověřte, že je vaše zařízení odemknuté.  Pokud jste to ještě neudělali, přečtěte si pokyny v [Windows Portál zařízení](/windows/mixed-reality/using-the-windows-device-portal) článku.

1. Pak se chcete dostat do Windows Portál zařízení. Doporučujeme to provést přes USB, a to zadáním do http://127.0.0.1:10080 prohlížeče.

1. Jakmile budete mít Windows Portál zařízení, potřebujeme, abyste tyto dva soubory, které jste stáhli, načtěte bokem. K tomu je potřeba přejít na levý boční panel, dokud se dostanete do **části Aplikace** a nevyberte **Aplikace.**

1. Zobrazí se obrazovka podobná následující.  Chcete přejít do části Instalace  aplikace a přejít na místo, kde jste tyto dva soubory APPX rozbalili. Můžete provést pouze jednu po jedné, takže po výběru první z nich klikněte v části Nasadit na Přejít. Pak to proveďte pro druhý soubor APPX.

   ![Windows Portál zařízení nainstalovat Side-Loaded aplikaci.](images/20190322-DevicePortal.png)

1. V tuto chvíli věříme, že vaše aplikace by měly znovu fungovat a že se můžete dostat také do Storu.

1. V některých případech je nutné před spuštěním ovlivněných aplikací spustit další krok spuštění 3D prohlížeč aplikace.

Vážíme si vaší trpělivosti, protože jsme prošli procesem řešení tohoto problému, a těšíme se, že budeme s naší komunitou dál pracovat na vytváření úspěšných Mixed Reality prostředí.

### <a name="device-update"></a>Aktualizace zařízení

- 30 sekund po nové aktualizaci může prostředí jednou zmizet. Proveďte gesto **bloomu** a obnovte relaci.

### <a name="visual-studio"></a>Visual Studio

- Aktuální [verzi nástroje najdete](/windows/mixed-reality/install-the-tools) v tématu Instalace nástrojů Visual Studio která se doporučuje HoloLens vývoji.

- Při nasazování aplikace z Visual Studio do HoloLens se může zobrazit chyba: Požadovanou operaci nelze provést u souboru s otevřeným oddílem **mapovaným uživatelem. (Výjimka na hodnoty HRESULT: 0x800704C8)**. Pokud k tomu dojde, zkuste to znovu a vaše nasazení bude obecně úspěšné.

### <a name="api"></a>rozhraní API

- Pokud aplikace nastaví zaměřovací [bod](/windows/mixed-reality/focus-point-in-unity) za uživatelem nebo normální hodnotu na fotoaparát.forward, hologramy se nezobrazí na Záznam hybridní reality fotografiích nebo videích. Dokud se tato chyba v nástroji Windows nevyřešila, měly by aplikace aktivně nastavit fokus, aby se zajistilo, že je normální rovina nastavená proti směru fotoaparátu (například normální = -camera.forward). [](/windows/mixed-reality/focus-point-in-unity)

### <a name="xbox-wireless-controller"></a>Bezdrátový ovladač pro Xbox

- Před použitím bezdrátového ovladače Xbox S je nutné ho aktualizovat s HoloLens. Před [pokusem o spárování kontroleru](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) s řadičem domény zkontrolujte, že jste HoloLens.

- Pokud při připojení bezdrátového HoloLens Xbox restartujete počítač, kontroler se automaticky znovu nepřipojí k HoloLens. Světlo tlačítka Guide (Průvodce) bude pomalu blikat, dokud se kontroler po 3 minutách nesvítí. Pokud chcete kontroler okamžitě znovu připojit, vypněte ho tak, že podržíte tlačítko Guide (Průvodce), dokud se světlo nevypíná. Po opětovném zapnutí kontroleru se kontroler znovu připojí k HoloLens.

- Pokud se HoloLens bezdrátového ovladače Pro Xbox připojí do pohotovostního režimu, všechny vstupy na kontroleru probudí HoloLens. Tomu můžete zabránit vypnutím kontroleru, až ho budete používat.

