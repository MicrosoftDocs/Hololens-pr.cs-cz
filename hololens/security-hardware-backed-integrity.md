---
title: Integrita zálohovaná hardwarem a ověření identity za běhu
description: Integrita zálohovaná hardwarem a ověření identity za běhu
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.prod: hololens
ms.topic: article
keywords: zabezpečení, hololens, integrita zálohovaných hardwaru, ověření identity za běhu, rozhraní uefi, zabezpečené spouštění uefi, zabezpečené spouštění, TPM, ochrana před hrozbami, Windows Assurance proti persistenci, integrita kódu, ochrana kódu,
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: de12231b87c028ed9d8ca785a5b351fc4cb1c6fd8dbe304e4baaccd6803c5f6a
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665399"
---
# <a name="hardware-backed-integrity-and-runtime-attestation"></a>Integrita zálohovaná hardwarem a ověření identity za běhu

Integrita zálohovaná v rámci hardwaru a ověřování za běhu chrání před hrozbami, které vznikly před začátkem operačního systému, během modulu runtime, když zařízení používá hardware a služby vzdáleného ověření identity, aby se zajistila integrita při spuštění a v celé době běhu.

## <a name="uefi-secure-boot"></a>Zabezpečené spouštění UEFI

HoloLens 2 vynutila vždy zabezpečené spouštění rozhraní UEFI (Unified Extensible Firmware Interface) (uefi) a rozhraní uefi se spustí jenom Windows Holographic for Business.
zabezpečené spouštění zajišťuje, že se u celého spouštěcího řetězu ověří integrita a že se Windows vždycky spustí se správnými zásadami zabezpečení, které se na něj vztahují. Přečtěte si další informace o [zabezpečeném spouštění](/windows-hardware/design/device-experiences/oem-secure-boot).

## <a name="tpm"></a>TPM

ČIP TPM (Trusted Platform Module) je specializovaný čip na zařízení koncového bodu. HoloLens 2 používá čip TPM 2,0, který zajišťuje izolaci klíčů vynucované hardwarem. Přečtěte si další informace o [základních modulech TPM](/windows/security/information-protection/tpm/tpm-fundamentals).

## <a name="persistence-access-threat-protection"></a>Ochrana před hrozbami pro zajištění trvalého přístupu

Cílem většiny kyberútokům je zachovat trvalý přístup k zařízení. v případě kybernetická zachovávání této trvalosti umožňuje napadené zařízení Windows připojit se k botnetu, prodávat přístup k zařízení nebo jiným uživatelům nekalé nebo povolit opakovanou krádeži dat. V rámci cílených útoků je trvalá trvalá úspěšná cyberattack – ať už na zařízení nebo (častěji), celou síť.  

Ve skutečnosti se cílené útoky považují za "rozšířené trvalé hrozby", protože jejich strategické potřeby udržují přístup k cílovému zařízení nebo síti. z tohoto důvodu Windows Holographic for Business považuje ochranu proti trvalosti naprosto zásadní a používá technologii ochrany před trvalým zajištěním, aby ironclad zákazníky provedli příslib zabezpečení.

### <a name="secure-boot"></a>Zabezpečené spuštění

HoloLens 2 vynutilo zabezpečené spouštění rozhraní UEFI (Unified Extensible Firmware Interface) (UEFI) ve všech základních stavech operačního systému. rozhraní UEFI spustí jenom důvěryhodné platformy microsoftu, což zajistí, že se u celého spouštěcího řetězu ověří integrita a že se Windows vždycky spustí se správnými zásadami zabezpečení, které se na něj vztahují. HoloLens 2 neprovádí zabezpečené spouštění, které není vypnuté, ani nepovoluje spouštěcí zavaděč třetích stran.

> [!Tip]
> Přečtěte si další informace o [zabezpečeném spouštění](/windows-hardware/design/device-experiences/oem-secure-boot).

### <a name="windows-anti-persistence-assurance"></a>Windows Záruka proti trvalosti

HoloLens 2 ochrana proti perzistenci zaručuje, že uživatelé i v vzácných situacích, kdy došlo k narušení běhu systému, jako je vzdálené zneužití – taková událost by byla zmírněna se zachováním veškerého škodlivého kódu ze systému pouhým vypnutím zařízení. aby bylo možné lépe posílit ochranu proti perzistenci, HoloLens 2 přizpůsobila výkonnou ochranu integrity a na základě nich byly vloženy ochrany jen pro čtení.

Trvalá data operačního systému ve formě dat jsou stále možná, pokud uživatel neprovede resetování zařízení (PBR) na tlačítku, které vymaže všechny proměnlivé oddíly. i když je trvalá trvalá i neproměnlivé oddíly, musí uživatel vytvořit PBR HoloLens 2, aby bylo možné z proměnlivých částí odstranit případná trvalá trvalá hrozba.

## <a name="code-integrity-protection"></a>Ochrana integrity kódu

Integrita kódu (CI) je klíčovou vlastností zabezpečení moderního operačního systému. Vynucování CI umožňuje rozhodování o zabezpečení, protože zaručuje, že provenience kódu je transparentní jak pro uživatele, tak pro operační systém. Úplná integrita kódu musí být rozšířena o poslední podepsání binárního obrázku a zahrnovat vynucení modulu runtime, jako je integrita toku řízení a dynamické omezení kódu. CI je důležité, aby se zabránilo více třídám útoků, včetně sociálních techniků, jako je ransomwarem, zneužití vzdáleného spouštění kódu a různých dalších tříd útoku.
