---
title: HoloLens 2 – dodržování předpisů a GDPR
description: Dokumentace k GDPR
keywords: HoloLens, GDPR, soukromí, PII
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
ms.openlocfilehash: 684a97a4fcdc3aaf830f164c54fb3079e296c78c
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637111"
---
# <a name="hololens-2-privacy-statement"></a>HoloLens 2 – prohlášení o zásadách ochrany osobních údajů

Jedním z základních prvků GDPR je ochrana dat podle návrhu. tento koncept se vztahuje hlavně na mobilní zařízení, jako je HoloLens 2, kvůli jejich přenositelnosti, neomezenému připojení k internetu a otevřeným komunikačním kanálům. výsledkem je, že [zabezpečení](/hololens/security-architecture) HoloLens 2 bylo přepracováno, aby poskytovalo pokročilé, inovativní zabezpečení a ochranu osobních údajů, a to včetně přístupu microsoftu k [ochraně osobních údajů a GDPR předpisů](https://privacy.microsoft.com/).

 >[!NOTE]
> tento dokument se nevztahuje na HoloLens (1. generace).

## <a name="privacy-overview"></a>Přehled ochrany osobních údajů

HoloLens 2 je samostatný Windows počítač se spuštěným Windows holografickým, který spouští aplikace a řešení v moderním prostředí s moderní realitou. Dá se použít jako zabezpečené offline zařízení nebo se nasadí jako [spravované zařízení](/mem/intune/fundamentals/windows-holographic-for-business) v rámci vaší organizace. na následujících odkazech najdete informace o tom, jak HoloLens 2 a Microsoft používá a chrání vaše data:

1. [prohlášení o zásadách ochrany osobních údajů společnosti Microsoft – HoloLens](https://privacy.microsoft.com/privacystatement) – v levé navigační nabídce rozbalte část **Enterprise a vývojář** a vyberte **Enterprise a vývojářský software a zařízení**. přejít na část **HoloLens** .
2. [Windows 10 a online služby](https://privacy.microsoft.com/windows10privacy)
3. [průvodce dodržováním předpisů Windows 10 & ochrany osobních údajů](/windows/privacy/windows-10-and-privacy-compliance)
4. [Ochrana soukromí a osobní údaje v Intune](/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>Zabezpečení sítě
po [použití běžných scénářů nasazení](/hololens/common-scenarios)HoloLens 2 budou vaše data chráněna [špičkovým dodržováním předpisů Azure](/azure/compliance/) spolu s právními a zákonnými integrací standardů. Pokud s Azure AD a Dynamics 365 Remote Assist začínáte, [Projděte si kontrolní seznam připravenosti na odpovědnost Azure a dynamics 365 pro GDPR](/compliance/regulatory/gdpr-arc-azure-dynamics).

Windows Defender brána Firewall navíc přináší důležité funkce pro zabezpečení připojení zařízení. u HoloLens 2 je brána firewall vždycky zapnutá a neexistuje žádný způsob, jak ho deaktivovat programově nebo prostřednictvím uživatelského rozhraní. pokud je HoloLens 2 nasazena jako spravované zařízení pomocí [intune](/mem/intune/protect/device-compliance-get-started), je k dispozici více funkcí dodržování předpisů s integrací [koncového bodu s Microsoft Intune](/mem/intune/protect/advanced-threat-protection) jako řešení ochrany před mobilními hrozbami.

přečtěte si další informace o [architektuře a zabezpečení](/hololens/security-architecture)HoloLens 2.

## <a name="os-security"></a>Zabezpečení operačního systému
aktualizace se provádí automaticky (ve výchozím nastavení), takže HoloLens 2 je vždycky aktuální s nejnovější verzí Windows holografickou a nainstalovanými aplikacemi. Další informace o tom, jak je náš operační systém bezpečně navržený, najdete v následujících tématech:

1. [Oddělení a izolace stavu](/hololens/security-state-separation-isolation)
1. [Správce – less – operační systém](/hololens/security-adminless-os)
1. [Omezení použití hesla](/hololens/security-limiting-password-use)

## <a name="physical-security"></a>Fyzické zabezpečení
HoloLens 2 má flash paměť, která je chráněná [šifrováním pomocí bitlockeru](/hololens/security-encryption-data-protection). Vaše zařízení a jeho místní data může být v režimu offline pomocí [pokročilého Průvodce obnovením](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) nebo vzdáleně smazána přes MDM, pokud byla nasazena jako spravované zařízení.

## <a name="data-protection"></a>Ochrana dat
aktualizace Windows se spouští automaticky (ve výchozím nastavení) a [integrace Azure](/hololens/security-encryption-data-protection#Azure-integration) chrání data na cestách mezi sebou a cloudem.

když nasazujete HoloLens 2 externím klientům, zajistí vám aplikace [Dynamics 365 Remote Assist](/hololens/hololens2-deployment-guide) , aby vaše citlivá firemní data a prostředky byly oddělené a bezpečné.

Sdílení diagnostických dat s Microsoftem může ručně nakonfigurovat MDM nebo uživatel při počátečním spuštění počítače. K dispozici jsou dvě možnosti: volitelná diagnostická data a požadovaná diagnostická data. pokud je pro účely odstraňování potíží potřeba změnit původní nastavení diagnostiky, může ho uživatel změnit v **Nastavení > ochrany osobních údajů – > diagnostika & zpětná vazba** nebo správce it (MDM), pokud se jedná o spravované zařízení. Další informace o [diagnostice, zpětné vazbě a ochraně osobních údajů najdete v tématu Windows 10](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319).

> [!Important]
> Protokoly diagnostiky zařízení obsahují identifikovatelné osobní údaje (PII), například informace o tom, jaké procesy nebo aplikace uživatel spouští během typických operací. pokud se zařízení HoloLens sdílí více uživatelů (například se uživatelé přihlašují ke stejnému zařízení pomocí různých účtů Microsoft Azure Active Directory (Azure AD)), diagnostické protokoly mohou obsahovat informace PII, které platí pro více uživatelů.

pro shromažďování diagnostických dat z HoloLens 2 je k dispozici [několik metod kolekce a zásad uchovávání dat](/hololens/hololens-diagnostic-logs) .  další informace o tom, jak společnost microsoft shromažďuje a používá diagnostická data, naleznete v tématu [prohlášení o zásadách ochrany osobních údajů společnosti microsoft – diagnostika](https://privacy.microsoft.com/privacystatement) -rozbalení **Windows** v levé navigační nabídce a vyberte možnost **diagnostika**. Přejít na část **Diagnostika** .
