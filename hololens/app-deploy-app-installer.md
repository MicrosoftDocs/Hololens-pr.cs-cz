---
title: Boční načtení a instalace aplikací přes HoloLens 2 Instalační program aplikací
description: Naučte se instalovat a řešit potíže s aplikacemi pomocí instalačního programu aplikací a instalace aplikací bokem a pomocí uživatelského rozhraní.
keywords: app management, app, hololens, app installer
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 11/10/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 9e413963dbf34dd071fc9603487590065b967ee7
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377577"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a>Instalace aplikací na HoloLens 2 prostřednictvím Instalační program aplikací

> [!NOTE]
> Tato funkce byla dostupná ve [Windows Holographic verze 20H2 –prosinec 2020 Update.](hololens-release-notes.md) Ujistěte se, že je [zařízení aktualizované](hololens-update-hololens.md) tak, aby tuto funkci bylo možné používat.

Přidali **jsme novou funkci (Instalační program aplikací),** která umožňuje hladce instalovat aplikace na zařízení HoloLens 2. Tato funkce bude ve **výchozím nastavení pro nespravovaná zařízení povolená.** Aby se zabránilo přerušení služeb podnikům, instalační program aplikací nebude v tuto chvíli dostupný **pro spravovaná** zařízení.  

Zařízení se považuje za "spravované", **pokud** platí kterákoli z následujících podmínek:

- Zaregistrované [](hololens-enroll-mdm.md) MDM
- Konfigurace se [zřizovacím balíčkem](hololens-provisioning.md)
- Identita [uživatele](hololens-identity.md) je Azure AD

Teď můžete instalovat aplikace bez nutnosti povolit vývojářský režim nebo používat Portál zařízení.  Stáhněte si do zařízení (přes USB nebo přes Microsoft Edge) sadu Appx a přejděte do sady Appx v Průzkumník souborů, abyste se vyzváni k instalaci.  Případně můžete [zahájit instalaci z webové stránky](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).  Stejně jako aplikace, které instalujete z Microsoft Store nebo bokem s využitím funkce nasazení obchodní [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) aplikace MDM, musí být aplikace digitálně podepsané pomocí nástroje sign a certifikát použitý k podepsání musí být pro zařízení HoloLens důvěryhodný, aby bylo možné aplikaci nasadit. [](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations)

## <a name="requirements"></a>Požadavky

### <a name="for-your-devices"></a>Pro vaše zařízení:

Tato funkce je aktuálně dostupná v buildech Windows Holographic 20H2 pro zařízení HoloLens 2. Ujistěte se, že jsou aktualizovaná všechna zařízení používající tuto [metodu.](hololens-update-hololens.md)

### <a name="for-your-apps"></a>Pro vaše aplikace:

Konfigurace řešení vaší aplikace musí  být  buď hlavní, nebo vy vydání, protože Instalační program aplikací bude používat závislosti z obchodu. Další informace o [vytváření balíčků aplikací najdete v tématu](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).

Aplikace nainstalované touto metodou musí být digitálně podepsané. K podepsání aplikace budete muset použít certifikát. Můžete buď získat certifikát ze seznamu důvěryhodných certifikačních autority [ms,](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)v takovém případě nebudete muset provést žádnou další akci. Nebo můžete podepsat vlastní certifikát, ale tento certifikát se bude muset do zařízení nasučit.

- Jak podepisovat [aplikace pomocí nástroje pro podpis](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Možnosti certifikátu:**

- [Seznam důvěryhodných certifikačních autorit ms](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**Vyberte metodu nasazení certifikátu.**

- [Zřizovací balíčky](hololens-provisioning.md) je možné použít na místní zařízení.
- MDM lze použít k [použití certifikátů s konfiguracemi zařízení.](https://docs.microsoft.com/mem/intune/protect/certificates-configure)
- Použijte ve Správci [certifikátů zařízení](certificate-manager.md).

## <a name="installation-method"></a>Metoda instalace

1. Zkontrolujte, že se vaše zařízení nepovažuje za spravované.
1. Zkontrolujte, že je zařízení HoloLens 2 zapnuté a že jste přihlášeni.
1. Na počítači přejděte do vlastní aplikace a zkopírujte yourapp.appxbundle do složky název_vašeho_zařízení\Interní úložiště\Soubory ke stažení.
    Po zkopírování souboru můžete zařízení odpojit a instalaci dokončit později.
1. Na zařízení HoloLens 2 otevřete **nabídku Start,** vyberte **Všechny aplikace** a spusťte **Průzkumník souborů** aplikaci.
1. Přejděte do složky Stažené soubory. Možná budete muset na levém panelu aplikace nejprve vybrat **Toto zařízení** a pak přejít na Položky ke stažení.
1. Vyberte soubor yourapp.appxbundle.
1. Spustí Instalační program aplikací. Vyberte **tlačítko Install** (Nainstalovat) a nainstalujte aplikaci.

Nainstalovaná aplikace se automaticky spustí po dokončení instalace.

![Instalace příkladů MRTK prostřednictvím Instalační program aplikací](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a>Řešení potíží s instalacemi

Pokud se vaší aplikaci nepodařilo nainstalovat, při řešení potíží zkontrolujte následující:

- Vaše aplikace je buď sestavení hlavní verze, nebo sestavení verze.
- Vaše zařízení se aktualizuje na sestavení, na kterém je tato funkce dostupná.
- Jste [připojení k internetu.](hololens-network.md)
- Vaše [koncové body pro Microsoft Store](hololens-offline.md) jsou správně nakonfigurované.  

## <a name="web-installer"></a>Webový instalační program

Uživatelé instalují aplikaci přímo z webového serveru. Tento tok využívá metodu Instalační program aplikací v kombinaci se snadnou metodou distribuce stahování a instalace.

### <a name="how-to-set-up-web-install"></a>Jak nastavit webovou instalaci:

1. Ujistěte se, že je aplikace správně nakonfigurovaná k instalaci.
1. Pokud chcete [povolit instalaci z webové stránky, postupujte podle těchto kroků.](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)

### <a name="end-user-experience"></a>Prostředí koncového uživatele:

1. Uživatel obdrží a nainstaluje certifikát do zařízení pomocí metody dříve zvolené výše.
1. Uživatel navštíví adresu URL vytvořenou v kroku výše.

Aplikace se teď nainstaluje do zařízení. Aplikaci najdete tak, že otevřete **nabídka Start** a výběrem tlačítka **Všechny aplikace** aplikaci najdete.

- Další pomoc s řešením potíží s metodou instalace instalačního programu aplikace najdete v tématu Řešení [potíží s instalačním programem aplikací.](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)

> [!NOTE]
> Uživatelské rozhraní během procesu aktualizace se nepodporuje. Možnost ShowPrompt na [této stránce](https://docs.microsoft.com/windows/msix/app-installer/update-settings) a související možnosti se proto nepodporují.

## <a name="sample-apps"></a>Ukázkové aplikace

Pokud si chcete Instalační program aplikací ukázkové aplikace, podívejte se na některé z našich dostupných ukázek:

- [MRTK Examples Hub](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [Povrchy](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [Ukázkové aplikace pro UPW, které je možné použít k testování](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
