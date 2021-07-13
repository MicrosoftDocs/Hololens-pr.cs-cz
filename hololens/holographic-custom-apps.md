---
title: Správa vlastních aplikací pro HoloLens (1. generace)
description: Naučte se instalovat, odinstalovat a načítat vlastní holografické aplikace na HoloLens zařízení pomocí Portál zařízení a Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens, sideload, side load, side-load, store, uwp, app, install
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: a179032978e1fc062273a6754e3b0a1ad50a5211
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635904"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a>Správa vlastních aplikací pro HoloLens (1. generace)

HoloLens podporuje mnoho existujících aplikací z Microsoft Store a také nové aplikace vytvořené speciálně pro HoloLens. Tento článek se zaměřuje na vlastní holografické aplikace.  

Další informace o aplikacích pro Store najdete v tématu [Správa aplikací ve Storu.](holographic-store-apps.md)

> [!IMPORTANT]
> Následující informace byly vytvořeny pro HoloLens (1. generace) také nazývané HoloLens Developer Edition. Jako takové bylo běžné instalovat aplikace bokem přes portál zařízení a Visual Studio přes zařízení. U podnikových nasazení nedoporučujeme povolovat vývojářský režim, který obě tyto metody používají. Pokud vás zajímá metoda zabezpečeného nasazení aplikací, projděte si naši správu [aplikací: Přehled.](app-deploy-overview.md)
>
> Pokud hledáte některou z metod instalace aplikací pro vývojáře HoloLens 2, přečtěte si:
>
> - [Portál zařízení: Instalace aplikace](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [Použití Visual Studio k nasazení a ladění aplikací](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a>Instalace vlastních aplikací

Vlastní aplikace můžete na HoloLens nainstalovat buď pomocí Portál zařízení, nebo nasazením aplikací z Visual Studio.

### <a name="installing-an-application-package-with-the-device-portal"></a>Instalace balíčku aplikace pomocí Portál zařízení

1. Navázání připojení [z Portál zařízení](/windows/mixed-reality/using-the-windows-device-portal) k cílovému HoloLens.

1. V levém navigačním panelu přejděte na **stránku** Aplikace.

1. V **části Balíček aplikace** přejděte k souboru .appx, který je přidružený k vaší aplikaci.

   > [!IMPORTANT]
   > Nezapomeňte odkazovat na všechny přidružené soubory závislostí a certifikátů.

1. Vyberte **Přejít.**

   > [!div class="mx-imgBorder"]
   > ![Instalace formuláře aplikace v Windows Portál zařízení na Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### <a name="deploying-from-microsoft-visual-studio-2015"></a>Nasazení z Microsoft Visual Studio 2015

1. Otevřete řešení pro Visual Studio aplikace (soubor .sln).

1. Otevřete vlastnosti **projektu**.

1. Vyberte následující konfiguraci sestavení: **Master/x86/Remote Machine**.

1. Když vyberete **Vzdálený počítač:**
   - Ujistěte se, že adresa odkazuje na Wi-Fi IP adresu vašeho HoloLens.
   - Nastavte ověřování **na Univerzální (nešifrovaný protokol).**
   
1. Sestavte své řešení.

1. Pokud chcete nasadit aplikaci z vývojového počítače do HoloLens vyberte **Vzdálený počítač**. Pokud již máte existující sestavení na HoloLens, vyberte **Ano** a nainstalujte tuto novější verzi.  

   ![Nasazení vzdáleného počítače pro aplikace Microsoft HoloLens v Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. Aplikace se na váš počítač nainstaluje a automaticky HoloLens.

Po instalaci aplikace ji najdete v seznamu Všechny aplikace  (**Start**  >  **Všechny aplikace**).
