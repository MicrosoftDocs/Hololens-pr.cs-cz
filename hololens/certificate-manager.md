---
title: Správce certifikátů
description: naučte se, jak ručně instalovat, spravovat a odebírat certifikáty na zařízeních HoloLens 2 mixed reality.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 8b1869e786e3f3324494cecbfd596f61811e1893
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032171"
---
# <a name="certificate-manager"></a>Správce certifikátů

- Vylepšené auditování, diagnostika a nástroje ověřování pro zabezpečení zařízení a dodržování předpisů prostřednictvím nového správce certifikátů. Tato funkce vám umožní nasadit, řešit potíže a ověřit škálování vašich certifikátů v komerčních prostředích.

v Windows holografická verze 20H2 přidáváme do aplikace HoloLens 2 Nastavení správce certifikátů. přejít na **Nastavení > aktualizace & certifikátů zabezpečení >**. Tato funkce poskytuje jednoduchý a uživatelsky přívětivý způsob zobrazení, instalace a odebrání certifikátů na vašem zařízení. Díky novému Správci certifikátů a správcům a uživatelům teď vylepšili Nástroj pro auditování, diagnostiku a ověřování, aby zařízení zůstala zabezpečená a kompatibilní. 

-   **Auditování:** Možnost ověřit, jestli je certifikát správně nasazený, nebo ověřit, že se certifikát odebral správně. 
-   **Diagnostika:** V případě problémů se ověří, že na zařízení existují vhodné certifikáty, které šetří čas a pomáhají při řešení problémů. 
-   **Ověření:** Ověření, že certifikát slouží k zamýšlenému účelu a je funkční, může ušetřit značný čas, zejména v komerčních prostředích před nasazením certifikátů ve větším měřítku.

Chcete-li v seznamu rychle najít konkrétní certifikát, existují možnosti řazení podle názvu, úložiště nebo data vypršení platnosti. Uživatelé můžou taky certifikát vyhledat přímo. Chcete-li zobrazit vlastnosti jednotlivých certifikátů, vyberte certifikát a klikněte na tlačítko **informace**. 

Instalace certifikátu v současné době podporuje soubory. cer a. CRT. Vlastníci zařízení mohou instalovat certifikáty v místním počítači a aktuálním uživateli.  všechny ostatní uživatele lze instalovat pouze do aktuálního uživatele.

## <a name="to-install-a-certificate"></a>Instalace certifikátu: 

1.  Připojení HoloLens 2 k počítači.
1.  soubor certifikátu, který chcete nainstalovat, umístěte do umístění na vašem HoloLens 2.
1.  přejděte na **Nastavení > aktualizace & > certifikátů zabezpečení** a vyberte nainstalovat certifikát.
1.  Klikněte na **importovat soubor** a přejděte do umístění, kam jste certifikát uložili.
1.  Vyberte **umístění úložiště**.
1.  Vyberte **úložiště certifikátů**.
1.  Klikněte na **Install** (Nainstalovat).

Certifikát by se teď měl nainstalovat na zařízení.

![prohlížeč certifikátů v aplikaci Nastavení v části certifikáty.](images/certificate-viewer-device.jpg)

![obrázek ukazující, jak použít uživatelské rozhraní certifikátu k instalaci certifikátu v Nastavení.](images/certificate-device-install.jpg)

## <a name="to-remove-a-certificate"></a>Odebrání certifikátu:

> [!WARNING]
> pomocí správce certifikátů můžou uživatelé odebrat jenom certifikáty nainstalované přímo z uživatelského rozhraní Nastavení. Pokud byl certifikát nainstalován jiným způsobem, musí být také odebrán stejným mechanismem a nelze jej odebrat ze Správce certifikátů. I když můžete zobrazit certifikáty nasazené v MDM ve Správci certifikátů, nemůžete je odinstalovat ve Správci certifikátů. Musíte je odinstalovat přes MDM.

1. přejděte na **Nastavení App > aktualizace a > certifikáty zabezpečení**.
1. Ve vyhledávacím poli vyhledejte certifikát podle názvu.
1. Vyberte certifikát.
1. Klikněte na **Odebrat** .
1. Po zobrazení výzvy k potvrzení vyberte **Ano** .

