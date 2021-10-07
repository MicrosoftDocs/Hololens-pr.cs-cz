---
title: Sdílení vašich HoloLens s více lidmi
description: Můžete nakonfigurovat, HoloLens sdílet více Azure Active Directory účty, nebo více uživateli, kteří používají jeden účet.
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/23/2021
ms.reviewer: anisgup
manager: sean-kerawala
appliesto:
- HoloLens 2
ms.openlocfilehash: bbb955edaa500187ea921538291bb1c7bda05422
ms.sourcegitcommit: be1393d24a98381e37bd1f56183c1f381f87cbd4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/06/2021
ms.locfileid: "129600725"
---
# <a name="share-your-hololens-with-multiple-people"></a>Sdílení vašich HoloLens s více lidmi

## <a name="overview"></a>Přehled

Firmy často investují do mnoha sdílených HoloLens zařízení. Způsob použití HoloLens je flexibilní napříč platformou v závislosti na vašich individuálních požadavcích. Tady je příklad několika uživatelských prostředí:

- Vozový park HoloLens 2 je nastavený prostřednictvím Windows Autopilot pro HoloLens 2 s konzistentním portfoliem firemních aplikací na každém zařízení. Nastavili jste několik různých profilů veřejného terminálu, které cílí na různé skupiny Azure AD. Každý uživatel se přihlásí do HoloLens pomocí klíčů FIDO2 a přihlásí se ke svému vlastnímu účtu Azure AD a zobrazí se přizpůsobené prostředí.
- Nezávislý výrobce softwaru (ISV) pronajímá zařízení HoloLens 2 s D365 Remote Assistem a obchodní aplikací pro společnost zákazníka. Tato zařízení jsou nakonfigurovaná pro terminály, které obsahují jenom obchodní aplikaci a Remote Assist a sdílí je více koncových uživatelů. WdAC slouží k tomu, aby Nastavení aplikace a Microsoft Edge spuštění. Součástí půjčovny je sada baterie USB-C, která uchová zařízení na plný poplatek po několika směnách.
- Koncový uživatel v podniku se pokusí provést úpravy Bluetooth na zařízení, aby mohl připojit nové zařízení, ale je povolená zásada Viditelnost stránky Nastavení, která omezuje zobrazení stránky Zařízení. Mají stále povolený přístup k dalším stránkám podle potřeby, například k Wi-Fi, aby mohli vzdálenou pomoc používat ve více umístěních se stejným HoloLens.

## <a name="best-practices"></a>Osvědčené postupy

Při plánování sdílení zařízení je potřeba vzít v úvahu několik požadavků na optimalizaci prostředí zařízení na základě vašich obchodních potřeb.

- [Identita a ověřování](#identity-and-authentication)
- [Správa zařízení](#device-management)
- [Pokročilá správa zařízení – Kiosk a WDAC](#advanced-device-management---kiosk-and-wdac)
- [Fyzická správa](#physical-management)

### <a name="identity-and-authentication"></a>[Identita a ověřování](hololens-identity.md)

Pokud plánujete mít na zařízení více účtů, budete mít účty Azure AD se všemi režimy ověřování. Tyto metody ověřování budou založené na Windows Hello [,](/windows-hardware/design/device-experiences/windows-hello)včetně klíčů Iris a FIDO2.

- Klíče zabezpečení FIDO 2 jsou vynikající, pokud máte více zařízení, mnoho uživatelů nebo neustále používáte nová zařízení.
- Pokud máte 10 nebo méně uživatelů, Iris je rychlé řešení pro přihlášení uživatelů, kteří se dříve přihlásili ke stejnému zařízení.

### <a name="device-management"></a>[Správa zařízení](hololens-csp-policy-overview.md)

Pokud se zařízení sdílí mezi uživateli, budete pravděpodobně chtít použít omezení zařízení. Pomocí správy zařízení můžete nastavit některé zásady, které uživatelům umožní používat zařízení, spravovat aktualizace nebo omezovat, co zařízení může dělat. Doporučujeme, abyste si projdete [naše běžná omezení zařízení](hololens-common-device-restrictions.md)a viděli, jestli se tato doporučení zdají být vhodná pro vaši organizaci. Jakmile víte, jaké zásady chcete použít, můžete je použít prostřednictvím balíčků [mdm (Endpoint Manager Microsoftu)](hololens-mdm-configure.md) nebo zřizovacími balíčky.

### <a name="advanced-device-management---kiosk-and-wdac"></a>Pokročilá správa zařízení – [Kiosk a](hololens-kiosk.md) [WDAC](windows-defender-application-control-wdac.md)

V některých případech můžete chtít omezit, ke kterým aplikacím mají koncoví uživatelé přístup. V bezobrazovkovém režimu můžete omezit, jaké aplikace se uživatelům zobrazí v nabídce [Start.](hololens-kiosk.md) Kiosk je možné nakonfigurovat tak, aby na základě uživatelů, skupin Azure nebo speciálních typů uživatelů prezentoval různé nabídky Start. takového návštěvníka nebo vyloučení vlastníků zařízení. Můžete zvolit více aplikací nebo jenom jednu aplikaci. Beziosk s více aplikacemi nezabýá spuštění jiné aplikace, takže pokud je k dispozici obchod nebo jiná aplikace, uživatelé mohou stále spustit jinou aplikaci.

Můžete také chtít úplně zastavit spouštění aplikací nebo služeb pomocí [nástroje Windows Defender Application Control (WDAC)](windows-defender-application-control-wdac.md) a omezit tak aplikace. Nástroj WDAC se liší od veřejného terminálu, protože nemění uživatelské rozhraní služby HoloLens ale neumožňuje spuštění blokované aplikace.

[Viditelnost Nastavení je](settings-uri-list.md) další způsob, jak do zařízení přidat omezení. V případě, že potřebujete uživatelům udělit přístup k některým stránkám v aplikaci Nastavení, ale ne všichni můžete k omezení přístupu použít Nastavení Viditelnost. To je užitečné například v případě, že uživatelé potřebují změnit Wi-Fi, ale nechcete, aby měli přístup na stránku Účty.

### <a name="physical-management"></a>Fyzická správa

Při sdílení zařízení mezi více uživateli je třeba vzít v úvahu určité fyzické aspekty.

- Ujistěte se, že se zařízení mezi směnami přebíjejí.
- Pokud je zařízení nutné pro směnu a musí trvat několik směn, zvažte použití externí baterie na začátku směny, zatímco zařízení má stále značný poplatek za řízení směru [heatho připojení](hololens2-charging.md#managing-heat).
- Při ukládání zařízení je udržujte připojená k síti a připojená k síti. Toto je nejlepší způsob, jak zajistit aktualizace operačního systému a aplikací.
- Zvažte, jak chcete [zařízení vyčistit mezi](hololens2-maintenance.md) uživateli.
- V případě zařízení s jedním sdíleným uživatelem, pokud pro jednoho uživatele používáte sdílený PIN kód nebo heslo, neumis použitím PIN kódu nebo hesla na straně zařízení.
- Pro více zařízení s jedním sdíleným uživatelem použijte různé PIN nebo hesla.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Sdílení s více lidmi, z nichž každá používá svůj vlastní účet

Individuální Azure Active Directory (Azure AD) jsou upřednostňovaným a nejbezpečnějším případem použití identity pro HoloLens 2 uživatele. Při použití vlastních účtů Azure AD může více uživatelů na zařízení zachovat vlastní uživatelská nastavení a uživatelská data. Současně může být přihlášen pouze jeden uživatel. Když se uživatel přihlásí, HoloLens předchozího uživatele odsoudí.

Pokud se chcete ujistit, že více lidí může ve vašem účtu HoloLens vlastní účty, nakonfigurujte ho takto:

1. Při nastavení [zařízení vyberte](hololens2-start.md)Můj pracovní nebo **školní** účet vlastní a přihlaste se pomocí účtu Azure AD.
1. Po dokončení nastavení se ujistěte, že nastavení účtu (Nastavení > Účty) zahrnují **ostatní uživatele**.

> [!NOTE]
> Pokud vaše zařízení nebylo nastavené s účtem Azure AD, je potřeba ho resetovat nebo nastavovat [reflashed](hololens-recovery.md) a správně ho nastavit.

Pokud chcete HoloLens, postupujte podle těchto kroků:

1. Pokud zařízení používá jiný uživatel, zvolte jednu z následujících možností:
   - Jednou stiskněte tlačítko napájení, abyste se vrátili do pohotovostního režimu, a pak znovu stiskněte tlačítko napájení, abyste se vrátili na zamykací obrazovku.
   - Vyberte dlaždici uživatele z **nabídka Start** nebo zvolte odhlásit se z nabídky **Napájení** a odhlásit aktuálního uživatele.

1. Pomocí přihlašovacích údajů účtu Azure AD se přihlaste k zařízení.  
    - Pokud zařízení používáte poprvé, zobrazí se vám po vás, abyste si HoloLens na vlastní oči. [](hololens-calibration.md)
    - Pokud jste zařízení používali dříve:
        - [Windows Holographic verze 20H2, build 19041.1128](hololens-release-notes.md#windows-holographic-version-20h2) nebo novější, se displej bezproblémově přizpůsobí kvalitě a pohodlnému prostředí pro sledování.
        - U předchozích sestavení bude potřeba ruční zásah, který vám umožní přizpůsobit se vašim očím.

> [!TIP]
> Pokud se uživatel ještě nepřihlásí k zařízení, zkuste pro rychlejší přihlášení použít jednu z těchto dvou metod:
>
> - **Klíč zabezpečení FIDO 2:** Váš klíč zabezpečení FIDO2 se automaticky rozpozná a uživatel nebude muset zazadat svoje přihlašovací údaje uživatele ani používat MFA. Jedná se o nejrychlejší způsob přihlášení k novému zařízení.
> - **Webové** ověřování: Když se přihlásíte k novému  zařízení, můžete vybrat odkaz Přihlásit se z jiného zařízení, který vygeneruje kód s 9 znaky, který můžete použít v [souboru aka.ms/devicelogin](https://login.microsoftonline.com/common/oauth2/deviceauth) k přihlášení jako uživatel v zařízení, nebo k zadání uživatelského jména a hesla pomocí klávesnice.

Pokud chcete zobrazit seznam uživatelů zařízení nebo uživatele ze zařízení odebrat, přejděte na stránku **Nastavení**  >    >  **Účty Ostatní uživatelé.**

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Sdílení s více lidmi pomocí stejného účtu

Několik uživatelů může také sdílet HoloLens zařízení při použití jednoho uživatelského účtu. I když se uživatelům HoloLens, aby se k zařízení přihlašovali pomocí svých individuálních identit (účtů Azure AD), není to v některých organizacích možné.

K dispozici jsou dvě metody sdíleného zařízení:

- **Více koncových uživatelů sdílí 1** zařízení – HoloLens zařízení je přiděleno k určenému prostoru, kde může zařízení používat libovolný zaměstnanec. Příkladem může být čistá místnost nebo sada pro tekutickou sadu.

- **Více koncových uživatelů sdílejících více** zařízení – HoloLens zařízení jsou ve sdíleném úložišti, kde zaměstnanci mohou používat jakékoli zařízení. Příkladem může být vrtáka na ropu nebo autoprodej nebo autoservis.

Když nový uživatel poprvé nasazovat zařízení a současně zachovat stejný účet přihlášený, vyzve ho k rychlému nastavení a přizpůsobení prostředí pro prohlížení. Zařízení bude ukládat informace o zásobách, aby se automaticky optimalizovala kvalita a komfort pro sledování jednotlivých uživatelů. Uživatelé nebudou muset zařízení znovu nakalibrovat.
