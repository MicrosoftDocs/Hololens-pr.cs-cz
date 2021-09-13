---
title: HoloLens architektura zabezpečení
description: Architektura zabezpečení
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: zabezpečení, HoloLens, HoloLens 2, zabezpečení hololens2, Přehled zabezpečení, Architektura zabezpečení, architektura, architektura HoloLens 2
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d8e68f73d05db397a7ee088382e82dfa762177b0
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036010"
---
# <a name="security-overview-and-architecture"></a>Přehled zabezpečení a architektura

architektura zabezpečení HoloLens 2 byla navržená a inženýrovaná od základu až po dobu od starších problémů se zabezpečením a zároveň při vytváření minimalizovaného prostoru pro útoky. Tato nová, inovativní architektura nabízí zabezpečené umístění úložiště a rozšířené prvky zabezpečení, s mechanismy schopnými chránit operační systémy před potenciálními hrozbami a ohroženími zabezpečení.

HoloLens 2 kombinuje hardware, software, sítě a služby, aby poskytovaly ucelené zabezpečení a zároveň poskytoval uživatelům optimální prostředí. u HoloLens 2 se teď automaticky zapne velká většina funkcí zabezpečení, což minimalizuje úsilí potřebné ke správnému nastavení a konfiguraci operačního systému.

Windows HoloLens 2 a architektura operačního systému nabízí tyto inovativní funkce zabezpečení:

  * **oddělení a izolace stavu**: tato nová architektura chrání kritické části operačního systému HoloLens 2 před změnou, například ty, které se vyžadují pro spuštění základního operačního systému do důvěryhodného stavu. Technologie izolace se používá k omezené nedůvěryhodných aplikací v oblasti izolovaného prostoru (sandbox), což zajistí, že nebudou mít vliv na zabezpečení systému. Celý operační systém je rozdělen do oddílů zabezpečení s každou sekcí chráněnou kombinací různých technologií zabezpečení.
  
  * **ochrana dat**: pokud dojde ke ztrátě nebo odcizení zařízení uživatele, HoloLens 2 zabraňuje neoprávněným aplikacím v čtení citlivých informací, protože se spoléhá na šifrování dat nástrojem BitLocker. 
  
  * **Operační systém bez hesla**: starší operační systémy založené na heslech můžou nechtěně vystavit uživatelům podvodné hrozby a často se zodpovídá za napadené účty. Windows Holographic for Business eliminují použití hesel pro přihlášení k MSA a Azure AD a posílí ochranu identity uživatelů pomocí Windows Hello™ a přihlášení FIDO2. 
  
    > [!NOTE]
    > Aby bylo možné podporovat FIDO2, musí být zařízení na buildu 19041 nebo vyšší. 

  * **zabezpečení sítě**: HoloLens 2 nabízí uživateli zvýšené zabezpečení sítě prostřednictvím vylepšených protokolů a výchozích nastavení.
