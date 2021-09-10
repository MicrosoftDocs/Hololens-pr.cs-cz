---
title: známé problémy pro HoloLens (1. generace)
description: udržujte si přehled o našich známých problémech a řešeních, která mohou ovlivnit HoloLens zákazníkům a vývojářům pomocí Unity a Windows portálu zařízení.
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
ms.openlocfilehash: 5c942bae91c7684f2c2d36aca6ace6306b5fed54
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428437"
---
# <a name="known-issues-for-hololens-1st-gen"></a>známé problémy pro HoloLens (1. generace)

toto je aktuální seznam známých problémů HoloLensch zařízení. V případě, že se zobrazuje liché chování, nejprve se podívejte sem. tento seznam se bude udržovat aktualizovaný, protože se objevují nebo nahlásí nové problémy, nebo jako problémy řešené v budoucích HoloLens aktualizacích softwaru.

>[!NOTE]
> - pokud zjistíte problém, který neblokuje, ohlaste ho prosím na zařízení HoloLens prostřednictvím [centra Feedback](hololens-feedback.md).
> - Pokud se problém, na který jste nastavili, blokuje kromě zpětné vazby, uveďte [žádost o podporu](https://aka.ms/hlsupport).


- [známé problémy pro všechny generace HoloLens](#known-issues-for-all-hololens-generations)
- [známé problémy pro HoloLens (1. generace)](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a>známé problémy pro všechny generace HoloLens

### <a name="unity"></a>Unity

- přečtěte si téma [instalace nástrojů](/windows/mixed-reality/install-the-tools) pro nejaktuálnější verzi Unity doporučenou pro HoloLens vývoj.
- známé problémy se službou unity HoloLens Technical Preview jsou popsány ve [HoloLens fórech unity](https://forum.unity3d.com/threads/known-issues.394627/).

### <a name="windows-device-portal"></a>Windows Portál zařízení

- Funkce Live Preview v rámci hybridního zachycení realit může při latenci vykazovat několik sekund.

- Na stránce virtuálního vstupu nejsou funkční gesta a posuvníky v části virtuální gesta. Jejich použití nebude mít žádný vliv. Virtuální klávesnice na stránce virtuálního vstupu funguje správně.

- po povolení režimu vývojářů v Nastavení může trvat několik sekund, než se zapne přepínač, aby se aktivoval portál zařízení.

### <a name="onedrive-camera-upload"></a>nahrávání OneDrive kamery

aplikace OneDrive pro HoloLens nepodporuje automatické nahrávání fotoaparátů pro pracovní nebo školní účty.

Alternativní řešení:

- Pokud je pro vaši firmu životaschopná, je automatické nahrávání kamery podporované u zákaznických účtů Microsoft. k vašemu účet Microsoft se můžete přihlásit navíc k pracovnímu nebo školnímu účtu (aplikace OneDrive podporuje duální přihlášení). z profilu účet Microsoft v rámci OneDrive můžete povolit automatické nahrávání snímků na pozadí.

- pokud nemůžete bezpečně použít účet Microsoft příjemce k automatickému nahrávání vašich fotografií, můžete fotky z OneDrive aplikace nahrát ručně do svého pracovního nebo školního účtu. abyste to mohli udělat, ujistěte se, že jste se přihlásili ke svému pracovnímu nebo školnímu účtu v aplikaci OneDrive. Vyberte **+** tlačítko a zvolte **Upload**. Najděte fotky nebo videa, která chcete nahrát, přechodem na **obrázky >ou kamerou**. Vyberte fotky nebo videa, která chcete nahrát, a pak vyberte tlačítko **otevřít** .

## <a name="known-issues-for-hololens-1st-gen"></a>známé problémy pro HoloLens (1. generace)

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a>nepovedlo se připojit a nasadit HoloLens prostřednictvím Visual Studio

> [!NOTE]
> poslední aktualizace: 8/8 @ 5:23:00-Visual Studio vydala VS 2019 verze 16,2, která obsahuje opravu tohoto problému. Doporučujeme aktualizovat na tuto nejnovější verzi, abyste se vyhnuli výskytu této chyby.

Visual Studio vydala VS 2019 verze 16,2, která obsahuje opravu tohoto problému. Doporučujeme aktualizovat na tuto nejnovější verzi, abyste se vyhnuli výskytu této chyby.

vystavení hlavní příčiny: uživatelé, kteří použili Visual Studio 2015 nebo dřívější verze Visual Studio 2017 k nasazení a ladění aplikací ve svých HoloLens a následné použití nejnovějších verzí Visual Studio 2017 nebo Visual Studio 2019 se stejným HoloLens bude mít vliv. novější verze Visual Studio nasazují novou verzi komponenty, ale soubory ze starší verze zůstanou na zařízení, což způsobí selhání novější verze.  To způsobí následující chybovou zprávu: DEP0100: Ujistěte se, že je na cílovém zařízení povolený vývojářský režim. Nebylo možné získat vývojářskou licenci \<ip\> z důvodu chyby 80004005.

#### <a name="workaround"></a>Alternativní řešení

Náš tým v současné době pracuje na opravě. Mezitím můžete problém obejít pomocí následujících kroků a zrušit nasazení a ladění.  

1. Otevřete sadu Visual Studio.

1. vyberte **soubor**  >  **nový**  >  **Project**.

1. vyberte **Visual C#**  >  **Windows Desktop**  >  **konzolová aplikace (.NET Framework)**.

1. dejte projektu název (například "HoloLensDeploymentFix") a ujistěte se, že je rozhraní nastavené na alespoň .NET Framework 4,5, a pak vyberte **OK**.

1. V Průzkumník řešení klikněte pravým tlačítkem myši na uzel **odkazy** a přidejte následující odkazy (vyberte do části **Procházet** a vyberte **Procházet**):

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > Pokud nemáte 10.0.18362.0 nainstalované, použijte nejnovější verzi, kterou máte.

1. Klikněte pravým tlačítkem na projekt v Průzkumník řešení a vyberte **Přidat**  >  **existující položku**.

1. přejděte do složky C:\Program Files (x86) \ Windows Kits\10\bin\10.0.18362.0\x86 a změňte filtr na **všechny soubory ( \* . \* )**.

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

1. po ukončení nástroje bez jakýchkoli zpráv (tato operace by měla trvat několik sekund) nyní budete moci nasadit a ladit z Visual Studio 2017 nebo novější.  Pokračování v používání tohoto nástroje není nutné.

Poskytneme vám další aktualizace, jakmile budou k dispozici.

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a>problémy se spouštěním Microsoft Store a aplikací na HoloLens

> [!NOTE]
> Poslední aktualizace: 4/2 @ 10 AM-problém byl vyřešen.

při pokusu o spuštění Microsoft Store a aplikací na HoloLens může docházet k problémům. Zjistili jsme, že k tomuto problému dochází, když aktualizace aplikace na pozadí nasadí novější verzi balíčků rozhraní v určitých sekvencích, zatímco jedna nebo více jejich závislých aplikací pořád běží. v tomto případě automatická aktualizace aplikace dodala novou verzi .NET Native frameworku (verze 10.0.25531 na 10.0.27413), protože aplikace, které jsou spuštěné, nejsou správně aktualizované pro všechny spuštěné aplikace, které využívají předchozí verzi rozhraní.  Průběh aktualizace rozhraní Framework je následující:

1. Nový balíček rozhraní se stáhne z úložiště a nainstaluje.

1. Všechny aplikace, které používají starší verze rozhraní, jsou "aktualizované", aby používaly novější verzi.

Pokud je krok 2 přerušen před dokončením, nepůjde spustit všechny aplikace, pro které není zaregistrované novější rozhraní, z nabídky Start.  věříme, že u každé aplikace v HoloLens může být tento problém ovlivněný.

Někteří uživatelé oznámili, že ukončení chyb aplikací a spuštění dalších aplikací, jako je například centrum feedback, prostorové zobrazení nebo fotografie, problém vyřeší, ale nefungují 100% času.

kořen způsobil, že tento problém nebyl příčinou samotné aktualizace, ale chyba v operačním systému, která vedla k nesprávnému zpracování aktualizace .NET Native framework. S radostí oznamujeme, že jsme zjistili opravu a vydali aktualizaci (operační systém verze 17763,380) obsahující opravu.  

Pokud chcete zjistit, jestli zařízení může tuto aktualizaci trvat:

1. přejdete do aplikace Nastavení a otevřete **& Security Update**.

1. Vyberte **Vyhledat aktualizace**.

1. Pokud je k dispozici aktualizace na 17763,380, aktualizujte prosím na toto sestavení, aby se zobrazila chyba zablokování aplikace.

1. Po aktualizaci na tuto verzi operačního systému by aplikace měly fungovat podle očekávání.

kromě HoloLens toho jsme na webu [Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380)publikovali FFU image.

pokud nechcete, aby se aktualizace dala provést, vydali jsme novou verzi aplikace Microsoft Store UWP od 3/29. Po dokončení aktualizované verze Storu:

1. Otevřete Store a potvrďte, že se načte.
1. Pomocí gesta Bloom otevřete nabídku.
1. Došlo k pokusu o otevření dříve přerušených aplikací.
1. Pokud se ještě nedá spustit, klepněte na ikonu poškozené aplikace a vyberte odinstalovat.
1. Přeinstalujte tyto aplikace ze Storu.

pokud vaše zařízení stále nemůže načítat aplikace, můžete bokem verzi rozhraní .NET Native Framework a modulu Runtime prostřednictvím služby stažení softwaru pomocí následujících kroků:

1. Stáhněte si [Tento soubor zip](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) z webu Microsoft Download Center. Rozzipovává vytvoří dva soubory.  Microsoft. NET. Native. Runtime. 1.7. appx a Microsoft. NET. Native. Framework. 1.7. appx.

1. Ověřte prosím, že se vaše zařízení odemklo na vývoj.  pokud jste to ještě neudělali, přečtěte si téma [použití Windowsového portálu pro zařízení](/windows/mixed-reality/using-the-windows-device-portal) .

1. pak se budete chtít dostat na portál zařízení Windows. Naším doporučením je provést tento postup přes USB. to provedete tak, že zadáte http://127.0.0.1:10080 do svého prohlížeče.

1. až budete mít Windows portál zařízení, potřebujeme, abyste na "straněnou zátěž" stáhli dva stažené soubory. K tomu je potřeba přejít na levou stranu, dokud se nedostanete do části **aplikace** a vyberete **aplikace**.

1. Zobrazí se obrazovka, která je podobná následující.  Chcete přejít do oddílu, který říká **instalaci aplikace** , a vyhledat, kde tyto dva soubory appx rozcházejí. Tuto akci můžete provést jen jednou, takže když vyberete první z nich, pak v části Nasazení klikněte na Přejít. Pak to udělejte pro druhý soubor APPX.

   ![Windows Portál zařízení pro instalaci aplikace Side-Loaded.](images/20190322-DevicePortal.png)

1. V tuto chvíli se domníváme, že by vaše aplikace znovu začaly fungovat a že se můžete dostat i do Storu.

1. V některých případech je nutné spustit další krok spuštění aplikace 3D Viewer před tím, než se aplikace spustí.

Vážíme si vaší trpělivosti v tom, že jsme provedli proces, který tento problém vyřešil, a těšíme se na spolupráci s naší komunitou, abychom mohli vytvářet úspěšné hybridní prostředí realit.

### <a name="device-update"></a>Aktualizace zařízení

- 30 sekund po nové aktualizaci může prostředí zmizet jednou za chvíli. Pokud chcete pokračovat v relaci, proveďte prosím gesto **Bloom** .

### <a name="visual-studio"></a>Visual Studio

- přečtěte si téma [instalace nástrojů](/windows/mixed-reality/install-the-tools) pro nejaktuálnější verzi Visual Studio, která se doporučuje pro vývoj HoloLens.

- když nasadíte aplikaci z Visual Studio do HoloLens, může se zobrazit chyba: **požadovanou operaci nejde provést u souboru s otevřeným oddílem mapovaným uživatelem. (Výjimka z HRESULT: 0x800704C8)**. Pokud k tomu dojde, zkuste to znovu a vaše nasazení bude obecně úspěšné.

### <a name="api"></a>rozhraní API

- Pokud aplikace nastaví [zaměření](/windows/mixed-reality/focus-point-in-unity) na uživatele nebo normální na kameru. předá, hologramy se ve hybridním videu nebo videích nezachytí. dokud se tato chyba nevyřešila v Windows, pokud aplikace aktivně nastavují [fokus](/windows/mixed-reality/focus-point-in-unity) , měli byste mít jistotu, že normální plocha je nastavená na opačnou dobu (například normal =-camera. dopředně).

### <a name="xbox-wireless-controller"></a>Adaptér bezdrátové sítě Xbox

- Aby bylo možné používat zařízení s HoloLens, musí být aktualizace bezdrátových řadičů Xbox aktualizované. Než se pokusíte spárovat kontroler s HoloLens, ujistěte se, že máte [aktuální data](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) .

- pokud restartujete HoloLens v době, kdy je adaptér bezdrátové sítě Xbox připojen, kontroler se automaticky znovu nepřipojí k HoloLens. Světlá tlačítko průvodce bude blikat pomalu, dokud se kontrolér nevypne po 3 minutách. Pokud chcete řadič znovu připojit hned, vypněte ho tak, že podržíte tlačítko průvodce, dokud se světlo nevypne. Po opětovném zapnutí kontroleru se znovu připojí k HoloLens.

- pokud váš HoloLens do úsporného režimu dorazí, když je připojen bezdrátový kontroler konzoly Xbox, veškerý vstup na řadiči bude probudit HoloLens. Můžete tomu zabránit tím, že ho vypínáte, až ho budete s použitím dělat.

