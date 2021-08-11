---
title: Sdílení vašich HoloLens s více lidmi
description: Můžete nakonfigurovat, HoloLens sdílet více Azure Active Directory účty, nebo více uživateli, kteří používají jeden účet.
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
ms.openlocfilehash: 821ef2d17531226177e508b1428af82012c16406e9fbce3ed1a5617c767adfe8
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663072"
---
# <a name="share-your-hololens-with-multiple-people"></a>Sdílení vašich HoloLens s více lidmi

Je běžné sdílet jeden HoloLens s mnoha lidmi nebo mít mnoho lidí, kteří sdílejí sadu zařízení HoloLens zařízení.  Tento článek popisuje různé způsoby, jak můžete sdílet zařízení.

## <a name="share-with-multiple-people-each-using-their-own-account"></a>Sdílení s více lidmi, z nichž každá používá svůj vlastní účet

**Požadavek:** HoloLens musí mít Windows 10 verze 1803 nebo novější.  HoloLens (1. generace) je také potřeba [upgradovat na Windows Holographic for Business](hololens-upgrade-enterprise.md).

Když používají vlastní účty Azure Active Directory (Azure AD), může si několik uživatelů na zařízení zachovat vlastní uživatelská nastavení a uživatelská data.

Pokud chcete zajistit, aby více lidí ve vašem účtu mohl používat vlastní HoloLens, nakonfigurujte ho takto:

1. Ujistěte se, že zařízení používá Windows 10 verze 1803 nebo novější.
   > [!IMPORTANT]
   > Pokud používáte zařízení HoloLens (1. generace), [upgradujte](hololens1-upgrade-enterprise.md)ho na Windows Holographic for Business .
1. Při nastavení zařízení vyberte Můj pracovní nebo **školní** účet vlastní a přihlaste se pomocí účtu Azure AD.
1. Po dokončení nastavení se ujistěte, že nastavení účtu (**Nastavení**  >  **Účty**) zahrnuje **ostatní uživatele**.

Pokud chcete HoloLens, postupujte podle těchto kroků:

1. Pokud zařízení používá jiný uživatel, proveďte jednu z následujících akcí:
   - Jednou stiskněte tlačítko napájení, abyste se vrátili do pohotovostního režimu, a pak znovu stiskněte tlačítko napájení, abyste se vrátili na zamykací obrazovku.
   - HoloLens 2 uživatelé mohou vybrat dlaždici uživatele z nabídka Start a odhlásit aktuálního uživatele.

1. Pomocí přihlašovacích údajů účtu Azure AD se přihlaste k zařízení.  
    Pokud zařízení používáte poprvé, musíte ho HoloLens na [](hololens-calibration.md) vlastní oči.

Pokud chcete zobrazit seznam uživatelů zařízení nebo uživatele ze zařízení odebrat, přejděte na stránku **Nastavení**  >    >  **Účty Ostatní uživatelé**.

## <a name="share-with-multiple-people-all-using-the-same-account"></a>Sdílet s více lidmi pomocí stejného účtu

Několik uživatelů může také sdílet HoloLens zařízení při použití jednoho uživatelského účtu.

**Když HoloLens 2** nový uživatel poprvé vhodí zařízení na hlavičku (při zachování stejného účtu přihlášené), zařízení vyzve nového uživatele, aby rychle zkalibruje a přizpůsobí prostředí pro prohlížení. Zařízení může ukládat informace o zásobách, aby v budoucnu bylo možné automaticky optimalizovat kvalitu a komfort pro sledování jednotlivých uživatelů. Uživatelé nemusí zařízení znovu nakalibrovat.

**V HoloLens (1. generace)** budou uživatelé, kteří sdílejí účet, muset požádat o překalibraci v Nastavení aplikaci.  Přečtěte si další informace o [systému](hololens-calibration.md).
