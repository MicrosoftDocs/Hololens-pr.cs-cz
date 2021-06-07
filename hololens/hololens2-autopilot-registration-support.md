---
title: Windows Autopilot registrace zařízení HoloLens 2
description: Zjistěte, jak získat podporu registrace pro Autopilot na zařízeních HoloLens 2.
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
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379337"
---
# <a name="hololens-2-registration-support-for-autopilot"></a>Podpora registrace HoloLens 2 pro Autopilot

Zákazníci a poskytovatelé CSP (Microsoft Cloud Solution Providers) teď mohou registrovat zařízení HoloLens 2 tak, že přímo Podpora Microsoftu. Tato stránka popisuje požadavky pro následující podporované scénáře registrace Autopilotu:

- **HoloLens 2 Device Autopilot Registration**. Odešle žádost o registraci zařízení HoloLens 2 do Windows Autopilot.
- **HoloLens 2 Device Hardware Hash Request**. Odešle žádost společnosti Podpora Microsoftu, aby vám poskytla hardwarové hash, které zákazníci nebo csp mohou použít k samoobslužné registraci zařízení přes Microsoft Intune nebo microsoft Partnerské centrum.
- **HoloLens 2 Device Autopilot Deregistration**. Odešle žádost o odstranění zařízení z Windows Autopilot, která se obvykle používá v případě ukončení životnosti zařízení.

Následující tabulka obsahuje podrobnosti o informacích, které budete muset shromáždit *před* odesláním žádostí o registraci Podpora Microsoftu.

| Požadované informace | Description | Registrace Autopilotu  | Požadavek na hodnotu hash hardwaru | Zrušení registrace Autopilotu |
------------|-------------------------------|--------------------------------------------------|------------------------------|--------------------------------|
|  Azure Active Directory ID tenanta    |    ID Azure Active Directory tenanta je globálně jedinečný identifikátor (GUID), který se liší od názvu nebo domény vaší organizace.    Pokud chcete zjistit ID tenanta, přihlaste se k [webu Azure Portal.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)    |     ✔️                         |                              |                         ✔️                        |
|  Azure Active Directory název domény    |   Název domény nejvyšší úrovně Například contoso.com.    |     ✔️                         |                              |                         ✔️                        |
|  Doklad o vlastnictví    |   Ověřte doklad o vlastnictví tak, že nahrajete původní fakturu nebo fakturu ve formátu PDF. Snímky obrazovky nejsou akceptovány. Prodejní nebo faktura musí obsahovat následující: sériová čísla zařízení. Název společnosti.     |     ✔️                         |              ✔️                |                         ✔️                        |
|  Sériová čísla zařízení    |   Nahrajte excelový soubor ve formátu CSV se sériovým číslem každého zařízení na novém řádku.     |     ✔️                         |              ✔️                |                         ✔️                        |

## <a name="submit-support-requests"></a>Odeslání žádostí o podporu

> [!div class="nextstepaction"]
> [Odeslání podpory registrace Autopilotu pro HoloLens 2](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
