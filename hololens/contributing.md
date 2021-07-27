---
title: Pokyny pro přispívání
description: naučte se, jak přispívat do HoloLens dokumentů na platformě docs.microsoft.com pomocí GitHub s charakterem markdownu.
author: hferrone
ms.author: mattwoj
ms.date: 01/04/2021
ms.topic: article
ms.prod: hololens
ms.openlocfilehash: b1efaa77a4b96ed4b55e84147448cbfbc706d677
ms.sourcegitcommit: 5130823947caffd2a444e9d8fb15cd24cbb6414c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/24/2021
ms.locfileid: "114659110"
---
# <a name="contributing-to-the-hololens-documentation"></a>přispívání do dokumentace k HoloLens

vítejte v [dokumentaci k HoloLens](https://github.com/MicrosoftDocs/Hololens). Všechny články, které v tomto úložišti vytváříte nebo upravujete, **budou přístupné veřejnosti.** 

dokumentace HoloLens se zobrazují na platformě docs.microsoft.com, která GitHub používá markdownu s funkcemi Markdig. Obsah, který upravíte v tomto úložišti, se naformátuje na stylizované stránky, které se zobrazují na/HoloLens.

Tato stránka obsahuje základní kroky a pokyny pro přispívání a odkazy na základy Markdownu. Děkujeme za váš příspěvek!

## <a name="available-repos"></a>Dostupná úložiště

| Název úložiště | URL |
| --- | --- |
| HoloLens | [MicrosoftDocs/HoloLens](https://github.com/MicrosoftDocs/Hololens) |
| Hybridní realita | [MicrosoftDocs/Mixed – realita](/windows/mixed-reality) |
| Průvodce nadšenci VR | [MicrosoftDocs/smíšený – realita/patříte mezi fanoušky – příručka](https://github.com/MicrosoftDocs/mixed-reality/tree/docs/enthusiast-guide) |

## <a name="before-you-start"></a>Než začnete

pokud ho ještě nemáte, budete muset [vytvořit účet GitHub](https://github.com/join).

>[!NOTE]
>pokud jste zaměstnancem microsoftu, propojte svůj účet GitHub s aliasem microsoftu na [portálu microsoft Open Source portal](https://repos.opensource.microsoft.com/). Připojte se ke organizacím **"Microsoft"** a **"MicrosoftDocs"** .

při nastavování účtu GitHub doporučujeme také tato bezpečnostní opatření:
- vytvořte [pro účet GitHub silné heslo](https://github.com/settings/admin).
- Povolte [dvojúrovňové ověřování](https://github.com/settings/two_factor_authentication/configure).
- Uložte si [kódy obnovení](https://github.com/settings/auth/recovery-codes) na bezpečné místo.
- Aktualizujte [Nastavení veřejného profilu](https://github.com/settings/profile).
   - Nastavte své jméno a zvažte nastavení *veřejného e-mailu* , aby se *nezobrazovala e-mailová adresa*.
   - Doporučujeme nahrát profilový obrázek, protože Miniatura se zobrazuje na stránkách docs, na které přispějete.
- Pokud plánujete použití příkazového řádku, zvažte nastavení [Správce přihlašovacích údajů Git pro Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows/releases/latest). Tímto způsobem nebudete muset zadávat heslo pokaždé, když provedete příspěvek.

systém publikování je vázaný na GitHub, takže tyto kroky jsou důležité. pomocí aliasu GitHub budete mít v každém článku možnost autor nebo přispěvatel.

## <a name="editing-an-existing-article"></a>Úprava existujícího článku

pomocí následujícího pracovního postupu proveďte aktualizace *existujícího článku* prostřednictvím GitHub ve webovém prohlížeči:

1. Ve složce Mixed-reality-docs přejděte k článku, který chcete upravit.

2. V pravém horním rohu vyberte tlačítko Upravit (ikona tužky).

   ![Upravit článek.](images/editpage.png)

   Tato akce automaticky rozvětvení větve mimo výchozí větev, _Hlavní_.

   > [!NOTE]
   > Tento článek obsahuje odkazy na _Hlavní_, termín, který už Microsoft nepoužívá. Po odebrání termínu ze softwaru ho odebereme z tohoto článku.
   
3. Upravte obsah článku podle [základních základů pro Markdownu](#markdown-basics).

4. Aktualizujte metadata v horní části každého článku:

   * **title**: nadpis stránky, který se zobrazí na kartě prohlížeče při prohlížení článku. Nadpisy stránek se používají pro SEO a indexování, takže neměňte název, pokud není potřeba (ale to je méně důležité, než se dokumentace zveřejní).
   * **Popis**: Napište stručný popis obsahu článku, který zvyšuje SEO a zjišťování.
   * **autor**: pokud jste primárním vlastníkem stránky, přidejte sem svůj alias GitHub.
   * **MS. Author**: Pokud jste primárním vlastníkem stránky, přidejte sem svůj alias Microsoftu (nepotřebujete @microsoft.com , jenom alias).
   * **MS. Date**: aktualizujte datum, pokud přidáváte hlavní obsah stránky, ale ne pro opravy, jako je například vyjasnění, formátování, gramatika nebo pravopis.
   * **klíčová slova**: pomocná klíčová slova v SEO (optimalizace vyhledávacích strojů). Přidejte klíčová slova, která jsou oddělená čárkou a mezerou, která jsou specifická pro váš článek, ale za poslední klíčová slova v seznamu se nezaokrouhlí žádné interpunkční znaménko. Nemusíte přidávat globální klíčová slova, která platí pro všechny články, protože jsou spravovaná jinde. 
   
5. Až dokončíte úpravy článků, přejděte dolů a vyberte **navrhnout změnu souboru**.

6. Na další stránce vyberte **vytvořit žádost o získání dat** pro sloučení automaticky vytvořené větve do výchozí větve, _hlavní_.

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

pomocí následujícího pracovního postupu můžete *vytvářet nové články* v úložišti dokumentace prostřednictvím GitHub ve webovém prohlížeči:

1. Pomocí tlačítka **rozvětvení** v pravém horním rohu vytvořte rozvětvení s výchozí větví, _Hlavní_ hodnotou MicrosoftDocs/Mixed-realitou.

   ![Rozvětvení výchozí větve, aktuálně pojmenované "Master".](images/forkbranch.png)

   > [!NOTE]
   > Tento článek obsahuje odkazy na _Hlavní_, termín, který už Microsoft nepoužívá. Po odebrání termínu ze softwaru ho odebereme z tohoto článku.
   
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

5. Vyplňte příslušná pole metadat, jak je popsáno výše v části [Úprava existujícího článku](#editing-an-existing-article).

6. Zápis obsahu článků pomocí [základů Markdownu](#markdown-basics)

7. Přidejte do `## See also` dolní části článku část s odkazy na další relevantní články.

8. Po dokončení vyberte **Potvrdit nový soubor**.

9. Vyberte **Nová žádost o** přijetí změn a slučte _hlavní_ větev rozvětvení do _hlavního serveru_ MicrosoftDocs/Mixed-reality (Ujistěte se, že šipka odkazuje na správný cíl).

   ![Vytvoření žádosti o přijetí změn z větve do MicrosoftDocs/smíšené reality](images/pr-to-master.png)

## <a name="markdown-basics"></a>Základy formátu Markdown

Následující materiály vám pomůžou naučit se, jak upravovat dokumentaci pomocí jazyka Markdownu:

- [Základy formátu Markdown](https://help.github.com/articles/basic-writing-and-formatting-syntax/)
- [Další zdroje informací pro zápis Markdownu pro docs.microsoft.com](/contribute/how-to-write-use-markdown)

### <a name="adding-tables"></a>Přidávání tabulek

Vzhledem k tomu, že tabulky stylů docs.microsoft.com, nemají ohraničení ani vlastní styly, ani když se pokusíte o vloženou šablonu stylů CSS. Zdá se, že bude fungovat po krátké době, ale nakonec bude tato platforma oddělit styly z tabulky. Proto Plánujte dopředu a udržujte své tabulky jednoduché. Tady je web, který usnadňuje Markdownu tabulek: [generátor tabulek]] ( https://www.tablesgenerator.com/markdown_tables) .

[rozšíření Docs markdownu pro Visual Studio Code](/teamblog/docs-extension) také usnadňuje generování tabulek, pokud používáte [Visual Studio Code (viz níže)](#using-visual-studio-code) , chcete-li upravit dokumentaci.

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
