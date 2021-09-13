---
title: Windows Podpora registrace Autopilotu pro HoloLens 2
description: Zjistěte, jak získat podporu registrace pro Autopilot na HoloLens 2.
author: joyjaz
ms.author: v-jjaswinski
ms.date: 5/20/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: Autopilota
manager: ylempidakis
ms.openlocfilehash: cdd2ab68905d5cc82b1c5ccc50640112e857f2f4
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126035981"
---
# <a name="hololens-2-registration-support-for-autopilot"></a>HoloLens 2 Podpora registrace pro Autopilot

Zákazníci a poskytovatelé CSP (Microsoft Cloud Solution Providers) si teď mohou zaregistrovat HoloLens 2 zařízení tím, že přímo Podpora Microsoftu. Tato stránka popisuje požadavky pro následující podporované scénáře registrace Autopilotu:

- **HoloLens 2 Registrace zařízení autopilotu**. Odešle žádost o registraci HoloLens 2 zařízení do Windows Autopilotu.
- **HoloLens 2 požadavky na hodnotu hash hardwaru zařízení.** Odešle žádost Podpora Microsoftu, aby vám poskytla hardwarové hash, které zákazníci nebo csp mohou použít k samoobslužné registraci zařízení přes Microsoft Intune nebo microsoft Partnerské centrum.
- **HoloLens 2: Zrušení registrace Autopilotu zařízení.** Odešle žádost o odstranění zařízení z Windows Autopilot, která se obvykle používá v situacích, kdy zařízení končí životností.

Následující tabulka obsahuje podrobnosti o informacích, které budete muset shromáždit *před* odesláním žádostí o registraci Podpora Microsoftu.

| Požadované informace | Description | Registrace Autopilotu  | Požadavek na hodnotu hash hardwaru | Zrušení registrace Autopilotu |
------------|-------------------------------|--------------------------------------------------|------------------------------|--------------------------------|
|  Azure Active Directory ID tenanta    |    ID Azure Active Directory tenanta je globálně jedinečný identifikátor (GUID), který se liší od názvu nebo domény vaší organizace.    Pokud chcete zjistit ID tenanta, přihlaste se k [webu Azure Portal.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)    |     ✔️                         |                              |                         ✔️                        |
|  Azure Active Directory Název domény    |   Název domény nejvyšší úrovně Například contoso.com.    |     ✔️                         |                              |                         ✔️                        |
|  Doklad o vlastnictví    |   Ověřte doklad o vlastnictví tak, že nahrajete původní fakturu nebo fakturu ve formátu PDF. Snímky obrazovky nejsou akceptovány. Prodejní nebo faktura musí obsahovat následující: sériová čísla zařízení. Název společnosti.     |     ✔️                         |              ✔️                |                         ✔️                        |
|  Sériová čísla zařízení    |   Upload Excel ve formátu CSV s každým sériovým číslem zařízení na novém řádku.     |     ✔️                         |              ✔️                |                         ✔️                        |

## <a name="submit-support-requests"></a>Odeslání žádostí o podporu

> [!div class="nextstepaction"]
> [Odeslání podpory registrace Autopilotu na HoloLens 2](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
