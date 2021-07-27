---
title: Běžné scénáře nasazení
description: přečtěte si další informace o nasazení a správě HoloLens v podnikovém prostředí, včetně infrastruktury, Azure Active Directory a správy mobilních zařízení.
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
ms.openlocfilehash: 529dde590c30d4a51fa8ae61e9d37d22170dc271
ms.sourcegitcommit: 5130823947caffd2a444e9d8fb15cd24cbb6414c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/24/2021
ms.locfileid: "114659059"
---
# <a name="common-deployment-scenarios"></a>Běžné scénáře nasazení

## <a name="overview"></a>Přehled

Když si vyzkoušíte, jak nasadit nové zařízení, může být bojovat při prvním spuštění. tady sdílíme různé způsoby nasazení a správy zařízení Microsoft HoloLens 2 v rámci organizace.

Chcete, aby byla řešení nasazená ve velkém měřítku. Chceme vás získat. Nejdřív se podíváme na postup nasazení zařízení, tedy na hologramy, abyste dosáhli hodnoty pro váš cílový scénář hybridní reality, ať už používáte D365 Remote Assist, příručky nebo aplikaci s podporou služby Azure Mixed reality, kterou jste vytvořili.

může se jednat o obchodní rozhodnutí, tvůrce IT specialisty nebo inovační tým, který se pokouší přijmout HoloLens v rámci vaší organizace. při sestavování z hlediska konceptu na nasazení s více instancemi jsou naše příručky pro nasazení smyslem HoloLens v rámci IT infrastruktury – bez ohledu na to, jak velká nebo malá. Nejběžnější jsou následující scénáře nasazení:

| Scenario |Využití | Klíčové body |
|---------|---------|---------|
| [Scénář A: zařízení připojená ke cloudu](hololens2-cloud-connected-overview.md) | Když začnete s nasazením, můžete začít malým a nasazovat jenom jedno zařízení připojené ke cloudu, abyste viděli základní proces. | Zařízení budou připojená ke cloudovým službám a k veřejnému Internetu. To je nejvhodnější pro případy použití zákazníků, služby pro pole a zkoušku konceptu.|
| [Scénář B: síť organizace](hololens2-corp-connected-overview.md) | Při nasazení do produkčního měřítka možná budete muset integrovat se sítí vaší organizace. | Zařízení budou připojená k podnikové síti Wi-Fi. To je nejvhodnější pro interní uživatele nebo použití v rámci podnikového prostředí.|
| [Scénář C: offline zabezpečené prostředí](hololens-common-scenarios-offline-secure.md) | Některé důležité procesy nebo některé podnikové zásady můžou vyžadovat použití offline prostředí. | Zařízení budou připojená k vysoce omezující síti nebo budou čistě offline zařízení. To je nejvhodnější pro vysoce zabezpečená prostředí nebo pro omezení připojení k internetu ve vzdálených oblastech. |

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>Scénář A: nasazení na zařízení připojená do cloudu

Tento scénář je porovnatelný z důvodů nasazení spravovaných mobilních zařízení v rámci společnosti. HoloLens 2 je nasazená pro použití primárně v prostředích, která jsou externí pro podnikovou síť. Firemní prostředky nejsou dostupné nebo můžou být omezené prostřednictvím sítě VPN.

[![Scénář A diagram](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

### <a name="when-to-use"></a>Kdy je použít

Vezměte v úvahu tento model nasazení pro:

* Nasazení ověření konceptu, pilotů a služeb pro pole
* Nasazení [vzdálené pomoci](hololens2-options-remote-assist.md)

### <a name="basic-common-configurations"></a>Základní běžné konfigurace

* Wi-Fi sítě jsou obvykle plně otevřené pro Internet a cloudové služby.
* Připojení k Azure AD pomocí automatického zápisu správy mobilních zařízení (MDM) – spravovaná MDM (Intune)
* Uživatelé se přihlásí pomocí vlastního podnikového účtu (Azure AD).
  * Podporuje se jeden nebo víc uživatelů na zařízení.
* Různé úrovně konfigurace uzamčení zařízení se aplikují v závislosti na specifických případech použití, od úplného otevření do veřejného terminálu s jednou aplikací.
* Jedna nebo víc aplikací se nasazuje přes MDM.

### <a name="common-challenges"></a>Běžné výzvy

* určení, které konfigurace MDM se mají použít na HoloLens 2 na základě požadavků na scénář

odpovídající průvodce připojeným ke cloudu popisuje, jak zaregistrovat HoloLens 2 do správy zařízení, použít licence podle potřeby a ověřit, že koncoví uživatelé můžou hned používat funkci vzdálená pomoc při instalaci zařízení.

> [!div class="nextstepaction"]
> [Průvodce nasazením připojeným ke cloudu](hololens2-cloud-connected-overview.md)

Pomocí Průvodce externími klienty nasaďte zařízení do vzdálené lokality pro krátkodobé nebo dlouhodobé externí použití.

> [!div class="nextstepaction"]
> [Příručka pro nasazení propojených do cloudu (externí klienti)](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>Scénář B: nasazení v síti vaší organizace

tento scénář je stejný jako klasický vývoj pro většinu Windows 10 počítačů. HoloLens 2 je nasazená pro použití primárně v podnikové síti s přístupem k interním podnikovým prostředkům. Internetové a cloudové služby můžou být omezené. 

[![Diagram scénáře B1](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![Diagram scénáře v B2](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

### <a name="when-to-use"></a>Kdy je použít

Vezměte v úvahu tento model nasazení pro:

* Interní uživatelé
* Nasazení ve velkém měřítku (pilotní a produkční) v podnikovém prostředí

### <a name="basic-common-configurations"></a>Základní běžné konfigurace

* Wi-Fi síť je interní podniková síť s přístupem k interním prostředkům a omezeným přístupem k internetovým nebo cloudovým službám.
* Připojení k Azure AD s automatickým zápisem MDM
* Spravovaná MDM (Intune)
* Uživatelé se přihlásí pomocí vlastního podnikového účtu (Azure AD).
  * Podporuje se jeden nebo víc uživatelů na zařízení.
* Různé úrovně konfigurace uzamčení zařízení se aplikují v závislosti na specifických případech použití, od úplného otevření do veřejného terminálu s jednou aplikací.
* Jedna nebo víc aplikací se nasazuje přes MDM.

### <a name="common-challenges"></a>Běžné výzvy

* HoloLens 2 nepodporuje místní připojení AD ani System Center Configuration Manager (SCCM). Jenom Azure AD JOIN s MDM. mnoho společností dnes ještě v tomto scénáři nasazuje Windows 10 počítače jako místní zařízení připojená k AD, spravovaná nástrojem SCCM a nemusí mít nasazenou nebo nakonfigurovanou infrastrukturu pro správu interních Windows 10ch zařízení prostřednictvím cloudových řešení MDM.
* jak HoloLens 2 je první cloudové zařízení, spoléhá se na internetovou a cloudovou službu připojenou pro ověřování uživatelů, aktualizace operačního systému, správu MDM a tak dále. při připojování k podnikové síti bude pravděpodobně nutné upravit pravidla proxy serveru nebo brány firewall tak, aby povolovala přístup pro HoloLens 2 a aplikace, které na něm běží.
* Připojení k podnikovému Wi-Fi obvykle vyžaduje certifikáty k ověření zařízení nebo uživatele v síti. požadovaná infrastruktura nebo nastavení pro nasazení certifikátů do zařízení Windows 10 prostřednictvím MDM může být náročná na konfiguraci.

odpovídající podniková příručka vám dá pokyn k registraci HoloLens 2 do vaší stávající správy zařízení, uplatnění licencí podle potřeby a ověření, že koncoví uživatelé můžou pracovat s průvodcem Dynamics 365, a také můžou po nastavení zařízení použít vlastní obchodní aplikace.

> [!div class="nextstepaction"]
> [Příručka k nasazení v podnikovém prostředí](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>Scénář C: nasazení v zabezpečeném prostředí offline

Toto je typické nasazení pro vysoce zabezpečená nebo důvěrná místa. HoloLens 2 je nasazen pro použití primárně v režimu offline bez přístupu k síti nebo internetu.

[![Offline zabezpečený diagram 1](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

### <a name="when-to-use"></a>Kdy je použít

Vezměte v úvahu tento model nasazení pro:

* Vysoce zabezpečená prostředí, ve kterých je potřeba uchovávat data v domu
* "Prostředí", kde veřejné budou zařízení používat
* Potíže s připojením k internetu ve vzdálené oblasti

### <a name="basic-common-configurations"></a>Základní běžné konfigurace

* Připojení Wi-Fi je zakázané. V případě potřeby může být pro připojení k místní síti LAN povolený Ethernet přes USB.
* Nespravované
* Místní uživatelský účet pro přihlášení zařízení
  * HoloLens 2 podporuje jenom jeden místní účet.
* Různé úrovně konfigurace uzamčení zařízení se používají prostřednictvím zřizovacích balíčků na základě konkrétních případů použití. Tyto konfigurace jsou obvykle omezené z důvodu požadavků na zabezpečení prostředí.
* Jedna nebo víc aplikací se nasazuje prostřednictvím zřizovacího balíčku.

### <a name="common-challenges"></a>Běžné výzvy

* Prostřednictvím zřizovacích balíčků je k dispozici omezená sada konfigurací.
* cloudové služby se nedají použít, proto omezení možností HoloLens 2.
* Vyšší režijní náklady na správu, protože tato zařízení musí být nastavená, nakonfigurovaná a aktualizovaná ručně.

odpovídající průvodce zabezpečenou nápovědou poskytuje pokyny pro použití ukázkového zřizovacího balíčku, který bude uzamknout HoloLens 2 pro použití v zabezpečených prostředích.

> [!div class="nextstepaction"]
> [Průvodce nasazením zabezpečeného prostředí offline](hololens-common-scenarios-offline-secure.md)
