---
title: Šifrování a ochrana dat
description: Seznamte se s šifrováním a ochranou dat na HoloLens 2, včetně integrace BitLockeru a Azure.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, Encryption, Data Protection, BitLocker Device, BitLocker, bitlocker, bitlocker encryption, azure integration,
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: e156fc21bfd1541dd8718a7349e7ba82b45576be
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639365"
---
# <a name="encryption-and-data-protection"></a>Šifrování a ochrana dat

Šifrování a ochrana dat chrání data v případě ztráty nebo odcizení zařízení a brání neoprávněným aplikacím v přístupu k citlivým informacím.

## <a name="bitlocker-device-encryption"></a>Šifrování zařízení nástrojem BitLocker

BitLocker je funkce šifrování plného svazku pro ochranu integrity médií jen pro čtení a ochranu osobních údajů zapisovatelného média.  Od svého vzniku se jedná o efektivní ochranu před neoprávněným přístupem k datům během offline útoků. HoloLens 2 ve výchozím nastavení povolí nástroj BitLocker Šifrování zařízení (BDE) k ochraně dat před neoprávněným fyzickým přístupem k zařízení. Microsoft se neustále vyvíjí, aby splňoval potřeby budoucnosti, a nadále investuje a vylepšuje tuto technologii.

BDE je funkce ochrany dat, která využívá šifrování AES-XTS-256 na všech svazcích v rozložení zařízení odděleném stavem. BDE poskytuje šifrování na úrovni zařízení v rozložení odděleném stavem. BitLocker Šifrování zařízení na svazkech operačního systému a pevných dat automaticky a nemůže být vypnutý, a to ani správci IT, takže zařízení je vždy chráněné.

Šifrovací klíče BDE se pak používají k transparentním dešifrování binárních souborů a dat požadovaných ke spuštění zařízení. Když se svazek operačního systému odemkne a systém se bude spustit, stanou se další svazky přístupné pomocí verze ochrany automatického odemknutí specifické pro svazek. K zajištění ochrany osobních údajů uživatelů nejsou k dispozici žádné další ochrany a jednotku je možné odemknout pouze na stejném zařízení. Vynucení jen pro čtení (RO) na požadovaných svazcích se aplikuje a vynucuje okamžitě od prvního spuštění. Obnovovací klíč bitlockeru není v životním cyklu nástroje HoloLens 2 potřeba.

## <a name="azure-integration"></a>Integrace Azure 

HoloLens 2 umožňuje zákazníkům integrovat svá zařízení se službami Azure. Komunikace mezi HoloLens 2 a Azure používá protokol TLS (Transport Layer Security) k ochraně dat mezi sebou a cloudovými službami, které poskytují silné ověřování, ochranu osobních údajů a integritu zpráv. Všechny služby Azure plně podporují protokol TLS 1.2 a všechny služby, ve kterých zákazníci používají pouze protokol TLS 1.2, přijímají přenosy pouze protokolu TLS 1.2. Standardy šifrování dat během přenosu v Azure jsou podrobně uvedené v [přehledu šifrování Azure.](/azure/security/fundamentals/encryption-overview) Další informace o osvědčených postupech pro zabezpečení a šifrování dat Azure najdete v dokumentaci k [Azure.](/azure/security/fundamentals/data-encryption-best-practices) 

OneDrive, což je příklad integrace cloudu s HoloLens 2, obsahuje funkci automatického nahrání, která umožňuje automaticky nahrávat soubory a dokumenty do cloudu při připojení k internetu. Pozastavení automatické synchronizace souborů není možné vypnout prostřednictvím zásad, ale je možné ji přímo konfigurovat prostřednictvím uživatelského rozhraní. 
