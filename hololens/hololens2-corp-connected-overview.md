---
title: průvodce nasazením – firemní připojení HoloLens 2 s průvodcem Dynamics 365 – přehled
description: naučte se registrovat zařízení HoloLens 2 pomocí průvodců Dynamics 365 přes síť propojenou s podnikem.
keywords: HoloLens, správa, připojení k podnikové síti, příručky k Dynamics 365, AAD, Azure AD, MDM, správa mobilních zařízení
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 541c1080d7f5fe9491d6cb11179ea98b160f687c
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428112"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>průvodce nasazením – firemní připojení HoloLens 2 s průvodcem Dynamics 365 – přehled

tato příručka pomůže odborníkům v oblasti it plánovat a nasazovat zařízení Microsoft HoloLens 2 pomocí průvodců Dynamics 365 (příruček) k organizaci. Tato příručka je ideální pro pilotní nasazení a také pro produkční nasazení a je podobná [scénáři B: nasazení v síťové příručce vaší organizace](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) . po otestování testování konceptu můžete pomocí tohoto průvodce přejít k části s integrací HoloLens do vaší organizace.

V této příručce se dozvíte, jak zaregistrovat vaše zařízení do vaší stávající správy zařízení, jak podle potřeby instalovat licence a ověřit, že koncoví uživatelé můžou pracovat s průvodcem Dynamics 365, a také po nastavení zařízení použít vlastní obchodní aplikace. 

## <a name="prerequisites"></a>Požadavky

Následující infrastruktura by již měla být zavedena:
- Wi-Fi
    - Interní podniková síť s přístupem k interním prostředkům a omezeným přístupem k internetovým nebo cloudovým službám
    - Ověřování pomocí certifikátu založeného na zařízení.
- připojení služby Azure Active Directory (Azure ad) k automatické registraci MDM (vyžaduje se[předplatné Azure AD P1](/azure/active-directory/fundamentals/active-directory-whatis) )
- Spravovaná MDM (Intune)
    - Jednu nebo více aplikací se nasazují přes MDM.
- Síť 
    - Certifikáty (SCEP nebo PKCS)
    - Konfigurace proxy serveru
- Uživatelé se přihlásí pomocí vlastního podnikového účtu (Azure AD).
    - Podporuje se jeden nebo víc uživatelů na zařízení.
- Různé úrovně konfigurací uzamčení zařízení se aplikují na základě konkrétních případů použití, od úplného otevření do veřejného terminálu s jednou aplikací.

## <a name="guides-licensing-and-requirements"></a>[Průvodce – licencování a požadavky](/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)

- Účet Azure AD
- Průvodce pro aplikace Dynamics 365 vás provede počítači a HoloLens
- Předplatné příručky pro Dynamics 365
    - Microsoft Data– doplněk (zahrnutý)
    - Power Apps (zahrnuto)
- Power BI Desktop
- Připojení k síti

[![Diagram propojené sítě Corp, fáze 1. ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagram propojené sítě Corp, fáze 2 ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

## <a name="in-this-guide-you-will"></a>V této příručce budete:
### <a name="prepare"></a>Příprava
> [!div class="checklist"]
>- [seznamte se se základy infrastruktury pro zařízení HoloLens 2.](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [Přečtěte si další informace o Azure AD a nastavte si ho, pokud ho nemáte.](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [Přečtěte si o správě identit a o tom, jak nejlépe nastavit účty Azure AD.](hololens2-corp-connected-prepare.md#identity-management)
>- [Přečtěte si další informace o MDM a nastavte Intune, pokud ještě nemáte připravenou.](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [Seznamte se s technologií Wi-Fi založenou na certifikátech.](hololens2-corp-connected-prepare.md#certificates)
>- [Seznamte se s proxy serverem.](hololens2-corp-connected-prepare.md#proxy)
>- [Zjistěte, jak můžete používat obchodní aplikace.](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [Přečtěte si další informace o tom, jak můžete používat příručky pro vaši organizaci.](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a>Konfigurace
> [!div class="checklist"]
>- [Vytváření uživatelů a skupin.](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [Jak nastavit automatický zápis.](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [Jak nastavit Wi-Fi certifikátů a profilů pro připojení k podnikovému Wi-Fi.](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [Upload a přiřaďte obchodní balíčky aplikací (LOB).](hololens2-corp-connected-configure.md#app-deployment)
>- [Průvodce instalací Dynamics 365.](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [Jak nakonfigurovat celoobrazovkový režim (volitelné).](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [Jak nakonfigurovat WDAC (volitelné).](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a>Nasadit
> [!div class="checklist"]
>-  [Ověřte registraci prostřednictvím zařízení a MDM.](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [Ověří Wi-Fi certifikátů.](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [Ověří instalaci aplikace LOB.](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [Ověřte vodítka pomocí vytváření a provozu.](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a>Údržba
> [!div class="checklist"]
>- [aktualizujte HoloLens 2.](hololens2-corp-connected-maintain.md#update-hololens)
>- [Postup aktualizace průvodců (aplikace pro Store)](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [Jak aktualizovat obchodní aplikace](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [Plán vývoje.](hololens2-corp-connected-maintain.md#development-plan) 
>- [Vytváří se plán podpory.](hololens2-corp-connected-maintain.md#support-plan)
>- [Možnosti správy zařízení.](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>Další krok 
> [!div class="nextstepaction"]
> [Firemní připojené nasazení – Příprava](hololens2-corp-connected-prepare.md)
