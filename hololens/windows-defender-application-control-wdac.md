---
title: Windows Defender Řízení aplikací (WDAC)
description: Přehled toho, co Windows Defender řízení aplikací je a jak ho používat ke správě HoloLens zařízení hybridní reality
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b5c3b55273346f330580b07e5294e7e8e65ea12d
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428651"
---
# <a name="windows-defender-application-control---wdac"></a>Windows Defender Řízení aplikací – WDAC

## <a name="overview"></a>Přehled

WdAC umožňuje nakonfigurovat HoloLens blokování spouštění aplikací. Liší se od bezobrazovkového režimu, kde uživatelské rozhraní skryje aplikace, ale přesto je můžete spustit. V nástroji WDAC vidíte aplikace, ale ne je možné je spustit.

> [!NOTE]
> Když se koncoví uživatelé pokusí spustit aplikaci blokovanou wdac na HoloLens, nebudou upozorněni na to, že aplikaci není možné spustit.

Zařízení může mít přiřazeno více než jednu zásadu WDAC. Pokud je v systému nastaveno více zásad WDAC, projeví se většina omezujících zásad. 

Následuje průvodce, který uživatelům pomůže naučit se používat funkce WDAC a Windows PowerShell k povolení nebo blokování aplikací na zařízeních [se systémem HoloLens 2](/mem/intune/configuration/custom-profile-hololens)s Microsoft Intune .

Když uživatelé vyhledájí aplikace nainstalované v počítači Windows 10 počítači pomocí prvního příkladu, možná budou muset provést několik pokusů o zúžení výsledků.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Pokud nevíte úplný název balíčku, možná budete muset několikrát spustit příkaz Get-AppxPackage -name \* YourBestGuess, abyste ho \* našli. Jakmile budete mít název, spusťte $package 1 = Get-AppxPackage -name Actual.PackageName.

Například spuštění následujícího kódu pro Microsoft Edge vrátí více než jeden výsledek, ale v tomto seznamu můžete zjistit, že úplný název, který potřebujete, je Microsoft.MicrosoftEdge.

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a>Názvy rodin balíčků pro aplikace v HoloLens

V průvodci propojeném výše můžete ručně upravit newPolicy.xml a přidat pravidla pro aplikace, které jsou nainstalované jenom v HoloLens s názvy jejich skupin balíčků. Někdy můžete použít aplikace, které nejsou na vašem stolním počítači a které chcete přidat do zásad.

Tady je seznam běžně používaných a In-Box aplikací pro HoloLens 2.

| Název aplikace                   | Název rodiny balíčků                                |
|----------------------------|----------------------------------------------------|
| 3D prohlížeč                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| Instalační program aplikací              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup>         |
| Kalendář                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Camera                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft.549981C3F5F10_8wekyb3d8bbwe              |
| Průvodci Dynamics 365        | Microsoft.Dynamics365.Guides_8wekyb3d8bbwe         |
| Dynamics 365 Remote Assist | Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| Centrum Feedback               | Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe         |
| Průzkumník souborů              | c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy |
| Poštovní                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| Movies & TV                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| Fotky                     | Microsoft. Windows. Photos_8wekyb3d8bbwe             |
| Nastavení                   | HolographicSystemSettings_cw5n1h2txyewy            |
| Tipy                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1 – Blokování Instalační program aplikací zablokuje jenom aplikaci Instalační program aplikací, a ne aplikace nainstalované z jiných zdrojů, jako je Microsoft Store nebo z vašeho řešení MDM.

### <a name="how-to-find-a-package-family-name"></a>Jak najít název rodiny balíčků

Pokud aplikace není v tomto seznamu, může uživatel použít Portál zařízení připojený k aplikaci HoloLens 2, která má nainstalovanou aplikaci, která má být blokovaná, k určení PackageRelativeID a odtud pak získat PackageFamilyName.

1. Nainstalujte aplikaci na zařízení HoloLens 2. 
1. Otevřete Nastavení -> Updates & Security -> For developers (Zabezpečení –> Pro vývojáře) a povolte Developer mode (Vývojářský **režim)** a **potom Device Portal (Portál zařízení).** 
    1. Další podrobnosti najdete v tématu další informace o [nastavení a používání portálu zařízení.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. Po Portál zařízení připojení přejděte na **Zobrazení a** pak na **Aplikace.** 
1. Na panelu Nainstalované aplikace vyberte pomocí rozevíracího seznamu nainstalovanou aplikaci. 
1. Vyhledejte PackageRelativeID. 
1. Zkopírujte znaky aplikace před `!` , tyto znaky budou vaše PackageFamilyName.

