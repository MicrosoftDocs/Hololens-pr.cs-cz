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
# <a name="provisioning-package"></a><span data-ttu-id="92911-104">Zřizovací balíček</span><span class="sxs-lookup"><span data-stu-id="92911-104">Provisioning Package</span></span>

<span data-ttu-id="92911-105">Zřizovací balíčky se dají použít k přípravě a konfiguraci zařízení v prostředí bez přístupu ke správě koncových bodů.</span><span class="sxs-lookup"><span data-stu-id="92911-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="92911-106">Můžou být taky nasazené do zařízení bez ohledu na identitu uživatele, stav registrace, během funkce OOBE (out-of-box) nebo při [použití zřizovacího balíčku během instalace](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span><span class="sxs-lookup"><span data-stu-id="92911-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <a name="provisioning-packages-considerations"></a><span data-ttu-id="92911-107">Požadavky zřizovacích balíčků:</span><span class="sxs-lookup"><span data-stu-id="92911-107">Provisioning Packages considerations:</span></span>

* <span data-ttu-id="92911-108">Neveřejné aplikace</span><span class="sxs-lookup"><span data-stu-id="92911-108">Non-Public apps</span></span>
* <span data-ttu-id="92911-109">Jenom USB – pouze načítání</span><span class="sxs-lookup"><span data-stu-id="92911-109">USB side-load only</span></span>
* <span data-ttu-id="92911-110">Žádná Automatická aktualizace (vyžaduje ruční aktualizace prostřednictvím PPKGs)</span><span class="sxs-lookup"><span data-stu-id="92911-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="92911-111">Aplikace nainstalované prostřednictvím zřizovacího balíčku musí být podepsané certifikátem v úložišti místního počítače.</span><span class="sxs-lookup"><span data-stu-id="92911-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="92911-112">Zřizovací balíčky můžou instalovat jenom certifikáty do úložiště zařízení (v místním počítači), takže aplikace a certifikát se můžou nainstalovat přes stejný zřizovací balíček.</span><span class="sxs-lookup"><span data-stu-id="92911-112">Provisioning packages can only install certificates to the device (local machine) store, therefore an app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="92911-113">Pokud certifikát nasazujete z MDM nebo ho nainstalujete přes [Správce certifikátů](certificate-manager.md), nezapomeňte nasadit certifikát do úložiště místního počítače, abyste mohli podepsat aplikace tímto způsobem.</span><span class="sxs-lookup"><span data-stu-id="92911-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="92911-114">základní informace o vytváření zřizovacího balíčku pro zařízení HoloLens najdete v [HoloLens zřizování](/hololens/hololens-provisioning).</span><span class="sxs-lookup"><span data-stu-id="92911-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](/hololens/hololens-provisioning).</span></span> <span data-ttu-id="92911-115">K nasazení aplikace je nutné začít s pokročilým zřizováním.</span><span class="sxs-lookup"><span data-stu-id="92911-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="92911-116">HoloLens (1. generace) má omezené podpory pro instalaci aplikací (**UniversalAppInstall**) pomocí zřizovacího balíčku.</span><span class="sxs-lookup"><span data-stu-id="92911-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="92911-117">zařízení HoloLens (1. generace) podporují jenom instalaci aplikace přes PPKG jenom během spuštění OOBE a jenom s instalací kontextu uživatele.</span><span class="sxs-lookup"><span data-stu-id="92911-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <a name="setup"></a><span data-ttu-id="92911-118">Nastavení</span><span class="sxs-lookup"><span data-stu-id="92911-118">Setup</span></span>

<span data-ttu-id="92911-119">v [nástroji Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) proveďte následující čtyři kroky.</span><span class="sxs-lookup"><span data-stu-id="92911-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following four steps.</span></span>

1. <span data-ttu-id="92911-120">Nastavte ApplicationManagement/AllowAllTrustedApps na Yes.</span><span class="sxs-lookup"><span data-stu-id="92911-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="92911-121">Viz: [ApplicationManagement/AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span><span class="sxs-lookup"><span data-stu-id="92911-121">See: [ApplicationManagement/AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="92911-122">Přejděte na **UniversalAppInstall**  >  **UserContextAppLicense** a zadejte **PackageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="92911-122">Navigate to **UniversalAppInstall** > **UserContextAppLicense** enter the **PackageFamilyName**.</span></span> <span data-ttu-id="92911-123">Viz [UniversalAppInstall](/windows/configuration/wcd/wcd-universalappinstall).</span><span class="sxs-lookup"><span data-stu-id="92911-123">See [UniversalAppInstall](/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="92911-124">Viz také: [UserContextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span><span class="sxs-lookup"><span data-stu-id="92911-124">See also: [UserContextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="92911-125">Portál zařízení můžete použít na zařízení, do kterého jste už aplikaci nainstalovali.</span><span class="sxs-lookup"><span data-stu-id="92911-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="92911-126">Navštivte stránku aplikace a podívejte se na PackageRelativeID řádek, všechny informace před "!". Je vaše **PackageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="92911-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>

3. <span data-ttu-id="92911-127">Uvidíte, že máte novou část, **ApplicationFile**.</span><span class="sxs-lookup"><span data-stu-id="92911-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="92911-128">Pomocí této oblasti nahrajte sadu appx.</span><span class="sxs-lookup"><span data-stu-id="92911-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="92911-129">V závislosti na tom, jestli jste si zakoupili aplikaci nebo jste vytvořili vlastní obchodní aplikaci, budete muset nahrát soubor s licencí nebo certifikát zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="92911-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="92911-130">Pro soubor s licencí: přejděte na **UniversalAppInstall**  >  **UserContextAppLicence** a vyhledejte umístění vaší licence a nahrajte ho.</span><span class="sxs-lookup"><span data-stu-id="92911-130">For license file: navigate to **UniversalAppInstall** > **UserContextAppLicence** and browse to the location of your license and upload it.</span></span>
    - <span data-ttu-id="92911-131">Pro soubor zabezpečení přejděte na **certifikáty** a vyberte certifikát, který chcete nainstalovat společně se sadou. appx.</span><span class="sxs-lookup"><span data-stu-id="92911-131">For the security file, navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="92911-132">Ujistěte se, že jste projekt uložili do zabezpečeného umístění.</span><span class="sxs-lookup"><span data-stu-id="92911-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="92911-133">Pak ho **exportujte** jako **zřizovací balíček**.</span><span class="sxs-lookup"><span data-stu-id="92911-133">Then **Export** it as a **Provisioning Package**.</span></span>  

<span data-ttu-id="92911-134">Viz také: [použití balíčku zřizování na HoloLens](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span><span class="sxs-lookup"><span data-stu-id="92911-134">See also: [Apply your provisioning package to HoloLens](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
