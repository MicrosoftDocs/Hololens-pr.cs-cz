---
title: 'HoloLens 2: Ochrana osobních údajů a ochrana dat'
description: Dokumentace k ochraně osobních údajů
keywords: HoloLens, GDPR, ochrana osobních údajů, PII, ochrana dat
author: golish
ms.author: marcingo
ms.reviewer: sekerawa, evmiller
ms.date: 02/05/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 74f74645a3fc1282f48cb7ce0f6f722979c91b04
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032267"
---
# <a name="hololens-2-privacy-and-data-protection"></a>HoloLens 2: Ochrana osobních údajů a ochrana dat

Jedním ze základních prvků nařízení GDPR je "ochrana dat ze návrhu". Tento koncept platí zejména pro mobilní zařízení, jako je HoloLens 2, a to kvůli jejich přenositelnosti, neomezenému počtu připojení k internetu a otevřeným komunikačním kanálům. V důsledku toho se zabezpečení HoloLens [](/hololens/security-architecture) 2 přepracovalo tak, aby poskytovalo pokročilé, inovativní zabezpečení a ochranu osobních údajů, a to od konce do konce a začlenění přístupu Microsoftu k ochraně osobních údajů a nařízení [GDPR](https://privacy.microsoft.com/).

 >[!NOTE]
> Tento dokument se nevztahuje na HoloLens (1. generace).

## <a name="privacy-overview"></a>Přehled ochrany osobních údajů

HoloLens 2 je samostatný počítač Windows se systémem Windows Holographic, který spouští aplikace a řešení v imerzivním prostředí hybridní reality. Můžete ho použít jako zabezpečené offline zařízení nebo ho nasadit jako [spravované zařízení](/mem/intune/fundamentals/windows-holographic-for-business) ve vaší organizaci. Následující odkazy vám porozumí, jak HoloLens 2 a Microsoft vaše data používají a chrání:

1. [Prohlášení o zásadách ochrany HoloLens](https://privacy.microsoft.com/privacystatement) společnosti Microsoft – rozbalte část Enterprise and **developer** v levé navigační nabídce a vyberte Enterprise a vývojářský software a **zařízení.** Přejděte do **části HoloLens.**
2. [Windows 10 a online služby](https://privacy.microsoft.com/windows10privacy)
3. [Windows 10 & dodržování předpisů pro ochranu osobních údajů](/windows/privacy/windows-10-and-privacy-compliance)
4. [Ochrana soukromí a osobní údaje v Intune](/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>Zabezpečení sítě
V souladu HoloLens 2 [běžných](/hololens/common-scenarios)scénářů nasazení budou vaše data chráněna prvotřídním dodržováním předpisů Azure spolu [s](/azure/compliance/) integrací právních a zákonných standardů. Pokud s Azure AD a Dynamics 365 Remote Assistem je pro vás novinka, přečtěte si kontrolní seznam připravenosti na odpovědnost v Azure a [Dynamics 365 pro GDPR.](/compliance/regulatory/gdpr-arc-azure-dynamics)

Kromě toho Windows Defender Firewall poskytuje důležité funkce pro zabezpečení připojení zařízení. Při HoloLens 2 je brána firewall vždycky povolená a neexistuje žádný způsob, jak ji programově nebo prostřednictvím uživatelského rozhraní zakázat. Když se HoloLens 2 nasadí jako spravované zařízení pomocí [Intune,](/mem/intune/protect/device-compliance-get-started)bude k dispozici další funkce dodržování předpisů s integrací služby Endpoint s [Microsoft Intune](/mem/intune/protect/advanced-threat-protection) jako řešením Mobile Threat Defense.

Přečtěte si další informace o zabezpečení a [architektuře](/hololens/security-architecture)HoloLens 2.

## <a name="os-security"></a>Zabezpečení operačního systému
Aktualizace se provádí automaticky (ve výchozím nastavení), takže HoloLens 2 je vždy aktuální s nejnovější verzí Windows Holographic a všech nainstalovaných aplikací. Pokud chcete lépe pochopit, jak je náš operační systém bezpečně navržený, projděte si následující témata:

1. [Oddělení a izolace stavu](/hololens/security-state-separation-isolation)
1. [Operační systém bez oprávnění správce](/hololens/security-adminless-os)
1. [Omezení použití hesla](/hololens/security-limiting-password-use)

## <a name="physical-security"></a>Fyzické zabezpečení
HoloLens 2 má paměť flash, která je chráněná [šifrováním BitLockeru.](/hololens/security-encryption-data-protection) Zařízení a jeho místní data je možné pomocí [doprovodných](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) funkcí Advanced Recovery Companion blikat do režimu offline nebo vzdáleně vymazat přes MDM, pokud bylo nasazeno jako spravované zařízení.

## <a name="data-protection"></a>Ochrana dat
Windows se automaticky (ve výchozím nastavení) a integrace [Azure](/hololens/security-encryption-data-protection#Azure-integration) chrání data mezi sebou a cloudem.

Při nasazování HoloLens 2 na externí klienty [zajišťuje Dynamics 365 Remote Assist,](/hololens/hololens2-deployment-guide) aby vaše citlivá firemní data a prostředky byly oddělené a bezpečné.

Sdílení diagnostických dat s Microsoftem může při spuštění počítače ručně nakonfigurovat MDM nebo uživatel. Existují dvě možnosti: volitelná diagnostická data a požadovaná diagnostická data. Pokud je potřeba původní nastavení diagnostiky později změnit pro účely řešení potíží, může ho uživatel změnit v nastavení ochrana osobních údajů v jazyce **Nastavení -> -> Diagnostics & Feedback** nebo Správce IT (MDM), pokud se jedná o spravované zařízení. Další informace o [diagnostice, zpětné vazbě a ochraně osobních údajů](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319)najdete v Windows 10 .

> [!Important]
> Diagnostické protokoly zařízení obsahují identifikovatelné osobní údaje ( PII), například o tom, jaké procesy nebo aplikace uživatel spouští během běžných operací. Když zařízení HoloLens sdílí více uživatelů (například se uživatelé přihlašuje ke stejnému zařízení pomocí různých účtů služby Microsoft Azure Active Directory (Azure AD), diagnostické protokoly mohou obsahovat informace o PII, které platí pro více uživatelů.

Existuje několik [metod shromažďování a zásad uchovávání dat](/hololens/hololens-diagnostic-logs) pro shromažďování diagnostických dat z HoloLens 2.  Další informace o tom, jak Microsoft shromažďuje a používá diagnostická data, najdete v tématu [Prohlášení o](https://privacy.microsoft.com/privacystatement) zásadách ochrany osobních údajů společnosti Microsoft – diagnostika – **rozbalte Windows** v levé navigační nabídce a vyberte **Diagnostika.** Přejděte do **části Diagnostika.**
