---
title: Zřizovací balíček
description: přečtěte si o nasazení aplikací, zřizování, nasazení a nasazení podnikových aplikací pro zařízení HoloLens.
keywords: aplikace, nasazení aplikace, nasazení podnikových aplikací, zřizování
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
ms.openlocfilehash: 5aa554f9e7fdc09c3112b628e0978ac3332bc57d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635513"
---
# <a name="provisioning-package"></a>Zřizovací balíček

Zřizovací balíčky se dají použít k přípravě a konfiguraci zařízení v prostředí bez přístupu ke správě koncových bodů. Můžou být taky nasazené do zařízení bez ohledu na identitu uživatele, stav registrace, během funkce OOBE (out-of-box) nebo při [použití zřizovacího balíčku během instalace](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).

## <a name="provisioning-packages-considerations"></a>Požadavky zřizovacích balíčků:

* Neveřejné aplikace
* Jenom USB – pouze načítání
* Žádná Automatická aktualizace (vyžaduje ruční aktualizace prostřednictvím PPKGs)

Aplikace nainstalované prostřednictvím zřizovacího balíčku musí být podepsané certifikátem v úložišti místního počítače. Zřizovací balíčky můžou instalovat jenom certifikáty do úložiště zařízení (v místním počítači), takže aplikace a certifikát se můžou nainstalovat přes stejný zřizovací balíček. Pokud certifikát nasazujete z MDM nebo ho nainstalujete přes [Správce certifikátů](certificate-manager.md), nezapomeňte nasadit certifikát do úložiště místního počítače, abyste mohli podepsat aplikace tímto způsobem.

základní informace o vytváření zřizovacího balíčku pro zařízení HoloLens najdete v [HoloLens zřizování](/hololens/hololens-provisioning). K nasazení aplikace je nutné začít s pokročilým zřizováním.

> [!NOTE]
> HoloLens (1. generace) má omezené podpory pro instalaci aplikací (**UniversalAppInstall**) pomocí zřizovacího balíčku. zařízení HoloLens (1. generace) podporují jenom instalaci aplikace přes PPKG jenom během spuštění OOBE a jenom s instalací kontextu uživatele.

## <a name="setup"></a>Nastavení

v [nástroji Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) proveďte následující čtyři kroky.

1. Nastavte ApplicationManagement/AllowAllTrustedApps na Yes. Viz: [ApplicationManagement/AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).

2. Přejděte na **UniversalAppInstall**  >  **UserContextAppLicense** a zadejte **PackageFamilyName**. Viz [UniversalAppInstall](/windows/configuration/wcd/wcd-universalappinstall). Viz také: [UserContextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).

   Portál zařízení můžete použít na zařízení, do kterého jste už aplikaci nainstalovali. Navštivte stránku aplikace a podívejte se na PackageRelativeID řádek, všechny informace před "!". Je vaše **PackageFamilyName**.

3. Uvidíte, že máte novou část, **ApplicationFile**. Pomocí této oblasti nahrajte sadu appx.

4. V závislosti na tom, jestli jste si zakoupili aplikaci nebo jste vytvořili vlastní obchodní aplikaci, budete muset nahrát soubor s licencí nebo certifikát zabezpečení.

    - Pro soubor s licencí: přejděte na **UniversalAppInstall**  >  **UserContextAppLicence** a vyhledejte umístění vaší licence a nahrajte ho.
    - Pro soubor zabezpečení přejděte na **certifikáty** a vyberte certifikát, který chcete nainstalovat společně se sadou. appx.

Ujistěte se, že jste projekt uložili do zabezpečeného umístění. Pak ho **exportujte** jako **zřizovací balíček**.  

Viz také: [použití balíčku zřizování na HoloLens](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).
