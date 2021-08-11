---
title: Průvodce nasazením – nasazení HoloLens 2 ve velkém měřítku pomocí nástroje Remote Assist – údržba
description: Získejte aktuální informace o našich tipech pro údržbu a podporu HoloLens přes síť připojenou ke cloudu.
keywords: HoloLens, správa, připojení ke cloudu, Remote Assist, AAD, Azure AD, MDM, Mobile Správa zařízení
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
ms.openlocfilehash: 879f89d84bbae5b4cc187bc8b1fca627036269145b1c2dd82787e3789fef259d
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660374"
---
# <a name="maintain---cloud-connected-guide"></a>Údržba – Průvodce připojeným ke cloudu

## <a name="updates"></a>Aktualizace

Společnost Microsoft navrhla službu Windows Update pro firmy, aby správcům IT poskytovala další funkce správy zaměřené na aktualizaci Windows, jako je například možnost nasazovat aktualizace do skupin zařízení a definovat intervaly pro správu a údržbu pro instalaci aktualizací.

Zjistěte, [jak spravovat HoloLens,](/hololens/hololens-updates) včetně plánovaných dnů, naplánovaného času a nastavení aktivních hodin v zařízení, aby se aktualizace šoustavy mimo pracovní dobu.

Remote Assist je In-Box aplikace a je možné ji aktualizovat prostřednictvím Microsoft Store aplikace. Pro všechny aplikace, které jsou staženy prostřednictvím Microsoft Store, je možné je [aktualizovat prostřednictvím Microsoft Store](/hololens/holographic-store-apps#update-apps) aplikace ručně.

## <a name="support-plan"></a>Plán podpory

Plán podpory je skvělá věc, kterou je třeba mít. Je užitečné mít někoho nebo skupinu natrénované na řešení potíží s procesem registrace na HoloLens zařízeních a také obecné použití HoloLens zařízení ve vaší organizaci. Pokud chcete uživatelům umožnit rychlejší řešení problémů, doporučujeme, aby se proces eskalace zpracovával podobným způsobem jako v tomto pořadí:

1. Váš tým podpory.
2. Váš tým HoloLens Expert
3. [HoloLens Docs](/hololens/)  /  [HoloLens dokumentace k řešení potíží](/hololens/hololens-troubleshooting)
4. [Kontaktovat podporu](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a>Plán vývoje

Když je zařízení úspěšně zaregistrované, jste připraveni na zařízení nasadit obchodní aplikace (obchodní aplikace). Jedná se o vlastní aplikace vytvořené pro vaši organizaci&#39;potřebám.

Pokud už máte obchodní aplikaci, můžete&#39;k nasazení aplikace [prostřednictvím MDM.](/hololens/app-deploy-intune) Pokud chcete&#39;jinou metodu, přečtěte si přehled nasazení aplikace pro [HoloLens 2,](/hololens/app-deploy-overview) abyste se dozvěděli další metody nasazení obchodní aplikace do zařízení.

Pokud jste&#39;vytvořili vlastní obchodní aplikaci nebo jste stále v procesu vytváření, přečtěte si naše dokumenty k vývoji pro hybridní realitu, kde můžete začít s návrhem a [vytvářením prototypů](/windows/mixed-reality/design/design) nebo se se seznamovat se základními koncepty, abyste se s vývojem hybridní reality [začali.](/windows/mixed-reality/discover/get-started-with-mr)

## <a name="device-management"></a>Správa zařízení 

I když tento průvodce mluvil o nastavení Mobile Správa zařízení (MDM), nebyl použit k použití omezení zařízení nebo zásad, které se použily na zařízení. Správu zařízení je možné použít k povolení přístupu prostřednictvím zápisu certifikátů nebo k omezení přístupu s různými omezeními zařízení. 

V mnoha případech mohou mít zařízení omezení připojení, jako Bluetooth, VPN nebo USB, nebo dokonce vypnout přístup k fotoaparátu nebo mikrofonu. Pokud vás některý z těchto zájmů zajímá, doporučujeme, abyste si přečetli naši běžnou [stránku omezení zařízení.](hololens-common-device-restrictions.md)

Existují i další složitější omezení zařízení, která můžete použít. Například:

- Omezení stránek, které lze zobrazit v aplikaci Nastavení, pomocí [NastaveníStránkaVisibility,](settings-uri-list.md)což uživatelům umožňuje přístup jenom k nastavením, která potřebují upravit, například ke změně Wi-Fi připojení.
- Pomocí [bezobrazovkového režimu](hololens-kiosk.md) omezte uživatelské rozhraní, které se zobrazí uživatelům na zařízení. Bezobrazovkové terminály můžete nastavit tak, aby se jedna aplikace nebo několik aplikací s vlastní úvodní stránkou zobrazují. Kiosky mohou také různým uživatelům prezentovat různá prostředí.  
- [Windows řízení aplikací (WDAC), aby](windows-defender-application-control-wdac.md) se určité aplikace nebo procesy úplně nespouštěl.

Pokud se chcete dozvědět více o různých metodách správy zařízení nebo omezeních zařízení, udělejte další krok a přečtěte si naše Správa zařízení zařízení.

## <a name="next-step"></a>Další krok

> [!div class="nextstepaction"]
> [Přečtěte si informace o zprostředkovateli csP a Správa zařízení o funkcích.](hololens-csp-policy-overview.md)