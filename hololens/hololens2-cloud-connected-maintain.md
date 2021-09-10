---
title: průvodce nasazením – Cloud připojený HoloLens 2 ve velkém měřítku s využitím funkce Remote Assist – údržba
description: díky našim tipům pro údržbu a podporu HoloLensch zařízení přes síť propojenou s cloudem můžete zůstat v aktuálním stavu.
keywords: HoloLens, správa, připojení k cloudu, vzdálená pomoc, AAD, Azure AD, MDM, správa mobilních zařízení
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 941de296d59713c098718b16431fa793bd1b60e6
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428734"
---
# <a name="maintain---cloud-connected-guide"></a>Údržba – Průvodce připojením k cloudu

## <a name="updates"></a>Aktualizace

společnost Microsoft navrhla web Windows Update pro firmy, aby správcům IT poskytovala další možnosti správy zaměřené na web Windows Update, jako je například možnost nasazení aktualizací do skupin zařízení a definování oken údržby pro instalaci aktualizací.

naučte se [spravovat HoloLens aktualizace](/hololens/hololens-updates) , včetně plánovaných dnů, naplánovaných časů a nastavení aktivních hodin v zařízení, aby se aktualizovala mimo pracovní dobu.

Remote Assist je In-Box aplikace a dá se aktualizovat prostřednictvím Microsoft Store aplikace. u všech aplikací, které jsou stažené prostřednictvím Microsoft Store, je můžete ručně [aktualizovat přímo pomocí aplikace Microsoft Store](/hololens/holographic-store-apps#update-apps) .

## <a name="support-plan"></a>Plán podpory

Plán podpory je vynikajícím krokem. uživatel nebo skupina, která je vyškolená při řešení potíží s procesem registrace na zařízeních HoloLens a také obecné použití HoloLensho zařízení v rámci vaší organizace, je užitečné. Abychom uživatelům umožnili rychlejší řešení jejich problémů, doporučujeme, aby proces eskalace byl zpracován podobným způsobem jako v tomto pořadí:

1. Vaše oddělení podpory.
2. váš tým odborníka na HoloLens
3. [HoloLens Docs](/hololens/)  /  [HoloLens řešení potíží s dokumenty](/hololens/hololens-troubleshooting)
4. [Kontaktujte podporu](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a>Plán vývoje

Po úspěšném zaregistrování zařízení teď budete připraveni k nasazení obchodních aplikací (LOB) na vaše zařízení. Jedná se o vlastní aplikace sestavené pro potřeby vaší organizace&#39;s.

Pokud už máte podnikovou aplikaci,&#39;znovu připravená k [nasazení vaší aplikace přes MDM](/hololens/app-deploy-intune). pokud&#39;d preferovat jinou metodu, přečtěte si téma [přehled nasazení aplikace HoloLens 2](/hololens/app-deploy-overview) , kde najdete další informace o nasazení obchodní aplikace do zařízení.

Pokud jste ještě&#39;, abyste si vytvořili vlastní obchodní aplikaci nebo jste stále v procesu vytváření, Projděte si naše dokumenty pro vývoj hybridních realit a [začněte navrhovat návrh a vytváření prototypů](/windows/mixed-reality/design/design) nebo Naučte se základními koncepty, které [vám pomůžou začít se smíšeným vývojem realit.](/windows/mixed-reality/discover/get-started-with-mr)

## <a name="device-management"></a>Správa zařízení 

I když se tato příručka mluvili o nastavení správy mobilních zařízení (MDM), která se nepoužívala při použití omezení zařízení nebo zásad, které byly použity na zařízeních. Správa zařízení se dá použít k umožnění přístupu prostřednictvím vložení certifikátů nebo omezení přístupu k různým omezením zařízení. 

v mnoha případech můžou mít zařízení omezení připojení, jako Bluetooth, VPN, USB, nebo dokonce vypnutí přístupu ke kameře nebo mikrofonu. Pokud některý z těchto zájmů potom pomůžete, doporučujeme, abyste si přečetli [Nejčastější stránku omezení pro zařízení](hololens-common-device-restrictions.md).

Existují další složitější omezení zařízení, která můžete použít. Například:

- omezení stránek, které se dají zobrazit v aplikaci Nastavení, pomocí [SettingsPageVisibility](settings-uri-list.md), takže uživatelé budou mít přístup jenom k nastavením, jako je třeba změna připojení Wi-Fi.
- Používejte [celoobrazovkový režim](hololens-kiosk.md) k omezení uživatelského rozhraní prezentovaného uživatelům na zařízení. Veřejné terminály můžete nastavit tak, aby zobrazovaly jednu aplikaci nebo více aplikací s vlastní úvodní stránkou. Veřejné terminály můžou také prezentovat různá prostředí různým uživatelům.  
- [Windows řízení aplikací (WDAC)](windows-defender-application-control-wdac.md) , aby se zajistilo, že konkrétní aplikace nebo procesy budou zcela spouštěny.

Pokud se chcete dozvědět víc o různých metodách správy zařízení nebo omezení zařízení, proveďte další krok a přečtěte si přehled správy zařízení.

## <a name="next-step"></a>Další krok

> [!div class="nextstepaction"]
> [Přečtěte si téma Přehled CSP a Správa zařízení.](hololens-csp-policy-overview.md)