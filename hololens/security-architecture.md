---
title: Architektura zabezpečení HoloLens
description: Architektura zabezpečení
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, hololens 2, hololens2 security, security overview, security architecture, architecture, hololens 2 architecture
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d8e68f73d05db397a7ee088382e82dfa762177b0
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379223"
---
# <a name="security-overview-and-architecture"></a><span data-ttu-id="6e620-104">Přehled a architektura zabezpečení</span><span class="sxs-lookup"><span data-stu-id="6e620-104">Security overview and architecture</span></span>

<span data-ttu-id="6e620-105">Architektura zabezpečení HoloLens 2 byla od základů navržena a zkonstruována tak, aby byla bez problémů se staršími verzemi zabezpečení a zároveň byla vytvořena minimální úroveň útoku.</span><span class="sxs-lookup"><span data-stu-id="6e620-105">The HoloLens 2 security architecture was designed and engineered from the ground up to be free from legacy security issues, while creating a minimized attack surface.</span></span> <span data-ttu-id="6e620-106">Tato nová inovativní architektura nabízí zabezpečená umístění úložiště a pokročilé prvky zabezpečení s mechanismy, které umožňují chránit operační systémy před potenciálními hrozbami a ohroženími zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="6e620-106">This new, innovative architecture offers secure storage locations and advanced security elements, with mechanisms capable of shielding operating systems from potential threats and vulnerabilities.</span></span>

<span data-ttu-id="6e620-107">HoloLens 2 kombinuje hardware, software, sítě a služby pro zajištění koncového zabezpečení a současně poskytuje uživatelům optimální prostředí.</span><span class="sxs-lookup"><span data-stu-id="6e620-107">HoloLens 2 combines hardware, software, networking, and services to deliver end-to-end security, while providing the user with an optimal experience.</span></span> <span data-ttu-id="6e620-108">S HoloLens 2 je teď velká většina funkcí zabezpečení zapnutá automaticky, což minimalizuje úsilí potřebné ke správnému nastavení a konfiguraci operačního systému.</span><span class="sxs-lookup"><span data-stu-id="6e620-108">With HoloLens 2, a large majority of security features are now turned on automatically, minimizing the effort required to correctly set up and configure the operating system.</span></span>

<span data-ttu-id="6e620-109">Windows HoloLens 2 a architektura operačního systému nabízejí tyto inovativní funkce zabezpečení:</span><span class="sxs-lookup"><span data-stu-id="6e620-109">Windows HoloLens 2 and operating system architecture offers these innovative security features:</span></span>

  * <span data-ttu-id="6e620-110">**Oddělení** a izolace stavu: Tato nová architektura chrání důležité části operačního systému HoloLens 2 před změnou – například ty, které jsou nutné pro spuštění základního operačního systému do důvěryhodného stavu.</span><span class="sxs-lookup"><span data-stu-id="6e620-110">**State separation and isolation**:  This new architecture protects critical portions of the HoloLens 2 operating system from change - such as those required for the core operating system to boot into a trusted state.</span></span> <span data-ttu-id="6e620-111">Technologie izolace se používá k omezení nedůvěryhodných aplikací v oblasti sandboxu, aby se zajistilo, že nemohou ovlivnit zabezpečení systému.</span><span class="sxs-lookup"><span data-stu-id="6e620-111">Isolation technology is used to confine untrusted apps in a sandbox area, ensuring that they cannot impact the system security.</span></span> <span data-ttu-id="6e620-112">Celý operační systém je segmentovaný do zabezpečených sekcí, z nichž každá je chráněná kombinací různých technologií zabezpečení.</span><span class="sxs-lookup"><span data-stu-id="6e620-112">The entire operating system is segmented into secure sections, with each section shielded by a combination of different security technologies.</span></span>
  
  * <span data-ttu-id="6e620-113">**Ochrana dat:** Pokud dojde ke ztrátě nebo odcizení zařízení uživatele, Zabrání HoloLens 2 neoprávněným aplikacím ve čtení citlivých informací tím, že spoléhá na šifrování dat nástrojem BitLocker.</span><span class="sxs-lookup"><span data-stu-id="6e620-113">**Data Protection**: If a user’s device is lost or stolen, HoloLens 2 prevents unauthorized applications from reading sensitive information by relying on BitLocker encryption of data.</span></span> 
  
  * <span data-ttu-id="6e620-114">**Operační systém bez hesla:** Starší operační systémy založené na heslech mohly nechtěně vystavit uživatele hrozbám útokům phishing a často byly zodpovědné za ohrožené účty.</span><span class="sxs-lookup"><span data-stu-id="6e620-114">**Password-less operating system**:  Older, password-based operating systems could inadvertently expose users to phishing threats and were often responsible for compromised accounts.</span></span> <span data-ttu-id="6e620-115">Windows Holographic for Business eliminuje použití hesel pro přihlášení k MSA a Azure AD a posiluje ochranu identit uživatelů pomocí Windows Hello™ a FIDO2.</span><span class="sxs-lookup"><span data-stu-id="6e620-115">Windows Holographic for Business eliminates the use of passwords for MSA and Azure AD sign-in and strengthens user-identity protection with Windows Hello™ and FIDO2 sign-in.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="6e620-116">Pokud chcete mít podporu FIDO2, musí být zařízení v buildu 19041 nebo novějším.</span><span class="sxs-lookup"><span data-stu-id="6e620-116">To have FIDO2 support, the device must be on Build 19041 or higher.</span></span> 

  * <span data-ttu-id="6e620-117">**Zabezpečení sítě:** HoloLens 2 nabízí uživatelům vyšší zabezpečení sítě prostřednictvím vylepšených protokolů a výchozích nastavení.</span><span class="sxs-lookup"><span data-stu-id="6e620-117">**Network security**: HoloLens 2 offers the user increased network security via improved protocols and default settings.</span></span>
