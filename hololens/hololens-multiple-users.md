---
title: Sdílení HoloLens s více lidmi
description: Můžete nakonfigurovat HoloLens pro sdílení pomocí více účtů Azure Active Directory nebo více uživatelů, kteří používají jeden účet.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 39de72bb704ff500b0262f2268d003a08d520eb2
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377646"
---
# <a name="share-your-hololens-with-multiple-people"></a>Sdílení HoloLens s více lidmi

Je běžné sdílet jeden HoloLens s mnoha lidmi nebo mít mnoho lidí, kteří sdílejí sadu zařízení HoloLens.  Tento článek popisuje různé způsoby, kterými můžete sdílet zařízení.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Sdílení s více lidmi, z nichž každý používá vlastní účet

**Předpoklad**: na zařízení HoloLens musí běžet Windows 10 verze 1803 nebo novější.  HoloLens (1. generace) je také potřeba [upgradovat na Windows holografick pro firmy](hololens-upgrade-enterprise.md).

Když používají vlastní účty Azure Active Directory (Azure AD), může každý z nich na zařízení uchovávat vlastní uživatelská nastavení a uživatelská data.

Aby bylo zajištěno, že více lidí bude moci na HoloLens používat vlastní účty, postupujte podle těchto kroků a proveďte jejich konfiguraci:

1. Ujistěte se, že na zařízení běží Windows 10 verze 1803 nebo novější.
   > [!IMPORTANT]
   > Pokud používáte zařízení HoloLens (1. gen), [upgradujte zařízení na Windows holografick pro firmy](hololens1-upgrade-enterprise.md).
1. Když zařízení nastavíte, vyberte možnost **Moje práce nebo škola, kterou vlastní** , a přihlaste se pomocí účtu Azure AD.
1. Po dokončení instalace se ujistěte, že nastavení účtu (**Nastavení**  >  **účty**) obsahuje **Další uživatele**.

Chcete-li použít HoloLens, každý uživatel provede následující kroky:

1. Pokud zařízení používal jiný uživatel, proveďte jednu z následujících akcí:
   - Pokud chcete přejít na úsporný režim, stiskněte tlačítko napájení a potom se stisknutím tlačítka napájení vraťte na zamykací obrazovku.
   - Uživatelé HoloLens 2 mohou vybrat dlaždici uživatele z nabídky Start pro odhlášení aktuálního uživatele.

1. Přihlaste se k zařízení pomocí svých přihlašovacích údajů k účtu Azure AD.  
    Pokud zařízení používáte poprvé, budete muset použít [kalibraci](hololens-calibration.md) HoloLens na vaše vlastní oči.

Pokud chcete zobrazit seznam uživatelů zařízení nebo odebrat uživatele ze zařízení, přejděte na **Nastavení**  >  **účty**  >  **ostatní uživatelé**.

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Sdílet s více lidmi a používat stejný účet

Zařízení HoloLens může sdílet několik uživatelů i při použití jediného uživatelského účtu.

Když **na HoloLens 2** nový uživatel umístí zařízení do svého hlavního umístění (při současném zachování stejného účtu), zařízení vyzve nového uživatele k rychlému kalibraci a přizpůsobení prostředí pro zobrazení. Zařízení může ukládat informace o kalibraci, takže v budoucnu může zařízení automaticky optimalizovat kvalitu a pohodlí možností zobrazení jednotlivých uživatelů. Uživatelé nepotřebují zařízení znovu kalibrovat.

**V případě HoloLens (1. generace)** budou muset uživatelé sdílející účet požádat o rekalibraci v aplikaci nastavení.  Přečtěte si další informace o [kalibraci](hololens-calibration.md).
