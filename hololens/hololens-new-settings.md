---
title: Představujeme novou aplikaci nastavení
description: Další informace o nové aplikaci nastavení
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, nastavení, výběr aplikace, svazek
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: bf1a2080c15346843b9ea9b2d0dc93154e185107
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379338"
---
# <a name="new-settings-app"></a><span data-ttu-id="f6c5a-104">Nová aplikace nastavení</span><span class="sxs-lookup"><span data-stu-id="f6c5a-104">New Settings app</span></span>

<span data-ttu-id="f6c5a-105">S [Windows holografickou verzí 21H1](hololens-release-notes.md#windows-holographic-version-21h1)zavádíme novou verzi aplikace nastavení.</span><span class="sxs-lookup"><span data-stu-id="f6c5a-105">With [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), we're introducing a new version of the Settings app.</span></span> <span data-ttu-id="f6c5a-106">Nová aplikace nastavení zahrnuje nové funkce a rozšířené nastavení pro HoloLens 2 v následujících oblastech: zvuk, Power & režim spánku, síť & Internetu, aplikace, účty, usnadnění přístupu a další.</span><span class="sxs-lookup"><span data-stu-id="f6c5a-106">The new Settings app includes new features and expanded settings for HoloLens 2 in the following areas: Sound, Power & sleep, Network & Internet, Apps, Accounts, Ease of Access, and more.</span></span>

> [!NOTE]
> <span data-ttu-id="f6c5a-107">Vzhledem k tomu, že je nová aplikace nastavení odlišná od aplikace se staršími nastaveními, všechna nastavení, která jste předtím umístili do prostředí, se po aktualizaci odeberou.</span><span class="sxs-lookup"><span data-stu-id="f6c5a-107">Because the new Settings app is distinct from the legacy Settings app, any Settings windows you previously placed around your environment will be removed upon update.</span></span>

![Domovská stránka nové aplikace nastavení](images/new-settings-app.png)

<span data-ttu-id="f6c5a-109">**Nové funkce a nastavení**</span><span class="sxs-lookup"><span data-stu-id="f6c5a-109">**New features and settings**</span></span>
- <span data-ttu-id="f6c5a-110">Hledání nastavení: Vyhledejte nastavení z domovské stránky nastavení pomocí klíčových slov nebo názvu nastavení.</span><span class="sxs-lookup"><span data-stu-id="f6c5a-110">Settings search: search for settings from the Settings homepage using keywords or the setting's name.</span></span>
- <span data-ttu-id="f6c5a-111">Systémová >ová [kalibrace barev](hololens2-display.md#how-to-use-display-color-calibration)</span><span class="sxs-lookup"><span data-stu-id="f6c5a-111">System > [Color calibration](hololens2-display.md#how-to-use-display-color-calibration)</span></span>
    - <span data-ttu-id="f6c5a-112">Vyberte alternativní barevný profil pro displej HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="f6c5a-112">Select an alternative color profile for your HoloLens 2 display.</span></span>
- <span data-ttu-id="f6c5a-113">Zvuk > systému:</span><span class="sxs-lookup"><span data-stu-id="f6c5a-113">System > Sound:</span></span>
  - <span data-ttu-id="f6c5a-114">Vstupní a výstupní zvuková zařízení: nezávisle vyberte vstupní a výstupní zvuková zařízení (například poslech zvuku přes sluchátka Bluetooth nebo použití mikrofonu USB-C pro zvukový vstup).</span><span class="sxs-lookup"><span data-stu-id="f6c5a-114">Input and output audio devices: independently choose your input and output audio devices (for example, listen to audio via Bluetooth headphones or use a USB-C microphone for audio input).</span></span>
    > [!NOTE]
    > <span data-ttu-id="f6c5a-115">Technologie HoloLens 2 nepodporuje mikrofony Bluetooth.</span><span class="sxs-lookup"><span data-stu-id="f6c5a-115">Bluetooth microphones are not supported by HoloLens 2.</span></span>
  - <span data-ttu-id="f6c5a-116">Svazek aplikace: nezávisle upravte hlasitost každé aplikace.</span><span class="sxs-lookup"><span data-stu-id="f6c5a-116">App volume: independently adjust the volume of each app.</span></span> <span data-ttu-id="f6c5a-117">Zobrazit [Řízení hlasitosti jednotlivých aplikací](holographic-home.md#per-app-volume-control).</span><span class="sxs-lookup"><span data-stu-id="f6c5a-117">See [per app volume control](holographic-home.md#per-app-volume-control).</span></span>
- <span data-ttu-id="f6c5a-118">Systém > napájení & režimu spánku: vyberte, kdy se má zařízení po určité době nečinnosti přejít do režimu spánku.</span><span class="sxs-lookup"><span data-stu-id="f6c5a-118">System > Power & sleep: choose when the device should go to sleep after a period of inactivity.</span></span>
- <span data-ttu-id="f6c5a-119">Systémová > baterie: ručně povolit režim spořiče baterie nebo nastavit prahovou hodnotu baterie, při které se režim spořiče baterie automaticky zapne.</span><span class="sxs-lookup"><span data-stu-id="f6c5a-119">System > Battery: manually enable battery saver mode or set a battery threshold at which point battery saver mode turns on automatically.</span></span>
- <span data-ttu-id="f6c5a-120">Zařízení > USB: ve výchozím nastavení můžete připojení USB zakázat.</span><span class="sxs-lookup"><span data-stu-id="f6c5a-120">Devices > USB: you can disable USB connections by default.</span></span>
- <span data-ttu-id="f6c5a-121">& sítě Internet:</span><span class="sxs-lookup"><span data-stu-id="f6c5a-121">Network & Internet:</span></span>
  - <span data-ttu-id="f6c5a-122">Adaptéry USB-C Ethernet se nyní zobrazí v síti & Internetu.</span><span class="sxs-lookup"><span data-stu-id="f6c5a-122">USB-C Ethernet adapters will now appear in Network & Internet.</span></span>
  - <span data-ttu-id="f6c5a-123">K dispozici jsou nyní nastavení adaptéru USB-C Ethernet, včetně jeho IP adresy.</span><span class="sxs-lookup"><span data-stu-id="f6c5a-123">USB-C Ethernet adapter settings are now available, including its IP address.</span></span>
  - <span data-ttu-id="f6c5a-124">Nyní můžete zapnout režim v letadle na HoloLens 2.</span><span class="sxs-lookup"><span data-stu-id="f6c5a-124">You can now enable airplane mode on HoloLens 2.</span></span>
- <span data-ttu-id="f6c5a-125">Aplikace: můžete obnovit výchozí aplikace používané pro typy souborů a odkazů.</span><span class="sxs-lookup"><span data-stu-id="f6c5a-125">Apps: you can reset the default apps used for file and link types.</span></span> <span data-ttu-id="f6c5a-126">Další informace najdete v tématu věnovaném [výchozím ovládacím prvkům aplikace](holographic-home.md#default-app-picker).</span><span class="sxs-lookup"><span data-stu-id="f6c5a-126">For more information see [Default app picker](holographic-home.md#default-app-picker).</span></span>
- <span data-ttu-id="f6c5a-127">Účty > jiných uživatelích: vlastníci zařízení můžou přidávat uživatele, upgradovat standardní uživatele na vlastníky zařízení, předowngradovat vlastníky zařízení na standardní uživatele a odebírat uživatele.</span><span class="sxs-lookup"><span data-stu-id="f6c5a-127">Accounts > Other users: device owners can add users, upgrade standard users to device owners, downgrade device owners to standard users, and remove users.</span></span>
- <span data-ttu-id="f6c5a-128">Usnadnění přístupu: Změna velikosti textu a některých vizuálních efektů.</span><span class="sxs-lookup"><span data-stu-id="f6c5a-128">Ease of Access: change text size and some visual effects.</span></span>

<span data-ttu-id="f6c5a-129">**Známé problémy**</span><span class="sxs-lookup"><span data-stu-id="f6c5a-129">**Known issues**</span></span>
- <span data-ttu-id="f6c5a-130">Okna dříve umístěná nastavení se odeberou (viz poznámku výše).</span><span class="sxs-lookup"><span data-stu-id="f6c5a-130">Previously placed Settings windows will be removed (see note above).</span></span>
- <span data-ttu-id="f6c5a-131">Zařízení už nemůžete přejmenovat pomocí aplikace nastavení.</span><span class="sxs-lookup"><span data-stu-id="f6c5a-131">You can no longer rename your device with the Settings app.</span></span> <span data-ttu-id="f6c5a-132">Správci IT můžou zařízení přejmenovat pomocí šablony [Windows autopilot pro název zařízení HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) nebo uzlu MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) EXT/Microsoft/DNSComputerName.</span><span class="sxs-lookup"><span data-stu-id="f6c5a-132">IT admins can rename devices by using the [Windows Autopilot for HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) device name template or the MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName node.</span></span>
- <span data-ttu-id="f6c5a-133">Na stránce Ethernet se vždy zobrazuje virtuální síť Ethernet (UsbNcm).</span><span class="sxs-lookup"><span data-stu-id="f6c5a-133">The Ethernet page shows a virtual Ethernet device ("UsbNcm") at all times.</span></span>
- <span data-ttu-id="f6c5a-134">Využití baterie pro nové Microsoft Edge nemusí být přesné, vzhledem k jeho povaze jako desktopová aplikace Win32 podporovaná vrstvou adaptéru UWP (zatím se nepředpokládá žádná oprava).</span><span class="sxs-lookup"><span data-stu-id="f6c5a-134">Battery usage for the new Microsoft Edge may not be accurate, due to its nature as a Win32 desktop application supported by a UWP adapter layer (no fix anticipated soon).</span></span>

