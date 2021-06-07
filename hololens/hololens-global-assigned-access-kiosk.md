---
title: Globální přiřazený přístup
description: Začínáme s naším průvodcem používáním OMA-URI pro terminály s globálním přiřazeným přístupem pomocí Intune a návrháře konfigurace Pro Windows.
author: evmill
ms.author: v-evmill
ms.date: 9/21/2020
ms.topic: article
keywords: hololens, hololens 2, přiřazený přístup, kiosk
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b86d88c7487043c6fcb057f03f353a57e44ef781
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379274"
---
# <a name="global-assigned-access--kiosk"></a><span data-ttu-id="5220f-104">Globální přiřazený přístup – Beziosk</span><span class="sxs-lookup"><span data-stu-id="5220f-104">Global Assigned Access – Kiosk</span></span>

<span data-ttu-id="5220f-105">Tato funkce konfiguruje zařízení HoloLens 2 pro režim veřejného terminálů s více aplikacemi, který je použitelný na úrovni systému, nemá žádné spřažení s žádnou identitou v systému a vztahuje se na všechny uživatele, kteří se k zařízení přihlásí.</span><span class="sxs-lookup"><span data-stu-id="5220f-105">This feature configures HoloLens 2 device for multiple app kiosk mode, which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span>

> [!NOTE]
> <span data-ttu-id="5220f-106">Tato funkce je aktuálně dostupná pouze v Windows Insider sestaveních.</span><span class="sxs-lookup"><span data-stu-id="5220f-106">This feature is currently only available in Windows Insider builds.</span></span> <span data-ttu-id="5220f-107">Pokud chcete tuto funkci vyzkoušet dříve, než je všeobecně dostupná v verzích HoloLens, přečtěte si další informace [o Windows Insider](hololens-insider.md) sestavení.</span><span class="sxs-lookup"><span data-stu-id="5220f-107">If you would like to try this feature before it is generally available in HoloLens releases please read more about [Windows Insider](hololens-insider.md) builds.</span></span>

## <a name="how-to-use-global-assigned-access-in-intune"></a><span data-ttu-id="5220f-108">Jak používat globální přiřazený přístup v Intune?</span><span class="sxs-lookup"><span data-stu-id="5220f-108">How to use Global Assigned Access in Intune?</span></span>

> [!NOTE]
> <span data-ttu-id="5220f-109">Mějte na paměti oblasti označené <!-.</span><span class="sxs-lookup"><span data-stu-id="5220f-109">Please be aware of the areas marked with "<!-".</span></span> <span data-ttu-id="5220f-110">Tyto oblasti budou vyžadovat, abyste na základě svých preferencí úpravy úpravy úpravy.</span><span class="sxs-lookup"><span data-stu-id="5220f-110">These areas will require you to make modifications based on your preferences.</span></span>

1. <span data-ttu-id="5220f-111">Následujícím způsobem vytvořte vlastní konfigurační profil zařízení OMA URI a použijte ho pro skupinu zařízení HoloLens:</span><span class="sxs-lookup"><span data-stu-id="5220f-111">Create a custom OMA URI device configuration profile as follows and apply it to HoloLens device group:</span></span>

    <span data-ttu-id="5220f-112">Hodnota identifikátoru URI: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span><span class="sxs-lookup"><span data-stu-id="5220f-112">URI value: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="5220f-113">![OMA-URI pro globálně přiřazený přístup v Intune](images/global-assigned-access-omauri.png)</span><span class="sxs-lookup"><span data-stu-id="5220f-113">![Global Assigned Access OMA-URI in Intune](images/global-assigned-access-omauri.png)</span></span>

2. <span data-ttu-id="5220f-114">Jako hodnotu aktualizujte a vložte následující obsah:</span><span class="sxs-lookup"><span data-stu-id="5220f-114">For value, update and paste following content:</span></span>

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a><span data-ttu-id="5220f-115">Jak používat globální přiřazený přístup v nástroji Windows Configuration Designer?</span><span class="sxs-lookup"><span data-stu-id="5220f-115">How to use Global Assigned Access in Windows Configuration Designer?</span></span>

1. <span data-ttu-id="5220f-116">Aktualizujte a uložte objekt blob XML uvedený výše jako soubor XML.</span><span class="sxs-lookup"><span data-stu-id="5220f-116">Update and save XML blob mentioned above as XML file.</span></span> 

2. <span data-ttu-id="5220f-117">Postupujte podle kroků v části Použití zřizovacího balíčku [k](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)nastavení veřejného terminálu s jednou nebo více aplikacemi, konkrétně v části "Prov".</span><span class="sxs-lookup"><span data-stu-id="5220f-117">Follow the steps in [Use a provisioning package to set up a single-app or multi-app kiosk](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk), specifically the section "Prov.</span></span> <span data-ttu-id="5220f-118">package, krok 2 – přidejte soubor XML konfigurace veřejného terminálů do zřizovacího balíčku a odkazujte na soubor XML, který jste uložili v předchozím kroku.</span><span class="sxs-lookup"><span data-stu-id="5220f-118">package, step 2 – Add the kiosk configuration XML file to a provisioning package" and refer to the XML file that was saved in the previous step.</span></span>

## <a name="can-i-create-a-configuration-where-global-applies-to-everyone-and-separate-configuration-applies-to-1-azure-ad-account-or-azure-ad-group"></a><span data-ttu-id="5220f-119">Můžu vytvořit konfiguraci, ve které globální platí pro všechny a samostatná konfigurace se vztahuje na 1 účet Azure AD nebo skupinu Azure AD?</span><span class="sxs-lookup"><span data-stu-id="5220f-119">Can I create a configuration where global applies to everyone and separate configuration applies to 1 Azure AD account or Azure AD group?</span></span> 

<span data-ttu-id="5220f-120">Ano, podívejte se na příklad objektu blob XML níže.</span><span class="sxs-lookup"><span data-stu-id="5220f-120">Yes, refer to the example XML blob below.</span></span> <span data-ttu-id="5220f-121">Profil globálního přiřazeného přístupu se na HoloLens použije, když se pro přihlášeného uživatele nenalezne konkrétní profil, takže se jedná o výchozí konfiguraci režimu veřejného terminálů pro přihlášeného uživatele.</span><span class="sxs-lookup"><span data-stu-id="5220f-121">Global Assigned Access profile is applied on HoloLens when a specific one for the signed in user is not found, so it is default kiosk mode configuration for signed-in user.</span></span>
<span data-ttu-id="5220f-122">Tady je příklad použití objektu blob XML:</span><span class="sxs-lookup"><span data-stu-id="5220f-122">Here is an example of XML blob to be used:</span></span>

> [!NOTE]
> <span data-ttu-id="5220f-123">Mějte na paměti zvýrazněné oblasti označené `<!-` .</span><span class="sxs-lookup"><span data-stu-id="5220f-123">Please be aware of the highlighted areas marked with `<!-`.</span></span> <span data-ttu-id="5220f-124">Tyto oblasti budou vyžadovat, abyste na základě svých preferencí úpravy úpravy úpravy.</span><span class="sxs-lookup"><span data-stu-id="5220f-124">These areas will require you to make modifications based on your preferences.</span></span>

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <a name="excluding-deviceowners-from-global-assigned-access-profile"></a><span data-ttu-id="5220f-125">Vyloučení vlastníků zařízení z globálního přiřazeného přístupového profilu</span><span class="sxs-lookup"><span data-stu-id="5220f-125">Excluding DeviceOwners from Global Assigned Access Profile</span></span>

<span data-ttu-id="5220f-126">Tato funkce umožňuje vyloučit uživatele, který je na HoloLens považován za vlastníka zařízení, z globálního přiřazeného přístupu.[](security-adminless-os.md)</span><span class="sxs-lookup"><span data-stu-id="5220f-126">This feature allows a user who is considered “[Device owner](security-adminless-os.md)" on HoloLens to be excluded from Global Assigned Access.</span></span> <span data-ttu-id="5220f-127">Pokud chcete tuto funkci využít, v objektu blob XML pro konfiguraci veřejného terminálů s více aplikacemi se ujistěte, že jsou přidané zvýrazněné řádky:</span><span class="sxs-lookup"><span data-stu-id="5220f-127">In order to take advantage of this feature, in the XML blob for multiple-app kiosk configuration, ensure highlighted lines are added:</span></span>

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <a name="additional-global-assigned-access-examples"></a><span data-ttu-id="5220f-128">Další příklady globálního přiřazeného přístupu</span><span class="sxs-lookup"><span data-stu-id="5220f-128">Additional Global Assigned Access Examples</span></span>

<span data-ttu-id="5220f-129">Toto je příklad veřejného terminálu s globálním přiřazeným přístupem, který bude mít, když se přihlásí nějaký uživatel, pomocí aplikace Nastavení, aplikace nastavení a Centrum Feedback a Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="5220f-129">This is an example Global Assigned Access kiosk that when any user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

<span data-ttu-id="5220f-130">Tento příklad je veřejného terminálu s globálním přiřazeným přístupem, který vyloučí vlastníka zařízení, když se přihlásí jakýkoli jiný uživatel Azure AD, bude mít kiosk s více aplikacemi pomocí aplikace nastavení, Centrum Feedback a Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="5220f-130">This example is a Global Assigned Access kiosk that excludes the device owner, when any other Azure AD user signs in they will have a multi-app kiosk with the Settings App, Feedback Hub, and Microsoft Edge.</span></span> <span data-ttu-id="5220f-131">Tento bezobrazovk zahrnuje také sekundární konfiguraci veřejného terminálů pro účet Návštěvník, ke kterému se může na zamykací obrazovce zaregistrovat kdokoli.</span><span class="sxs-lookup"><span data-stu-id="5220f-131">This kiosk also includes a secondary kiosk configuration for a Visitor account, which may be signed into by anyone on the lock screen.</span></span> <span data-ttu-id="5220f-132">Když se uživatel přihlásí k účtu Návštěvník, bude mít kiosk s více aplikacemi, který má jenom Centrum Feedback aplikace.</span><span class="sxs-lookup"><span data-stu-id="5220f-132">When a user signs into the Visitor account they will have a multi-app kiosk that only has the Feedback Hub app.</span></span>

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
