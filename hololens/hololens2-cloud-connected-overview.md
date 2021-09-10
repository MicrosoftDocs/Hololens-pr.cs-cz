---
title: přehled cloudu s připojením HoloLens 2 s funkcí Remote Assist
description: naučte se registrovat zařízení HoloLens 2 přes cloudovou propojenou síť pomocí programu vzdálená pomoc pro Dynamics 365.
keywords: HoloLens, správa, připojení k cloudu, vzdálená pomoc, AAD, Azure AD, MDM, správa mobilních zařízení
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
ms.openlocfilehash: 66e543dd699edbd54ab41474f3ea86fa313bf6ba
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427413"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>průvodce nasazením – Cloud připojený HoloLens 2 s funkcí Remote Assist – přehled

tato příručka pomůže odborníkům v oblasti it plánovat a nasazovat zařízení Microsoft HoloLens 2 se vzdálenou asistencí do organizace. tato akce bude sloužit jako model nasazení pro účely konceptu do vaší organizace v různých případech použití HoloLens 2. Instalace se podobá [scénáři a: nasazení do cloudu připojení zařízení](common-scenarios.md#scenario-a). 

V této příručce se dozvíte, jak zaregistrovat vaše zařízení do správy zařízení, použít licence podle potřeby a ověřit, jestli koncoví uživatelé můžou hned po nastavení zařízení hned používat vzdálenou pomoc. provedeme to tak, že budete mít k dispozici důležité možnosti infrastruktury potřebné k tomu, abyste nastavili a mohli běžet – dosahování nasazení ve velkém měřítku HoloLens 2. V této příručce se nepoužijí žádná další omezení zařízení ani konfigurace, ale doporučujeme, abyste tyto možnosti prozkoumali po dokončení.

## <a name="prerequisites"></a>Požadavky

následující infrastruktura by měla být zavedena, aby bylo možné nasadit HoloLens 2. V takovém případě je nastavení Azure a Intune zahrnuté v tomto průvodci:

Toto je instalační program, který se podobá [scénáři a: nasazení do cloudového připojení](/hololens/common-scenarios#scenario-a), což je dobrá možnost pro mnoho nasazení konceptu, která budou zahrnovat:

- Wi-Fi sítě jsou obvykle plně otevřené pro Internet a cloudové služby.
- Připojení ke službě Azure AD s automatickým zápisem MDM – spravovaná přes MDM (Intune)
- Uživatelé se přihlásí pomocí vlastního podnikového účtu (Azure AD).
    - Podporuje se jeden nebo víc uživatelů na zařízení.

:::image type="content" alt-text="Scénář připojený ke cloudu" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a>Další informace o funkci Remote Assist

Vzdálená pomoc umožňuje spolupráci a opravy, vzdálenou kontrolu a také sdílení a školení ve znalostní bázi. Když propojíte lidi v různých rolích a místech, technik, který používá vzdálenou pomoc, se může připojit ke vzdálenému spolupracujícímu spolupracujícímu na Microsoft Teams. Můžou kombinovat video, snímky obrazovky a poznámky a vyřešit problémy v reálném čase, i když nejsou ve stejném umístění. Vzdálení spolupracovníci můžou vkládat referenční obrázky, schémata a další užitečné informace, které se týkají fyzického prostoru technika, aby se na ně mohli odkazovat v době, kdy se na HoloLens pracuje na schématu a praktická místa.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a>Licencování a požadavky vzdálené pomoci

- Účet Azure AD (potřebný pro zakoupení předplatného a přiřazování licencí)
- [Předplatné vzdálené pomoci](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (nebo [zkušební verze vzdáleného asistence](/dynamics365/mixed-reality/remote-assist/try-remote-assist))
    
#### <a name="dynamics-365-remote-assist-user"></a>Uživatel funkce Remote Assist pro uživatele Dynamics 365

- Licence pro vzdálenou pomoc
- Připojení k síti

#### <a name="microsoft-teams-user"></a>Microsoft Teams uživatel

- Microsoft Teams nebo [Teams Freemium](https://products.office.com/microsoft-teams/free).
- Připojení k síti

Pokud plánujete implementaci tohoto [scénáře mezi klienty](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), budete možná potřebovat licenci na informace o bariérách. Pokud chcete zjistit, jestli je nutná licence k informační Bariérě, přečtěte si téma [Dodavatelé a zákazníci s úplnými možnostmi služby Dynamics 365 Remote Assist](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation).

## <a name="in-this-guide-you-will"></a>V této příručce budete:

Systém

> [!div class="checklist"]
> - [seznamte se se základy infrastruktury pro zařízení HoloLens 2.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Přečtěte si další informace o službě Azure AD a nastavte ji, pokud ji&#39;t.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Přečtěte si o správě identit a o tom, jak nejlépe nastavit účty Azure AD.](hololens2-cloud-connected-prepare.md#identity-management)
> - [Přečtěte si další informace o MDM a nastavte Intune, pokud&#39;t už máte připravený.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Seznamte se s požadavky na síť pro vzdálenou pomoc.](hololens2-cloud-connected-prepare.md#network)
> - [Volitelně: připojení k prostředkům organizace pomocí sítě VPN](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Konfigurace

> [!div class="checklist"]
> - [Vytváření uživatelů a skupin.](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Jak nastavit automatickou registraci v rámci služby Azure AD.](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [Jak přiřadit licence k aplikacím.](hololens2-cloud-connected-configure.md#application-licenses)

Nasazení:

> [!div class="checklist"]
> - [nastavte HoloLens 2 a ověřte registraci.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Ověřte, že můžete provést volání vzdáleného asistence.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Vést

> [!div class="checklist"]
> - [jak aktualizovat vzdálenou pomoc pomocí aplikace Microsoft Store.](hololens2-cloud-connected-maintain.md#updates)
> - [Vytváří se plán podpory.](hololens2-cloud-connected-maintain.md#support-plan)
> - [Plán vývoje.](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>Další krok

> [!div class="nextstepaction"]
> [Nasazení připojené ke cloudu – Příprava](hololens2-cloud-connected-prepare.md)

