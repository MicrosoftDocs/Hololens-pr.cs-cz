---
title: Řešení potíží
description: Aktuální informace o nejběžnějších řešeních problémů se zařízeními HoloLens a jejich řešení
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: issues, bug, troubleshoot, fix, help, support, HoloLens
ms.openlocfilehash: 1039af533b5039eb4eef6599c7cbb480955b0661
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111377638"
---
# <a name="troubleshoot-common-issues"></a>Řešení běžných potíží

Tento článek popisuje, jak vyřešit několik běžných problémů s HoloLens.

## <a name="my-hololens-is-unresponsive-or-wont-start"></a>Moje HoloLens nereaguje nebo se nespustí

Pokud se HoloLens nespustí:

- Pokud se indikátory LED vedle tlačítka napájení nesvítí nebo krátce blikne jenom jedna dioda LED, možná budete muset zařízení [HoloLens naúčtovat.](hololens-recovery.md#charge-the-device)
- Pokud se LED diody rozsvítí, když stisknete tlačítko napájení, ale na displeji se nic [neuvidí,](hololens-recovery.md#hard-reset-procedure)vynulujte zařízení předem.

Pokud holoLens zamrzne nebo přestane reagovat:

- Zařízení HoloLens vypněte stisknutím tlačítka napájení, dokud se všechny 5 led diod nevypnou, nebo po dobu 15 sekund, pokud diody LED nereagují. HoloLens spustíte tak, že znovu stisknete tlačítko napájení.

Pokud tyto kroky nefungují, můžete zkusit obnovit zařízení [HoloLens 2](hololens-recovery.md) nebo [HoloLens (1. generace).](hololens1-recovery.md)

## <a name="holograms-dont-look-good"></a>Hologramy nevypadá dobře

Pokud jsou hologramy nestabilní, jumpy nebo nevypadá správně, zkuste:

- Vyčištění visoru zařízení a panelu senzorů na přední straně zařízení HoloLens
- Zvětšete světlo v místnosti.
- Procházíte se po okolí a díváte se na své okolí, aby je HoloLens mohl kompletněji prohledat.
- Nakalibrování HoloLens pro vaše oči Přejděte na **Settings** System Utilities  >  **(Nastavení – systémové**  >  **nástroje).** V části Chysoce vyberte **Open Uchovat.** 
 
### <a name="reporting-issues-where-holograms-are-unstable-or-dont-look-right"></a>Hlášení problémů, kdy jsou hologramy nestabilní nebo nevycílněly správně
 
1. Nahrajte a [Záznam hybridní reality video](holographic-photos-and-videos.md#capture-a-mixed-reality-video) o problému. Toto video můžete později nahrát prostřednictvím Centrum Feedback jako připojený soubor.  
1. Povolte úplnou telemetrii prostřednictvím aplikace Nastavení -> **Privacy**  Diagnostics & názory a v části Volitelná diagnostická data se ujistěte, že je přepínač nastavený na  ->   **Zapnout.** 
1. Nejnovější opravy škálování a stability hologramu získáte aktualizací na nejnovější verzi [Windows Holographic OS (20H2 nebo vyšší).](hololens-release-notes.md#windows-holographic-version-20h2) Po aktualizaci proveďte následující:
    1. Odeberte všechny hologramy prostřednictvím aplikace Nastavení ->    ->  **Hologramy systému** -> pak vyberte Odebrat všechny **hologramy** a začněte novou mapou.
    1. Vytvořte novou mapu svého prostoru tím, že máte holoLens, procházíte se v místnosti a díváte se na všechny oblasti a povrchy v prostoru. Proveďte to po dobu 2 až 3 minut.
    1. Proveďte operaci IPD. Přejděte na **Settings** System Utilities  >  **(Nastavení – systémové**  >  **nástroje).** V části Chysoce vyberte **Open Uchovat.** 
    1. Znovu scénář otestujte a podívejte se, jestli pořád přetrvává.
1. Pokud aktualizace tento problém nevypraví, zadejte Centrum Feedback [problému.](hololens-feedback.md) Po odeslání zpětné vazby můžete  použít tlačítko Sdílet a vytvořit snadno sdílet odkaz, který můžete odeslat při kontaktování podpory.

## <a name="hololens-doesnt-respond-to-hand-input"></a>HoloLens nereaguje na ruční vstup

Abyste zajistili, že HoloLens uvidí vaše ruce, musíte je ponechat v snímku gest.  Domovská Mixed Reality poskytuje zpětnou vazbu, která vám dá vědět, kdy jsou vaše ruce sledované.  Názory na různé verze HoloLens se liší:
- V HoloLens (1. generace) se kurzor pohledu změní z tečky na kruh.
- Na HoloLensu 2 se zobrazí kurzor prstu, když je vaše ruce blízko slate, a když jsou břidíčky dále, zobrazí se ruční paprsk.

Řada imerzivních aplikací dodržuje vzory vstupu, které se podobají Mixed Reality Domovské obrazovce.  Přečtěte si další informace o použití ručního vstupu [v HoloLens (1. generace)](hololens1-basic-usage.md#use-hololens-with-your-hands) a [HoloLens 2.](hololens2-basic-usage.md#the-hand-tracking-frame)

Pokud máte problémy s chemií, mějte na vědomí, že některé typy choumů nefungují se sledováním rukou.  Běžným příkladem je černá guma, která obvykle absorbuje infračervené světlo a nenabírá je hloubková kamera.  Pokud vaše práce zahrnuje gumové gumy, doporučujeme, abyste si zkusili světlejší barvu, například modrou nebo šedou.  Dalším příkladem je velká nesrozumilá aplikace, která má tendenci zakrytí tvaru vaší ruky. Pro nejlepší výsledky doporučujeme použít co nejvíce tvarování.

Pokud má váš vizuátor otisky prstů nebo šmouhy, vyčistěte vizuály pomocí mikrovlákna, které jste dodáli s HoloLens.

## <a name="hololens-doesnt-respond-to-my-voice-commands"></a>HoloLens nereaguje na hlasové příkazy

Pokud Cortana nereaguje na vaše hlasové příkazy, ujistěte se, že je zapnutá Cortana. V seznamu Všechny aplikace poznámkového bloku **nabídky Cortany** proveďte  >    >    >   změny. Další informace o tom, co můžete říct, najdete v [tématu Použití hlasu s HoloLens.](hololens-cortana.md)

## <a name="i-cant-place-holograms-or-see-holograms-that-i-previously-placed"></a>Nemůžu umístit hologramy nebo zobrazit hologramy, které jsem umístil(a) dříve

Pokud HoloLens nemůže mapovat ani načíst prostor, vstoupí do omezeného režimu a nebudete moct umístit hologramy ani zobrazit hologramy, které jste umístili. Vyzkoušejte něco z tohoto:

- Ujistěte se, že je ve vašem prostředí dostatek světla, aby holoLens mohl prostor zobrazit a namapovat.
- Ujistěte se, že jste připojeni k Wi-Fi síti. Pokud nejste připojení k Wi-Fi, HoloLens nemůže identifikovat a načíst známé místo.
- Pokud potřebujete vytvořit nové místo, připojte se k Wi-Fi a restartujte HoloLens.
- Pokud chcete zobrazit, jestli je aktivní správné místo, nebo pokud chcete mezeru načíst ručně, přejděte do **části Nastavení**  >  **systémových**  >  **prostorů.**
- Pokud je načteno správné místo a stále máte problémy, může být prostor poškozený. Pokud chcete tento problém vyřešit, vyberte místo a pak vyberte **Odebrat.** Po odebrání prostoru začne HoloLens mapovat vaše okolí a vytvořit nový prostor.

## <a name="my-hololens-cant-tell-what-space-im-in"></a>Moje HoloLens nemůže zjistit, ve které oblasti se nacházím

Pokud holoLens nemůže automaticky identifikovat a načíst prostor, ve které se nacházíte, zkontrolujte následující faktory:

- Ujistěte se, že jste připojeni k Wi-Fi
- Ujistěte se, že je v místnosti spousta světla.
- Ujistěte se, že v okolí nebyly žádné zásadní změny.

Prostor můžete také načíst ručně nebo můžete prostory spravovat tak, že přejdeme do **nastavení**  >  **Systémové**  >  **prostory.**

## <a name="im-getting-a-low-disk-space-error"></a>Při pokusu o získání volného místa na disku se mi zobrazí chyba

Budete muset některé místo úložiště volná jedním nebo více z následujících způsobů:

- Odstraňte některé nepoužívané mezery. Přejděte na **Nastavení**  >    >  **Systémových prostorů,** vyberte mezeru, kterou už nepotřebujete, a pak vyberte **Odebrat.**
- Odeberte některé hologramy, které jste umístili.
- Odstraňte některé obrázky a videa z aplikace Photos.
- Odinstalujte některé aplikace z HoloLens. V seznamu **Všechny aplikace** klepněte a podržte aplikaci, kterou chcete odinstalovat, a pak vyberte **Odinstalovat.**

## <a name="my-hololens-cant-create-a-new-space"></a>Moje HoloLens nemůže vytvořit nový prostor

Nejpravděpodobnějším problémem je nedostatek úložného prostoru. Zkuste některé z [předchozích tipů](#im-getting-a-low-disk-space-error) volného místa na disku volného místa.

## <a name="the-hololens-emulator-isnt-working"></a>Emulátor HoloLens nefunguje

Informace o emulátoru HoloLens najdete v naší dokumentaci pro vývojáře.  Přečtěte si další [informace o řešení potíží s emulátorem HoloLens.](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)
