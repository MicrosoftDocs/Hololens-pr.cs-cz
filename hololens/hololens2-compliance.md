---
title: Dodržování předpisů a NAŘÍZENÍ GDPR pro HoloLens 2
description: Dokumentace k GDPR
keywords: HoloLens, GDPR, ochrana osobních údajů, PII
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: skerewala, evmiller
ms.date: 02/05/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 8b795513d83c9d23f70b8dd8365e703d1fc43a51
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377720"
---
# <a name="hololens-2-privacy-statement"></a>Prohlášení o zásadách ochrany osobních údajů pro HoloLens 2

Jedním ze základních prvků nařízení GDPR je "ochrana dat ze návrhu". Tento koncept platí zejména pro mobilní zařízení, jako je HoloLens 2, kvůli jejich přenositelnosti, neomezenému počtu připojení k internetu a otevřeným komunikačním kanálům. V důsledku toho bylo zabezpečení holoLens 2 přepracováno tak, aby poskytovalo pokročilé, inovativní zabezpečení a ochranu osobních údajů, komplexní začlenění přístupu Microsoftu k ochraně osobních údajů a nařízení [GDPR](https://privacy.microsoft.com/). [](https://docs.microsoft.com/hololens/security-architecture)

 >[!NOTE]
> Tento dokument se nevztahuje na HoloLens (1. generace).

## <a name="privacy-overview"></a>Přehled ochrany osobních údajů

HoloLens 2 je samostatný počítač s Windows, na který běží Windows Holographic a který spouští aplikace a řešení v imerzivním prostředí hybridní reality. Můžete ho použít jako zabezpečené offline zařízení nebo ho nasadit jako [spravované zařízení](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business) ve vaší organizaci. Na následujících odkazech najdete informace o tom, jak HoloLens 2 a Microsoft používají a chrání vaše data:
1. [Prohlášení o zásadách ochrany osobních údajů společnosti Microsoft – HoloLens](https://privacy.microsoft.com/privacystatement) – v levé navigační nabídce rozbalte část Enterprise and **developer** a vyberte Enterprise and developer software and appliances (Podnikový **a vývojářský software a zařízení).** Přejděte do **části HoloLens.**
2.  [Windows 10 a online služby](https://privacy.microsoft.com/windows10privacy)
3.  [Windows 10 & dodržování předpisů pro ochranu osobních údajů](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
4.  [Ochrana soukromí a osobní údaje v Intune](https://docs.microsoft.com/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>Zabezpečení sítě
V souladu s běžnými scénáři nasazení HoloLens [2](https://docs.microsoft.com/hololens/common-scenarios)budou vaše data chráněna prvotřídním dodržováním předpisů [Azure](https://docs.microsoft.com/azure/compliance/) spolu s integrací právních a zákonných standardů. Pokud s Azure AD a Dynamics 365 Remote Assistem je pro vás novinka, přečtěte si kontrolní seznam připravenosti na odpovědnost v Azure a [Dynamics 365 pro GDPR.](https://docs.microsoft.com/compliance/regulatory/gdpr-arc-azure-dynamics)

Kromě toho Firewall v programu Windows Defender poskytuje důležité funkce pro zabezpečení připojení zařízení. U HoloLens 2 je brána firewall vždycky povolená a neexistuje žádný způsob, jak ji programově nebo prostřednictvím uživatelského rozhraní zakázat. Když se HoloLens 2 nasadí jako spravované zařízení pomocí [Intune,](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)je k dispozici další funkce dodržování předpisů s integrací koncového bodu se [službou Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection) jako řešením Mobile Threat Defense. 

Přečtěte si další informace o zabezpečení a [architektuře](https://docs.microsoft.com/hololens/security-architecture)HoloLens 2.

## <a name="os-security"></a>Zabezpečení operačního systému
Aktualizace se provádí automaticky (ve výchozím nastavení), takže holoLens 2 je vždy aktuální s nejnovější verzí Windows Holographic a všech nainstalovaných aplikací. Další informace o tom, jak je náš operační systém bezpečně navržený, najdete v následujících informacích:
1. [Oddělení a izolace stavu](https://docs.microsoft.com/hololens/security-state-separation-isolation)
1. [Operační systém bez oprávnění správce](https://docs.microsoft.com/hololens/security-adminless-os)
1. [Omezení použití hesla](https://docs.microsoft.com/hololens/security-limiting-password-use)

## <a name="physical-security"></a>Fyzické zabezpečení
HoloLens 2 má flash paměť, která je chráněná [šifrováním BitLockeru.](https://docs.microsoft.com/hololens/security-encryption-data-protection) Zařízení a jeho místní data je možné pomocí [doprovodných](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) funkcí Advanced Recovery Companion blikat do režimu offline nebo vzdáleně vymazat přes MDM, pokud bylo nasazeno jako spravované zařízení.

## <a name="data-protection"></a>Ochrana dat
Aktualizace Windows se spouštějí automaticky (ve výchozím nastavení) a [integrace Azure](https://docs.microsoft.com/hololens/security-encryption-data-protection#Azure-integration) chrání data mezi sebou a cloudem. 

Při nasazování HoloLens 2 na externí klienty [zajišťuje Dynamics 365 Remote Assist,](https://docs.microsoft.com/hololens/hololens2-deployment-guide) aby vaše citlivá firemní data a prostředky byly oddělené a bezpečné. 

Sdílení diagnostických dat s Microsoftem může při spuštění počítače ručně nakonfigurovat MDM nebo uživatel. Existují dvě možnosti: volitelná diagnostická data a požadovaná diagnostická data. Pokud je potřeba původní nastavení diagnostiky později změnit pro účely řešení potíží, může ho uživatel změnit v Nastavení -> Ochrana osobních údajů **-> Diagnostická & Zpětná** vazba nebo Správce IT (MDM), pokud se jedná o spravované zařízení. Další informace o [diagnostice, zpětné vazbě a ochraně osobních údajů](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319)najdete v Windows 10 .

> [!Important]
> Diagnostické protokoly zařízení obsahují identifikovatelné osobní údaje ( PII), například o tom, jaké procesy nebo aplikace uživatel spouští během typického provozu. Když zařízení HoloLens sdílí více uživatelů (například uživatelé se přihlásí ke stejnému zařízení pomocí různých účtů Microsoft Azure Active Directory (Azure AD), diagnostické protokoly mohou obsahovat informace o PII, které platí pro více uživatelů.

 

Existuje několik [metod shromažďování a zásad uchovávání dat](https://docs.microsoft.com/hololens/hololens-diagnostic-logs) pro shromažďování diagnostických dat z HoloLens 2.  Další informace o tom, jak Microsoft shromažďuje a používá diagnostická data, najdete v tématu [Prohlášení o](https://privacy.microsoft.com/privacystatement) zásadách ochrany osobních údajů společnosti Microsoft – Diagnostika – rozbalte v levé navigační nabídce možnost **Windows** a **vyberte Diagnostika.** Přejděte do **části Diagnostika.**
