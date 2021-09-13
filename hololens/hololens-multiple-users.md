---
title: sdílení HoloLens s více lidmi
description: můžete nakonfigurovat, aby HoloLens sdíleli více účtů Azure Active Directory, nebo více uživatelů, kteří používají jeden účet.
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e3acd2665e93e44bce2c5dad467c825dc768bfed
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032407"
---
# <a name="share-your-hololens-with-multiple-people"></a>sdílení HoloLens s více lidmi

## <a name="overview"></a>Přehled
firmy často investují do mnoha sdílených HoloLens zařízení. způsob použití HoloLens je flexibilní v závislosti na jednotlivých požadavcích. Tady je příklad některých prostředí pro více uživatelů: 

- zařízení, kterým se účtují, a s příručkami k Dynamics 365 a umožňují vašim zaměstnancům otevřít aplikaci Nastavení, aby bylo možné Wi-Fi potřebovat, ale zásady viditelnosti stránky Nastavení umožňují omezit stránky množství, které jsou k dispozici v aplikaci Nastavení.
- Zařízení, která jsou pro vzdálenou pomoc, a vaši podnikovou aplikaci, která je pronajatá ostatním společnostem. Tato zařízení mají veřejné terminály, které obsahují jenom vaši aplikaci a vzdálenou pomoc. WDAC se používá k udržení Nastavení aplikace a Microsoft Edge spuštění. Součástí pronájmu je sada baterií USB-C, která zachová zařízení v plné výši přes několik posunů.
- Všechna vaše zařízení se nastavují pro účely autopilotu a stahují všechny aplikace vaší společnosti. Nastavili jste několik různých profilů veřejného terminálu, které cílí na různé skupiny Azure AD. každý uživatel se do HoloLens přihlásí pomocí klíčů FIDO2 a přihlašuje se k vlastnímu účtu Azure AD a zobrazí se s přizpůsobeným prostředím.



## <a name="share-with-multiple-people-each-using-their-own-account"></a>Sdílení s více lidmi, z nichž každý používá vlastní účet

**předpoklad**: HoloLens zařízení musí běžet Windows 10 verze 1803 nebo novější.  HoloLens (1. generace) je také potřeba [upgradovat na Windows Holographic for Business](hololens-upgrade-enterprise.md).

když používají vlastní účty Azure Active Directory (Azure AD), může každý z nich na zařízení uchovávat vlastní uživatelská nastavení a uživatelská data.

chcete-li zajistit, aby více uživatelů mohl používat vlastní účty v HoloLens, postupujte podle těchto pokynů:

1. ujistěte se, že je na zařízení spuštěný Windows 10 verze 1803 nebo novější.
   > [!IMPORTANT]
   > pokud používáte zařízení HoloLens (1. generace), [upgradujte zařízení na Windows Holographic for Business](hololens1-upgrade-enterprise.md).
1. Když zařízení nastavíte, vyberte možnost **Moje práce nebo škola, kterou vlastní** , a přihlaste se pomocí účtu Azure AD.
1. po dokončení instalace se ujistěte, že nastavení účtu (**Nastavení**  >  **účty**) obsahuje **další uživatele**.

pokud chcete použít HoloLens, bude každý uživatel postupovat podle těchto kroků:

1. Pokud zařízení používal jiný uživatel, vyberte jednu z následujících možností:
   - Pokud chcete přejít na úsporný režim, stiskněte tlačítko napájení a potom se stisknutím tlačítka napájení vraťte na zamykací obrazovku.
   - HoloLens 2 uživatelé mohou k odhlášení aktuálního uživatele vybrat dlaždici uživatele z nabídka Start.

1. Přihlaste se k zařízení pomocí svých přihlašovacích údajů k účtu Azure AD.  
    pokud se zařízení poprvé používá, musíte ho [kalibrovat](hololens-calibration.md) HoloLens na své vlastní oči.

pokud chcete zobrazit seznam uživatelů zařízení nebo odebrat uživatele ze zařízení, přejděte na **Nastavení**  >  **účty**  >  **ostatní uživatelé**.

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Sdílet s více lidmi a používat stejný účet

zařízení HoloLens může sdílet několik uživatelů při použití jediného uživatelského účtu.

**v HoloLens 2** se při prvním vložení zařízení do svého hlavního umístění (při zachování stejného účtu) vyzve zařízení nového uživatele k rychlému kalibraci a přizpůsobení prostředí pro zobrazení. Zařízení může ukládat informace o kalibraci, takže v budoucnu může zařízení automaticky optimalizovat kvalitu a pohodlí možností zobrazení jednotlivých uživatelů. Uživatelé nepotřebují zařízení znovu kalibrovat.

**v HoloLens (1. generace)** budou muset uživatelé sdílející účet požádat o rekalibraci v aplikaci Nastavení.  Přečtěte si další informace o [kalibraci](hololens-calibration.md).