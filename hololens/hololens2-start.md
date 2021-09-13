---
title: nastavení HoloLens 2
description: přečtěte si, jak nastavit HoloLens 2 při prvním používání Wi-Fi sítě pomocí účtu Microsoft (MSA) nebo Azure Active Directory (AAD).
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 6/09/2021
keywords: HoloLens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 8f07ed42c873b62b3b4201c2756b55bbb29707d3
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126035850"
---
# <a name="set-up-your-hololens-2"></a>nastavení HoloLens 2

při prvním zapnutí HoloLens vás provedete nastavením zařízení, přihlášením pomocí uživatelského účtu a kalibrací HoloLens na oči.  v této části se seznámíte s úvodním prostředím HoloLens 2.

v další části se dozvíte, jak pracovat s HoloLens a pracovat s hologramy. pokud chcete přejít k tomuto článku, přečtěte si téma [HoloLens 2](hololens2-basic-usage.md).

## <a name="before-you-start"></a>Než začnete

Než začnete, ujistěte se, že máte k dispozici následující:

**Připojení k síti**. k jejímu nastavení budete muset připojit HoloLens k síti. pomocí HoloLens 2 se můžete připojit pomocí Wi-Fi nebo přes síť ethernet (budete potřebovat adaptér USB-C-to-ethernet). Při prvním připojení budete potřebovat otevřenou síť chráněnou heslem, která nevyžaduje navigaci na web nebo použití certifikátů k připojení. [přečtěte si další informace o webech, které HoloLens používá](hololens-offline.md).

**Účet Microsoft**. také se budete muset přihlásit k HoloLens pomocí účet Microsoft (nebo s pracovním účtem, pokud vaše organizace zařízení vlastní). Pokud nemáte účet Microsoft, navštivte [account.Microsoft.com](https://account.microsoft.com) a nastavte si ho zdarma.

**Bezpečný a dobře osvětlený prostor bez Trip nebezpečí**. [Stav a bezpečnostní údaje](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**volitelná pomůcka pro pohodlí** , která byla dodávána s vaším HoloLens, aby vám pomohla lépe se přizpůsobit. [Další informace o přizpůsobení a pohodlí](hololens2-setup.md#adjust-fit).

## <a name="set-up-windows"></a>Instalace Windows

při prvním spuštění HoloLens 2 je prvním úkolem nastavit Windows holografický.  když začnete HoloLens, uslyšíte si hudbu a zobrazí se logo microsoftu.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWGGGk]

<br/>
<img src="images/01-magic-moment.png" width="500px" alt="First screen during first boot">

Zobrazí se Hummingbird kolem.

<img src="images/hummingbird-1.png" width="500px" alt="Hummingbird flying">

Bude postupovat podle vaší ruky.

<img src="images/hummingbird-2.png" width="500px" alt="Hummingbird flying close up">

Zobrazí se tlačítko s logem Microsoftu. stiskněte tlačítko a HoloLens 2 vás provede následujícími kroky:

1. Vyberte svůj jazyk.

    <img src="images/04-language.png" width="500px" alt="Select language">

1. Vyberte oblast.

    <img src="images/05-region.png" width="500px" alt="Select region">

1. kalibrujte HoloLens své oči.  Pokud se rozhodnete přeskočit kalibraci, budete vyzváni k dalšímu přihlášení. 

    1. Nejdřív upravíte své hypervisory.
    
    <img src="images/06-et-corners.png" width="500px" alt="Calibration selection screen">
    
    2. Kalibraci provedete tak, že se podíváte na sadu cílů (označovaných jako Gems). Je to v pořádku, pokud během kalibrace bliká nebo blízko vaše oči, ale nemusíte je postarit na jiné objekty v místnosti nebo na fyzickém místě. HoloLens tento proces využívá k tomu, abyste se dozvěděli o vaší poloze očí, aby mohl lépe vykreslovat svůj holografický svět. 

        <img src="images/07-adjust-eyes.png" width="500px" alt="Adjust for your eyes">

        Po kalibraci se hologramy zobrazí správně i v případě, že se hypervisory posunou na hlavu. Informace o kalibraci jsou uloženy místně na zařízení a nejsou přidruženy k žádným informacím o účtu. Další informace najdete v tématu [data kalibrace a zabezpečení](hololens-calibration.md#calibration-data-and-security).

        <img src="images/calibration-complete.png" width="500px" alt="Calibration is complete">

1. Připojení k internetu (vyberte Wi-Fi nebo připojení k síti ethernet).

     HoloLens automaticky nastaví vaše časové pásmo na základě informací získaných z Wi-Fi sítě. po dokončení instalace můžete časové pásmo změnit pomocí aplikace Nastavení.

    ![Připojení Wi-Fi.](images/11-network.png)

    > [!NOTE] 
    > Pokud budete postupovat po Wi-Fim kroku a později potřebujete přepnout na jinou síť, ale stále v instalačním programu, můžete stisknutím tlačítka **hlasitosti dolů** a **napájení** přejít na tento krok, pokud používáte verzi operačního systému od října 2019 nebo novější. V případě starších verzí možná budete muset [zařízení resetovat](hololens-recovery.md) nebo restartovat v umístění, kde není dostupná síť Wi-Fi, aby se zabránilo automatickému připojení.
    > 
    > všimněte si také, že během HoloLens nastavení je časový limit přihlašovacích údajů 2 minuty. Uživatelské jméno nebo heslo je třeba zadat do dvou minut, jinak bude pole uživatelské jméno automaticky vymazáno.

1. pokud existuje HoloLens 2, bude vyhledávat a používat profil autopilotu. Na této obrazovce není nutná žádná akce.
 
    ![Hledání profilu autopilotu.](images/autopilot-profile-search.png) 

1. Na obrazovce licencování klikněte na **přijmout** .

    ![Windows licenční smlouva.](images/windows-license-agreement.png)

1. Přihlaste se ke svému uživatelskému účtu. Zvolíte si, že **se jedná o pracovní nebo školní vlastnictví** a **vlastní IT**.

    ![Nastavte uživatele.](images/13-device-owner.png)
    - Když zvolíte **Moje práce nebo škola**, přihlásíte se pomocí účtu Azure AD. pokud vaše organizace používá Azure AD Premium a nakonfigurovali automatickou registraci MDM, HoloLens se automaticky zaregistrují v mdm. pokud vaše organizace nepoužívá Azure AD Premium, automatický zápis MDM není k dispozici. v takovém případě je třeba [ručně zaregistrovat HoloLens ve správě zařízení](hololens-enroll-mdm.md#different-ways-to-enroll).

        1. Zadejte informace o účtu organizace.
        1. Přijměte prohlášení o zásadách ochrany osobních údajů a licenční smlouvu s koncovým uživatelem.
        1. Přihlaste se pomocí svých přihlašovacích údajů Azure AD. To se může přesměrovat na přihlašovací stránku vaší organizace.
        1. Pokračujte v nastavování zařízení.

    - Když si vyberete **vlastní IT**, přihlásíte se účet Microsoft. po dokončení instalace můžete [HoloLens ručně zaregistrovat do správy zařízení](hololens-enroll-mdm.md#different-ways-to-enroll).

        1. Zadejte informace o účet Microsoft.
        2. Zadejte svoje heslo. Pokud vaše účet Microsoft vyžaduje [dvoustupňové ověřování (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), dokončete proces ověření.

        
1. Nastavte přihlášení Iris výběrem možnosti **Další**. Přes podobné prostředí se můžete setkat s kalibrací očí. Až se kontrola dokončí, vyberte **Hotovo** . Pokud chcete tento krok obejít, můžete taky vybrat **Přeskočit** .
    
    <img src="images/setup-iris.png" width="500px" alt="Iris setup">

    <img src="images/iris-setup-complete.png" width="500px" alt="Iris setup completion">

     
  
1. Nastavíte PIN kód pro přihlášení k zařízení. Tento kód PIN je specifický pro zařízení. 

    ![Instalační program Windows Hello.](images/setup-windows-hello.png)

    ![nastavení Windows Hello PIN kódu.](images/windows-hello-pin.png)

    ![Windows Hello Instalace byla úspěšná.](images/windows-hello-successful.png) 

    
1. vyberte, jestli se má povolit rozpoznávání řeči na HoloLens 2.

    <img src="images/22-do-more-with-voice.png" width="500px" alt="Enable Cortana">

1. vyberte, jestli se má povolit umístění na HoloLens 2.
    
    <img src="images/setup-location-services.png" width="500px" alt="Enable location services">

1. Vyberte úroveň telemetrie. Pokud můžete, povolte prosím volitelnou telemetrii. tyto informace skutečně pomáhají HoloLens technický tým.

    <img src="images/24-telemetry.png" width="500px" alt="Telemetry level">


1. naučte se používat počáteční gesto na HoloLens 2.

    <img src="images/26-01-startmenu-learning.png" width="500px" alt="Learn how to use the start gesture, image 1">

    <img src="images/26-02-startmenu-learning.png" width="500px" alt="Learn how to use the start gesture, image 2">
    
    > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3Wxng]
    
    Gratulujeme!  Instalace je hotová a Vy jste připraveni použít HoloLens!

## <a name="next-steps"></a>Další kroky

1. začněte pracovat hned se smíšenými realitami a projděte si Windows 10 v HoloLens – podívejte se na **Tipy** aplikaci, kde najdete praktická cvičení pro interakce. Použijte gesto Start, pokud chcete přejít na Start nebo vyslovit příkaz "Přejít na začátek" a vybrat Tipy.

1. kliknutím dole můžete pokračovat v čtení HoloLens 2.

> [!div class="nextstepaction"]
> [Práce s HoloLens 2](hololens2-basic-usage.md)
