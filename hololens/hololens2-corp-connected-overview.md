---
title: Průvodce nasazením – Příručky pro firemní HoloLens 2 s Dynamics 365 – přehled
description: Zjistěte, jak zaregistrovat HoloLens 2 pomocí průvodců Dynamics 365 přes podnikovou připojenou síť.
keywords: HoloLens, správa, firemní připojení, Průvodci Dynamics 365, AAD, Azure AD, MDM, Mobile Správa zařízení
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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032296"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>Průvodce nasazením – Průvodci podnikovým HoloLens 2 s Dynamics 365 – přehled

Tato příručka pomůže IT specialistům plánovat a nasazovat Microsoft HoloLens 2 pomocí průvodců Dynamics 365 (průvodci) pro jejich organizaci. Tato příručka je skvělá pro pilotní i produkční nasazení a podobá se scénáři [B: Nasazení](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) v síti vaší organizace. Po otestování testování konceptu můžete pomocí tohoto průvodce pokračovat v integraci HoloLens do vaší organizace.

V této příručce se budeme řídit tím, jak zaregistrovat zařízení do stávající správy zařízení, jak podle potřeby použít licence a ověřit, že koncoví uživatelé po nastavení zařízení mohou používat příručku Dynamics 365 a také používat vlastní obchodní aplikace. 

## <a name="prerequisites"></a>Požadavky

Už by měla být k dispozici následující infrastruktura:
- Wi-Fi
    - Interní podniková síť s přístupem k interním prostředkům a omezeným přístupem k internetu nebo cloudovým službám
    - Ověřování certifikátů na základě zařízení.
- Azure Active Directory (Azure AD) Join s automatickou registrací MDM (je potřeba[předplatné Azure AD P1)](/azure/active-directory/fundamentals/active-directory-whatis)
- Správa MDM (Intune)
    - Jedna nebo více aplikací se nasadí přes MDM.
- Síť 
    - Certifikáty (SCEP nebo PKCS)
    - Konfigurace proxy serveru
- Uživatelé se přihlašují pomocí vlastního podnikového účtu (Azure AD).
    - Podporuje se jeden nebo více uživatelů na zařízení.
- Různé úrovně konfigurace uzamčení zařízení použité na základě konkrétních případů použití, od plně otevřeného až po beznabitový terminál s jednou aplikací

## <a name="guides-licensing-and-requirements"></a>[Průvodci licencování a požadavky](/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)

- Účet Azure AD
- Dynamics 365 Guides applications PC and HoloLens
- Předplatné průvodců Dynamics 365
    - Microsoft Dataverse (zahrnuto)
    - Power Apps (zahrnuto)
- Power BI Desktop
- Připojení k síti

[![Diagram sítě připojený společnosti, fáze 1. ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagram sítě připojený společnosti, fáze 2. ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

## <a name="in-this-guide-you-will"></a>V této příručce:
### <a name="prepare"></a>Příprava
> [!div class="checklist"]
>- [Seznamte se se základy infrastruktury pro HoloLens 2.](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [Přečtěte si další informace o Službě Azure AD a nastavte si ji, pokud ji nemáte.](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [Přečtěte si o správě identit a o tom, jak nejlépe nastavit účty Azure AD.](hololens2-corp-connected-prepare.md#identity-management)
>- [Přečtěte si další informace o MDM a nastavení s Intune, pokud ho ještě nemáte připravený.](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [Seznamte se s Wi-Fi založenou na certifikátech.](hololens2-corp-connected-prepare.md#certificates)
>- [Seznamte se s proxy serverem.](hololens2-corp-connected-prepare.md#proxy)
>- [Seznamte se s používáním obchodních aplikací.](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [Přečtěte si další informace o tom, jak můžete používat příručky pro vaši organizaci.](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a>Konfigurace
> [!div class="checklist"]
>- [Jak vytvářet uživatele a skupiny](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [Jak nastavit automatickou registraci](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [Postup nastavení Wi-Fi profilů a certifikátů pro připojení Wi-Fi podnikové sítě](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [Upload a přiřadit balíčky obchodních aplikací.](hololens2-corp-connected-configure.md#app-deployment)
>- [Nastavení průvodců Dynamics 365](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [Konfigurace bezobrazovkového režimu (volitelné)](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [Postup konfigurace nástroje WDAC (volitelné)](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a>Nasadit
> [!div class="checklist"]
>-  [Ověření registrace prostřednictvím zařízení a MDM](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [Ověřte Wi-Fi certifikáty.](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [Ověřte instalaci obchodní aplikace.](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [Ověřte příručky prostřednictvím vytváření a provozu.](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a>Údržba
> [!div class="checklist"]
>- [Aktualizujte HoloLens 2.](hololens2-corp-connected-maintain.md#update-hololens)
>- [Jak aktualizovat příručky (aplikace pro Store).](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [Jak aktualizovat obchodní aplikace](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [Plán vývoje.](hololens2-corp-connected-maintain.md#development-plan) 
>- [Vytvoření plánu podpory](hololens2-corp-connected-maintain.md#support-plan)
>- [Možnosti správy zařízení.](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>Další krok 
> [!div class="nextstepaction"]
> [Nasazení připojené k podnikové síti – Příprava](hololens2-corp-connected-prepare.md)
