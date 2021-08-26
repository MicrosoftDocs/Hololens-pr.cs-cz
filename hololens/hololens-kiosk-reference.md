---
title: HoloLens referenční informace pro veřejný terminál
description: informace a ukázky pro veřejné terminály na zařízeních HoloLens.
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
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/25/2021
ms.locfileid: "122863935"
---
# <a name="hololens-kiosk-reference-information"></a>HoloLens Informace o beznabídkovém odkazu

tato stránka obsahuje užitečné informace pro nastavení celoobrazovkového režimu HoloLens zařízení. Mezi tyto odkazy patří AUMIDs pro aplikace doručené pošty a hledání vašich změn a několik ukázek XML pro celoobrazovkový režim, které jsou jenom několik úprav, které je možné použít pro několik různých scénářů. Informace o nastavení veřejného terminálu najdete na [stránce Nastavení veřejného terminálu.](hololens-kiosk.md)

## <a name="hololens-application-user-model-ids-aumids"></a>HoloLens ID modelu uživatele aplikace (AUMIDs)  

Obecné informace o tom, jak zvolit aplikace na veřejném terminálu, najdete v tématu [pokyny pro výběr aplikace pro přiřazený přístup (celoobrazovkový režim)](/windows/configuration/guidelines-for-assigned-access-app).

Pokud ke konfiguraci celoobrazovkového režimu použijete systém správy mobilních zařízení (MDM) nebo zřizovací balíček, použijte k určení aplikací [poskytovatele služby AssignedAccess Configuration Service Provider (CSP)](/windows/client-management/mdm/assignedaccess-csp) . CSP používá k identifikaci aplikací [ID modelu uživatele aplikace (AUMIDs)](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) . V následující tabulce je uveden seznam AUMIDs některých integrovaných aplikací, které můžete použít v terminálu s více aplikacemi.

<a id="aumids"></a>

|Název aplikace |AUMID |
| --- | --- |
|Prohlížeč 3D |Microsoft. Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft. Microsoft3DViewer |
|Kalendář |Microsoft. windowscommunicationsapps \_ 8wekyb3d8bbwe \! Microsoft. windowslive. Calendar |
|Kamera<sup>1, 2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |Aplikace Microsoft. 549981C3F5F10 \_ 8wekyb3d8bbwe \! |
|výběr zařízení v HoloLens (1. generace) |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|výběr zařízení na HoloLens 2 |Microsoft. Windows. DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft. Windows. DevicesFlowHost |
|Příručky k Dynamics 365 |Microsoft. Dynamics365. příruček \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Vzdálená pomoc pro Dynamics 365 |Microsoft. MicrosoftRemoteAssist \_ 8wekyb3d8bbwe \! Microsoft. RemoteAssist |
|&nbsp;Centrum Feedback |Aplikace Microsoft. WindowsFeedbackHub \_ 8wekyb3d8bbwe \! |
|Průzkumník souborů |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy! Aplikace |
|Poštovní |microsoft.windowscommunicationsapps_8wekyb3d8bbwe! Microsoft. windowslive. mail |
|Původní Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe! MicrosoftEdge |
|Nový Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe! MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe! Aplikace |
|Miracast<sup>4</sup> | &nbsp; |
|Filmy & televizor |Microsoft. ZuneVideo \_ 8wekyb3d8bbwe \! Microsoft. ZuneVideo |
|OneDrive |aplikace Microsoft. microsoftskydrive \_ 8wekyb3d8bbwe \! |
|Fotky |Microsoft. Windows. \_Aplikace fotek 8wekyb3d8bbwe \! |
|původní Nastavení |HolographicSystemSettings_cw5n1h2txyewy! Aplikace |
|nový Nastavení |BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy! Aplikace |
|Tipy |Microsoft. HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> Pokud chcete povolit digitalizaci fotek nebo videa, musíte aplikaci kamery povolit jako beznabídkovou aplikaci.  
> <sup>2</sup> Pokud povolíte aplikaci kamery, pamatujte na následující podmínky:
> - Nabídka rychlé akce obsahuje tlačítka pro fotografii a video.
> - měli byste taky povolit aplikaci (například fotky, poštu nebo OneDrive), která může pracovat s obrázky nebo je z ní načítat.  
>  
> <sup>3</sup> i v případě, že nepovolíte Cortana jako beznabídkovou aplikaci, jsou integrované hlasové příkazy povolené. Příkazy, které se vztahují k zakázaným funkcím, ale nemají žádný vliv.  
> <sup>4</sup> Miracast přímo nelze povolit. Pokud chcete povolit Miracast jako beznabídkovou aplikaci, povolte aplikaci kamery a aplikaci pro výběr zařízení.

Kromě toho není možné nastavit domovskou stránku hybridní reality jako beznabídkovou aplikaci.

Návrat k [podporovaným scénářům pro celoobrazovkový režim na základě typu identity](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

## <a name="kiosk-xml-code-samples"></a>Ukázka kódu XML veřejného terminálu

1. [Globální přiřazený profil přístupu k více aplikacím](#multiple-app-global-assigned-access-profile)
1. [Více aplikací globální přiřazený profil přístupu s výjimkou vlastníků zařízení](#multiple-app-global-assigned-access-profile-excluding-device-owners)
1. [Pro místní účet nebo uživatelský účet AAD má více aplikací přiřazený profil přístupu.](#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account)
1. [Více přidaných profilů přístupu aplikace pro dva uživatele AAD nebo více](#multiple-app-assigned-access-profiles-for-two-aad-users-or-more)
1. [Přidaný profil přístupu k více aplikacím pro jednu skupinu AAD](#multiple-app-assigned-access-profile-for-one-aad-group)
1. [Více přidaný profil přístupu aplikace pro dvě skupiny AAD nebo více](#multiple-app-assigned-access-profile-for-two-aad-groups-or-more)
1. [Pro jeden účet AAD a jednu skupinu AAD má aplikace přiřazený profil přístupu k více aplikacím.](#multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group)
1. [Víc přidaných profilů přístupu aplikace pro návštěvníky](#multiple-app-assigned-access-profile-for-visitors)

> [!NOTE]
> Podle vašich požadavků nahraďte akce TODO.

### <a name="multiple-app-global-assigned-access-profile"></a>Globální přiřazený profil přístupu k více aplikacím

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone.xml" highlight="18-20":::

[Zpět na seznam](#kiosk-xml-code-samples) <br>
Návrat k [podporovaným scénářům pro celoobrazovkový režim na základě typu identity](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-global-assigned-access-profile-excluding-device-owners"></a>Více aplikací globální přiřazený profil přístupu s výjimkou vlastníků zařízení

:::code language="xml" source="samples/kiosk-sample-global-multiapp-for-everyone-excluding-device-owners.xml" highlight="18-20":::

[Zpět na seznam](#kiosk-xml-code-samples) <br>
Návrat k [podporovaným scénářům pro celoobrazovkový režim na základě typu identity](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account"></a>Pro místní účet nebo uživatelský účet AAD má více aplikací přiřazený profil přístupu.

:::code language="xml" source="samples/kiosk-sample-multi-app-local-or-aad-user.xml" highlight="18-20,51,55":::

[Zpět na seznam](#kiosk-xml-code-samples) <br>
Návrat k [podporovaným scénářům pro celoobrazovkový režim na základě typu identity](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profiles-for-two-aad-users-or-more"></a>Více přidaných profilů přístupu aplikace pro dva uživatele AAD nebo více

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-users-or-more.xml" highlight="22-24,52,53,80,88":::

[Zpět na seznam](#kiosk-xml-code-samples) <br>
Návrat k [podporovaným scénářům pro celoobrazovkový režim na základě typu identity](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-one-aad-group"></a>Přidaný profil přístupu k více aplikacím pro jednu skupinu AAD

:::code language="xml" source="samples/kiosk-sample-multi-app-one-aad-group.xml" highlight="28":::

[Zpět na seznam](#kiosk-xml-code-samples) <br>
Návrat k [podporovaným scénářům pro celoobrazovkový režim na základě typu identity](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-two-aad-groups-or-more"></a>Více přidaný profil přístupu aplikace pro dvě skupiny AAD nebo více

:::code language="xml" source="samples/kiosk-sample-multi-app-two-aad-groups-or-more.xml" highlight="22-24,52,53,83,94":::

[Zpět na seznam](#kiosk-xml-code-samples) <br>
Návrat k [podporovaným scénářům pro celoobrazovkový režim na základě typu identity](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-one-aad-account-and-one-aad-group"></a>Pro jeden účet AAD a jednu skupinu AAD má aplikace přiřazený profil přístupu k více aplikacím.

:::code language="xml" source="samples/kiosk-sample-multi-app-for-aad-user-and-aad-group.xml" highlight="22-24,52,53,80,91":::

[Zpět na seznam](#kiosk-xml-code-samples) <br>
Návrat k [podporovaným scénářům pro celoobrazovkový režim na základě typu identity](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)

### <a name="multiple-app-assigned-access-profile-for-visitors"></a>Víc přidaných profilů přístupu aplikace pro návštěvníky

:::code language="xml" source="samples/kiosk-sample-multi-app-visitor-user.xml" highlight="18-20":::

[Zpět na seznam](#kiosk-xml-code-samples) <br>
Návrat k [podporovaným scénářům pro celoobrazovkový režim na základě typu identity](hololens-kiosk.md#supported-scenarios-for-kiosk-mode-based-on-identity-type)
