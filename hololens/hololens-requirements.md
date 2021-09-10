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
ms.openlocfilehash: 5a4f251f3ca6eae5e85e4d763074e035039159cb
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428077"
---
# <a name="common-deployment-scenarios"></a>Běžné scénáře nasazení

## <a name="overview"></a>Přehled

Zjištění, jak nasadit nové zařízení, může být při prvním pokusu o jeho nasazení problém. Tady sdílíme různé způsoby nasazení a správy Microsoft HoloLens 2 zařízení v rámci organizace.

Chcete řešení nasadit ve velkém měřítku. Chceme vás tam dostat. Nejprve si promluvme o postupu nasazení zařízení, tedy hologramů k dosažení hodnoty pro váš cílový scénář hybridní reality, ať už používáte D365 Remote Assist, příručky nebo aplikaci s povolenou službou Azure mixed reality, kterou jste vytvořili.

Můžete být pracovníkem s rozhodovací pravomocí v oblasti obchodu, IT profesionálem nebo týmem pro inovace, který se HoloLens ve vaší organizaci. Jak budete stavět od důkazu konceptu až po škálované nasazení, naši průvodci nasazením HoloLens v rámci vaší IT infrastruktury – bez ohledu na to, jak velká nebo malá. Nejběžnější jsou následující scénáře nasazení:

| Scenario |Využití | Klíčové body |
|---------|---------|---------|
| [Scénář A: Zařízení připojená ke cloudu](hololens2-cloud-connected-overview.md) | Když poprvé zahájíte nasazení, můžete začít v malém a nasadit jedno zařízení připojené ke cloudu, abyste viděli základní proces. | Zařízení budou připojená ke cloudovým službám a veřejnému internetu. To je nejvhodnější pro případy zákaznického použití, služby v terénu a doklad o konceptu.|
| [Scénář B: Síť organizace](hololens2-corp-connected-overview.md) | Při nasazení do produkčního prostředí ve velkém měřítku možná budete muset integraci s vlastní sítí organizace. | Zařízení budou připojená k podnikové síti Wi-Fi. To je nejvhodnější pro interní uživatele nebo použití v rámci podnikového prostředí.|
| [Scénář C: Zabezpečené offline prostředí](hololens-common-scenarios-offline-secure.md) | Některé klíčové procesy nebo některé firemní zásady mohou požadovat použití offline prostředí. | Zařízení budou připojená k vysoce omezující síti nebo budou čistě offline. To je nejvhodnější pro vysoce zabezpečená prostředí nebo omezení připojení k internetu ve vzdálených oblastech. |

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Scénář A: Nasazení do zařízení připojených ke cloudu

Tento scénář je srovnatelný s nasazením spravovaných mobilních zařízení v rámci společnosti. HoloLens 2 se nasazovat pro použití primárně v prostředích mimo podnikovou síť. K podnikovým prostředkům se přistupuje nebo je možné, že budou omezené prostřednictvím sítě VPN.

[![Diagram scénáře A](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

### <a name="when-to-use"></a>Kdy je použít

Vezměte v úvahu tento model nasazení pro:

* Nasazení důkazu konceptu, pilotních nasazení a služeb v terénu
* Nasazení [vzdáleného nástroje Remote Assist](hololens2-options-remote-assist.md)

### <a name="basic-common-configurations"></a>Základní běžné konfigurace

* Wi-Fi sítě jsou obvykle plně otevřené pro internet a cloudové služby.
* Připojení ke službě Azure AD s Správa zařízení mobilních zařízení (MDM) – spravovaná pomocí MDM (Intune)
* Uživatelé se přihlašují pomocí vlastního podnikového účtu (Azure AD).
  * Podpora jednoho nebo více uživatelů na zařízení
* Na základě konkrétních případů použití, od plně otevřeného až po beznabitový terminál s jednou aplikací, se používají různé úrovně konfigurací uzamčení zařízení.
* Jedna nebo více aplikací se nasadí přes MDM.

### <a name="common-challenges"></a>Běžné problémy

* Určení konfigurací MDM, které se mají použít pro HoloLens 2 na základě požadavků scénáře

Odpovídající příručka připojená ke cloudu popisuje, jak zaregistrovat HoloLens 2 do správy zařízení, jak podle potřeby použít licence a ověřit, že koncoví uživatelé mohou vzdálenou pomoc při nastavení zařízení okamžitě používat.

> [!div class="nextstepaction"]
> [Průvodce nasazením v připojeném cloudu](hololens2-cloud-connected-overview.md)

Pomocí příručky Externí klienti nasaďte zařízení do vzdálené lokality pro krátkodobé nebo dlouhodobé externí použití.

> [!div class="nextstepaction"]
> [Průvodce nasazením připojení ke cloudu (externí klienti)](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>Scénář B: Nasazení v síti vaší organizace

Tento scénář je stejný jako u klasického nasazení pro většinu Windows 10 počítačů. HoloLens 2 je nasazená pro použití primárně v podnikové síti s přístupem k interním podnikovým prostředkům. Internet a cloudové služby mohou být omezené. 

[![Diagram scénáře B1](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagram scénáře B2](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

### <a name="when-to-use"></a>Kdy je použít

Vezměte v úvahu tento model nasazení pro:

* Interní uživatelé
* Nasazení ve velkém měřítku (pilotní a produkční) v rámci podnikového prostředí

### <a name="basic-common-configurations"></a>Základní běžné konfigurace

* Wi-Fi je interní podniková síť s přístupem k interním prostředkům a omezeným přístupem k internetu nebo cloudovým službám.
* Připojení ke službě Azure AD s automatickou registrací MDM
* Správa MDM (Intune)
* Uživatelé se přihlašují pomocí vlastního podnikového účtu (Azure AD).
  * Podpora jednoho nebo více uživatelů na zařízení
* Na základě konkrétních případů použití, od plně otevřeného až po beznabitový terminál s jednou aplikací, se používají různé úrovně konfigurací uzamčení zařízení.
* Jedna nebo více aplikací se nasadí přes MDM.

### <a name="common-challenges"></a>Běžné problémy

* HoloLens 2 nepodporuje připojení k místní službě AD ani System Center Configuration Manager (SCCM). K MDM se připojuje jenom Azure AD. Mnoho společností v tomto scénáři stále nasazovat počítače Windows 10 jako místní zařízení připojená k AD, spravovaná pomocí SCCM a nemusí mít nasazenou nebo nakonfigurovanou infrastrukturu pro správu interních zařízení Windows 10 prostřednictvím cloudových řešení MDM.
* Protože HoloLens 2 je první zařízení v cloudu, při ověřování uživatelů, aktualizacích operačního systému, správě MDM atd. do značné míry spoléhá na služby připojené k internetu a cloudu. Při připojování k podnikové síti bude pravděpodobně potřeba upravit pravidla proxy serveru nebo brány firewall, aby byl povolen přístup pro HoloLens 2 a aplikace, které na ní běží.
* Podnikové Wi-Fi připojení obvykle vyžaduje certifikáty k ověření zařízení nebo uživatele v síti. Konfigurace požadované infrastruktury nebo nastavení pro nasazení certifikátů Windows 10 zařízení prostřednictvím MDM může být náročná.

Odpovídající příručka Pro podnikové připojení instruuje, jak zaregistrovat HoloLens 2 do stávající správy zařízení, jak podle potřeby použít licence a ověřit, že koncoví uživatelé mohou po nastavení zařízení používat příručku Dynamics 365 a také používat vlastní obchodní aplikace.

> [!div class="nextstepaction"]
> [Průvodce nasazením připojení k podnikové síti](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>Scénář C: Nasazení v zabezpečeném offline prostředí

Toto je typické nasazení pro vysoce zabezpečená nebo důvěrná umístění. HoloLens 2 je nasazená pro použití primárně offline bez přístupu k síti nebo internetu.

[![Offline zabezpečený diagram 1.](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

### <a name="when-to-use"></a>Kdy je použít

Vezměte v úvahu tento model nasazení pro:

* Vysoce zabezpečená prostředí, ve kterých je potřeba uchovávat data na místě
* "Prostředí", kde budou zařízení používat veřejnost
* Problém s připojením k internetu ve vzdálené oblasti

### <a name="basic-common-configurations"></a>Základní běžné konfigurace

* Wi-Fi připojení je zakázané. Ethernet přes USB může být v případě potřeby povolený pro připojení k síti LAN.
* Nespravovaná
* Místní uživatelský účet pro přihlášení zařízení
  * HoloLens 2 podporuje pouze jeden místní účet
* Prostřednictvím zřizovací balíčky se na základě konkrétních případů použití používají různé úrovně konfigurací uzamčení zařízení. Tyto konfigurace jsou obvykle omezené z důvodu požadavků na zabezpečené prostředí.
* Jedna nebo více aplikací se nasadí prostřednictvím zřizovacího balíčku.

### <a name="common-challenges"></a>Běžné problémy

* Prostřednictvím zřizovacích balíčků je k dispozici omezená sada konfigurací.
* Cloudové služby není možné používat, a proto je možné omezit HoloLens 2.
* Vyšší režijní náklady na správu, protože tato zařízení musí být nastavená, nakonfigurovaná a aktualizovaná ručně.

Odpovídající průvodce zabezpečením offline poskytuje pokyny pro použití ukázkového zřizovacího balíčku, který uzamkne HoloLens 2 pro použití v zabezpečených prostředích.

> [!div class="nextstepaction"]
> [Průvodce nasazením zabezpečeného prostředí offline](hololens-common-scenarios-offline-secure.md)
