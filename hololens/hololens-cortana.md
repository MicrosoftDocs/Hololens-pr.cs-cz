---
title: Využijte svůj hlas k práci s HoloLens
description: Přečtěte si, jak Cortana vám může pomáhat dělat všechny druhy věcí na zařízeních s hybridní realitou HoloLens, včetně hlasových příkazů, diktování a interakcí na hologram.
ms.assetid: fd96fb0e-6759-4dbe-be1f-58bedad66fed
ms.date: 03/10/2020
keywords: HoloLens
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
audience: ITPro
ms.author: v-tea
ms.topic: article
manager: jarrettr
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f6e3dd8f7dc90cea158d000251973ec75dc76a90
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379281"
---
# <a name="use-your-voice-to-operate-hololens"></a>Využijte svůj hlas k práci s HoloLens

Můžete použít svůj hlas k tomu, abyste v HoloLens mohli dělat skoro cokoli, jako je třeba vytvoření rychlé fotografie nebo otevření aplikace. Mnoho hlasových příkazů je integrováno do HoloLens, zatímco jiné jsou k dispozici prostřednictvím Cortany.

Tento článek vás seznámí s tím, jak ovládat HoloLens a váš holografický svět pomocí vašeho hlasu a Cortany.

> [!NOTE]
> Rozpoznávání řeči je podporováno pouze v [některých jazycích](hololens2-language-support.md). Jazyk řeči je založen na jazyku zobrazení systému Windows, nikoli v jazyku klávesnice.  
>  
> Jazyk zobrazení systému Windows můžete ověřit tak, že vyberete **Nastavení**  >  **čas a jazyk jazyka**  >  .

## <a name="built-in-voice-commands"></a>Integrované hlasové příkazy

Využijte k rychlejšímu zpracování HoloLens tyto základní příkazy. Aby je bylo možné použít, je třeba povolit rozpoznávání řeči během prvního spuštění zařízení nebo v **Nastavení**  >  **soukromí**  >  **řeči**. V horní části nabídky Start můžete vždy zjistit, jestli je zapnutý Speech. Pro dosažení nejlepších výsledků rozpoznávání řeči využívá HoloLens 2 cloudové služby Microsoftu. Tuto funkci však můžete zakázat pomocí nastavení. To uděláte tak, že v nastavení vypnete **rozpoznávání řeči online**. Po změně tohoto nastavení bude HoloLens 2 zpracovávat pouze hlasová data místně, aby bylo možné rozpoznat příkazy a diktování a Cortana nebude k dispozici.

### <a name="general-speech-commands"></a>Obecné příkazy pro rozpoznávání řeči

Pomocí těchto příkazů v rámci Windows Mixed reality se můžete rychleji vyhnout. Některé příkazy používají pohledu ukazatel, který se zobrazí vyslovením příkazu "vybrat".

> [!NOTE]
> Pro HoloLens (1. generace) se ruky nepodporují.

| Řekněme | Akce |
| - | - |
| Vybrali | Vyslovením příkazu "SELECT" zobrazíte pohledu ukazatel. Pak změňte polohu kurzoru na věc, kterou chcete vybrat, a vyslovení příkazu "vybrat". |
| "Přejít na začátek" |  Otevření nabídky Start |
| Uzavírací  | Zavření nabídky Start |
| Vyslovením příkazu "Přejít na začátek" zobrazíte nabídku rychlé akce a potom řekněme "Mixed reality – Domovská stránka".  | Opuštění moderní aplikace |
| "Skrýt ruka pro ruky"/"Zobrazit ruku – Ray" | Skrytí a zobrazení příručních paprsků |
| Co můžu říci?  | Zobrazit dostupné příkazy řeči |

Počínaje verzí 19041. x z HoloLens 2 můžete použít také tyto příkazy:

| Řekněme | Akce |
| - | - |
| "Restartovat zařízení" | Otevřete dialog pro potvrzení, že chcete zařízení restartovat. Pro restartování můžete vyslovit "Ano". |
| Vypnutí zařízení | Zobrazte dialog pro potvrzení, že chcete zařízení vypnout. Pro potvrzení můžete vyslovit "Ano". |
| "Jas nahoru/dolů" | Zvýšit nebo snížit jas displeje o 10%. |
| "Navýšení/snížení hlasitosti" | Zvyšte nebo snižte hlasitost o 10%. |
| "Co je moje IP adresa" | Zobrazte si dialog zobrazující aktuální IP adresu vašeho zařízení v místní síti. |
| "Přebírat obrázek" | Zachyťte si fotografii se smíšenou realitou toho, co v tuto chvíli vidíte. |
| "Zabrat si video" | Spustí záznam videa se smíšenými realitami. | 
| "Zastavit záznam" | Zastaví aktuální záznam videa ve smíšené realitě, pokud právě probíhá. |

### <a name="hologram-commands"></a>Příkazy hologramu

Pokud chcete tyto příkazy použít, pohledu se v 3D objektu, hologramu nebo okně aplikace.

| Řekněme | Akce |
| - | - |
| Zvýšen | Zvětšete |
| Zmenšen | Zmenšit |
| "Tvář jsem" | Nastavte si to jako tvář |
| "Přesunout tuto" | Přesunout (postupujte podle svého pohledu) |
| Uzavírací | Zavřít |
| "Pokračovat"/"zastavit následující" | Udělejte to při přechodu kolem |

### <a name="see-it-say-it"></a>Podívejte se, jak se to říká

Mnoho tlačítek a dalších prvků na HoloLens také reaguje na váš hlas – například **Sledujte mě** **a na** panelu aplikace nebo na tlačítko **zpět** na okraji. Pokud chcete zjistit, jestli **je u tlačítka** povolený hlas, nechte za chvíli **pohledu kurzor**, **dotykové ovládání** nebo jednu kapacitu. Pokud je na tlačítku zapnuté hlasové hovory, zobrazí se hlasový Tip.

### <a name="dictation-mode"></a>Režim diktování

Už vás unavuje psaní? Přepněte do režimu diktování, kdykoli je tato holografická klávesnice aktivní. Začněte tím, že vyberete tlačítko mikrofonu, nebo vyslovením příkazu "spustit diktování". Chcete-li ukončit diktování, znovu vyberte tlačítko nebo vyslovení příkazu "zastavit diktování". Pokud chcete odstranit to, co jste právě nadiktuji, vyslovte "odstranit to". 

> [!NOTE]
> Chcete-li použít režim diktování, je nutné mít připojení k Internetu.

Diktování HoloLens používá explicitní interpunkci, což znamená, že je název interpunkční znaménka, které chcete použít. Například můžete vyslovit "Hey **čárka** , co jste na **otazník**."

Tady jsou klíčová slova interpunkce, která můžete použít:

- Tečka, čárka, otazník, vykřičník nebo vykřičník
- Nový řádek/nový odstavec
- Střední, dvojtečka
- Otevřít uvozovky, zavřít uvozovky
- Hashtag, smajlík nebo Veselý obličej, zamračené, Winky
- Dolar, procenta

Někdy je užitečné hláskovat například e-mailové adresy. Například pro diktování example@outlook.com byste řekli "E X A M P L E" v aplikaci Outlook dot com. "

## <a name="do-more-with-cortana"></a>Další s Cortana

Cortana vám může pomoci dělat všechny druhy věcí na HoloLens, ale v závislosti na tom, kterou verzi Windows holografickou používáte, můžou být tyto možnosti odlišné. Další informace o aktualizovaných možnostech nejnovější verze Cortany najdete tady: [Cortana v nadcházející verzi Windows 10: zaměřuje se na produktivitu s využitím zvýšeného zabezpečení a ochrany osobních údajů](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/). 

![Hey Cortana!](images/cortana-on-hololens.png)

Tady je několik věcí, které můžete vyzkoušet (nezapomeňte nejdřív vyslovit "Hey Cortana").

**Hey, Cortana**...

- Co mám říct?
- Spusťte <*název aplikace*>.
- Kolik je hodin?
- Zobrazit nejnovější NBA skóre
- Řekněte mi zábavný.

Pokud používáte *verzi 18362. x nebo starší*, můžete použít také tyto příkazy:

**Hey, Cortana**...

- Zvětšete svazek.
- Snižte jas.
- Odprejskni.
- Restart.
- Jdi spát.
- Vypnutí.
- Přesuňte <*název aplikace*> sem (pohledu na místě, na které se má aplikace přesunout).
- Přejděte na Start.
- Pořídit obrázek.
- Spustit záznam. (Spustí záznam videa.)
- Zastavit nahrávání. (Zastaví nahrávání videa.)
- Kolik baterie zbývá?

Některé funkce Cortany, které jste použili v systému Windows na vašem počítači nebo telefonu (například připomenutí a oznámení), se v Microsoft HoloLens nepodporují a prostředí Cortana se může lišit od jedné oblasti do druhé.

### <a name="turn-cortana-off"></a>Vypnout Cortanu

Cortana je v době, kdy jste povolili rozpoznávání řeči při prvním použití HoloLens. Můžete ho zapnout v nastavení Cortany. V seznamu **všechny aplikace** vyberte   >  **Nastavení** Cortany. Potom Cortana může poskytnout návrhy, nápady, připomenutí, výstrahy a další.

Pokud Cortana nereaguje na "Hey Cortana", zkontrolujte, že je v nabídce Start zapnutý Speech, přejít na nastavení Cortany a ověřte, jestli je zapnutý.
