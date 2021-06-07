---
title: Windows Defender řízení aplikací – WDAC
description: Přehled toho, Windows Defender řízení aplikací je a jak ho používat ke správě zařízení hybridní reality HoloLens
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
ms.openlocfilehash: 23c9a274387424e8f084a4729ee621e130820716
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377611"
---
# <a name="windows-defender-application-control---wdac"></a>Windows Defender řízení aplikací – WDAC

WdAC umožňuje správci IT nakonfigurovat svá zařízení tak, aby blokují spouštění aplikací na zařízeních. To se liší od metod omezení zařízení, jako je třeba režim veřejného terminála, kde se uživateli zobrazí uživatelské rozhraní, které skryje aplikace v zařízení, ale přesto je možné je spustit. I když je nástroj WDAC implementován, aplikace se stále zobrazí v seznamu Všechny aplikace, ale nástroj WDAC zastaví spuštění těchto aplikací a procesů uživatelem zařízení.

Zařízení může mít přiřazeno více než jednu zásadu WDAC. Pokud je v systému nastaveno více zásad WDAC, projeví se většina omezujících zásad. 

> [!NOTE]
> Když se koncoví uživatelé pokusí spustit aplikaci, která je blokovaná wdac, na HoloLens neobdrží oznámení o tom, že ji není možné spustit.

Následuje průvodce, který uživatelům pomůže naučit se používat funkce WDAC a Windows PowerShell k povolení nebo blokování aplikací na [zařízeních HoloLens 2](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)s Microsoft Intune .

Když uživatelé vyhledájí aplikace nainstalované na svém počítači Windows 10 počítači pomocí prvního příkladu, možná budou muset provést několik pokusů o zúžení výsledků.

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

Pokud nevíte úplný název balíčku, možná budete muset několikrát spustit příkaz Get-AppxPackage -name \* YourBestGuess, abyste ho \* našli. Jakmile budete mít název, spusťte $package 1 = Get-AppxPackage -name Actual.PackageName.

Například spuštění následujícího kódu pro Microsoft Edge vrátí více než jeden výsledek, ale v tomto seznamu můžete zjistit, že úplný název, který potřebujete, je Microsoft.MicrosoftEdge.

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a>Názvy rodin balíčků pro aplikace na HoloLens

V průvodci propojeném výše můžete ručně upravit newPolicy.xml a přidat pravidla pro aplikace, které jsou nainstalované jenom na HoloLens s názvy jejich skupin balíčků. Někdy můžete použít aplikace, které nejsou na vašem stolním počítači a které chcete přidat do zásad.

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
| Fotky                     | Microsoft.Windows.Photos_8wekyb3d8bbwe             |
| Nastavení                   | HolographicSystemSettings_cw5n1h2txyewy            |
| Tipy                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1 – Blokování Instalační program aplikací zablokuje jenom aplikaci Instalační program aplikací, a ne aplikace nainstalované z jiných zdrojů, jako je Microsoft Store nebo z vašeho řešení MDM.

### <a name="how-to-find-a-package-family-name"></a>Jak najít rodinu balíčků

Pokud aplikace není v tomto seznamu, může uživatel použít Portál zařízení připojený k HoloLens 2, který má nainstalovanou aplikaci, kterou chcete blokovat, k určení PackageRelativeID a odtud získat PackageFamilyName.

1. Nainstalujte aplikaci na zařízení HoloLens 2. 
1. Otevřete Nastavení -> Aktualizace & Zabezpečení -> Pro vývojáře a povolte Vývojářský **režim** a potom **Portál zařízení.** 
    1. Další podrobnosti najdete v tématu další informace o [nastavení a používání portálu zařízení.](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)
1. Po Portál zařízení připojení přejděte na **Zobrazení a** pak na **Aplikace.** 
1. Na panelu Nainstalované aplikace vyberte pomocí rozevíracího seznamu nainstalovanou aplikaci. 
1. Vyhledejte PackageRelativeID. 
1. Zkopírujte znaky aplikace před znakem !, tyto znaky budou vaše PackageFamilyName.


