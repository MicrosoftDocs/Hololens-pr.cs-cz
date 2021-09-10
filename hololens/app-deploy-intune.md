---
title: intune a Portál společnosti
description: Naučte se, jak pomocí Intune, správy mobilních zařízení a portálu společnosti nastavit, přiřazovat a vytvářet příjemné uživatelské prostředí.
keywords: Intune, Správa aplikací, aplikace, portál společnosti, portál, HoloLens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b192732f5e7edffaa1d0ab081454e4034c416191
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427628"
---
# <a name="intune--company-portal"></a>intune & Portál společnosti

se správou mobilních zařízení (MDM) můžete pomocí [Microsoft Endpoint Manager (intune)](/intune/windows-holographic-for-business) používat vlastní aplikace, které přímo nasadíte do vašich HoloLensch zařízení. Microsoft Intune je cloudová služba, která se zaměřuje na správu mobilních zařízení (MDM) a správu mobilních aplikací (MAM). intune je součástí [sady Microsoft Enterprise Mobility + Securitye (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)a umožňuje uživatelům zvýšit produktivitu při zachování chráněných dat vaší organizace. Pokud se chcete o Intune dozvědět víc, přečtěte si téma [co je Intune](/mem/intune/fundamentals/what-is-intune).

## <a name="setup"></a>Nastavení

1. Upload aplikaci na firmu nebo nahrajte vlastní aplikaci do svého tenanta intune. viz také: [Enterprise správa aplikací](/windows/client-management/mdm/enterprise-app-management).

2. [Přiřaďte aplikaci ke skupině](/mem/intune/apps/apps-deploy). V závislosti na zvoleném typu přiřazení může být aplikace automaticky dodávána nebo k dispozici, aby ji bylo možné snadno vyřizovat, pokud máte výběr aplikací.

> [!NOTE]
> Při sestavování sady appx se ujistěte, že máte na zřeteli architekturu pro zařízení, která nasazujete do nástroje. HoloLens 2 je ARM64 a HoloLens (1. generace) je x86. V případě, že máte v plánu prostředí se smíšenými zařízeními, můžete zahrnout obojí do jedné sady appx.

## <a name="assignment-types"></a>Typy přiřazení

Pokud chcete, aby se vaše aplikace po registraci automaticky nainstalovala do zařízení, měli byste pro tyto skupiny vybrat možnost **požadováno** .
Pokud chcete aplikaci zpřístupnit pro stažení do zařízení zaregistrovaných prostřednictvím portálu společnosti, vyberte možnost **dostupné pro zaregistrovaná zařízení**.

## <a name="end-user-experience"></a>Prostředí End-User

Po nastavení konfigurace v Intune jste připraveni na to, aby koncoví uživatelé získali vybrané aplikace.

K automatickému získání aplikací použijte následující postup:

1. Zaregistrujte svoje zařízení u svého tenanta.
2. Po dokončení registrace zařízení byste měli aplikaci obdržet na svém zařízení.
3. pokud vám nevidíte aplikaci hned, přejděte na **Nastavení**  >  **účty**  >  **pracovní nebo školní**  >  informace o *účtu* , a posuňte se dolů a zobrazte si informace o stavu nainstalované aplikace.

jak získat aplikace pomocí Portál společnosti:

1. Otevřete **nabídku Start** a vyberte možnost **Microsoft Store**.
2. vyhledejte **Portál společnosti** a stáhněte si aplikaci.
3. Přihlaste se ke svému účtu.
4. Vyberte aplikaci, kterou chcete přijmout, a stáhněte ji.

> [!Tip]
> přečtěte si další informace o [automatické instalaci Portál společnosti](/mem/intune/apps/company-portal-app) a [nasazení a správě aplikací v intune](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).
