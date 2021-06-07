---
title: Správa vlastních aplikací pro HoloLens 2
description: Naučte se instalovat, odinstalovat a načítat vlastní holografické aplikace na zařízeních HoloLens 2 pomocí portálu zařízení a sady Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 01/21/2021
manager: yannisle
keywords: HoloLens, HoloLens 2, bokem, na straně zatížení, zkušební zatížení, úložiště, UWP, aplikace, instalace
ms.prod: hololens
ms.sitesec: library
author: joyjaz
ms.author: v-jjaswinski
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens 2
ms.openlocfilehash: e3ae180697c889a426108992ba345dc23b96505c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377583"
---
# <a name="manage-custom-apps-for-hololens-2"></a><span data-ttu-id="4d1bc-104">Správa vlastních aplikací pro HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="4d1bc-104">Manage custom apps for HoloLens 2</span></span>

<span data-ttu-id="4d1bc-105">HoloLens podporuje mnoho stávajících aplikací z Microsoft Store a také nové aplikace sestavené speciálně pro HoloLens.</span><span class="sxs-lookup"><span data-stu-id="4d1bc-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> 

<span data-ttu-id="4d1bc-106">Další informace o aplikacích pro Store najdete v tématu [Správa aplikací ve Storu](holographic-store-apps.md).</span><span class="sxs-lookup"><span data-stu-id="4d1bc-106">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d1bc-107">Pro podniková nasazení nedoporučujeme povolit vývojářský režim, který obě tyto metody používají.</span><span class="sxs-lookup"><span data-stu-id="4d1bc-107">For enterprise deployments, we don't recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="4d1bc-108">Pokud vás zajímá metoda bezpečného nasazení aplikace, přečtěte si prosím naši [správu aplikací: Přehled](app-deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4d1bc-108">If you're interested in a secure app deployment method, please review our [App Management: Overview](app-deploy-overview.md).</span></span>

<span data-ttu-id="4d1bc-109">Pokud hledáte metodu pro vývojáře instalace aplikace pro zařízení HoloLens 2, přečtěte si:</span><span class="sxs-lookup"><span data-stu-id="4d1bc-109">If you're looking for either developer method of app installation for HoloLens 2 devices, refer to:</span></span>
- [<span data-ttu-id="4d1bc-110">Portál zařízení: instalace aplikace</span><span class="sxs-lookup"><span data-stu-id="4d1bc-110">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
- [<span data-ttu-id="4d1bc-111">Nasazení a ladění aplikací pomocí sady Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4d1bc-111">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

<span data-ttu-id="4d1bc-112">Pokud byste chtěli nasadit vlastní aplikace na HoloLens (1. generace), podívejte se na naše [Průvodce](holographic-custom-apps.md) .</span><span class="sxs-lookup"><span data-stu-id="4d1bc-112">See our [guide](holographic-custom-apps.md) if you'd like to deploy custom apps on HoloLens (1st gen).</span></span>