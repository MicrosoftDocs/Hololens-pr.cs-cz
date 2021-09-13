---
title: Pokyny k přispívání
description: Zjistěte, jak přispívat do HoloLens dokumentů na docs.microsoft.com platformě pomocí GitHub Markdownu.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: d511156d6940574deda7448a6f634c0004b8f053
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032172"
---
# <a name="contributing-to-the-hololens-documentation"></a>Přispívání do HoloLens dokumentace

Vítá vás dokumentace [HoloLens.](https://github.com/MicrosoftDocs/Hololens) Všechny články, které v tomto repo vytvoříte nebo upravíte, **budou viditelné pro veřejnost.** 

HoloLens dokumentace se zobrazují na docs.microsoft.com platformě, která používá GitHub Markdown s funkcemi Markdigu. Obsah, který v tomto repo upravíte, se naformátuje na stylizované stránky, které se zobrazí na /hololens.

Tato stránka popisuje základní kroky a pokyny pro přispívání a odkazy na základy Markdownu. Děkujeme za váš příspěvek!

## <a name="available-repos"></a>Dostupná úložiště

| Název úložiště | URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Hybridní realita | [MicrosoftDocs/hybridní realita](/windows/mixed-reality) |
| Průvodce nadšenci VR | [MicrosoftDocs/mixed-reality/enthusiast-guide](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a>Než začnete

Pokud ho ještě nemáte, budete si muset vytvořit účet [GitHub .](https://github.com/join)

>[!NOTE]
>Pokud jste zaměstnancem Microsoftu, propoejte svůj GitHub s aliasem Microsoftu na portálu [Microsoft Open Source.](https://repos.opensource.microsoft.com/) Připojte **se k organizacím Microsoft** a **MicrosoftDocs.**

Při nastavování GitHub účtu doporučujeme také tato bezpečnostní opatření:
- Vytvořte silné [heslo pro svůj GitHub účet](https://github.com/settings/admin).
- Povolte [dvojfaktorové ověřování](https://github.com/settings/two_factor_authentication/configure).
- Kódy pro [obnovení uložte](https://github.com/settings/auth/recovery-codes) na bezpečném místě.
- Aktualizujte [nastavení veřejného profilu.](https://github.com/settings/profile)
   - Nastavte své jméno a zvažte nastavení veřejného *e-mailu* na *Nez zobrazení mé e-mailové adresy*.
   - Doporučujeme nahrát profilový obrázek, protože se na stránkách dokumentace, na které přispíváte, zobrazuje miniatura.
- Pokud máte v plánu použít příkazový řádek, zvažte nastavení [gitu Správce přihlašovacích údajů pro Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest). Tímto způsobem nebudete muset zadávat heslo pokaždé, když přispíváte.

Systém publikování je svázán s GitHub, takže tyto kroky jsou důležité. Budete uvedeni jako autor nebo přispěvatel každého článku pomocí vašeho aliasu GitHub článku.

## <a name="editing-an-existing-article"></a>Úprava existujícího článku

Pomocí následujícího pracovního postupu můžete provádět aktualizace *existujícího* článku GitHub ve webovém prohlížeči:

1. Přejděte do článku, který chcete upravit, ve složce mixed-reality-docs.

2. V pravém horním rohu vyberte tlačítko pro úpravy (ikona tužky).

   ![Úprava článku](images/editpage.png)

   Tím se automaticky vytvoří fork jednodušné větve z výchozí větve _master_.

   > [!NOTE]
   > Tento článek obsahuje odkazy na _hlavní výraz_, který microsoft už používá. Když se termín odebere ze softwaru, odebereme ho z tohoto článku.
   
3. Upravte obsah článku podle základních [informací o Markdownu.](#markdown-basics)

4. Aktualizujte metadata v horní části každého článku:

   * **title**: Název stránky, který se zobrazí na kartě prohlížeče při prohlížení článku. Názvy stránek se používají pro SEO a indexování, proto ho neměňte, pokud to není nutné (i když je to méně důležité, než se dokumentace zveřejní).
   * **description**: Napište stručný popis obsahu článku, který zvýší SEO a zjišťování.
   * **author**(autor): Pokud jste primárním vlastníkem stránky, přidejte sem svůj GitHub alias.
   * **ms.author:** Pokud jste primárním vlastníkem stránky, přidejte sem svůj alias Microsoftu (nepotřebujete @microsoft.com jenom alias).
   * **ms.date:** Aktualizujte datum, pokud na stránku přidáváte hlavní obsah, ale ne pro opravy, jako je objasnění, formátování, gramatika nebo pravopis.
   * **keywords**: Keywords aid in SEO (search engine optimization). Přidejte klíčová slova oddělená čárkou a mezerou, která jsou specifická pro váš článek, ale žádná interpunkce za posledním klíčovým slovem v seznamu. Nemusíte přidávat globální klíčová slova, která se vztahují na všechny články, protože se spravují jinde. 
   
5. Po dokončení úprav článku se posuňte dolů a vyberte **Propose file change (Navrhnout změnu souboru).**

6. Na další stránce vyberte Create **pull request (Vytvořit** žádost o vyžádání) a sloučí se automaticky vytvořená větev do výchozí větve _master_.

7. Opakujte výše uvedené kroky pro další článek, který chcete upravit.

## <a name="renaming-or-deleting-an-existing-article"></a>Přejmenování nebo odstranění existujícího článku

Pokud vaše změna přejmenuje nebo odstraní existující článek, nezapomeňte přidat přesměrování. Každý, kdo má odkaz na existující článek, tak bude pořád na správném místě. Přesměrování spravuje soubor .openpublishing.redirection.json v kořenovém adresáři repo.

Pokud chcete přidat přesměrování na .openpublishing.redirection.json, přidejte do pole `redirections` záznam:

```json
{
    "redirections": [
        {
            "source_path": "hololens/old-article.md",
            "redirect_url": "new-article#section-about-old-topic",
            "redirect_document_id": false
        },
```

- `source_path`je relativní cesta úložiště ke starému článku, který odebíráte. Ujistěte se, že cesta začíná na a `mixed-reality-docs` končí na `.md` .

- `redirect_url`je relativní veřejná adresa URL ze starého článku do nového článku. Ujistěte se, **že tato adresa** URL neobsahuje nebo , protože odkazuje na veřejnou adresu `mixed-reality-docs` `.md` URL, a ne cestu k úložišti. Odkazování na oddíl v novém článku pomocí je `#section` povolené. V případě potřeby můžete také použít absolutní cestu k jiné lokalitě.

- `redirect_document_id` určuje, jestli chcete zachovat ID dokumentu z předchozího souboru. Výchozí formát je `false`. Tuto `true` možnost použijte, pokud chcete zachovat `ms.documentid` hodnotu atributu z přesměrovaných článku. Pokud zachováte ID dokumentu, data, jako jsou zobrazení stránek a hodnocení, se přenesou do cílového článku. Proveďte to v případě, že je přesměrování primárně přejmenování, a nikoli ukazatel na jiný článek, který pokrývá pouze část stejného obsahu.

Pokud přidáte přesměrování, nezapomeňte odstranit i starý soubor.

## <a name="creating-a-new-article"></a>Vytvoření nového článku

Pomocí následujícího pracovního postupu *můžete vytvářet nové články* v GitHub ve webovém prohlížeči:

1. Vytvořte fork z výchozí větve _master_ pro MicrosoftDocs/mixed-reality pomocí tlačítka **Fork** v pravém horním rohu.

   ![Rozvětvení výchozí větve, aktuálně s názvem "master".](images/forkbranch.png)

   > [!NOTE]
   > Tento článek obsahuje odkazy na _hlavní výraz_, který microsoft už používá. Když se termín odebere ze softwaru, odebereme ho z tohoto článku.
   
2. Ve složce mixed-reality-docs vyberte **vpravo** nahoře Vytvořit nový soubor.

3. Vytvořte název stránky článku (místo mezer použijte spojovníky a nepoužívejte interpunkci ani apostrofy) a připojte ".md".

   ![Pojmete novou stránku.](images/newpagetitle.png)
   
   >[!IMPORTANT]
   >Nezapomeňte vytvořit nový článek ze složky mixed-reality-docs. Můžete to ověřit tak, že na novém řádku názvu souboru najdete /mixed-reality-docs/.

4. Do horní části nové stránky přidejte následující blok metadat:

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

5. Vyplňte příslušná pole metadat, jak je popsáno výše v [části Úprava existujícího článku.](#editing-an-existing-article)

6. Napište obsah článku s využitím [základů Markdownu.](#markdown-basics)

7. Do dolní `## See also` části článku přidejte oddíl s odkazy na další relevantní články.

8. Po dokončení vyberte **Commit new file (Potvrdit nový soubor).**

9. Vyberte **New pull request (Nová**  žádost o stažení) a sloučíte hlavní větev vašeho forku do MicrosoftDocs/mixed-reality _master_ (ujistěte se, že šipka ukazuje na správný cíl).

   ![Vytvořte žádost o stažení z forku do MicrosoftDocs/mixed-reality.](images/pr-to-master.png)

## <a name="markdown-basics"></a>Základy formátu Markdown

Následující zdroje informací vám pomůžou naučit se upravovat dokumentaci pomocí jazyka Markdown:

- [Základy formátu Markdown](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [Další materiály pro psaní Markdownu pro docs.microsoft.com](/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a>Přidání tabulek

Vzhledem ke způsobu, docs.microsoft.com styly tabulek, nebudou mít ohraničení ani vlastní styly, i když zkusíte vložené šablony stylů CSS. Bude se zdát, že bude fungovat po krátkou dobu, ale platforma nakonec styl z tabulky vypadne. Proto si naplánujte dopředu a udržujte tabulky jednoduché. Tady je web, který usnadňuje tabulky Markdownu: [Tables Generator]] ( https://www.tablesgenerator.com/markdown_tables) .

Rozšíření [Docs Markdown pro Visual Studio Code](/teamblog/docs-extension) také usnadňuje generování tabulek, pokud k úpravám dokumentace používáte Visual Studio Code [(viz](#using-visual-studio-code) níže).

### <a name="adding-images"></a>Přidání obrázků

Obrázky budete muset nahrát do složky mixed-reality-docs/images v tomto umístění a pak na ně odpovídajícím způsobem odkazovat v článku. Obrázky se automaticky zobrazí v plné velikosti, což znamená, že velké obrázky vyplní celou šířku článku. Před nahráním obrázků doporučujeme předem nastavit jejich velikost. Doporučená šířka je 600 až 700 pixelů, ale pokud se jedná o hustotu snímku obrazovky nebo zlomek snímku obrazovky, měli byste velikost nahoru nebo dolů.

>[!IMPORTANT]
>Obrázky můžete do svého forku uložit jenom před sloučením. Pokud tedy plánujete přidat obrázky do článku, budete muset pomocí [nástroje Visual Studio Code](#using-visual-studio-code) nejprve přidat obrázky do složky "images" forku nebo se ujistit, že jste ve webovém prohlížeči provedli následující:
>
>1. Fork v repo MicrosoftDocs/mixed-reality.
>2. Upravoval jste článek ve forku.
>3. Nahráli jste obrázky, na které ve svém článku odkazujete, do složky mixed-reality-docs/images ve forku.
>4. Vytvořili jste **žádost o stažení** pro sloučení vašeho forku do hlavní větve MicrosoftDocs/mixed-reality. 
>
>Pokud chcete zjistit, jak nastavit vlastní roz fork, postupujte podle pokynů k [vytvoření nového článku.](#creating-a-new-article)

## <a name="previewing-your-work"></a>Náhled práce

Při úpravách GitHub ve webovém prohlížeči můžete vybrat kartu **Náhled** v horní části stránky a před potvrzením zobrazit náhled své práce. 

>[!NOTE]
>Náhled změn na webu review.docs.microsoft.com je k dispozici pouze zaměstnancům Microsoftu.

Zaměstnanci Microsoftu: Když se vaše příspěvky sloučí do výchozí větve _master,_ můžete obsah zkontrolovat předtím, než se zveřejní na adrese </hololens?branch=master>. Článek najdete pomocí obsahu v levém sloupci.

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a>Úpravy v prohlížeči vs. úpravy pomocí desktopových klientů

Úpravy v prohlížeči jsou nejjednodušším způsobem, jak provést rychlé změny, ale má to několik nevýhod:

- Kontrola pravopisu se vám neschová.
- Inteligentní propojení s jinými články se nezískající (název souboru článku musíte zadat ručně).
- Nahrávání obrázků a odkazování na obrázky může být obměná.

Pokud se těmto problémům těmto problémům chytáte, použijte desktopového klienta, jako [je Visual Studio Code](https://code.visualstudio.com/) s [několika](#useful-extensions) užitečnými rozšířeními při přispívání.

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

Pomocí následujícího pracovního postupu můžete provádět změny v dokumentaci s Visual Studio Code:

>[!NOTE]
>Všechny pokyny k [úpravám](#editing-an-existing-article) a vytváření [článků](#creating-a-new-article) a základní informace o úpravě [Markdownu](#markdown-basics)uvedené výše platí i při Visual Studio Code jazyce.

1. Ujistěte se, že je naklonovaný fork aktuální s oficiálním repo.

   1. Ve webovém prohlížeči vytvořte žádost o stažení pro synchronizaci nedávných změn od ostatních přispěvatelů ve výchozí větvi MicrosoftDocs/mixed-reality _master_ do vašeho forku (ujistěte se, že šipka ukazuje na správný cíl).
      
      ![Synchronizace změn z MicrosoftDocs/hybridní reality do forku](images/sync-repos.png)
      
   2. V Visual Studio Code tlačítkem Synchronizovat synchronizujte aktuální fork s místním klonem.
      
      ![Klikněte na obrázek tlačítka Synchronizovat.](images/sync-clone.png)
      
2. Články můžete vytvářet nebo upravovat v naklonovaném Visual Studio Code.

   1. Upravte jeden nebo více článků (v případě potřeby přidejte obrázky do složky images).
   
   2. **Uložte** změny v **Průzkumníku**.
      
      ![V Průzkumníku zvolte Uložit vše.](images/explorer-save.png)
      
   3. **Potvrďte všechny** změny ve **zdrojovém kódu** (po zobrazení výzvy zapište zprávu potvrzení).
   
      ![Volba možnosti Potvrdit vše ve správy zdrojového kódu](images/source-control-commit.png)
      
   4. Výběrem **tlačítka synchronizovat** synchronizujte změny zpět do původního zdroje (váš fork na GitHub).
      
      ![Klikněte na tlačítko Synchronizovat.](images/sync-back.png)
      
3. Ve webovém prohlížeči vytvořte žádost o stažení pro synchronizaci nových změn ve forku zpět do MicrosoftDocs/hlavního hlavního serveru hybridní _reality_ (ujistěte se, že šipka ukazuje na správný cíl).

   ![Vytvořte žádost o stažení z forku do MicrosoftDocs/mixed-reality.](images/pr-to-master.png)

### <a name="useful-extensions"></a>Užitečná rozšíření

Při úpravách Visual Studio Code jsou užitečná následující rozšíření:

- [Rozšíření Docs Markdown pro Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) – pomocí **kombinace alt+M** zobrazíte nabídku možností vytváření dokumentů, jako jsou:
   - Prohledat a odkazovat na obrázky, které jste nahráli.
   - Přidejte formátování, jako jsou seznamy, tabulky a volání specifická pro docs, jako `>[!NOTE]` je .
   - Můžete vyhledávat interní odkazy a záložky a odkazovat na je (odkazy na konkrétní oddíly na stránce).
   - Chyby formátování jsou zvýrazněné (pokud se chcete dozvědět víc, najeďte myší na chybu).
- [Kontrola pravopisu kódu](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) – chybně napsaná slova budou podtržena. klikněte pravým tlačítkem na chybně napsané slovo a změňte ho nebo ho uložte do slovníku.
