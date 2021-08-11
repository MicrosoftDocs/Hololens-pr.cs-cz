---
title: Intune a Portál společnosti
description: Zjistěte, jak nastavit, přiřadit a vytvořit pohodlné uživatelské prostředí pro Intune, správu mobilních zařízení a portál společnosti.
keywords: intune, app management, app, company portal, portal, hololens
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
ms.openlocfilehash: f1c178c940224ed3cd07c58b886b176108614caf7a8463af089e2f2357f45553
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665246"
---
# <a name="intune--company-portal"></a>Intune & Portál společnosti

S Mobile Správa zařízení (MDM) můžete použít vlastní aplikace prostřednictvím [služby Microsoft Endpoint Manager (Intune)](/intune/windows-holographic-for-business) a nasadit je přímo do vašich HoloLens zařízení. Microsoft Intune je cloudová služba, která se zaměřuje na správu mobilních zařízení (MDM) a správu mobilních aplikací (MAM). Intune je součástí sady [Microsoftu Enterprise Mobility + Security (EMS)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)a umožňuje uživatelům být produktivní a současně chránit data vaší organizace. Další informace o Intune najdete v co [je Intune.](/mem/intune/fundamentals/what-is-intune)

## <a name="setup"></a>Nastavení

1. Upload aplikaci do obchodního podniku nebo nahrát vlastní aplikaci do tenanta Intune. Viz také: [Enterprise správy aplikací.](/windows/client-management/mdm/enterprise-app-management)

2. [Přiřaďte aplikaci ke skupině](/mem/intune/apps/apps-deploy). Na základě typu přiřazení, který zvolíte, můžete aplikaci doručit automaticky nebo ji můžete snadno načíst, pokud máte vybrané aplikace.

> [!NOTE]
> Při vytváření sady appx nezapomeňte zohlednit zahrnutí architektury pro zařízení, na která nasazujete. HoloLens 2 je ARM64 a HoloLens (1. generace) je x86. Pokud plánujete mít prostředí se smíšenými zařízeními, můžete obojí zahrnout do jedné sady appx.

## <a name="assignment-types"></a>Typy přiřazení

Pokud chcete, aby se vaše aplikace po registraci  automaticky nainstalovala na zařízení, měli byste pro tuto skupinu nebo skupiny vybrat Povinné.
Pokud chcete aplikaci stáhnout do zařízení zaregistrovaná prostřednictvím portálu společnosti, vyberte **Dostupná pro zaregistrovaná zařízení.**

## <a name="end-user-experience"></a>End-User prostředí

Po nastavení konfigurace v Intune jste připraveni koncovým uživatelům přijímat vybrané aplikace.

Pokud chcete automaticky získat aplikace, postupujte podle těchto kroků:

1. Zaregistrujte své zařízení v tenantovi.
2. Po dokončení registrace zařízení byste měli aplikaci obdržet na svém zařízení.
3. Pokud aplikaci nevidíte okamžitě, přejděte do části Nastavení Accounts Work or School your account Info **(Pracovní** nebo školní informace o účtu) a posuňte se dolů, kde najdete informace o  >    >    >   stavu nainstalované aplikace.

Jak se dostat k aplikacím prostřednictvím Portál společnosti:

1. Otevřete **nabídku Start a** vyberte **Microsoft Store**.
2. Vyhledejte **Portál společnosti** a stáhněte si aplikaci.
3. Přihlaste se ke svému účtu.
4. Vyberte aplikaci, kterou chcete obdržet, a stáhněte si ji.

> [!Tip]
> Přečtěte si [další informace o automatické instalaci Portál společnosti](/mem/intune/apps/company-portal-app) a nasazení a správě aplikací v [Intune.](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)
