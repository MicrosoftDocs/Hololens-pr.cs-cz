---
title: správa vlastních aplikací pro HoloLens (1. generace)
description: naučte se instalovat, odinstalaci a načítat vlastní holografické aplikace na zařízeních HoloLens pomocí portálu pro zařízení a Visual Studio.
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: HoloLens, bokem, zatížení na straně, zkušební zatížení, úložiště, UWP, aplikace, instalace
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
ms.openlocfilehash: b6769c36f821ee3619ac9b62efd637ac561192bb
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032215"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a>správa vlastních aplikací pro HoloLens (1. generace)

HoloLens podporuje mnoho stávajících aplikací z Microsoft Store a také nové aplikace sestavené speciálně pro HoloLens. Tento článek se zaměřuje na vlastní holografické aplikace.  

Další informace o aplikacích pro Store najdete v tématu [Správa aplikací ve Storu](holographic-store-apps.md).

> [!IMPORTANT]
> následující informace byly vytvořeny pro HoloLens (1. generace), označované také jako verze HoloLens Developer Edition v daném okamžiku. jako takové aplikace pro zkušební načtení přes portál zařízení a instalace aplikací prostřednictvím Visual Studio se maloobchodech. Pro podniková nasazení nedoporučujeme povolit vývojářský režim, který obě tyto metody používají. Pokud vás zajímá Metoda nasazení zabezpečené aplikace, přečtěte si téma [Správa aplikací: Přehled](app-deploy-overview.md).
>
> pokud hledáte metodu pro vývojáře instalace aplikace HoloLens 2, přečtěte si:
>
> - [Portál zařízení: instalace aplikace](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [nasazení a ladění aplikací pomocí Visual Studio](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a>Instalace vlastních aplikací

vlastní aplikace můžete nainstalovat na HoloLens buď pomocí portálu zařízení, nebo nasazením aplikací z Visual Studio.

### <a name="installing-an-application-package-with-the-device-portal"></a>Instalace balíčku aplikace pomocí portálu zařízení

1. Navažte připojení z [portálu zařízení](/windows/mixed-reality/using-the-windows-device-portal) k cílovému HoloLens.

1. V levém navigačním panelu přejděte na stránku **aplikace** .

1. V části **balíček aplikace** přejděte na soubor. appx, který je přidružený k vaší aplikaci.

   > [!IMPORTANT]
   > Ujistěte se, že odkazujete na všechny přidružené závislosti a soubory certifikátů.

1. Vyberte **Přejít**.

   > [!div class="mx-imgBorder"]
   > ![nainstalujte formulář aplikace na Windows portál zařízení na Microsoft HoloLens.](images/deviceportal-appmanager.jpg)

### <a name="deploying-from-microsoft-visual-studio-2015"></a>nasazení z Microsoft Visual Studio 2015

1. otevřete řešení Visual Studio vaší aplikace (soubor. sln).

1. Otevřete **vlastnosti** projektu.

1. Vyberte následující konfiguraci sestavení: **hlavní/x86/vzdálený počítač**.

1. Když vyberete **vzdálený počítač**:
   - Zajistěte, aby adresa odkazovala na Wi-Fi IP adresa vašeho HoloLens.
   - Nastavte ověřování na **univerzální (nešifrovaný protokol)**.
   
1. Sestavte řešení.

1. pokud chcete aplikaci nasadit z vývojového počítače do HoloLens, vyberte **vzdálený počítač**. pokud již máte v HoloLens existující sestavení, vyberte **ano** pro instalaci této novější verze.  

   ![nasazení vzdáleného počítače pro aplikace, které se Microsoft HoloLens v Visual Studio.](images/vs2015-remotedeployment.jpg)  
   
1. Aplikace se nainstaluje a automaticky spustí na svém HoloLens.

Až aplikaci nainstalujete, najdete ji v seznamu **všechny aplikace** (**Spustit**  >  **všechny aplikace**).
