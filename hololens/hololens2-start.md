---
title: Nastavení HoloLens 2
description: Zjistěte, jak poprvé nastavit HoloLens 2 v síti Wi-Fi pomocí účtu Microsoft (MSA) nebo Azure Active Directory (AAD).
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
ms.openlocfilehash: 0d087037e94bcaed2cd79d9cff77ed3039919a09
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923713"
---
# <a name="set-up-your-hololens-2"></a>Nastavení HoloLens 2

Při prvním zapnutí HoloLens vás provede nastavením zařízení, přihlášením pomocí uživatelského účtu a zkalibrací HoloLensu do očí.  Tato část vás provede počátečním nastavením HoloLens 2.

V další části se dozvíte, jak pracovat s HoloLens a pracovat s hologramy. Pokud chcete přeskočit na tento článek, podívejte se na článek [Sesíť kolem HoloLens 2.](hololens2-basic-usage.md)

## <a name="before-you-start"></a>Než začnete

Než začnete, ujistěte se, že máte k dispozici následující:

**Síťové připojení**. Abyste ho nastavili, budete muset holoLens připojit k síti. S HoloLens 2 se můžete připojit pomocí Wi-Fi nebo pomocí ethernetu (budete potřebovat adaptér USB-C-to-Ethernet). Při prvním připojení budete potřebovat otevřenou síť nebo síť chráněnou heslem, která nevyžaduje přechod na web ani používání certifikátů pro připojení. [Přečtěte si další informace o webech, které HoloLens používá.](hololens-offline.md)

**A účet Microsoft**. Budete se také muset přihlásit k HoloLens pomocí účet Microsoft (nebo pomocí pracovního účtu, pokud vaše organizace vlastní zařízení). Pokud nemáte vlastní účet Microsoft, přejděte na [account.microsoft.com](https://account.microsoft.com) a nastavte si ho zdarma.

**Bezpečný a dobře rozsvícený prostor bez nebezpečí při vyjetí.** [Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**Volitelné příslušenství pro komfort,** které se dodá s holoLens, vám pomůže s co nejpohodlnějším fitem. [Další informace o fitu a komfortu.](hololens2-setup.md#adjust-fit)

## <a name="set-up-windows"></a>Instalace Windows

Při prvním spuštění HoloLens 2 je vaším prvním úkolem nastavit Windows Holographic.  Když spustíte HoloLens, uslyšíte hudbu a uvidíte logo Windows.

![První obrazovka při prvním spuštění](images/01-magic-moment.png)

HoloLens 2 vás provede následujícími kroky:

1. Vyberte svůj jazyk.

    ![Výběr jazyka](images/04-language.png)

1. Vyberte svou oblast.

    ![Výběr oblasti](images/05-region.png)

1. Nakalibrovat HoloLens do očí.  Pokud se rozhodnete přeskočit přeskočení, při příštím přihlášení se zobrazí výzva. 

    1. Nejprve upravíte vizuátor.
    
        ![Obrazovka pro výběr nahody](images/06-et-corners.png)

    2. Při nakalibrování se podíváte na sadu cílů (označované jako gemy). Je to v pořádku, pokud během chouly blikne nebo zavřete oči, ale snažte se nekoukat na jiné objekty v místnosti nebo fyzickém prostoru. HoloLens tento proces používá k tomu, aby se dozvěděl o pozici oka, aby mohl lépe vykreslit holografický svět. 

        ![Upravit pro vaše oči](images/07-adjust-eyes.png)

        Po dokončení se hologramy zobrazí správně, i když se visor posune na vaší hlavy. Informace o výuce se ukládají místně v zařízení a nejsou přidružené k žádným informacím o účtu. Další informace najdete v tématu [o ochraně osobních údajů a zabezpečení.](hololens-calibration.md#calibration-data-and-security)

        ![Je dokončená operace](images/calibration-complete.png)

1. Připojte se k internetu (vyberte Wi-Fi nebo ethernetové připojení).

     HoloLens nastaví časové pásmo automaticky na základě informací získaných z Wi-Fi sítě. Po dokončení nastavení můžete časové pásmo změnit pomocí aplikace Nastavení.

    ![Připojení k Wi-Fi](images/11-network.png)

    > [!NOTE] 
    > Pokud postupíte po kroku Wi-Fi a později budete muset přepnout na jinou síť, zatímco  jste stále v nastavení, můžete se k tomuto kroku vrátit stisknutím tlačítek Snížení objemu a napájení současně, pokud používáte verzi operačního systému z října 2019 nebo novější.  U starších verzí možná [](hololens-recovery.md) budete muset resetovat zařízení nebo ho restartovat v umístění, kde není dostupná síť Wi-Fi, aby se zabránilo jeho automatickému připojení.
    > 
    > Všimněte si také, že během instalace HoloLens došlo k časovému limitu přihlašovacích údajů dvou minut. Uživatelské jméno a heslo je potřeba zadat do dvou minut, jinak se pole uživatelského jména automaticky vyškrtne.

1. HoloLens 2 vyhledá a použije profil Autopilotu, pokud existuje. Na této obrazovce není potřeba žádná akce.
 
    ![Vyhledávání profilu Autopilotu](images/autopilot-profile-search.png) 

1. Na **obrazovce** licencování klikněte na Přijmout.

    ![Licenční smlouva pro Windows](images/windows-license-agreement.png)

1. Přihlaste se ke svému uživatelskému účtu. Zvolíte si, jestli je můj **pracovní nebo** školní vlastnit a já **ho vlastním.**

    - Když zvolíte **Možnost Můj pracovní nebo školní účet** vlastní , přihlásíte se pomocí účtu Azure AD. Pokud vaše organizace používá Azure AD Premium a nakonfiguroval automatickou registraci MDM, HoloLens se do MDM automaticky zaregistruje. Pokud vaše organizace tuto funkci Azure AD Premium, automatická registrace MDM není dostupná. V takovém případě musíte [holoLens](hololens-enroll-mdm.md#different-ways-to-enroll)zaregistrovat ručně ve správě zařízení.

        1. Zadejte informace o účtu organizace.
        1. Přijměte prohlášení o zásadách ochrany osobních údajů a licenční smlouvu s koncovým uživatelem.
        1. Přihlaste se pomocí svých přihlašovacích údajů azure AD. To se může přesměrovat na přihlašovací stránku vaší organizace.
        1. Pokračujte v nastavování zařízení.

    - Když zvolíte **Možnost vlastnit**, přihlásíte se pomocí účet Microsoft. Po dokončení instalace můžete [holoLens](hololens-enroll-mdm.md#different-ways-to-enroll)zaregistrovat do správy zařízení ručně.

        1. Zadejte své účet Microsoft údaje.
        2. Zadejte svoje heslo. Pokud váš účet Microsoft vyžaduje [dvoukrokové ověřování ,](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)dokončete proces ověřování.

    ![Nastavení uživatele](images/13-device-owner.png)

1. Na nastavení přihlášení Iris vyberte **Další.** Projdete si podobné prostředí jako při pohledu. Po **dokončení** kontroly vyberte Hotovo. Tento krok můžete také **obejít** výběrem možnosti Přeskočit.
    
    ![Iris – nastavení ](images/setup-iris.png) ![ Dokončení instalace Iris](images/iris-setup-complete.png) 
     
  
1. Pro přihlášení k zařízení si nasnídáte KÓD PIN. Tento PIN kód je specifický pro zařízení. 

    ![Nastavení Windows Hello](images/setup-windows-hello.png)

    ![Nastavení Windows Hello PIN kódu](images/windows-hello-pin.png)

    ![Windows Hello instalace byla úspěšná](images/windows-hello-successful.png) 
    
1. Vyberte, jestli chcete povolit řeč na HoloLens 2.

    ![Povolení Cortany](images/22-do-more-with-voice.png)

1. Vyberte, jestli se má povolit umístění na HoloLens 2.
    
    ![Povolení polohových služeb](images/setup-location-services.png)

1. Vyberte úroveň telemetrie. Pokud můžete, povolte volitelnou telemetrii. Tyto informace ve skutečnosti pomáhají technickém týmu HoloLens.

     ![Úroveň telemetrie](images/24-telemetry.png)

1. Naučte se používat gesto spuštění na HoloLens 2.

     ![Přečtěte si, jak používat gesto spuštění, obrázek 1.](images/26-01-startmenu-learning.png)

     ![Přečtěte si, jak používat gesto spuštění, obrázek 2.](images/26-02-startmenu-learning.png)

Gratulujeme!  Nastavení je hotové a jste připraveni k použití HoloLens!

## <a name="next-steps"></a>Další kroky

1. Začněte ihned pracovat s Mixed Reality a procházením Windows 10 na HoloLens – podívejte  se na aplikaci Tipy, ve které najdete návody k interakcím pomocí rukou. Pomocí gesta spuštění přejděte na Start nebo řekněte "Přejít na start" a vyberte Tipy.

1. Klikněte níže a pokračujte ve čtení o použití HoloLens 2.

> [!div class="nextstepaction"]
> [Práce s HoloLens 2](hololens2-basic-usage.md)
