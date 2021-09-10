---
title: Nastavení HoloLens 2
description: Zjistěte, jak poprvé nastavit HoloLens 2 přes Wi-Fi pomocí účtu Microsoft (MSA) nebo Azure Active Directory (AAD).
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 6/09/2021
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 8f07ed42c873b62b3b4201c2756b55bbb29707d3
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428608"
---
# <a name="set-up-your-hololens-2"></a>Nastavení HoloLens 2

Při prvním zapnutí zařízení HoloLens provedete nastavením zařízení, přihlášením pomocí uživatelského účtu a HoloLens na pohled.  Tato část vás provede počátečním HoloLens 2.

V další části se dozvíte, jak pracovat s hologramy HoloLens s hologramy. Pokud chcete přeskočit na tento článek, podívejte se na [článek o přechodu HoloLens 2](hololens2-basic-usage.md).

## <a name="before-you-start"></a>Než začnete

Než začnete, ujistěte se, že máte k dispozici následující:

**Síťové připojení**. Abyste ho nastavili, budete HoloLens k síti. S HoloLens 2 se můžete připojit pomocí Wi-Fi nebo pomocí ethernetu (budete potřebovat adaptér USB-C-to-Ethernet). Při prvním připojení budete potřebovat otevřenou síť nebo síť chráněnou heslem, která nevyžaduje přechod na web ani používání certifikátů pro připojení. [Přečtěte si další informace o webech, HoloLens používají](hololens-offline.md).

**A účet Microsoft**. Budete se také muset přihlásit k účtu HoloLens pomocí účet Microsoft (nebo pomocí pracovního účtu, pokud vaše organizace vlastní zařízení). Pokud nemáte vlastní účet Microsoft, přejděte na [account.microsoft.com](https://account.microsoft.com) a nastavte si ho zdarma.

**Bezpečný a dobře rozsvícený prostor bez nebezpečí při vyjetí.** [Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**Volitelné příslušenství pro komfort,** které se HoloLens, které vám pomůže s co nejpohodlnějším fitem. [Další informace o fitu a komfortu.](hololens2-setup.md#adjust-fit)

## <a name="set-up-windows"></a>Instalace Windows

Při prvním spuštění úlohy HoloLens 2 je vaším prvním úkolem nastavení Windows Holographic.  Když spustíte aplikaci HoloLens, uslyšíte hudbu a uvidíte logo Microsoftu.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWGGGk]

<br/>
<img src="images/01-magic-moment.png" width="500px" alt="First screen during first boot">

Uvidíte, jak kolem sebe letí hrmingbird.

<img src="images/hummingbird-1.png" width="500px" alt="Hummingbird flying">

Bude vás sledovat.

<img src="images/hummingbird-2.png" width="500px" alt="Hummingbird flying close up">

Zobrazí se tlačítko s logem Microsoftu. Stiskněte tlačítko a HoloLens 2 vás provede následujícími kroky:

1. Vyberte svůj jazyk.

    <img src="images/04-language.png" width="500px" alt="Select language">

1. Vyberte svou oblast.

    <img src="images/05-region.png" width="500px" alt="Select region">

1. Nakalibrovat HoloLens do očí.  Pokud se rozhodnete přeskočit přeskočení, při příštím přihlášení se zobrazí výzva. 

    1. Nejprve upravíte vizuátor.
    
    <img src="images/06-et-corners.png" width="500px" alt="Calibration selection screen">
    
    2. Při nakalibrování se podíváte na sadu cílů (označované jako gemy). Je v pořádku, když během chouly blikne nebo zavřete oči, ale snažte se nekoukat na jiné objekty v místnosti nebo fyzickém prostoru. HoloLens tento proces používá k tomu, aby se dozvěděli o pozici oka, aby bylo možné lépe vykreslit holografický svět. 

        <img src="images/07-adjust-eyes.png" width="500px" alt="Adjust for your eyes">

        Po dokončení se hologramy zobrazí správně, i když se visor posune na vaší hlavy. Informace o výuce se ukládají místně v zařízení a nejsou přidružené k žádným informacím o účtu. Další informace najdete v tématu [o ochraně osobních údajů a zabezpečení.](hololens-calibration.md#calibration-data-and-security)

        <img src="images/calibration-complete.png" width="500px" alt="Calibration is complete">

1. Připojení k internetu (vyberte Wi-Fi nebo ethernetové připojení).

     HoloLens časové pásmo automaticky na základě informací získaných z Wi-Fi sítě. Po dokončení instalace můžete změnit časové pásmo pomocí Nastavení aplikace.

    ![Připojení na Wi-Fi.](images/11-network.png)

    > [!NOTE] 
    > Pokud postupíte v kroku Wi-Fi a později budete muset přepnout na jinou síť, zatímco  jste stále v nastavení, můžete se k tomuto kroku vrátit stisknutím tlačítek Snížení objemu a napájení současně, pokud používáte verzi operačního systému z října 2019 nebo novější.  U starších verzí možná [](hololens-recovery.md) budete muset resetovat zařízení nebo ho restartovat v umístění, kde není dostupná síť Wi-Fi, aby se zabránilo jeho automatickému připojení.
    > 
    > Upozorňujeme také, že během HoloLens instalace došlo k časovému limitu přihlašovacích údajů dvou minut. Uživatelské jméno a heslo je potřeba zadat do dvou minut, jinak se pole uživatelského jména automaticky vymazat.

1. HoloLens 2 vyhledá a použije profil Autopilot, pokud existuje. Na této obrazovce není potřeba žádná akce.
 
    ![Vyhledávání profilu Autopilotu.](images/autopilot-profile-search.png) 

1. Na **obrazovce** licencování klikněte na Přijmout.

    ![Windows licenční smlouvu.](images/windows-license-agreement.png)

1. Přihlaste se ke svému uživatelskému účtu. Zvolíte si, jestli je můj **pracovní nebo** školní vlastnit a já **ho vlastním.**

    ![Nastavte uživatele.](images/13-device-owner.png)
    - Když zvolíte **Možnost Můj pracovní nebo školní účet** vlastní , přihlásíte se pomocí účtu Azure AD. Pokud vaše organizace používá Azure AD Premium a nakonfiguroval automatickou registraci MDM, HoloLens se automaticky zaregistruje do MDM. Pokud vaše organizace tuto funkci Azure AD Premium, automatická registrace MDM není dostupná. V takovém případě je potřeba ručně [zaregistrovat HoloLens ve správě zařízení.](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. Zadejte informace o účtu organizace.
        1. Přijměte prohlášení o zásadách ochrany osobních údajů a licenční smlouvu s koncovým uživatelem.
        1. Přihlaste se pomocí svých přihlašovacích údajů azure AD. To se může přesměrovat na přihlašovací stránku vaší organizace.
        1. Pokračujte v nastavování zařízení.

    - Když zvolíte **Možnost vlastnit**, přihlásíte se pomocí účet Microsoft. Po dokončení instalace můžete ručně zaregistrovat [HoloLens ve správě zařízení.](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. Zadejte své účet Microsoft údaje.
        2. Zadejte svoje heslo. Pokud vaše účet Microsoft vyžaduje [dvoukrokové ověřování ,](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)dokončete proces ověřování.

        
1. Na nastavení přihlášení Iris vyberte **Další.** Projdete si podobné prostředí jako při pohledu. Po **dokončení** kontroly vyberte Hotovo. Tento krok můžete také **obejít** výběrem možnosti Přeskočit.
    
    <img src="images/setup-iris.png" width="500px" alt="Iris setup">

    <img src="images/iris-setup-complete.png" width="500px" alt="Iris setup completion">

     
  
1. Pro přihlášení k zařízení si nasnídáte KÓD PIN. Tento PIN kód je specifický pro zařízení. 

    ![Nastavení Windows Hello.](images/setup-windows-hello.png)

    ![Nastavení Windows Hello PIN kódu](images/windows-hello-pin.png)

    ![Windows Hello Instalace byla úspěšná.](images/windows-hello-successful.png) 

    
1. Vyberte, jestli chcete povolit řeč na HoloLens 2.

    <img src="images/22-do-more-with-voice.png" width="500px" alt="Enable Cortana">

1. Vyberte, jestli chcete povolit umístění na HoloLens 2.
    
    <img src="images/setup-location-services.png" width="500px" alt="Enable location services">

1. Vyberte úroveň telemetrie. Pokud můžete, povolte volitelnou telemetrii. Tyto informace ve skutečnosti pomáhají HoloLens týmu.

    <img src="images/24-telemetry.png" width="500px" alt="Telemetry level">


1. Přečtěte si, jak používat počáteční gesto na HoloLens 2.

    <img src="images/26-01-startmenu-learning.png" width="500px" alt="Learn how to use the start gesture, image 1">

    <img src="images/26-02-startmenu-learning.png" width="500px" alt="Learn how to use the start gesture, image 2">
    
    > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3Wxng]
    
    Gratulujeme!  Nastavení je hotové a jste připraveni k použití HoloLens!

## <a name="next-steps"></a>Další kroky

1. Začněte ihned pracovat s Mixed Reality a procházením Windows 10 na HoloLens – podívejte se na aplikaci **Tipy,** která vám pomůže s ručními kurzy. Pomocí gesta spuštění přejděte na Start nebo řekněte "Přejít na start" a vyberte Tipy.

1. Klikněte níže a pokračujte ve čtení o tom, jak se dostat HoloLens 2.

> [!div class="nextstepaction"]
> [Práce s HoloLens 2](hololens2-basic-usage.md)
