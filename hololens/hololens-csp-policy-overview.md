---
title: Konfigurace CSP a Správa zařízení služby
description: Zjistěte, jak nakonfigurovat CSP, zásady a správu zařízení pomocí mobile Správa zařízení a zřizovací balíčky.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 60e73a9a70a70c5c583edc73a0add2f0f502ef80
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377681"
---
# <a name="configure-csps-and-device-management-overview"></a>Konfigurace CSP a Správa zařízení služby

Správci IT můžou definovat a implementovat nastavení zásad na HoloLens 2. Nastavení konfigurace, která použijete, se budou lišit v závislosti na scénáři nasazení a podniková zařízení budou nabízet IT co nejširší možnosti kontroly. V Windows 10 jsou poskytovatelé konfiguračních služeb (CSP) rozhraní pro čtení, nastavení, úpravu nebo odstranění konfiguračních nastavení na zařízení. Tato nastavení se mapovat na klíče nebo soubory registru. Někteří poskytovatelé konfiguračních služeb podporují formát WAP, někteří podporují SyncML a někteří podporují obojí.

Další informace o zprostředkovatelích Windows 10 Holographic správy zařízení najdete v úplném seznamu csP podporovaných [v zařízeních HoloLens.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)
Správci IT můžou také spravovat poskytovatele CSP zásad na zařízeních. Úplný seznam csP zásad [podporovaných aplikací HoloLens 2.](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## <a name="configuration-methods"></a>Metody konfigurace

### <a name="configure-with-mdm"></a>Konfigurace pomocí MDM

CsP a zásady je možné snadno spravovat na libovolném osobním nebo podnikovém zařízení zaregistrované v systému MDM. Jakmile je zařízení zaregistrované v řešení MDM, budete moct toto zařízení nebo sadu zařízení spravovat pomocí konfigurací zařízení. Přečtěte si další informace [o správě zařízení HoloLens prostřednictvím MDM.](hololens-mdm-configure.md)

### <a name="configure-with-provisioning-packages"></a>Konfigurace se zřizovacími balíčky

HoloLens 2 také podporuje nastavení omezené sady konfigurací CSP pro zařízení HoloLens 2 prostřednictvím vlastních zřizovacích balíčků. Zřizovací balíčky se obvykle využívají pro zařízení nespravovaná pomocí MDM a vyžadují ruční použití na každé zařízení. Přečtěte si informace o vytváření [vlastních zřizovacích balíčků pro HoloLens.](https://docs.microsoft.com/hololens/hololens-provisioning)

## <a name="configurations"></a>Konfigurace

### <a name="common-device-restrictions"></a>Běžná omezení zařízení

Některá omezení zařízení jsou jednoduchá a zakují funkce nebo připojení k zařízení. Další informace o těchto omezeních najdete v [běžných omezeních zařízení.](hololens-common-device-restrictions.md)

### <a name="kiosk-modes"></a>Bezobrazovkové režimy

Pomocí bezobrazovkového režimu můžete řídit, které identity mají ve výchozím nastavení přístup ke kterým aplikacím. Kiosky je možné použít pro jednu aplikaci nebo více prostředí uživatelského rozhraní aplikace. Konfigurace veřejného terminálů jsou v rozsahu od jedné aplikace pro každého, kdo zařízení používá, až po různé výběry aplikací pro různé skupiny. Bezobrazovkové režim nezabývání "povoleným aplikacím" ve spouštění jiných aplikací a nebyl nikdy zamýšlen. Další informace najdete [v článku o režimech veřejného terminálů](hololens-kiosk.md)a o tom, jak je používat.

### <a name="settings-page-visibility"></a>Nastavení viditelnosti stránky

Pomocí zásad aplikace Nastavení můžete řídit, které identity mají ve výchozím nastavení přístup k nastavení. Pomocí této zásady je možné aplikaci Nastavení nakonfigurovat tak, aby buď zobrazovat jenom vybrané stránky, nebo skrýt všechny vybrané stránky. [Přečtěte si, jak nakonfigurovat stránky, které jsou k dispozici.](settings-uri-list.md)

Tato funkce je aktuálně dostupná pouze [v Windows Insider sestaveních](hololens-insider.md). Ujistěte se, že zařízení, pro která chcete tuto funkci používat, jsou ve verzi 19041.1349 nebo více.

### <a name="wdac"></a>WDAC

Pomocí konfigurace WDAC můžete řídit, které aplikace nebo procesy se mají povolit nebo zakázat spuštění bez ohledu na to, jestli je systém v beznastavovém režimu.
[Podívejte se na náš přehled nástroje WDAC.](windows-defender-application-control-wdac.md)
