---
title: Hardware HoloLens 2
description: Seznamte se s komponentami, které tvoří Microsoft HoloLens 2, což je nejnovější vývoj nepřipojeného holografického počítače společnosti Microsoft s Windows 10.
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 10/20/2020
keywords: HoloLens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 88687559310a9abc24f34c416880e02caf535177
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924515"
---
# <a name="about-hololens-2"></a>O HoloLens 2

![Zobrazení na straně HoloLens 2](images/hololens2-breakdown.png)

Microsoft HoloLens 2 je nepřipojený holografický počítač.  Vyhodnotí cestu k holografickým výpočetním činnostem, kterou zahájila HoloLens (1. generace), a poskytuje pohodlnější a atraktivní prostředí spárované s dalšími možnostmi pro spolupráci ve smíšené realitě. HoloLens 2 běží na [holografickém operačním systému Windows](hololens-release-notes.md), který je založený na "charakteru" Windows 10, který poskytuje uživatelům, správcům a vývojářům robustní, výkonnou a zabezpečenou platformu. 

> [!NOTE]
> Nedávné oznámení Windows 11 se zaměřilo na verzi PC systému Windows. Nedávno jsme spustili [velkou aktualizaci operačního systému](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067) na HoloLens 2 v květnu 2021 a pracujeme na nadcházející verzi na základě zpětné vazby od zákazníků.

Pro použití HoloLens 2 je vyžadován uživatelský účet.

## <a name="hololens-components"></a>Komponenty HoloLens

- **Rozcestník**. Obsahuje senzory HoloLens a displeje. Můžete střídat hypervisor nahoru a přitom se zachováním HoloLens.
- **HEADBAND**. Chcete-li umístit na HoloLens, pomocí kolečka úprav rozbalte HEADBAND. Když je nastavené HoloLens, seložte úchyt úprav tak, že zapnete napravo, dokud se HEADBAND necítí.
- **Tlačítka pro jas** Při používání HoloLens jsou tlačítka jasu na levé straně rozhraní rozcestníku poblíž vaší Temple.
- **Tlačítka hlasitosti**. Při používání HoloLens jsou tlačítka hlasitosti na pravé straně rozhraní Temple v blízkosti vaší.
- **Tlačítko napájení**. Při používání HoloLens je tlačítko napájení umístěno na pravé straně vnějšího krytu.
- **Port USB-C**. Při používání HoloLens je port USB-C umístěný na pravé straně vnějšího krytu pod tlačítkem napájení.

## <a name="in-the-box"></a>V poli

- **[Prohlížeč panel](https://www.microsoft.com/p/microsoft-hololens-2-brow-pad/90z10rsslqp0)**. Prohlížeč panel můžete podle potřeby odebrat a nahradit.
- **[Popruh režijních nákladů](https://www.microsoft.com/p/microsoft-hololens-2-overhead-strap/8wxl8wmk1f7z)** Pokud při přesouvání nebudete používat HoloLens, použijte k zajištění toho, aby zařízení bylo zachováno, pomocí popruhu režijních nákladů. Při používání HoloLens po delší dobu může popruh režie zvýšit pohodlí zařízení.
- **[Nabíječka a kabel USB-C](https://www.microsoft.com/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5)**. Napájecí napájení se připojí k napájení z elektrické zásuvky. Pomocí kabelu USB-C Připojte svůj HoloLens k zdroji napájení pro zpoplatnění nebo připojte HoloLens k počítači.
- **Microfiber tkanina**. Použijte k vyčištění hypervisoru HoloLens.

### <a name="power-supply-details"></a>Podrobnosti o zdroji napájení

Zdroj napájení a kabel USB, který je součástí zařízení, je nejlepším podporovaným mechanismem pro zpoplatnění. Zdrojem napájení je 18W nabíječka.  9V dodá na 2A.

Rychlost nabíjení a rychlost se můžou lišit v závislosti na prostředí, ve kterém je zařízení spuštěné.

Aby se zajistilo, že interní procento poplatků za baterii v době, kdy je zařízení zapnuté, musí být připojení minimálně k 15W nabíječkě.

## <a name="device-specifications"></a>Specifikace zařízení

### <a name="display"></a>Zobrazení

|   |   |
| - | - |
| Optické optiky | Prohlédněte si holografické čočky (waveguides) |
| Holografické řešení | lehké moduly 2k 3:2 |
| Holografická hustota | >2.5 k radiants (body světla na Radian) |
| Vykreslování na základě očí | Zobrazit optimalizaci pozice prostorového oka |

### <a name="sensors"></a>Čidl

|   |   |
| - | - |
| Sledování hlav | 4 viditelné světelné kamery |
| Sledování očí | 2 kamery pro infračervený přenos (IR) |
| Úrovní | 1. MP časový senzor hloubky |
| Jednotka měření Inertial (IMU) | Akcelerometr, vybavený gyroskopem, magnetometer |
| Camera | 8. MP stále 1080p30 video |

![Senzory HoloLens 2](images/hololens2-front-view.png)

> [!NOTE]
> Nekrytí žádných senzorů, které jsou na obrázku vyvolány. Kamery sledující hlavní fotoaparáty mají velmi velký FOV, nic by se kolem nich nemělo dokrýt.

### <a name="audio-and-speech"></a>Zvuk a řeč

|   |   |
| - | - |
| Mikrofonní pole | 5 kanálů |
| Mluvčích | Vestavěný prostorový zvuk |

### <a name="compute-and-connectivity"></a>Výpočetní prostředí a připojení

|   |   |
| - | - |
| Systém na čipu | [Podrobnosti o](https://www.qualcomm.com/products/snapdragon-850-mobile-compute-platform) výpočetní platformě pro Qualcomm Snapdragon 850 |
| Holografická jednotka zpracování | Vlastní vytvořená jednotka holografického zpracování druhé generace |
| Memory (Paměť) | 4 GB LPDDR4x systému paměti DRAM |
| Storage | 64 GB UFS 2,1 |
| WiFi | 802.11 AC 2x2 |
| Bluetooth | 5.0 |
| USB | Typ USB – DRP C |

### <a name="power"></a>Napájení

|   |   |
| - | - |
| Výdrž baterie | 2-3 hodin aktivního použití Až dva týdny v pohotovostním čase. |
| Technologie baterie | [Lithium baterie](https://www.microsoft.com/download/details.aspx?id=43388) |
| Chování zpoplatnění | Plně funkční při zpoplatnění |
| Typ chlazení | Prochlazené (bez ventilátorů) |
| Vykreslování napájení | Aby se zajistilo, že interní procento poplatků za baterii v době, kdy je zařízení zapnuté, musí být připojení minimálně k 15W nabíječkě. |

### <a name="fit"></a>Vhodnost

|   |   |
| - | - |
| Velikosti | Jedna velikost s přizpůsobitelným pruhem.  Hodí se ke brýlím. |
| Hmotnost | 566 gramů |

## <a name="device-capabilities"></a>Možnosti zařízení

### <a name="human-understanding"></a>Lidské porozumění

|   |   |
| - | - |
| Ruční sledování | Plně artikulovaný model se dvěma rucemi, přímá manipulace |
| Sledování očí | Sledování v reálném čase |
| Hlas | Příkazy a ovládání na zařízení; Přirozený jazyk Cortany s připojením k internetu |

### <a name="environment-understanding"></a>Principy prostředí

|   |   |
| - | - |
| Sledování šesti stupňů volnosti (6DoF) | Sledování poziční polohy na světové úrovni |
| Prostorové mapování | Síť prostředí v reálném čase |
| Zachycení hybridní reality | Fotky a videa ve smíšeném hologramu a fyzickém prostředí |

## <a name="pre-installed-software"></a>Předinstalovaný software

|   |   |
| - | - |
| Operační systém Windows Holographic | V [operačním systému Windows Holographic](hololens-release-notes.md)Windows 10 uživatelé prostřednictvím HoloLens 2 používat některé své aplikace a hry v prostředí hybridní reality.
| 3D prohlížeč | [3D prohlížeč](https://www.microsoft.com/p/3d-viewer/9nblggh42ths?activetab=pivot:overviewtab) umožňuje snadno zobrazit 3D modely a animace v reálném čase.|
| Cortana | [Cortana](https://www.microsoft.com/p/cortana/9nffx4szz23l?activetab=pivot:overviewtab), vaše osobní asistentka pro produktivitu, vám pomůže udržovat si informace o tom, co je důležité, a ušetřit čas hledáním toho, co potřebujete.  |
| Průvodci Dynamics 365 |  [Průvodci Dynamics 365 pomůžou](https://www.microsoft.com/p/microsoft-dynamics-365-guides/9n038fb42kkb?activetab=pivot:overviewtab) zaměstnancům rychleji se učit nové dovednosti na zařízeních HoloLens. |
| Dynamics 365 Remote Assist | [Microsoft Dynamics 365 Remote Assist](https://www.microsoft.com/p/microsoft-dynamics-365-remote-assist/9p77qgw10k9m?activetab=pivot:overviewtab) umožňuje technikům spolupracovat a řešit problémy se vzdálenými spolupracovníky pomocí Microsoft Teams nebo Dynamics 365 Remote Assistu.  |
| Centrum Feedback | [Centrum Feedback](https://www.microsoft.com/p/feedback-hub/9nblggh4r32n?activetab=pivot:overviewtab) vám umožňuje poskytnout zpětnou vazbu k Windows a aplikacím tím, že sdílíte své návrhy nebo problémy.  |
| Průzkumník souborů | Průzkumník souborů poskytuje grafické uživatelské rozhraní pro přístup k systémům souborů. |
| Pošta a kalendář | Aplikace Pošta a [Kalendář](https://www.microsoft.com/p/mail-and-calendar/9wzdncrfhvqm#activetab=pivot:overviewtab) vám pomůžou být v e-mailu aktuální, spravovat plán a zůstat v kontaktu s vašimi kontakty. |  
| Microsoft Edge | Microsoft Edge poskytuje prvotřídní výkon s větší ochranou osobních údajů, vyšší produktivitou a větší hodnotou při procházení. |
| Microsoft Store | The [Microsoft Store](https://www.microsoft.com) is your go-to source for apps and games that work with HoloLens.|
| Movies & TV | [Filmy & TV](https://www.microsoft.com/p/movies-tv/9wzdncrfj3p2?activetab=pivot:overviewtab) vám přinášejí nejnovější zábavu v jedné jednoduché, rychlé a elegantní aplikaci. |
| OneDrive | [OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3?activetab=pivot:overviewtab) umožňuje přístup k souborům a jejich úpravy ze všech zařízení odkudkoli.  |
| Fotky| [Fotky](https://www.microsoft.com/p/microsoft-photos/9wzdncrfjbh4?activetab=pivot:overviewtab) umožňují prohlížet a upravovat fotky a videa, vytvářet filmy a vytvářet filmy.  |
| Nastavení | Aplikace Nastavení je místo, kde můžete podrobně přizpůsobit, jak Windows Holographic funguje.  |
| Tipy | [Tipy](https://www.microsoft.com/p/microsoft-tips/9wzdncrdtbjj?activetab=pivot:overviewtab) vám umožní zvládnout překvapivé a méně známé věci, které můžete dělat ve Windows Holographic. |

## <a name="device-certifications"></a>Certifikace zařízení

### <a name="safety"></a>Bezpečnost

* [Bezpečnost produktu](https://support.microsoft.com/en-us/help/4023454/safety-information)
* [Bezpečnostní upozornění a pokyny k produktu](https://support.microsoft.com/en-us/help/4558037/product-safety-warnings-and-instructions)
* Bezpečnost očí: Zařízení HoloLens 2 bylo otestováno a odpovídá základním požadavkům na ochranu proti dopadu pro ANSI Z87.1, CSA Z94.3 a EN 166.
* [Informace SAR](https://support.microsoft.com/help/12673/mobile-devices-sar-information)

### <a name="regulatory-information"></a>Zákonné informace
[HoloLens Regulatory:](https://support.microsoft.com/en-us/help/13761/hololens-regulatory-information)Zahrnuje informace o teplotě, vyřazení, radioaktivině a televizním rušit a další informace.

## <a name="warranty-information"></a>Informace o záruce

Microsoft HoloLens 2 se dodává se standardní [omezenou zárukou.](https://support.microsoft.com/topic/warranties-extended-service-plans-and-terms-conditions-for-your-device-eedf7a23-84a7-1a47-480b-0e10503eedf5) 


Nákup podléhá Microsoft Store [podmínkám použití a prodeji](https://www.microsoft.com/storedocs/terms-of-sale?rtc=1). Všechny prodeje jsou konečné. Žádné refundace.

Zakoupením HoloLens 2 souhlasíte s licenční [smlouvou na software](https://www.microsoft.com/Useterms/).

Není určeno pro děti mladší než 13 let.

## <a name="package-dimensions"></a>Rozměry balíčku

|      Měření               |      Metrika jednotek     |      Units ( Jednotky)     |
|--------------------------------|-----------------------|-------------------------|
|     Délka jednotky                |     378,97 mm          |     14,920 palců       |
|     Šířka jednotky                 |     247,90 mm          |     9,760 palců        |
|     Hloubka jednotek                 |     163,07 mm          |     6,420 palců        |
|     Hmotnost jednotky                |     2,878 kg           |     6,344 lbs           |
|     Náplní délky shipperu    |     446,00 mm          |     17,559 palců       |
|     Šedou šířku shipperu     |     257,99 mm          |     10,157 palců       |
|     Zamyšlná hloubka lodí     |     172,01 mm          |     6,772 palců        |
|     Přisoudná hmotnost shipperu    |     3,284 kg           |     7,240 lbs           |

> [!NOTE]
> - Jednotka: Černá skříňka ve stylu maloobchodního prodeje HoloLens 2 se prodává.
> - Přisudce Shipper: Ochranné obaly pro expedici kolem jednotky.

## <a name="finding-the-serial-number"></a>Vyhledání sériového čísla

Pod zorníkem se vytiskne sériové číslo zařízení HoloLens 2.

1. Zdvižte zorník zařízení.
1. Podívejte se do blízkosti padu brow.
1. Sériové číslo, které se nachází blízko, můžete najít v pantu.

<img src="images/serial-number-diagram-hl2.png" alt=Null width="625" height="903" />

Sériové číslo lze také najít prostřednictvím připojeného počítače:

1. Připojit zařízení
1. Přejít na **Tento počítač** v Průzkumníkovi souborů
1. Klikněte pravým tlačítkem a vyberte **vlastnosti** zařízení HoloLens.
1. Zobrazí se číslo série zařízení, jak je znázorněno na snímku obrazovky níže.

<img src="images/ResetRecovery2.png" alt=null line width="400" height="600" />

## <a name="next-steps"></a>Další krok (y)

> [!div class="nextstepaction"]
> [Porovnání edicí HoloLens 2](hololens2-options.md)

> [!div class="nextstepaction"]
> [Nastavení a zahájení HoloLens 2](hololens2-setup.md)
