---
ms.openlocfilehash: d96a769b40daba0948f8f3c71a88513576c531b5
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859206"
---
# <a name="non-aad-configuration"></a>[Konfigurace jiného typu než AAD](#tab/nonaadlogon)

#### <a name="non-aad-configuration"></a>Konfigurace jiného typu než AAD

1. Vytvořte zřizovací balíček, který:
    1. Nakonfiguruje nastavení modulu runtime/AssignedAccess tak, aby umožňoval účty návštěvníků.
    1. Volitelně můžete zařízení zaregistrovat v MDM (nastavení modulu runtime/pracoviště/registrace), aby se mohlo spravovat později.
    1. Nevytvářet místní účet
2. [Použijte zřizovací balíček](../hololens-provisioning.md).

# <a name="aad-configuration"></a>[Konfigurace AAD](#tab/aadlogon)

#### <a name="aad-configuration"></a>Konfigurace AAD

Zařízení připojená k AAD nakonfigurovaná pro celoobrazovkový režim se můžou přihlásit k účtu návštěvníka jedním klepnutím na přihlašovací obrazovce. Po přihlášení k účtu návštěvníka se zařízení nevyzve k opětovnému přihlášení, dokud se návštěvník výslovně odhlásí z nabídky Start nebo když se zařízení nerestartuje.

Automatické přihlašování návštěvníka se dá spravovat pomocí [vlastních zásad OMA-URI](/mem/intune/configuration/custom-settings-windows-10):

- Hodnota identifikátoru URI:./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Zásady | Description | Konfigurace |
| --------------------------- | ------------- | -------------------- |
| MixedReality/VisitorAutoLogon | Umožňuje návštěvníkovi automatické přihlašování do veřejného terminálu. | 1 (Ano), 0 (ne, výchozí) |