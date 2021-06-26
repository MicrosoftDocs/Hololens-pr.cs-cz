---
title: Známé problémy HoloLens (1. generace)
description: Udržujte si přehled o našich známých problémech a řešeních, která mohou mít vliv na zákazníky a vývojáře s využitím Unity a na portále zařízení s Windows.
keywords: řešení potíží, známý problém, help
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
ms.openlocfilehash: 558eba8c2260b24a228e957b27927d508a077ec4
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923546"
---
# <a name="known-issues-for-hololens-1st-gen"></a>Známé problémy HoloLens (1. generace)

Zde je aktuální seznam známých problémů pro zařízení HoloLens. V případě, že se zobrazuje liché chování, nejprve se podívejte sem. Tento seznam se bude udržovat aktualizovaný, protože se objevují nebo nahlásí nové problémy, nebo jako problémy řešené v budoucích aktualizacích softwaru HoloLens.

>[!NOTE]
> - Pokud zjistíte problém, který se neblokuje, ohlaste ho prosím na zařízení HoloLens prostřednictvím [centra Feedback](hololens-feedback.md).
> - Pokud se problém, na který jste nastavili, blokuje kromě zpětné vazby, uveďte [žádost o podporu](https://aka.ms/hlsupport).


- [Známé problémy pro všechny generace HoloLens](#known-issues-for-all-hololens-generations)
- [Známé problémy HoloLens (1. generace)](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a>Známé problémy pro všechny generace HoloLens

### <a name="unity"></a>Unity

- Přečtěte si téma [Instalace nástrojů](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) pro nejaktuálnější verzi Unity, doporučená pro vývoj pro HoloLens.
- Známé problémy s nástrojem Unity HoloLens Technical Preview jsou popsány ve [fórech Unity pro HoloLens](https://forum.unity3d.com/threads/known-issues.394627/).

### <a name="windows-device-portal"></a>Portál zařízení Windows

- Funkce Live Preview v rámci hybridního zachycení realit může při latenci vykazovat několik sekund.

- Na stránce virtuálního vstupu nejsou funkční gesta a posuvníky v části virtuální gesta. Jejich použití nebude mít žádný vliv. Virtuální klávesnice na stránce virtuálního vstupu funguje správně.

- Po povolení režimu vývojářů v nastavení může trvat několik sekund, než se zapne přepínač, aby se aktivoval portál zařízení.

### <a name="onedrive-camera-upload"></a>Nahrávání kamery na OneDrivu

Aplikace OneDrive pro HoloLens nepodporuje automatické nahrávání fotoaparátů pro pracovní nebo školní účty.

Alternativní řešení:

- Pokud je pro vaši firmu životaschopná, je automatické nahrávání kamery podporované u zákaznických účtů Microsoft. Můžete se přihlásit k účet Microsoft kromě pracovního nebo školního účtu (aplikace OneDrive podporuje duální přihlášení). Z profilu účet Microsoft v rámci OneDrivu můžete povolit automatické nahrávání snímků na pozadí.

- Pokud nemůžete bezpečně použít účet Microsoft příjemce k automatickému nahrávání vašich fotografií, můžete fotky do svého pracovního nebo školního účtu ručně nahrát z aplikace OneDrive. Abyste to mohli udělat, ujistěte se, že jste se přihlásili ke svému pracovnímu nebo školnímu účtu v aplikaci OneDrive. Vyberte **+** tlačítko a zvolte **nahrát**. Najděte fotky nebo videa, která chcete nahrát, přechodem na **obrázky >ou kamerou**. Vyberte fotky nebo videa, která chcete nahrát, a pak vyberte tlačítko **otevřít** .

## <a name="known-issues-for-hololens-1st-gen"></a>Známé problémy HoloLens (1. generace)

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>Nejde se připojit a nasadit na HoloLens prostřednictvím sady Visual Studio.

> [!NOTE]
> Poslední aktualizace: 8/8 @ 5:23:00-sada Visual Studio vydala VS 2019 verze 16,2, která zahrnuje opravu tohoto problému. Doporučujeme aktualizovat na tuto nejnovější verzi, abyste se vyhnuli výskytu této chyby.

Sada Visual Studio vydala VS 2019 verze 16,2, která obsahuje opravu tohoto problému. Doporučujeme aktualizovat na tuto nejnovější verzi, abyste se vyhnuli výskytu této chyby.

Vystavení hlavní příčiny: uživatelé, kteří použili sadu Visual Studio 2015 nebo dřívější vydání sady Visual Studio 2017 pro nasazení a ladění aplikací na svém HoloLens a následné použití nejnovějších verzí sady Visual Studio 2017 nebo Visual Studio 2019 se stejnou HoloLens bude ovlivněn. Novější verze sady Visual Studio nasazují novou verzi komponenty, ale soubory ze starší verze zůstanou na zařízení, což způsobí selhání novější verze.  To způsobí následující chybovou zprávu: DEP0100: Ujistěte se, že je na cílovém zařízení povolený vývojářský režim. Nebylo možné získat vývojářskou licenci \<ip\> z důvodu chyby 80004005.

#### <a name="workaround"></a>Alternativní řešení

Náš tým v současné době pracuje na opravě. Mezitím můžete problém obejít pomocí následujících kroků a zrušit nasazení a ladění.  

1. Otevřete sadu Visual Studio.

1. Vyberte **soubor**  >  **Nový**  >  **projekt**.

1. Vyberte **Visual C#**  >  **Windows Desktop**  >  **Console aplikace (.NET Framework)**.

1. Dejte projektu název (například "HoloLensDeploymentFix") a ujistěte se, že je rozhraní nastavené na alespoň .NET Framework 4,5, a pak vyberte **OK**.

1. V Průzkumník řešení klikněte pravým tlačítkem myši na uzel **odkazy** a přidejte následující odkazy (vyberte do části **Procházet** a vyberte **Procházet**):

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > Pokud nemáte 10.0.18362.0 nainstalované, použijte nejnovější verzi, kterou máte.

1. Klikněte pravým tlačítkem na projekt v Průzkumník řešení a vyberte **Přidat**  >  **existující položku**.

1. Přejděte do složky C:\Program Files (x86) \Windows Kits\10\bin\10.0.18362.0\x86 a změňte filtr na **všechny soubory ( \* . \* )**.

1. Vyberte SirepClient.dll i SshClient.dll a vyberte **Přidat**.

1. Vyhledejte a vyberte oba soubory v Průzkumník řešení (měly by být v dolní části seznamu souborů) a změňte možnost **Kopírovat do výstupního adresáře** v okně **vlastnosti** na možnost **vždy kopírovat**.

1. V horní části souboru přidejte do existujícího seznamu `using` příkazů následující:

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. Uvnitř `static void Main(...)` přidejte následující kód:

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. Vyberte   >  **řešení** sestavení sestavení.

1. Otevřete okno příkazového řádku a disk CD do složky, která obsahuje zkompilovaný soubor .exe (například C:\MyProjects\HoloLensDeploymentFix\bin\Debug).

1. Spusťte spustitelný soubor a zadejte IP adresu zařízení jako argument příkazového řádku. (Pokud jste připojení pomocí USB, můžete použít 127.0.0.1, jinak použít Wi-Fi IP adresu zařízení.)  Například "HoloLensDeploymentFix 127.0.0.1".

1. Po ukončení nástroje bez jakýchkoli zpráv (Tato operace by měla trvat několik sekund) nyní budete moci nasadit a ladit ze sady Visual Studio 2017 nebo novější.  Pokračování v používání tohoto nástroje není nutné.

Poskytneme vám další aktualizace, jakmile budou k dispozici.

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>Problémy se spouštěním Microsoft Store a aplikací na HoloLens

> [!NOTE]
> Poslední aktualizace: 4/2 @ 10 AM-problém byl vyřešen.

Při pokusu o spuštění Microsoft Store a aplikací na HoloLens může docházet k problémům. Zjistili jsme, že k tomuto problému dochází, když aktualizace aplikace na pozadí nasadí novější verzi balíčků rozhraní v určitých sekvencích, zatímco jedna nebo více jejich závislých aplikací pořád běží. V tomto případě Automatická aktualizace aplikace dodala novou verzi .NET Native Frameworku (verze 10.0.25531 na 10.0.27413), protože aplikace, které jsou spuštěné, nejsou správně aktualizované pro všechny spuštěné aplikace, které využívají předchozí verzi rozhraní.  Průběh aktualizace rozhraní Framework je následující:

1. Nový balíček rozhraní se stáhne z úložiště a nainstaluje.

1. Všechny aplikace, které používají starší verze rozhraní, jsou "aktualizované", aby používaly novější verzi.

Pokud je krok 2 přerušen před dokončením, nepůjde spustit všechny aplikace, pro které není zaregistrované novější rozhraní, z nabídky Start.  Domníváme se, že se tento problém týká jakékoli aplikace na HoloLens.

Někteří uživatelé oznámili, že ukončení chyb aplikací a spuštění dalších aplikací, jako je například centrum feedback, prostorové zobrazení nebo fotografie, problém vyřeší, ale nefungují 100% času.

Kořen způsobil, že tento problém nebyl příčinou samotné aktualizace, ale chyba v operačním systému, která vedla k nesprávnému zpracování aktualizace .NET Native Framework. S radostí oznamujeme, že jsme zjistili opravu a vydali aktualizaci (operační systém verze 17763,380) obsahující opravu.  

Pokud chcete zjistit, jestli zařízení může tuto aktualizaci trvat:

1. Přejít do aplikace nastavení a otevřete **& zabezpečení aktualizace**.

1. Vyberte **Vyhledat aktualizace**.

1. Pokud je k dispozici aktualizace na 17763,380, aktualizujte prosím na toto sestavení, aby se zobrazila chyba zablokování aplikace.

1. Po aktualizaci na tuto verzi operačního systému by aplikace měly fungovat podle očekávání.

Kromě toho jsme na [webu Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380)publikovali image FFU, a to stejně jako u každé verze systému HoloLens.

Pokud nechcete, aby se aktualizace dala provést, vydali jsme novou verzi aplikace Microsoft Store UWP od 3/29. Po dokončení aktualizované verze Storu:

1. Otevřete Store a potvrďte, že se načte.
1. Pomocí gesta Bloom otevřete nabídku.
1. Došlo k pokusu o otevření dříve přerušených aplikací.
1. Pokud se ještě nedá spustit, klepněte na ikonu poškozené aplikace a vyberte odinstalovat.
1. Přeinstalujte tyto aplikace ze Storu.

Pokud vaše zařízení stále nemůže načítat aplikace, můžete bokem verzi rozhraní .NET Native Framework a modulu runtime prostřednictvím služby Stažení softwaru pomocí následujících kroků:

1. Stáhněte si [Tento soubor zip](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) z webu Microsoft Download Center. Rozzipovává vytvoří dva soubory.  Microsoft. NET. Native. Runtime. 1.7. appx a Microsoft. NET. Native. Framework. 1.7. appx.

1. Ověřte prosím, že se vaše zařízení odemklo na vývoj.  Pokud jste to ještě neudělali, přečtěte si pokyny v tématu [použití portálu pro zařízení s Windows](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) .

1. Pak se budete chtít dostat na portál zařízení Windows. Naším doporučením je provést tento postup přes USB. to provedete tak, že zadáte http://127.0.0.1:10080 do svého prohlížeče.

1. Až budete mít portál zařízení se systémem Windows, potřebujeme, abyste na "straněnou zátěž" stáhli dva stažené soubory. K tomu je potřeba přejít na levou stranu, dokud se nedostanete do části **aplikace** a vyberete **aplikace**.

1. Zobrazí se obrazovka, která je podobná následující.  Chcete přejít do oddílu, který říká **instalaci aplikace** , a vyhledat, kde tyto dva soubory appx rozcházejí. Tuto akci můžete provést jen jednou, takže když vyberete první z nich, pak v části Nasazení klikněte na Přejít. Pak to udělejte pro druhý soubor APPX.

   ![Portál zařízení Windows pro instalaci aplikace Side-Loaded](images/20190322-DevicePortal.png)

1. V tuto chvíli se domníváme, že by vaše aplikace znovu začaly fungovat a že se můžete dostat i do Storu.

1. V některých případech je nutné spustit další krok spuštění aplikace 3D Viewer před tím, než se aplikace spustí.

Vážíme si vaší trpělivosti v tom, že jsme provedli proces, který tento problém vyřešil, a těšíme se na spolupráci s naší komunitou, abychom mohli vytvářet úspěšné hybridní prostředí realit.

### <a name="device-update"></a>Aktualizace zařízení

- 30 sekund po nové aktualizaci může prostředí zmizet jednou za chvíli. Pokud chcete pokračovat v relaci, proveďte prosím gesto **Bloom** .

### <a name="visual-studio"></a>Visual Studio

- Přečtěte si téma [Instalace nástrojů](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) pro nejaktuálnější verzi sady Visual Studio, která se doporučuje pro vývoj pro HoloLens.

- Když nasadíte aplikaci ze sady Visual Studio do HoloLens, může se zobrazit chyba: **požadovanou operaci nelze provést u souboru s otevřeným oddílem mapovaným uživatelem. (Výjimka z HRESULT: 0x800704C8)**. Pokud k tomu dojde, zkuste to znovu a vaše nasazení bude obecně úspěšné.

### <a name="api"></a>rozhraní API

- Pokud aplikace nastaví [zaměření](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) na uživatele nebo normální na kameru. předá, hologramy se ve hybridním videu nebo videích nezachytí. Dokud se tato chyba v systému Windows nevyřešila, v případě, že aplikace aktivně nastavují [fokus](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) , by měly mít jistotu, že normální plocha je nastavená proti kameře (například Normal =-Camera. dopředné).

### <a name="xbox-wireless-controller"></a>Adaptér bezdrátové sítě Xbox

- Bezdrátový adaptér Xbox se musí aktualizovat předtím, než bude možné ho použít s HoloLens. Než se pokusíte spárovat kontroler s HoloLens, ujistěte se, že máte [aktuální data](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) .

- Pokud restartujete svůj HoloLens a adaptér bezdrátové sítě Xbox je připojený, kontroler se automaticky znovu nepřipojí k HoloLens. Světlá tlačítko průvodce bude blikat pomalu, dokud se kontrolér nevypne po 3 minutách. Pokud chcete řadič znovu připojit hned, vypněte ho tak, že podržíte tlačítko průvodce, dokud se světlo nevypne. Po opětovném zapnutí kontroleru se znovu připojí k HoloLens.

- Pokud váš HoloLens dorazí do úsporného režimu, zatímco je připojený bezdrátový kontroler konzoly Xbox, veškerý vstup na řadiči bude probudit HoloLens. Můžete tomu zabránit tím, že ho vypínáte, až ho budete s použitím dělat.

