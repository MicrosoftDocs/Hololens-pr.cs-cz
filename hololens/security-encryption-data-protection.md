---
title: Šifrování a ochrana dat
description: přečtěte si o šifrování a ochraně dat na zařízeních HoloLens 2, včetně nástroje BitLocker a integrace Azure.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: zabezpečení, HoloLens, šifrování, ochrana dat, zařízení s BitLockerem, BitLocker, BitLocker, šifrování nástrojem BitLocker, Integrace Azure
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: cd1d3ae238924537b1d36f4acdf239f0dc644326827d2c6041ceb94b013b3801
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665501"
---
# <a name="encryption-and-data-protection"></a>Šifrování a ochrana dat

Šifrování a ochrana dat chrání data v případě ztráty nebo odcizení zařízení a zabraňuje neautorizovaným aplikacím v přístupu k citlivým informacím.

## <a name="bitlocker-device-encryption"></a>Šifrování zařízení nástrojem BitLocker

BitLocker je plná funkce šifrování, která chrání integritu média jen pro čtení (RO) a ochranu osobních údajů pro zapisovatelné médium.  Vzhledem k tomu, že je jeho zahájením, bylo to efektivní proti neoprávněnému přístupu k datům během offline útoků. HoloLens 2 ve výchozím nastavení povoluje šifrování zařízení pomocí nástroje Bitlocker (Bitlocker) k ochraně dat před jakýmkoli neautorizovaným fyzickým přístupem k zařízení. Společnost Microsoft stále vyvíjí a vylepšuje tuto technologii, a to i nadále, aby splňovala potřeby budoucích potřeb.

BDE je funkce ochrany dat, která využívá šifrování AES-XTS-256 na všech svazcích v rozložení zařízení odděleném stavem. BDE poskytuje šifrování na úrovni zařízení v rozložení odděleném stavem. Šifrování zařízení BitLockeru je povolené automaticky v operačních systémech a pevných datových svazcích a nedá se vypnout, i když správci IT, aby bylo zařízení vždycky chráněné.

Šifrovací klíče BDE se pak používají k transparentnímu dešifrování binárních souborů a k datům potřebným ke spuštění zařízení. Jelikož je svazek operačního systému odemčený a systém se spouští, budou k dispozici další svazky pomocí verze ochrany pro automatické odemknutí určenou svazkem. Žádné další ochrany nejsou k dispozici pro zachování ochrany osobních údajů uživatelů a tuto jednotku lze odemknout pouze na jednom zařízení. Vynucování a vynucování oprávnění jen pro čtení (RO) na požadovaných svazcích se projeví okamžitě počínaje prvním spuštěním. v životním cyklu HoloLens 2 není potřebný obnovovací klíč bitlockeru.

## <a name="azure-integration"></a>Integrace Azure 

HoloLens 2 umožňuje zákazníkům integrovat jejich zařízení se službami Azure. komunikace mezi zařízeními HoloLens 2 a Azure používá protokol TLS (Transport Layer Security) k ochraně dat mezi sebou samými a cloudových služeb, které poskytují silné ověřování, soukromí zpráv a integritu. Všechny služby Azure plně podporují protokol TLS 1,2 a všechny služby, ve kterých zákazníci používají jenom TLS 1,2, přijímají jenom přenosy TLS 1,2. Standardy šifrování Azure pro přenos dat při přenosu jsou podrobně popsané v článku [Přehled šifrování Azure](/azure/security/fundamentals/encryption-overview). Další informace o [osvědčených postupech pro zabezpečení a šifrování dat Azure](/azure/security/fundamentals/data-encryption-best-practices)najdete v dokumentaci k Azure. 

OneDrive příklad cloudové integrace s HoloLens 2 má funkci automatického nahrávání, do které se soubory a dokumenty můžou automaticky nahrávat do cloudu, když se připojí k internetu. Pozastavení automatických synchronizací souborů se nedá vypnout prostřednictvím zásad, ale dá se přímo konfigurovat prostřednictvím uživatelského rozhraní. 
