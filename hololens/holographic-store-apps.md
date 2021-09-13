---
title: Hledání, instalace a odinstalace aplikací
description: Microsoft Store je váš zdroj pro aplikace a hry, které pracují s HoloLens.  Přečtěte si další informace o hledání, instalaci a odinstalaci holografických aplikací.
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 9/7/2021
manager: jarrettr
keywords: HoloLens, Store, UWP, aplikace, instalace
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 3442da500e7554d7f97db2178cbaceeecad143ac
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126035843"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a>Hledání, instalace a odinstalace aplikací z Microsoft Store

Microsoft Store je váš zdroj přechodu na aplikace a hry, které pracují s HoloLens. když přejdete na obchod na svém HoloLens, všechny aplikace, které vidíte, se na něm spustí.

aplikace na HoloLens používají 2d zobrazení nebo holografické zobrazení. Aplikace, které používají 2D zobrazení, vypadají jako Windows a můžou se po celém světě umístit. Aplikace, které používají Holografické zobrazení, se dostanou jenom na aplikaci, kterou vidíte.

HoloLens podporuje mnoho stávajících aplikací z Microsoft Store a nové aplikace sestavené speciálně pro HoloLens.  Tento článek se zaměřuje na holografické aplikace z Microsoft Store.

Pokud chcete získat další informace o instalaci a spouštění vlastních aplikací, přečtěte si [vlastní holografické aplikace](holographic-custom-apps.md).

## <a name="find-apps"></a>Najít aplikace

otevřete Microsoft Store v nabídce **Start** . Pak vyhledejte aplikace a hry. Pomocí [hlasových příkazů](hololens-cortana.md) můžete hledat vyslovením "hledání", jakmile se otevře okno hledání "zahájení diktování" a pak když se zobrazí výzva, začne dočínat hledané výrazy.

> [!NOTE]
> požadavky na systém pro HoloLens zařízení jsou založené na architektuře buildu aplikace. pokud se sestavení aplikace pro HoloLens (1. generace) neaktualizovalo na novější UWP v úložišti, aby zahrnovalo balíček architektury ARM, nebude k dispozici pro zařízení HoloLens 2. podobně platí, že pokud aplikace HoloLens 2 neobsahuje balíček architektury x86, nebude k dispozici pro zařízení HoloLens (1. generace). HoloLens architektury zařízení:
>
> - x86 = HoloLens (1. generace)
> - ARM = HoloLens 2

> [!NOTE]
> 12. ledna 2021 budou tyto aplikace dostupné na konci podpory HoloLensch zařízení. Pro použití webové verze aplikace doporučujeme na svém zařízení použít následující odkaz.

| Aplikace        | Odkaz                                          |
|------------|-----------------------------------------------|
| Excel mobilní zařízení      | [https://office.live.com/start/Excel.aspx](https://office.live.com/start/Excel.aspx)      |
| Mobilní aplikace Word       | [https://office.live.com/start/Word.aspx](https://office.live.com/start/Word.aspx)       |
| PowerPoint mobilní zařízení | [https://office.live.com/start/PowerPoint.aspx](https://office.live.com/start/PowerPoint.aspx) |

> [!NOTE]
> aplikace OneDrive se v současnosti pro účty Azure AD v HoloLens nepodporuje. doporučujeme stáhnout aplikaci Microsoft OneDrive PWA. [Pomocí těchto kroků stáhněte aplikaci.]

## <a name="install-apps"></a>Instalace aplikací

Chcete-li stáhnout aplikace, budete muset být přihlášeni pomocí účet Microsoft. Některé aplikace jsou bezplatné a dají se hned stáhnout. Pro aplikace, které vyžadují nákup, musíte být přihlášení do obchodu s vaším účet Microsoft a mít platný způsob platby.

> [!NOTE]
> účet, který používáte v Microsoft Store, nemusí být stejný jako účet, pomocí kterého jste se přihlásili. pokud na svém HoloLens používáte pracovní nebo školní účet, možná se budete muset přihlásit pomocí osobního účtu v aplikaci Store a koupit si ho.

> [!TIP]
> Pokud chcete nastavit způsob platby, klikněte na [account.Microsoft.com](https://account.microsoft.com/) a vyberte možnost platební **& platby faktury**  >    >  **Přidat možnost platby**.

1. chcete-li otevřít [nabídku **start**](holographic-home.md), proveďte v HoloLens gesto [začátku](/hololens/hololens2-basic-usage#start-gesture) nebo [bloom](hololens1-basic-usage.md) (1. generace).

1. vyberte aplikaci Microsoft Store. Po otevření aplikace ze Storu:
   1. Vyhledejte aplikace pomocí panelu hledání.
   1. vyberte základní aplikace nebo aplikace, které jsou určené speciálně pro HoloLens z jedné z kategorií, které byly v kategorii.
   1. V pravém horním rohu aplikace pro Store vyberte tlačítko **"..."** a pak výběrem možnosti **Moje knihovna** zobrazíte všechny dříve zakoupené aplikace.

1. Na stránce aplikace vyberte **získat** nebo **nainstalovat** (může se vyžadovat nákup).

### <a name="install-microsoft-onedrive-pwa-app"></a>instalace aplikace Microsoft OneDrive PWA

předpoklady: uživatel již připojil zařízení HoloLens 2 ke svému pracovnímu tenantovi.

1. Otevřete nabídku Start a spusťte prohlížeč Edge.

    ![Nabídka Start](images/office-pwa-1.jpg)

1. v HoloLens přejděte na [https://onedrive.live.com/about/signin](https://onedrive.live.com/about/signin) a zadejte své přihlašovací údaje k pracovnímu účtu.

    ![Pracovní přihlášení](images/office-pwa-2.jpg)

1. po úspěšném přihlášení k OneDrive webový portál počkejte na 30 až 60 sekund, než se tlačítko pro stažení PWA pro stažení zobrazí.

    ![PWA – tlačítko nainstalovat](images/office-pwa-3.jpg)

1. vyberte PWA tlačítko stáhnout a nainstalujte aplikaci.

    ![Výzva k instalaci](images/office-pwa-4.jpg)

1. zavřete prohlížeč Edge a z nabídka Start vyberte tlačítko **všechny aplikace** a spusťte aplikaci OneDrive PWA s označením **Microsoft OneDrive**

    ![Všechny aplikace, které zobrazují obě aplikace](images/office-pwa-5.jpg)

> [!NOTE]
> "Microsoft OneDrive" je PWA aplikace, kde "OneDrive" je starší UWP.

1. pak budete moci zobrazit soubory OneDrive.

    ![OneDrive PWA](images/office-pwa-6.jpg)

viz také: [povolení automatického nahrávání OneDrive pro firmy](hololens-release-notes.md#onedrive-for-work-or-school-camera-roll-upload) .

## <a name="update-apps"></a>Aktualizovat aplikace

pokud chcete aktualizovat aplikaci, kterou jste nainstalovali z Microsoft Store, můžete aplikaci aktualizovat z aplikace Microsoft Store. pro aplikace nainstalované pro Microsoft Store pro firmy můžete tyto aplikace aktualizovat taky z Microsoft Store pro firmy.

1. chcete-li otevřít [nabídku **start**](holographic-home.md), proveďte v HoloLens gesto [začátku](/hololens/hololens2-basic-usage#start-gesture) nebo [bloom](hololens1-basic-usage.md) (1. generace).

1. Vyberte aplikaci ze Storu.

1. Podívejte se do pravé horní části aplikace pro Store.

1. Vyberte tlačítko **"..."** nebo "Zobrazit další".

   > [!div class="mx-imgBorder"]
   > ![snímek obrazovky aplikace Microsoft Store](images/store-update-1.png)

1. Vyberte **soubory ke stažení a aktualizace**.
    1. Pokud zařízení obsahuje dříve identifikované aktualizace, může se jednat o šipku dolů a číslo, které představuje nedokončené aktualizace.

1. Vyberte **získat aktualizace**. Vaše zařízení teď bude vyhledávat aktualizace a nastavit je ke stažení a instalaci.

   > [!div class="mx-imgBorder"]
   > ![snímek obrazovky aplikace Microsoft Store pro získávání aktualizací...](images/store-update-2.png.jpg)

> [!NOTE]
> Pokud byly aplikace v zařízení distribuovány vaší organizací, je možné je aktualizovat prostřednictvím stejné metody správy komerčních aplikací. Pokud se to týká vaší situace, přečtěte si další [informace prostřednictvím našeho přehledu nasazení komerční aplikace.](app-deploy-overview.md)
>
> Pokud chcete aktualizovat vlastní aplikaci, která byla zkušebně načtené nebo nasazená, budete muset použít stejnou metodu s aktualizovanou verzí vaší aplikace. Pokud chcete získat další informace o instalaci a spouštění vlastních aplikací, přečtěte si [vlastní holografické aplikace](holographic-custom-apps.md).

## <a name="uninstall-apps"></a>Odinstalovat aplikace

Existují tři způsoby, jak odinstalovat aplikace. aplikace můžete odinstalovat prostřednictvím Microsoft Store, nabídka Start nebo z Nastavení.

> [!WARNING]
> nemůžete odinstalovat systémovou aplikaci ani Microsoft Store sebe sama.

> [!IMPORTANT]
> pokud má HoloLens 2 více uživatelů, musíte být přihlášeni jako uživatel, který aplikaci nainstaloval, a odinstalovat ji.

### <a name="uninstall-from-the-microsoft-store"></a>Odinstalace z Microsoft Store

v nabídce **Start** otevřete Microsoft Store a vyhledejte aplikaci, kterou chcete odinstalovat.  Na stránce Store má každá nainstalovaná aplikace tlačítko **odinstalovat** .

### <a name="uninstall-from-the-start-menu"></a>odinstalace z nabídka Start

V nabídce **Start** nebo v seznamu **všechny aplikace** přejděte do aplikace. Vyberte a podržte, dokud se nabídka nezobrazí, a pak vyberte **odinstalovat**.

### <a name="uninstall-from-settings"></a>odinstalace z Nastavení

v nabídce **Start** vyberte **Nastavení > aplikace.** Vyhledejte aplikaci ze seznamu, vyberte ji a pak klikněte na **odinstalovat**.

Pokud nemůžete odinstalovat aplikaci, pošlete [nám svůj názor](/hololens/hololens-feedback) pomocí centra Feedback.
