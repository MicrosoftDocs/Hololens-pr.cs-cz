---
title: Mapování fyzických prostorů pomocí HoloLens
description: HoloLens zjistí, jak prostor v průběhu času vypadá. Uživatelé mohou tento proces usnadnit přesunutím HoloLens určitým způsobem přes prostor.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: hololens, Windows Mixed Reality, design, spatial mapping, HoloLens, surface reconstruction, mesh, head tracking, mapping
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: 7cedf2af90744477c33736087c85a43168167707
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379259"
---
# <a name="map-physical-spaces-with-hololens"></a>Mapování fyzických prostorů pomocí HoloLens

HoloLens spojuje hologramy s fyzickým světem. K tomu musí HoloLens získat informace o fyzickém světě kolem vás a pamatovat si, kam do tohoto prostoru umístit hologramy.

V průběhu času holoLens vytvoří prostorovou *mapu* prostředí, které viděl.  HoloLens aktualizuje mapu při změně prostředí. Dokud jste přihlášeni a zařízení je zapnuté, HoloLens vytvoří a aktualizuje prostorové mapy. Pokud zařízení držíte nebo opotřebováte fotoaparáty, které jsou v prostoru, holoLens se pokusí oblast mapovat. I když se HoloLens naučí prostor přirozeně v průběhu času, existují způsoby, jak můžete holoLens pomoct mapovat prostor rychleji a efektivněji.  

> [!NOTE]
> Pokud holoLens nemůže mapovat prostor nebo je mimo prostor, může HoloLens vstoupit do omezeného režimu. V omezeném režimu nebudete moct hologramy umístit do svého okolí.

Tento článek vysvětluje, jak HoloLens mapuje prostory, jak vylepšit prostorové mapování a jak spravovat prostorová data, která HoloLens shromažďuje.

## <a name="choosing-and-setting-up-and-your-space"></a>Volba a nastavení a prostor

Funkce ve vašem prostředí mohou ztížovat interpretaci prostoru pro HoloLens. Úrovně světla, materiály v prostoru, rozložení objektů a další mohou ovlivnit, jak HoloLens mapuje oblast.

HoloLens funguje nejlépe v určitých typech prostředí. Pokud chcete vytvořit nejlepší prostorovou mapu, zvolte místnost, která má dostatečné světlo a dostatek místa. Vyhněte se tmavým prostorům a místnostem, které mají spoustu tmavých, šišitých nebo průsvitných povrchů (například zrcadla nebo vousy).

HoloLens je optimalizovaný pro použití v interiérech. Prostorové mapování také funguje nejlépe Wi-Fi je zapnuté, i když nemusí být připojené k síti. HoloLens může získat Wi-Fi přístupové body, i když není připojený nebo ověřený. Funkce HoloLens nemění, jestli jsou přístupové body připojené k internetu, nebo jenom k intranetu nebo místnímu prostředí.

HoloLens používejte jenom na bezpečných místech bez rizika při vyjetí. [Další informace o bezpečnosti](https://support.microsoft.com/help/4023454/safety-information)

## <a name="mapping-your-space"></a>Mapování prostoru

Teď jste připraveni začít mapovat náhradní.  Když HoloLens začne mapovat vaše okolí, uvidíte grafické rozložení sítě po prostoru.  V domovském prostředí hybridní reality můžete aktivovat zobrazení mapy výběrem na mapované ploše.

Tady jsou pokyny pro vytvoření skvělé prostorové mapy.

### <a name="understand-the-scenarios-for-the-area"></a>Pochopení scénářů pro oblast

Je důležité strávený co nejvíce času používáním HoloLens, aby mapa byla relevantní a kompletní. Pokud například uživatelský scénář pro HoloLens zahrnuje přechod z bodu A na bod B, projděte si cestu dvakrát až třikrát a při pohybu se díváte ve všech směrech.  

### <a name="walk-slowly-around-the-space"></a>Pomalu procházte prostor

Pokud se po této oblasti budete projít příliš rychle, je pravděpodobné, že HoloLens nebude mít k dispozici mapové oblasti. Pomalu si projděte prostor a každých 5 až 8 stop se zastavujte, abyste se podívali na okolí.  

Hladké pohyby také pomáhají mapu HoloLens efektivněji.

### <a name="look-in-all-directions"></a>Hledejte ve všech směrech.

Při pohledu na mapu prostoru dává HoloLens více dat o tom, kde jsou body vzájemně relativní.  

Pokud například nevyhledáte holoLens, nemusí vědět, kde je strop v místnosti.  

Při mapování prostoru se nezapomeňte podívat dolů na podlaží.

### <a name="cover-key-areas-multiple-times"></a>Vícenásobné pokrytí klíčových oblastí

Vícenásobný přesun oblasti vám pomůže vybrat funkce, které jste v prvním názorném postupu vynechali. Pokud chcete vytvořit ideální mapu, zkuste dvakrát až třikrát pro procházení oblasti.

Pokud je to možné, při opakování těchto pohybů věnujte čas tomu, abyste procházeli oblastí v jednom směru, pak se otočíte a vrátíte se zpět.

### <a name="take-your-time-mapping-the-area"></a>Udělejte si čas namapování oblasti

Může trvat 15 až 20 minut, než se HoloLens plně namapuje a přizpůsobí svému okolí. Pokud máte prostor, ve kterém plánujete holoLens často používat, může pozdějšímu namapování prostoru zabraňovat problémům.  

## <a name="possible-errors-in-the-spatial-map"></a>Možné chyby v prostorové mapě

Chyby v datech prostorového mapování spadají do několika kategorií:

- *Otvory:* V datech prostorového mapování chybí povrchy z reálného světa.
- *Halukuna:* Povrchy existují v datech prostorového mapování, která neexistují ve skutečném světě.
- *Wormholes*: HoloLens "ztratí" část prostorové mapy tím, že si myslí, že je v jiné části mapy než ve skutečnosti.
- *Předsudky:* Povrchy v datech prostorového mapování jsou nedokonalě zarovnané s reálnými povrchy, buď nasazované, nebo vytahované.

Pokud se zobrazí jakákoli z těchto chyb, pošlete nám svůj názor na [FeedbackHub.](hololens-feedback.md)

## <a name="security-and-storage-for-spatial-data"></a>Zabezpečení a úložiště prostorových dat

Windows 10 verze 1803 pro Microsoft HoloLens a novější ukládá data mapování v místní databázi (na zařízení).

Uživatelé HoloLens nemohou získat přímý přístup k databázi mapy, a to ani v případě, že je zařízení připojené k počítači nebo Průzkumník souborů aplikaci. Když je na HoloLens povolený BitLocker, zašifrují se také uložená data mapy společně s celým svazkem.

### <a name="remove-map-data-and-known-spaces-from-hololens"></a>Odebrání dat mapy a známých prostorů z HoloLens

Existují dvě možnosti odstranění dat mapy v **Nastavení > System > Hologramy:**

- Pokud chcete odstranit hologramy v okolí, vyberte **Odebrat hologramy v okolí.** Tento příkaz vymaže data mapy a ukotvené hologramy pro aktuální prostor. Pokud budete zařízení dál používat ve stejném prostoru, vytvoří a uloží zcela novou sekci mapy, která nahradí odstraněné informace.

   > [!NOTE]
   > Hologramy "blízkých" jsou hologramy ukotvené v rámci stejného oddílu mapy v aktuálním prostoru.

   Tuto možnost můžete například použít k vymazání dat map souvisejících s prací, aniž by to ovlivnilo jakákoli data mapy související s domovskou stránku.

- Pokud chcete odstranit všechny hologramy, vyberte **Odebrat všechny hologramy.** Tento příkaz vymaže všechna mapová data uložená v zařízení i všechny ukotvené hologramy. Všechny hologramy budete muset explicitně umístit. Dříve umístěné hologramy nebudete moct znovu najít.

> [!NOTE]
> Po odebrání blízkých nebo všech hologramů začne HoloLens okamžitě skenovat a mapovat aktuální prostor.

### <a name="wi-fi-data-in-spatial-maps"></a>Wi-Fi dat v prostorových mapách

HoloLens ukládá Wi-Fi, které pomáhají korelovat umístění hologramů a oddíly map, které jsou uložené v databázi HoloLens známých prostorů. Informace o Wi-Fi charakteristiky nejsou uživatelům přístupné a neposílané Microsoftu pomocí cloudu nebo telemetrie.

Pokud je Wi-Fi povoleno, HoloLens koreluje data map s blízkými Wi-Fi přístupových bodů. Bez ohledu na to, jestli je síť připojená nebo detekována blízko, není v chování žádný rozdíl. Pokud Wi-Fi zakázaná, HoloLens stále prohledá prostor. HoloLens ale musí prohledávat více dat mapy v rámci databáze prostorů a může potřebovat více času na nalezení hologramů. Bez Wi-Fi musí HoloLens porovnat aktivní kontroly se všemi kotvami hologramů a oddíly mapy, které jsou uložené v zařízení, aby bylo možné najít správnou část mapy.

## <a name="related-topics"></a>Související témata

- [Návrh prostorového mapování](https://docs.microsoft.com/windows/mixed-reality/spatial-mapping)
