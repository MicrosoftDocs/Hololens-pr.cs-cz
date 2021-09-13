---
title: HoloLens referenčních informací k beziosku
description: Informace a ukázky pro bezobrazovkové terminály na HoloLens zařízeních.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/24/2021
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9f8cfd0013ac5b8cf85a334cbb89c458440820d9
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032244"
---
# <a name="hololens-kiosk-reference-information"></a>HoloLens Referenční informace k beziosku

Tato stránka obsahuje užitečné informace pro nastavení HoloLens zařízení v bezobrazovkovém režimu. Mezi tyto odkazy patří identifikátory AUMID pro aplikace doručené pošty a vyhledání vaší aplikace a několik ukázek XML pro beznaioskový režim, které jsou od několika úprav od toho, abyste je připravili pro několik různých scénářů. Informace o nastavení veřejného terminálu najdete na stránce Nastavení veřejného [terminálu.](hololens-kiosk.md)

## <a name="hololens-application-user-model-ids-aumids"></a>HoloLens ID modelů uživatelů aplikací (AUMID)  

Obecné informace o tom, jak zvolit aplikace v bezobrazovkovém režimu, najdete v tématu Pokyny pro výběr aplikace pro přiřazený přístup [(bezioskový režim).](/windows/configuration/guidelines-for-assigned-access-app)

Pokud ke konfiguraci beziosku používáte systém Mobile Správa zařízení (MDM) nebo zřizovací balíček, použijete k určení aplikací poskytovatele konfiguračních služeb [AssignedAccess.](/windows/client-management/mdm/assignedaccess-csp) CSP používá k identifikaci aplikací ID aplikačních modelů [(AUMID).](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) V následující tabulce jsou uvedené identifikátory AUMID některých aplikací, které můžete použít v beznaiosku s více aplikacemi.

<a id="aumids"></a>

|Název aplikace |AUMID |
| --- | --- |
|3D prohlížeč |Microsoft.Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft.Microsoft3DViewer |
|Kalendář |microsoft.windowscommunicationsapps \_ 8wekyb3d8bbwe \! microsoft.windowslive.calendar |
|Kamera<sup>1, 2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Microsoft.549981C3F5F10 \_ 8wekyb3d8bbwe \! App |
|Výběr zařízení v HoloLens (1. generace) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|Výběr zařízení na HoloLens 2 |Microsoft. Windows. DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft.Windows. DevicesFlowHost |
|Průvodci Dynamics 365 |Microsoft.Dynamics365.Guides \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft.MicrosoftRemoteAssst \_ 8wekyb3d8bbwe \! Microsoft.RemoteAssst |
|Centrum &nbsp; feedback |Aplikace Microsoft.WindowsFeedbackHub \_ 8wekyb3d8bbwe \! |
|Průzkumník souborů |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy! App |
|Poštovní |microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail |
|Starý Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge |
|Nový Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe! App |
|Miracast<sup>4</sup> | &nbsp; |
|Movies & TV |Microsoft.ZuneVideo \_ 8wekyb3d8bbwe \! Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive \_ 8wekyb3d8bbwe \! App |
|Fotky |Microsoft. Windows. Aplikace Photos \_ 8wekyb3d8bbwe \! |
|Starý Nastavení |HolographicSystemSettings_cw5n1h2txyewy! App |
|Nové Nastavení |BAEAEF15-9BE-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! App |
|Tipy |Microsoft.HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> Pokud chcete povolit zachytávání fotek nebo videí, musíte aplikaci Fotoaparát povolit jako aplikaci veřejného terminálu.  
> <sup>2</sup> Když povolíte aplikaci Fotoaparát, je třeba mít na paměti následující podmínky:
> - Nabídka Rychlé akce obsahuje tlačítka Fotografie a Video.
> - Měli byste také povolit aplikaci (například Fotky, Pošta nebo OneDrive), která může pracovat s obrázky nebo načítat obrázky.  
>  
> <sup>3</sup> I v případě, že Cortana jako aplikaci veřejného terminálu, jsou povolené integrované hlasové příkazy. Příkazy, které souvisejí se zakázanými funkcemi, ale nemají žádný vliv.  
> <sup>4</sup> Nelze povolit Miracast. Pokud chcete Miracast jako aplikaci veřejného terminále, povolte aplikaci Fotoaparát a Aplikaci pro výběr zařízení.

Kromě toho Mixed Reality domovskou stránku není možné nastavit jako aplikaci veřejného terminálu.

Vraťte se [k podporovaným scénářům pro beznaioskový režim na základě typu identity.](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

## <a name="kiosk-xml-code-samples"></a>Ukázky kódu XML veřejného terminálu

1. [Více profilů přístupu přiřazených globálním aplikacím](#multiple-app-global-assigned-access-profile)
1. [Více profilů přístupu přiřazených globálním aplikacím s výjimkou vlastníků zařízení](#multiple-app-global-assigned-access-profile-excluding-device-owners)
1. [Více profilů přístupu přiřazených aplikací pro místní účet nebo uživatelský účet AAD](#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account)
1. [Více profilů přístupu přiřazených aplikacím pro dva uživatele AAD nebo více](#multiple-app-assigned-access-profiles-for-two-aad-users-or-more)
1. [Více profilů přístupu přiřazených aplikací pro jednu skupinu AAD](#multiple-app-assigned-access-profile-for-one-aad-group)
1. [Více profilů přístupu přiřazených aplikacím pro dvě nebo více skupin AAD](#multiple-app-assigned-access-profile-for-two-aad-groups-or-more)
1. [Více profilů přístupu přiřazených aplikací pro jeden účet AAD a jednu skupinu AAD](#multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group)
1. [Více přístupových profilů přiřazených aplikacím pro návštěvníky](#multiple-app-assigned-access-profile-for-visitors)

> [!NOTE]
> Nahraďte akce TODO podle vašich požadavků.

### <a name="multiple-app-global-assigned-access-profile"></a>Více profilů přístupu přiřazených globálním aplikacím

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone.xml" highlight="18-20":::

[Zpět na seznam](#kiosk-xml-code-samples) <br>
Vraťte se [k podporovaným scénářům pro beznaioskový režim na základě typu identity.](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-global-assigned-access-profile-excluding-device-owners"></a>Více profilů přístupu přiřazených globálním aplikacím s výjimkou vlastníků zařízení

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone-excluding-device-owners.xml" highlight="18-20":::

[Zpět na seznam](#kiosk-xml-code-samples) <br>
Vraťte se [k podporovaným scénářům pro beznaioskový režim na základě typu identity.](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account"></a>Více profilů přístupu přiřazených aplikací pro místní účet nebo uživatelský účet AAD

:::code language="xml" source="samples/kiosk-sample-multi-app-local-or-aad-user.xml" highlight="18-20,51,55":::

[Zpět na seznam](#kiosk-xml-code-samples) <br>
Vraťte se [k podporovaným scénářům pro beznaioskový režim na základě typu identity.](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profiles-for-two-aad-users-or-more"></a>Více profilů přístupu přiřazených aplikacím pro dva uživatele AAD nebo více

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-users-or-more.xml" highlight="22-24,52,53,80,88":::

[Zpět na seznam](#kiosk-xml-code-samples) <br>
Vraťte se [k podporovaným scénářům pro beznaioskový režim na základě typu identity.](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-one-aad-group"></a>Více profilů přístupu přiřazených aplikací pro jednu skupinu AAD

:::code language="xml" source="samples/kiosk-sample-multi-app-one-aad-group.xml" highlight="28":::

[Zpět na seznam](#kiosk-xml-code-samples) <br>
Vraťte se [k podporovaným scénářům pro beznaioskový režim na základě typu identity.](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-two-aad-groups-or-more"></a>Více profilů přístupu přiřazených aplikacím pro dvě nebo více skupin AAD

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-groups-or-more.xml" highlight="22-24,52,53,83,94":::

[Zpět na seznam](#kiosk-xml-code-samples) <br>
Vraťte se [k podporovaným scénářům pro beznaioskový režim na základě typu identity.](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group"></a>Více profilů přístupu přiřazených aplikací pro jeden účet AAD a jednu skupinu AAD

:::code language="xml" source="samples/kiosk-sample-multi-app-for-aad-user-and-aad-group.xml" highlight="22-24,52,53,80,91":::

[Zpět na seznam](#kiosk-xml-code-samples) <br>
Vraťte se [k podporovaným scénářům pro beznaioskový režim na základě typu identity.](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-visitors"></a>Více přístupových profilů přiřazených aplikacím pro návštěvníky

:::code language="xml" source="samples/kiosk-sample-multi-app-visitor-user.xml" highlight="18-20":::

[Zpět na seznam](#kiosk-xml-code-samples) <br>
Vraťte se [k podporovaným scénářům pro beznaioskový režim na základě typu identity.](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)
