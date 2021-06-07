---
title: Správce certifikátů
description: Naučte se ručně instalovat, spravovat a odebírat certifikáty na zařízeních s hybridní realitou HoloLens 2.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: f9dcf98cbd200ac54cd786648fdfe286bff1aa00
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111377567"
---
# <a name="certificate-manager"></a><span data-ttu-id="3db96-103">Správce certifikátů</span><span class="sxs-lookup"><span data-stu-id="3db96-103">Certificate Manager</span></span>

- <span data-ttu-id="3db96-104">Vylepšené nástroje pro auditování, diagnostiku a ověřování pro zabezpečení a dodržování předpisů zařízení prostřednictvím nového Správce certifikátů</span><span class="sxs-lookup"><span data-stu-id="3db96-104">Improved auditing, diagnosis, and validation tooling for device security and compliance through the new Certificate Manager.</span></span> <span data-ttu-id="3db96-105">Tato funkce vám umožní nasazovat, řešit potíže a ověřovat certifikáty ve velkém měřítku v komerčních prostředích.</span><span class="sxs-lookup"><span data-stu-id="3db96-105">This capability will enable you to deploy, troubleshoot, and validate your certificates at scale in commercial environments.</span></span>

<span data-ttu-id="3db96-106">Ve Windows Holographic verze 20H2 přidáváme Správce certifikátů v aplikaci Nastavení HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="3db96-106">In Windows Holographic, version 20H2, we are adding a Certificate Manager in the HoloLens 2 Settings app.</span></span> <span data-ttu-id="3db96-107">Přejděte na **Nastavení > Update & Security > Certificates**.</span><span class="sxs-lookup"><span data-stu-id="3db96-107">Go to **Settings > Update & Security > Certificates**.</span></span> <span data-ttu-id="3db96-108">Tato funkce poskytuje jednoduchý a uživatelsky přívětivý způsob zobrazení, instalace a odebrání certifikátů v zařízení.</span><span class="sxs-lookup"><span data-stu-id="3db96-108">This feature provides a simple and user-friendly way to view, install and remove certificates on your device.</span></span> <span data-ttu-id="3db96-109">S novým Správcem certifikátů teď správci a uživatelé vylepšili auditování, diagnostiku a ověřování, aby zajistili, že zařízení zůstanou zabezpečená a vyhovující.</span><span class="sxs-lookup"><span data-stu-id="3db96-109">With the new Certificate Manager, admins and users now have improved auditing, diagnosis and validation tooling to ensure that devices remain secure and compliant.</span></span> 

-   <span data-ttu-id="3db96-110">**Auditování:** Možnost ověřit, že je certifikát správně nasazený, nebo ověřit, že byl správně odebrán.</span><span class="sxs-lookup"><span data-stu-id="3db96-110">**Auditing:** Ability to validate that a certificate is deployed correctly or to confirm that it was removed appropriately.</span></span> 
-   <span data-ttu-id="3db96-111">**Diagnostika:** Když dojde k problémům, ověření, že v zařízení existují příslušné certifikáty, šetří čas a pomáhá s řešením potíží.</span><span class="sxs-lookup"><span data-stu-id="3db96-111">**Diagnosis:** When issues arise, validating that the appropriate certificates exist on the device saves time and helps with troubleshooting.</span></span> 
-   <span data-ttu-id="3db96-112">**Ověření:** Ověření, že certifikát slouží zamýšlenému účelu a je funkční, může ušetřit značný čas, zejména v komerčních prostředích před nasazením certifikátů ve větším měřítku.</span><span class="sxs-lookup"><span data-stu-id="3db96-112">**Validation:** Verifying that a certificate serves the intended purpose and is functional, can save significant time, particularly in commercial environments before deploying certificates at larger scale.</span></span>

<span data-ttu-id="3db96-113">Pokud chcete rychle najít konkrétní certifikát v seznamu, existují možnosti řazení podle názvu, úložiště nebo data vypršení platnosti.</span><span class="sxs-lookup"><span data-stu-id="3db96-113">To find a specific certificate in the list quickly, there are options to sort by name, store or expiration date.</span></span> <span data-ttu-id="3db96-114">Uživatelé mohou také přímo vyhledat certifikát.</span><span class="sxs-lookup"><span data-stu-id="3db96-114">Users may also directly search for a certificate.</span></span> <span data-ttu-id="3db96-115">Pokud chcete zobrazit vlastnosti jednotlivých certifikátů, vyberte certifikát a klikněte na **Informace.**</span><span class="sxs-lookup"><span data-stu-id="3db96-115">To view individual certificate properties, select the certificate and click on **Info**.</span></span> 

<span data-ttu-id="3db96-116">Instalace certifikátu aktuálně podporuje soubory .cer a .crt.</span><span class="sxs-lookup"><span data-stu-id="3db96-116">Certificate installation currently supports .cer and .crt files.</span></span> <span data-ttu-id="3db96-117">Vlastníci zařízení mohou instalovat certifikáty v místním počítači a aktuálním uživateli.  Všichni ostatní uživatelé se instaluje jenom do aktuálního uživatele.</span><span class="sxs-lookup"><span data-stu-id="3db96-117">Device Owners can install certificates in Local Machine and Current User;  all other users can only install into Current User.</span></span> <span data-ttu-id="3db96-118">Uživatelé mohou odebrat jenom certifikáty nainstalované přímo z uživatelského rozhraní Nastavení.</span><span class="sxs-lookup"><span data-stu-id="3db96-118">Users can only remove certificates installed directly from the Settings UI.</span></span> <span data-ttu-id="3db96-119">Pokud byl certifikát nainstalován jiným způsobem, musí být také odebrán stejným mechanismem.</span><span class="sxs-lookup"><span data-stu-id="3db96-119">If a certificate has been installed through other means, it must also be removed by the same mechanism.</span></span>

## <a name="to-install-a-certificate"></a><span data-ttu-id="3db96-120">Instalace certifikátu:</span><span class="sxs-lookup"><span data-stu-id="3db96-120">To install a certificate:</span></span> 

1.  <span data-ttu-id="3db96-121">Připojte HoloLens 2 k počítači.</span><span class="sxs-lookup"><span data-stu-id="3db96-121">Connect your HoloLens 2 to a PC.</span></span>
1.  <span data-ttu-id="3db96-122">Umístěte soubor certifikátu, který chcete nainstalovat, do umístění na holoLens 2.</span><span class="sxs-lookup"><span data-stu-id="3db96-122">Place the certificate file you want to install in a location on your HoloLens 2.</span></span>
1.  <span data-ttu-id="3db96-123">Přejděte na **Nastavení App > Update & Security > Certificates** a vyberte Nainstalovat certifikát.</span><span class="sxs-lookup"><span data-stu-id="3db96-123">Navigate to **Settings App > Update & Security > Certificates**, and select Install a certificate.</span></span>
1.  <span data-ttu-id="3db96-124">Klikněte **na Importovat** soubor a přejděte do umístění, do něj které jste certifikát uložili.</span><span class="sxs-lookup"><span data-stu-id="3db96-124">Click **Import File** and navigate to the location you saved the certificate.</span></span>
1.  <span data-ttu-id="3db96-125">Vyberte **Store Location (Umístění obchodu).**</span><span class="sxs-lookup"><span data-stu-id="3db96-125">Select **Store Location**.</span></span>
1.  <span data-ttu-id="3db96-126">Vyberte **Úložiště certifikátů.**</span><span class="sxs-lookup"><span data-stu-id="3db96-126">Select **Certificate Store**.</span></span>
1.  <span data-ttu-id="3db96-127">Klikněte na **Install** (Nainstalovat).</span><span class="sxs-lookup"><span data-stu-id="3db96-127">Click **Install**.</span></span>

<span data-ttu-id="3db96-128">Certifikát by teď měl být nainstalovaný na zařízení.</span><span class="sxs-lookup"><span data-stu-id="3db96-128">The certificate should now be installed on the device.</span></span>

## <a name="to-remove-a-certificate"></a><span data-ttu-id="3db96-129">Odebrání certifikátu:</span><span class="sxs-lookup"><span data-stu-id="3db96-129">To remove a certificate:</span></span> 
>[!WARNING]
> <span data-ttu-id="3db96-130">I když můžete zobrazit certifikáty nasazené v MDM ve Správci certifikátů, nelze je odinstalovat ve Správci certifikátů.</span><span class="sxs-lookup"><span data-stu-id="3db96-130">Although you can view MDM-deployed certificates in Certificate Manager, you cannot uninstall them in Certificate Manager.</span></span> <span data-ttu-id="3db96-131">Musíte je odinstalovat prostřednictvím MDM.</span><span class="sxs-lookup"><span data-stu-id="3db96-131">You must uninstall them through MDM.</span></span>
1. <span data-ttu-id="3db96-132">Přejděte na **Nastavení App > Update and Security > Certificates**.</span><span class="sxs-lookup"><span data-stu-id="3db96-132">Navigate to **Settings App > Update and Security > Certificates**.</span></span>
1. <span data-ttu-id="3db96-133">Ve vyhledávacím poli vyhledejte certifikát podle názvu.</span><span class="sxs-lookup"><span data-stu-id="3db96-133">Search for the certificate by name in the search box.</span></span>
1. <span data-ttu-id="3db96-134">Vyberte certifikát.</span><span class="sxs-lookup"><span data-stu-id="3db96-134">Select the certificate.</span></span>
1. <span data-ttu-id="3db96-135">Klikněte na **Odebrat.**</span><span class="sxs-lookup"><span data-stu-id="3db96-135">Click **Remove**</span></span>
1. <span data-ttu-id="3db96-136">Po **zobrazení** výzvy k potvrzení vyberte Ano.</span><span class="sxs-lookup"><span data-stu-id="3db96-136">Select **Yes** when prompted for confirmation.</span></span>



![Prohlížeč certifikátů v aplikaci Nastavení v části Certifikáty](images/certificate-viewer-device.jpg)

![Obrázek znázorňující, jak pomocí uživatelského rozhraní certifikátu nainstalovat certifikát v Nastavení](images/certificate-device-install.jpg)
