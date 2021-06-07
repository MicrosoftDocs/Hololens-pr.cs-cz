---
title: Nastavení HoloLens (1. generace)
description: Naučte se, jak nastavit HoloLens (1.1. generace) po prvním Wi-Fi síti pomocí účtu Microsoft (MSA) nebo Azure Active Directory (AAD).
ms.assetid: 0136188e-1305-43be-906e-151d70292e87
ms.prod: hololens
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.date: 8/12/2019
manager: jarrettr
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: f0ec62e55f15fda6d5a8304ea2bb77039d644b9e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377601"
---
# <a name="set-up-your-hololens-1st-gen"></a>Nastavení HoloLens (1. generace)

Při prvním zapnutí HoloLens se vám provede kalibrací zařízení, nastavení zařízení a přihlašování.  Tento článek vás provede procesem prvního spuštění HoloLens (1. generace) a prostředím nastavení.

V další části se dozvíte, jak pracovat s HoloLens a pracovat s hologramy. Pokud chcete přejít k tomuto článku, přečtěte si téma Začínáme [s HoloLens (1. generace)](hololens1-basic-usage.md).

## <a name="before-you-start"></a>Než začnete

Než začnete, ujistěte se, že máte k dispozici následující:

**Wi-Fi připojení**. K jeho nastavení budete muset připojit svůj HoloLens k síti Wi-Fi. Při prvním připojení budete potřebovat otevřenou síť chráněnou heslem, která nevyžaduje navigaci na web nebo použití certifikátů k připojení. [Přečtěte si další informace o webech, které využívá HoloLens](hololens-offline.md).

**Účet Microsoft nebo pracovní účet**. Budete taky muset použít účet Microsoft (nebo pracovní účet, pokud vaše organizace vlastní zařízení), abyste se přihlásili k HoloLens. Pokud nemáte účet Microsoft, navštivte [account.Microsoft.com](https://account.microsoft.com) a nastavte si ho zdarma.

**Bezpečný a dobře osvětlený prostor bez Trip nebezpečí**. [Stav a bezpečnostní údaje](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**Volitelná pomůcka pro pohodlí** , která byla dodána s vaším hololensm, aby vám pomohla lépe přizpůsobenému potřebám. [Další informace o přizpůsobení a pohodlí](https://support.microsoft.com/help/12632/hololens-fit-your-hololens).

> [!NOTE]
>  
> - Při prvním použití HoloLens je [Cortana](hololens-cortana.md) už zapnutá a připravený, aby vás provedl (i když nebude moct reagovat na vaše otázky až po nastavení zařízení). Cortana můžete kdykoliv vypnout v nastaveních Cortany.
> - Aby bylo možné přepnout na čínskou nebo japonskou verzi HoloLens, budete muset stáhnout sestavení pro jazyk na počítači a pak ho nainstalovat na HoloLens. Další informace najdete v tématu [instalace lokalizovaných verzí HoloLens (1. generace)](hololens1-install-localized.md).

## <a name="start-your-hololens-and-set-up-windows"></a>Zahajte HoloLens a nastavte Windows.

Při prvním spuštění HoloLens je vaším prvním úkolem, jak na zařízení nastavit Windows holografické.

1. Připojte se k Internetu (pomocí Průvodce HoloLens můžete vybrat Wi-Fi síť).

1. Přihlaste se ke svému uživatelskému účtu. Výběr mezi **pracovními nebo školními úkoly** a jejich **vlastním** vlastníkem
    - Když zvolíte **Moje práce nebo škola**, přihlásíte se pomocí účtu Azure AD. Pokud vaše organizace používá Azure AD Premium a nakonfigurovala automatickou registraci MDM, HoloLens se automaticky zaregistruje v MDM. Pokud vaše organizace nepoužívá Azure AD Premium, Automatická registrace MDM není k dispozici, takže budete muset do [správy zařízení ručně zaregistrovat HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll). Pokud se chcete k zařízení přihlásit poprvé pomocí pracovního nebo školního účtu, postupujte podle těchto kroků:
        1. Zadejte informace o účtu organizace.
        1. Přijměte prohlášení o zásadách ochrany osobních údajů.
        1. Přihlaste se pomocí svých přihlašovacích údajů Azure AD. To se může přesměrovat na přihlašovací stránku vaší organizace.
        1. Pokračujte v nastavování zařízení.
    - Když si vyberete **vlastní IT**, přihlásíte se pomocí účet Microsoft. Až se instalace dokončí, můžete [do správy zařízení ručně zaregistrovat HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll).
        1. Zadejte informace o účet Microsoft.
        1. Zadejte svoje heslo. Pokud vaše účet Microsoft vyžaduje [dvoustupňové ověřování (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), dokončete proces ověření.

1. Zařízení nastaví vaše časové pásmo na základě informací, které získá z Wi-Fi sítě.

## <a name="calibration"></a>Kalibrace

Jakmile Cortana zaznamená, že je dalším krokem nastavení kalibrace. Pro nejlepší prostředí HoloLens byste měli během instalace dokončit proces kalibrace.

HoloLens (1. generace) využívá vzdálenost mezi žákům (IPD nebo [interpupillary](https://en.wikipedia.org/wiki/Interpupillary_distance)), aby bylo možné hologramy vymazat a snadno pracovat s nimi. Pokud není IPD správné, můžou se zdát, že se zdají být nestabilní nebo mají nesprávnou vzdálenost.

Během kalibrace se zaměřuje na to, abyste přirovnali prst k řadě šesti cílů na oči. HoloLens používá tento proces k nastavení správného IPD pro vaši oči. Pokud musí být kalibrace aktualizována nebo upravena pro nového uživatele, může nový uživatel spustit aplikaci kalibrace mimo instalační program.

![IPD prst – obrazovka zarovnání v druhém kroku](./images/ipd-finger-alignment-300px.jpg)

*IPD prst – obrazovka zarovnání v druhém kroku*

Gratulujeme! Instalace je hotova a můžete začít používat HoloLens.

## <a name="next-steps"></a>Další kroky

> [!div class="nextstepaction"]
> [Začínáme s HoloLens (1. generace)](hololens1-basic-usage.md)
