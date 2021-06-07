---
title: Podnikový zápis zařízení HoloLens na adrese MAC s omezeným Wi-Fi prostředím
description: Postup adresy MAC pro síť na zařízeních s HoloLens 2
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: mata
ms.topic: article
ms.localizationpriority: high
ms.date: 10/01/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: a577eace62040e2d48de5d3e4cc99ef108bd006c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379227"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a><span data-ttu-id="93f55-103">Podnikový zápis zařízení HoloLens na adrese MAC s omezeným Wi-Fi prostředím</span><span class="sxs-lookup"><span data-stu-id="93f55-103">Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment</span></span>

<span data-ttu-id="93f55-104">Tento dokument popisuje běžný scénář, který jsme identifikovali v rámci zákaznických prostředí, kde je Wi-Fi omezen adresami MAC, nebo jsou pro připojení k bezdrátovým sítím vyžadovány certifikáty.</span><span class="sxs-lookup"><span data-stu-id="93f55-104">This document will describe a common scenario we have identified within customer environments where the Wi-Fi is restricted by MAC addresses, or certificates are required to join Wireless networks.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="93f55-105">Ukázkový scénář</span><span class="sxs-lookup"><span data-stu-id="93f55-105">Example Scenario</span></span>

<span data-ttu-id="93f55-106">Mnoho zákazníků v zabezpečených prostředích má omezení pro bezdrátové nebo kabelové sítě, které umožní úspěšně připojit schválená zařízení (na základě adres MAC).</span><span class="sxs-lookup"><span data-stu-id="93f55-106">Many customers in secure environments have restrictions on their Wireless or wired networks that will only allow approved devices (based on MAC Addresses) to connect successfully.</span></span> <span data-ttu-id="93f55-107">To může být vynutilo filtrování adres MAC v bezdrátovém přístupovém bodě nebo prostřednictvím serveru DHCP.</span><span class="sxs-lookup"><span data-stu-id="93f55-107">This may be enforced through MAC Address filtering on a Wireless Access Point or through a DHCP server.</span></span> <span data-ttu-id="93f55-108">Kromě toho je možné některé bezdrátové sítě chránit pomocí protokolu PEAP, což vyžaduje, aby se pro zařízení před ověřením v bezdrátové síti používal certifikát.</span><span class="sxs-lookup"><span data-stu-id="93f55-108">Additionally, some Wireless networks can be protected with PEAP, which requires that a certificate be applied to the device prior to authenticating on the Wireless network.</span></span>

<span data-ttu-id="93f55-109">V tomto scénáři můžou dva klíčové požadavky způsobit zpoždění nebo vyžadovat ruční zásah při připojování zařízení s HoloLens k síti:</span><span class="sxs-lookup"><span data-stu-id="93f55-109">In this scenario, two key requirements may introduce delays or require manual intervention when joining HoloLens devices to the network:</span></span>

- <span data-ttu-id="93f55-110">Aby se zařízení úspěšně připojilo k bezdrátové síti, musí se k němu použít bezdrátový certifikát protokolu PEAP.</span><span class="sxs-lookup"><span data-stu-id="93f55-110">The Wireless PEAP certificate must be applied to the device prior to the device successfully joining the wireless network.</span></span>
- <span data-ttu-id="93f55-111">Adresa MAC Wi-Fi adaptéru HoloLens musí být zaregistrovaná.</span><span class="sxs-lookup"><span data-stu-id="93f55-111">The MAC Address of the HoloLens Wi-Fi adaptor must be registered.</span></span>

<span data-ttu-id="93f55-112">Základní problémy s výše uvedenými požadavky:</span><span class="sxs-lookup"><span data-stu-id="93f55-112">The core challenges with the requirements above are:</span></span>

1. <span data-ttu-id="93f55-113">Adresa MAC se v současnosti dá identifikovat jenom z aplikace nastavení v zařízení nebo z Intune po úspěšné registraci.</span><span class="sxs-lookup"><span data-stu-id="93f55-113">The MAC Address can currently only be identified from the Settings app on the device, or from Intune after a successful enrollment.</span></span>

2. <span data-ttu-id="93f55-114">Bez adresy MAC se nemůže zařízení připojit k síti Wi-Fi, aby bylo možné zahájit registraci.</span><span class="sxs-lookup"><span data-stu-id="93f55-114">Without the MAC address, the device cannot join the Wi-Fi Network to begin enrollment.</span></span>

3. <span data-ttu-id="93f55-115">Ruční alternativní řešení těchto problémů vyžadují, aby určitý pracovník komunikoval se zařízením.</span><span class="sxs-lookup"><span data-stu-id="93f55-115">Manual workarounds to these challenges require a technician to interact with the device.</span></span>

## <a name="solutions"></a><span data-ttu-id="93f55-116">Řešení</span><span class="sxs-lookup"><span data-stu-id="93f55-116">Solutions</span></span>

<span data-ttu-id="93f55-117">Existuje mnoho způsobů, jak tuto situaci zlepšit, v závislosti na infrastruktuře dostupné v rámci prostředí.</span><span class="sxs-lookup"><span data-stu-id="93f55-117">There are many ways to improve this situation, depending on the infrastructure available within the environment.</span></span>

| <span data-ttu-id="93f55-118">Řešení</span><span class="sxs-lookup"><span data-stu-id="93f55-118">Solution</span></span> | <span data-ttu-id="93f55-119">Výhody</span><span class="sxs-lookup"><span data-stu-id="93f55-119">Benefits</span></span> | <span data-ttu-id="93f55-120">Požadavky</span><span class="sxs-lookup"><span data-stu-id="93f55-120">Requirements</span></span> |
| --- | --- | --- |
| <span data-ttu-id="93f55-121">Zřizovací balíček s adaptérem Ethernet</span><span class="sxs-lookup"><span data-stu-id="93f55-121">Provisioning Package with Ethernet Adaptor</span></span> | <span data-ttu-id="93f55-122">Vylepšuje možnosti počátečního nastavení a umožňuje rychlejší práci v technikech.</span><span class="sxs-lookup"><span data-stu-id="93f55-122">Improves OOBE experience and allows for a quicker technician experience.</span></span> | <span data-ttu-id="93f55-123">Kompatibilní s rozhraním USB – rozbočovač USB-C + adaptér sítě Ethernet a technik bude stále muset pracovat se zařízením pro zachycení počítače MAC a finalizaci počátečního souboru.</span><span class="sxs-lookup"><span data-stu-id="93f55-123">HoloLens compatible USB-C Hub + Ethernet adaptor, and technician will still need to interact with the device for MAC capture and OOBE finalization</span></span> |
| <span data-ttu-id="93f55-124">Autopilotování pomocí registrace v Intune přes Ethernet</span><span class="sxs-lookup"><span data-stu-id="93f55-124">Autopilot with Intune Registration over Ethernet</span></span> | <span data-ttu-id="93f55-125">Toto je připojení s jedním krokem a registrace zařízení do prostředí zákazníka.</span><span class="sxs-lookup"><span data-stu-id="93f55-125">This is a single-step connection and registration of the device to the customer environment.</span></span> <span data-ttu-id="93f55-126">Záznam MAC je možné dokončit, aniž by bylo nutné pracovat se zařízením.</span><span class="sxs-lookup"><span data-stu-id="93f55-126">MAC capture can be completed without needing to interact with the device</span></span> | <span data-ttu-id="93f55-127">Povolená Intune pro tenanta AAD zákazníka a adaptér Ethernet USB-C kompatibilní s HoloLens</span><span class="sxs-lookup"><span data-stu-id="93f55-127">Intune enabled for the customer AAD tenant and a HoloLens compatible USB-C Ethernet adaptor</span></span> |
| <span data-ttu-id="93f55-128">Automatizované vytváření sestav adres MAC</span><span class="sxs-lookup"><span data-stu-id="93f55-128">Automated reporting of MAC Addresses</span></span> | <span data-ttu-id="93f55-129">Když jsou zařízení zaregistrovaná v tenantovi Intune, může skript vykázat adresu MAC technikovi.</span><span class="sxs-lookup"><span data-stu-id="93f55-129">When devices are registered with the Intune tenant, a script can report the MAC address to the technician.</span></span> | <span data-ttu-id="93f55-130">Rutiny PowerShellu pro Intune</span><span class="sxs-lookup"><span data-stu-id="93f55-130">Intune PowerShell cmdlets</span></span> |

## <a name="provisioning-package-with-ethernet-adaptor"></a><span data-ttu-id="93f55-131">Zřizovací balíček s adaptérem Ethernet</span><span class="sxs-lookup"><span data-stu-id="93f55-131">Provisioning Package with Ethernet Adaptor</span></span>

> [!NOTE] 
> <span data-ttu-id="93f55-132">Pokud je v drátové síti i v závislosti na omezeních pro MAC, musí být adresa MAC rozbočovače USB-C + adaptér sítě Ethernet také předem schválená.</span><span class="sxs-lookup"><span data-stu-id="93f55-132">If the wired network is also subject to MAC restrictions, then the MAC address of the USB-C Hub + Ethernet adaptor will also need to be pre-approved.</span></span> <span data-ttu-id="93f55-133">S tímto adaptérem byste měli dbát, protože umožní přístup k síti z jiných zařízení.</span><span class="sxs-lookup"><span data-stu-id="93f55-133">Care should be taken with this adapter as it will allow access to the network from other devices.</span></span>

### <a name="requirements"></a><span data-ttu-id="93f55-134">Požadavky</span><span class="sxs-lookup"><span data-stu-id="93f55-134">Requirements</span></span>

- <span data-ttu-id="93f55-135">Port drátové sítě s přístupem k síti zákazníka</span><span class="sxs-lookup"><span data-stu-id="93f55-135">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="93f55-136">Rozbočovač USB-C kompatibilní s HoloLens s adaptérem Ethernet – všechny adaptéry, které nevyžadují žádné další ovladače nebo instalace aplikací, by měly být vhodné.</span><span class="sxs-lookup"><span data-stu-id="93f55-136">HoloLens Compatible USB-C Hub with Ethernet adaptor — Any adapter that doesn't require any additional drivers or application installs should be suitable.</span></span>
- <span data-ttu-id="93f55-137">Zřizovací balíček obsahující:</span><span class="sxs-lookup"><span data-stu-id="93f55-137">Provisioning Package containing:</span></span>
  - <span data-ttu-id="93f55-138">Obsahující informace o bezdrátové síti a certifikát</span><span class="sxs-lookup"><span data-stu-id="93f55-138">Containing Wireless Network information and Certificate</span></span>
  - <span data-ttu-id="93f55-139">Volitelně obsahující informace o registraci pro Azure AD organizace</span><span class="sxs-lookup"><span data-stu-id="93f55-139">Optionally containing enrollment information for the Organization's Azure AD</span></span>
  - <span data-ttu-id="93f55-140">Obsahující všechna další požadovaná nastavení zřizování</span><span class="sxs-lookup"><span data-stu-id="93f55-140">Containing any other required provisioning settings</span></span>

### <a name="process"></a><span data-ttu-id="93f55-141">Proces</span><span class="sxs-lookup"><span data-stu-id="93f55-141">Process</span></span>

<span data-ttu-id="93f55-142">Tento proces se může lišit v závislosti na úrovni softwaru daného zařízení.</span><span class="sxs-lookup"><span data-stu-id="93f55-142">The Process may vary depending on the software level of the device.</span></span> <span data-ttu-id="93f55-143">Pokud má zařízení [aktualizaci květen 2004](hololens-release-notes.md#windows-holographic-version-2004), postupujte podle následujících kroků.</span><span class="sxs-lookup"><span data-stu-id="93f55-143">If the device has the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="93f55-144">Zřizovací balíček umístěte do kořenového adresáře USB Stick a připojte se k rozbočovači.</span><span class="sxs-lookup"><span data-stu-id="93f55-144">Place the provisioning package onto the root of a USB stick, and plug into the Hub.</span></span>
2. <span data-ttu-id="93f55-145">Připojte kabel sítě Ethernet k adaptéru rozbočovače + Ethernet.</span><span class="sxs-lookup"><span data-stu-id="93f55-145">Connect Ethernet cable to the Hub + Ethernet adapter.</span></span>
3. <span data-ttu-id="93f55-146">Připojte rozbočovač USB-C k zařízení HoloLens.</span><span class="sxs-lookup"><span data-stu-id="93f55-146">Connect USB-C Hub to HoloLens device.</span></span>
4. <span data-ttu-id="93f55-147">Zapněte HoloLens a vložte ho do zařízení.</span><span class="sxs-lookup"><span data-stu-id="93f55-147">Turn on the HoloLens and put on the device.</span></span>
5. <span data-ttu-id="93f55-148">Pro použití zřizovacího balíčku stiskněte **tlačítko dolů a vypínač** .</span><span class="sxs-lookup"><span data-stu-id="93f55-148">Press the **Volume Down and Power button** to apply the Provisioning Package.</span></span>
6. <span data-ttu-id="93f55-149">Technik se teď může dodržet na začátku počáteční hodnoty a po dokončení otevřete aplikaci nastavení, která načte adresu MAC zařízení.</span><span class="sxs-lookup"><span data-stu-id="93f55-149">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

<span data-ttu-id="93f55-150">Pokud má zařízení Build operačního systému před [aktualizací květen 2004](hololens-release-notes.md#windows-holographic-version-2004), postupujte podle následujících kroků.</span><span class="sxs-lookup"><span data-stu-id="93f55-150">If the device has an OS build before the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="93f55-151">Zapněte HoloLens a připojte zařízení k počítači.</span><span class="sxs-lookup"><span data-stu-id="93f55-151">Turn on the HoloLens and plug the device into a PC.</span></span>
2. <span data-ttu-id="93f55-152">Zařízení by se mělo zobrazit na počítači jako zařízení úložiště souborů.</span><span class="sxs-lookup"><span data-stu-id="93f55-152">The device should show up on the PC as a file storage device.</span></span>
3. <span data-ttu-id="93f55-153">Zkopírování zřizovacího balíčku do zařízení</span><span class="sxs-lookup"><span data-stu-id="93f55-153">Copy the Provisioning Package to the Device</span></span>
4. <span data-ttu-id="93f55-154">Připojte kabel Ethernet k rozbočovači.</span><span class="sxs-lookup"><span data-stu-id="93f55-154">Connect Ethernet cable to the hub.</span></span>
5. <span data-ttu-id="93f55-155">Připojte rozbočovač USB-C k zařízení HoloLens.</span><span class="sxs-lookup"><span data-stu-id="93f55-155">Connect USB-C Hub to HoloLens device.</span></span>
6. <span data-ttu-id="93f55-156">Umístit na HoloLens</span><span class="sxs-lookup"><span data-stu-id="93f55-156">Put on the HoloLens</span></span>
7. <span data-ttu-id="93f55-157">Pro použití zřizovacího balíčku stiskněte tlačítko **dolů a vypínač** .</span><span class="sxs-lookup"><span data-stu-id="93f55-157">Press the **Volume Down and Power** button to apply the Provisioning Package.</span></span>
8. <span data-ttu-id="93f55-158">Technik se teď může dodržet na začátku počáteční hodnoty a po dokončení otevřete aplikaci nastavení, která načte adresu MAC zařízení.</span><span class="sxs-lookup"><span data-stu-id="93f55-158">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

### <a name="benefits"></a><span data-ttu-id="93f55-159">Výhody</span><span class="sxs-lookup"><span data-stu-id="93f55-159">Benefits</span></span>

<span data-ttu-id="93f55-160">To umožní "jedinému dotyku" zařízení, použít správný zřizovací balíček a shromažďovat adresu MAC zařízení.</span><span class="sxs-lookup"><span data-stu-id="93f55-160">This will allow a "Single touch" of the device, to apply the correct provisioning package and gather the MAC address of the device.</span></span> [<span data-ttu-id="93f55-161">Zřizovací balíčky se dají vytvořit podle pokynů uvedených tady.</span><span class="sxs-lookup"><span data-stu-id="93f55-161">Provisioning packages can be created following the guidance here.</span></span>](https://docs.microsoft.com/hololens/hololens-provisioning)

## <a name="autopilot-with-intune-enrollment"></a><span data-ttu-id="93f55-162">Automatický pilotní nasazení pomocí Intune</span><span class="sxs-lookup"><span data-stu-id="93f55-162">Autopilot with Intune Enrollment</span></span>

### <a name="requirements"></a><span data-ttu-id="93f55-163">Požadavky</span><span class="sxs-lookup"><span data-stu-id="93f55-163">Requirements</span></span>

- <span data-ttu-id="93f55-164">Port drátové sítě s přístupem k síti zákazníka</span><span class="sxs-lookup"><span data-stu-id="93f55-164">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="93f55-165">Zařízení HoloLens s Windows holografickým 2004</span><span class="sxs-lookup"><span data-stu-id="93f55-165">HoloLens devices running Windows Holographic 2004</span></span>
- <span data-ttu-id="93f55-166">Ethernetový adaptér USB-C kompatibilní s HoloLens</span><span class="sxs-lookup"><span data-stu-id="93f55-166">HoloLens Compatible USB-C Ethernet adapter</span></span>
- <span data-ttu-id="93f55-167">Nastavení a povolení Intune pro tenanta zákazníka</span><span class="sxs-lookup"><span data-stu-id="93f55-167">Intune set up and enabled for the customer Tenant</span></span>
- <span data-ttu-id="93f55-168">Zařízení zaregistrované pro autopilotování a naimportované do tenanta zákazníka</span><span class="sxs-lookup"><span data-stu-id="93f55-168">Device registered for Autopilot and imported into the Customer Tenant</span></span>
- <span data-ttu-id="93f55-169">Zásady Intune definované pro zařízení:</span><span class="sxs-lookup"><span data-stu-id="93f55-169">Intune Policies defined for the device:</span></span>
   - <span data-ttu-id="93f55-170">Obsahující informace o bezdrátové síti a certifikát</span><span class="sxs-lookup"><span data-stu-id="93f55-170">Containing Wireless Network information and Certificate</span></span>
   - <span data-ttu-id="93f55-171">Obsahující všechna další požadovaná nastavení zřizování</span><span class="sxs-lookup"><span data-stu-id="93f55-171">Containing any other required provisioning settings</span></span>

<span data-ttu-id="93f55-172">To umožní zákazníkovi s pokročilými požadavky na síť zaregistrovat zařízení v praxi, škálovatelný přístup</span><span class="sxs-lookup"><span data-stu-id="93f55-172">This will allow a customer with advanced networking requirements to enroll the devices in a hands-off, scalable approach</span></span>

<span data-ttu-id="93f55-173">Další požadavky budete potřebovat, jak je uvedeno níže:</span><span class="sxs-lookup"><span data-stu-id="93f55-173">Additional pre-requisites will be needed as below:</span></span>
1. <span data-ttu-id="93f55-174">[Povolte tenanta pro verzi Preview programu autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot).</span><span class="sxs-lookup"><span data-stu-id="93f55-174">[Enable the Tenant for the Autopilot preview](https://docs.microsoft.com/hololens/hololens2-autopilot).</span></span>
1. <span data-ttu-id="93f55-175">Vytvořte zásady HoloLens pro nahrazení zřizovacího balíčku v Intune.</span><span class="sxs-lookup"><span data-stu-id="93f55-175">Create the HoloLens policies to replace the Provisioning Package within Intune.</span></span>
1. <span data-ttu-id="93f55-176">Vytvořte zásady pro HoloLens Intune.</span><span class="sxs-lookup"><span data-stu-id="93f55-176">Create the HoloLens Intune Policies.</span></span>
1. <span data-ttu-id="93f55-177">Přiřaďte zařízení ke správné skupině.</span><span class="sxs-lookup"><span data-stu-id="93f55-177">Assign the devices to the correct group.</span></span>

### <a name="process"></a><span data-ttu-id="93f55-178">Proces</span><span class="sxs-lookup"><span data-stu-id="93f55-178">Process</span></span>

1. <span data-ttu-id="93f55-179">Připojte kabel sítě Ethernet k adaptéru a připojte adaptér k portu USB-C na zařízení HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="93f55-179">Connect the ethernet cable to the adapter and plug the adapter into the USB-C port on the HoloLens 2 device.</span></span>

2. <span data-ttu-id="93f55-180">Zapněte HoloLens.</span><span class="sxs-lookup"><span data-stu-id="93f55-180">Turn on the HoloLens.</span></span>

3. <span data-ttu-id="93f55-181">Zařízení by se mělo automaticky připojit k Internetu během OOBE přes adaptér sítě Ethernet.</span><span class="sxs-lookup"><span data-stu-id="93f55-181">The device should automatically connect to the internet during OOBE via the Ethernet adaptor.</span></span> <span data-ttu-id="93f55-182">Měl by detekovat konfiguraci autopilotu a automaticky se registrovat v Azure AD a Intune.</span><span class="sxs-lookup"><span data-stu-id="93f55-182">It should detect the Autopilot configuration and automatically register with Azure AD and Intune.</span></span>

4. <span data-ttu-id="93f55-183">Zařízení použije požadované Wi-Fi certifikáty a další konfiguraci podle potřeby prostřednictvím Intune.</span><span class="sxs-lookup"><span data-stu-id="93f55-183">The Device will apply the required Wi-Fi Certificates and other configuration as needed via Intune.</span></span>

5. <span data-ttu-id="93f55-184">Po dokončení může technik načíst portál Intune (správce koncových bodů) a přejít na stránku vlastností zařízení na stránce **Domů-> zařízení-> zařízení-> hardware**.</span><span class="sxs-lookup"><span data-stu-id="93f55-184">When complete, the technician can load the Intune (Endpoint Manager) Portal and drill into the device properties page at **Home -> Devices -> DeviceName -> Hardware**.</span></span>

6. <span data-ttu-id="93f55-185">Adresa MAC Wi-Fi bude viditelná v portálu Intune.</span><span class="sxs-lookup"><span data-stu-id="93f55-185">The Wi-Fi MAC address will be visible within the Intune Portal.</span></span>

   ![Adresa MAC přes Intune](images/mac-address-intune.jpg)

7. <span data-ttu-id="93f55-187">Technik přidá tuto adresu MAC jako povolené zařízení.</span><span class="sxs-lookup"><span data-stu-id="93f55-187">The technician will add this MAC address as an allowed device.</span></span>

### <a name="benefits"></a><span data-ttu-id="93f55-188">Výhody</span><span class="sxs-lookup"><span data-stu-id="93f55-188">Benefits</span></span>

<span data-ttu-id="93f55-189">Tím umožníte, aby se v Technikě v rámci nasazení v nástroji "prošly" možnosti nasazení, které zařízení dokáže přejít do služby Azure AD a Intune, aniž by bylo nutné, aby zařízení využilo zařízení nebo ručně nespolupracovalo s prostředím HoloLens.</span><span class="sxs-lookup"><span data-stu-id="93f55-189">This will allow a "Heads off" deployment experience for the Technician, with the device being able to go from the box to enrolled in Azure AD and Intune without the technician having to wear the device or manually interact with the HoloLens environment.</span></span>

## <a name="reporting-of-mac-addresses-to-the-technician"></a><span data-ttu-id="93f55-190">Hlášení adres MAC technikům</span><span class="sxs-lookup"><span data-stu-id="93f55-190">Reporting of MAC addresses to the Technician</span></span>

### <a name="requirements"></a><span data-ttu-id="93f55-191">Požadavky</span><span class="sxs-lookup"><span data-stu-id="93f55-191">Requirements</span></span>

- <span data-ttu-id="93f55-192">Autorizace "Intune Graph PowerShellu" proti klientovi zákazníka</span><span class="sxs-lookup"><span data-stu-id="93f55-192">Authorization of the "Intune Graph PowerShell" against the customer Tenant</span></span>
- <span data-ttu-id="93f55-193">Instalace prostředí Intune Graph PowerShellu na stroji technici</span><span class="sxs-lookup"><span data-stu-id="93f55-193">Installation of the Intune Graph PowerShell on the technicians machine.</span></span>
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- <span data-ttu-id="93f55-194">Přístup pro čtení do prvků spravovaná zařízení v Intune</span><span class="sxs-lookup"><span data-stu-id="93f55-194">Read access to the "Managed Devices" elements of Intune.</span></span> <span data-ttu-id="93f55-195">(Operátor helpdesku nebo výše nebo vlastní role)</span><span class="sxs-lookup"><span data-stu-id="93f55-195">(Help Desk Operator or above, or a custom role)</span></span>

<span data-ttu-id="93f55-196">V současné době neexistuje jednoduchý způsob, jak aktivovat příkaz automatizace na základě registrace nového zařízení v Intune.</span><span class="sxs-lookup"><span data-stu-id="93f55-196">At present, there is no "simple" way to trigger an automation command based on the enrollment of a new device within Intune.</span></span> <span data-ttu-id="93f55-197">Proto tento příkaz poskytne technikovi jednoduchý způsob, jak načíst adresu MAC, aniž by se musela přihlásit na portál a ručně ji načíst.</span><span class="sxs-lookup"><span data-stu-id="93f55-197">Therefore, this command will provide the technician a simple way to retrieve the MAC address without needing to log onto the portal and manually retrieve it.</span></span>

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

<span data-ttu-id="93f55-198">Tato akce vrátí název a adresu MAC všech zařízení HoloLens, která byla zaregistrována za posledních 30 dní.</span><span class="sxs-lookup"><span data-stu-id="93f55-198">This will return the name and MAC address of any HoloLens devices that have been enrolled in the last 30 days.</span></span>

![Adresa MAC prostřednictvím PowerShellu](images/mac-address-powershell.jpg)

### <a name="process"></a><span data-ttu-id="93f55-200">Proces</span><span class="sxs-lookup"><span data-stu-id="93f55-200">Process</span></span>

<span data-ttu-id="93f55-201">Po dokončení registrace Intune technik spustí výše uvedený skript, který načte adresu MAC.</span><span class="sxs-lookup"><span data-stu-id="93f55-201">After the Intune enrollment has completed, the Technician would run the above script to retrieve the MAC address.</span></span>
