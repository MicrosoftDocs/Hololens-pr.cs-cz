---
title: Správa zařízení s Endpoint Manager Microsoftem pomocí HoloLens Intune
description: Naučte se používat MDM ke konfiguraci CSP, zásadám a správě HoloLens hybridní reality ve velkém měřítku pomocí Intune.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/9/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 5485a4b2558a11a6c0545ec8b3405c120cff287c
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427374"
---
# <a name="using-microsofts-endpoint-manager-intune-to-manage-hololens-devices"></a>Správa zařízení s Endpoint Manager Microsoftem pomocí HoloLens Intune

Existuje mnoho různých nastavení, která můžete spravovat přes MDM. Použití zařízení Intune je možné seskupit dohromady a do těchto skupin uživatelů nebo zařízení je možné nasadit konfigurace. Aplikace je také možné nasazovat a spravovat, nastavovat zařízení pro připojení k síti a konfigurovat aktualizace, které prostanou v požadovaném čase a v potřebném aktualizačním okruhu. 

## <a name="how-to-manage-via-intune"></a>Správa přes Intune

### <a name="device-categories-and-groups"></a>Kategorie a skupiny zařízení
Pomocí Intune můžete vytvářet kategorie zařízení, které automaticky přidávají zařízení do skupin na základě kategorií, které vytvoříte, jako jsou technické, lékařské, vývojářské atd. Cílem je usnadnit správu zařízení s Windows Holographic for Business.
Další informace: [Kategorizace zařízení do skupin](/mem/intune/enrollment/device-group-mapping)

### <a name="device-configuration-profiles"></a>Konfigurační profily zařízení
Intune obsahuje nastavení a funkce, které můžete různým zařízením v organizaci povolit nebo zakázat. Tato nastavení a funkce se spravují pomocí profilů. Můžete například vytvořit profil, který povolí Cortana Obrazovku Smart Screen v programu Microsoft Defender na zařízeních s Windows Holographic for Business.
V profilech můžete k přizpůsobení některých nastavení, vytvoření omezení pro zařízení a konfiguraci sítí VPN a Wi-Fi použít OMA-URI.
[Začínáme s konfiguračními profily](/mem/intune/configuration/device-profiles)a [přehledem profilu](/mem/intune/configuration/device-profile-create)

## <a name="examples-of-what-can-be-managed-and-configured"></a>Příklady toho, co je možné spravovat a konfigurovat

Použití MDM ke správě zařízení poskytuje širokou škálu položek, které je možné vybrat. 

### <a name="wi-fi"></a>Wi-Fi
[Nastavení Wi-Fi](/mem/intune/configuration/wi-fi-settings-configure) přiřadí uživatelům a zařízením nastavení bezdrátové sítě. Když přiřadíte profil Wi-Fi, uživatelé budou mít přístup k vašemu firemnímu Wi-Fi, aniž by ji museli konfigurovat sami.
Další informace [o konfiguraci sítě pro HoloLens](hololens-commercial-infrastructure.md)

### <a name="certificates"></a>Certifikáty
Certifikáty pomáhají zlepšit zabezpečení tím, že poskytují ověřování účtu, Wi-Fi ověřování, šifrování sítě VPN a šifrování SSL webového obsahu. I když správci můžou spravovat certifikáty na zařízeních ručně prostřednictvím zřizování balíčků, je osvědčeným postupem používat systém MDM ke správě těchto certifikátů v průběhu celého jejich životního cyklu – od registrace až po obnovení a odvolání. Systém MDM může tyto certifikáty automaticky nasadit do úložišť certifikátů zařízení po registraci zařízení (pokud systém MDM podporuje standardy Simple Certificate Enrollment Protocol (SCEP) nebo PKCS#12 (Public Key Cryptography Standards #12).) MDM může také dotazovat a odstraňovat zaregistrované klientské certifikáty nebo aktivovat novou žádost o registraci před vypršením platnosti aktuálního certifikátu. 

### <a name="proxy"></a>Proxy server
Většina podnikových intranetových sítí využívá ke správě interního provozu proxy server. V HoloLens 2 můžete nakonfigurovat připojení proxy server ethernetová a Wi-Fi připojení. Tato nastavení se nevztahují na připojení VPN. Další podrobnosti o nastavení proxy serveru pro Windows 10 v tématu [NetworkProxy CSP.](/windows/client-management/mdm/networkproxy-csp)

### <a name="vpn"></a>Síť VPN
Organizace často používají síť VPN k řízení přístupu k aplikacím a prostředkům na intranetu společnosti. HoloLens 2 podporuje připojení SSL VPN, která vyžadují modul plug-in ke stažení od Microsoft Store a jsou specifická pro dodavatele sítě VPN podle vašeho výběru. 
- Další informace o [síti VPN najdete na HoloLens](hololens-network.md#vpn).
- Další podrobnosti o profilech VPN najdete v tématu [VPNv2 CSP.](/windows/client-management/mdm/vpnv2-csp)

### <a name="deploy-and-manage-apps"></a>Nasazení a správa aplikací
V Intune můžete do zařízení s Windows Holographic for Business přidat aplikace. Řešení pro správu mobilních zařízení umožňuje správcům a správcům IT soukromě automaticky instalovat (nabízeně) svoje vlastní obchodní aplikace nebo nakupovat aplikace prostřednictvím Storu pro skupinu uživatelů. Existují různé způsoby nasazování aplikací:
-   [Intune a Portál společnosti]( app-deploy-intune.md)
-   [Microsoft Store pro firmy]( app-deploy-store-business.md)

Přečtěte si další informace o správě aplikací prostřednictvím Intune.
-   [Přidání aplikací do Intune](/mem/intune/apps/apps-add)
-   [Přidání aplikací z Microsoft Storu](/mem/intune/apps/store-apps-windows)
-   [Přidání vytvořených aplikací](/mem/intune/apps/lob-apps-windows)
- [Přiřazení aplikací skupinám](/mem/intune/apps/apps-deploy)

### <a name="software-updates"></a>Aktualizace softwaru
V Intune je funkce Aktualizační kanály zařízení s Windows 10. Tyto aktualizační kanály zahrnují skupinu nastavení, která určují, jak se budou aktualizace instalovat. Pro instalaci aktualizací můžete třeba vytvořit časové období údržby nebo můžete zvolit, že po instalaci aktualizací chcete zařízení restartovat. Aktualizační kanál můžete použít pro více zařízení s Windows Holographic for Business.
Přečtěte si další informace o [správě aktualizací HoloLens a](hololens-updates.md) správě aktualizací softwaru prostřednictvím [Intune.](/mem/intune/protect/windows-update-for-business-configure)

### <a name="configure-kiosk-mode"></a>Konfigurace beznabídkového režimu
Pomocí funkcí sdíleného nebo hostovaného počítače dostupných v Intune můžete na zařízeních s Windows Holographic for Business nakonfigurovat beznabídkový režim. Na těchto zařízení může běžet jen jedna aplikace (beznabídkový režim s jednou aplikací), nebo několik aplikací (beznabídkový režim s více aplikacemi). Bezobrazovový režim je uživatelské rozhraní, které řídí, které identity mají ve výchozím nastavení přístup ke kterým aplikacím.
[Zjistěte, jak nastavit HoloLens jako beziosk.]( hololens-kiosk.md)

