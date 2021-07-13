---
title: používání služby Endpoint Manager intune microsoftu ke správě zařízení HoloLens
description: naučte se používat MDM ke konfiguraci CSP, zásad a správě HoloLens zařízení se smíšeným realitou ve velkém měřítku pomocí intune.
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
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640269"
---
# <a name="using-microsofts-endpoint-manager-intune-to-manage-hololens-devices"></a>používání služby Endpoint Manager intune microsoftu ke správě zařízení HoloLens

Přes MDM můžete spravovat řadu různých nastavení. Používání zařízení Intune je možné seskupit dohromady a konfigurace je možné nasadit do těchto skupin uživatelů nebo zařízení. Aplikace je také možné nasadit a spravovat, nastavovat zařízení pro připojení k síti a také konfigurovat aktualizace, které se mají provést v požadovaném čase a v případě potřeby aktualizačního vyzvánění. 

## <a name="how-to-manage-via-intune"></a>Jak spravovat přes Intune

### <a name="device-categories-and-groups"></a>Kategorie a skupiny zařízení
Pomocí Intune můžete vytvořit kategorie zařízení, které budou automaticky přidávat zařízení do skupin na základě kategorií, které vytvoříte, například technického, lékařského, vývojáře a tak dále. Cílem je usnadnit správu zařízení s Windows Holographic for Business.
Další informace: [kategorizace zařízení do skupin](/mem/intune/enrollment/device-group-mapping)

### <a name="device-configuration-profiles"></a>Konfigurační profily zařízení
Intune obsahuje nastavení a funkce, které můžete různým zařízením v organizaci povolit nebo zakázat. Tato nastavení a funkce se spravují pomocí profilů. můžete například vytvořit profil, který umožňuje Cortana nebo na zařízeních s Windows Holographic for Business používá inteligentní obrazovku Microsoft defenderu.
V profilech můžete k přizpůsobení některých nastavení, vytvoření omezení pro zařízení a konfiguraci sítí VPN a Wi-Fi použít OMA-URI.
[Začínáme s konfiguračními profily](/mem/intune/configuration/device-profiles)a [přehledem profilů](/mem/intune/configuration/device-profile-create).

## <a name="examples-of-what-can-be-managed-and-configured"></a>Příklady toho, co je možné spravovat a konfigurovat

Použití MDM ke správě zařízení nabízí nejrůznější položky, které se dají vybrat. 

### <a name="wi-fi"></a>Wi-Fi
[Nastavení Wi-Fi](/mem/intune/configuration/wi-fi-settings-configure) přiřadí uživatelům a zařízením nastavení bezdrátové sítě. Když přiřadíte profil Wi-Fi, uživatelé získají přístup k firemním Wi-Fi, aniž by ji museli konfigurovat sami.
Další informace o [konfiguraci sítě pro HoloLens](hololens-commercial-infrastructure.md)

### <a name="certificates"></a>Certifikáty
Certifikáty zlepšují zabezpečení tím, že poskytují ověřování účtu, Wi-Fi ověřování, šifrování sítě VPN a šifrování SSL webového obsahu. I když správci můžou certifikáty na zařízeních spravovat ručně prostřednictvím zřizovacích balíčků, je osvědčeným postupem použití systému MDM ke správě certifikátů v celém celém životním cyklu – od registrace po obnovení a odvolání. Systém MDM může tyto certifikáty po registraci zařízení automaticky nasadit do úložišť certifikátů zařízení (Pokud systém MDM podporuje Simple Certificate Enrollment Protocol (SCEP) nebo #12 veřejného klíče kryptografie (PKCS # 12)). MDM taky může dotazovat a odstraňovat zaregistrované klientské certifikáty nebo aktivovat novou žádost o registraci před vypršením platnosti aktuálního certifikátu. 

### <a name="proxy"></a>Proxy server
Většina podnikových intranetových sítí využívá proxy server ke správě interního provozu. pomocí HoloLens 2 můžete nakonfigurovat proxy server připojení ethernet a Wi-Fi. Tato nastavení se nevztahují na připojení VPN. další podrobnosti o nastaveních proxy serveru pro Windows 10 najdete v tématu [NetworkProxy CSP](/windows/client-management/mdm/networkproxy-csp).

### <a name="vpn"></a>Síť VPN
Organizace často používají síť VPN k řízení přístupu k aplikacím a prostředkům na intranetu své společnosti. HoloLens 2 podporuje připojení SSL vpn, která vyžadují modul plug-in ke stažení z Microsoft Store a jsou specifická pro dodavatele VPN podle vašeho výběru. 
- Přečtěte si další informace o [síti VPN v HoloLens](hololens-network.md#vpn).
- Další podrobnosti o profilech sítě VPN najdete v tématu [CSP pro podpora vpnv2](/windows/client-management/mdm/vpnv2-csp).

### <a name="deploy-and-manage-apps"></a>Nasazení a správa aplikací
V Intune můžete do zařízení s Windows Holographic for Business přidat aplikace. Řešení pro správu mobilních zařízení umožňuje IT tvůrcům a správcům IT nastavovat soukromou automatickou automatickou instalaci (nabízené) podnikové aplikace nebo si koupit aplikace v obchodě pro skupinu uživatelů. Existují různé způsoby nasazování aplikací:
-   [intune a Portál společnosti]( app-deploy-intune.md)
-   [Microsoft Store pro firmy]( app-deploy-store-business.md)

Přečtěte si další informace o správě aplikací prostřednictvím Intune.
-   [Přidání aplikací do Intune](/mem/intune/apps/apps-add)
-   [Přidání aplikací z Microsoft Storu](/mem/intune/apps/store-apps-windows)
-   [Přidání vytvořených aplikací](/mem/intune/apps/lob-apps-windows)
- [Přiřazení aplikací skupinám](/mem/intune/apps/apps-deploy)

### <a name="software-updates"></a>Aktualizace softwaru
V Intune je funkce Aktualizační kanály zařízení s Windows 10. Tyto aktualizační kanály zahrnují skupinu nastavení, která určují, jak se budou aktualizace instalovat. Pro instalaci aktualizací můžete třeba vytvořit časové období údržby nebo můžete zvolit, že po instalaci aktualizací chcete zařízení restartovat. Aktualizační kanál můžete použít pro více zařízení s Windows Holographic for Business.
přečtěte si další informace o tom, jak [spravovat HoloLens aktualizace](hololens-updates.md) a [spravovat aktualizace softwaru přes intune](/mem/intune/protect/windows-update-for-business-configure).

### <a name="configure-kiosk-mode"></a>Konfigurace beznabídkového režimu
Pomocí funkcí sdíleného nebo hostovaného počítače dostupných v Intune můžete na zařízeních s Windows Holographic for Business nakonfigurovat beznabídkový režim. Na těchto zařízení může běžet jen jedna aplikace (beznabídkový režim s jednou aplikací), nebo několik aplikací (beznabídkový režim s více aplikacemi). Celoobrazovkový režim je uživatelské rozhraní, které určuje, které identity mají přístup k aplikacím, které jsou ve výchozím nastavení k dispozici.
přečtěte si, jak [nastavit HoloLens jako veřejný terminál]( hololens-kiosk.md) .

