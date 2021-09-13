---
title: Mapování fyzických prostorů pomocí HoloLens
description: HoloLens zjistí, jak prostor v průběhu času vypadá. Uživatelé mohou tento proces usnadnit přesunutím HoloLens různými způsoby přes prostor.
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
ms.openlocfilehash: b8bda049f0ef4610dcf0ca6fe81d89dd5a316e3e
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126035984"
---
# <a name="map-physical-spaces-with-hololens"></a>Mapování fyzických prostorů pomocí HoloLens

HoloLens spojuje hologramy s fyzickým světem. Aby to bylo HoloLens, musí se dozvědět o fyzickém světě kolem vás a pamatovat si, kam do tohoto prostoru umístit hologramy.

V průběhu času HoloLens vytvoří prostorovou *mapu* prostředí, které viděl.  HoloLens aktualizuje mapu při změně prostředí. Dokud jste přihlášeni a zařízení je zapnuté, můžete HoloLens prostorové mapy a aktualizovat je. Pokud zařízení držíte nebo opotřebováte fotoaparáty, které jsou HoloLens prostoru, pokusí se oblast mapovat. Přestože HoloLens se naučí prostor přirozeně v průběhu času, existují způsoby, jak můžete HoloLens prostor rychleji a efektivněji mapovat.  

> [!NOTE]
> Pokud HoloLens váš prostor namapovat nebo vám to nevypadne, HoloLens do omezeného režimu. V omezeném režimu nebudete moct hologramy umístit do svého okolí.

Tento článek vysvětluje, HoloLens mapovat prostory, jak vylepšit prostorové mapování a jak spravovat prostorová data, která HoloLens shromažďuje.

## <a name="choosing-and-setting-up-and-your-space"></a>Volba a nastavení a prostor

Funkce ve vašem prostředí mohou ztížovat interpretaci HoloLens prostoru pro uživatele. Úrovně světla, materiály v prostoru, rozložení objektů a další mohou ovlivnit, HoloLens mapují oblast.

HoloLens funguje nejlépe v určitých typech prostředí. Pokud chcete vytvořit nejlepší prostorovou mapu, zvolte místnost, která má dostatečné světlo a dostatek místa. Vyhněte se tmavým prostorům a místnostem, které mají spoustu tmavých, šišitých nebo průsvitných povrchů (například zrcadla nebo vousy).

HoloLens je optimalizovaný pro použití v interiérech. Prostorové mapování funguje nejlépe Wi-Fi je zapnuté, i když nemusí být připojené k síti. HoloLens přístupové body Wi-Fi, i když nejsou připojené nebo ověřené. HoloLens funkčnosti se nezmění, jestli jsou přístupové body připojené k internetu, nebo jenom k intranetu nebo místnímu prostředí.

Používejte HoloLens na bezpečných místech bez rizika při vyjetí. [Další informace o bezpečnosti](https://support.microsoft.com/help/4023454/safety-information)

## <a name="mapping-your-space"></a>Mapování prostoru

Teď jste připraveni začít mapovat náhradní.  Když HoloLens namapovat okolí, uvidíte, jak se po prostoru rozprostíří grafické prvky ze sítě.  V domovském prostředí hybridní reality můžete aktivovat zobrazení mapy výběrem na mapované ploše.

Tady jsou pokyny pro vytvoření skvělé prostorové mapy.

### <a name="understand-the-scenarios-for-the-area"></a>Pochopení scénářů pro oblast

Je důležité strávit nejvíce času tím, že budete používat HoloLens, aby mapa byla relevantní a úplná. Pokud například uživatelský scénář pro HoloLens zahrnuje přechod z bodu A na bod B, projděte si cestu dvakrát až třikrát a při pohybu se díváte ve všech směrech.  

### <a name="walk-slowly-around-the-space"></a>Pomalu procházte prostor

Pokud se po této oblasti budete příliš rychle procházet, je pravděpodobné, že HoloLens oblasti mapování. Pomalu si projděte prostor a každých 5 až 8 stop se zastavujte, abyste se podívali na okolí.  

Hladké pohyby také pomáhají HoloLens mapy efektivněji.

### <a name="look-in-all-directions"></a>Hledejte ve všech směrech.

Při pohledu na mapu prostoru získáte HoloLens dat o tom, kde jsou body vzájemně relativní.  

Pokud například nevyhledáte, nemusí HoloLens, kde je strop v místnosti.  

Při mapování prostoru se nezapomeňte podívat dolů na podlaží.

### <a name="cover-key-areas-multiple-times"></a>Vícenásobné pokrytí klíčových oblastí

Vícenásobný přesun oblasti vám pomůže vybrat funkce, které jste v prvním názorném postupu vynechali. Pokud chcete vytvořit ideální mapu, zkuste dvakrát až třikrát pro procházení oblasti.

Pokud je to možné, při opakování těchto pohybů věnujte čas tomu, abyste procházeli oblastí v jednom směru, pak se otočíte a vrátíte se zpět.

### <a name="take-your-time-mapping-the-area"></a>Udělejte si čas namapování oblasti

Může trvat 15 až 20 minut, než se HoloLens úplně namapuje a přizpůsobí svému okolí. Pokud máte prostor, ve kterém máte v plánu používat HoloLens čas předem, může pozdějšímu namapování prostoru zabránit problémům.  

## <a name="possible-errors-in-the-spatial-map"></a>Možné chyby v prostorové mapě

Chyby v datech prostorového mapování spadají do několika kategorií:

- *Otvory:* V datech prostorového mapování chybí reálné povrchy.
- *Halukuna:* Povrchy existují v datech prostorového mapování, která neexistují ve skutečném světě.
- *Wormholes*: HoloLens prostorové mapy "ztratí" tím, že si myslí, že je v jiné části mapy, než ve skutečnosti je.
- *Předsudky:* Povrchy v datech prostorového mapování jsou nedokonalě zarovnané s reálnými povrchy, buď nasazované, nebo vytažené.

Pokud se zobrazí jakákoli z těchto chyb, pošlete nám svůj názor na [FeedbackHub.](hololens-feedback.md)

## <a name="security-and-storage-for-spatial-data"></a>Zabezpečení a úložiště prostorových dat

Windows 10 verze 1803 pro Microsoft HoloLens a novější ukládá data mapování v místní databázi (na zařízení).

HoloLens uživatelé nemohou získat přímý přístup k databázi mapy, a to ani v případě, že je zařízení připojené k počítači nebo Průzkumník souborů aplikaci. Když je bitLocker povolený HoloLens, zašifrují se také uložená data mapy společně s celým svazkem.

### <a name="remove-map-data-and-known-spaces-from-hololens"></a>Odebrání dat mapy a známých prostorů z HoloLens

Existují dvě možnosti odstranění mapových dat v **nástroji Nastavení > System > Hologramy**:

- Pokud chcete odstranit hologramy v okolí, vyberte **Odebrat hologramy v okolí.** Tento příkaz vymaže data mapy a ukotvené hologramy pro aktuální prostor. Pokud budete zařízení dál používat ve stejném prostoru, vytvoří a uloží zcela novou sekci mapy, která nahradí odstraněné informace.

   > [!NOTE]
   > Hologramy "blízkých" jsou hologramy ukotvené v rámci stejného oddílu mapy v aktuálním prostoru.

   Tuto možnost můžete například použít k vymazání dat map souvisejících s prací, aniž by to ovlivnilo jakákoli data mapy související s domovskou stránku.

- Pokud chcete odstranit všechny hologramy, vyberte **Odebrat všechny hologramy.** Tento příkaz vymaže všechna mapová data uložená v zařízení i všechny ukotvené hologramy. Všechny hologramy budete muset explicitně umístit. Dříve umístěné hologramy nebudete moct znovu najít.

> [!NOTE]
> Po odebrání blízkých nebo všech hologramů můžete HoloLens začít s prohledáváním a mapováním aktuálního prostoru.

### <a name="wi-fi-data-in-spatial-maps"></a>Wi-Fi dat v prostorových mapách

HoloLens úložiště Wi-Fi charakteristiky, které pomáhají korelovat umístění hologramů a oddíly map, které jsou uložené v HoloLens databáze známých prostorů. Informace o Wi-Fi charakteristiky nejsou přístupné pro uživatele a neposílané Microsoftu pomocí cloudu nebo telemetrie.

Pokud je tato Wi-Fi povolená, HoloLens mapová data koreluje s blízkými Wi-Fi přístupových bodů. Bez ohledu na to, jestli je síť připojená nebo detekována v okolí, není v chování žádný rozdíl. Pokud Wi-Fi zakázaná, HoloLens prostor stále prohledá. Ale HoloLens více dat mapy v rámci databáze prostorů a může potřebovat více času na nalezení hologramů. Bez Wi-Fi musí HoloLens porovnat aktivní kontroly se všemi ukotveními hologramů a oddíly mapy, které jsou uložené v zařízení, aby bylo možné najít správnou část mapy.

## <a name="related-topics"></a>Související témata

- [Návrh prostorového mapování](/windows/mixed-reality/spatial-mapping)
