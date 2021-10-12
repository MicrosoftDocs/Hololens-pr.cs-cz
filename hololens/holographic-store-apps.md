---
title: Vyhledání, instalace a odinstalace aplikací
description: Tento Microsoft Store je zdrojem pro aplikace a hry, které pracují s HoloLens.  Přečtěte si další informace o hledání, instalaci a odinstalaci holografických aplikací.
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 9/7/2021
manager: jarrettr
keywords: hololens, store, uwp, app, install
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4705112ee41ce6de0598358b9c81775f261bb2fa
ms.sourcegitcommit: 8a3f925d2bda13c095b35f14d80afdd876aa859c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2021
ms.locfileid: "129800551"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a>Vyhledání, instalace a odinstalace aplikací z Microsoft Store

Hlavní Microsoft Store je vaším zdrojem informací pro aplikace a hry, které pracují s HoloLens. Když na svém zařízení ve Storu HoloLens, spustí se na ní všechny aplikace, které tam vidíte.

Aplikace v HoloLens používají buď 2D zobrazení, nebo holografické zobrazení. Aplikace, které používají 2D zobrazení, vypadají jako okna a můžete je umístit kolem sebe. Aplikace, které používají holografické zobrazení, vás obklopují a stanou se jedinou aplikací, kterou vidíte.

HoloLens podporuje mnoho existujících aplikací z Microsoft Store a nové aplikace vytvořené speciálně pro HoloLens.  Tento článek se zaměřuje na holografické aplikace z Microsoft Store.

Další informace o instalaci a spouštění vlastních aplikací najdete v tématu [Vlastní holografické aplikace.](holographic-custom-apps.md)

## <a name="find-apps"></a>Hledání aplikací

Otevřete Microsoft Store z **nabídky Start.** Pak vyhledejte aplikace a hry. Hlasové příkazy [můžete](hololens-cortana.md) použít k vyhledávání tak, že řeknete "Hledat", jakmile se okno hledání otevře, řekne "Start dictating" (Začít diktovat) a po zobrazení výzvy začne hledaný výraz říkat.

> [!NOTE]
> Požadavky na systém HoloLens zařízení jsou založené na architektuře sestavení aplikace. Pokud sestavení aplikace pro HoloLens (1. generace) nebylo aktualizováno na novější UPW ve Storu tak, aby zahrnovalo balíček architektury ARM, nebude dostupné pro zařízení HoloLens 2. Podobně platí, že pokud aplikace HoloLens 2 neobsahuje balíček architektury x86, nebude k dispozici pro HoloLens (1. generace). HoloLens architektury zařízení:
>
> - x86 = HoloLens (1. generace)
> - ARM = HoloLens 2

> [!NOTE]
> 12. ledna 2021 se následující aplikace dostanou na konec podpory na HoloLens zařízeních. Pokud chcete používat webovou verzi aplikace, doporučujeme na svém zařízení použít následující odkaz.

| Aplikace        | Odkaz                                          |
|------------|-----------------------------------------------|
| Excel Mobile      | [https://office.live.com/start/Excel.aspx](https://office.live.com/start/Excel.aspx)      |
| Word Mobile       | [https://office.live.com/start/Word.aspx](https://office.live.com/start/Word.aspx)       |
| PowerPoint Mobile | [https://office.live.com/start/PowerPoint.aspx](https://office.live.com/start/PowerPoint.aspx) |

> [!NOTE]
> Aplikace OneDrive se v současné době nepodporuje pro účty Azure AD na HoloLens. Doporučujeme stáhnout si Microsoft OneDrive PWA aplikaci. [Aplikaci stáhnete pomocí těchto kroků.]

## <a name="install-apps"></a>Instalace aplikací

Pokud chcete stahovat aplikace, musíte být přihlášeni pomocí účet Microsoft. Některé aplikace jsou zdarma a můžete si je hned stáhnout. U aplikací, které vyžadují nákup, musíte být přihlášeni ke Storu pomocí účet Microsoft a mít platný způsob platby.

> [!NOTE]
> Účet, který používáte v Microsoft Store, nemusí být stejný jako účet, pod nímž jste přihlášení. Pokud na svém zařízení používáte pracovní nebo školní účet HoloLens možná se budete muset přihlásit pomocí svého osobního účtu v aplikaci pro Store a provést nákup.

> [!TIP]
> Pokud chcete nastavit způsob platby, přejděte do části [account.microsoft.com](https://account.microsoft.com/) vyberte **Payment & billing Payment**  >  **options**  >  **(Způsoby platby) Add a payment option**(Přidat možnost platby).

1. Pokud chcete otevřít [ **nabídku Start,**](holographic-home.md)proveďte [gesto spuštění](/hololens/hololens2-basic-usage#start-gesture) nebo gesto [bloomu](hololens1-basic-usage.md) HoloLens (1. generace).

1. Vyberte aplikaci Microsoft Store. Po otevření aplikace pro Store:
   1. Pomocí panelu hledání vyhledejte aplikace.
   1. Vyberte základní aplikace nebo aplikace speciálně pro HoloLens z jedné z kurátorovaných kategorií.
   1. V pravém horním rohu aplikace pro Store vyberte **tlačítko "..."** a pak vyberte **Moje** knihovna. Zobrazí se všechny dříve zakoupené aplikace.

1. Na  stránce **aplikace** vyberte Získat nebo Nainstalovat (může být nutné koupit).

### <a name="install-microsoft-onedrive-pwa-app"></a>Instalace Microsoft OneDrive PWA aplikace

> [!NOTE]
> PWA není možné spravovat ani nasazovat prostřednictvím Microsoft Intune nebo MDM.

Předpoklady: Uživatel už připojil zařízení HoloLens 2 ke svému pracovnímu tenantovi.

1. Otevřete nabídku Start a spusťte prohlížeč Edge.

    ![Nabídka Start](images/office-pwa-1.jpg)

1. Na svém HoloLens na a [https://onedrive.live.com/about/signin](https://onedrive.live.com/about/signin) zadejte přihlašovací údaje k pracovnímu účtu.

    ![Pracovní přihlášení](images/office-pwa-2.jpg)

1. Po úspěšném přihlášení k webovému portálu OneDrive počkejte 30 až 60 sekund, než se PWA tlačítko pro stažení.

    ![PWA tlačítko Nainstalovat](images/office-pwa-3.jpg)

1. Vyberte tlačítko PWA stáhnout a nainstalujte aplikaci.

    ![Výzva k instalaci](images/office-pwa-4.jpg)

1. Zavřete prohlížeč Edge a v nabídka Start  vyberte tlačítko Všechny aplikace a spusťte aplikaci OneDrive PWA označenou **Microsoft OneDrive**

    ![Všechny aplikace obě aplikace.](images/office-pwa-5.jpg)

    > [!NOTE]
    > "Microsoft OneDrive" je PWA, kde jako "OneDrive" je starší UPW.

1. Pak budete moci zobrazit své OneDrive soubory.

    ![OneDrive PWA](images/office-pwa-6.jpg)

Viz také: [Povolení automatického nahrávání do OneDrive pro firmy](hololens-release-notes.md#onedrive-for-work-or-school-camera-roll-upload)

## <a name="update-apps"></a>Aktualizace aplikací

### <a name="manual-updates"></a>Ruční aktualizace

Pokud chcete aktualizovat aplikaci, kterou jste nainstalovali z Microsoft Store, můžete ji aktualizovat z Microsoft Store aplikace. U aplikací nainstalovaných pro Microsoft Store pro firmy můžete tyto aplikace také aktualizovat z Microsoft Store pro firmy.

1. Pokud chcete otevřít [ **nabídku Start,**](holographic-home.md)proveďte [gesto spuštění](/hololens/hololens2-basic-usage#start-gesture) nebo gesto [bloomu](hololens1-basic-usage.md) HoloLens (1. generace).

1. Vyberte aplikaci pro Store.

1. Podívejte se do pravého horního rohu aplikace Store.

1. Vyberte **tlačítko "..."** nebo "Zobrazit další".

   > [!div class="mx-imgBorder"]
   > ![Microsoft Store snímku obrazovky aplikace](images/store-update-1.png)

1. Vyberte **Položky ke stažení a aktualizace.**
    1. Pokud zařízení dříve identifikovalo aktualizace, může se zobrazit šipka dolů a číslo, které představuje čekající aktualizace.

1. Vyberte **Získat aktualizace.** Zařízení teď bude hledat aktualizace a nastavovat je tak, aby se stáhly a instalují.

   > [!div class="mx-imgBorder"]
   > ![Microsoft Store snímku obrazovky aplikace se získáním aktualizací.](images/store-update-2.png.jpg)

> [!NOTE]
> Pokud vaše organizace distribuuje aplikace na vašem zařízení, můžete je aktualizovat stejnými komerčními metodami správy aplikací. Pokud se to týká vaší situace, přečtěte si další informace v [přehledu nasazení komerčních aplikací.](app-deploy-overview.md)
>
> Pokud chcete aktualizovat vlastní aplikaci, která se nasadila bokem nebo bokem, budete muset použít stejnou metodu s aktualizovanou verzí aplikace. Další informace o instalaci a spouštění vlastních aplikací najdete v tématu [o vlastních holografických aplikacích.](holographic-custom-apps.md)

### <a name="automatic-app-updates"></a>Automatické aktualizace aplikací

Automatické aktualizace se Microsoft Store nebo Microsoft Store pro firmy aplikací a instalují se automaticky jenom v případě, že byly nainstalovány přímo ze Storu. Pokud je služba IT nainstalovaná z Intune, může z MDM dostávat aktualizace tím, že synchronizuje s Microsoft Store pro firmy nejnovější dostupnou verzi aplikace.

> [!NOTE]
> U aplikací, které jsou Microsoft Store pro firmy, musíte být přihlášeni do Storu a ověřovat pomocí stejného tenanta, který je přidružený Microsoft Store pro firmy katalogu použitému na zařízení.

#### <a name="how-automatic-updates-work"></a>Jak fungují automatické aktualizace

Automatické aktualizace aplikací se plánují každý den (přibližně každých 24 hodin) v závislosti na dostupnosti sítě. Pokud chcete dostávat aktualizace, nechte zařízení aktivní nebo zapojené do střídavého napětí. I když se aktualizace aplikace stahují během aktivního denního využití, použijí se jenom v případě, že se aplikace, která se má aktualizovat, už se nebude používat.

> [!TIP]
> Pokud je to možné, účtuje zařízení přes noc, když je připojené k podnikové síti. Pokud je možné aktualizace stáhnout a nainstalovat přes noc, je méně pravděpodobné, že přeruší aktivní používání zařízení.

#### <a name="how-it-administrators-can-control-automatic-updates"></a>Jak můžou správci IT řídit automatické aktualizace

Správci IT můžou řídit automatické aktualizace aplikací prostřednictvím [zásad ApplicationManagement/AllowAppStoreAutoUpdate.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) Tato zásada jim umožňuje povolit nebo zakázat automatické aktualizace aplikací úplně, ale nesnížuje, kdy k aktualizacím dojde.

Od [verze 21H2](hololens-release-notes.md#windows-holographic-version-21h1)můžou správci IT také pomocí zásad [ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures) řídit, kdy se aplikace, které se používají, ale v předchozích pokusech se neaktualizace nepomáhaly, měly vynucovat restartování.

## <a name="uninstall-apps"></a>Odinstalovat aplikace

Existují tři způsoby odinstalace aplikací. Aplikace můžete odinstalovat prostřednictvím Microsoft Store, nabídka Start nebo z Nastavení.

> [!WARNING]
> Systémovou aplikaci ani samotnou aplikaci Microsoft Store odinstalovat.

> [!IMPORTANT]
> pokud má HoloLens 2 více uživatelů, musíte být přihlášeni jako uživatel, který aplikaci nainstaloval, a odinstalovat ji.

### <a name="uninstall-from-the-microsoft-store"></a>Odinstalace z Microsoft Store

v nabídce **Start** otevřete Microsoft Store a vyhledejte aplikaci, kterou chcete odinstalovat.  Na stránce Store má každá nainstalovaná aplikace tlačítko **odinstalovat** .

### <a name="uninstall-from-the-start-menu"></a>odinstalace z nabídka Start

V nabídce **Start** nebo v seznamu **všechny aplikace** přejděte do aplikace. Vyberte a podržte, dokud se nabídka nezobrazí, a pak vyberte **odinstalovat**.

### <a name="uninstall-from-settings"></a>odinstalace z Nastavení

v nabídce **Start** vyberte **Nastavení > aplikace.** Vyhledejte aplikaci ze seznamu, vyberte ji a pak klikněte na **odinstalovat**.

Pokud nemůžete odinstalovat aplikaci, pošlete [nám svůj názor](/hololens/hololens-feedback) pomocí centra Feedback.
