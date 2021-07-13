---
title: Enterprise Registrace zařízení HoloLens v prostředí s omezenými adresami MAC Wi-Fi Prostředí
description: Jak adresou MAC pro síť na zařízeních HoloLens 2
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
ms.openlocfilehash: 7938a433921a096913986f5eccff953fd17f1534
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639433"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a><span data-ttu-id="ba66d-103">Enterprise Registrace zařízení HoloLens v prostředí s omezenými adresami MAC Wi-Fi Prostředí</span><span class="sxs-lookup"><span data-stu-id="ba66d-103">Enterprise Enrollment of HoloLens Devices in MAC address restricted Wi-Fi Environment</span></span>

<span data-ttu-id="ba66d-104">Tento dokument popisuje běžný scénář, který jsme identifikovali v zákaznických prostředích, kde je Wi-Fi omezený adresami MAC, nebo jsou vyžadovány certifikáty pro připojení k bezdrátovým sítím.</span><span class="sxs-lookup"><span data-stu-id="ba66d-104">This document will describe a common scenario we have identified within customer environments where the Wi-Fi is restricted by MAC addresses, or certificates are required to join Wireless networks.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="ba66d-105">Ukázkový scénář</span><span class="sxs-lookup"><span data-stu-id="ba66d-105">Example Scenario</span></span>

<span data-ttu-id="ba66d-106">Mnoho zákazníků v zabezpečených prostředích má omezení v bezdrátových nebo drátových sítích, která umožní úspěšné připojení jenom schváleným zařízením (na základě adres MAC).</span><span class="sxs-lookup"><span data-stu-id="ba66d-106">Many customers in secure environments have restrictions on their Wireless or wired networks that will only allow approved devices (based on MAC Addresses) to connect successfully.</span></span> <span data-ttu-id="ba66d-107">To může být vynuceno prostřednictvím filtrování adres MAC v bezdrátovém přístupového bodu nebo prostřednictvím serveru DHCP.</span><span class="sxs-lookup"><span data-stu-id="ba66d-107">This may be enforced through MAC Address filtering on a Wireless Access Point or through a DHCP server.</span></span> <span data-ttu-id="ba66d-108">Kromě toho některé bezdrátové sítě mohou být chráněny protokolem PEAP, který vyžaduje, aby certifikát se použil na zařízení před ověřením v bezdrátové síti.</span><span class="sxs-lookup"><span data-stu-id="ba66d-108">Additionally, some Wireless networks can be protected with PEAP, which requires that a certificate be applied to the device prior to authenticating on the Wireless network.</span></span>

<span data-ttu-id="ba66d-109">V tomto scénáři mohou dva klíčové požadavky způsobit zpoždění nebo vyžadovat ruční zásah HoloLens zařízení k síti:</span><span class="sxs-lookup"><span data-stu-id="ba66d-109">In this scenario, two key requirements may introduce delays or require manual intervention when joining HoloLens devices to the network:</span></span>

- <span data-ttu-id="ba66d-110">Certifikát protokolu PEAP bezdrátové sítě musí být použita na zařízení před úspěšné připojení zařízení k bezdrátové síti.</span><span class="sxs-lookup"><span data-stu-id="ba66d-110">The Wireless PEAP certificate must be applied to the device prior to the device successfully joining the wireless network.</span></span>
- <span data-ttu-id="ba66d-111">Adresa MAC adaptéru HoloLens Wi-Fi musí být zaregistrovaná.</span><span class="sxs-lookup"><span data-stu-id="ba66d-111">The MAC Address of the HoloLens Wi-Fi adaptor must be registered.</span></span>

<span data-ttu-id="ba66d-112">Základní problémy s výše uvedenými požadavky jsou následující:</span><span class="sxs-lookup"><span data-stu-id="ba66d-112">The core challenges with the requirements above are:</span></span>

1. <span data-ttu-id="ba66d-113">Adresu MAC je aktuálně možné identifikovat pouze z Nastavení zařízení nebo z Intune po úspěšné registraci.</span><span class="sxs-lookup"><span data-stu-id="ba66d-113">The MAC Address can currently only be identified from the Settings app on the device, or from Intune after a successful enrollment.</span></span>

2. <span data-ttu-id="ba66d-114">Bez adresy MAC se zařízení nemůže připojit ke Wi-Fi Network a zahájit registraci.</span><span class="sxs-lookup"><span data-stu-id="ba66d-114">Without the MAC address, the device cannot join the Wi-Fi Network to begin enrollment.</span></span>

3. <span data-ttu-id="ba66d-115">Ruční alternativní řešení těchto problémů vyžadují, aby technik se zařízením komunikoval.</span><span class="sxs-lookup"><span data-stu-id="ba66d-115">Manual workarounds to these challenges require a technician to interact with the device.</span></span>

## <a name="solutions"></a><span data-ttu-id="ba66d-116">Řešení</span><span class="sxs-lookup"><span data-stu-id="ba66d-116">Solutions</span></span>

<span data-ttu-id="ba66d-117">V závislosti na infrastruktuře dostupné v rámci prostředí existuje mnoho způsobů, jak tuto situaci vylepšit.</span><span class="sxs-lookup"><span data-stu-id="ba66d-117">There are many ways to improve this situation, depending on the infrastructure available within the environment.</span></span>

| <span data-ttu-id="ba66d-118">Řešení</span><span class="sxs-lookup"><span data-stu-id="ba66d-118">Solution</span></span> | <span data-ttu-id="ba66d-119">Výhody</span><span class="sxs-lookup"><span data-stu-id="ba66d-119">Benefits</span></span> | <span data-ttu-id="ba66d-120">Požadavky</span><span class="sxs-lookup"><span data-stu-id="ba66d-120">Requirements</span></span> |
| --- | --- | --- |
| <span data-ttu-id="ba66d-121">Zřizovací balíček s adaptérem sítě Ethernet</span><span class="sxs-lookup"><span data-stu-id="ba66d-121">Provisioning Package with Ethernet Adaptor</span></span> | <span data-ttu-id="ba66d-122">Vylepšuje prostředí pro OOBE a umožňuje rychlejší prostředí techniků.</span><span class="sxs-lookup"><span data-stu-id="ba66d-122">Improves OOBE experience and allows for a quicker technician experience.</span></span> | <span data-ttu-id="ba66d-123">HoloLens adaptérem USB-C Hub + Ethernet a technik bude muset se zařízením stále pracovat kvůli zachycení mac a finalizaci OOBE.</span><span class="sxs-lookup"><span data-stu-id="ba66d-123">HoloLens compatible USB-C Hub + Ethernet adaptor, and technician will still need to interact with the device for MAC capture and OOBE finalization</span></span> |
| <span data-ttu-id="ba66d-124">Autopilot s registrací Přes Ethernet v Intune</span><span class="sxs-lookup"><span data-stu-id="ba66d-124">Autopilot with Intune Registration over Ethernet</span></span> | <span data-ttu-id="ba66d-125">Jedná se o jednokrokové připojení a registraci zařízení do prostředí zákazníka.</span><span class="sxs-lookup"><span data-stu-id="ba66d-125">This is a single-step connection and registration of the device to the customer environment.</span></span> <span data-ttu-id="ba66d-126">Zachytávání maců je možné dokončit bez nutnosti interakce se zařízením.</span><span class="sxs-lookup"><span data-stu-id="ba66d-126">MAC capture can be completed without needing to interact with the device</span></span> | <span data-ttu-id="ba66d-127">Služba Intune povolená pro tenanta AAD zákazníka a HoloLens adaptér sítě Ethernet KOMPATIBILNÍ s USB-C</span><span class="sxs-lookup"><span data-stu-id="ba66d-127">Intune enabled for the customer AAD tenant and a HoloLens compatible USB-C Ethernet adaptor</span></span> |
| <span data-ttu-id="ba66d-128">Automatizované generování sestav adres MAC</span><span class="sxs-lookup"><span data-stu-id="ba66d-128">Automated reporting of MAC Addresses</span></span> | <span data-ttu-id="ba66d-129">Když jsou zařízení zaregistrovaná v tenantovi Intune, skript může adresu MAC nahlásit technikovi.</span><span class="sxs-lookup"><span data-stu-id="ba66d-129">When devices are registered with the Intune tenant, a script can report the MAC address to the technician.</span></span> | <span data-ttu-id="ba66d-130">Rutiny PowerShellu pro Intune</span><span class="sxs-lookup"><span data-stu-id="ba66d-130">Intune PowerShell cmdlets</span></span> |

## <a name="provisioning-package-with-ethernet-adaptor"></a><span data-ttu-id="ba66d-131">Zřizovací balíček s adaptérem sítě Ethernet</span><span class="sxs-lookup"><span data-stu-id="ba66d-131">Provisioning Package with Ethernet Adaptor</span></span>

> [!NOTE] 
> <span data-ttu-id="ba66d-132">Pokud se na drátovou síť vztahují také omezení MAC, bude také potřeba předem schválit adresu MAC rozbočovače USB-C a ethernetového adaptéru.</span><span class="sxs-lookup"><span data-stu-id="ba66d-132">If the wired network is also subject to MAC restrictions, then the MAC address of the USB-C Hub + Ethernet adaptor will also need to be pre-approved.</span></span> <span data-ttu-id="ba66d-133">Tento adaptér je třeba pečovat, protože umožňuje přístup k síti z jiných zařízení.</span><span class="sxs-lookup"><span data-stu-id="ba66d-133">Care should be taken with this adapter as it will allow access to the network from other devices.</span></span>

### <a name="requirements"></a><span data-ttu-id="ba66d-134">Požadavky</span><span class="sxs-lookup"><span data-stu-id="ba66d-134">Requirements</span></span>

- <span data-ttu-id="ba66d-135">Port drátové sítě s přístupem k síti zákazníka</span><span class="sxs-lookup"><span data-stu-id="ba66d-135">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="ba66d-136">HoloLens Kompatibilní rozbočovač USB-C s ethernetovým adaptérem – Jakýkoli adaptér, který nevyžaduje žádné další ovladače nebo instalaci aplikací, by měl být vhodný.</span><span class="sxs-lookup"><span data-stu-id="ba66d-136">HoloLens Compatible USB-C Hub with Ethernet adaptor — Any adapter that doesn't require any additional drivers or application installs should be suitable.</span></span>
- <span data-ttu-id="ba66d-137">Zřizovací balíček obsahující:</span><span class="sxs-lookup"><span data-stu-id="ba66d-137">Provisioning Package containing:</span></span>
  - <span data-ttu-id="ba66d-138">Obsahující informace o bezdrátové síti a certifikát</span><span class="sxs-lookup"><span data-stu-id="ba66d-138">Containing Wireless Network information and Certificate</span></span>
  - <span data-ttu-id="ba66d-139">Volitelně obsahující informace o registraci pro Azure AD organizace</span><span class="sxs-lookup"><span data-stu-id="ba66d-139">Optionally containing enrollment information for the Organization's Azure AD</span></span>
  - <span data-ttu-id="ba66d-140">Obsahuje další požadovaná nastavení zřizování.</span><span class="sxs-lookup"><span data-stu-id="ba66d-140">Containing any other required provisioning settings</span></span>

### <a name="process"></a><span data-ttu-id="ba66d-141">Proces</span><span class="sxs-lookup"><span data-stu-id="ba66d-141">Process</span></span>

<span data-ttu-id="ba66d-142">Proces se může lišit v závislosti na úrovni softwaru zařízení.</span><span class="sxs-lookup"><span data-stu-id="ba66d-142">The Process may vary depending on the software level of the device.</span></span> <span data-ttu-id="ba66d-143">Pokud má zařízení aktualizaci [z května 2004,](hololens-release-notes.md#windows-holographic-version-2004)postupujte podle následujících kroků.</span><span class="sxs-lookup"><span data-stu-id="ba66d-143">If the device has the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="ba66d-144">Umístěte zřizovací balíček do kořenového adresáře USB flash disku a připojte se k rozbočovači.</span><span class="sxs-lookup"><span data-stu-id="ba66d-144">Place the provisioning package onto the root of a USB stick, and plug into the Hub.</span></span>
2. <span data-ttu-id="ba66d-145">Připojení Ethernetový kabel k rozbočovači + ethernetovému adaptéru.</span><span class="sxs-lookup"><span data-stu-id="ba66d-145">Connect Ethernet cable to the Hub + Ethernet adapter.</span></span>
3. <span data-ttu-id="ba66d-146">Připojení Rozbočovač USB-C HoloLens zařízení.</span><span class="sxs-lookup"><span data-stu-id="ba66d-146">Connect USB-C Hub to HoloLens device.</span></span>
4. <span data-ttu-id="ba66d-147">Zapněte HoloLens zařízení.</span><span class="sxs-lookup"><span data-stu-id="ba66d-147">Turn on the HoloLens and put on the device.</span></span>
5. <span data-ttu-id="ba66d-148">Stisknutím tlačítka **Volume Down (Snížení objemu)** a Power (Napájení) použijte zřizovací balíček.</span><span class="sxs-lookup"><span data-stu-id="ba66d-148">Press the **Volume Down and Power button** to apply the Provisioning Package.</span></span>
6. <span data-ttu-id="ba66d-149">Technik teď může postupovat podle pokynů pro OOBE a po dokončení otevřít aplikaci Nastavení a načíst adresu MAC zařízení.</span><span class="sxs-lookup"><span data-stu-id="ba66d-149">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

<span data-ttu-id="ba66d-150">Pokud má zařízení build operačního systému před aktualizací z května [2004,](hololens-release-notes.md#windows-holographic-version-2004)postupujte následovně.</span><span class="sxs-lookup"><span data-stu-id="ba66d-150">If the device has an OS build before the [May 2004 update](hololens-release-notes.md#windows-holographic-version-2004), follow the steps below.</span></span>

1. <span data-ttu-id="ba66d-151">Zapněte počítač HoloLens připojte zařízení k počítači.</span><span class="sxs-lookup"><span data-stu-id="ba66d-151">Turn on the HoloLens and plug the device into a PC.</span></span>
2. <span data-ttu-id="ba66d-152">Zařízení by se mělo v počítači zobrazit jako zařízení úložiště souborů.</span><span class="sxs-lookup"><span data-stu-id="ba66d-152">The device should show up on the PC as a file storage device.</span></span>
3. <span data-ttu-id="ba66d-153">Zkopírování zřizovacího balíčku do zařízení</span><span class="sxs-lookup"><span data-stu-id="ba66d-153">Copy the Provisioning Package to the Device</span></span>
4. <span data-ttu-id="ba66d-154">Připojení Ethernetový kabel k rozbočovači.</span><span class="sxs-lookup"><span data-stu-id="ba66d-154">Connect Ethernet cable to the hub.</span></span>
5. <span data-ttu-id="ba66d-155">Připojení Rozbočovač USB-C HoloLens zařízení.</span><span class="sxs-lookup"><span data-stu-id="ba66d-155">Connect USB-C Hub to HoloLens device.</span></span>
6. <span data-ttu-id="ba66d-156">Dejte na HoloLens</span><span class="sxs-lookup"><span data-stu-id="ba66d-156">Put on the HoloLens</span></span>
7. <span data-ttu-id="ba66d-157">Stisknutím tlačítka **Volume Down (Snížení objemu)** a Power (Napájení) použijte zřizovací balíček.</span><span class="sxs-lookup"><span data-stu-id="ba66d-157">Press the **Volume Down and Power** button to apply the Provisioning Package.</span></span>
8. <span data-ttu-id="ba66d-158">Technik teď může postupovat podle pokynů pro OOBE a po dokončení otevřít aplikaci Nastavení a načíst adresu MAC zařízení.</span><span class="sxs-lookup"><span data-stu-id="ba66d-158">The technician can now follow OOBE, and when complete, open the Settings App to retrieve the MAC Address of the device.</span></span>

### <a name="benefits"></a><span data-ttu-id="ba66d-159">Výhody</span><span class="sxs-lookup"><span data-stu-id="ba66d-159">Benefits</span></span>

<span data-ttu-id="ba66d-160">To umožní jedinému dotykovému ovládání zařízení použít správný zřizovací balíček a shromáždit adresu MAC zařízení.</span><span class="sxs-lookup"><span data-stu-id="ba66d-160">This will allow a "Single touch" of the device, to apply the correct provisioning package and gather the MAC address of the device.</span></span> [<span data-ttu-id="ba66d-161">Zřizovací balíčky můžete vytvořit podle těchto pokynů.</span><span class="sxs-lookup"><span data-stu-id="ba66d-161">Provisioning packages can be created following the guidance here.</span></span>](hololens-provisioning.md)

## <a name="autopilot-with-intune-enrollment"></a><span data-ttu-id="ba66d-162">Autopilot s registrací do Intune</span><span class="sxs-lookup"><span data-stu-id="ba66d-162">Autopilot with Intune Enrollment</span></span>

### <a name="requirements"></a><span data-ttu-id="ba66d-163">Požadavky</span><span class="sxs-lookup"><span data-stu-id="ba66d-163">Requirements</span></span>

- <span data-ttu-id="ba66d-164">Port drátové sítě s přístupem k síti zákazníka</span><span class="sxs-lookup"><span data-stu-id="ba66d-164">Wired network port with access to the customer network</span></span>
- <span data-ttu-id="ba66d-165">HoloLens zařízení s Windows Holographic 2004</span><span class="sxs-lookup"><span data-stu-id="ba66d-165">HoloLens devices running Windows Holographic 2004</span></span>
- <span data-ttu-id="ba66d-166">HoloLens Kompatibilní ethernetový adaptér USB-C</span><span class="sxs-lookup"><span data-stu-id="ba66d-166">HoloLens Compatible USB-C Ethernet adapter</span></span>
- <span data-ttu-id="ba66d-167">Nastavení a povolení Intune pro tenanta zákazníka</span><span class="sxs-lookup"><span data-stu-id="ba66d-167">Intune set up and enabled for the customer Tenant</span></span>
- <span data-ttu-id="ba66d-168">Zařízení zaregistrované pro Autopilot a importované do tenanta zákazníka</span><span class="sxs-lookup"><span data-stu-id="ba66d-168">Device registered for Autopilot and imported into the Customer Tenant</span></span>
- <span data-ttu-id="ba66d-169">Zásady Intune definované pro zařízení:</span><span class="sxs-lookup"><span data-stu-id="ba66d-169">Intune Policies defined for the device:</span></span>
   - <span data-ttu-id="ba66d-170">Obsahující informace o bezdrátové síti a certifikát</span><span class="sxs-lookup"><span data-stu-id="ba66d-170">Containing Wireless Network information and Certificate</span></span>
   - <span data-ttu-id="ba66d-171">Obsahuje další požadovaná nastavení zřizování.</span><span class="sxs-lookup"><span data-stu-id="ba66d-171">Containing any other required provisioning settings</span></span>

<span data-ttu-id="ba66d-172">To umožní zákazníkovi s pokročilými požadavky na síť zaregistrovat zařízení pomocí hands-off a škálovatelného přístupu.</span><span class="sxs-lookup"><span data-stu-id="ba66d-172">This will allow a customer with advanced networking requirements to enroll the devices in a hands-off, scalable approach</span></span>

<span data-ttu-id="ba66d-173">Budete potřebovat další požadavky, jak je uvedeno níže:</span><span class="sxs-lookup"><span data-stu-id="ba66d-173">Additional pre-requisites will be needed as below:</span></span>
1. <span data-ttu-id="ba66d-174">[Povolte tenanta pro Autopilot Preview.](hololens2-autopilot.md)</span><span class="sxs-lookup"><span data-stu-id="ba66d-174">[Enable the Tenant for the Autopilot preview](hololens2-autopilot.md).</span></span>
1. <span data-ttu-id="ba66d-175">Vytvořte zásady HoloLens, které nahradí zřizovací balíček v Rámci Intune.</span><span class="sxs-lookup"><span data-stu-id="ba66d-175">Create the HoloLens policies to replace the Provisioning Package within Intune.</span></span>
1. <span data-ttu-id="ba66d-176">Vytvořte HoloLens Intune.</span><span class="sxs-lookup"><span data-stu-id="ba66d-176">Create the HoloLens Intune Policies.</span></span>
1. <span data-ttu-id="ba66d-177">Přiřaďte zařízení ke správné skupině.</span><span class="sxs-lookup"><span data-stu-id="ba66d-177">Assign the devices to the correct group.</span></span>

### <a name="process"></a><span data-ttu-id="ba66d-178">Proces</span><span class="sxs-lookup"><span data-stu-id="ba66d-178">Process</span></span>

1. <span data-ttu-id="ba66d-179">Připojení ethernetový kabel k adaptéru a připojte adaptér k portu USB-C na HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="ba66d-179">Connect the ethernet cable to the adapter and plug the adapter into the USB-C port on the HoloLens 2 device.</span></span>

2. <span data-ttu-id="ba66d-180">Zapněte HoloLens.</span><span class="sxs-lookup"><span data-stu-id="ba66d-180">Turn on the HoloLens.</span></span>

3. <span data-ttu-id="ba66d-181">Zařízení by se mělo automaticky připojit k internetu během OOBE přes ethernetový adaptér.</span><span class="sxs-lookup"><span data-stu-id="ba66d-181">The device should automatically connect to the internet during OOBE via the Ethernet adaptor.</span></span> <span data-ttu-id="ba66d-182">Měla by zjistit konfiguraci Autopilotu a automaticky se zaregistrovat v Azure AD a Intune.</span><span class="sxs-lookup"><span data-stu-id="ba66d-182">It should detect the Autopilot configuration and automatically register with Azure AD and Intune.</span></span>

4. <span data-ttu-id="ba66d-183">Zařízení použije požadované certifikáty Wi-Fi a další konfiguraci podle potřeby prostřednictvím Intune.</span><span class="sxs-lookup"><span data-stu-id="ba66d-183">The Device will apply the required Wi-Fi Certificates and other configuration as needed via Intune.</span></span>

5. <span data-ttu-id="ba66d-184">Po dokončení může technik načíst portál Intune (Endpoint Manager) a přejít na stránku vlastností zařízení na domovské stránce **-> Devices -> DeviceName -> Hardware**.</span><span class="sxs-lookup"><span data-stu-id="ba66d-184">When complete, the technician can load the Intune (Endpoint Manager) Portal and drill into the device properties page at **Home -> Devices -> DeviceName -> Hardware**.</span></span>

6. <span data-ttu-id="ba66d-185">Adresa MAC Wi-Fi zobrazí na portálu Intune.</span><span class="sxs-lookup"><span data-stu-id="ba66d-185">The Wi-Fi MAC address will be visible within the Intune Portal.</span></span>

   ![Adresa MAC přes Intune](images/mac-address-intune.jpg)

7. <span data-ttu-id="ba66d-187">Technik přidá tuto adresu MAC jako povolené zařízení.</span><span class="sxs-lookup"><span data-stu-id="ba66d-187">The technician will add this MAC address as an allowed device.</span></span>

### <a name="benefits"></a><span data-ttu-id="ba66d-188">Výhody</span><span class="sxs-lookup"><span data-stu-id="ba66d-188">Benefits</span></span>

<span data-ttu-id="ba66d-189">To technikovi umožní nasazení "bez problémů", kdy zařízení může přejít z krabice do Azure AD a Intune, aniž by technik museli zařízení používat nebo ručně pracovat s HoloLens prostředím.</span><span class="sxs-lookup"><span data-stu-id="ba66d-189">This will allow a "Heads off" deployment experience for the Technician, with the device being able to go from the box to enrolled in Azure AD and Intune without the technician having to wear the device or manually interact with the HoloLens environment.</span></span>

## <a name="reporting-of-mac-addresses-to-the-technician"></a><span data-ttu-id="ba66d-190">Hlášení adres MAC technikovi</span><span class="sxs-lookup"><span data-stu-id="ba66d-190">Reporting of MAC addresses to the Technician</span></span>

### <a name="requirements"></a><span data-ttu-id="ba66d-191">Požadavky</span><span class="sxs-lookup"><span data-stu-id="ba66d-191">Requirements</span></span>

- <span data-ttu-id="ba66d-192">Autorizace "Intune Graph PowerShellu" vůči zákaznickému tenantovi</span><span class="sxs-lookup"><span data-stu-id="ba66d-192">Authorization of the "Intune Graph PowerShell" against the customer Tenant</span></span>
- <span data-ttu-id="ba66d-193">Instalace Intune Graph PowerShellu na počítači techniků.</span><span class="sxs-lookup"><span data-stu-id="ba66d-193">Installation of the Intune Graph PowerShell on the technicians machine.</span></span>
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- <span data-ttu-id="ba66d-194">Přístup pro čtení k prvkům "Spravovaná zařízení" v Intune.</span><span class="sxs-lookup"><span data-stu-id="ba66d-194">Read access to the "Managed Devices" elements of Intune.</span></span> <span data-ttu-id="ba66d-195">(Operátor help desky nebo vyšší nebo vlastní role)</span><span class="sxs-lookup"><span data-stu-id="ba66d-195">(Help Desk Operator or above, or a custom role)</span></span>

<span data-ttu-id="ba66d-196">V současné době neexistuje žádný "jednoduchý" způsob aktivace příkazu automatizace na základě registrace nového zařízení v Intune.</span><span class="sxs-lookup"><span data-stu-id="ba66d-196">At present, there is no "simple" way to trigger an automation command based on the enrollment of a new device within Intune.</span></span> <span data-ttu-id="ba66d-197">Tento příkaz proto technikovi poskytne jednoduchý způsob, jak získat adresu MAC, aniž by se muset přihlásit k portálu a ručně ji načíst.</span><span class="sxs-lookup"><span data-stu-id="ba66d-197">Therefore, this command will provide the technician a simple way to retrieve the MAC address without needing to log onto the portal and manually retrieve it.</span></span>

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

<span data-ttu-id="ba66d-198">Vrátí se název a adresa MAC všech zařízení HoloLens která byla zaregistrovaná během posledních 30 dnů.</span><span class="sxs-lookup"><span data-stu-id="ba66d-198">This will return the name and MAC address of any HoloLens devices that have been enrolled in the last 30 days.</span></span>

![Adresa MAC přes PowerShell](images/mac-address-powershell.jpg)

### <a name="process"></a><span data-ttu-id="ba66d-200">Proces</span><span class="sxs-lookup"><span data-stu-id="ba66d-200">Process</span></span>

<span data-ttu-id="ba66d-201">Po dokončení registrace Intune technik spustí výše uvedený skript, který načte adresu MAC.</span><span class="sxs-lookup"><span data-stu-id="ba66d-201">After the Intune enrollment has completed, the Technician would run the above script to retrieve the MAC address.</span></span>
