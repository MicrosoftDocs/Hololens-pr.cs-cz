---
title: Běžné scénáře nasazení
description: Další informace o nasazení a správě HoloLens podnikových prostředích, včetně infrastruktury, Azure Active Directory a správy mobilních zařízení.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bgener
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: ccccdcc7d3188919d02eb5855131137415c12d16
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639824"
---
# <a name="common-deployment-scenarios"></a>Běžné scénáře nasazení

## <a name="overview"></a>Přehled

Tato stránka poskytuje základní přehled architektury pro tři běžné scénáře nasazení a správy Microsoft HoloLens 2 zařízení v rámci podniku.

Způsob správy zařízení a přístupu k prostředkům vaší organizace je často určován z velké části faktory, které už jsou na místě. V závislosti na vaší stávající infrastruktuře si prohlédněte běžný styl správy zařízení (MDM) v následujících scénářích a pak si v článku Plánování nasazení [HoloLens 2](hololens-core-components.md) v komerčním prostředí zjistěte, který scénář vyhovuje vašim potřebám. K dispozici jsou také tři odpovídající příručky, které můžete použít během nasazení.


 1. [Průvodce nasazením prostředí připojeného ke cloudu](hololens2-cloud-connected-overview.md)
     1. [Průvodce nasazením prostředí připojeného ke cloudu (externí klienti)](hololens2-deployment-guide.md)
 1. [Průvodce nasazením podnikové sítě](hololens2-corp-connected-overview.md)
 1. [Průvodce nasazením zabezpečeného prostředí offline](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Scénář A: Nasazení do zařízení připojených ke cloudu

Tento scénář je srovnatelný s nasazením spravovaných mobilních zařízení v rámci společnosti. HoloLens 2 se nasazovat pro použití primárně v prostředích mimo podnikovou síť. K podnikovým prostředkům se přistupuje nebo je možné, že budou omezené prostřednictvím sítě VPN. 
 * Základní běžné konfigurace
   * Wi-Fi sítě jsou obvykle plně otevřené pro internet a cloudové služby.
   * Připojení ke službě Azure AD s Správa zařízení mobilních zařízení (MDM) – spravovaná pomocí MDM (Intune)
   * Uživatelé se přihlašují pomocí vlastního podnikového účtu (Azure AD).
     * Podpora jednoho nebo více uživatelů na zařízení
   * Na základě konkrétních případů použití, od plně otevřeného až po beznabitový terminál s jednou aplikací, se používají různé úrovně konfigurací uzamčení zařízení.
   * Jedna nebo více aplikací se nasadí přes MDM.

* Běžné problémy
   * Určení konfigurací MDM, které se mají použít pro HoloLens 2 na základě požadavků scénáře

[![Diagram scénáře ](images/deployment-guides-revised-scenario-a.png) A](images/deployment-guides-revised-scenario-a.png#lightbox)

Odpovídající příručka připojená ke cloudu popisuje, jak zaregistrovat HoloLens 2 do správy zařízení, jak podle potřeby použít licence a ověřit, že koncoví uživatelé mohou vzdálenou pomoc při nastavení zařízení okamžitě používat. Pomocí příručky Externí klienti můžete nasadit zařízení do vzdálené lokality pro krátkodobé nebo dlouhodobé externí použití.

> [!div class="nextstepaction"]
> [Průvodce nasazením prostředí připojeného ke cloudu](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [Průvodce nasazením prostředí připojeného ke cloudu (externí klienti)](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>Scénář B: Nasazení v síti vaší organizace

Tento scénář je stejný jako u klasického nasazení pro většinu Windows 10 počítačů. HoloLens 2 je nasazená pro použití primárně v podnikové síti s přístupem k interním podnikovým prostředkům. Internet a cloudové služby mohou být omezené. 

 * Základní běžné konfigurace
   * Wi-Fi je interní podniková síť s přístupem k interním prostředkům a omezeným přístupem k internetu nebo cloudovým službám.
   * Připojení ke službě Azure AD s automatickou registrací MDM
   * Správa MDM (Intune)
   * Uživatelé se přihlašují pomocí vlastního podnikového účtu (Azure AD).
     * Podpora jednoho nebo více uživatelů na zařízení
   * Na základě konkrétních případů použití, od plně otevřeného až po beznabitový terminál s jednou aplikací, se používají různé úrovně konfigurací uzamčení zařízení.
   * Jedna nebo více aplikací se nasadí přes MDM.

 * Běžné problémy
   * HoloLens 2 nepodporuje připojení k místní službě AD ani SCCM. Pouze připojení k Azure AD pomocí MDM. Mnoho společností v tomto scénáři stále nasazovat počítače Windows 10 jako místní zařízení připojená k AD spravovaná přes System Center Configuration Manager (SCCM) a nemusí mít nasazenou nebo nakonfigurovanou infrastrukturu pro správu interních zařízení Windows 10 prostřednictvím cloudových řešení MDM.
   * Protože HoloLens 2 je první zařízení v cloudu, spoléhá do značné míry na internetové a cloudové služby pro ověřování uživatelů, aktualizace operačního systému, správu MDM atd. Při připojování k podnikové síti bude pravděpodobně potřeba upravit pravidla proxy serveru nebo brány firewall, aby byl povolen přístup pro HoloLens 2 a aplikace, které na ní běží.
   * Připojení Wi-Fi podnikové sítě obvykle vyžaduje certifikáty k ověření zařízení nebo uživatele v síti. Konfigurace požadované infrastruktury nebo nastavení pro nasazení certifikátů do Windows 10 zařízení prostřednictvím MDM může být náročná.

[![Diagram scénáře B1 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagram scénáře B2 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

Odpovídající příručka k podnikové síti instruuje, jak zaregistrovat HoloLens 2 do stávající správy zařízení, jak podle potřeby použít licence a ověřit, jestli koncoví uživatelé po nastavení zařízení mohou používat příručku Dynamics 365 a také používat vlastní obchodní aplikace.

> [!div class="nextstepaction"]
> [Průvodce nasazením podnikové sítě](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>Scénář C: Nasazení v zabezpečeném offline prostředí

Toto je typické nasazení pro vysoce zabezpečená nebo důvěrná umístění. HoloLens 2 je nasazená pro použití primárně offline bez přístupu k síti nebo internetu. 
 * Základní běžné konfigurace
   * Wi-Fi připojení je zakázané. Ethernet přes USB může být v případě potřeby povolený pro připojení k síti LAN.
   * Nespravovaná.
   * Místní uživatelský účet pro přihlášení k zařízení.
     * HoloLens 2 podporuje pouze jeden místní účet.
   * Prostřednictvím zřizovací balíčky se na základě konkrétních případů použití používají různé úrovně konfigurací uzamčení zařízení. Tyto konfigurace jsou obvykle omezené z důvodu požadavků na zabezpečené prostředí.
   * Jedna nebo více aplikací se nasadí prostřednictvím zřizovacího balíčku.

 * Běžné problémy
   * Prostřednictvím zřizovacích balíčků je k dispozici omezená sada konfigurací.
   * Cloudové služby není možné použít, a proto je možné omezit HoloLens 2.
   * Vyšší režijní náklady na správu, protože tato zařízení musí být nastavená, nakonfigurovaná a aktualizovaná ručně.

[![Offline zabezpečený diagram 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

Odpovídající průvodce zabezpečením offline poskytuje pokyny k použití ukázkového zřizovacího balíčku, který uzamkne HoloLens 2 pro použití v zabezpečených prostředích.

> [!div class="nextstepaction"]
> [Průvodce nasazením zabezpečeného prostředí offline](hololens-common-scenarios-offline-secure.md)


