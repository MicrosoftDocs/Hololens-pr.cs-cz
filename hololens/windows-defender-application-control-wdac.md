---
title: Windows Defender Řízení aplikací – WDAC
description: Přehled toho, co Windows Defender řízení aplikací je a jak ho používat ke správě HoloLens zařízení hybridní reality
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
ms.openlocfilehash: ab05f1bbe1570d4966932d6f8ac857e5bd2d8a7d3a8f5b93aaba0335eda05b01
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665552"
---
# <a name="windows-defender-application-control---wdac"></a>Windows Defender Řízení aplikací – WDAC

WdAC umožňuje správci IT nakonfigurovat svá zařízení tak, aby blokují spouštění aplikací na zařízeních. To se liší od metod omezení zařízení, jako je třeba režim veřejného terminála, kde se uživateli zobrazí uživatelské rozhraní, které skryje aplikace v zařízení, ale přesto je možné je spustit. I když je nástroj WDAC implementován, aplikace se stále zobrazí v seznamu Všechny aplikace, ale nástroj WDAC zastaví spuštění těchto aplikací a procesů uživatelem zařízení.

Zařízení může mít přiřazeno více než jednu zásadu WDAC. Pokud je v systému nastaveno více zásad WDAC, projeví se většina omezujících zásad. 

> [!NOTE]
> Když se koncoví uživatelé pokusí spustit aplikaci blokovanou wdac, v HoloLens se jim nebude dostávat oznámení o tom, že aplikaci nelze spustit.

Následuje průvodce, který uživatelům pomůže naučit se používat wdac a Windows PowerShell k povolení nebo blokování aplikací na zařízeních [HoloLens 2](/mem/intune/configuration/custom-profile-hololens)s Microsoft Intune .

Když uživatelé vyhledá aplikace nainstalované v počítači Windows 10 počítači pomocí prvního příkladu, budou možná muset provést několik pokusů o zúžení výsledků.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Pokud nevíte úplný název balíčku, možná budete muset několikrát spustit příkaz Get-AppxPackage -name \* YourBestGuess, abyste ho \* našli. Jakmile budete mít název, spusťte $package 1 = Get-AppxPackage -name Actual.PackageName.

Například spuštění následujícího kódu pro Microsoft Edge vrátí více než jeden výsledek, ale v tomto seznamu můžete zjistit, že úplný název, který potřebujete, je Microsoft.MicrosoftEdge.

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a>Názvy rodin balíčků pro aplikace v HoloLens

V průvodci propojeném výše můžete ručně upravit newPolicy.xml pravidla pro aplikace, které jsou nainstalované jenom v HoloLens s názvy jejich rodin balíčků. Někdy můžete použít aplikace, které nejsou na vašem stolním počítači a které chcete přidat do zásad.

Tady je seznam běžně používaných a In-Box pro zařízení HoloLens 2.

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

### <a name="how-to-find-a-package-family-name"></a>Jak najít rodinu balíčků

Pokud aplikace není v tomto seznamu, může uživatel použít Portál zařízení připojený k aplikaci HoloLens 2, která má nainstalovanou aplikaci, která má být blokovaná, k určení PackageRelativeID a odtud pak získat PackageFamilyName.

1. Nainstalujte aplikaci na zařízení HoloLens 2. 
1. Otevřete Nastavení -> Updates & Security -> For developers (Zabezpečení –> Pro vývojáře) a povolte Developer **mode** (Vývojářský režim) a **potom Device Portal (Portál zařízení).** 
    1. Další podrobnosti najdete v tématu další informace o [nastavení a používání portálu zařízení.](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. Po Portál zařízení připojení přejděte na **Zobrazení a** pak na **Aplikace.** 
1. Na panelu Nainstalované aplikace vyberte pomocí rozevíracího seznamu nainstalovanou aplikaci. 
1. Vyhledejte PackageRelativeID. 
1. Zkopírujte znaky aplikace před znakem !, tyto znaky budou vaše PackageFamilyName.


