---
title: Využijte svůj hlas k provozu HoloLens
description: přečtěte si, jak vám Cortana může pomáhat dělat všechny druhy věcí na vašich HoloLensch hybridních realit, včetně hlasových příkazů, diktování a interakcí s hologramem.
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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126035829"
---
# <a name="use-your-voice-to-operate-hololens"></a>Využijte svůj hlas k provozu HoloLens

můžete použít svůj hlas k tomu, abyste mohli prakticky cokoli o HoloLens, jako je třeba pořizování rychlé fotografie nebo otevření aplikace. mnoho hlasových příkazů je integrováno do HoloLens, zatímco jiné jsou k dispozici prostřednictvím Cortana.

v tomto článku se naučíte, jak řídit HoloLens a váš holografický svět pomocí hlasu a Cortana.

> [!NOTE]
> Rozpoznávání řeči je podporováno pouze v [některých jazycích](hololens2-language-support.md). jazyk řeči je založený na jazyce zobrazení Windows, nikoli v jazyku klávesnice.  
>  
> jazyk zobrazení Windows můžete ověřit tak, že vyberete **Nastavení**  >  **čas a jazyk jazyka**  >  .

## <a name="built-in-voice-commands"></a>Integrované hlasové příkazy

pomocí těchto základních příkazů se dostanete HoloLens rychleji. aby je bylo možné použít, je třeba povolit rozpoznávání řeči během prvního spuštění zařízení nebo v **Nastavení**  >  **ochrany osobních údajů**  >  . v horní části nabídka Start můžete kdykoli zjistit, jestli je řeč povolený. pro dosažení nejlepších výsledků rozpoznávání řeči HoloLens 2 používá cloudové služby microsoftu. tuto funkci však můžete zakázat pomocí Nastavení. chcete-li to provést, v Nastavení vypněte **rozpoznávání řeči Online**. po změně tohoto nastavení bude HoloLens 2 zpracovávat pouze hlasová data místně, aby bylo možné rozpoznat příkazy a diktování a Cortana nebudou k dispozici.

### <a name="general-speech-commands"></a>Obecné příkazy pro rozpoznávání řeči

pomocí těchto příkazů v celém Windows Mixed Reality se můžete rychleji vyhnout. Některé příkazy používají pohledu ukazatel, který se zobrazí vyslovením příkazu "vybrat".

> [!NOTE]
> u HoloLens (1. generace) se nepodporují ruční paprsky.

| Řekněme | Akce |
| - | - |
| Vybrali | Vyslovením příkazu "SELECT" zobrazíte pohledu ukazatel. Pak změňte polohu kurzoru na věc, kterou chcete vybrat, a vyslovení příkazu "vybrat". |
| "Přejít na začátek" |  Otevření nabídky Start |
| Uzavírací  | zavřít nabídka Start |
| Vyslovením příkazu "Přejít na začátek" zobrazíte nabídku rychlé akce a potom řekněme "Mixed reality – Domovská stránka".  | Opuštění moderní aplikace |
| "Skrýt ruka pro ruky"/"Zobrazit ruku – Ray" | Skrytí a zobrazení příručních paprsků |
| Co můžu říci?  | Zobrazit dostupné příkazy řeči |

počínaje verzí 19041. x z HoloLens 2 můžete použít také tyto příkazy:

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

mnoho tlačítek a dalších prvků HoloLens také reaguje na váš hlas – například **sledujte mě** **a na** panelu aplikace nebo na tlačítko **zpět** na okraji. Pokud chcete zjistit, jestli **je u tlačítka** povolený hlas, nechte za chvíli **pohledu kurzor**, **dotykové ovládání** nebo jednu kapacitu. Pokud je na tlačítku zapnuté hlasové hovory, zobrazí se hlasový Tip.

### <a name="dictation-mode"></a>Režim diktování

Už vás unavuje psaní? Přepněte do režimu diktování, kdykoli je tato holografická klávesnice aktivní. Začněte tím, že vyberete tlačítko mikrofonu, nebo vyslovením příkazu "spustit diktování". Chcete-li ukončit diktování, znovu vyberte tlačítko nebo vyslovení příkazu "zastavit diktování". Pokud chcete odstranit to, co jste právě nadiktuji, vyslovte "odstranit to". 

> [!NOTE]
> Chcete-li použít režim diktování, je nutné mít připojení k Internetu.

HoloLens diktování používá explicitní interpunkci, což znamená, že je název interpunkční znaménka, které chcete použít. Například můžete vyslovit "Hey **čárka** , co jste na **otazník**."

Tady jsou klíčová slova interpunkce, která můžete použít:

- Tečka, čárka, otazník, vykřičník nebo vykřičník
- Nový řádek/nový odstavec
- Střední, dvojtečka
- Otevřít uvozovky, zavřít uvozovky
- Hashtag, smajlík nebo Veselý obličej, zamračené, Winky
- Dolar, procenta

Někdy je užitečné hláskovat například e-mailové adresy. Například pro diktování example@outlook.com byste řekli "E X A M P L E" v aplikaci Outlook dot com. "

## <a name="do-more-with-cortana"></a>Další s Cortana

Cortana vám může pomoci dělat všechny druhy věcí v HoloLens, ale v závislosti na tom, kterou verzi Windows holografickou používáte, můžou být tyto možnosti odlišné. další informace o aktualizovaných možnostech nejnovější verze Cortana najdete tady: [Cortana v nadcházející Windows 10 verzi: zaměřuje se na vaši produktivitu s vylepšeným zabezpečením a ochranou osobních údajů](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/). 

![Hey Cortana!](images/cortana-on-hololens.png)

tady je několik věcí, které můžete vyzkoušet (nezapomeňte nejdřív vyslovit "Hey Cortana").

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

některé funkce Cortana, které jste použili v Windows na vašem počítači nebo telefonu (například připomenutí a oznámení), nejsou v Microsoft HoloLens podporované a Cortana možnosti se můžou lišit od jedné oblasti k druhé.

### <a name="turn-cortana-off"></a>vypnout Cortana

Cortana je při prvním použití HoloLens, když povolíte řeč. jeho vypnutí můžete vypnout v nastavení Cortana. v seznamu **všechny aplikace** vyberte **Cortana**  >  **Nastavení**. vypnutí Cortana vám může poskytnout návrhy, nápady, připomenutí, výstrahy a další.

pokud Cortana neodpovídá na "Hey Cortana", zkontrolujte, že je v nabídce Start zapnutý speech, přejít na nastavení Cortana a ověřte, jestli je zapnutý.
