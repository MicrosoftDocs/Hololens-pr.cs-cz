---
title: Insider preview pro Microsoft HoloLens
description: Zjistěte, jak začít se sestaveními Insider a poskytnout cennou zpětnou vazbu pro naši další velkou aktualizaci operačního systému pro HoloLens.
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
ms.date: 10/19/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: 382c979138068ab1d9682ee4e84831accc9e4553
ms.sourcegitcommit: 73a1555fb8b84f3d20c480282c648d8d800a6c98
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/26/2021
ms.locfileid: "130351639"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider preview pro Microsoft HoloLens

Vítá vás nejnovější sestavení Insider Preview pro HoloLens! Začít a poskytnout cennou [zpětnou vazbu](hololens-insider.md#start-receiving-insider-builds) pro naši další velkou aktualizaci operačního systému pro HoloLens.

## <a name="windows-insider-release-notes"></a>Windows Poznámky k verzi Insider

Co je nového a na horizontu pro HoloLens? Podívejte se na tyto nové aktualizace, které HoloLens!

### <a name="colorblind-mode"></a>Colorblind mode (Barevný režim)

Přidání v buildu Insider 20348.1463

Barevně podtržený režim je užitečnou funkcí, díky které HoloLens přístupnější. Nový režim barví se nachází v aplikaci Nastavení v části Nastavení  ->  **Usnadnění přístupu**  ->  **Filtry barev**. K dispozici je několik nových filtrů. Tady je příklad některých dostupných filtrů.

| Vypnout | Stupně šedi | Tritanopia |
|-----|-----------|------------|
| ![Vypnutý filtr barev](images/colorblind-off.png)   | ![Barevné filtry ve šedě](images/colorblind-greyscale.png)         | ![Tritanopia filtru barev](images/colorblind-tritanopia.png)          |

### <a name="fixes-and-improvements"></a>Opravy a vylepšení

- Byl opraven známý problém, kdy se při každém [18%](hololens-troubleshooting.md#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)výkonu zařízení náhle automaticky vypnulo .
- Vylepšení přesunu režimu platformy při zjišťování směru dolů
- Opravili jsme problém s dialogy aktualizací.
- Aktualizovaná doručená Microsoft Edge verze prohlížeče.
- Opravili jsme problém, kdy přepínání volitelných diagnostických dat nezachovávalo zvolené nastavení na stránce nastavení telemetrie po restartování.
- Opravili jsme problém, kdy se nerozpoznaly kódy QR, když byly otáčíny v úhlu 45 stupňů vzhledem k zařízení.

## <a name="start-receiving-insider-builds"></a>Zahájení přijímání sestavení Insider

> [!NOTE]
> Pokud jste to ještě neudělali, restartujte zařízení, abyste aktualizovali stav a získejte nejnovější build.
>
> - Hlasový příkaz Restartovat zařízení funguje dobře.
> - Můžete také zvolit tlačítko pro restartování v Nastavení/Windows Insider Program.
>
> Na back-endu jsme měli chybu, se kterou jste se mohli setkat, a tím se vrátíte na cestu.

Na zařízení HoloLens 2 přejděte na **Nastavení** Update & Security Windows Insider Program a  >    >   vyberte **Začínáme.** Propojte účet, který jste použili k registraci, Windows Insider.

> [!NOTE]
> Pokud chcete své zařízení zaregistrovat v buildech Insider, budete muset povolit volitelnou telemetrii. Pokud jste to ještě neudělali, otevřete aplikaci Nastavení, vyberte Diagnostika ochrany osobních údajů & názory a pak   ->   vyberte **Volitelná diagnostická data**.

Windows insider se teď přesouvá na Kanály. Kanál **Fast** se stane **vývojový** kanál, kanál **Slow** se stane **kanálem Beta kanál** a kanál release **preview** se stane **kanálem Release Preview**. Toto mapování vypadá takhle:

![Windows Vysvětlení kanálů insider.](images/WindowsInsiderChannels.png)

Další informace najdete v článku [Představení kanálů Windows Insider na](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) Windows blogech.
Pak vyberte **Aktivní vývoj Windows,** zvolte, jestli chcete dostávat Dev **Channel** nebo Beta kanál **buildy,** a zkontrolujte podmínky programu.
Dokončete **> Potvrdit a** restartovat. Po restartování zařízení přejděte na stránku Nastavení > **Update & Security >** Vyhledejte aktualizace a získejte nejnovější sestavení.

### <a name="update-error-0x80070490-work-around"></a>Aktualizace 0x80070490 obchádky

Pokud při aktualizaci na kanálu pro 0x80070490 nebo beta verzi dojde k chybě aktualizace, vyzkoušejte následující krátkodobé řešení. Zahrnuje přesunutí kanálu insider, vyzvednutí aktualizace a pak přesunutí kanálu Insider zpět.

#### <a name="stage-one---release-preview"></a>Fáze 1 – Verze Preview

1. Nastavení, & Security a Windows Insider Program vyberte Kanál Release **Preview.**

2. Nastavení, aktualizace &, aktualizace Windows, **kontrola aktualizací**. Po aktualizaci pokračujte fází 2.

#### <a name="stage-two---dev-channel"></a>Fáze 2 – Vývojový kanál

1. Nastavení, & Security a Windows Insider Program vyberte **Dev Channel**.

2. Nastavení, aktualizace &, aktualizace Windows, **kontrola aktualizací**.

## <a name="ffu-download-and-flash-directions"></a>Pokyny ke stažení ffu a flash

Pokud chcete testovat pomocí ffu podepsaného letem, musíte nejprve letět s odemknutým zařízením před flash flash diskem ffu.

1. Na počítači:
    1. Stáhněte si ffu do počítače z [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .

    1. Nainstalujte ARC (Advanced Recovery Companion) z Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .

1. Na HoloLens – Letové odemčení: Otevřete **Nastavení** Update & Security Windows Insider Program a pak se zaregistrujte a  >    >   restartujte zařízení.

1. Flash FFU – Nyní můžete flash diskem podepsaného letem FFU použít ARC.

### <a name="provide-feedback-and-report-issues"></a>Poskytnutí zpětné vazby a hlášení problémů

Pokud chcete [poskytnout zpětnou vazbu a Centrum Feedback problémy,](hololens-feedback.md) použijte aplikaci HoloLens na svém počítači. Pomocí Centrum Feedback zajistíte, že se zahrnou všechny potřebné diagnostické informace, které našim technikům pomůžou rychle ladit a vyřešit problém.  Problémy s čínštinou a japonštinou HoloLens by měly být hlášeny stejným způsobem.

> [!NOTE]
> Nezapomeňte přijmout výzvu s dotazem, jestli chcete Centrum Feedback ke složce  Dokumenty (po zobrazení výzvy vyberte Ano).

## <a name="note-for-developers"></a>Poznámka pro vývojáře

Vítá vás a doporučujeme, abyste si zkusili vyvíjet aplikace pomocí buildů insider HoloLens.  Pokud chcete [začít, HoloLens si prohlédněte dokumentaci pro](https://developer.microsoft.com/windows/mixed-reality/development) vývojáře. Stejné pokyny fungují i se sestaveními insider HoloLens.  Můžete použít stejná sestavení Unity a Visual Studio, které už používáte pro HoloLens vývoj.

## <a name="stop-receiving-insider-builds"></a>Zastavení přijímání sestavení Insider

Pokud už nechcete dostávat buildy Insider systému Windows Holographic, můžete to vyjádřit výslovně, když HoloLens [](hololens-recovery.md) používá produkční build, nebo můžete obnovit zařízení pomocí doplňku Advanced Recovery Companion a obnovit zařízení na verzi Windows Holographic, která není z programu Insider.

> [!CAUTION]
> Existuje známý problém, kdy se uživatelům, kteří po ruční přeinstalaci nové verze Preview buildu ruší registraci ve verzi Insider Preview, zobrazí modrá obrazovka. Potom musí zařízení obnovit ručně. Úplné podrobnosti o tom, jestli by vás to ovlivnilo nebo ne, najdete v části Další informace o tomto [známém problému.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)

Pokud chcete ověřit, HoloLens vaše aplikace používá produkční sestavení:

1. Přejděte na **Nastavení > System > About** a vyhledejte číslo sestavení.

1. [Podívejte se na poznámky k verzi pro čísla produkčních buildů](hololens-release-notes.md).

Odhlášení sestavení Insider:

1. Na HoloLens produkčním sestavení přejděte na Nastavení > **Update & Security > Windows Insider Program** a vyberte Zastavit sestavení **Insider.**

1. Postupujte podle pokynů a odhlásit zařízení.
