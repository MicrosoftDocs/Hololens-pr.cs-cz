---
title: Zřizovací balíček
description: Seznamte se s balením aplikací, zřizováním, nasazením a nasazením podnikových aplikací pro zařízení HoloLens.
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
ms.openlocfilehash: 9c73b03e6a8dca6baf6c58fed091df96994c3780
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377612"
---
# <a name="provisioning-package"></a><span data-ttu-id="b1b3f-104">Zřizovací balíček</span><span class="sxs-lookup"><span data-stu-id="b1b3f-104">Provisioning Package</span></span>

<span data-ttu-id="b1b3f-105">Zřizovací balíčky je možné použít k přípravě a konfiguraci zařízení v prostředí bez přístupu ke správě koncových bodů.</span><span class="sxs-lookup"><span data-stu-id="b1b3f-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="b1b3f-106">Můžete je také nasadit do zařízení bez ohledu na identitu uživatele, stav registrace, prostředí při spuštění počítače nebo instalaci zřizovacího balíčku během [instalace](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span><span class="sxs-lookup"><span data-stu-id="b1b3f-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <a name="provisioning-packages-considerations"></a><span data-ttu-id="b1b3f-107">Důležité informace o zřizovacích balíčcích:</span><span class="sxs-lookup"><span data-stu-id="b1b3f-107">Provisioning Packages considerations:</span></span>

* <span data-ttu-id="b1b3f-108">Ne veřejné aplikace</span><span class="sxs-lookup"><span data-stu-id="b1b3f-108">Non-Public apps</span></span>
* <span data-ttu-id="b1b3f-109">Jenom zkušební načtení USB</span><span class="sxs-lookup"><span data-stu-id="b1b3f-109">USB side-load only</span></span>
* <span data-ttu-id="b1b3f-110">Žádná automatická aktualizace (vyžaduje ruční aktualizace prostřednictvím PPKG)</span><span class="sxs-lookup"><span data-stu-id="b1b3f-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="b1b3f-111">Aplikace nainstalované prostřednictvím zřizovacího balíčku musí být podepsané certifikátem v místním počítači.</span><span class="sxs-lookup"><span data-stu-id="b1b3f-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="b1b3f-112">Zřizovací balíčky instaluje certifikáty jenom do úložiště zařízení (místního počítače), proto je možné nainstalovat aplikaci a certifikát prostřednictvím stejného zřizovacího balíčku.</span><span class="sxs-lookup"><span data-stu-id="b1b3f-112">Provisioning packages can only install certificates to the device (local machine) store, therefore an app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="b1b3f-113">Pokud nasazujete certifikát z MDM nebo instalujete přes [Správce](certificate-manager.md)certifikátů , nezapomeňte certifikát nasadit do úložiště místního počítače, abyste aplikace nainstalovali tímto způsobem.</span><span class="sxs-lookup"><span data-stu-id="b1b3f-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="b1b3f-114">Základní informace o vytvoření zřizovacího balíčku pro zařízení HoloLens najdete v tématu [Zřizování HoloLens.](https://docs.microsoft.com/hololens/hololens-provisioning)</span><span class="sxs-lookup"><span data-stu-id="b1b3f-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="b1b3f-115">Pokud chcete nasadit aplikaci, musíte začít s pokročilým zřizováním.</span><span class="sxs-lookup"><span data-stu-id="b1b3f-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="b1b3f-116">HoloLens (1. generace) má omezenou podporu instalace aplikací (**UniversalAppInstall**) pomocí zřizovacího balíčku.</span><span class="sxs-lookup"><span data-stu-id="b1b3f-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="b1b3f-117">Zařízení HoloLens (1. generace) podporují instalaci aplikace přes PPKG jenom během OOBE a jenom při instalaci kontextu uživatele.</span><span class="sxs-lookup"><span data-stu-id="b1b3f-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <a name="setup"></a><span data-ttu-id="b1b3f-118">Nastavení</span><span class="sxs-lookup"><span data-stu-id="b1b3f-118">Setup</span></span>

<span data-ttu-id="b1b3f-119">V [nástroji Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) postupujte podle čtyř kroků.</span><span class="sxs-lookup"><span data-stu-id="b1b3f-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following four steps.</span></span>

1. <span data-ttu-id="b1b3f-120">Nastavte ApplicationManagement/AllowAllTrustedApps na Ano.</span><span class="sxs-lookup"><span data-stu-id="b1b3f-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="b1b3f-121">Viz: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span><span class="sxs-lookup"><span data-stu-id="b1b3f-121">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="b1b3f-122">Přejděte na **UniversalAppInstall**  >  **UserContextAppLicense** a zadejte **PackageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="b1b3f-122">Navigate to **UniversalAppInstall** > **UserContextAppLicense** enter the **PackageFamilyName**.</span></span> <span data-ttu-id="b1b3f-123">Viz [UniversalAppInstall.](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall)</span><span class="sxs-lookup"><span data-stu-id="b1b3f-123">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="b1b3f-124">Viz také: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span><span class="sxs-lookup"><span data-stu-id="b1b3f-124">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="b1b3f-125">Můžete použít Portál zařízení zařízení, na které jste už aplikaci nainstalovali.</span><span class="sxs-lookup"><span data-stu-id="b1b3f-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="b1b3f-126">Přejděte na stránku Aplikace a podívejte se na řádek PackageRelativeID se všemi informacemi před "!" Je váš **packageFamilyName**.</span><span class="sxs-lookup"><span data-stu-id="b1b3f-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>

3. <span data-ttu-id="b1b3f-127">Pak uvidíte, že máte novou část **ApplicationFile**.</span><span class="sxs-lookup"><span data-stu-id="b1b3f-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="b1b3f-128">Tuto oblast použijte k nahrání sady appx.</span><span class="sxs-lookup"><span data-stu-id="b1b3f-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="b1b3f-129">V závislosti na tom, jestli jste si zakoupili aplikaci nebo jste si vlastní obchodní aplikaci koupili, budete muset nahrát licenční soubor nebo certifikát zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="b1b3f-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="b1b3f-130">Soubor s licencí: Přejděte na **UniversalAppInstall**  >  **UserContextAppLicence** a přejděte do umístění vaší licence a nahrajte ji.</span><span class="sxs-lookup"><span data-stu-id="b1b3f-130">For license file: navigate to **UniversalAppInstall** > **UserContextAppLicence** and browse to the location of your license and upload it.</span></span>
    - <span data-ttu-id="b1b3f-131">V případě souboru zabezpečení přejděte na **Certifikáty** a vyberte certifikát, který chcete nainstalovat společně se sadou .appx.</span><span class="sxs-lookup"><span data-stu-id="b1b3f-131">For the security file, navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="b1b3f-132">Nezapomeňte projekt uložit do zabezpečeného umístění.</span><span class="sxs-lookup"><span data-stu-id="b1b3f-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="b1b3f-133">Pak **ho exportujte** jako **zřizovací balíček**.</span><span class="sxs-lookup"><span data-stu-id="b1b3f-133">Then **Export** it as a **Provisioning Package**.</span></span>  

<span data-ttu-id="b1b3f-134">Viz také: [Použití zřizovacího balíčku pro HoloLens.](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)</span><span class="sxs-lookup"><span data-stu-id="b1b3f-134">See also: [Apply your provisioning package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
