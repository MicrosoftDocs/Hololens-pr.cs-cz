---
title: Plánování HoloLens 2 v komerčním prostředí
description: Seznamte se se základními potřebami pro nasazení a správu HoloLens podnikových prostředích, včetně infrastruktury, Azure Active Directory a správy mobilních zařízení.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: joyjaz
ms.author: v-jjaswinski
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/21/2021
appliesto:
- HoloLens 2
ms.openlocfilehash: 8605d1a889fb9facdab0e9585a43a61880155952
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/30/2021
ms.locfileid: "123188895"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a>Plánování HoloLens 2 v komerčním prostředí

## <a name="overview"></a>Přehled

> [!NOTE]
> Tento přehled pomáhá IT specialistům pochopit aspekty nasazení a správy Microsoft HoloLens 2 v rámci organizace. Informace o koncových uživatelích [zařízení najdete v tématu HoloLens 2 začít](hololens2-setup.md) používat.

HoloLens 2 běží na Windows 10 Holographic, který organizacím poskytuje robustní, flexibilní integrované technologie správy mobilních zařízení a aplikací. Windows 10 Holographic podporuje koncovou správu životního cyklu zařízení, aby společnosti nad svými zařízeními, daty a aplikacemi kontrolul. Řešení HoloLens 2 je možné snadno začlenit do standardních postupů životního cyklu, od registrace zařízení, konfigurace a správy aplikací až po údržbu a vyřazení pomocí komplexního řešení pro správu mobilních zařízení.

Následující kroky a video vás pomůžou provést procesem přechodu na HoloLens 2 v rámci vaší organizace.

| &nbsp; | &nbsp; |
|--|--|
| ![Krok 1.](images/1green.png)| <br/> **[Běžné scénáře nasazení:](hololens-requirements.md)** Seznamte se se scénáři nasazení a prozkoumejte základní komponenty potřebné k HoloLens 2 zařízení. |
| ![Krok 2.](images/2green.png)| <br/> **[Příprava:](#prepare)** Seznamte se se základními prvky infrastruktury potřebnými pro HoloLens 2. |
| ![Krok 3.](images/3green.png) | <br/> **[Konfigurace:](#configure)** Zjistěte, jak nakonfigurovat základní komponenty pro cloudové nasazení. |
| ![Krok 4:](images/4green.png) | <br/> **[Nasazení:](#deploy)** Zjistěte, jak bezpečně a efektivně nasadit zařízení a distribuovat aplikace. |
| ![Krok 5.](images/5green.png) | <br/> **[Údržba:](#maintain)** Zjistěte, co je potřeba ke správné údržbě stavu vašich zařízení HoloLens 2 a zajištění dodržování firemních zásad. |

<br/>

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a>Příprava

Seznamte se se základními službami infrastruktury potřebnými k podpoře úplné sady HoloLens 2.

| Komponenta | Popis |
|-----------|------------|
| [Azure AD](hololens-identity.md) | Poskytuje správu identit a přístupu pro HoloLens 2.  |
| [Správa mobilních zařízení](hololens-mdm-configure.md)| Spravuje HoloLens 2 zařízení připojená k vašemu tenantovi.  |
| [Síť Wi-Fi](hololens-commercial-infrastructure.md)| Wi-Fi je k dispozici a zařízení je možné připojit k internetu.  |

## <a name="configure"></a>Konfigurace

Intune a Autopilot můžete použít jako nízko touch řešení pro registraci a konfiguraci HoloLens 2 do tenanta Azure AD a MDM vaší organizace.

| Komponenta | Popis |
|-----------|------------|
| [Automatická registrace](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | Po počátečním přihlášení se zařízení automaticky zaregistrují v Azure AD a zaregistrují se do MDM.  |
| [Licence aplikací](hololens2-cloud-connected-configure.md#application-licenses)| Lze použít pro uživatele, skupiny uživatelů nebo skupiny zařízení.  |
| [Uživatelé a skupiny Azure](hololens2-cloud-connected-configure.md#azure-users-and-groups) | Pomáhá přiřazovat konfigurace a licence pro HoloLens 2.  |

## <a name="deploy"></a>Nasadit

Distribuujte zařízení HoloLens 2 a ověřte jejich konfiguraci. 

| Komponenta | Popis |
|-----------|------------|
| [Ověření registrace](hololens2-corp-connected-deploy.md#enrollment-validation) | Ověření připojení zařízení k Azure AD z Nastavení nebo webu Azure Portal |
| [Ověření certifikátu](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | Zkontrolujte nastavení a ověřte, že se správně distribuují. |
| [Ověření instalací aplikace](hololens2-corp-connected-deploy.md#validate-lob-app-install) | Ověřte, že aplikace existuje a pracuje na vaší aplikaci HoloLens 2. |

## <a name="maintain"></a>Údržba

Pomocí Windows Update for Business spolu se systémem MDM nebo Microsoft Store udržujte vozový park aplikací HoloLens 2 a aplikací aktualizovaných.

| Komponenta | Popis |
|-----------|------------|
| [Aktualizace HoloLens 2](hololens-updates.md) | Podle potřeby nakonfigurujte aktualizace prostřednictvím Windows Updates for Business. |
| [Aktualizace aplikací](app-deploy-overview.md) | Konfigurace prostřednictvím systému MDM nebo Microsoft Store
