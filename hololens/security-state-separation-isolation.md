---
title: Oddělení a izolace stavu
description: přečtěte si o odděleních stavu, izolaci, podepisování kódu a aplikacích defenderu na vašem zařízení HoloLens 2 mixed reality.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: zabezpečení, HoloLens, oddělení stavu, oddělení stavu a izolace, HoloLens 2, hololens2 zabezpečení, Přehled zabezpečení, Architektura zabezpečení, architektura, architektura HoloLens 2
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 0487ea49c706c753f4dfca7da7daa499d1715e9f
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428427"
---
# <a name="state-separation-and-isolation"></a>Oddělení a izolace stavu

Oddělení a izolace stavu chrání kritické části operačního systému HoloLens 2, například ty, které jsou potřeba k tomu, aby se operační systém spouštěl do důvěryhodného stavu. Díky technologii izolace jsou nedůvěryhodné aplikace přesunuty do izolovaného prostředí izolovaného prostoru (sandbox), aby se zajistilo, že nebudou mít vliv na zabezpečení systému.

## <a name="state-separation"></a>Oddělení stavu

oddělení stavu HoloLens 2 značně vylepšuje zabezpečení a použitelnost (aktualizace) a pomáhá chránit data aplikací.  Oddělení stavu funguje následujícím způsobem:
  * Základní operační systém je uložený ve svazku základního operačního systému (důvěryhodný nebo ověřený operační systém Microsoft pro aktualizaci operačního systému).
  * Části operačního systému, které se dají změnit za běhu (například ovladače a konfigurace ke stažení), umožňují rozdělit data na oddíly a ukládat je do zabezpečených, oddělených umístění úložiště.
  * Každé umístění zabezpečeného úložiště má jedinečné zásady zabezpečení, které jsou k němu přidružené, a nabízí různé výhody zabezpečení, jak je popsáno v následující části.

## <a name="state-separation-benefits"></a>Výhody oddělení stavu

  * zabezpečení: oddělení stavu HoloLens 2 významně vylepšuje integritu platformy, odolnost proti malwaru a ochranu uživatelských dat. Oddělením neměnitelné části operačního systému a tím, že je jen pro čtení nebo chráněná integrita, je rozdělení stavu velmi obtížné, aby se malware zachoval po studeném restartování. 
  * aktualizace: u HoloLens 2 platí, že jakmile je základní operační systém neupravitelný a byl čistě oddělený od zbytku dat v zařízení, aktualizace budou jednoduché a spolehlivé.  Kromě toho oddělení stavu stanoví zásadní základy pro výrazně rychlejší aktualizace, což umožňuje, aby se operační systém nahradil v jednom kroku (atomická jednotka).
  * resetování zařízení: HoloLens 2 resetuje vymazávání dat generovaných uživatelem a uživatelských aplikací na zařízení – včetně umístění interního a externího úložiště. Zachovává aktuální aplikace pro operační systém a kritické aplikace zabezpečení a aktuální aplikace přizpůsobené od Microsoftu a OEM (předinstalované). Tyto předinstalované aplikace je možné po dokončení resetování znovu zapnout v zařízení.

### <a name="state-separation-states"></a>Stavy oddělení stavu

Oddělení stavu zajišťuje, aby operační systém mohl změnit pouze součásti důvěryhodných zařízení společnosti Microsoft a aby bylo možné zachovat pouze stav vysoké hodnoty v rámci restartování. jiný stav systému existuje jenom po dobu trvání relace spuštění a po restartování se zahodí. Oddělení stavu rychle vrátí zařízení zpátky do továrního stavu. Windows Holographic for Business stavy lze rozdělit do těchto různých kategorií:
  * Základní operační systém – stav bez úprav
  * Data operačního systému – měnitelné stavy 
  * Uživatelská data – měnitelné stavy

každý z těchto HoloLens 2 – provozní stavy jsou popsány v následující části.

#### <a name="core-operating-system"></a>Základní operační systém

Neproměnlivý stav se skládá ze spustitelných souborů a dat, která nelze měnit a kterou může změnit pouze společnost Microsoft při instalaci aktualizací. Během takové aktualizace základního operačního systému je povolená nová image obsahující nejnovější požadovaný provozní stav.
Nezměněný stav je označen jako jen pro čtení (nebo je jinak chráněn integritou) a brání tak trvalému malwaru se zvýšenými oprávněními. Následující spustitelné soubory a data jsou chráněny v neměnném stavu:
  * Windows Ovladače holografické pošty
  * Binární soubory operačního systému
  * ovladače Windows doručených zpráv
  * nastavení statických Windows holografických uložení v podregistru Windows registru (HKLM)
    * Příklad: HKLM ukládá informace o konfiguraci aplikací nainstalovaných v počítači. Také ukládá informace k detekci hardwaru a odpovídajících ovladačů.
Díky ochraně těchto v neměnném stavu (integrita a jen pro čtení) zajišťujeme, aby se základní operační systém vždy spouštěl do důvěryhodného stavu. Když se zařízení resetuje, můžeme se ujistit, že se zařízení spouští jenom na součásti, které jsou v tomto neměnném oddílu. 

#### <a name="operating-system-data"></a>Data operačního systému 

Je důležité si uvědomit, že spustitelné soubory a data, která se mění za běhu (a nejsou důležité pro funkci operačního systému), je možné zahodit a znovu vytvořit, když jsou data poškozená nebo ohrožená. stav, který lze změnit na vysokou hodnotu, je buď funkčně nutný k uchování v operačním systému, nebo v případě výpadku operačního systému a při restartování prostřednictvím podporovaných Windows scénářů operačního systému a zařízení. Příklady proměnlivého stavu vysoké hodnoty jsou:
  * Správce IT nakonfiguroval globální nastavení zařízení, například zakázání umístění pro všechny uživatele.
  * Přístup k datům síťového připojení sítě Wi-Fi – zařízení – zapamatovatelné sítě a přidružená hesla připojení
  * Výpisy stavu systému včetně nastavení, protokolů.
  * Ovladače stažené na vyžádání nově zjištěných zařízení.
stav, který může být ve stavu HoloLens 2 v umístění s vysokou hodnotou, se nachází v umístění zabezpečení dat operačního systému, a to buď jako uložený soubor na disku, nebo v trvalém podregistru.

#### <a name="user-data"></a>Uživatelská data

Poslední kategorie stavu představuje uživatelská data vytvořená nebo trvalá aplikacemi UWP nebo operačním systémem. V tomto umístění jsou uloženy také všechny známé složky uživatele, například soubory ke stažení, dokumenty, videa, profily uživatelů a HKEY_CURRENT_USER podregistr. Tato data se nedají extrahovat bez správných přihlašovacích údajů. Další informace o tom, jak jsou vaše data chráněná, najdete v tématu [šifrování a ochrana dat](security-encryption-data-protection.md).

##  <a name="isolation"></a>Izolace

pro dosažení tohoto zůstatku HoloLens 2 má základní operační systém, který se používá pro primární funkce, jako je spouštění, řízení hardwaru, protokolování atd. Existují jenom dvě sady aplikací, které běží na základním operačním systému – předem nainstalované aplikace a aplikace pro UWP.

## <a name="code-signing"></a>Podepisování kódu

Digitální podepisování kódu umožňuje odůvodnění, že se spustitelné soubory a skripty nezměnily, protože byly podepsány důvěryhodným zdrojem, proto by poskytovala pravost a integritu. autority, které ve výchozím nastavení HoloLens 2 důvěřují, jsou Microsoft a Microsoft Store. Správci IT můžou do zařízení přidávat nové certifikáty prostřednictvím CSP [ClientCertificateInstall](/windows/client-management/mdm/clientcertificateinstall-csp) a [RootCATrustedCertificates](/windows/client-management/mdm/rootcacertificates-csp) . Můžou taky používat [zásady AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) k tomu, aby důvěřovaly dalším zkušebně načtené nebo [obchodním aplikacím](/intune/apps/lob-apps-windows). Certifikáty se nacházejí v úložišti certifikátů místního počítače, které je uloženo v klíči HKLM/root, pokud používáte "zařízení" nebo "v rozhraní HKCU", pokud používáte "User".

## <a name="defender-protections"></a>Ochrana v programu Defender
HoloLens 2 používá služby Microsoft k poskytnutí pokročilé úrovně zabezpečení pro uživatele:

* [filtr SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) je automaticky povolený pro Windows holografický operačním systémem a chrání před phishingem a malwarem a také stahování potenciálně škodlivých souborů na hraničních zařízeních. Nemůže být vypnutá uživatelem, ale dá se zakázat prostřednictvím zásad.

* [Firewall Defenderu](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) blokuje neoprávněný síťový provoz z vašeho zařízení a z něj. Ve výchozím nastavení je povolená a zákazník ho nemůže konfigurovat prostřednictvím místních akcí nebo zásad. 

* [Windows Defender řízení aplikací](/windows/security/threat-protection/windows-defender-application-control/wdac-and-applocker-overview): HoloLens 2 podporuje WDAC, který umožňuje správci IT zaručovat do zařízení zásady řízení aplikací. další informace najdete v [WDACě v zařízení s HoloLens 2 s použitím protokolu MSFT intune](/mem/intune/configuration/custom-profile-hololens). 

Správci IT můžou pomocí [těchto zásad](/windows/client-management/mdm/policy-csps-supported-by-hololens2)spravovat chování SmartScreen prostřednictvím [AllowSmartScreen](/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen) a chování prohlížeče. 

