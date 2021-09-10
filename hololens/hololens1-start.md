---
title: nastavit HoloLens (1. generace)
description: naučte se, jak nastavit HoloLens (první gen) po prvním Wi-Fi síti pomocí účtu Microsoft (MSA) nebo Azure Active Directory (AAD).
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
ms.openlocfilehash: 06b7142be471d0db3f45812654288a33425abd60
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124426987"
---
# <a name="set-up-your-hololens-1st-gen"></a>nastavení HoloLens (1. generace)

při prvním zapnutí HoloLens vás provede kalibrací zařízení, nastavením zařízení a přihlašováním.  tento článek vás provede procesem prvního spuštění HoloLens (1. generace) a možností nastavení.

v další části se dozvíte, jak pracovat s HoloLens a pracovat s hologramy. pokud chcete přejít k tomuto článku, přečtěte si téma začínáme [s HoloLens (1. generace)](hololens1-basic-usage.md).

## <a name="before-you-start"></a>Než začnete

Než začnete, ujistěte se, že máte k dispozici následující:

**Wi-Fi připojení**. k jejímu nastavení budete muset připojit HoloLens k Wi-Fi síti. Při prvním připojení budete potřebovat otevřenou síť chráněnou heslem, která nevyžaduje navigaci na web nebo použití certifikátů k připojení. [přečtěte si další informace o webech, které HoloLens používá](hololens-offline.md).

**Účet Microsoft nebo pracovní účet**. Budete taky muset použít účet Microsoft (nebo pracovní účet, pokud vaše organizace vlastní zařízení), aby se přihlásil k HoloLens. Pokud nemáte účet Microsoft, navštivte [account.Microsoft.com](https://account.microsoft.com) a nastavte si ho zdarma.

**Bezpečný a dobře osvětlený prostor bez Trip nebezpečí**. [Stav a bezpečnostní údaje](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**volitelná pomůcka pro pohodlí** , která byla dodávána s vaším HoloLens, aby vám pomohla lépe se přizpůsobit. [Další informace o přizpůsobení a pohodlí](https://support.microsoft.com/help/12632/hololens-fit-your-hololens).

> [!NOTE]
>  
> - při prvním použití HoloLens je už [Cortana](hololens-cortana.md) zapnutá a připravená k provedení průvodce (i když na vaše otázky nebudete moct reagovat až po nastavení zařízení). Cortana můžete kdykoliv zapnout v nastavení Cortana.
> - chcete-li přepnout na čínskou nebo japonskou verzi HoloLens, budete muset stáhnout sestavení pro jazyk na počítači a pak ho nainstalovat do HoloLens. další informace najdete v tématu [instalace lokalizovaných verzí HoloLens (1. generace)](hololens1-install-localized.md).

## <a name="start-your-hololens-and-set-up-windows"></a>Zahajte HoloLens a nastavte Windows

při prvním spuštění HoloLens je vaším prvním úkolem nastavení Windows holografické na zařízení.

1. Připojení k internetu (HoloLens vás, abyste vybrali Wi-Fi síť).

1. Přihlaste se ke svému uživatelskému účtu. Výběr mezi **pracovními nebo školními úkoly** a jejich **vlastním** vlastníkem
    - Když zvolíte **Moje práce nebo škola**, přihlásíte se pomocí účtu Azure AD. pokud vaše organizace používá Azure AD Premium a nakonfigurovali automatickou registraci MDM, HoloLens se automaticky zaregistrují v mdm. pokud vaše organizace nepoužívá Azure AD Premium, automatická registrace MDM není k dispozici, takže budete muset [HoloLens zaregistrovat do správy zařízení ručně](hololens-enroll-mdm.md#different-ways-to-enroll). Pokud se chcete k zařízení přihlásit poprvé pomocí pracovního nebo školního účtu, postupujte podle těchto kroků:
        1. Zadejte informace o účtu organizace.
        1. Přijměte prohlášení o zásadách ochrany osobních údajů.
        1. Přihlaste se pomocí svých přihlašovacích údajů Azure AD. To se může přesměrovat na přihlašovací stránku vaší organizace.
        1. Pokračujte v nastavování zařízení.
    - Když si vyberete **vlastní IT**, přihlásíte se pomocí účet Microsoft. po dokončení instalace můžete [HoloLens ručně zaregistrovat do správy zařízení](hololens-enroll-mdm.md#different-ways-to-enroll).
        1. Zadejte informace o účet Microsoft.
        1. Zadejte svoje heslo. Pokud vaše účet Microsoft vyžaduje [dvoustupňové ověřování (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), dokončete proces ověření.

1. Zařízení nastaví vaše časové pásmo na základě informací, které získá z Wi-Fi sítě.

## <a name="calibration"></a>Kalibrace

po Cortana zavádíme další krok nastavení kalibrace. pro nejlepší HoloLens prostředí byste měli během instalace dokončit proces kalibrace.

HoloLens (1. generace) využívá vzdálenost mezi žákům (IPD nebo [interpupillary](https://en.wikipedia.org/wiki/Interpupillary_distance)), aby byly hologramy jasné a snadno interaktivní. Pokud není IPD správné, můžou se zdát, že se zdají být nestabilní nebo mají nesprávnou vzdálenost.

během kalibrace HoloLens požádá o zarovnání prstu s řadou šesti cílů na oči. HoloLens tento proces používá k nastavení správného IPD pro vaši oči. Pokud musí být kalibrace aktualizována nebo upravena pro nového uživatele, může nový uživatel spustit aplikaci kalibrace mimo instalační program.

![IPD prst – obrazovka zarovnání v druhém kroku.](./images/ipd-finger-alignment-300px.jpg)

*IPD prst – obrazovka zarovnání v druhém kroku*

Gratulujeme! Instalace je hotova a můžete začít používat HoloLens.

## <a name="next-steps"></a>Další kroky

> [!div class="nextstepaction"]
> [začínáme s HoloLens (1. generace)](hololens1-basic-usage.md)
