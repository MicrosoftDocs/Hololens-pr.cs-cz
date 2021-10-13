---
title: Microsoft Store pro firmy
description: Zjistěte, jak pracovat s Microsoft Store pro firmy a publikovat aplikace hybridní reality pro vaši firmu.
keywords: Microsoft Store pro firmy, msfb, nasazení aplikace, store
author: evmill
ms.author: v-evmill
ms.date: 10/13/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
ms.openlocfilehash: 5bc719539aaa254b8aacb05e24554152231f7e5a
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924326"
---
# <a name="microsoft-store-for-business"></a>Microsoft Store pro firmy

Tato [Microsoft Store pro firmy](/microsoft-store/microsoft-store-for-business-overview) je určená primárně pro správce a s rozhodovací pravomocí v oblasti IT ve firmách nebo organizacích s flexibilním způsobem, jak najít, získat, spravovat a distribuovat bezplatné a placené aplikace na vybraném trhu a Windows 10 zařízení v objemu. 

Můžete spravovat Microsoft Store a privátní obchodní aplikace v jednom inventáři a podle potřeby přiřazovat a znovu používat licence. Můžete také zvolit nejlepší způsob distribuce pro vaši organizaci: přímo přiřazovat aplikace jednotlivcům a týmům, publikovat aplikace na soukromé stránky v Microsoft Store nebo se připojit pomocí řešení pro správu a získat tak další možnosti.

Pokud Microsoft Store pro firmy koncový uživatel použije, spustí aplikaci Microsoft Store aplikace. Po spuštění bude uživatel moct vybrat kartu s názvem organizace, zobrazí se jim aplikace, které mají k dispozici, nebo toto zařízení.

> [!Note]
> Microsoft Store pro firmy automaticky nestáhne (push) aplikace do zařízení. Aplikace ze služby Microsoft Store pro firmy ale mohou být přidružené k vašemu serveru pro správu zařízení (MDM), aby bylo možné cílit aplikace a synchronizovat je se zařízeními.

Další informace o používání této služby najdete na následujících Microsoft Store pro firmy:

* [Úrovně oprávnění používané pro instalaci aplikací](/mem/intune/configuration/device-restrictions-windows-holographic#app-store)
* [Přidání aplikace do Storu pro firmy](/mem/intune/apps/store-apps-windows)
* [Přiřazení aplikací ke skupinám zaměstnanců](/mem/intune/apps/windows-store-for-business)

Pokud chcete přidružit Microsoft Store pro firmy, přejděte na [stránku Přidružení Microsoft Store pro firmy k Intune.](/mem/intune/apps/windows-store-for-business#associate-your-microsoft-store-for-business-account-with-intune)

> [!Tip]
> Přečtěte si další [informace o distribuci offline aplikací při](/microsoft-store/distribute-offline-apps) použití aplikací, jako je Advanced Recovery Companion (ARC) a Windows Configuration Designer (WCD).

## <a name="use-only-private-store-apps-for-microsoft-store"></a>Pro Microsoft Store používejte jenom aplikace pro privátní Microsoft Store

- Zavedená v [Windows Holographic verze 21H2](hololens-release-notes.md#windows-holographic-version-21h2).

Zásady RequirePrivateStoreOnly jsou povolené pro HoloLens. Tato zásada umožňuje konfiguraci Microsoft Store tak, aby se v aplikaci nakonfiguroval jenom privátní obchod nakonfigurovaný pro vaši organizaci. Omezení přístupu pouze na aplikace, které jste k dispozici.

Další informace o [ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)

## <a name="smart-retry-for-app-updates"></a>Inteligentní opakování pro aktualizace aplikací

- Zavedená v [Windows Holographic verze 21H2](hololens-release-notes.md#windows-holographic-version-21h2).

Nově povolená pro HoloLens je nová zásada, která správcům IT umožňuje nastavit opakované nebo jedno časové datum pro restartování aplikací, jejichž aktualizace selhala kvůli tomu, že se aplikace používá a umožňuje instalaci aktualizace. Můžete je nastavit na základě několika různých triggerů, jako je například naplánovaný čas nebo přihlášení. Další informace o použití této zásady najdete v tématu [ApplicationManagement/ScheduleForceRestartForUpdateFailures.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)