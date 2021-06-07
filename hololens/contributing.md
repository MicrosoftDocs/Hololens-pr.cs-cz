---
title: Pokyny pro přispívání
description: Přečtěte si, jak přispívat do dokumentů HoloLens na platformě docs.microsoft.com pomocí Markdownu s charakterem GitHubu.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: dd205ab1fe399d6612be982136c80733a5eb087e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377560"
---
# <a name="contributing-to-the-hololens-documentation"></a><span data-ttu-id="730a5-103">Přispívání do dokumentace k HoloLens</span><span class="sxs-lookup"><span data-stu-id="730a5-103">Contributing to the HoloLens documentation</span></span>

<span data-ttu-id="730a5-104">Vítejte v [dokumentaci k HoloLens](https://github.com/MicrosoftDocs/Hololens).</span><span class="sxs-lookup"><span data-stu-id="730a5-104">Welcome to the [HoloLens documentation](https://github.com/MicrosoftDocs/Hololens)!</span></span> <span data-ttu-id="730a5-105">Všechny články, které v tomto úložišti vytváříte nebo upravujete, **budou přístupné veřejnosti.**</span><span class="sxs-lookup"><span data-stu-id="730a5-105">Any articles you create or edit in this repo **will be visible to the public.**</span></span> 

<span data-ttu-id="730a5-106">Dokumenty HoloLens se zobrazují na platformě docs.microsoft.com, která využívá Markdownu s funkcemi Markdig s využitím GitHubu.</span><span class="sxs-lookup"><span data-stu-id="730a5-106">HoloLens docs are displayed on the docs.microsoft.com platform, which uses GitHub-flavored Markdown with Markdig features.</span></span> <span data-ttu-id="730a5-107">Obsah, který upravíte v tomto úložišti, se naformátuje na stylizované stránky, které se zobrazují na https://docs.microsoft.com/hololens .</span><span class="sxs-lookup"><span data-stu-id="730a5-107">The content you edit in this repo gets formatted into stylized pages that show up at https://docs.microsoft.com/hololens.</span></span> 

<span data-ttu-id="730a5-108">Tato stránka obsahuje základní kroky a pokyny pro přispívání a odkazy na základy Markdownu.</span><span class="sxs-lookup"><span data-stu-id="730a5-108">This page covers the basic steps and guidelines for contributing and links to Markdown basics.</span></span> <span data-ttu-id="730a5-109">Děkujeme za váš příspěvek!</span><span class="sxs-lookup"><span data-stu-id="730a5-109">Thanks for your contribution!</span></span>

## <a name="available-repos"></a><span data-ttu-id="730a5-110">Dostupná úložiště</span><span class="sxs-lookup"><span data-stu-id="730a5-110">Available repos</span></span>

| <span data-ttu-id="730a5-111">Název úložiště</span><span class="sxs-lookup"><span data-stu-id="730a5-111">Repository name</span></span> | <span data-ttu-id="730a5-112">URL</span><span class="sxs-lookup"><span data-stu-id="730a5-112">URL</span></span> |
| --- | --- |
| <span data-ttu-id="730a5-113">HoloLens</span><span class="sxs-lookup"><span data-stu-id="730a5-113">HoloLens</span></span> | [<span data-ttu-id="730a5-114">MicrosoftDocs/HoloLens</span><span class="sxs-lookup"><span data-stu-id="730a5-114">MicrosoftDocs/HoloLens</span></span>](https://github.com/MicrosoftDocs/Hololens) |
| <span data-ttu-id="730a5-115">Hybridní realita</span><span class="sxs-lookup"><span data-stu-id="730a5-115">Mixed Reality</span></span> | [<span data-ttu-id="730a5-116">MicrosoftDocs/Mixed – realita</span><span class="sxs-lookup"><span data-stu-id="730a5-116">MicrosoftDocs/mixed-reality</span></span>](https://docs.microsoft.com/windows/mixed-reality) |
| <span data-ttu-id="730a5-117">Průvodce nadšenci VR</span><span class="sxs-lookup"><span data-stu-id="730a5-117">VR Enthusiasts Guide</span></span> | [<span data-ttu-id="730a5-118">MicrosoftDocs/smíšený – realita/patříte mezi fanoušky – příručka</span><span class="sxs-lookup"><span data-stu-id="730a5-118">MicrosoftDocs/mixed-reality/enthusiast-guide</span></span>](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a><span data-ttu-id="730a5-119">Než začnete</span><span class="sxs-lookup"><span data-stu-id="730a5-119">Before you start</span></span>

<span data-ttu-id="730a5-120">Pokud ho ještě nemáte, budete muset [vytvořit účet GitHub](https://github.com/join).</span><span class="sxs-lookup"><span data-stu-id="730a5-120">If you don't already have one, you'll need to [create a GitHub account](https://github.com/join).</span></span>

>[!NOTE]
><span data-ttu-id="730a5-121">Pokud jste zaměstnancem Microsoftu, propojte svůj účet GitHub s aliasem Microsoftu na [portálu Microsoft Open Source Portal](https://repos.opensource.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="730a5-121">If you're a Microsoft employee, link your GitHub account to your Microsoft alias on the [Microsoft Open Source portal](https://repos.opensource.microsoft.com/).</span></span> <span data-ttu-id="730a5-122">Připojte se ke organizacím **"Microsoft"** a **"MicrosoftDocs"** .</span><span class="sxs-lookup"><span data-stu-id="730a5-122">Join the **"Microsoft"** and **"MicrosoftDocs"** organizations.</span></span>

<span data-ttu-id="730a5-123">Při nastavování účtu GitHub doporučujeme také tato bezpečnostní opatření:</span><span class="sxs-lookup"><span data-stu-id="730a5-123">When setting up your GitHub account, we also recommend these security precautions:</span></span>
- <span data-ttu-id="730a5-124">Vytvořte [pro svůj účet GitHub silné heslo](https://github.com/settings/admin).</span><span class="sxs-lookup"><span data-stu-id="730a5-124">Create a [strong password for your GitHub account](https://github.com/settings/admin).</span></span>
- <span data-ttu-id="730a5-125">Povolte [dvojúrovňové ověřování](https://github.com/settings/two_factor_authentication/configure).</span><span class="sxs-lookup"><span data-stu-id="730a5-125">Enable [two-factor authentication](https://github.com/settings/two_factor_authentication/configure).</span></span>
- <span data-ttu-id="730a5-126">Uložte si [kódy obnovení](https://github.com/settings/auth/recovery-codes) na bezpečné místo.</span><span class="sxs-lookup"><span data-stu-id="730a5-126">Save your [recovery codes](https://github.com/settings/auth/recovery-codes) in a safe place.</span></span>
- <span data-ttu-id="730a5-127">Aktualizujte [Nastavení veřejného profilu](https://github.com/settings/profile).</span><span class="sxs-lookup"><span data-stu-id="730a5-127">Update your [public profile settings](https://github.com/settings/profile).</span></span>
   - <span data-ttu-id="730a5-128">Nastavte své jméno a zvažte nastavení *veřejného e-mailu* , aby se *nezobrazovala e-mailová adresa*.</span><span class="sxs-lookup"><span data-stu-id="730a5-128">Set your name, and consider setting your *Public email* to *Don't show my email address*.</span></span>
   - <span data-ttu-id="730a5-129">Doporučujeme nahrát profilový obrázek, protože Miniatura se zobrazuje na stránkách docs, na které přispějete.</span><span class="sxs-lookup"><span data-stu-id="730a5-129">We recommend you upload a profile picture because a thumbnail is shown on docs pages you contribute to.</span></span>
- <span data-ttu-id="730a5-130">Pokud plánujete použití příkazového řádku, zvažte nastavení [Správce přihlašovacích údajů Git pro Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span><span class="sxs-lookup"><span data-stu-id="730a5-130">If you plan to use the command line, consider setting up [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest).</span></span> <span data-ttu-id="730a5-131">Tímto způsobem nebudete muset zadávat heslo pokaždé, když provedete příspěvek.</span><span class="sxs-lookup"><span data-stu-id="730a5-131">That way, you won't have to enter your password every time you make a contribution.</span></span>

<span data-ttu-id="730a5-132">Systém publikování je svázán s GitHubem, takže tyto kroky jsou důležité.</span><span class="sxs-lookup"><span data-stu-id="730a5-132">The publishing system is tied to GitHub, so these steps are important.</span></span> <span data-ttu-id="730a5-133">Pomocí vašeho aliasu GitHubu budete mít k jednotlivým článkům v seznamu buď autora, nebo přispěvatele.</span><span class="sxs-lookup"><span data-stu-id="730a5-133">You'll be listed as either author or contributor to each article using your GitHub alias.</span></span>

## <a name="editing-an-existing-article"></a><span data-ttu-id="730a5-134">Úprava existujícího článku</span><span class="sxs-lookup"><span data-stu-id="730a5-134">Editing an existing article</span></span>

<span data-ttu-id="730a5-135">Pomocí následujícího pracovního postupu můžete provést aktualizace *existujícího článku* přes GitHub ve webovém prohlížeči:</span><span class="sxs-lookup"><span data-stu-id="730a5-135">Use the following workflow to make updates to *an existing article* via GitHub in a web browser:</span></span>

1. <span data-ttu-id="730a5-136">Ve složce Mixed-reality-docs přejděte k článku, který chcete upravit.</span><span class="sxs-lookup"><span data-stu-id="730a5-136">Navigate to the article you wish to edit in the "mixed-reality-docs" folder.</span></span>

2. <span data-ttu-id="730a5-137">V pravém horním rohu vyberte tlačítko Upravit (ikona tužky), které bude automaticky rozvětvit větev mimo hlavní větev.</span><span class="sxs-lookup"><span data-stu-id="730a5-137">Select the edit button (pencil icon) in the top right, which will automatically fork a disposable branch off the 'master' branch.</span></span>

   ![Upravit článek.](images/editpage.png)
   
3. <span data-ttu-id="730a5-139">Upravte obsah článku podle [tématu základní informace o Markdownu](#markdown-basics).</span><span class="sxs-lookup"><span data-stu-id="730a5-139">Edit the content of the article according to the ["Markdown basics"](#markdown-basics).</span></span>

4. <span data-ttu-id="730a5-140">Aktualizujte metadata v horní části každého článku:</span><span class="sxs-lookup"><span data-stu-id="730a5-140">Update metadata at the top of each article:</span></span>

   * <span data-ttu-id="730a5-141">**title**: nadpis stránky, který se zobrazí na kartě prohlížeče při prohlížení článku.</span><span class="sxs-lookup"><span data-stu-id="730a5-141">**title**: Page title that appears in the browser tab when the article is being viewed.</span></span> <span data-ttu-id="730a5-142">Nadpisy stránek se používají pro SEO a indexování, takže neměňte název, pokud není potřeba (ale to je méně důležité, než se dokumentace zveřejní).</span><span class="sxs-lookup"><span data-stu-id="730a5-142">Page titles are used for SEO and indexing, so don't change the title unless necessary (though this is less critical before documentation goes public).</span></span>
   * <span data-ttu-id="730a5-143">**Popis**: Napište stručný popis obsahu článku, který zvyšuje SEO a zjišťování.</span><span class="sxs-lookup"><span data-stu-id="730a5-143">**description**: Write a brief description of the article's content, which boosts SEO and discovery.</span></span>
   * <span data-ttu-id="730a5-144">**Autor**: Pokud jste primárním vlastníkem stránky, přidejte sem svůj alias GitHubu.</span><span class="sxs-lookup"><span data-stu-id="730a5-144">**author**: If you're the primary owner of the page, add your GitHub alias here.</span></span>
   * <span data-ttu-id="730a5-145">**MS. Author**: Pokud jste primárním vlastníkem stránky, přidejte sem svůj alias Microsoftu (nepotřebujete @microsoft.com , jenom alias).</span><span class="sxs-lookup"><span data-stu-id="730a5-145">**ms.author**: If you're the primary owner of the page, add your Microsoft alias here (you don't need @microsoft.com, just the alias).</span></span>
   * <span data-ttu-id="730a5-146">**MS. Date**: aktualizujte datum, pokud přidáváte hlavní obsah stránky, ale ne pro opravy, jako je například vyjasnění, formátování, gramatika nebo pravopis.</span><span class="sxs-lookup"><span data-stu-id="730a5-146">**ms.date**: Update the date if you're adding major content to the page, but not for fixes like clarification, formatting, grammar, or spelling.</span></span>
   * <span data-ttu-id="730a5-147">**klíčová slova**: pomocná klíčová slova v SEO (optimalizace vyhledávacích strojů).</span><span class="sxs-lookup"><span data-stu-id="730a5-147">**keywords**: Keywords aid in SEO (search engine optimization).</span></span> <span data-ttu-id="730a5-148">Přidejte klíčová slova, která jsou oddělená čárkou a mezerou, která jsou specifická pro váš článek, ale za poslední klíčová slova v seznamu se nezaokrouhlí žádné interpunkční znaménko.</span><span class="sxs-lookup"><span data-stu-id="730a5-148">Add keywords, separated by a comma and a space, that are specific to your article, but no punctuation after the last keyword in your list.</span></span> <span data-ttu-id="730a5-149">Nemusíte přidávat globální klíčová slova, která platí pro všechny články, protože jsou spravovaná jinde.</span><span class="sxs-lookup"><span data-stu-id="730a5-149">You don't need to add global keywords that apply to all articles, as those are managed elsewhere.</span></span> 
   
5. <span data-ttu-id="730a5-150">Až dokončíte úpravy článků, přejděte dolů a vyberte **navrhnout změnu souboru**.</span><span class="sxs-lookup"><span data-stu-id="730a5-150">When you've completed your article edits, scroll down and select **Propose file change**.</span></span>

6. <span data-ttu-id="730a5-151">Na další stránce vyberte **vytvořit žádost o získání dat** a slučte automaticky vytvořenou větev do hlavního.</span><span class="sxs-lookup"><span data-stu-id="730a5-151">On the next page, select **Create pull request** to merge your automatically created branch into 'master.'</span></span>

7. <span data-ttu-id="730a5-152">Opakujte výše uvedené kroky pro další článek, který chcete upravit.</span><span class="sxs-lookup"><span data-stu-id="730a5-152">Repeat the steps above for the next article you want to edit.</span></span>

## <a name="renaming-or-deleting-an-existing-article"></a><span data-ttu-id="730a5-153">Přejmenování nebo odstranění existujícího článku</span><span class="sxs-lookup"><span data-stu-id="730a5-153">Renaming or deleting an existing article</span></span>

<span data-ttu-id="730a5-154">Pokud vaše změna přejmenuje nebo odstraní existující článek, nezapomeňte přidat přesměrování.</span><span class="sxs-lookup"><span data-stu-id="730a5-154">If your change will rename or delete an existing article, be sure to add a redirect.</span></span> <span data-ttu-id="730a5-155">Tím se na správném místě pořád ukončí kdokoli s odkazem na stávající článek.</span><span class="sxs-lookup"><span data-stu-id="730a5-155">That way, anyone with a link to the existing article will still end up in the right place.</span></span> <span data-ttu-id="730a5-156">Přesměrování se spravují pomocí .openpublishing.redirection.jsv souboru v kořenovém adresáři úložiště.</span><span class="sxs-lookup"><span data-stu-id="730a5-156">Redirects are managed by the .openpublishing.redirection.json file in the root of the repo.</span></span>

<span data-ttu-id="730a5-157">Chcete-li přidat přesměrování na .openpublishing.redirection.jsna, přidejte do pole položku `redirections` :</span><span class="sxs-lookup"><span data-stu-id="730a5-157">To add a redirect to .openpublishing.redirection.json, add an entry to the `redirections` array:</span></span>

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- <span data-ttu-id="730a5-158">`source_path`Je relativní cesta úložiště ke starému článku, který odebíráte.</span><span class="sxs-lookup"><span data-stu-id="730a5-158">The `source_path` is the relative repository path to the old article that you're removing.</span></span> <span data-ttu-id="730a5-159">Ujistěte se, že cesta začíná `mixed-reality-docs` a končí na `.md` .</span><span class="sxs-lookup"><span data-stu-id="730a5-159">Be sure the path starts with `mixed-reality-docs` and ends with `.md`.</span></span>

- <span data-ttu-id="730a5-160">`redirect_url`Je relativní veřejná adresa URL od starého článku k novému článku.</span><span class="sxs-lookup"><span data-stu-id="730a5-160">The `redirect_url` is the relative public URL from the old article to the new article.</span></span> <span data-ttu-id="730a5-161">Ujistěte se, že tato **Adresa URL neobsahuje** `mixed-reality-docs` nebo `.md` , jak odkazuje na veřejnou adresu URL, a ne na cestu k úložišti.</span><span class="sxs-lookup"><span data-stu-id="730a5-161">Be sure that this URL **doesn't** contain `mixed-reality-docs` or `.md`, as it refers to the public URL and not the repository path.</span></span> <span data-ttu-id="730a5-162">Odkaz na oddíl v rámci nového článku pomocí `#section` je povolen.</span><span class="sxs-lookup"><span data-stu-id="730a5-162">Linking to a section within the new article using `#section` is allowed.</span></span> <span data-ttu-id="730a5-163">V případě potřeby můžete také použít absolutní cestu k jinému webu.</span><span class="sxs-lookup"><span data-stu-id="730a5-163">You can also use an absolute path to another site here, if necessary.</span></span>

- <span data-ttu-id="730a5-164">`redirect_document_id` Určuje, zda chcete zachovat ID dokumentu z předchozího souboru.</span><span class="sxs-lookup"><span data-stu-id="730a5-164">`redirect_document_id` indicates whether you would like to keep the document ID from the previous file.</span></span> <span data-ttu-id="730a5-165">Výchozí formát je `false`.</span><span class="sxs-lookup"><span data-stu-id="730a5-165">The default is `false`.</span></span> <span data-ttu-id="730a5-166">Použijte, `true` Pokud chcete zachovat `ms.documentid` hodnotu atributu z přesměrovaného článku.</span><span class="sxs-lookup"><span data-stu-id="730a5-166">Use `true` if you want to preserve the `ms.documentid` attribute value from the redirected article.</span></span> <span data-ttu-id="730a5-167">Pokud zachováte ID dokumentu, data, jako jsou například zobrazení stránky a klasifikace, budou přenesena do cílového článku.</span><span class="sxs-lookup"><span data-stu-id="730a5-167">If you preserve the document ID, data, such as page views and rankings, will be transferred to the target article.</span></span> <span data-ttu-id="730a5-168">Udělejte to, pokud je přesměrování primárně přejmenováno, a ne ukazatel na jiný článek, který se vztahuje pouze na část stejného obsahu.</span><span class="sxs-lookup"><span data-stu-id="730a5-168">Do this if the redirect is primarily a rename, and not a pointer to different article that only covers some of the same content.</span></span>

<span data-ttu-id="730a5-169">Pokud přidáte přesměrování, nezapomeňte odstranit i starý soubor.</span><span class="sxs-lookup"><span data-stu-id="730a5-169">If you add a redirect, be sure to delete the old file as well.</span></span>

## <a name="creating-a-new-article"></a><span data-ttu-id="730a5-170">Vytváření nového článku</span><span class="sxs-lookup"><span data-stu-id="730a5-170">Creating a new article</span></span>

<span data-ttu-id="730a5-171">Pomocí následujícího pracovního postupu můžete *vytvářet nové články* v úložišti dokumentace přes GitHub ve webovém prohlížeči:</span><span class="sxs-lookup"><span data-stu-id="730a5-171">Use the following workflow to *create new articles* in the documentation repo via GitHub in a web browser:</span></span>

1. <span data-ttu-id="730a5-172">Vytvořte rozvětvení s větví "Master" MicrosoftDocs/Mixed-reality (pomocí tlačítka **rozvětvení** v pravém horním rohu).</span><span class="sxs-lookup"><span data-stu-id="730a5-172">Create a fork off the MicrosoftDocs/mixed-reality 'master' branch (using the **Fork** button in the top right).</span></span>

   ![Rozvětvení hlavní větve](images/forkbranch.png)
   
2. <span data-ttu-id="730a5-174">Ve složce Mixed-reality-docs vyberte **vytvořit nový soubor** v pravém horním rohu.</span><span class="sxs-lookup"><span data-stu-id="730a5-174">In the "mixed-reality-docs" folder, select **Create new file** in the top right.</span></span>

3. <span data-ttu-id="730a5-175">Vytvořte název stránky pro článek (místo mezer použijte spojovníky a nepoužívejte interpunkci nebo apostrofy) a přidejte ". MD".</span><span class="sxs-lookup"><span data-stu-id="730a5-175">Create a page name for the article (use hyphens instead of spaces and don't use punctuation or apostrophes) and append ".md"</span></span>

   ![Pojmenujte novou stránku.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   ><span data-ttu-id="730a5-177">Ujistěte se, že jste nový článek vytvořili ze složky "Mixed-reality-docs".</span><span class="sxs-lookup"><span data-stu-id="730a5-177">Make sure you create the new article from within the "mixed-reality-docs" folder.</span></span> <span data-ttu-id="730a5-178">To můžete ověřit zaškrtnutím "/Mixed-reality-docs/" v novém řádku s názvem souboru.</span><span class="sxs-lookup"><span data-stu-id="730a5-178">You can confirm this by checking for "/mixed-reality-docs/" in the new file name line.</span></span>

4. <span data-ttu-id="730a5-179">V horní části nové stránky přidejte následující blok metadat:</span><span class="sxs-lookup"><span data-stu-id="730a5-179">At the top of your new page, add the following metadata block:</span></span>

   ```md
   ---
   title:
   description:
   author:
   ms.author:
   ms.date:
   ms.topic: article
   keywords:
   ---
   ```

5. <span data-ttu-id="730a5-180">Vyplňte příslušná pole metadat podle pokynů v [části výše](#editing-an-existing-article).</span><span class="sxs-lookup"><span data-stu-id="730a5-180">Fill in the relevant metadata fields per the instructions in the [section above](#editing-an-existing-article).</span></span>

6. <span data-ttu-id="730a5-181">Zápis obsahu článků pomocí [základů Markdownu](#markdown-basics)</span><span class="sxs-lookup"><span data-stu-id="730a5-181">Write article content using [Markdown basics](#markdown-basics).</span></span>

7. <span data-ttu-id="730a5-182">Přidejte do `## See also` dolní části článku část s odkazy na další relevantní články.</span><span class="sxs-lookup"><span data-stu-id="730a5-182">Add a `## See also` section at the bottom of the article with links to other relevant articles.</span></span>

8. <span data-ttu-id="730a5-183">Po dokončení vyberte **Potvrdit nový soubor**.</span><span class="sxs-lookup"><span data-stu-id="730a5-183">When finished, select **Commit new file**.</span></span>

9. <span data-ttu-id="730a5-184">Vyberte **Nová žádost o** přijetí změn a slučte "hlavní" větev svého rozvětvení do MicrosoftDocs/smíšené-reality "Master" (Ujistěte se, že šipka ukazuje správný způsob).</span><span class="sxs-lookup"><span data-stu-id="730a5-184">Select **New pull request** and merge your fork's 'master' branch into MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Vytvoření žádosti o přijetí změn z větve do MicrosoftDocs/smíšené reality](images/pr-to-master.png)

## <a name="markdown-basics"></a><span data-ttu-id="730a5-186">Základy formátu Markdown</span><span class="sxs-lookup"><span data-stu-id="730a5-186">Markdown basics</span></span>

<span data-ttu-id="730a5-187">Následující materiály vám pomůžou naučit se, jak upravovat dokumentaci pomocí jazyka Markdownu:</span><span class="sxs-lookup"><span data-stu-id="730a5-187">The following resources will help you learn how to edit documentation using the Markdown language:</span></span>

- [<span data-ttu-id="730a5-188">Základy formátu Markdown</span><span class="sxs-lookup"><span data-stu-id="730a5-188">Markdown basics</span></span>](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [<span data-ttu-id="730a5-189">Další zdroje informací pro zápis Markdownu pro docs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="730a5-189">Additional resources for writing Markdown for docs.microsoft.com</span></span>](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a><span data-ttu-id="730a5-190">Přidávání tabulek</span><span class="sxs-lookup"><span data-stu-id="730a5-190">Adding tables</span></span>

<span data-ttu-id="730a5-191">Vzhledem k tomu, že tabulky stylů docs.microsoft.com, nemají ohraničení ani vlastní styly, ani když se pokusíte o vloženou šablonu stylů CSS.</span><span class="sxs-lookup"><span data-stu-id="730a5-191">Because of the way docs.microsoft.com styles tables, they won’t have borders or custom styles, even if you try inline CSS.</span></span> <span data-ttu-id="730a5-192">Zdá se, že bude fungovat po krátké době, ale nakonec bude tato platforma oddělit styly z tabulky.</span><span class="sxs-lookup"><span data-stu-id="730a5-192">It will appear to work for a short period of time, but eventually the platform will strip the styling out of the table.</span></span> <span data-ttu-id="730a5-193">Proto Plánujte dopředu a udržujte své tabulky jednoduché.</span><span class="sxs-lookup"><span data-stu-id="730a5-193">So plan ahead and keep your tables simple.</span></span> <span data-ttu-id="730a5-194">[Tady je web, který usnadňuje Markdownu tabulek](https://www.tablesgenerator.com/markdown_tables).</span><span class="sxs-lookup"><span data-stu-id="730a5-194">[Here’s a site that makes Markdown tables easy](https://www.tablesgenerator.com/markdown_tables).</span></span>

<span data-ttu-id="730a5-195">[Rozšíření docs Markdownu pro Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) také usnadňuje generování tabulek, pokud používáte [Visual Studio Code (viz níže)](#using-visual-studio-code) , chcete-li upravit dokumentaci.</span><span class="sxs-lookup"><span data-stu-id="730a5-195">The [Docs Markdown Extension for Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) also makes table generation easy if you're using [Visual Studio Code (see below)](#using-visual-studio-code) to edit the documentation.</span></span>

### <a name="adding-images"></a><span data-ttu-id="730a5-196">Přidávání imagí</span><span class="sxs-lookup"><span data-stu-id="730a5-196">Adding images</span></span>

<span data-ttu-id="730a5-197">Vaše image budete muset nahrát do složky "Mixed-realit-docs/images" v úložišti a pak je podle potřeby odkázat v článku.</span><span class="sxs-lookup"><span data-stu-id="730a5-197">You’ll need to upload your images to the "mixed-reality-docs/images" folder in the repo, and then reference them appropriately in the article.</span></span> <span data-ttu-id="730a5-198">Obrázky se automaticky zobrazí v plné velikosti, což znamená, že velké obrázky budou vyplnit celou šířku článku.</span><span class="sxs-lookup"><span data-stu-id="730a5-198">Images will automatically show up at full-size, which means large images will fill the entire width of the article.</span></span> <span data-ttu-id="730a5-199">Před odesláním imagí doporučujeme předem nastavovat jejich změny.</span><span class="sxs-lookup"><span data-stu-id="730a5-199">We recommend pre-sizing your images before uploading them.</span></span> <span data-ttu-id="730a5-200">Doporučená šířka je mezi 600 a 700 pixelů, ale pokud se jedná o hustý snímek obrazovky nebo zlomek snímku obrazovky, měli byste velikost navýšit nebo snížit.</span><span class="sxs-lookup"><span data-stu-id="730a5-200">The recommended width is between 600 and 700 pixels, though you should size up or down if it’s a dense screenshot or a fraction of a screenshot, respectively.</span></span>

>[!IMPORTANT]
><span data-ttu-id="730a5-201">Obrázky můžete do svého forku nahrát jenom před sloučením.</span><span class="sxs-lookup"><span data-stu-id="730a5-201">You can only upload images to your forked repo before merging.</span></span> <span data-ttu-id="730a5-202">Pokud tedy plánujete přidat obrázky do článku, budete muset pomocí [nástroje Visual Studio Code](#using-visual-studio-code) nejprve přidat obrázky do složky "images" forku nebo se ujistit, že jste ve webovém prohlížeči provedli následující:</span><span class="sxs-lookup"><span data-stu-id="730a5-202">So, if you plan on adding images to an article, you'll need to [use Visual Studio Code](#using-visual-studio-code) to add the images to your fork's "images" folder first or make sure you've done the following in a web browser:</span></span>
>
>1. <span data-ttu-id="730a5-203">Fork je v microsoftdocs/hybridním reality.</span><span class="sxs-lookup"><span data-stu-id="730a5-203">Forked the MicrosoftDocs/mixed-reality repo.</span></span>
>2. <span data-ttu-id="730a5-204">Upravoval jste článek ve forku.</span><span class="sxs-lookup"><span data-stu-id="730a5-204">Edited the article in your fork.</span></span>
>3. <span data-ttu-id="730a5-205">Nahráli jste obrázky, na které odkazujete ve svém článku, do složky mixed-reality-docs/images ve forku.</span><span class="sxs-lookup"><span data-stu-id="730a5-205">Uploaded the images you're referencing in your article to the "mixed-reality-docs/images" folder in your fork.</span></span>
>4. <span data-ttu-id="730a5-206">Vytvořili jste **žádost o stažení** pro sloučení vašeho forku do hlavní větve MicrosoftDocs/mixed-reality.</span><span class="sxs-lookup"><span data-stu-id="730a5-206">Created a **pull request** to merge your fork into the MicrosoftDocs/mixed-reality 'master' branch.</span></span>
>
><span data-ttu-id="730a5-207">Pokud chcete zjistit, jak nastavit vlastní roz fork, postupujte podle pokynů k [vytvoření nového článku.](#creating-a-new-article)</span><span class="sxs-lookup"><span data-stu-id="730a5-207">To learn how to set up your own forked repo, follow the instructions for [creating a new article](#creating-a-new-article).</span></span>

## <a name="previewing-your-work"></a><span data-ttu-id="730a5-208">Náhled práce</span><span class="sxs-lookup"><span data-stu-id="730a5-208">Previewing your work</span></span>

<span data-ttu-id="730a5-209">Při úpravách na GitHubu prostřednictvím webového prohlížeče můžete vybrat kartu **Náhled** v horní části stránky a před potvrzením zobrazit náhled své práce.</span><span class="sxs-lookup"><span data-stu-id="730a5-209">While editing in GitHub via a web browser, you can select the **Preview** tab near the top of the page to preview your work before committing.</span></span> 

>[!NOTE]
><span data-ttu-id="730a5-210">Náhled změn na webu review.docs.microsoft.com je k dispozici pouze zaměstnancům Microsoftu.</span><span class="sxs-lookup"><span data-stu-id="730a5-210">Previewing your changes on review.docs.microsoft.com is only available to Microsoft employees</span></span>

<span data-ttu-id="730a5-211">Zaměstnanci Microsoftu: Po sloučení příspěvků do hlavní větve můžete obsah zkontrolovat předtím, než se zveřejní na https://review.docs.microsoft.com/hololens?branch=master adrese .</span><span class="sxs-lookup"><span data-stu-id="730a5-211">Microsoft employees: once your contributions have been merged into the 'master' branch, you can review the content before it goes public at https://review.docs.microsoft.com/hololens?branch=master.</span></span> <span data-ttu-id="730a5-212">Najděte svůj článek pomocí obsahu v levém sloupci.</span><span class="sxs-lookup"><span data-stu-id="730a5-212">Find your article using the table of contents in the left column.</span></span>

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a><span data-ttu-id="730a5-213">Úpravy v prohlížeči vs. úpravy pomocí desktopových klientů</span><span class="sxs-lookup"><span data-stu-id="730a5-213">Editing in the browser vs. editing with a desktop client</span></span>

<span data-ttu-id="730a5-214">Úpravy v prohlížeči jsou nejjednodušším způsobem, jak provést rychlé změny, ale má to několik nevýhod:</span><span class="sxs-lookup"><span data-stu-id="730a5-214">Editing in the browser is the easiest way to make quick changes, however, there are a few disadvantages:</span></span>

- <span data-ttu-id="730a5-215">Kontrola pravopisu se vám neschová.</span><span class="sxs-lookup"><span data-stu-id="730a5-215">You don't get spell-check.</span></span>
- <span data-ttu-id="730a5-216">S jinými články nemáte žádné inteligentní propojení (název souboru článku musíte zadat ručně).</span><span class="sxs-lookup"><span data-stu-id="730a5-216">You don't get any smart-linking to other articles (you have to manually type the article's filename).</span></span>
- <span data-ttu-id="730a5-217">Nahrávání obrázků a odkazování na obrázky může být problém.</span><span class="sxs-lookup"><span data-stu-id="730a5-217">It can be a hassle to upload and reference images.</span></span>

<span data-ttu-id="730a5-218">Pokud se těmto problémům těmto problémům chytáte raději, použijte desktopového klienta, jako [je Visual Studio Code](https://code.visualstudio.com/) s [několika](#useful-extensions) užitečnými rozšířeními při přispívání.</span><span class="sxs-lookup"><span data-stu-id="730a5-218">If you'd rather not deal with these issues, use a desktop client like [Visual Studio Code](https://code.visualstudio.com/) with a couple [helpful extensions](#useful-extensions) when contributing.</span></span>

## <a name="using-visual-studio-code"></a><span data-ttu-id="730a5-219">Používání nástroje Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="730a5-219">Using Visual Studio Code</span></span>

<span data-ttu-id="730a5-220">Z důvodů uvedených [výše](#editing-in-the-browser-vs-editing-with-a-desktop-client)můžete preferovat použití desktopových klientů k úpravám dokumentace místo webového prohlížeče.</span><span class="sxs-lookup"><span data-stu-id="730a5-220">For the reasons listed [above](#editing-in-the-browser-vs-editing-with-a-desktop-client), you may prefer using a desktop client to edit documentation instead of a web browser.</span></span> <span data-ttu-id="730a5-221">Doporučujeme použít [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="730a5-221">We recommend using [Visual Studio Code](https://code.visualstudio.com/).</span></span>

### <a name="setup"></a><span data-ttu-id="730a5-222">Nastavení</span><span class="sxs-lookup"><span data-stu-id="730a5-222">Setup</span></span>

<span data-ttu-id="730a5-223">Postupujte podle těchto kroků a Visual Studio Code pro práci s tímto repo:</span><span class="sxs-lookup"><span data-stu-id="730a5-223">Follow these steps to configure Visual Studio Code to work with this repo:</span></span>

1. <span data-ttu-id="730a5-224">Ve webovém prohlížeči:</span><span class="sxs-lookup"><span data-stu-id="730a5-224">In a web browser:</span></span>
    1. <span data-ttu-id="730a5-225">Nainstalujte [git pro svůj počítač.](https://git-scm.com/downloads)</span><span class="sxs-lookup"><span data-stu-id="730a5-225">Install [Git for your PC](https://git-scm.com/downloads).</span></span>
    2. <span data-ttu-id="730a5-226">Nainstalujte [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="730a5-226">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
    3. <span data-ttu-id="730a5-227">[Fork MicrosoftDocs/mixed-reality,](#creating-a-new-article) pokud jste to ještě neudělali.</span><span class="sxs-lookup"><span data-stu-id="730a5-227">[Fork MicrosoftDocs/mixed-reality](#creating-a-new-article) if you haven't already.</span></span>
    4. <span data-ttu-id="730a5-228">Ve forku vyberte Clone **or download (Klonovat nebo stáhnout)** a zkopírujte adresu URL.</span><span class="sxs-lookup"><span data-stu-id="730a5-228">In your fork, select **Clone or download** and copy the URL.</span></span>
2. <span data-ttu-id="730a5-229">Vytvořte místní klon forku v Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="730a5-229">Create a local clone of your fork in Visual Studio Code:</span></span>
    1. <span data-ttu-id="730a5-230">V **nabídce View** (Zobrazení) vyberte **Command Palette (Paleta příkazů).**</span><span class="sxs-lookup"><span data-stu-id="730a5-230">From the **View** menu, select **Command Palette**.</span></span>
    2. <span data-ttu-id="730a5-231">Napište Git: Clone.</span><span class="sxs-lookup"><span data-stu-id="730a5-231">Type "Git: Clone."</span></span>
    3. <span data-ttu-id="730a5-232">Vložte zkopírované adresy URL.</span><span class="sxs-lookup"><span data-stu-id="730a5-232">Paste the URL you copied.</span></span>
    4. <span data-ttu-id="730a5-233">Zvolte, kam chcete klon uložit do počítače.</span><span class="sxs-lookup"><span data-stu-id="730a5-233">Choose where to save the clone on your PC.</span></span>
    5. <span data-ttu-id="730a5-234">V místní nabídce vyberte Open **repo** (Otevřít repo).</span><span class="sxs-lookup"><span data-stu-id="730a5-234">Select **Open repo** in the pop-up.</span></span>

### <a name="editing-documentation"></a><span data-ttu-id="730a5-235">Úprava dokumentace</span><span class="sxs-lookup"><span data-stu-id="730a5-235">Editing documentation</span></span>

<span data-ttu-id="730a5-236">Pomocí následujícího pracovního postupu můžete provádět změny v dokumentaci pomocí Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="730a5-236">Use the following workflow to make changes to the documentation with Visual Studio Code:</span></span>

>[!NOTE]
><span data-ttu-id="730a5-237">Všechny pokyny k [úpravám](#editing-an-existing-article) a vytváření [článků](#creating-a-new-article) a základy úprav [Markdownu](#markdown-basics)uvedené výše platí i při Visual Studio Code kódu.</span><span class="sxs-lookup"><span data-stu-id="730a5-237">All the guidance for [editing](#editing-an-existing-article) and [creating](#creating-a-new-article) articles, and the [basics of editing Markdown](#markdown-basics), from above applies when using Visual Studio Code as well.</span></span>

1. <span data-ttu-id="730a5-238">Ujistěte se, že je naklonovaný fork aktuální s oficiálním repo.</span><span class="sxs-lookup"><span data-stu-id="730a5-238">Make sure your cloned fork is up to date with the official repo.</span></span>

   1. <span data-ttu-id="730a5-239">Ve webovém prohlížeči vytvořte žádost o stažení, která synchronizuje nedávné změny od ostatních přispěvatelů v MicrosoftDocs nebo hlavní realitě do vašeho forku (ujistěte se, že šipka ukazuje správným směrem).</span><span class="sxs-lookup"><span data-stu-id="730a5-239">In a web browser, create a pull request to sync recent changes from other contributors in MicrosoftDocs/mixed-reality 'master' to your fork (make sure the arrow is pointing the right way).</span></span>
      
      ![Synchronizace změn z MicrosoftDocs/hybridní reality do forku](images/sync-repos.png)
      
   2. <span data-ttu-id="730a5-241">V Visual Studio Code tlačítko Synchronizovat, aby se nový aktualizovaný fork synchronizoval s místním klonem.</span><span class="sxs-lookup"><span data-stu-id="730a5-241">In Visual Studio Code, select the sync button to sync your freshly updated fork to the local clone.</span></span>
      
      ![Klikněte na obrázek tlačítka Synchronizace.](images/sync-clone.png)
      
2. <span data-ttu-id="730a5-243">Články můžete vytvářet nebo upravovat v naklonovaném Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="730a5-243">Create or edit articles in your cloned repo using Visual Studio Code.</span></span>

   1. <span data-ttu-id="730a5-244">Upravte jeden nebo více článků (v případě potřeby přidejte obrázky do složky images).</span><span class="sxs-lookup"><span data-stu-id="730a5-244">Edit one or more articles (add images to “images” folder if necessary).</span></span>
   
   2. <span data-ttu-id="730a5-245">**Uložte** změny v **Průzkumníku**.</span><span class="sxs-lookup"><span data-stu-id="730a5-245">**Save** changes in **Explorer**.</span></span>
      
      ![V Průzkumníku zvolte Uložit vše.](images/explorer-save.png)
      
   3. <span data-ttu-id="730a5-247">**Potvrďte všechny** změny ve **zdrojovém kódu** (po zobrazení výzvy zapište zprávu potvrzení).</span><span class="sxs-lookup"><span data-stu-id="730a5-247">**Commit all** changes in **Source Control** (write commit message when prompted).</span></span>
   
      ![Volba možnosti Potvrdit vše ve správy zdrojového kódu](images/source-control-commit.png)
      
   4. <span data-ttu-id="730a5-249">Výběrem **tlačítka synchronizovat** synchronizujte změny zpět do původního zdroje (váš fork na GitHubu).</span><span class="sxs-lookup"><span data-stu-id="730a5-249">Select the **sync** button to sync your changes back to origin (your fork on GitHub).</span></span>
      
      ![Klikněte na tlačítko Synchronizovat.](images/sync-back.png)
      
3. <span data-ttu-id="730a5-251">Ve webovém prohlížeči vytvořte žádost o stažení pro synchronizaci nových změn ve forku zpět do MicrosoftDocs/master hybridní reality (ujistěte se, že šipka ukazuje správným způsobem).</span><span class="sxs-lookup"><span data-stu-id="730a5-251">In a web browser, create a pull request to sync new changes in your fork back to MicrosoftDocs/mixed-reality 'master' (make sure the arrow is pointing the correct way).</span></span>

   ![Vytvoření žádosti o stažení z forku do MicrosoftDocs/mixed-reality](images/pr-to-master.png)

### <a name="useful-extensions"></a><span data-ttu-id="730a5-253">Užitečná rozšíření</span><span class="sxs-lookup"><span data-stu-id="730a5-253">Useful extensions</span></span>

<span data-ttu-id="730a5-254">Při úpravách Visual Studio Code jsou užitečná následující rozšíření:</span><span class="sxs-lookup"><span data-stu-id="730a5-254">The following Visual Studio Code extensions are useful when editing documentation:</span></span>

- <span data-ttu-id="730a5-255">[Rozšíření Docs Markdown pro Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) – pomocí **kombinace alt+M** zobrazíte nabídku možností vytváření dokumentů, jako jsou:</span><span class="sxs-lookup"><span data-stu-id="730a5-255">[Docs Markdown Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) - Use **Alt+M** to bring up a menu of docs authoring options like:</span></span>
   - <span data-ttu-id="730a5-256">Prohledat a odkazovat na obrázky, které jste nahráli.</span><span class="sxs-lookup"><span data-stu-id="730a5-256">Search and reference images you've uploaded.</span></span>
   - <span data-ttu-id="730a5-257">Přidejte formátování, jako jsou seznamy, tabulky a volání specifická pro docs, jako `>[!NOTE]` je .</span><span class="sxs-lookup"><span data-stu-id="730a5-257">Add formatting like lists, tables, and docs-specific call-outs like `>[!NOTE]`.</span></span>
   - <span data-ttu-id="730a5-258">Můžete vyhledávat interní odkazy a záložky a odkazovat na je (odkazy na konkrétní oddíly na stránce).</span><span class="sxs-lookup"><span data-stu-id="730a5-258">Search and reference internal links and bookmarks (links to specific sections within a page).</span></span>
   - <span data-ttu-id="730a5-259">Chyby formátování jsou zvýrazněné (pokud se chcete dozvědět více, najeďte myší na chybu).</span><span class="sxs-lookup"><span data-stu-id="730a5-259">Formatting errors are highlighted (hover your mouse over the error to learn more).</span></span>
- <span data-ttu-id="730a5-260">[Kontrola pravopisu kódu](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) – chybně napsaná slova budou podtržena. klikněte pravým tlačítkem na chybně napsané slovo a změňte ho nebo ho uložte do slovníku.</span><span class="sxs-lookup"><span data-stu-id="730a5-260">[Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) - misspelled words will be underlined; right-click on a misspelled word to change it or save it to the dictionary.</span></span>
