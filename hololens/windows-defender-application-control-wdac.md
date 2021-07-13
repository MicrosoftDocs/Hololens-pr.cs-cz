---
title: Windows Defender Řízení aplikací – WDAC
description: přehled o tom, co Windows Defender Application Control je a jak ho používat ke správě HoloLens zařízení se smíšeným realitou.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/26/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: a27a16913873c5245f734dbe084eb2b7ed007c20
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639926"
---
# <a name="windows-defender-application-control---wdac"></a>Windows Defender Řízení aplikací – WDAC

WDAC umožňuje správci IT nakonfigurovat zařízení tak, aby blokovala spuštění aplikací na zařízeních. To se liší od metod omezení zařízení, jako je celoobrazovkový režim, kde se uživatel zobrazuje s uživatelským ROZHRANÍm, které skrývá aplikace na zařízení, ale je možné ho přesto spustit. I když je implementováno WDAC, aplikace jsou stále viditelné v seznamu všechny aplikace, ale WDAC zastaví aplikace a procesy, aby je mohli spustit uživatel zařízení.

Zařízení může mít přiřazeno více než jednu zásadu WDAC. Pokud je v systému nastaveno více zásad WDAC, většina omezujících se projeví. 

> [!NOTE]
> když se koncoví uživatelé pokusí spustit aplikaci, která je blokovaná službou WDAC HoloLens, neobdrží oznámení o tom, že tuto aplikaci nepůjde spustit.

následuje průvodce pro uživatele, kteří se naučí [používat WDAC a Windows PowerShell k povolení nebo blokování aplikací na zařízeních HoloLens 2 s Microsoft Intune](/mem/intune/configuration/custom-profile-hololens).

když uživatelé hledají aplikace nainstalované na svém Windows 10 počítači pomocí prvního ukázkového kroku, může být potřeba provést několik pokusů o zúžení výsledků.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Pokud neznáte úplný název balíčku, možná několikrát spustíte rutinu Get-AppxPackage-name \* YourBestGuess \* . Po zadání názvu spusťte ' $package 1 = Get-AppxPackage-Name skutečnost. název balíčku '

například když Microsoft Edge spustíte následující příkaz, vrátí se více výsledků, ale z tohoto seznamu můžete zjistit, že úplný název, který potřebujete, je Microsoft. MicrosoftEdge.

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a>Názvy rodin balíčků pro aplikace v HoloLens

v průvodci výše můžete ručně upravit newPolicy.xml a přidat pravidla pro aplikace, které jsou nainstalovány pouze v HoloLens s názvy jejich rodin balíčků. Někdy existují aplikace, které můžete použít k použití, které nejsou na stolním počítači, které chcete přidat do zásad.

tady je seznam běžně používaných a In-Box aplikací pro zařízení HoloLens 2.

| Název aplikace                   | Název rodiny balíčků                                |
|----------------------------|----------------------------------------------------|
| Prohlížeč 3D                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| Instalační program aplikace              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup>         |
| Kalendář                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Camera                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft.549981C3F5F10_8wekyb3d8bbwe              |
| Příručky k Dynamics 365        | Microsoft.Dynamics365.Guides_8wekyb3d8bbwe         |
| Vzdálená pomoc pro Dynamics 365 | Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| Centrum Feedback               | Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe         |
| Průzkumník souborů              | c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy |
| Poštovní                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| Filmy & televizor                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| Fotky                     | Microsoft. Windows. Photos_8wekyb3d8bbwe             |
| Nastavení                   | HolographicSystemSettings_cw5n1h2txyewy            |
| Tipy                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1. blokování instalačního programu aplikace zablokuje jenom aplikaci instalátor aplikace a ne aplikace nainstalované z jiných zdrojů, jako je Microsoft Store nebo z řešení MDM.

### <a name="how-to-find-a-package-family-name"></a>Jak najít název řady balíčků

pokud aplikace není na tomto seznamu, pak uživatel může použít portál zařízení, který je připojený k HoloLens 2, která má nainstalovanou aplikaci, kterou chcete zablokovat, abyste zjistili, jak PackageRelativeID, tak PackageFamilyName.

1. nainstalujte aplikaci na zařízení HoloLens 2. 
1. otevřete Nastavení-> aktualizace & zabezpečení > pro vývojáře a povolte **vývojářský režim** a potom **portál zařízení**. 
    1. Další podrobnosti najdete [v tématu o nastavení a používání portálu pro zařízení tady](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).
1. Jakmile je portál zařízení připojený, přejděte do **zobrazení** a pak na **aplikace**. 
1. V panelu nainstalované aplikace vyberte pomocí rozevírací nabídky nainstalovanou aplikaci. 
1. Vyhledejte PackageRelativeID. 
1. Kopírovat znaky aplikace před!. tyto znaky budou vaší PackageFamilyName.


