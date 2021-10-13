---
title: Insider Preview pro Microsoft HoloLens
description: Naučte se, jak začít s buildy Insider, a poskytněte vám užitečnou zpětnou vazbu k naší další aktualizaci operačního systému HoloLens.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 10/12/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: 080eb5949bc80d1ce922d57f099c375668f5633f
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924354"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider Preview pro Microsoft HoloLens

Vítejte v nejnovějších buildech Insider Preview pro HoloLens! Je jednoduché začít a poskytnout cennou zpětnou [vazbu k naší](hololens-insider.md#start-receiving-insider-builds) další hlavní aktualizaci operačního systému pro HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Poznámky k verzi programu Insider

Jsme si zajímáme, že všechny nejnovější funkce programu Insider zmizely jako veřejné! Pokud se o těchto informací chcete seznámit, přečtěte si [stránku poznámky k verzi](hololens-release-notes.md) .

## <a name="start-receiving-insider-builds"></a>Zahájit přijímání buildů Insider

> [!NOTE]
> Pokud jste se neaktualizovali v poslední době, restartujte prosím své zařízení, aby se aktualizovaly stav, a získejte nejnovější Build.
>
> - Hlasový příkaz "restartovat zařízení" dobře funguje.
> - můžete také zvolit tlačítko restartovat v programu Nastavení/Windows Insider.
>
> Na back-endu jsme narazili na chybu, která se vám mohla vyskytnout, a získáte zpět sledování.

na zařízení HoloLens 2 přejít do **Nastavení**  >  **Update & Security**  >  **Windows Program Insider** a vyberte začínáme . propojte účet, který jste použili k registraci jako Windows Insider.

> [!NOTE]
> Aby bylo možné zaregistrovat zařízení v buildech Insider, budete muset povolit volitelnou telemetrii. pokud jste to ještě neudělali, otevřete aplikaci Nastavení a vyberte možnost diagnostika **osobních údajů**  ->  **& zpětná vazba** a pak vyberte **volitelná diagnostická data**.

Windows insider se teď přesouvá na kanály. **Rychlý** prstenec se stane **kanálem pro vývoj**, **pomalé** vyzvánění se stane **kanálem beta verze** a prstenec **verze Preview** se stane **kanálem verze Preview**. Toto mapování vypadá takto:

![Windows Vysvětlení kanálů Insider.](images/WindowsInsiderChannels.png)

další informace najdete v tématu [představení Windowsch kanálů Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) na Windows blogů.
pak vyberte možnost **aktivní vývoj Windows**, zvolte, jestli chcete dostávat buildy pro **vývoj** nebo **Beta kanál** , a podívejte se na licenční program.
Kliknutím na tlačítko **potvrdit > restartovat nyní** dokončete instalaci. po restartování zařízení přejít na **Nastavení > Update & Security > vyhledat aktualizace** a získat nejnovější build.

### <a name="update-error-0x80070490-work-around"></a>Chyba aktualizace 0x80070490 práce

Pokud narazíte na chybu aktualizace 0x80070490 při aktualizaci na vývojovém nebo beta kanálu, zkuste následující krátkodobé řešení. Zahrnuje přesun kanálu služby Insider, aktualizaci a přesun kanálu Insider zpátky.

#### <a name="stage-one---release-preview"></a>Fáze verze Preview 1

1. Nastavení, Update & Security Windows programu Insider vyberte **kanál verze preview**.

2. Nastavení, aktualizujte & zabezpečení, web Windows Update vyhledejte **aktualizace**. Po aktualizaci pokračujte do fáze 2.

#### <a name="stage-two---dev-channel"></a>Fáze – dva vývojové kanály

1. Nastavení, aktualizovat & zabezpečení Windows programu Insider vyberte možnost **vývojového kanálu**.

2. Nastavení, aktualizujte & zabezpečení, web Windows Update vyhledejte **aktualizace**.

## <a name="ffu-download-and-flash-directions"></a>FFU stažení a pokyny pro Flash

Pokud chcete otestovat ffuem podepsaným letem, musíte nejdřív zařízení odemknout a před zavedením ffuého letu podepsaného.

1. V počítači:
    1. Stáhněte si FFU do počítače z [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .

    1. Nainstalujte oblouk (Průvodce pokročilým obnovením) z Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. při HoloLensovém odemknutí: otevřít **Nastavení**  >  **aktualizace & zabezpečení**  >  **Windows programu Insider** , zaregistrujte se a restartujte zařízení.

1. FFU Flash – nyní můžete FFU podepsaný pro let pomocí ARC.

### <a name="provide-feedback-and-report-issues"></a>Poskytněte zpětnou vazbu a nahlásit problémy

k poskytnutí zpětné vazby a hlášení problémů použijte prosím [aplikaci centra Feedback](hololens-feedback.md) v HoloLens. Pomocí centra Feedback zajišťujeme, aby byly k dispozici všechny potřebné diagnostické informace, které nám pomohly rychle ladit a řešit potíže.  problémy s čínskou a japonskou verzí HoloLens by měly být hlášeny stejným způsobem.

> [!NOTE]
> Nezapomeňte přijmout výzvu s dotazem, jestli chcete, aby měl centrum zpětné vazby přístup ke složce dokumentů (po zobrazení výzvy vyberte **Ano** ).

## <a name="note-for-developers"></a>Poznámka pro vývojáře

Jste připraveni a doporučujeme vyzkoušet vývoj aplikací pomocí buildů Insider HoloLens.  pokud chcete začít, podívejte se na [dokumentaci pro vývojáře HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) . Stejné pokyny fungují s buildy Insider HoloLens.  můžete použít stejná sestavení Unity a Visual Studio, která už používáte pro HoloLens vývoj.

## <a name="stop-receiving-insider-builds"></a>Zastavit příjem buildů Insider

pokud už nechcete dostávat buildy Insider Windows holografické, můžete se odhlásit, když HoloLens spouští výrobní sestavení, nebo můžete [zařízení obnovit](hololens-recovery.md) pomocí průvodce pokročilým obnovením a obnovit zařízení do verze programu Windows holografické v jiné verzi než Insider.

> [!CAUTION]
> Došlo k známému problému, při kterém se uživatelé, kteří zruší registraci v buildu Insider Preview po ruční instalaci nového buildu Preview, zobrazí modrá obrazovka. Potom musí zařízení ručně obnovit. Podrobné informace o tom, jestli by se to ovlivnilo, najdete v tomto [známém problému](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).

chcete-li ověřit, zda HoloLens spouští výrobní sestavení:

1. přejít na **Nastavení > systému > o** a najít číslo sestavení.

1. [Přečtěte si poznámky k verzi pro výrobní čísla buildu](hololens-release-notes.md).

Odhlášení od buildů Insider:

1. na HoloLens, na kterém běží výrobní sestavení, navštivte **Nastavení > Update & Security > Windows Insider** a vyberte zastavit buildy **Insider**.

1. Pokud chcete zařízení odhlásit, postupujte podle pokynů.
