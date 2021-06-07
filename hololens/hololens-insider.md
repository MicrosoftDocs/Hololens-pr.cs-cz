---
title: Insider Preview pro Microsoft HoloLens
description: Naučte se, jak začít se sestavami Insider a poskytnout cennou zpětnou vazbu k naší další hlavní aktualizaci operačního systému pro HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 8545b5f23dc81c194b68ea8b40feb83e525dfdf7
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111377658"
---
# <a name="insider-preview-for-microsoft-hololens"></a>Insider Preview pro Microsoft HoloLens

Vítejte v nejnovějších buildech Insider Preview pro HoloLens! Je jednoduché začít a poskytnout cennou zpětnou [vazbu k naší](hololens-insider.md#start-receiving-insider-builds) další hlavní aktualizaci operačního systému pro HoloLens.

## <a name="windows-insider-release-notes"></a>Poznámky k verzi Windows Insider

S radostí začneme znovu začínat nové funkce pro Windows Insider. Pro nejnovější aktualizace budou nové buildy zacházet s kanály pro vývoj a beta verze. Tuto stránku budeme dál aktualizovat, protože přidáváme další funkce a aktualizace našich buildů Windows Insider. Využijte rádi a připravte se na tyto aktualizace ke své realitě. 

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>Nahrávání na OneDrive pro práci nebo na školní kameře

*Představené v buildu 20346,1402*

Do aplikace nastavení HoloLens 2 jsme přidali novou funkci, která zákazníkům umožňuje automaticky nahrávat fotky a videa ze všech videí ze zařízení > složky fotoaparátu do odpovídající složky OneDrive for Work nebo School. Tato funkce řeší [mezeru funkcí v rámci aplikace OneDrive](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos) na HoloLens 2, která podporuje automatické nahrání z kamery na osobní účet Microsoft zákazníka (a ne na svůj pracovní nebo školní účet).

**Jak to funguje**

- Pokud chcete povolit "nahrávání kamery", přejděte na **nastavení > System > Mixed reality** .
- Když nastavíte tuto funkci na **pozici,** všechny fotky nebo videa ve smíšené realitě zaznamenané do vašeho zařízení se automaticky zařadí do fronty, aby se nahrály do složky obrázky > fotoaparátu na pracovní nebo školní účet.
    >[!NOTE]
    >Fotografie a videa zachycené před povolením této funkce *se* nebudou zařadit do fronty pro nahrání a pořád je budete muset nahrát ručně.
- Stavová zpráva na stránce nastavení zobrazí počet souborů, které čekají na nahrání (nebo čtení, že je OneDrive v aktuálním stavu), kdy se nahrály všechny soubory, které čekají na zpracování.
- Pokud máte obavy o šířku pásma nebo chcete "pozastavit" nahrávání z jakéhokoli důvodu, můžete funkci přepnout na **volnou** pozici. Když funkci dočasně zakážete, zajistíte tak, že se fronta nahrávání během přidávání nových souborů do složky fotoaparátu bude dál zvyšovat, ale soubory se nebudou nahrávat, dokud tuto funkci znovu nepovolíte.
- Nejnovější soubory se nahraje jako první (poslední v, první ven).
- Pokud má váš účet OneDrive problémy (například po změně hesla), zobrazí se na stránce nastavení tlačítko **opravit** .
- Není k dispozici žádná maximální velikost souboru, ale mějte na paměti, že se nahrávání velkých souborů bude trvat déle (zejména pokud je vaše šířka pásma nahrávání omezená). Pokud zadáte "pozastavit" nebo vypnete nahrávání při nahrávání velkého souboru, okamžitě se nahrávání zruší. Po opětovném povolení této funkce se nahrávání restartuje. nepřijdete o žádné soubory, ale částečné nahrání se zahodí.

**Známé problémy a upozornění**

- Toto nastavení nemá integrované omezení na základě aktuálního využití šířky pásma. Pokud potřebujete maximalizovat šířku pásma pro jiný scénář, vypněte nastavení ručně. Nahrávání se pozastaví, ale funkce bude i nadále monitorovat nově přidané soubory do sady fotoaparátů. Až budete připraveni, můžete nahrávání znovu povolit.
- Tato funkce musí být povolená pro každý uživatelský účet v zařízení a může aktivně nahrávat soubory pro uživatele, který je aktuálně přihlášený k zařízení.
- Pokud při sledování počtu odesílání na stránce nastavení v reálném čase vybíráte fotky nebo videa, může se počet nezpracovaných souborů změnit, dokud se nedokončí odeslání aktuálního souboru.
- Nahrávání se pozastaví, pokud zařízení přejde do režimu spánku nebo je vypnuté. Abyste zajistili, že se vaše nevyřízená nahrávání dokončí, aktivně zařízení použije, dokud stránka nastavení nenačte "OneDrive je aktuální", nebo upravte nastavení **napájení & režimu spánku** .

## <a name="start-receiving-insider-builds"></a>Zahájit přijímání buildů Insider
> [!NOTE]
> Pokud jste se neaktualizovali v poslední době, restartujte prosím své zařízení, aby se aktualizovaly stav, a získejte nejnovější Build.
> - Hlasový příkaz "restartovat zařízení" dobře funguje. 
> - V nastavení/programu Windows Insider můžete také zvolit tlačítko restartovat.
>
> Na back-endu jsme narazili na chybu, která se vám mohla vyskytnout, a získáte zpět sledování.

V zařízení HoloLens 2 přejít na **Nastavení**  >  **aktualizace & zabezpečení**  >  **Windows Insider program** a vyberte Začínáme . Propojte účet, který jste použili k registraci jako Windows Insider.
Windows Insider se teď přesouvá na kanály. **Rychlý** prstenec se stane **kanálem pro vývoj**, **pomalé** vyzvánění se stane **kanálem beta verze** a prstenec **verze Preview** se stane **kanálem verze Preview**. Toto mapování vypadá takto: ![ vysvětlení kanálů Windows Insider ](images/WindowsInsiderChannels.png) pro další informace najdete v tématu [představení kanálů Windows Insider](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) na blogu Windows.
Pak vyberte **aktivní vývoj oken**, zvolte, jestli chcete dostávat buildy pro **vývoj** nebo **beta kanál** , a zkontrolujte, jaké jsou tyto programy.
Kliknutím na tlačítko **potvrdit > restartovat nyní** dokončete instalaci. Po restartování zařízení přejít na **nastavení > Update & Security > vyhledat aktualizace** a získat nejnovější Build.
### <a name="update-error-0x80070490-work-around"></a>Chyba aktualizace 0x80070490 práce
Pokud narazíte na chybu aktualizace 0x80070490 při aktualizaci na vývojovém nebo beta kanálu, zkuste následující krátkodobé řešení. Zahrnuje přesun kanálu služby Insider, aktualizaci a přesun kanálu Insider zpátky.
#### <a name="stage-one---release-preview"></a>Fáze verze Preview 1
1.  Nastavení, aktualizace & zabezpečení, program Windows Insider, výběr **kanálu verze Preview**.
2.  Nastavení, aktualizace & zabezpečení web Windows Update, **Vyhledat aktualizace**. Po aktualizaci pokračujte do fáze 2.
#### <a name="stage-two---dev-channel"></a>Fáze – dva vývojové kanály
1. Nastavení, aktualizace & zabezpečení, program Windows Insider, výběr **vývojového kanálu**.
2. Nastavení, aktualizace & zabezpečení web Windows Update, **Vyhledat aktualizace**.
## <a name="ffu-download-and-flash-directions"></a>FFU stažení a pokyny pro Flash
Pokud chcete otestovat ffuem podepsaným letem, musíte nejdřív zařízení odemknout a před zavedením ffuého letu podepsaného.
1. V počítači:
    1. Stáhněte si FFU do počítače z [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .
    
    1. Nainstalujte oblouk (Průvodce pokročilým obnovením) z Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. Při zablokování HoloLens: Otevřete **Nastavení**  >  **aktualizovat & zabezpečení**  >  **program Windows Insider** a potom se zaregistrujte a restartujte zařízení.
1. FFU Flash – nyní můžete FFU podepsaný pro let pomocí ARC.
### <a name="provide-feedback-and-report-issues"></a>Poskytněte zpětnou vazbu a nahlásit problémy
K poskytnutí zpětné vazby a hlášení problémů použijte prosím [aplikaci centra Feedback](hololens-feedback.md) na HoloLens. Pomocí centra Feedback zajišťujeme, aby byly k dispozici všechny potřebné diagnostické informace, které nám pomohly rychle ladit a řešit potíže.  Problémy s čínskou a japonskou verzí HoloLens by měly být hlášeny stejným způsobem.
> [!NOTE]
> Nezapomeňte přijmout výzvu s dotazem, jestli chcete, aby měl centrum zpětné vazby přístup ke složce dokumentů (po zobrazení výzvy vyberte **Ano** ).
## <a name="note-for-developers"></a>Poznámka pro vývojáře
Jste připraveni a doporučujeme vyzkoušet vývoj vašich aplikací pomocí buildů Insider pro HoloLens.  Začněte tím, že si Projděte [dokumentaci pro vývojáře HoloLens](https://developer.microsoft.com/windows/mixed-reality/development) . Stejné pokyny fungují s buildy pro práci s buildem HoloLens.  Můžete použít stejné sestavení Unity a Visual Studio, které už používáte pro vývoj na HoloLens.
## <a name="stop-receiving-insider-builds"></a>Zastavit příjem buildů Insider
Pokud už nechcete dostávat buildy Insider pro Windows holografické, můžete se odhlásit, když na HoloLens běží výrobní sestavení, nebo můžete [zařízení obnovit](hololens-recovery.md) pomocí Průvodce pokročilým obnovením a obnovit zařízení do verze Windows holografického v jiné verzi než Insider.
> [!CAUTION]
> Došlo k známému problému, při kterém se uživatelé, kteří zruší registraci v buildu Insider Preview po ruční instalaci nového buildu Preview, zobrazí modrá obrazovka. Potom musí zařízení ručně obnovit. Podrobné informace o tom, jestli by se to ovlivnilo, najdete v tomto [známém problému](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).
Chcete-li ověřit, zda je na HoloLens spuštěno výrobní sestavení:
1. Přejít na **nastavení > systémové > o produktu** a najít číslo buildu.
1. [Přečtěte si poznámky k verzi pro výrobní čísla buildu](hololens-release-notes.md).
Odhlášení od buildů Insider:
1. Na HoloLens, na kterém běží výrobní sestavení, klikněte na **nastavení > Update & Security > program Windows Insider** a vyberte **Zastavit buildy Insider**.
1. Pokud chcete zařízení odhlásit, postupujte podle pokynů.
