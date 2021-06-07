---
title: Šifrování a ochrana dat
description: Přečtěte si o šifrování a ochraně dat na zařízeních HoloLens 2, včetně integrace BitLockeru a Azure.
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
ms.openlocfilehash: ebe1d072f36cdf4ad9b3543882e61fa2ed4a0300
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379222"
---
# <a name="encryption-and-data-protection"></a>Šifrování a ochrana dat

Šifrování a ochrana dat chrání data v případě ztráty nebo odcizení zařízení a brání neoprávněným aplikacím v přístupu k citlivým informacím.

## <a name="bitlocker-device-encryption"></a>Šifrování zařízení nástrojem BitLocker

BitLocker je funkce šifrování plného svazku pro ochranu integrity médií jen pro čtení a ochranu osobních údajů zapisovatelného média.  Od svého vzniku se jedná o efektivní ochranu před neoprávněným přístupem k datům během offline útoků. HoloLens 2 ve výchozím nastavení Šifrování zařízení bitlockeru (BDE) k ochraně dat před neoprávněným fyzickým přístupem k zařízení. Microsoft se neustále vyvíjí, aby splňoval potřeby budoucnosti, a nadále investuje a vylepšuje tuto technologii.

BDE je funkce ochrany dat, která využívá šifrování AES-XTS-256 na všech svazcích v rozložení zařízení odděleném stavem. BDE poskytuje šifrování na úrovni zařízení v rozložení odděleném stavem. BitLocker Šifrování zařízení na svazkech operačního systému a pevných dat automaticky a nemůže být vypnutý, a to ani správci IT, takže zařízení je vždy chráněné.

Šifrovací klíče BDE se pak používají k transparentním dešifrování binárních souborů a dat požadovaných ke spuštění zařízení. Když se svazek operačního systému odemkne a systém se bude spustit, stanou se další svazky přístupné pomocí verze ochrany automatického odemknutí specifické pro svazek. K zajištění ochrany osobních údajů uživatelů nejsou k dispozici žádné další ochrany a jednotku je možné odemknout pouze na stejném zařízení. Vynucení jen pro čtení (RO) na požadovaných svazcích se aplikuje a vynucuje okamžitě od prvního spuštění. Obnovovací klíč Bitlockeru není v životním cyklu HoloLens 2 potřeba.

## <a name="azure-integration"></a>Integrace Azure 

HoloLens 2 umožňuje zákazníkům integrovat svá zařízení se službami Azure. Komunikace mezi zařízeními HoloLens 2 a Azure používá protokol TLS (Transport Layer Security) k ochraně dat mezi sebou a cloudovými službami, které poskytují silné ověřování, ochranu osobních údajů a integritu zpráv. Všechny služby Azure plně podporují protokol TLS 1.2 a všechny služby, ve kterých zákazníci používají pouze protokol TLS 1.2, přijímají přenosy pouze protokolu TLS 1.2. Standardy šifrování dat během přenosu v Azure jsou podrobně uvedené v [přehledu šifrování Azure.](https://docs.microsoft.com/azure/security/fundamentals/encryption-overview) Další informace o osvědčených postupech pro zabezpečení a šifrování dat Azure najdete v dokumentaci k [Azure.](https://docs.microsoft.com/azure/security/fundamentals/data-encryption-best-practices) 

OneDrive, příklad integrace cloudu s HoloLens 2, má funkci automatického nahrávání, ve které se soubory a dokumenty po připojení k internetu automatického nahrají do cloudu. Pozastavení automatické synchronizace souborů není možné vypnout prostřednictvím zásad, ale je možné ji přímo konfigurovat prostřednictvím uživatelského rozhraní. 
