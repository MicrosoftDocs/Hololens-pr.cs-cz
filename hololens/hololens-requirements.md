---
title: Běžné scénáře nasazení
description: přečtěte si další informace o nasazení a správě HoloLens v podnikovém prostředí, včetně infrastruktury, Azure Active Directory a správy mobilních zařízení.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bogenera
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: 72b9e61c52d6f4f08cf5a29baf7b01c29fae7489
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635462"
---
# <a name="common-deployment-scenarios"></a>Běžné scénáře nasazení

## <a name="overview"></a>Přehled

tato stránka poskytuje přehled architektury vysoké úrovně pro tři běžné scénáře při nasazení a správě zařízení Microsoft HoloLens 2 v rámci podniku.

Správa zařízení a přístup k prostředkům vaší organizace je často určována podle faktorů, které jsou už na místě. v závislosti na vaší stávající infrastruktuře vás vyzveme ke kontrole společného stylu správy zařízení (MDM) v následujících scénářích a potom si můžete přečíst téma [plánování nasazení HoloLens 2 v komerčním prostředí](hololens-core-components.md) , abyste zjistili, který scénář vyhovuje vašim potřebám. K dispozici jsou také tři odpovídající příručky pro použití během nasazování.


 1. [Průvodce nasazením propojeného prostředí v cloudu](hololens2-cloud-connected-overview.md)
     1. [Příručka pro nasazení prostředí připojeného k cloudu (externí klienti)](hololens2-deployment-guide.md)
 1. [Průvodce nasazením podnikové sítě](hololens2-corp-connected-overview.md)
 1. [Průvodce nasazením zabezpečeného prostředí offline](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Scénář A: nasazení na zařízení připojená do cloudu

Tento scénář je porovnatelný z důvodů nasazení spravovaných mobilních zařízení v rámci společnosti. HoloLens 2 je nasazená pro použití primárně v prostředích, která jsou externí pro podnikovou síť. Firemní prostředky nejsou dostupné nebo můžou být omezené prostřednictvím sítě VPN. 
 * Základní běžné konfigurace
   * Wi-Fi sítě jsou obvykle plně otevřené pro Internet a cloudové služby.
   * Připojení k Azure AD pomocí automatického zápisu správy mobilních zařízení (MDM) – spravovaná MDM (Intune)
   * Uživatelé se přihlásí pomocí vlastního podnikového účtu (Azure AD).
     * Podporuje se jeden nebo víc uživatelů na zařízení.
   * Různé úrovně konfigurace uzamčení zařízení se aplikují v závislosti na specifických případech použití, od úplného otevření do veřejného terminálu s jednou aplikací.
   * Jedna nebo víc aplikací se nasazuje přes MDM.

* Běžné výzvy
   * určení, které konfigurace MDM se mají použít na HoloLens 2 na základě požadavků na scénář

[![Scénář A diagram ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

odpovídající průvodce připojeným ke cloudu popisuje, jak zaregistrovat HoloLens 2 do správy zařízení, použít licence podle potřeby a ověřit, že koncoví uživatelé můžou hned používat funkci vzdálená pomoc při instalaci zařízení. Pomocí Průvodce externími klienty nasaďte zařízení do vzdálené lokality pro krátkodobé nebo dlouhodobé externí použití.

> [!div class="nextstepaction"]
> [Průvodce nasazením propojeného prostředí v cloudu](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [Příručka pro nasazení prostředí připojeného k cloudu (externí klienti)](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>Scénář B: nasazení v síti vaší organizace

tento scénář je stejný jako klasický vývoj pro většinu Windows 10 počítačů. HoloLens 2 je nasazená pro použití primárně v podnikové síti s přístupem k interním podnikovým prostředkům. Internetové a cloudové služby můžou být omezené. 

 * Základní běžné konfigurace
   * Wi-Fi síť je interní podniková síť s přístupem k interním prostředkům a omezeným přístupem k internetovým nebo cloudovým službám.
   * Připojení k Azure AD s automatickým zápisem MDM
   * Spravovaná MDM (Intune)
   * Uživatelé se přihlásí pomocí vlastního podnikového účtu (Azure AD).
     * Podporuje se jeden nebo víc uživatelů na zařízení.
   * Různé úrovně konfigurace uzamčení zařízení se aplikují v závislosti na specifických případech použití, od úplného otevření do veřejného terminálu s jednou aplikací.
   * Jedna nebo víc aplikací se nasazuje přes MDM.

 * Běžné výzvy
   * HoloLens 2 nepodporuje místní službu AD join ani SCCM. Jenom Azure AD JOIN s MDM. mnoho společností dnes ještě v tomto scénáři nasazuje Windows 10 počítače, jako jsou místní zařízení připojená k AD, spravovaná pomocí System Center Configuration Manager (SCCM) a nemusí mít nasazenou a nakonfigurovanou infrastrukturu pro správu interních Windows 10 zařízení přes cloudová řešení MDM.
   * jak HoloLens 2 je první cloudové zařízení, spoléhá se na internetovou a cloudovou službu připojenou pro ověřování uživatelů, aktualizace operačního systému, správu MDM a tak dále. při připojování k podnikové síti bude pravděpodobně nutné upravit pravidla Proxy serveru nebo brány Firewall tak, aby povolovala přístup pro HoloLens 2 a aplikace, které na něm běží.
   * Připojení k podnikovému Wi-Fi obvykle vyžaduje certifikáty k ověření zařízení nebo uživatele v síti. požadovaná infrastruktura nebo nastavení pro nasazení certifikátů do zařízení Windows 10 prostřednictvím MDM může být náročná na konfiguraci.

[![Diagram ](images/deployment-guides-revised-scenario-b-01-1.png) scénáře B1](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagram ](images/deployment-guides-revised-scenario-b-02-1.png) scénáře v B2](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

odpovídající příručka k podnikové síti obsahuje pokyny k tomu, jak zaregistrovat HoloLens 2 do vaší stávající správy zařízení, použít licence podle potřeby a ověřit, že koncoví uživatelé můžou pracovat s průvodcem Dynamics 365 a také používat vlastní obchodní aplikace po nastavení zařízení.

> [!div class="nextstepaction"]
> [Průvodce nasazením podnikové sítě](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>Scénář C: nasazení v zabezpečeném prostředí offline

Toto je typické nasazení pro vysoce zabezpečená nebo důvěrná místa. HoloLens 2 je nasazen pro použití primárně v režimu offline bez přístupu k síti nebo internetu. 
 * Základní běžné konfigurace
   * Připojení Wi-Fi je zakázané. V případě potřeby může být v případě potřeby povolená síť Ethernet přes USB.
   * Nespravováno
   * Místní uživatelský účet pro přihlášení zařízení.
     * HoloLens 2 podporuje pouze jeden místní účet.
   * Různé úrovně konfigurace uzamčení zařízení se používají prostřednictvím zřizovacích balíčků na základě konkrétních případů použití. Tyto konfigurace jsou obvykle omezené z důvodu požadavků na zabezpečení prostředí.
   * Jedna nebo víc aplikací se nasazuje prostřednictvím zřizovacího balíčku.

 * Běžné výzvy
   * Prostřednictvím zřizovacích balíčků je k dispozici omezená sada konfigurací.
   * cloudové služby se nedají použít, proto omezení možností HoloLens 2.
   * Vyšší režijní náklady na správu, protože tato zařízení musí být nastavená, nakonfigurovaná a aktualizovaná ručně.

[![Offline zabezpečený diagram 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

odpovídající průvodce zabezpečenou nápovědou poskytuje pokyny pro použití ukázkového zřizovacího balíčku, který bude uzamknout HoloLens 2 pro použití v zabezpečených prostředích.

> [!div class="nextstepaction"]
> [Průvodce nasazením zabezpečeného prostředí offline](hololens-common-scenarios-offline-secure.md)


