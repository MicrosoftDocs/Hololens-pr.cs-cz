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
# <a name="global-assigned-access--kiosk"></a>Globální přiřazený přístup – Beziosk

Tato funkce konfiguruje zařízení HoloLens 2 pro režim veřejného terminálů s více aplikacemi, který je použitelný na úrovni systému, nemá žádné spřažení s žádnou identitou v systému a vztahuje se na všechny uživatele, kteří se k zařízení přihlásí.

> [!NOTE]
> Tato funkce je aktuálně dostupná pouze v Windows Insider sestaveních. Pokud chcete tuto funkci vyzkoušet dříve, než je všeobecně dostupná v verzích HoloLens, přečtěte si další informace [o Windows Insider](hololens-insider.md) sestavení.

## <a name="how-to-use-global-assigned-access-in-intune"></a>Jak používat globální přiřazený přístup v Intune?

> [!NOTE]
> Mějte na paměti oblasti označené <!-. Tyto oblasti budou vyžadovat, abyste na základě svých preferencí úpravy úpravy úpravy.

1. Následujícím způsobem vytvořte vlastní konfigurační profil zařízení OMA URI a použijte ho pro skupinu zařízení HoloLens:

    Hodnota identifikátoru URI: ./Device/Vendor/MSFT/AssignedAccess/Configuration

    > [!div class="mx-imgBorder"]
    > ![OMA-URI pro globálně přiřazený přístup v Intune](images/global-assigned-access-omauri.png)

2. Jako hodnotu aktualizujte a vložte následující obsah:

    :::code language="xml" source="samples/global-assigned-access.xml" highlight="12-13,23":::

## <a name="how-to-use-global-assigned-access-in-windows-configuration-designer"></a>Jak používat globální přiřazený přístup v nástroji Windows Configuration Designer?

1. Aktualizujte a uložte objekt blob XML uvedený výše jako soubor XML. 

2. Postupujte podle kroků v části Použití zřizovacího balíčku [k](https://docs.microsoft.com/hololens/hololens-kiosk#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)nastavení veřejného terminálu s jednou nebo více aplikacemi, konkrétně v části "Prov". package, krok 2 – přidejte soubor XML konfigurace veřejného terminálů do zřizovacího balíčku a odkazujte na soubor XML, který jste uložili v předchozím kroku.

## <a name="can-i-create-a-configuration-where-global-applies-to-everyone-and-separate-configuration-applies-to-1-azure-ad-account-or-azure-ad-group"></a>Můžu vytvořit konfiguraci, ve které globální platí pro všechny a samostatná konfigurace se vztahuje na 1 účet Azure AD nebo skupinu Azure AD? 

Ano, podívejte se na příklad objektu blob XML níže. Profil globálního přiřazeného přístupu se na HoloLens použije, když se pro přihlášeného uživatele nenalezne konkrétní profil, takže se jedná o výchozí konfiguraci režimu veřejného terminálů pro přihlášeného uživatele.
Tady je příklad použití objektu blob XML:

> [!NOTE]
> Mějte na paměti zvýrazněné oblasti označené `<!-` . Tyto oblasti budou vyžadovat, abyste na základě svých preferencí úpravy úpravy úpravy.

 :::code language="xml" source="samples/exclude-one-aad-user-or-group.xml" highlight="8,11,17":::

## <a name="excluding-deviceowners-from-global-assigned-access-profile"></a>Vyloučení vlastníků zařízení z globálního přiřazeného přístupového profilu

Tato funkce umožňuje vyloučit uživatele, který je na HoloLens považován za vlastníka zařízení, z globálního přiřazeného přístupu.[](security-adminless-os.md) Pokud chcete tuto funkci využít, v objektu blob XML pro konfiguraci veřejného terminálů s více aplikacemi se ujistěte, že jsou přidané zvýrazněné řádky:

 :::code language="xml" source="samples/exclude-device-owners-from-global.xml" highlight="6,16-18":::

## <a name="additional-global-assigned-access-examples"></a>Další příklady globálního přiřazeného přístupu

Toto je příklad veřejného terminálu s globálním přiřazeným přístupem, který bude mít, když se přihlásí nějaký uživatel, pomocí aplikace Nastavení, aplikace nastavení a Centrum Feedback a Microsoft Edge.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access.xml":::

Tento příklad je veřejného terminálu s globálním přiřazeným přístupem, který vyloučí vlastníka zařízení, když se přihlásí jakýkoli jiný uživatel Azure AD, bude mít kiosk s více aplikacemi pomocí aplikace nastavení, Centrum Feedback a Microsoft Edge. Tento bezobrazovk zahrnuje také sekundární konfiguraci veřejného terminálů pro účet Návštěvník, ke kterému se může na zamykací obrazovce zaregistrovat kdokoli. Když se uživatel přihlásí k účtu Návštěvník, bude mít kiosk s více aplikacemi, který má jenom Centrum Feedback aplikace.

:::code language="xml" source="samples/kiosk-sample-global-assigned-access-visitor-exclude.xml":::
