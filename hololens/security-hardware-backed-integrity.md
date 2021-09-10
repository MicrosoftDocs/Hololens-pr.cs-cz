---
title: Integrita a ověření modulu runtime s hardwarovou zálohou
description: Integrita a ověření modulu runtime s hardwarovou zálohou
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.prod: hololens
ms.topic: article
keywords: security, hololens, Hardware backed integrity, runtime attestation, UEFI, UEFI secure boot, secure boot, TPM, threat protection, Windows Anti-Persistence Assurance, code integrity, code protection,
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 037f9325555244314518c81d7814bf983c345af6
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428445"
---
# <a name="hardware-backed-integrity-and-runtime-attestation"></a>Integrita s hardwarovým zabezpečením a ověření modulu runtime

Integrita a ověřování modulu runtime s hardwarovým zabezpečením chrání před hrozbami, které vznikly před spuštěním operačního systému, za běhu, kdy zařízení používá hardware a služby vzdáleného ověření, aby se zajistila integrita při spuštění a během doby běhu.

## <a name="uefi-secure-boot"></a>Zabezpečené spouštění UEFI

HoloLens 2 vynucuje zabezpečené spouštění rozhraní UEFI (Unified Extensible Firmware Interface) vždy a rozhraní UEFI se spustí pouze Windows Holographic for Business.
Zabezpečené spouštění zajišťuje, že je ověřený celý řetěz spouštění a že Windows vždy spustí se správnými použitými zásadami zabezpečení. Přečtěte si další informace [o zabezpečeném spouštění.](/windows-hardware/design/device-experiences/oem-secure-boot)

## <a name="tpm"></a>TPM

Čip specifikace TPM (Trusted Platform Module) (TPM) je specializovaný čip na zařízení koncového bodu. HoloLens 2 používá čip TPM 2.0, který poskytuje hardwarově vynucenou izolaci klíčů. Přečtěte si další [informace o základech čipu TPM.](/windows/security/information-protection/tpm/tpm-fundamentals)

## <a name="persistence-access-threat-protection"></a>Ochrana před internetovou hrozbou pro trvalost přístupu

Cílem většiny kybernetických útoků je udržovat trvalý přístup k zařízení. V případě ky Windows berzlomyslné ochrany umožňuje udržování této trvalosti ohrožené zařízení připojit se k botnetu, prodávat přístup k zařízení nebo jiným nekalé uživatele nebo umožnit opakované krádeže dat. Ve světě cílených útoků je trvalost nezbytná pro úspěšný kybernetický útok – ať už na zařízení nebo (častěji) v celé síti.  

Cílové útoky se ve skutečnosti považují za "pokročilé trvalé hrozby", protože jejich strategická potřeba udržovat přístup k cílovému zařízení nebo síti. Z tohoto důvodu Windows Holographic for Business bránit trvalosti, která je naprosto nezbytná, a používá technologii odolnosti proti trvalosti k tomu, aby se přisliboval pro zabezpečení zákazníků.

### <a name="secure-boot"></a>Zabezpečené spuštění

HoloLens 2 vynucuje zabezpečené spouštění rozhraní UEFI (Unified Extensible Firmware Interface) ve všech stavech základního operačního systému. Rozhraní UEFI spustí pouze důvěryhodné platformy Microsoftu, které zajistí, aby byl celý řetěz spouštění ověřený z integrity a že se Windows vždy spustí se správnými použitými zásadami zabezpečení. HoloLens 2 neumožňuje vypnout zabezpečené spouštění ani neumožňuje zavaděče spouštění třetích stran.

> [!Tip]
> Další informace o [zabezpečeném spouštění.](/windows-hardware/design/device-experiences/oem-secure-boot)

### <a name="windows-anti-persistence-assurance"></a>Windows Anti-Persistence Assurance

HoloLens 2 zaručuje svým uživatelům, že i ve výjimečných situacích, kdy dojde k ohrožení systému za běhu ( například při vzdáleném zneužití ), bude taková událost zmírněna odstraněním veškerého škodlivého kódu ze systému pouhým vypnutím zařízení. Aby bylo možné ochranu proti trvalosti ještě více posílit, HoloLens 2 přidala výkonnou ochranu integrity a zasadila ochranu jen pro čtení.

Trvalost dat operačního systému ve formě dat je stále možná, pokud uživatel nezačlení resetování tlačítkem zařízení, které vymaže všechny mutable oddíly. I když je trvalost neměnných oddílů mnohem obtížnější, uživatel musí PBR použít HoloLens 2, aby se z mutable částí odstranila jakákoli možná trvalost hrozeb.

## <a name="code-integrity-protection"></a>Ochrana integrity kódu

Integrita kódu (CI) je klíčovou vlastností zabezpečení moderního operačního systému. Vynucování CI umožňuje zvuková rozhodnutí o zabezpečení, protože zaručuje, že původ kódu bude pro uživatele i operační systém transparentní. Úplná integrita kódu musí rozšířit minulé podepisování binárních obrázků a zahrnout vynucení modulu runtime, jako je integrita toku řízení a dynamická omezení kódu. CI je důležité k tomu, aby se zabránilo více třídám útoků, včetně socialy inženýrovaných malwaru, jako je ransomware, zneužití vzdáleného spouštění kódu a různé další třídy útoku.
