---
title: Nejčastější dotazy k zařízením HoloLens a hologramům
description: Máte rychlý dotaz na HoloLens nebo interakci s hologramy?  Tento článek poskytuje rychlou odpověď a další prostředky.
keywords: HoloLens, nejčastější dotazy, známý problém, help
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 02/27/2020
ms.reviewer: ''
ms.custom:
- CI 114606
- CSSTroubleshooting
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ae44ae1d9a2e088a1ef746f4e929e8fae73880bf
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924022"
---
# <a name="holograms-and-interactions-troubleshooting"></a><span data-ttu-id="144dd-105">Řešení potíží s hologramy a interakcemi</span><span class="sxs-lookup"><span data-stu-id="144dd-105">Holograms and interactions troubleshooting</span></span>

<span data-ttu-id="144dd-106">Tento článek řeší problémy při umísťování hologramů, práci s prostory a hlášení problémů s hologramy.</span><span class="sxs-lookup"><span data-stu-id="144dd-106">This article troubleshoots issues with placing holograms, working with spaces, and reporting issues with holograms.</span></span>

<span data-ttu-id="144dd-107">Kdykoli máte problémy, ujistěte se, že:</span><span class="sxs-lookup"><span data-stu-id="144dd-107">Anytime that you have problems, make sure:</span></span>
- <span data-ttu-id="144dd-108">Zkuste [to znovu, abyste viděli, jestli](hololens-restart-recover.md) opravuje nějaké věci.</span><span class="sxs-lookup"><span data-stu-id="144dd-108">Try [restarting it](hololens-restart-recover.md) to see whether that fixes things.</span></span>
- <span data-ttu-id="144dd-109">Před řešením potíží se ujistěte, že se na HoloLens [účtuje](hololens2-charging.md) (účtuje se aspoň za hodinu).</span><span class="sxs-lookup"><span data-stu-id="144dd-109">Before troubleshooting, ensure the HoloLens is [charged up](hololens2-charging.md) (charged for at least an hour).</span></span> 


<span data-ttu-id="144dd-110">Pokud nám chcete poslat informace o problému, použijte prosím aplikaci Feedback.</span><span class="sxs-lookup"><span data-stu-id="144dd-110">Please use the Feedback app to send us information about the issue.</span></span> <span data-ttu-id="144dd-111">V [nabídce **Start**](holographic-home.md)najdete aplikaci Feedback.</span><span class="sxs-lookup"><span data-stu-id="144dd-111">You'll find the Feedback app on the [**Start** menu](holographic-home.md).</span></span> 

<span data-ttu-id="144dd-112">Tipy, jak nosit HoloLens, najdete v tématu [přizpůsobení přizpůsobení](hololens2-setup.md#adjust-fit).</span><span class="sxs-lookup"><span data-stu-id="144dd-112">For tips about how to wear your HoloLens, see [Adjust Fit](hololens2-setup.md#adjust-fit).</span></span>

<a id="list"></a>
- [<span data-ttu-id="144dd-113">Nelze vytvořit nové prostory</span><span class="sxs-lookup"><span data-stu-id="144dd-113">New spaces can't be created</span></span>](#new-spaces-cant-be-created)
- [<span data-ttu-id="144dd-114">Mezery se nedají identifikovat ani načíst.</span><span class="sxs-lookup"><span data-stu-id="144dd-114">Spaces can't be identified or loaded</span></span>](#spaces-cant-be-identified-or-loaded)
- [<span data-ttu-id="144dd-115">Návody odstranit všechny mezery?</span><span class="sxs-lookup"><span data-stu-id="144dd-115">How do I delete all spaces?</span></span>](#how-do-i-delete-all-spaces)
- [<span data-ttu-id="144dd-116">Hologramy nevypadají správně nebo se pohybují</span><span class="sxs-lookup"><span data-stu-id="144dd-116">Holograms don't look right or are moving around</span></span>](#holograms-dont-look-right-or-are-moving-around)
- [<span data-ttu-id="144dd-117">Zpráva hledání prostoru</span><span class="sxs-lookup"><span data-stu-id="144dd-117">"Finding your space" message</span></span>](#finding-your-space-message)
- [<span data-ttu-id="144dd-118">Očekávané hologramy nejsou zobrazeny v mém prostoru</span><span class="sxs-lookup"><span data-stu-id="144dd-118">Expected holograms aren't showing in my space</span></span>](#expected-holograms-arent-showing-in-my-space)
- [<span data-ttu-id="144dd-119">Nelze umístit hologramy nebo zobrazit dříve umístěné hologramy.</span><span class="sxs-lookup"><span data-stu-id="144dd-119">Can't place holograms or see previously placed holograms</span></span>](#cant-place-holograms-or-see-previously-placed-holograms)
- [<span data-ttu-id="144dd-120">Hologramy zmizí nebo jsou encasedy jinými hologramy nebo objekty.</span><span class="sxs-lookup"><span data-stu-id="144dd-120">Holograms disappear or are encased in other holograms or objects</span></span>](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [<span data-ttu-id="144dd-121">Hologramy se zobrazují na druhé straně zdi.</span><span class="sxs-lookup"><span data-stu-id="144dd-121">Holograms are appearing on the other side of a wall</span></span>](#holograms-are-appearing-on-the-other-side-of-a-wall)
- [<span data-ttu-id="144dd-122">Po umístění hologramu na zeď se zdá být plovoucí</span><span class="sxs-lookup"><span data-stu-id="144dd-122">After placing a hologram on a wall, it seems to float</span></span>](#after-placing-a-hologram-on-a-wall-it-seems-to-float)
- [<span data-ttu-id="144dd-123">Po přesunutí se aplikace zobrazují příliš blízko.</span><span class="sxs-lookup"><span data-stu-id="144dd-123">Apps appear too close after moving them</span></span>](#apps-appear-too-close-after-moving-them)
- [<span data-ttu-id="144dd-124">Hlášení problémů s nestabilními nebo nepřesnými hologramy</span><span class="sxs-lookup"><span data-stu-id="144dd-124">Reporting issues with unstable or inexact holograms</span></span>](#reporting-issues-with-unstable-or-inexact-holograms)

## <a name="new-spaces-cant-be-created"></a><span data-ttu-id="144dd-125">Nelze vytvořit nové prostory</span><span class="sxs-lookup"><span data-stu-id="144dd-125">New spaces can't be created</span></span>

<span data-ttu-id="144dd-126">Nejpravděpodobnějším problémem je, že dochází místo v úložišti.</span><span class="sxs-lookup"><span data-stu-id="144dd-126">The most likely problem is that you're running low on storage space.</span></span> <span data-ttu-id="144dd-127">[Uvolněte místo na disku](hololens-troubleshooting.md#low-disk-space-error) a pak to zkuste znovu.</span><span class="sxs-lookup"><span data-stu-id="144dd-127">[Free up some disk space](hololens-troubleshooting.md#low-disk-space-error) and then retry.</span></span>

[<span data-ttu-id="144dd-128">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="144dd-128">Back to list</span></span>](#list)

## <a name="spaces-cant-be-identified-or-loaded"></a><span data-ttu-id="144dd-129">Mezery se nedají identifikovat ani načíst.</span><span class="sxs-lookup"><span data-stu-id="144dd-129">Spaces can't be identified or loaded</span></span>

<span data-ttu-id="144dd-130">Pokud vaše HoloLens nemůže identifikovat a načíst prostor, který se nachází automaticky, Projděte si následující faktory:</span><span class="sxs-lookup"><span data-stu-id="144dd-130">If your HoloLens can't identify and load the space you're in automatically, check the following factors:</span></span>

- <span data-ttu-id="144dd-131">Ujistěte se, že jste připojení k Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="144dd-131">Make sure that you're connected to Wi-Fi</span></span>
- <span data-ttu-id="144dd-132">Ujistěte se, že je v místnosti dostatek světla.</span><span class="sxs-lookup"><span data-stu-id="144dd-132">Make sure that there's plenty of light in the room</span></span>
- <span data-ttu-id="144dd-133">Ujistěte se, že nedošlo k žádným podstatným změnám v okolí.</span><span class="sxs-lookup"><span data-stu-id="144dd-133">Make sure that there haven't been any major changes to the surroundings.</span></span>

<span data-ttu-id="144dd-134">Místo toho můžete ručně načíst mezeru nebo spravovat své prostory, a to tak, že kliknete na **Nastavení**  >  **systémové**  >  **prostory**.</span><span class="sxs-lookup"><span data-stu-id="144dd-134">You can also load a space manually or manage your spaces by going to **Settings** > **System** > **Spaces**.</span></span>

[<span data-ttu-id="144dd-135">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="144dd-135">Back to list</span></span>](#list)

## <a name="how-do-i-delete-all-spaces"></a><span data-ttu-id="144dd-136">Návody odstranit všechny mezery?</span><span class="sxs-lookup"><span data-stu-id="144dd-136">How do I delete all spaces?</span></span>

<span data-ttu-id="144dd-137">*Již brzy*</span><span class="sxs-lookup"><span data-stu-id="144dd-137">*Coming soon*</span></span>

[<span data-ttu-id="144dd-138">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="144dd-138">Back to list</span></span>](#list)

## <a name="holograms-dont-look-right-or-are-moving-around"></a><span data-ttu-id="144dd-139">Hologramy nevypadají správně nebo se pohybují</span><span class="sxs-lookup"><span data-stu-id="144dd-139">Holograms don't look right or are moving around</span></span>

<span data-ttu-id="144dd-140">Pokud vaše hologramy nevypadají správně (například se kolísáním nebo potřesem nebo se nad nimi zobrazují černé opravy), zkuste jednu z těchto oprav:</span><span class="sxs-lookup"><span data-stu-id="144dd-140">If your holograms don't look right (for example, they're jittery or shaky, or you see black patches on top of them), try one of these fixes:</span></span>

- <span data-ttu-id="144dd-141">[Vyčistěte hypervisor zařízení](hololens1-hardware.md#care-and-cleaning) a ujistěte se, že senzory neblokují nic.</span><span class="sxs-lookup"><span data-stu-id="144dd-141">[Clean your device visor](hololens1-hardware.md#care-and-cleaning) and make sure nothing is blocking the sensors.</span></span>
- <span data-ttu-id="144dd-142">Ujistěte se, že jste ve dobře osvětlené místnosti, která nemá velký přímý sluneční světlo.</span><span class="sxs-lookup"><span data-stu-id="144dd-142">Make sure that you're in a well-lit room that does not have a lot of direct sunlight.</span></span>
- <span data-ttu-id="144dd-143">Zkuste se podívat, co se gazing, a Prohlédněte si své okolí, aby HoloLens mohli provést jejich kompletní kontrolu.</span><span class="sxs-lookup"><span data-stu-id="144dd-143">Try walking around and gazing at your surroundings so that HoloLens can scan them more completely.</span></span>
- <span data-ttu-id="144dd-144">Pokud jste umístili spoustu hologramů, zkuste některé z nich odebrat.</span><span class="sxs-lookup"><span data-stu-id="144dd-144">If you've placed a lot of holograms, try removing some.</span></span>

<span data-ttu-id="144dd-145">Pokud máte potíže i nadále, zkuste spustit aplikaci kalibrace.</span><span class="sxs-lookup"><span data-stu-id="144dd-145">If you're still having problems, trying running the Calibration app.</span></span> <span data-ttu-id="144dd-146">Tato aplikace kalibruje váš HoloLens jenom za vás, aby vám pomohli lépe sledovat vaše hologramy.</span><span class="sxs-lookup"><span data-stu-id="144dd-146">This app calibrates your HoloLens just for you to help keep your holograms looking their best.</span></span> <span data-ttu-id="144dd-147">Provedete to tak, že přejdete na **Nastavení**  >  **systémové**  >  **nástroje**.</span><span class="sxs-lookup"><span data-stu-id="144dd-147">To do this, go to **Settings** > **System** > **Utilities**.</span></span> <span data-ttu-id="144dd-148">V části **kalibrace** vyberte **otevřít kalibraci**.</span><span class="sxs-lookup"><span data-stu-id="144dd-148">Under **Calibration**, select **Open Calibration**.</span></span>

[<span data-ttu-id="144dd-149">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="144dd-149">Back to list</span></span>](#list)

## <a name="finding-your-space-message"></a><span data-ttu-id="144dd-150">Zpráva hledání prostoru</span><span class="sxs-lookup"><span data-stu-id="144dd-150">"Finding your space" message</span></span>

<span data-ttu-id="144dd-151">Když HoloLens zajímá nebo načítá mezeru, může se zobrazit Stručná zpráva s informacemi o tom, jak místo vyhledat.</span><span class="sxs-lookup"><span data-stu-id="144dd-151">When HoloLens is learning or loading a space, you may see a brief message that says "Finding your space."</span></span> <span data-ttu-id="144dd-152">Pokud se tato zpráva zobrazí déle než několik sekund, v nabídce Start se zobrazí další zpráva s informacemi o tom, že se vaše místo pořád hledá.</span><span class="sxs-lookup"><span data-stu-id="144dd-152">If this message displays for more than a few seconds, you'll see another message under the Start menu that says "Still looking for your space."</span></span>

<span data-ttu-id="144dd-153">Tyto zprávy znamenají, že HoloLens má potíže s mapováním vašeho prostoru.</span><span class="sxs-lookup"><span data-stu-id="144dd-153">These messages mean that HoloLens is having trouble mapping your space.</span></span> <span data-ttu-id="144dd-154">Pokud k tomu dojde, můžete otevřít aplikace, ale do svého prostředí nemůžete umístit hologramy.</span><span class="sxs-lookup"><span data-stu-id="144dd-154">When this happens, you can open apps, but you can't place holograms in your environment.</span></span>

<span data-ttu-id="144dd-155">Pokud se tyto zprávy zobrazí často, zkuste jednu nebo více z následujících oprav:</span><span class="sxs-lookup"><span data-stu-id="144dd-155">If you see these messages often, try one or more of the following fixes:</span></span>

- <span data-ttu-id="144dd-156">Ujistěte se, že jste ve dobře osvětlené místnosti, která nemá velký přímý sluneční světlo.</span><span class="sxs-lookup"><span data-stu-id="144dd-156">Make sure that you're in a well-lit room that does not have a lot of direct sunlight.</span></span>
- <span data-ttu-id="144dd-157">Ujistěte se, že je zařízení vyčištěné.</span><span class="sxs-lookup"><span data-stu-id="144dd-157">Make sure that your device visor is clean.</span></span> <span data-ttu-id="144dd-158">[Naučte se vyčistit své Rozcestníky](hololens1-hardware.md#care-and-cleaning).</span><span class="sxs-lookup"><span data-stu-id="144dd-158">[Learn how to clean your visor](hololens1-hardware.md#care-and-cleaning).</span></span>
- <span data-ttu-id="144dd-159">Ujistěte se, že máte signál silného Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="144dd-159">Make sure that you have a strong Wi-Fi signal.</span></span> <span data-ttu-id="144dd-160">Pokud zadáte nové prostředí, které nemá Wi-Fi, nebo slabý Wi-Fi signál, HoloLens nebude moci najít váš prostor.</span><span class="sxs-lookup"><span data-stu-id="144dd-160">If you enter a new environment that has no Wi-Fi or a weak Wi-Fi signal, HoloLens won't be able find your space.</span></span> <span data-ttu-id="144dd-161">Kliknutím na **Nastavení**  >  **síť &amp; Internet**  >  **Wi-Fi** ověřte Wi-Fi připojení.</span><span class="sxs-lookup"><span data-stu-id="144dd-161">Check your Wi-Fi connection by going to **Settings** > **Network &amp; Internet** > **Wi-Fi**.</span></span>
- <span data-ttu-id="144dd-162">Zkuste se pomaleji přesunout.</span><span class="sxs-lookup"><span data-stu-id="144dd-162">Try moving more slowly.</span></span>

[<span data-ttu-id="144dd-163">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="144dd-163">Back to list</span></span>](#list)

## <a name="expected-holograms-arent-showing-in-my-space"></a><span data-ttu-id="144dd-164">Očekávané hologramy nejsou zobrazeny v mém prostoru</span><span class="sxs-lookup"><span data-stu-id="144dd-164">Expected holograms aren't showing in my space</span></span>

<span data-ttu-id="144dd-165">Pokud nevidíte hologramy, které jste umístili, nebo pokud vidíte některé, které neočekáváte, zkuste jednu nebo více z následujících oprav:</span><span class="sxs-lookup"><span data-stu-id="144dd-165">If you don't see the holograms that you placed, or if you're seeing some that you don't expect, try one or more of the following fixes:</span></span>

- <span data-ttu-id="144dd-166">Zapněte některé světla.</span><span class="sxs-lookup"><span data-stu-id="144dd-166">Turn on some lights.</span></span> <span data-ttu-id="144dd-167">HoloLens funguje nejlépe v dobře osvětleném prostoru.</span><span class="sxs-lookup"><span data-stu-id="144dd-167">HoloLens works best in a well-lit space.</span></span>
- <span data-ttu-id="144dd-168">Odstraňte hologramy, které nepotřebujete, a to tak, že v **Nastavení**  >  **systémových**  >  **hologramů**  >  **odeberete okolní hologramy**.</span><span class="sxs-lookup"><span data-stu-id="144dd-168">Remove holograms that you don't need by going to **Settings** > **System** > **Holograms** > **Remove nearby holograms**.</span></span> <span data-ttu-id="144dd-169">V případě potřeby vyberte možnost **Odebrat všechny hologramy**.</span><span class="sxs-lookup"><span data-stu-id="144dd-169">Or, if needed, select **Remove all holograms**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="144dd-170">Pokud se změní rozložení nebo osvětlení v prostoru významně, vaše zařízení může mít potíže s určením vašeho prostoru a zobrazování vašich hologramů.</span><span class="sxs-lookup"><span data-stu-id="144dd-170">If the layout or lighting in your space changes significantly, your device might have trouble identifying your space and showing your holograms.</span></span>

[<span data-ttu-id="144dd-171">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="144dd-171">Back to list</span></span>](#list)

## <a name="cant-place-holograms-or-see-previously-placed-holograms"></a><span data-ttu-id="144dd-172">Nelze umístit hologramy nebo zobrazit dříve umístěné hologramy.</span><span class="sxs-lookup"><span data-stu-id="144dd-172">Can't place holograms or see previously placed holograms</span></span>

<span data-ttu-id="144dd-173">Pokud HoloLens nemůže namapovat nebo načíst vaše místo, přejde do omezeného režimu a nebudete moci umístit hologramy nebo zobrazit hologramy, které jste umístili.</span><span class="sxs-lookup"><span data-stu-id="144dd-173">If HoloLens can't map or load your space, it enters Limited mode and you won't be able to place holograms or see holograms that you've placed.</span></span> <span data-ttu-id="144dd-174">Vyzkoušejte něco z tohoto:</span><span class="sxs-lookup"><span data-stu-id="144dd-174">Here are some things to try:</span></span>

- <span data-ttu-id="144dd-175">Ujistěte se, že je ve vašem prostředí dostatečné světlo, aby HoloLens mohl vidět a namapovat prostor.</span><span class="sxs-lookup"><span data-stu-id="144dd-175">Make sure that there's enough light in your environment so HoloLens can see and map the space.</span></span>
- <span data-ttu-id="144dd-176">Stojan mezi jedním a třemi měřiči, ze kterých se snažíte umístit hologram</span><span class="sxs-lookup"><span data-stu-id="144dd-176">Stand between one and three meters from where you're trying to place the hologram.</span></span>
- <span data-ttu-id="144dd-177">Neumísťujte hologramy na černé nebo odrážetelné povrchy.</span><span class="sxs-lookup"><span data-stu-id="144dd-177">Don't place holograms on black or reflective surfaces.</span></span>
- <span data-ttu-id="144dd-178">Ujistěte se, že jste připojení k síti Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="144dd-178">Make sure that you're connected to a Wi-Fi network.</span></span> <span data-ttu-id="144dd-179">Pokud nejste připojení k Wi-Fi, HoloLens nemůže identifikovat a načíst známé místo.</span><span class="sxs-lookup"><span data-stu-id="144dd-179">If you're not connected to Wi-Fi, HoloLens can't identify and load a known space.</span></span>
- <span data-ttu-id="144dd-180">Projděte si místnosti, aby HoloLens mohli znovu prohledat vaše okolí.</span><span class="sxs-lookup"><span data-stu-id="144dd-180">Walk around the rooms so HoloLens can rescan your surroundings.</span></span> <span data-ttu-id="144dd-181">Chcete-li zjistit, co již bylo prohledáno, klepněte na tlačítko Air pro zobrazení mapy mřížky mapování.</span><span class="sxs-lookup"><span data-stu-id="144dd-181">To see what's already been scanned, air tap to reveal the mapping mesh graphic.</span></span>
- <span data-ttu-id="144dd-182">Pokud potřebujete vytvořit nové místo, připojte se k Wi-Fi a restartujte HoloLens.</span><span class="sxs-lookup"><span data-stu-id="144dd-182">If you need to create a new space, connect to Wi-Fi, then restart your HoloLens.</span></span>
- <span data-ttu-id="144dd-183">Chcete-li zjistit, zda je správné místo aktivní, nebo ručně načíst mezeru, přejděte do části **Nastavení**  >  **systémové**  >  **prostory**.</span><span class="sxs-lookup"><span data-stu-id="144dd-183">To see if the correct space is active, or to manually load a space, go to **Settings** > **System** > **Spaces**.</span></span>
- <span data-ttu-id="144dd-184">Pokud je načteno správné místo a stále dochází k problémům, je možné, že je místo poškozeno.</span><span class="sxs-lookup"><span data-stu-id="144dd-184">If the correct space is loaded and you're still having problems, the space may be corrupt.</span></span> <span data-ttu-id="144dd-185">Pokud chcete tento problém vyřešit, vyberte požadované místo a pak vyberte **Odebrat**.</span><span class="sxs-lookup"><span data-stu-id="144dd-185">To fix this issue, select the space, then select **Remove**.</span></span> <span data-ttu-id="144dd-186">Po odebrání prostoru HoloLens začne namapovat okolí a vytvořit nové místo.</span><span class="sxs-lookup"><span data-stu-id="144dd-186">After you remove the space, HoloLens starts to map your surroundings and create a new space.</span></span>

[<span data-ttu-id="144dd-187">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="144dd-187">Back to list</span></span>](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a><span data-ttu-id="144dd-188">Hologramy zmizí nebo jsou encasedy jinými hologramy nebo objekty.</span><span class="sxs-lookup"><span data-stu-id="144dd-188">Holograms disappear or are encased in other holograms or objects</span></span>

<span data-ttu-id="144dd-189">Pokud se zobrazí příliš blízko hologramu, bude dočasně zmizet z tohoto &mdash; hologramu, stačí opustit ho.</span><span class="sxs-lookup"><span data-stu-id="144dd-189">If you get too close to a hologram, it will temporarily disappear&mdash;to restore the hologram, just move away from it.</span></span> <span data-ttu-id="144dd-190">I když jste umístili několik hologramů blízko sebe, některé z nich mohou zmizet.</span><span class="sxs-lookup"><span data-stu-id="144dd-190">Also, if you've placed several holograms close together, some may disappear.</span></span> <span data-ttu-id="144dd-191">Zkuste odebrat pár.</span><span class="sxs-lookup"><span data-stu-id="144dd-191">Try removing a few.</span></span>

<span data-ttu-id="144dd-192">Hologramy můžou být taky blokované nebo encased jinými hologramy nebo objekty, jako jsou zdi.</span><span class="sxs-lookup"><span data-stu-id="144dd-192">Holograms can also be blocked or encased by other holograms or by objects such as walls.</span></span> <span data-ttu-id="144dd-193">Pokud k tomu dojde, zkuste jednu z následujících oprav:</span><span class="sxs-lookup"><span data-stu-id="144dd-193">If this happens, try one of the following fixes:</span></span>

- <span data-ttu-id="144dd-194">Pokud je hologram encased na jiném hologramu, přesuňte hologram encased do jiného umístění.</span><span class="sxs-lookup"><span data-stu-id="144dd-194">If the hologram is encased in another hologram, move the encased hologram to another location.</span></span> <span data-ttu-id="144dd-195">Provedete to tak, že vyberete **Upravit** a pak klepnete a podržíte umístění.</span><span class="sxs-lookup"><span data-stu-id="144dd-195">To do this, select **Adjust**, then tap and hold to position it.</span></span>
- <span data-ttu-id="144dd-196">Pokud je hologram encased na stěně, vyberte **přizpůsobit**, potom na zeď, dokud se nezobrazí hologram.</span><span class="sxs-lookup"><span data-stu-id="144dd-196">If the hologram is encased in a wall, select **Adjust**, then walk toward the wall until the hologram appears.</span></span> <span data-ttu-id="144dd-197">Klepněte a podržte ho a pak Stáhněte si hologram na zeď.</span><span class="sxs-lookup"><span data-stu-id="144dd-197">Tap and hold, then pull the hologram forward and out of the wall.</span></span>
- <span data-ttu-id="144dd-198">Pokud nemůžu přesunout hologram pomocí gest, odeberte ho pomocí hlasu.</span><span class="sxs-lookup"><span data-stu-id="144dd-198">If you can't move the hologram by using gestures, use your voice to remove it.</span></span> <span data-ttu-id="144dd-199">Pohledu na hologramu a pak vyslovit "odebrat."</span><span class="sxs-lookup"><span data-stu-id="144dd-199">Gaze at the hologram, then say "Remove."</span></span> <span data-ttu-id="144dd-200">Pak otevřete hologram a vložte ho do nového umístění.</span><span class="sxs-lookup"><span data-stu-id="144dd-200">Then reopen the hologram and place it in a new location.</span></span>

[<span data-ttu-id="144dd-201">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="144dd-201">Back to list</span></span>](#list)

## <a name="holograms-are-appearing-on-the-other-side-of-a-wall"></a><span data-ttu-id="144dd-202">Hologramy se zobrazují na druhé straně zdi.</span><span class="sxs-lookup"><span data-stu-id="144dd-202">Holograms are appearing on the other side of a wall</span></span>

<span data-ttu-id="144dd-203">Pokud máte na stěnu hodně blízko, nebo pokud jste zeď ještě nezkontrolovali, můžete zobrazit hologramy, které jsou v další místnosti.</span><span class="sxs-lookup"><span data-stu-id="144dd-203">If you're very close to a wall, or if HoloLens hasn't scanned the wall yet, you can see holograms that are in the next room.</span></span> <span data-ttu-id="144dd-204">Pokud chcete prověřit zeď, je nutné mít na stěně jeden a tři měřiče a pohledu.</span><span class="sxs-lookup"><span data-stu-id="144dd-204">To scan the wall, stand between one and three meters from the wall and gaze at it.</span></span>

<span data-ttu-id="144dd-205">Černý nebo odrazný objekt (například černý Couch nebo chladnička z korozivzdorné oceli) poblíž zdi může způsobit problémy při pokusu o skenování na zeď.</span><span class="sxs-lookup"><span data-stu-id="144dd-205">A black or reflective object (for example, a black couch or a stainless steel refrigerator) near the wall may cause problems when HoloLens tries to scan the wall.</span></span> <span data-ttu-id="144dd-206">Pokud nějaký objekt existuje, naskenováním na druhé straně zdi.</span><span class="sxs-lookup"><span data-stu-id="144dd-206">If there is such an object, scan the other side of the wall.</span></span>

[<span data-ttu-id="144dd-207">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="144dd-207">Back to list</span></span>](#list)

## <a name="after-placing-a-hologram-on-a-wall-it-seems-to-float"></a><span data-ttu-id="144dd-208">Po umístění hologramu na zeď se zdá být plovoucí</span><span class="sxs-lookup"><span data-stu-id="144dd-208">After placing a hologram on a wall, it seems to float</span></span>

<span data-ttu-id="144dd-209">Hologram, který umístíte na zeď, se obvykle jeví jako 15palcový nebo mimo zeď.</span><span class="sxs-lookup"><span data-stu-id="144dd-209">A hologram that you place on a wall typically appears to be an inch or so away from the wall.</span></span> <span data-ttu-id="144dd-210">Pokud se zdá, že bude větší, zkuste jednu nebo více z následujících oprav:</span><span class="sxs-lookup"><span data-stu-id="144dd-210">If it appears to be farther away, try one or more of the following fixes:</span></span>

- <span data-ttu-id="144dd-211">Když umístíte hologram na zeď, podržíte jeden a tři měřiče od stěny a plošku na stěně rovnou.</span><span class="sxs-lookup"><span data-stu-id="144dd-211">When you place a hologram on a wall, stand between one and three meters from the wall and face the wall straight on.</span></span>
- <span data-ttu-id="144dd-212">Po klepnutí na zeď se zobrazí bublina s mapováním obrázku.</span><span class="sxs-lookup"><span data-stu-id="144dd-212">Air tap the wall to reveal the mapping mesh graphic.</span></span> <span data-ttu-id="144dd-213">Ujistěte se, že je síť zarovnána se stěnou.</span><span class="sxs-lookup"><span data-stu-id="144dd-213">Make sure that the mesh aligns with the wall.</span></span> <span data-ttu-id="144dd-214">Pokud ne, vyjměte hologram, znovu prohledejte zeď a potom to zkuste znovu.</span><span class="sxs-lookup"><span data-stu-id="144dd-214">If it doesn't, remove the hologram, rescan the wall, and then try again.</span></span>
- <span data-ttu-id="144dd-215">Pokud se problém opakuje, spusťte aplikaci kalibrace.</span><span class="sxs-lookup"><span data-stu-id="144dd-215">If the issue persists, run the Calibration app.</span></span> <span data-ttu-id="144dd-216">Najdete ho v **Nastavení**  >  **systémové**  >  **nástroje**.</span><span class="sxs-lookup"><span data-stu-id="144dd-216">You'll find it in **Settings** > **System** > **Utilities**.</span></span>

[<span data-ttu-id="144dd-217">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="144dd-217">Back to list</span></span>](#list)

## <a name="apps-appear-too-close-after-moving-them"></a><span data-ttu-id="144dd-218">Po přesunutí se aplikace zobrazují příliš blízko.</span><span class="sxs-lookup"><span data-stu-id="144dd-218">Apps appear too close after moving them</span></span>

<span data-ttu-id="144dd-219">Zkuste si prohledat a podívat se na oblast, do které aplikaci umísťujete, aby HoloLens prohledala oblast z různých úhlů.</span><span class="sxs-lookup"><span data-stu-id="144dd-219">Try walking around and looking at the area where you're placing the app so that HoloLens scans the area from different angles.</span></span> <span data-ttu-id="144dd-220">Může také pomáhat [Vyčištění zařízení v rozcestníku](hololens1-hardware.md#care-and-cleaning) .</span><span class="sxs-lookup"><span data-stu-id="144dd-220">[Cleaning your device visor](hololens1-hardware.md#care-and-cleaning) may also help.</span></span>

[<span data-ttu-id="144dd-221">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="144dd-221">Back to list</span></span>](#list)

## <a name="reporting-issues-with-unstable-or-inexact-holograms"></a><span data-ttu-id="144dd-222">Hlášení problémů s nestabilními nebo nepřesnými hologramy</span><span class="sxs-lookup"><span data-stu-id="144dd-222">Reporting issues with unstable or inexact holograms</span></span>
 
1. <span data-ttu-id="144dd-223">Zaznamenejte si a podívejte se na [video s zachycenými hybridními realitami](holographic-photos-and-videos.md#capture-a-mixed-reality-video) .</span><span class="sxs-lookup"><span data-stu-id="144dd-223">Please record and a [Mixed Reality Capture video](holographic-photos-and-videos.md#capture-a-mixed-reality-video) of the issue.</span></span> <span data-ttu-id="144dd-224">Toto video se dá později nahrát prostřednictvím centra zpětné vazby jako přiloženého souboru.</span><span class="sxs-lookup"><span data-stu-id="144dd-224">This video can be later uploaded through Feedback Hub as an attached file.</span></span>  
1. <span data-ttu-id="144dd-225">Povolení úplné telemetrie prostřednictvím **Nastavení** aplikace – > Diagnostika **ochrany osobních údajů**  ->  **& zpětná vazba** a v části **volitelná diagnostická data** zajistěte, aby byl přepínač nastaven na **zapnuto**</span><span class="sxs-lookup"><span data-stu-id="144dd-225">Enable full telemetry via the **Settings** app -> **Privacy** -> **Diagnostics & feedback** and under **Optional diagnostics data** ensure the toggle is set to **On**</span></span>
1. <span data-ttu-id="144dd-226">Získejte nejnovější hologram a opravy stability pomocí aktualizace na nejnovější [holografický operační systém Windows (20H2 nebo vyšší)](hololens-release-notes.md#windows-holographic-version-20h2).</span><span class="sxs-lookup"><span data-stu-id="144dd-226">Get the latest hologram scale and stability fixes by updating to the latest [Windows Holographic OS, (20H2 or higher)](hololens-release-notes.md#windows-holographic-version-20h2).</span></span> <span data-ttu-id="144dd-227">Po dokončení aktualizace proveďte následující:</span><span class="sxs-lookup"><span data-stu-id="144dd-227">After updating perform the following:</span></span>
    1. <span data-ttu-id="144dd-228">Odebrat všechny hologramy prostřednictvím **Nastavení** aplikace-> **systémových**  ->  **hologramů** – > pak vyberte **Odebrat všechny hologramy** a začít s čerstvou mapou.</span><span class="sxs-lookup"><span data-stu-id="144dd-228">Remove all Holograms via **Settings** app -> **System** -> **Holograms** -> then select **Remove all holograms** and start with a fresh map.</span></span>
    1. <span data-ttu-id="144dd-229">Vytvořte novou mapu svého prostoru pomocí HoloLens a Prohlédněte si svou místnost a Prohlédněte si všechny oblasti a plochy v prostoru.</span><span class="sxs-lookup"><span data-stu-id="144dd-229">Create a new map of your space by wearing the HoloLens and walking around your room and looking at all areas and surfaces in the space.</span></span> <span data-ttu-id="144dd-230">To proveďte po 2-3 minut.</span><span class="sxs-lookup"><span data-stu-id="144dd-230">Do this for 2-3 minutes.</span></span>
    1. <span data-ttu-id="144dd-231">Proveďte kalibraci IPD.</span><span class="sxs-lookup"><span data-stu-id="144dd-231">Perform IPD calibration.</span></span> <span data-ttu-id="144dd-232">Přejít na **Nastavení**  >  **systémové**  >  **nástroje**.</span><span class="sxs-lookup"><span data-stu-id="144dd-232">Go to **Settings** > **System** > **Utilities**.</span></span> <span data-ttu-id="144dd-233">V části **kalibrace** vyberte **otevřít kalibraci**.</span><span class="sxs-lookup"><span data-stu-id="144dd-233">Under **Calibration**, select **Open Calibration**.</span></span>
    1. <span data-ttu-id="144dd-234">Otestujte scénář znovu a zkontrolujte, zda stále přetrvává.</span><span class="sxs-lookup"><span data-stu-id="144dd-234">Re-test the scenario and see if it still persists.</span></span>
1. <span data-ttu-id="144dd-235">Pokud aktualizace problém neopraví, zajistěte prosím [problém centra zpětné vazby](hololens-feedback.md).</span><span class="sxs-lookup"><span data-stu-id="144dd-235">If updating does not fix the issue, please file a [Feedback Hub issue](hololens-feedback.md).</span></span> <span data-ttu-id="144dd-236">Po vyplňování zpětné vazby můžete použít tlačítko **sdílet** a vytvořit snadno propojený odkaz, který se dá odeslat při kontaktování podpory.</span><span class="sxs-lookup"><span data-stu-id="144dd-236">After you've filled feedback you can use the **Share** button, to create an easy to share link that can be sent when contacting support.</span></span>

[<span data-ttu-id="144dd-237">Zpět na seznam</span><span class="sxs-lookup"><span data-stu-id="144dd-237">Back to list</span></span>](#list)