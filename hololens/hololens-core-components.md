---
title: plánování nasazení HoloLens 2 v komerčním prostředí
description: přečtěte si o základních potřebách pro nasazení a správu HoloLens v podnikových prostředích, včetně infrastruktury, azure active directory a správy mobilních zařízení.
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
ms.openlocfilehash: 2fb58345f623a0b70c1fda10b9fb550de70f4c6d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635785"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a>plánování nasazení HoloLens 2 v komerčním prostředí

## <a name="overview"></a>Přehled
> [!NOTE]
> tento přehled je určený k tomu, aby odborníci v oblasti IT pochopili důležité informace o nasazení a správě zařízení Microsoft HoloLens 2 v rámci organizace. informace o koncových uživatelích zařízení najdete v článku o tom, jak začít [používat HoloLens 2](hololens2-setup.md) .

HoloLens 2 se spouští na Windows 10 Holographic, která poskytuje organizacím robustní, flexibilní a integrované technologie pro správu mobilních zařízení a aplikací. Windows 10 Holographic podporuje komplexní správu životního cyklu zařízení, aby společnosti poskytovaly kontrolu nad svými zařízeními, daty a aplikacemi. HoloLens 2 je možné snadno začlenit do standardních postupů životního cyklu, od registrace zařízení, konfigurace a správy aplikací až po údržbu a vyřazení z provozu pomocí komplexního řešení pro správu mobilních zařízení.

následující kroky a videa vám pomůžou s postupem HoloLens 2 při přijímání v rámci vaší organizace.

| | |
|--|--|
| ![Krok 1](images/1green.png)| <br/> **[obvyklé scénáře nasazení](hololens-requirements.md)**: pochopení scénářů nasazení a zkoumání základních součástí potřebných k nasazení zařízení HoloLens 2. |
| ![Krok 2](images/2green.png)| <br/> **[příprava](#prepare)**: seznámení se základy infrastruktury potřebnými pro HoloLens 2. |
| ![Krok 3](images/3green.png) | <br/> **[Konfigurace](#configure)**: Naučte se konfigurovat základní komponenty pro cloudové nasazení. |
| ![Krok 4](images/4green.png) | <br/> **[Nasazení](#deploy)**: Zjistěte, jak vaše zařízení nasadit a jak bezpečně a efektivně distribuovat aplikace. |
| ![Krok 5](images/5green.png) | <br/> **[údržba](#maintain)**: zjistěte, co je potřeba pro správné udržování stavu zařízení HoloLens 2 a zajištění souladu s podnikovými zásadami. |

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a>Příprava

seznamte se se základními službami infrastruktury potřebnými k podpoře plné sady možností HoloLens 2. 

| Komponenta | Popis |
|-----------|------------|
| [Azure AD](hololens-identity.md) | poskytuje správu identit a přístupu pro HoloLens 2.  |
| [Správa mobilních zařízení](hololens-mdm-configure.md)| spravuje HoloLens 2 zařízení připojená k vašemu tenantovi.  |
| [Síť Wi-Fi](hololens-commercial-infrastructure.md)| Wi-Fi je k dispozici a zařízení je možné připojit k Internetu  |

## <a name="configure"></a>Konfigurace

používejte intune a autopilot jako řešení s nízkým dotykem pro registraci a konfiguraci HoloLens 2 pro tenanta Azure AD vaší organizace a MDM.

| Komponenta | Popis |
|-----------|------------|
| [Automatický zápis](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | Po počátečním přihlášení se zařízení automaticky registrují ve službě Azure AD a zaregistrují se do MDM.  |
| [Licence k aplikacím](hololens2-cloud-connected-configure.md#application-licenses)| Dá se použít pro uživatele, skupiny uživatelů nebo skupiny zařízení.  |
| [Uživatelé a skupiny Azure](hololens2-cloud-connected-configure.md#azure-users-and-groups) | pomáhá přiřadit konfigurace a licence pro HoloLens 2.  |

## <a name="deploy"></a>Nasadit

distribuujte zařízení HoloLens 2 a ověřte jejich konfiguraci. 

| Komponenta | Popis |
|-----------|------------|
| [Ověřování registrace](hololens2-corp-connected-deploy.md#enrollment-validation) | ověřte, jestli je zařízení připojené k azure AD, Nastavení nebo azure Portal. |
| [Ověření certifikátu](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | Zkontrolujte nastavení a ověřte, zda byly správně distribuovány. |
| [Ověřit instalace aplikace](hololens2-corp-connected-deploy.md#validate-lob-app-install) | potvrďte, že je aplikace přítomná a funguje na vašem HoloLens 2 |

## <a name="maintain"></a>Údržba

použijte web Windows Update pro firmy společně s vaším systémem MDM nebo Microsoft Store, aby se zajistilo, že se vaše flotila HoloLens 2 a aplikace aktualizovala.

| Komponenta | Popis |
|-----------|------------|
| [aktualizace HoloLens 2](hololens-updates.md) | konfigurace aktualizací podle potřeby prostřednictvím Windows aktualizací pro firmy |
| [Aktualizace aplikací](app-deploy-overview.md) | Konfigurace prostřednictvím systému MDM nebo Microsoft Store
