---
title: Sdílení HoloLens s více lidmi
description: Můžete nakonfigurovat HoloLens pro sdílení pomocí více účtů Azure Active Directory nebo více uživatelů, kteří používají jeden účet.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 39de72bb704ff500b0262f2268d003a08d520eb2
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377646"
---
# <a name="share-your-hololens-with-multiple-people"></a><span data-ttu-id="6328e-103">Sdílení HoloLens s více lidmi</span><span class="sxs-lookup"><span data-stu-id="6328e-103">Share your HoloLens with multiple people</span></span>

<span data-ttu-id="6328e-104">Je běžné sdílet jeden HoloLens s mnoha lidmi nebo mít mnoho lidí, kteří sdílejí sadu zařízení HoloLens.</span><span class="sxs-lookup"><span data-stu-id="6328e-104">It's common to share one HoloLens with many people or to have many people share a set of HoloLens devices.</span></span>  <span data-ttu-id="6328e-105">Tento článek popisuje různé způsoby, kterými můžete sdílet zařízení.</span><span class="sxs-lookup"><span data-stu-id="6328e-105">This article describes the different ways in which you can share a device.</span></span>

## <a name="share-with-multiple-people-each-using-their-own-account"></a><span data-ttu-id="6328e-106">Sdílení s více lidmi, z nichž každý používá vlastní účet</span><span class="sxs-lookup"><span data-stu-id="6328e-106">Share with multiple people, each using their own account</span></span>

<span data-ttu-id="6328e-107">**Předpoklad**: na zařízení HoloLens musí běžet Windows 10 verze 1803 nebo novější.</span><span class="sxs-lookup"><span data-stu-id="6328e-107">**Prerequisite**: The HoloLens device must be running Windows 10, version 1803 or later.</span></span>  <span data-ttu-id="6328e-108">HoloLens (1. generace) je také potřeba [upgradovat na Windows holografick pro firmy](hololens-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="6328e-108">HoloLens (1st gen) also need to be [upgraded to Windows Holographic for Business](hololens-upgrade-enterprise.md).</span></span>

<span data-ttu-id="6328e-109">Když používají vlastní účty Azure Active Directory (Azure AD), může každý z nich na zařízení uchovávat vlastní uživatelská nastavení a uživatelská data.</span><span class="sxs-lookup"><span data-stu-id="6328e-109">When they use their own Azure Active Directory (Azure AD) accounts, multiple users can each keep their own user settings and user data on the device.</span></span>

<span data-ttu-id="6328e-110">Aby bylo zajištěno, že více lidí bude moci na HoloLens používat vlastní účty, postupujte podle těchto kroků a proveďte jejich konfiguraci:</span><span class="sxs-lookup"><span data-stu-id="6328e-110">To make sure that multiple people can use their own accounts on your HoloLens, follow these steps to configure it:</span></span>

1. <span data-ttu-id="6328e-111">Ujistěte se, že na zařízení běží Windows 10 verze 1803 nebo novější.</span><span class="sxs-lookup"><span data-stu-id="6328e-111">Make sure the the device is running Windows 10, version 1803 or later.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="6328e-112">Pokud používáte zařízení HoloLens (1. gen), [upgradujte zařízení na Windows holografick pro firmy](hololens1-upgrade-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="6328e-112">If you are using a HoloLens (1st gen) device, [upgrade the device to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>
1. <span data-ttu-id="6328e-113">Když zařízení nastavíte, vyberte možnost **Moje práce nebo škola, kterou vlastní** , a přihlaste se pomocí účtu Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6328e-113">When you set up the device, select **My work or school owns it** and sign in by using an Azure AD account.</span></span>
1. <span data-ttu-id="6328e-114">Po dokončení instalace se ujistěte, že nastavení účtu (**Nastavení**  >  **účty**) obsahuje **Další uživatele**.</span><span class="sxs-lookup"><span data-stu-id="6328e-114">After you finish setup, make sure that the account settings (**Settings** > **Accounts**) includes **Other users**.</span></span>

<span data-ttu-id="6328e-115">Chcete-li použít HoloLens, každý uživatel provede následující kroky:</span><span class="sxs-lookup"><span data-stu-id="6328e-115">To use HoloLens, each user follows these steps:</span></span>

1. <span data-ttu-id="6328e-116">Pokud zařízení používal jiný uživatel, proveďte jednu z následujících akcí:</span><span class="sxs-lookup"><span data-stu-id="6328e-116">If another user has been using the device, do one of the following:</span></span>
   - <span data-ttu-id="6328e-117">Pokud chcete přejít na úsporný režim, stiskněte tlačítko napájení a potom se stisknutím tlačítka napájení vraťte na zamykací obrazovku.</span><span class="sxs-lookup"><span data-stu-id="6328e-117">Press the power button once to go to standby, and then press the power button again to return to the lock screen</span></span>
   - <span data-ttu-id="6328e-118">Uživatelé HoloLens 2 mohou vybrat dlaždici uživatele z nabídky Start pro odhlášení aktuálního uživatele.</span><span class="sxs-lookup"><span data-stu-id="6328e-118">HoloLens 2 users may select the user tile from the Start menu to sign out the current user.</span></span>

1. <span data-ttu-id="6328e-119">Přihlaste se k zařízení pomocí svých přihlašovacích údajů k účtu Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6328e-119">Use your Azure AD account credentials to sign in to the device.</span></span>  
    <span data-ttu-id="6328e-120">Pokud zařízení používáte poprvé, budete muset použít [kalibraci](hololens-calibration.md) HoloLens na vaše vlastní oči.</span><span class="sxs-lookup"><span data-stu-id="6328e-120">If this is the first time that you have used the device, you have to [calibrate](hololens-calibration.md) HoloLens to your own eyes.</span></span>

<span data-ttu-id="6328e-121">Pokud chcete zobrazit seznam uživatelů zařízení nebo odebrat uživatele ze zařízení, přejděte na **Nastavení**  >  **účty**  >  **ostatní uživatelé**.</span><span class="sxs-lookup"><span data-stu-id="6328e-121">To see a list of the device users or to remove a user from the device, go to **Settings** > **Accounts** > **Other users**.</span></span>

## <a name="share-with-multiple-people-all-using-the-same-account"></a><span data-ttu-id="6328e-122">Sdílet s více lidmi a používat stejný účet</span><span class="sxs-lookup"><span data-stu-id="6328e-122">Share with multiple people, all using the same account</span></span>

<span data-ttu-id="6328e-123">Zařízení HoloLens může sdílet několik uživatelů i při použití jediného uživatelského účtu.</span><span class="sxs-lookup"><span data-stu-id="6328e-123">Multiple users can also share a HoloLens device while using a single user account.</span></span>

<span data-ttu-id="6328e-124">Když **na HoloLens 2** nový uživatel umístí zařízení do svého hlavního umístění (při současném zachování stejného účtu), zařízení vyzve nového uživatele k rychlému kalibraci a přizpůsobení prostředí pro zobrazení.</span><span class="sxs-lookup"><span data-stu-id="6328e-124">**On HoloLens 2**, when a new user puts the device on their head for the first time (while keeping the same account signed in), the device prompts the new user to quickly calibrate and personalize the viewing experience.</span></span> <span data-ttu-id="6328e-125">Zařízení může ukládat informace o kalibraci, takže v budoucnu může zařízení automaticky optimalizovat kvalitu a pohodlí možností zobrazení jednotlivých uživatelů.</span><span class="sxs-lookup"><span data-stu-id="6328e-125">The device can store the calibration information so that in the future, the device can automatically optimize the quality and comfort of each user's viewing experience.</span></span> <span data-ttu-id="6328e-126">Uživatelé nepotřebují zařízení znovu kalibrovat.</span><span class="sxs-lookup"><span data-stu-id="6328e-126">The users do not need to calibrate the device again.</span></span>

<span data-ttu-id="6328e-127">**V případě HoloLens (1. generace)** budou muset uživatelé sdílející účet požádat o rekalibraci v aplikaci nastavení.</span><span class="sxs-lookup"><span data-stu-id="6328e-127">**On HoloLens (1st gen)** users sharing an account will need to ask to recalibrate in the Settings app.</span></span>  <span data-ttu-id="6328e-128">Přečtěte si další informace o [kalibraci](hololens-calibration.md).</span><span class="sxs-lookup"><span data-stu-id="6328e-128">Read more about [calibration](hololens-calibration.md).</span></span>
