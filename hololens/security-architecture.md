---
title: Architektura zabezpečení HoloLens
description: Architektura zabezpečení
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, hololens 2, hololens2 security, security overview, security architecture, architecture, hololens 2 architecture
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d8e68f73d05db397a7ee088382e82dfa762177b0
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379223"
---
# <a name="security-overview-and-architecture"></a>Přehled a architektura zabezpečení

Architektura zabezpečení HoloLens 2 byla od základů navržena a zkonstruována tak, aby byla bez problémů se staršími verzemi zabezpečení a zároveň byla vytvořena minimální úroveň útoku. Tato nová inovativní architektura nabízí zabezpečená umístění úložiště a pokročilé prvky zabezpečení s mechanismy, které umožňují chránit operační systémy před potenciálními hrozbami a ohroženími zabezpečení.

HoloLens 2 kombinuje hardware, software, sítě a služby pro zajištění koncového zabezpečení a současně poskytuje uživatelům optimální prostředí. S HoloLens 2 je teď velká většina funkcí zabezpečení zapnutá automaticky, což minimalizuje úsilí potřebné ke správnému nastavení a konfiguraci operačního systému.

Windows HoloLens 2 a architektura operačního systému nabízejí tyto inovativní funkce zabezpečení:

  * **Oddělení** a izolace stavu: Tato nová architektura chrání důležité části operačního systému HoloLens 2 před změnou – například ty, které jsou nutné pro spuštění základního operačního systému do důvěryhodného stavu. Technologie izolace se používá k omezení nedůvěryhodných aplikací v oblasti sandboxu, aby se zajistilo, že nemohou ovlivnit zabezpečení systému. Celý operační systém je segmentovaný do zabezpečených sekcí, z nichž každá je chráněná kombinací různých technologií zabezpečení.
  
  * **Ochrana dat:** Pokud dojde ke ztrátě nebo odcizení zařízení uživatele, Zabrání HoloLens 2 neoprávněným aplikacím ve čtení citlivých informací tím, že spoléhá na šifrování dat nástrojem BitLocker. 
  
  * **Operační systém bez hesla:** Starší operační systémy založené na heslech mohly nechtěně vystavit uživatele hrozbám útokům phishing a často byly zodpovědné za ohrožené účty. Windows Holographic for Business eliminuje použití hesel pro přihlášení k MSA a Azure AD a posiluje ochranu identit uživatelů pomocí Windows Hello™ a FIDO2. 
  
    > [!NOTE]
    > Pokud chcete mít podporu FIDO2, musí být zařízení v buildu 19041 nebo novějším. 

  * **Zabezpečení sítě:** HoloLens 2 nabízí uživatelům vyšší zabezpečení sítě prostřednictvím vylepšených protokolů a výchozích nastavení.
