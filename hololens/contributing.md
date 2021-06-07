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
# <a name="contributing-to-the-hololens-documentation"></a>Přispívání do dokumentace k HoloLens

Vítejte v [dokumentaci k HoloLens](https://github.com/MicrosoftDocs/Hololens). Všechny články, které v tomto úložišti vytváříte nebo upravujete, **budou přístupné veřejnosti.** 

Dokumenty HoloLens se zobrazují na platformě docs.microsoft.com, která využívá Markdownu s funkcemi Markdig s využitím GitHubu. Obsah, který upravíte v tomto úložišti, se naformátuje na stylizované stránky, které se zobrazují na https://docs.microsoft.com/hololens . 

Tato stránka obsahuje základní kroky a pokyny pro přispívání a odkazy na základy Markdownu. Děkujeme za váš příspěvek!

## <a name="available-repos"></a>Dostupná úložiště

| Název úložiště | URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Hybridní realita | [MicrosoftDocs/Mixed – realita](https://docs.microsoft.com/windows/mixed-reality) |
| Průvodce nadšenci VR | [MicrosoftDocs/smíšený – realita/patříte mezi fanoušky – příručka](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a>Než začnete

Pokud ho ještě nemáte, budete muset [vytvořit účet GitHub](https://github.com/join).

>[!NOTE]
>Pokud jste zaměstnancem Microsoftu, propojte svůj účet GitHub s aliasem Microsoftu na [portálu Microsoft Open Source Portal](https://repos.opensource.microsoft.com/). Připojte se ke organizacím **"Microsoft"** a **"MicrosoftDocs"** .

Při nastavování účtu GitHub doporučujeme také tato bezpečnostní opatření:
- Vytvořte [pro svůj účet GitHub silné heslo](https://github.com/settings/admin).
- Povolte [dvojúrovňové ověřování](https://github.com/settings/two_factor_authentication/configure).
- Uložte si [kódy obnovení](https://github.com/settings/auth/recovery-codes) na bezpečné místo.
- Aktualizujte [Nastavení veřejného profilu](https://github.com/settings/profile).
   - Nastavte své jméno a zvažte nastavení *veřejného e-mailu* , aby se *nezobrazovala e-mailová adresa*.
   - Doporučujeme nahrát profilový obrázek, protože Miniatura se zobrazuje na stránkách docs, na které přispějete.
- Pokud plánujete použití příkazového řádku, zvažte nastavení [Správce přihlašovacích údajů Git pro Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest). Tímto způsobem nebudete muset zadávat heslo pokaždé, když provedete příspěvek.

Systém publikování je svázán s GitHubem, takže tyto kroky jsou důležité. Pomocí vašeho aliasu GitHubu budete mít k jednotlivým článkům v seznamu buď autora, nebo přispěvatele.

## <a name="editing-an-existing-article"></a>Úprava existujícího článku

Pomocí následujícího pracovního postupu můžete provést aktualizace *existujícího článku* přes GitHub ve webovém prohlížeči:

1. Ve složce Mixed-reality-docs přejděte k článku, který chcete upravit.

2. V pravém horním rohu vyberte tlačítko Upravit (ikona tužky), které bude automaticky rozvětvit větev mimo hlavní větev.

   ![Upravit článek.](images/editpage.png)
   
3. Upravte obsah článku podle [tématu základní informace o Markdownu](#markdown-basics).

4. Aktualizujte metadata v horní části každého článku:

   * **title**: nadpis stránky, který se zobrazí na kartě prohlížeče při prohlížení článku. Nadpisy stránek se používají pro SEO a indexování, takže neměňte název, pokud není potřeba (ale to je méně důležité, než se dokumentace zveřejní).
   * **Popis**: Napište stručný popis obsahu článku, který zvyšuje SEO a zjišťování.
   * **Autor**: Pokud jste primárním vlastníkem stránky, přidejte sem svůj alias GitHubu.
   * **MS. Author**: Pokud jste primárním vlastníkem stránky, přidejte sem svůj alias Microsoftu (nepotřebujete @microsoft.com , jenom alias).
   * **MS. Date**: aktualizujte datum, pokud přidáváte hlavní obsah stránky, ale ne pro opravy, jako je například vyjasnění, formátování, gramatika nebo pravopis.
   * **klíčová slova**: pomocná klíčová slova v SEO (optimalizace vyhledávacích strojů). Přidejte klíčová slova, která jsou oddělená čárkou a mezerou, která jsou specifická pro váš článek, ale za poslední klíčová slova v seznamu se nezaokrouhlí žádné interpunkční znaménko. Nemusíte přidávat globální klíčová slova, která platí pro všechny články, protože jsou spravovaná jinde. 
   
5. Až dokončíte úpravy článků, přejděte dolů a vyberte **navrhnout změnu souboru**.

6. Na další stránce vyberte **vytvořit žádost o získání dat** a slučte automaticky vytvořenou větev do hlavního.

7. Opakujte výše uvedené kroky pro další článek, který chcete upravit.

## <a name="renaming-or-deleting-an-existing-article"></a>Přejmenování nebo odstranění existujícího článku

Pokud vaše změna přejmenuje nebo odstraní existující článek, nezapomeňte přidat přesměrování. Tím se na správném místě pořád ukončí kdokoli s odkazem na stávající článek. Přesměrování se spravují pomocí .openpublishing.redirection.jsv souboru v kořenovém adresáři úložiště.

Chcete-li přidat přesměrování na .openpublishing.redirection.jsna, přidejte do pole položku `redirections` :

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- `source_path`Je relativní cesta úložiště ke starému článku, který odebíráte. Ujistěte se, že cesta začíná `mixed-reality-docs` a končí na `.md` .

- `redirect_url`Je relativní veřejná adresa URL od starého článku k novému článku. Ujistěte se, že tato **Adresa URL neobsahuje** `mixed-reality-docs` nebo `.md` , jak odkazuje na veřejnou adresu URL, a ne na cestu k úložišti. Odkaz na oddíl v rámci nového článku pomocí `#section` je povolen. V případě potřeby můžete také použít absolutní cestu k jinému webu.

- `redirect_document_id` Určuje, zda chcete zachovat ID dokumentu z předchozího souboru. Výchozí formát je `false`. Použijte, `true` Pokud chcete zachovat `ms.documentid` hodnotu atributu z přesměrovaného článku. Pokud zachováte ID dokumentu, data, jako jsou například zobrazení stránky a klasifikace, budou přenesena do cílového článku. Udělejte to, pokud je přesměrování primárně přejmenováno, a ne ukazatel na jiný článek, který se vztahuje pouze na část stejného obsahu.

Pokud přidáte přesměrování, nezapomeňte odstranit i starý soubor.

## <a name="creating-a-new-article"></a>Vytváření nového článku

Pomocí následujícího pracovního postupu můžete *vytvářet nové články* v úložišti dokumentace přes GitHub ve webovém prohlížeči:

1. Vytvořte rozvětvení s větví "Master" MicrosoftDocs/Mixed-reality (pomocí tlačítka **rozvětvení** v pravém horním rohu).

   ![Rozvětvení hlavní větve](images/forkbranch.png)
   
2. Ve složce Mixed-reality-docs vyberte **vytvořit nový soubor** v pravém horním rohu.

3. Vytvořte název stránky pro článek (místo mezer použijte spojovníky a nepoužívejte interpunkci nebo apostrofy) a přidejte ". MD".

   ![Pojmenujte novou stránku.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   >Ujistěte se, že jste nový článek vytvořili ze složky "Mixed-reality-docs". To můžete ověřit zaškrtnutím "/Mixed-reality-docs/" v novém řádku s názvem souboru.

4. V horní části nové stránky přidejte následující blok metadat:

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

5. Vyplňte příslušná pole metadat podle pokynů v [části výše](#editing-an-existing-article).

6. Zápis obsahu článků pomocí [základů Markdownu](#markdown-basics)

7. Přidejte do `## See also` dolní části článku část s odkazy na další relevantní články.

8. Po dokončení vyberte **Potvrdit nový soubor**.

9. Vyberte **Nová žádost o** přijetí změn a slučte "hlavní" větev svého rozvětvení do MicrosoftDocs/smíšené-reality "Master" (Ujistěte se, že šipka ukazuje správný způsob).

   ![Vytvoření žádosti o přijetí změn z větve do MicrosoftDocs/smíšené reality](images/pr-to-master.png)

## <a name="markdown-basics"></a>Základy formátu Markdown

Následující materiály vám pomůžou naučit se, jak upravovat dokumentaci pomocí jazyka Markdownu:

- [Základy formátu Markdown](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [Další zdroje informací pro zápis Markdownu pro docs.microsoft.com](https://docs.microsoft.com/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a>Přidávání tabulek

Vzhledem k tomu, že tabulky stylů docs.microsoft.com, nemají ohraničení ani vlastní styly, ani když se pokusíte o vloženou šablonu stylů CSS. Zdá se, že bude fungovat po krátké době, ale nakonec bude tato platforma oddělit styly z tabulky. Proto Plánujte dopředu a udržujte své tabulky jednoduché. [Tady je web, který usnadňuje Markdownu tabulek](https://www.tablesgenerator.com/markdown_tables).

[Rozšíření docs Markdownu pro Visual Studio Code](https://docs.microsoft.com/teamblog/docs-extension) také usnadňuje generování tabulek, pokud používáte [Visual Studio Code (viz níže)](#using-visual-studio-code) , chcete-li upravit dokumentaci.

### <a name="adding-images"></a>Přidávání imagí

Vaše image budete muset nahrát do složky "Mixed-realit-docs/images" v úložišti a pak je podle potřeby odkázat v článku. Obrázky se automaticky zobrazí v plné velikosti, což znamená, že velké obrázky budou vyplnit celou šířku článku. Před odesláním imagí doporučujeme předem nastavovat jejich změny. Doporučená šířka je mezi 600 a 700 pixelů, ale pokud se jedná o hustý snímek obrazovky nebo zlomek snímku obrazovky, měli byste velikost navýšit nebo snížit.

>[!IMPORTANT]
>Obrázky můžete do svého forku nahrát jenom před sloučením. Pokud tedy plánujete přidat obrázky do článku, budete muset pomocí [nástroje Visual Studio Code](#using-visual-studio-code) nejprve přidat obrázky do složky "images" forku nebo se ujistit, že jste ve webovém prohlížeči provedli následující:
>
>1. Fork je v microsoftdocs/hybridním reality.
>2. Upravoval jste článek ve forku.
>3. Nahráli jste obrázky, na které odkazujete ve svém článku, do složky mixed-reality-docs/images ve forku.
>4. Vytvořili jste **žádost o stažení** pro sloučení vašeho forku do hlavní větve MicrosoftDocs/mixed-reality.
>
>Pokud chcete zjistit, jak nastavit vlastní roz fork, postupujte podle pokynů k [vytvoření nového článku.](#creating-a-new-article)

## <a name="previewing-your-work"></a>Náhled práce

Při úpravách na GitHubu prostřednictvím webového prohlížeče můžete vybrat kartu **Náhled** v horní části stránky a před potvrzením zobrazit náhled své práce. 

>[!NOTE]
>Náhled změn na webu review.docs.microsoft.com je k dispozici pouze zaměstnancům Microsoftu.

Zaměstnanci Microsoftu: Po sloučení příspěvků do hlavní větve můžete obsah zkontrolovat předtím, než se zveřejní na https://review.docs.microsoft.com/hololens?branch=master adrese . Najděte svůj článek pomocí obsahu v levém sloupci.

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a>Úpravy v prohlížeči vs. úpravy pomocí desktopových klientů

Úpravy v prohlížeči jsou nejjednodušším způsobem, jak provést rychlé změny, ale má to několik nevýhod:

- Kontrola pravopisu se vám neschová.
- S jinými články nemáte žádné inteligentní propojení (název souboru článku musíte zadat ručně).
- Nahrávání obrázků a odkazování na obrázky může být problém.

Pokud se těmto problémům těmto problémům chytáte raději, použijte desktopového klienta, jako [je Visual Studio Code](https://code.visualstudio.com/) s [několika](#useful-extensions) užitečnými rozšířeními při přispívání.

## <a name="using-visual-studio-code"></a>Používání nástroje Visual Studio Code

Z důvodů uvedených [výše](#editing-in-the-browser-vs-editing-with-a-desktop-client)můžete preferovat použití desktopových klientů k úpravám dokumentace místo webového prohlížeče. Doporučujeme použít [Visual Studio Code](https://code.visualstudio.com/).

### <a name="setup"></a>Nastavení

Postupujte podle těchto kroků a Visual Studio Code pro práci s tímto repo:

1. Ve webovém prohlížeči:
    1. Nainstalujte [git pro svůj počítač.](https://git-scm.com/downloads)
    2. Nainstalujte [Visual Studio Code](https://code.visualstudio.com/).
    3. [Fork MicrosoftDocs/mixed-reality,](#creating-a-new-article) pokud jste to ještě neudělali.
    4. Ve forku vyberte Clone **or download (Klonovat nebo stáhnout)** a zkopírujte adresu URL.
2. Vytvořte místní klon forku v Visual Studio Code:
    1. V **nabídce View** (Zobrazení) vyberte **Command Palette (Paleta příkazů).**
    2. Napište Git: Clone.
    3. Vložte zkopírované adresy URL.
    4. Zvolte, kam chcete klon uložit do počítače.
    5. V místní nabídce vyberte Open **repo** (Otevřít repo).

### <a name="editing-documentation"></a>Úprava dokumentace

Pomocí následujícího pracovního postupu můžete provádět změny v dokumentaci pomocí Visual Studio Code:

>[!NOTE]
>Všechny pokyny k [úpravám](#editing-an-existing-article) a vytváření [článků](#creating-a-new-article) a základy úprav [Markdownu](#markdown-basics)uvedené výše platí i při Visual Studio Code kódu.

1. Ujistěte se, že je naklonovaný fork aktuální s oficiálním repo.

   1. Ve webovém prohlížeči vytvořte žádost o stažení, která synchronizuje nedávné změny od ostatních přispěvatelů v MicrosoftDocs nebo hlavní realitě do vašeho forku (ujistěte se, že šipka ukazuje správným směrem).
      
      ![Synchronizace změn z MicrosoftDocs/hybridní reality do forku](images/sync-repos.png)
      
   2. V Visual Studio Code tlačítko Synchronizovat, aby se nový aktualizovaný fork synchronizoval s místním klonem.
      
      ![Klikněte na obrázek tlačítka Synchronizace.](images/sync-clone.png)
      
2. Články můžete vytvářet nebo upravovat v naklonovaném Visual Studio Code.

   1. Upravte jeden nebo více článků (v případě potřeby přidejte obrázky do složky images).
   
   2. **Uložte** změny v **Průzkumníku**.
      
      ![V Průzkumníku zvolte Uložit vše.](images/explorer-save.png)
      
   3. **Potvrďte všechny** změny ve **zdrojovém kódu** (po zobrazení výzvy zapište zprávu potvrzení).
   
      ![Volba možnosti Potvrdit vše ve správy zdrojového kódu](images/source-control-commit.png)
      
   4. Výběrem **tlačítka synchronizovat** synchronizujte změny zpět do původního zdroje (váš fork na GitHubu).
      
      ![Klikněte na tlačítko Synchronizovat.](images/sync-back.png)
      
3. Ve webovém prohlížeči vytvořte žádost o stažení pro synchronizaci nových změn ve forku zpět do MicrosoftDocs/master hybridní reality (ujistěte se, že šipka ukazuje správným způsobem).

   ![Vytvoření žádosti o stažení z forku do MicrosoftDocs/mixed-reality](images/pr-to-master.png)

### <a name="useful-extensions"></a>Užitečná rozšíření

Při úpravách Visual Studio Code jsou užitečná následující rozšíření:

- [Rozšíření Docs Markdown pro Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) – pomocí **kombinace alt+M** zobrazíte nabídku možností vytváření dokumentů, jako jsou:
   - Prohledat a odkazovat na obrázky, které jste nahráli.
   - Přidejte formátování, jako jsou seznamy, tabulky a volání specifická pro docs, jako `>[!NOTE]` je .
   - Můžete vyhledávat interní odkazy a záložky a odkazovat na je (odkazy na konkrétní oddíly na stránce).
   - Chyby formátování jsou zvýrazněné (pokud se chcete dozvědět více, najeďte myší na chybu).
- [Kontrola pravopisu kódu](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) – chybně napsaná slova budou podtržena. klikněte pravým tlačítkem na chybně napsané slovo a změňte ho nebo ho uložte do slovníku.
