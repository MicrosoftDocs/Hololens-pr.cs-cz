---
title: Zřizovací balíček
description: Seznamte se s balením, zřizováním, nasazením a nasazením podnikových aplikací pro HoloLens zařízení.
keywords: aplikace, nasazení aplikace, nasazení podnikové aplikace, zřizování
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: d071f4326a35a9ea61e2069618da7107bb808f04
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032204"
---
# <a name="provisioning-package"></a>Zřizovací balíček

Zřizovací balíčky je možné použít k přípravě a konfiguraci zařízení v prostředí bez přístupu ke správě koncových bodů. Můžete je také nasadit do zařízení bez ohledu na identitu uživatele, stav registrace, prostředí při spuštění počítače nebo použití zřizovacího balíčku během [instalace](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).

## <a name="provisioning-packages-considerations"></a>Důležité informace o zřizovacích balíčcích

* Ne veřejné aplikace
* Jenom zkušební načtení USB
* Žádná automatická aktualizace (vyžaduje ruční aktualizace prostřednictvím PPKG)

Aplikace nainstalované prostřednictvím zřizovacího balíčku musí být podepsané certifikátem v místním počítači. Zřizovací balíčky instaluje certifikáty jenom do úložiště zařízení (místního počítače). Aplikace a certifikát je proto možné nainstalovat prostřednictvím stejného zřizovacího balíčku. Pokud nasazujete certifikát z MDM nebo instalujete přes [Správce](certificate-manager.md)certifikátů , nezapomeňte certifikát nasadit do úložiště místního počítače, abyste aplikace nainstalovali tímto způsobem.

Základní informace o vytvoření zřizovacího balíčku pro HoloLens zařízení najdete v [HoloLens zřizování.](/hololens/hololens-provisioning) Pokud chcete nasadit aplikaci, musíte začít s pokročilým zřizováním.

> [!NOTE]
> HoloLens (1. generace) má omezenou podporu instalace aplikací (**UniversalAppInstall**) pomocí zřizovacího balíčku. HoloLens (1. generace) podporují instalaci aplikace přes PPKG jenom během OOBE a jenom při instalaci kontextu uživatele.

## <a name="setup"></a>Nastavení

V [Windows Configuration Designeru postupujte](https://www.microsoft.com/store/productId/9NBLGGH4TX22) podle následujících čtyř kroků.

1. Nastavte ApplicationManagement/AllowAllTrustedApps na Ano. Viz: [ApplicationManagement/AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).

2. Přejděte na **UniversalAppInstall**  >  **UserContextApp** a zadejte **PackageFamilyName**. Viz [UniversalAppInstall.](/windows/configuration/wcd/wcd-universalappinstall)

   Můžete použít Portál zařízení zařízení, na které jste už aplikaci nainstalovali. Přejděte na stránku Aplikace a podívejte se na řádek PackageRelativeID, všechny informace před "!" Je váš **packageFamilyName**.

3. Pak uvidíte, že máte novou část **ApplicationFile**. Tuto oblast použijte k nahrání sady appx.

4. V závislosti na tom, jestli jste si zakoupili aplikaci nebo jste si vlastní obchodní aplikaci koupili, budete muset nahrát licenční soubor nebo certifikát zabezpečení.

    - Soubor s licencí: Přejděte na **UniversalAppInstall**  >  **UserContextAppLicence** a zadejte ID produktu licence. Vytvoří se nová část <b>LicenseProductID:</b><i>vaše ID</i> produktu licence, vyberte tuto novou část, přejděte do umístění vaší licence a nahrajte ji.
        - Viz [UserContextAppLicense.](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense)
    - V případě souboru zabezpečení přejděte na **Certifikáty** a vyberte certifikát, který chcete nainstalovat společně se sadou .appx.

Nezapomeňte projekt uložit do zabezpečeného umístění. Pak **ho exportujte** jako **zřizovací balíček**.  

Viz také: [Použití zřizovacího balíčku pro HoloLens](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).
