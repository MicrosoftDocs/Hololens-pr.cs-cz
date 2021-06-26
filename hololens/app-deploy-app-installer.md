---
title: Jak na straně načíst a nainstalovat aplikace přes instalační program aplikace pro HoloLens 2
description: Naučte se instalovat a řešit potíže s aplikacemi pomocí instalačního programu aplikace a na straně zátěže a instalovat aplikace přes uživatelské rozhraní.
keywords: Správa aplikací, aplikace, HoloLens, instalační program aplikace
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
ms.openlocfilehash: d8be5c2ed7fba38b6710aba9c122557a36073a79
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924124"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a>Instalace aplikací na HoloLens 2 prostřednictvím instalačního programu aplikace

> [!NOTE]
> Tato funkce byla dostupná ve [Windows holografickém systému, verze 20H2 – prosinec 2020 Update](hololens-release-notes.md). Ujistěte se, že je vaše zařízení [aktualizované](hololens-update-hololens.md) , aby tuto funkci používalo.

Přidali jsme **novou funkci (instalační program aplikace), která vám umožní na zařízeních HoloLens 2 plynule instalovat aplikace** . Tato funkce bude **ve výchozím nastavení zapnutá pro nespravovaná zařízení**. Aby nedošlo k narušení podniků, instalační program aplikace nebude v tuto chvíli **k dispozici pro spravovaná zařízení** .  

Zařízení se považuje za spravované, pokud platí **některá** z následujících podmínek:

- [Zaregistrované](hololens-enroll-mdm.md) MDM
- Nakonfigurováno pomocí [zřizovacího balíčku](hololens-provisioning.md)
- [Identita](hololens-identity.md) uživatele je Azure AD

Nyní je možné instalovat aplikace bez nutnosti povolit vývojářský režim ani používat portál zařízení.  Stáhněte si do svého zařízení (přes USB nebo přes Microsoft Edge) sadu appx a přejděte do sady appx v Průzkumníkovi souborů, kde se zobrazí výzva k ukončení instalace.  Případně můžete [zahájit instalaci z webové stránky](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).  Stejně jako aplikace, které instalujete z Microsoft Store nebo bokem pomocí možnosti nasazení aplikace LOB pro správu mobilních aplikací, musí být aplikace digitálně podepsané pomocí [nástroje Signer](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) a [certifikát použitý k podepsání musí být](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) před nasazením aplikace důvěryhodný pro zařízení HoloLens.

## <a name="requirements"></a>Požadavky

### <a name="for-your-devices"></a>Pro vaše zařízení:

Tato funkce je aktuálně dostupná ve Windows holografické 20H2 buildech pro zařízení HoloLens 2. Zajistěte, aby všechna zařízení používající tuto metodu byla [aktualizovaná](hololens-update-hololens.md).

### <a name="for-your-apps"></a>Pro vaše aplikace:

Konfigurace řešení vaší aplikace musí být buď **Hlavní** , nebo **verze** , protože instalační program aplikace bude používat závislosti ze Storu. Přečtěte si další informace o [vytváření balíčků aplikací](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).

Aplikace, které jsou nainstalované přes tuto metodu, musí být digitálně podepsané. K podepsání aplikace budete muset použít certifikát. Můžete buď získat certifikát ze [seznamu důvěryhodných certifikačních autorit MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT). v takovém případě nebudete muset provádět žádnou další akci. Případně můžete podepsat vlastní certifikát, ale tento certifikát bude nutné do zařízení vložit.

- Jak podepisovat aplikace [pomocí nástroje Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Možnosti certifikátu:**

- [Seznam důvěryhodných certifikačních autorit MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**Vyberte metodu nasazení certifikátu.**

- [Balíčky zřizování](hololens-provisioning.md) se dají použít na místní zařízení.
- MDM se dá použít k [aplikování certifikátů s konfiguracemi zařízení](https://docs.microsoft.com/mem/intune/protect/certificates-configure).
- Použijte [Správce certifikátů](certificate-manager.md)zařízení.

## <a name="installation-method"></a>Metoda instalace

1. Ověřte, že se zařízení nepovažuje za spravované.
1. Ověřte, že je zařízení HoloLens 2 zapnuté a že jste přihlášení.
1. Na svém počítači přejděte do vlastní aplikace a zkopírujte yourapp. appxbundle do yourdevicename\Internal Storage\Downloads..
    Po dokončení kopírování souboru můžete zařízení odpojit a instalaci dokončit později.
1. V zařízení HoloLens 2 Otevřete **nabídku Start**, vyberte **všechny aplikace** a spusťte aplikaci **Průzkumník souborů** .
1. Přejděte do složky Stažené soubory. Možná budete muset na levém panelu aplikace vybrat **Toto zařízení** jako první a pak přejít na soubory ke stažení.
1. Vyberte soubor yourapp. appxbundle.
1. Spustí se instalační program aplikace. Vyberte tlačítko **nainstalovat** a nainstalujte svou aplikaci.

Nainstalovaná aplikace se automaticky spustí po dokončení instalace.

![Instalace příkladů MRTK prostřednictvím instalačního programu aplikace](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a>Řešení potíží s instalací

Pokud se aplikaci nepovedlo nainstalovat, Projděte si následující problémy:

- Vaše aplikace je buď hlavní Build, nebo sestavení pro vydání.
- Vaše zařízení je aktualizováno na sestavení, ve kterém je tato funkce k dispozici.
- Jste [připojení k Internetu](hololens-network.md).
- Vaše [koncové body pro Microsoft Store](hololens-offline.md) jsou správně nakonfigurované.  

## <a name="web-installer"></a>Webový instalační program

Uživatelé můžou aplikaci nainstalovat přímo z webového serveru. Tento tok využívá instalační program aplikace v kombinaci s snadnou metodou stažení a instalace pro distribuci.

### <a name="how-to-set-up-web-install"></a>Jak nastavit webovou instalaci:

1. Ujistěte se, že je aplikace správně nakonfigurovaná pro instalaci.
1. Pomocí těchto [kroků Povolte instalaci z webové stránky](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).

### <a name="end-user-experience"></a>Činnost koncového uživatele:

1. Uživatel obdrží certifikát do zařízení a nainstaluje ho pomocí metody výše zvolené výše.
1. Uživatel navštíví adresu URL vytvořenou z výše uvedeného kroku.

Aplikace se teď nainstaluje do zařízení. Pokud chcete aplikaci najít, otevřete **nabídku Start** a vyberte tlačítko **všechny aplikace** a vyhledejte svou aplikaci.

- Další pomoc při řešení potíží s metodou instalace instalačního programu aplikace najdete v tématu [řešení potíží s instalačním programem aplikace](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).

> [!NOTE]
> Uživatelské rozhraní není během procesu aktualizace podporováno. Proto není možnost ShowPrompt na [této stránce](https://docs.microsoft.com/windows/msix/app-installer/update-settings) a související možnosti podporována.

## <a name="sample-apps"></a>Ukázkové aplikace

Vyzkoušejte si instalační program aplikace s některou z našich dostupných ukázkových aplikací. 
> [!div class="nextstepaction"]
> [Ukázkové aplikace](https://docs.microsoft.com/windows/mixed-reality/develop/features-and-samples?tabs=unity#sample-apps)
