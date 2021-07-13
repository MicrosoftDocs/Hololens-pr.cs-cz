---
title: Přehled připojení ke cloudu HoloLens 2 pomocí vzdálené pomoci
description: Zjistěte, jak zaregistrovat HoloLens 2 přes síť připojenou ke cloudu pomocí Dynamics 365 Remote Assistu.
keywords: HoloLens, správa, připojení ke cloudu, Remote Assist, AAD, Azure AD, MDM, Mobile Správa zařízení
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 86d36275d5cf1296ca3e9fec90684a188a29f3f0
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635122"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>Průvodce nasazením – Cloud connected HoloLens 2 with Remote Assist – Přehled

Tato příručka pomůže IT specialistům plánovat a nasazovat Microsoft HoloLens 2 zařízení s Remote Assistem v organizaci. To bude sloužit jako model pro nasazení do vaší organizace v rámci různých scénářů HoloLens 2. Nastavení se podobá [scénáři A: Nasazení do zařízení s připojením ke cloudu.](https://docs.microsoft.com/hololens/common-scenarios#scenario-a) 

V této příručce se budeme řídit tím, jak zaregistrovat zařízení do správy zařízení, jak podle potřeby použít licence a ověřit, že koncoví uživatelé mohou vzdálenou pomoc při nastavení zařízení okamžitě používat. Za tímto účelem si projdeme důležité části infrastruktury potřebné k nastavení a z provozu – a dosáhneme nasazení ve velkém měřítku pomocí HoloLens 2. V tomto průvodci se nebudou používat žádná další omezení ani konfigurace zařízení, ale doporučujeme vám tyto možnosti prozkoumat po dokončení.

## <a name="prerequisites"></a>Požadavky

Aby bylo možné nasadit HoloLens 2, měla by být zavedena následující infrastruktura. Pokud ne, nastavení Azure a Intune je součástí tohoto průvodce:

Toto je nastavení podobné scénáři [A:](/hololens/common-scenarios#scenario-a)Nasazení do zařízení s připojením ke cloudu, což je dobrá možnost pro mnoho nasazení s potvrzením konceptu, která bude zahrnovat:

- Wi-Fi sítě jsou obvykle plně otevřené pro internet a cloudové služby.
- Připojení ke službě Azure AD s automatickou registrací MDM – spravovaná pomocí MDM (Intune)
- Uživatelé se přihlašují pomocí vlastního podnikového účtu (Azure AD).
    - Podporuje se jeden nebo více uživatelů na zařízení.

:::image type="content" alt-text="Scénář připojení ke cloudu" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a>Další informace o vzdálené pomoci

Remote Assist umožňuje spolupráci s údržbou a opravami, vzdálenou kontrolu a také sdílení znalostí a školení. Propojením lidí v různých rolích a umístěních se technik pomocí vzdálené pomoci může spojit se vzdáleným spolupracovníkem na Microsoft Teams. Mohou kombinovat video, snímky obrazovky a poznámky k řešení problémů v reálném čase, i když&#39;nejsou na stejném místě. Vzdálení spolupracovníci mohou vkládat referenční obrázky, schémata&#39;další užitečné informace o fyzickém prostoru technika, aby mohli na schéma odkazovat při práci s pannami a bez rukou na HoloLens.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a>Licencování a požadavky služby Remote Assist

- Účet Azure AD (vyžadované pro nákup předplatného a přiřazení licencí)
- [Předplatné Remote Assistu](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (nebo [zkušební verze Remote Assistu)](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)
    
#### <a name="dynamics-365-remote-assist-user"></a>Uživatel Dynamics 365 Remote Assistu

- Licence Remote Assistu
- Připojení k síti

#### <a name="microsoft-teams-user"></a>Microsoft Teams uživatele

- Microsoft Teams nebo [Teams Freemium.](https://products.office.com/microsoft-teams/free)
- Připojení k síti

Pokud plánujete implementaci tohoto scénáře [napříč tenanty,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)možná budete potřebovat licenci Information Barriers. Informace [o tom,](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) jestli se vyžaduje licence Information Barrier, najdete v tomto článku.

## <a name="in-this-guide-you-will"></a>V této příručce:

Připravit:

> [!div class="checklist"]
> - [Seznamte se se základy infrastruktury pro HoloLens 2.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Přečtěte si další informace o Službě Azure AD a nastavte ji,&#39;ji nemáte.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Přečtěte si o správě identit a o tom, jak nejlépe nastavit účty Azure AD.](hololens2-cloud-connected-prepare.md#identity-management)
> - [Přečtěte si další informace o MDM a nastavte intune, pokud&#39;ještě nemáte připravenou.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Seznamte se s požadavky funkce Remote Assist na síť.](hololens2-cloud-connected-prepare.md#network)
> - [Volitelně: Síť VPN pro připojení k prostředkům organizace](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Konfigurace:

> [!div class="checklist"]
> - [Vytvoření uživatelů a skupin](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Jak nastavit automatickou registraci v rámci Azure AD](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [Postup přiřazení licencí aplikace](hololens2-cloud-connected-configure.md#application-licenses)

Nasazení:

> [!div class="checklist"]
> - [Nastavte svou registraci HoloLens 2 a ověřte registraci.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Ověřte, že můžete provést volání vzdálené pomoci.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Udržovat:

> [!div class="checklist"]
> - [Jak aktualizovat remote assist pomocí Microsoft Store aplikace.](hololens2-cloud-connected-maintain.md#updates)
> - [Vytvoření plánu podpory](hololens2-cloud-connected-maintain.md#support-plan)
> - [Plán vývoje.](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>Další krok

> [!div class="nextstepaction"]
> [Nasazení připojené ke cloudu – Příprava](hololens2-cloud-connected-prepare.md)

