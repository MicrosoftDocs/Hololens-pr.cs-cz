---
title: Přehled připojení HoloLens 2 ke cloudu s funkcí Remote Assist
description: Naučte se registrovat zařízení HoloLens 2 přes cloudovou propojenou síť pomocí programu Vzdálená pomoc pro Dynamics 365.
keywords: HoloLens, Správa, připojení k cloudu, Vzdálená pomoc, AAD, Azure AD, MDM, Správa mobilních zařízení
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
ms.openlocfilehash: 43fbcc3a841f6c3f15006f285188e55d22f10599
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111377536"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>Průvodce nasazením – Cloud s připojením HoloLens 2 s funkcí Remote Assist – přehled

Tato příručka pomáhá odborníkům v oblasti IT plánovat a nasazovat zařízení Microsoft HoloLens 2 do své organizace s cílem zajistit, aby byla tato zařízení připojená k vaší organizaci pomocí programu Remote Assist služby Dynamics 365, který je připravený k použití. Mějte na paměti, že tato akce bude sloužit jako model nasazení pro účely konceptu do vaší organizace v rámci nejrůznějších případů použití HoloLens 2.

V této příručce se dozvíte, jak zaregistrovat vaše zařízení do správy zařízení, použít licence podle potřeby a ověřit, jestli koncoví uživatelé můžou hned po nastavení zařízení hned používat vzdálenou pomoc. Pokud to chcete provést, přejdeme na důležité části infrastruktury potřebné k tomu, aby se daly nastavit a spustit – dosahování nasazení ve velkém měřítku s využitím HoloLens 2.

[![Scénář ](./images/deployment-guides-revised-scenario-a.png) připojení ke cloudu](./images/deployment-guides-revised-scenario-a.png#lightbox)
## <a name="in-this-guide"></a>V této příručce

Tato příručka má konkrétní cíl nastavení vzdáleného asistence v rámci vaší organizace na zařízeních HoloLens. Pokryjeme Necessities potřebný k dosažení tohoto cíle. Aby se zajistilo zaměření na tento cíl, některá příprava a konfigurace se předem vybere, aby se optimalizoval pro toto nasazení, nebo aby se snížily položky potřebné ke konfiguraci. O těchto volbách budete informováni a můžete přizpůsobit nasazení na základě vašich obchodních potřeb.

Toto nastavení se podobá [scénáři a: nasazení do cloudových připojení](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), což je dobrá možnost pro spoustu nasazení konceptů, která budou zahrnovat:

- Wi-Fi sítě jsou obvykle plně otevřené pro Internet a cloudové služby.
- Připojení Azure AD k automatické registraci MDM – spravovaná MDM (Intune)
- Uživatelé se přihlásí pomocí vlastního podnikového účtu (Azure AD).
  - Podporuje se jeden nebo víc uživatelů na zařízení.
- Na základě specifických případů použití se aplikují různé úrovně konfigurací uzamčení zařízení, od úplného otevření do veřejného terminálu s jednou aplikací.



V této příručce se nepoužijí žádná další omezení zařízení ani konfigurace, ale doporučujeme vám, abyste tyto možnosti prozkoumali po dokončení.

## <a name="learn-about-remote-assist"></a>Další informace o funkci Remote Assist

Vzdálená pomoc umožňuje spolupráci a opravy, vzdálenou kontrolu a také sdílení a školení ve znalostní bázi. Propojením lidí s různými rolemi a umístěním se technik, který používá vzdálenou pomoc, může připojit se vzdáleným spolupracovníka v Microsoft Teams. Můžou kombinovat video, snímky obrazovky a poznámky a vyřešit problémy v reálném čase, i když&#39;t ve stejném umístění. Vzdálení spolupracovníci můžou vkládat referenční obrázky, schémata a další užitečné informace, které&#39;pracovník s fyzickým prostorem.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a>V této příručce budete:

Systém

> [!div class="checklist"]
> - [Seznamte se se základy infrastruktury pro zařízení HoloLens 2.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Přečtěte si další informace o službě Azure AD a nastavte ji, pokud ji&#39;t.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Přečtěte si o správě identit a o tom, jak nejlépe nastavit účty Azure AD.](hololens2-cloud-connected-prepare.md#identity-management)
> - [Přečtěte si další informace o MDM a nastavte Intune, pokud&#39;t už máte připravený.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Seznamte se s požadavky na síť pro vzdálenou pomoc.](hololens2-cloud-connected-prepare.md#network)
> - [Volitelně: připojení k prostředkům organizace pomocí sítě VPN](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Konfigurace

> [!div class="checklist"]
> - [Vytváření uživatelů a skupin.](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Jak nastavit automatickou registraci v rámci služby Azure AD.](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [Jak přiřadit licence k aplikacím.](hololens2-cloud-connected-configure.md#application-licenses)

Nasazení:

> [!div class="checklist"]
> - [Nastavte svůj HoloLens 2 a ověřte registraci.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Ověřte, že můžete provést volání vzdáleného asistence.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Vést

> [!div class="checklist"]
> - [Jak aktualizovat vzdálenou pomoc pomocí aplikace Microsoft Store.](hololens2-cloud-connected-maintain.md#updates)
> - [Vytváří se plán podpory.](hololens2-cloud-connected-maintain.md#support-plan)
> - [Plán vývoje.](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>Další krok

> [!div class="nextstepaction"]
> [Nasazení připojené ke cloudu – Příprava](hololens2-cloud-connected-prepare.md)

