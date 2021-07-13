---
title: správa vlastních aplikací pro HoloLens 2
description: naučte se instalovat, odinstalaci a načítat vlastní holografické aplikace na zařízeních HoloLens 2 pomocí portálu pro zařízení a Visual Studio.
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
ms.openlocfilehash: d2280a794455090c61a7bf30bc5dc5b8faf5adbe
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636397"
---
# <a name="manage-custom-apps-for-hololens-2"></a><span data-ttu-id="fced8-104">správa vlastních aplikací pro HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="fced8-104">Manage custom apps for HoloLens 2</span></span>

<span data-ttu-id="fced8-105">HoloLens podporuje mnoho stávajících aplikací z Microsoft Store a také nové aplikace sestavené speciálně pro HoloLens.</span><span class="sxs-lookup"><span data-stu-id="fced8-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> 

<span data-ttu-id="fced8-106">Další informace o aplikacích pro Store najdete v tématu [Správa aplikací ve Storu](holographic-store-apps.md).</span><span class="sxs-lookup"><span data-stu-id="fced8-106">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fced8-107">Pro podniková nasazení nedoporučujeme povolit vývojářský režim, který obě tyto metody používají.</span><span class="sxs-lookup"><span data-stu-id="fced8-107">For enterprise deployments, we don't recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="fced8-108">Pokud vás zajímá metoda bezpečného nasazení aplikace, přečtěte si prosím naši [správu aplikací: Přehled](app-deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fced8-108">If you're interested in a secure app deployment method, please review our [App Management: Overview](app-deploy-overview.md).</span></span>

<span data-ttu-id="fced8-109">pokud hledáte metodu pro vývojáře instalace aplikace pro zařízení HoloLens 2, přečtěte si:</span><span class="sxs-lookup"><span data-stu-id="fced8-109">If you're looking for either developer method of app installation for HoloLens 2 devices, refer to:</span></span>

- [<span data-ttu-id="fced8-110">Portál zařízení: instalace aplikace</span><span class="sxs-lookup"><span data-stu-id="fced8-110">Device Portal: Installing an App</span></span>](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
- [<span data-ttu-id="fced8-111">nasazení a ladění aplikací pomocí Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fced8-111">Using Visual Studio to deploy and debug Apps</span></span>](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

<span data-ttu-id="fced8-112">pokud chcete nasadit vlastní aplikace na HoloLens (1. generace), podívejte se na naše [průvodce](holographic-custom-apps.md) .</span><span class="sxs-lookup"><span data-stu-id="fced8-112">See our [guide](holographic-custom-apps.md) if you'd like to deploy custom apps on HoloLens (1st gen).</span></span>
