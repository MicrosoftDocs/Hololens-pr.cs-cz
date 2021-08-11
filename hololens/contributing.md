---
title: Pokyny k přispívání
description: Zjistěte, jak přispívat do HoloLens dokumentů na docs.microsoft.com platformě pomocí GitHub Markdownu.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: cbf0b2e4b61f006d0b5d7d74d3d81a4b33cfd6d8c2e124288b17959d54a5a1ad
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665026"
---
# <a name="contributing-to-the-hololens-documentation"></a>Přispívání do HoloLens dokumentace

Vítá vás dokumentace [HoloLens.](https://github.com/MicrosoftDocs/Hololens) Všechny články, které v tomto repo vytvoříte nebo upravíte, **budou viditelné pro veřejnost.** 

HoloLens dokumentace se zobrazují na docs.microsoft.com platformě, která používá GitHub Markdown s funkcemi Markdigu. Obsah, který v tomto repo budete upravovat, se naformátuje na stylizované stránky, které se zobrazí na adrese /hololens.

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
   - Nastavte své jméno a zvažte nastavení veřejného *e-mailu* na *Nez zobrazení mé e-mailové adresy.*
   - Doporučujeme nahrát profilový obrázek, protože miniatura se zobrazuje na stránkách dokumentace, na které přispíváte.
- Pokud máte v plánu použít příkazový řádek, zvažte nastavení [gitu Správce přihlašovacích údajů pro Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest). Tímto způsobem nebudete muset zadávat heslo pokaždé, když přispíváte.

Systém publikování je svázán s GitHub, takže tyto kroky jsou důležité. Budete uvedeni jako autor nebo přispěvatel každého článku pomocí vašeho aliasu GitHub článku.

## <a name="editing-an-existing-article"></a>Úprava existujícího článku

Pomocí následujícího pracovního postupu proveďte aktualizace *existujícího* článku prostřednictvím GitHub ve webovém prohlížeči:

1. Přejděte do článku, který chcete upravit, ve složce mixed-reality-docs.

2. V pravém horním rohu vyberte tlačítko pro úpravy (ikona tužky).

   ![Úprava článku](images/editpage.png)

   Tím se automaticky vytvoří fork jednodušné větve z výchozí větve _master_.

   > [!NOTE]
   > Tento článek obsahuje odkazy na _hlavní název_, termín, který microsoft už používá. Když se termín odebere ze softwaru, odebereme ho z tohoto článku.
   
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

Pokud vaše změna přejmenuje nebo odstraní existující článek, nezapomeňte přidat přesměrování. Každý, kdo má odkaz na existující článek, tak bude pořád na správném místě. Přesměrování spravuje soubor .openpublishing.redirection.jsv kořenovém adresáři tohoto repo.

Pokud chcete přidat přesměrování .openpublishing.redirection.js, přidejte do pole `redirections` položku :

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

- `redirect_url`je relativní veřejná adresa URL ze starého článku do nového článku. Ujistěte se, že **tato adresa** URL neobsahuje nebo , protože odkazuje na veřejnou `mixed-reality-docs` adresu `.md` URL, a ne na cestu k úložišti. Odkazování na oddíl v novém článku pomocí je `#section` povolené. V případě potřeby můžete také použít absolutní cestu k jiné lokalitě.

- `redirect_document_id` určuje, jestli chcete zachovat ID dokumentu z předchozího souboru. Výchozí formát je `false`. Pokud `true` chcete zachovat hodnotu atributu z `ms.documentid` přesměrovaných článku, použijte . Pokud zachováte ID dokumentu, data, jako jsou zobrazení stránek a hodnocení, se přenesou do cílového článku. Proveďte to v případě, že je přesměrování primárně přejmenování, a nikoli ukazatel na jiný článek, který pokrývá pouze část stejného obsahu.

Pokud přidáte přesměrování, nezapomeňte odstranit i starý soubor.

## <a name="creating-a-new-article"></a>Vytvoření nového článku

Pomocí následujícího pracovního postupu *můžete vytvářet nové články* v GitHub ve webovém prohlížeči:

1. Vytvořte fork z výchozí větve _master_ pro MicrosoftDocs/mixed-reality pomocí tlačítka **Fork** v pravém horním rohu.

   ![Rozvětvení výchozí větve, aktuálně s názvem "master".](images/forkbranch.png)

   > [!NOTE]
   > Tento článek obsahuje odkazy na _hlavní název_, termín, který microsoft už používá. Když se termín odebere ze softwaru, odebereme ho z tohoto článku.
   
2. Ve složce mixed-reality-docs vyberte **vpravo** nahoře Vytvořit nový soubor.

3. Vytvořte název stránky článku (místo mezer použijte spojovníky a nepoužívejte interpunkci ani apostrofy) a připojte ".md".

   ![Pojmechte novou stránku.](images/newpagetitle.png)
   
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

   ![Vytvoření žádosti o stažení z forku do MicrosoftDocs/mixed-reality](images/pr-to-master.png)

## <a name="markdown-basics"></a>Základy formátu Markdown

Následující zdroje informací vám pomůžou naučit se upravovat dokumentaci pomocí jazyka Markdown:

- [Základy formátu Markdown](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [Další materiály pro psaní Markdownu pro docs.microsoft.com](/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a>Přidání tabulek

Vzhledem ke způsobu, docs.microsoft.com styly tabulek, nebudou mít ohraničení ani vlastní styly, i když zkusíte vložené šablony stylů CSS. Bude to vypadat, že bude fungovat po krátkou dobu, ale platforma nakonec styl z tabulky vypadne. Proto si naplánujte dopředu a udržujte tabulky jednoduché. Tady je web, který usnadňuje tabulky Markdownu: [Tables Generator]] ( https://www.tablesgenerator.com/markdown_tables) .

Rozšíření [Docs Markdown pro Visual Studio Code](/teamblog/docs-extension) také usnadňuje generování tabulek, pokud k úpravám dokumentace používáte Visual Studio Code [(viz](#using-visual-studio-code) níže).

### <a name="adding-images"></a>Přidávání imagí

Vaše image budete muset nahrát do složky "Mixed-realit-docs/images" v úložišti a pak je podle potřeby odkázat v článku. Obrázky se automaticky zobrazí v plné velikosti, což znamená, že velké obrázky budou vyplnit celou šířku článku. Před odesláním imagí doporučujeme předem nastavovat jejich změny. Doporučená šířka je mezi 600 a 700 pixelů, ale pokud se jedná o hustý snímek obrazovky nebo zlomek snímku obrazovky, měli byste velikost navýšit nebo snížit.

>[!IMPORTANT]
>Před sloučením můžete do rozvětvené úložiště nahrávat jenom obrázky. takže pokud plánujete přidání imagí k článku, budete muset [použít Visual Studio Code](#using-visual-studio-code) k prvnímu přidání imagí do složky "image" vašeho rozvětvení, nebo se ujistěte, že jste ve webovém prohlížeči provedli následující:
>
>1. Bylo rozvětvené úložiště MicrosoftDocs/Mixed-realita.
>2. Úprava článku ve větvi.
>3. Nahráli jsme obrázky, na které odkazujete ve svém článku, do složky "Mixed-reality-docs/images" ve vašem rozvětvení.
>4. Vytvořili jste **žádost** o přijetí změn pro sloučení vašeho rozvětvení do _hlavní_ větve MicrosoftDocs/Mixed-reality.
>
>Pokud se chcete dozvědět, jak nastavit vlastní rozvětvené úložiště, postupujte podle pokynů pro [Vytvoření nového článku](#creating-a-new-article).

## <a name="previewing-your-work"></a>Náhled práce

při úpravách v GitHub přes webový prohlížeč můžete vybrat kartu **náhled** v horní části stránky a zobrazit náhled práce před potvrzením. 

>[!NOTE]
>Náhled změn v review.docs.microsoft.com je k dispozici pouze zaměstnancům společnosti Microsoft.

Zaměstnanci Microsoftu: po sloučení vašich příspěvků do výchozí větve si můžete obsah prohlédnout před tím, než bude _veřejný, na_</HoloLens? větev = hlavní>. Vyhledejte svůj článek pomocí obsahu v levém sloupci.

## <a name="editing-in-the-browser-vs-editing-with-a-desktop-client"></a>Úpravy v prohlížeči vs. úpravy pomocí desktopového klienta

Úpravou v prohlížeči je nejjednodušší způsob, jak provádět rychlé změny, ale existuje několik nevýhod:

- Nezískáte kontrolu pravopisu.
- Nezískáte žádné inteligentní propojení s jinými články (musíte ručně zadat název souboru článku).
- Je možné, že budete mít na starosti nahrávání a odkazování imagí.

pokud byste s těmito problémy nechtěli, použijte desktopového klienta, jako je [Visual Studio Code](https://code.visualstudio.com/) s několika [užitečnými rozšířeními](#useful-extensions) při přispívání.

## <a name="using-visual-studio-code"></a>Používání nástroje Visual Studio Code

Z [výše](#editing-in-the-browser-vs-editing-with-a-desktop-client)uvedených důvodů můžete preferovat použití desktopového klienta k úpravám dokumentace místo webového prohlížeče. doporučujeme použít [Visual Studio Code](https://code.visualstudio.com/).

### <a name="setup"></a>Nastavení

pomocí těchto kroků nakonfigurujete Visual Studio Code pro práci s tímto úložištěm:

1. Ve webovém prohlížeči:
    1. Nainstalujte [si Git pro váš počítač](https://git-scm.com/downloads).
    2. nainstalujte [Visual Studio Code](https://code.visualstudio.com/).
    3. [Rozvětvení MicrosoftDocs/Mixed – realita](#creating-a-new-article) , pokud jste to ještě neudělali.
    4. V rozvětvení vyberte **klonovat nebo stáhnout** a zkopírujte adresu URL.
2. Vytvořte místní klon svého rozvětvení v Visual Studio Code:
    1. V nabídce **zobrazení** vyberte **paleta příkazů**.
    2. Zadejte git: Clone.
    3. Vložte adresu URL, kterou jste zkopírovali.
    4. Určete, kam se má na svém počítači uložit klon.
    5. V automaticky otevíraném okně vyberte **Otevřít úložiště** .

### <a name="editing-documentation"></a>Úprava dokumentace

K provedení změn v dokumentaci pomocí Visual Studio Code použijte následující pracovní postup:

>[!NOTE]
>všechny doprovodné materiály k [úpravám](#editing-an-existing-article) a [vytváření](#creating-a-new-article) článků a [základní informace o úpravách markdownu](#markdown-basics)se vztahují i na použití Visual Studio Code.

1. Ujistěte se, že je naklonované rozvětvení aktuální s oficiálním úložištěm.

   1. Ve webovém prohlížeči vytvořte žádost o přijetí změn, která synchronizuje poslední změny od ostatních přispěvatelů ve výchozí větvi MicrosoftDocs/Mixed-reality, _Master_, do vašeho rozvětvení (Ujistěte se, že šipka odkazuje na správný cíl).
      
      ![Synchronizace změn z MicrosoftDocs/smíšené reality do rozvětvení](images/sync-repos.png)
      
   2. v Visual Studio Code vyberte tlačítko synchronizovat pro synchronizaci aktualizovaného rozvětvení s místním klonem.
      
      ![Klikněte na obrázek tlačítka synchronizace.](images/sync-clone.png)
      
2. Vytvořte nebo upravte články v klonovaném úložišti pomocí Visual Studio Code.

   1. Úprava jednoho nebo více článků (Pokud je to nutné, přidejte obrázky do složky "image").
   
   2. **Uložte** změny v **Průzkumníkovi**.
      
      ![Výběr možnosti Uložit vše v Průzkumníkovi](images/explorer-save.png)
      
   3. **Potvrďte všechny** změny ve **správě zdrojového kódu** (po zobrazení výzvy zapsat zprávu potvrzení).
   
      ![Výběr možnosti potvrdit vše ve zdrojovém řízení](images/source-control-commit.png)
      
   4. Kliknutím na tlačítko **synchronizovat** synchronizujete změny zpět do původního umístění (vaše rozvětvení na GitHub).
      
      ![Klikněte na tlačítko synchronizovat.](images/sync-back.png)
      
3. Ve webovém prohlížeči vytvořte žádost o přijetí změn, která synchronizuje nové změny v rozvětvení zpátky do MicrosoftDocs/Mixed _-reality (_ Ujistěte se, že šipka odkazuje na správný cíl).

   ![Vytvoření žádosti o přijetí změn z větve do MicrosoftDocs/smíšené reality](images/pr-to-master.png)

### <a name="useful-extensions"></a>Užitečná rozšíření

následující rozšíření Visual Studio Code jsou užitečná při úpravách dokumentace:

- [rozšíření docs markdownu pro Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) – pomocí **Alt + M** zobrazíte nabídku možností vytváření dokumentů, jako je:
   - Hledání a referenční obrázky, které jste nahráli.
   - Přidejte formátování, jako jsou seznamy, tabulky a volání specifické pro dokumentaci `>[!NOTE]` .
   - Vyhledat a odkazovat na interní odkazy a záložky (odkazy na konkrétní oddíly na stránce).
   - Chyby formátování jsou zvýrazněné (Další informace získáte najetím myši na chybu).
- [Kontrola pravopisu kódu](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) – slova s chybným pravopisem budou podtržena; Klikněte pravým tlačítkem na nesprávně napsané slovo, které chcete změnit, nebo ho uložte do slovníku.
