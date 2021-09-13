---
title: Konfigurace CSP a Přehled správy zařízení
description: Naučte se konfigurovat správu CSP, zásad a zařízení pomocí správy mobilních zařízení a zřizovacích balíčků.
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
ms.openlocfilehash: b312f9d20c9a75c5e4c1906c4ec55f42fda977f6
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032167"
---
# <a name="configure-csps-and-device-management-overview"></a>Konfigurace CSP a Přehled správy zařízení

správci IT můžou definovat a implementovat nastavení zásad na HoloLens 2. Nastavení konfigurace, která použijete, se budou lišit v závislosti na scénáři nasazení a podniková zařízení budou nabízet nejširší škálu ovládacích prvků. v Windows 10 jsou poskytovatelé konfiguračních služeb (CSP) s rozhraním pro čtení, nastavení, úpravu nebo odstranění nastavení konfigurace na zařízení. Tato nastavení se mapují na klíče registru nebo soubory. Někteří poskytovatelé konfigurační služby podporují formát WAP, některé podporují SyncML a některé podporují.

další informace o zprostředkovatelích Windows 10 Holographic pro správu zařízení najdete v tématu úplný seznam [csp podporovaných v HoloLens zařízeních](/windows/client-management/mdm/configuration-service-provider-reference#hololens).
správci IT taky můžou na zařízeních spravovat zprostředkovatele csp v úplném seznamu [csp zásad, které podporuje HoloLens 2](/windows/client-management/mdm/policy-csps-supported-by-hololens2).

## <a name="configuration-methods"></a>Metody konfigurace

### <a name="configure-with-mdm"></a>Konfigurace pomocí MDM

Zprostředkovatele CSP a zásady je možné snadno spravovat na jakémkoli osobním nebo podnikovém zařízení zaregistrovaném v systému MDM. Jakmile je zařízení zaregistrované v řešení MDM, budete moct spravovat toto zařízení nebo sadu zařízení pomocí konfigurací zařízení. přečtěte si další informace o tom, jak [spravovat zařízení HoloLens prostřednictvím MDM](hololens-mdm-configure.md).

### <a name="configure-with-provisioning-packages"></a>Konfigurace pomocí zřizovacích balíčků

HoloLens 2 taky podporuje nastavení omezené sady konfigurací CSP pro zařízení HoloLens 2 prostřednictvím vlastních zřizovacích balíčků. Zřizovací balíčky se typicky využívají pro zařízení spravovaná bez MDM a vyžadují ruční použití na každé zařízení. Přečtěte si informace o vytváření vlastních [zřizovacích balíčků pro HoloLens](hololens-provisioning.md).

## <a name="configurations"></a>Konfigurace

### <a name="common-device-restrictions"></a>Běžná omezení zařízení

Některá omezení zařízení jsou jednoduchá a zakázaná funkce nebo připojení k zařízení. Další informace o těchto možnostech najdete v tématu o [běžných omezeních zařízení.](hololens-common-device-restrictions.md)

### <a name="kiosk-modes"></a>Celoobrazovkový režimy

Celoobrazovkový režim použijte k řízení, které identity mají přístup k aplikacím, které jsou ve výchozím nastavení k dispozici. Veřejné terminály je možné použít pro jednu aplikaci nebo více možností uživatelského rozhraní aplikace. Konfigurace veřejného terminálu jsou v rozsahu od jediné aplikace pro kohokoli, kdo zařízení používá, k různým výběrům aplikací pro různé skupiny. Beznabídkový režim nezastaví spouštěním jiných aplikací povolené aplikace a nebylo zamýšleno pro minulosti. Přečtěte si další informace [o beznabídkovém režimu a o tom, jak je používat](hololens-kiosk.md).

### <a name="settings-page-visibility"></a>Nastavení Viditelnost stránky

pomocí Nastavení zásady aplikace můžete řídit, které identity mají ve výchozím nastavení přístup k nastavením. pomocí této zásady můžete Nastavení aplikaci nakonfigurovat tak, aby buď zobrazovala jenom stránky pro výběr, nebo aby se skryly všechny vybrané stránky. [Přečtěte si o tom, jak konfigurovat dostupné stránky](settings-uri-list.md).

tato funkce je v tuto chvíli dostupná jenom v [Windows buildy Insider](hololens-insider.md). Ujistěte se, že zařízení, pro která chcete tuto funkci používat, jsou na 19041.1349 sestavení +.

### <a name="wdac"></a>WDAC

Pomocí konfigurace WDAC můžete řídit, které aplikace a procesy jsou povolené nebo Nepovolit, aby se spustily bez ohledu na to, jestli je systém v celoobrazovkovém režimu nebo ne.
[Podívejte se na náš přehled pro WDAC.](windows-defender-application-control-wdac.md)
