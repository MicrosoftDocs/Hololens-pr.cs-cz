---
title: Oddělení a izolace stavu
description: Seznamte se s aplikacemi pro oddělení stavu, izolaci, podepisování kódu a defender na zařízení s hybridní realitou HoloLens 2.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, State Separation, State Separation and Isolation, hololens 2, hololens2 security, security overview, security architecture, architecture, hololens 2 architecture
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 60d6d7c0e281395957ce9158144a5f3d60927682
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379298"
---
# <a name="state-separation-and-isolation"></a>Oddělení a izolace stavu

Oddělení a izolace stavu chrání důležité části operačního systému Hololens 2 před změnou – například ty, které jsou nutné pro spuštění operačního systému do důvěryhodného stavu. Díky technologii izolace se nedůvěryhodné aplikace přesunou do izolovaného prostředí sandboxu, aby se zajistilo, že neovlivní zabezpečení systému.

## <a name="state-separation"></a>Oddělení stavu

Oddělení stavu na HoloLens 2 výrazně zlepšuje zabezpečení a použitelnost (aktualizace) a pomáhá chránit data aplikací.  Oddělení stavu funguje takto:
  * Základní operační systém je uložený na svazku základního operačního systému (důvěryhodný nebo ověřený operační systém Microsoftu, který aktualizuje operační systém).
  * Části operačního systému, které je možné změnit za běhu (například ovladače a konfigurace ke stažení), používají další oddělení stavu k rozdělení dat a jejich uložení do zabezpečených samostatných umístění úložiště.
  * Ke každému zabezpečenému umístění úložiště jsou přidružené odlišné zásady zabezpečení, které nabízejí různé výhody zabezpečení, které jsou podrobně uvedená v následující části.

## <a name="state-separation-benefits"></a>Výhody oddělení států

  * Zabezpečení: Oddělení stavu, které je v HoloLens 2, výrazně zlepšuje integritu platformy, odolnost proti malwaru a ochranu uživatelských dat. Oddělením nealterovatelné části operačního systému a zajištěním, že je jen pro čtení nebo chráněná proti integritě, je oddělení stavu velmi obtížné, aby se malware při studeném restartování uchoval. 
  * Aktualizace: S HoloLens 2 se aktualizace stávají jednoduchými a spolehlivými, jakmile je základní operační systém neupravitelný a je dobře oddělený od ostatních dat v zařízení.  Kromě toho oddělení stavu popisuje zásadní základ pro dramaticky rychlejší aktualizace, které umožňují nahradit operační systém v jednom kroku (atomická jednotka).
  * Resetování zařízení: Resetování HoloLens 2 vymaže data vygenerovaná uživatelem a data uživatelských aplikací na zařízení – včetně interních a externích umístění úložiště. Zachovává aktuální aplikace operačního systému a aplikace kritické pro zabezpečení a aktuální přizpůsobené aplikace Microsoftu a OEM (předinstalované). Po dokončení resetování je možné tyto předinstalované aplikace do zařízení znovu dosadět.

### <a name="state-separation-states"></a>Stavy oddělení stavu

Oddělení stavu zajišťuje, aby operační systém mohl být změněn jenom důvěryhodnými komponentami zařízení Microsoftu a aby se po restartování mohl zachovat jenom stav s vysokou hodnotou. Jiný stav systému existuje jenom po dobu trvání relace spuštění a po restartování se zahodí. Oddělení stavu rychle vrátí zařízení zpět do továrního stavu. Windows Holographic for Business stavy lze rozdělit do těchto odlišných kategorií:
  * Základní operační systém – Nealterovatelný stav
  * Data operačního systému – měnitelný stav 
  * Uživatelská data – měnitelný stav

Každý z těchto provozních stavů HoloLens 2 je popsán v následující části.

#### <a name="core-operating-system"></a>Základní operační systém

Neměnný stav se skládá ze spustitelných souborů a dat, které jsou nealterovatelné a mohou být změněny společností Microsoft pouze během instalace aktualizací. Během takové aktualizace základního operačního systému se povolí nová image obsahující nejnovější požadovaný provozní stav.
Nealterovatelný stav je označený jako jen pro čtení (nebo je jinak chráněný integritou), což brání trvalosti jakéhokoli malwaru se zvýšenými oprávněními. Následující spustitelné soubory a data jsou chráněny v neměnném stavu:
  * Ovladače doručené pošty s Windows Holographic
  * Binární soubory operačního systému
  * Ovladače doručené pošty ve Windows
  * Statická nastavení Windows Holographic uložená v podregistru registru Windows (HKLM)
    * Příklad: HKLM ukládá informace o konfiguraci aplikací nainstalovaných na počítači. Ukládá také informace pro detekci hardwaru a odpovídajících ovladačů.
Tím, že je chráníme v neměnném stavu (integrity a chráněném jen pro čtení), zajišťujeme, že se základní operační systém vždy spustí do důvěryhodného stavu. Kromě toho můžeme při resetování zařízení zajistit, že se zařízení spustí jenom do komponent, které jsou v této neměnné části. 

#### <a name="operating-system-data"></a>Data operačního systému 

Je důležité si uvědomit, že spustitelné soubory a data, která je možné měnit za běhu (a která nejsou pro funkci operačního systému zásadní), je možné zahodit a znovu vytvořit, když jsou data poškozena nebo ohrožena. Pro zachování operačního systému, nebo se očekává zachování během vypínání operačního systému nebo při různých restartováních podporovaných scénářů operačního systému Windows a zařízení, se vyžaduje funkční stav s vysokou hodnotou. Mezi příklady stavů s vysokou hodnotou, které lze přeměnovat, patří:
  * Globální nastavení zařízení nakonfigurovaná správcem IT, například zakázání umístění pro všechny uživatele.
  * Připojení k síti Wi-Fi přistupuje k sítím, které si zařízení zapamatuje, a k přidruženým hesly připojení.
  * Výpisy stavu systému včetně nastavení a protokolů.
  * Ovladače stažené na vyžádání pro nově zjištěná zařízení.
Vysoce hodnotný měnitelný stav v HoloLens 2 se nachází v umístění zabezpečení dat operačního systému, a to buď jako uložený soubor na disku, nebo v trvalém podregistru registru.

#### <a name="user-data"></a>Uživatelská data

Poslední kategorie stavu představuje uživatelská data vytvořená nebo uchovaná aplikacemi UPW nebo operačním systémem. V tomto umístění jsou uložené také všechny známé složky uživatelů, jako jsou soubory ke stažení, dokumenty, videa, profily HKEY_CURRENT_USER a podregistr. Tato data nelze extrahovat bez správných přihlašovacích údajů. Další informace o tom, jak jsou vaše data chráněná, najdete v tématu Šifrování a [ochrana dat.](security-encryption-data-protection.md)

##  <a name="isolation"></a>Izolace

K dosažení této rovnováhy má HoloLens 2 základní operační systém, který se používá pro primární funkce, jako je spouštění, ovládání hardwaru, přihlašování atd. Existují pouze dvě sady aplikací, které běží na základním operačním systému – předinstalovaných aplikací a aplikací pro UPW.

## <a name="code-signing"></a>Podepisování kódu

Digitální podepisování kódu umožňuje určit, že spustitelné soubory a skripty nebyly změněny, protože byly podepsány důvěryhodným zdrojem, a proto poskytují pravost a integritu. Autority, které HoloLens 2 ve výchozím nastavení důvěřuje, jsou microsoft a Microsoft Store. Správci IT můžou do zařízení přidat nové certifikáty prostřednictvím [csP ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) a [RootCATrustedCertificates.](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp) Mohou také použít zásadu [AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) k důvěřování dalším aplikacím s bočním načtením nebo obchodním [aplikacím](https://docs.microsoft.com/intune/apps/lob-apps-windows). Certifikáty se nacházejí v místním počítači úložiště certifikátů, které je uložené v HKLM/Root, pokud používáte "zařízení" nebo v HKCU, pokud používáte "uživatel".

## <a name="defender-protections"></a>Ochrany v programu Defender
HoloLens 2 služby Microsoft k zajištění pokročilé úrovně zabezpečení:

* [Filtr SmartScreen v](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) programu Defender je automaticky povolený na Zařízení s Windows Holographic operačním systémem a chrání před útoky phishing a malwarem a také stahování potenciálně škodlivých souborů v Edge. Uživatel ho nemůže vypnout, ale může ho zakázat prostřednictvím zásad.

* [Brána firewall v programu Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) blokuje tok neoprávněného síťového provozu do a z vašeho zařízení. Ve výchozím nastavení je povolená a zákazník ji nemůže konfigurovat prostřednictvím místních akcí nebo zásad. 

* [Windows Defender řízení aplikací:](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/wdac-and-applocker-overview)HoloLens 2 podporuje WDAC, což správci IT umožňuje na zařízení předá zásady řízení aplikací. Další informace najdete v článku Použití [WDAC na zařízeních HoloLens 2 s MSFT Intune.](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens) 

Správci IT mohou chování obrazovky SmartScreen spravovat prostřednictvím [funkce AllowSmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen) a chování prohlížeče prostřednictvím [těchto zásad.](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2) 

