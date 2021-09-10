---
title: postup při načítání a instalaci aplikací prostřednictvím instalačního programu aplikace HoloLens 2
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
ms.openlocfilehash: 071dfb3b211928c561fc84754dd7ed4d64886f61
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427106"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a>instalace aplikací na HoloLens 2 prostřednictvím instalačního programu aplikace

> [!NOTE]
> tato funkce byla dostupná ve [Windows holografické verzi 20H2 – prosince 2020 Update](hololens-release-notes.md). Ujistěte se, že je vaše zařízení [aktualizované](hololens-update-hololens.md) , aby tuto funkci používalo.

přidali jsme **novou funkci (instalační program aplikace), která vám umožní na zařízeních HoloLens 2 plynule instalovat aplikace** . Tato funkce bude **ve výchozím nastavení zapnutá pro nespravovaná zařízení**. Aby nedošlo k narušení podniků, instalační program aplikace nebude v tuto chvíli **k dispozici pro spravovaná zařízení** .  

Zařízení se považuje za spravované, pokud platí **některá** z následujících podmínek:

- [Zaregistrované](hololens-enroll-mdm.md) MDM
- Nakonfigurováno pomocí [zřizovacího balíčku](hololens-provisioning.md)
- [Identita](hololens-identity.md) uživatele je Azure AD

Nyní je možné instalovat aplikace bez nutnosti povolit vývojářský režim ani používat portál zařízení.  stáhněte si do svého zařízení (přes USB nebo přes Microsoft Edge) sadu appx a přejděte do sady appx v průzkumníkovi souborů, kde se zobrazí výzva k ukončení instalace.  Případně můžete [zahájit instalaci z webové stránky](/windows/msix/app-installer/installing-windows10-apps-web). stejně jako aplikace, které instalujete z Microsoft Store nebo bokem pomocí možnosti nasazení aplikace LOB pro správu mobilních aplikací, musí být aplikace digitálně podepsané pomocí [nástroje signer](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) a [certifikát použitý k podepsání musí být](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) před nasazením aplikace důvěryhodný pro HoloLens zařízení.

## <a name="requirements"></a>Požadavky

### <a name="for-your-devices"></a>Pro vaše zařízení:

tato funkce je v současnosti dostupná v Windows holografické 20H2 buildy pro HoloLens 2 zařízení. Zajistěte, aby všechna zařízení používající tuto metodu byla [aktualizovaná](hololens-update-hololens.md).

### <a name="for-your-apps"></a>Pro vaše aplikace:

Konfigurace řešení vaší aplikace musí být buď **Hlavní** , nebo **verze** , protože instalační program aplikace bude používat závislosti ze Storu. Přečtěte si další informace o [vytváření balíčků aplikací](/windows/msix/app-installer/create-appinstallerfile-vs).

Aplikace, které jsou nainstalované přes tuto metodu, musí být digitálně podepsané. K podepsání aplikace budete muset použít certifikát. Můžete buď získat certifikát ze [seznamu důvěryhodných certifikačních autorit MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT). v takovém případě nebudete muset provádět žádnou další akci. Případně můžete podepsat vlastní certifikát, ale tento certifikát bude nutné do zařízení vložit.

- Jak podepisovat aplikace [pomocí nástroje Sign Tool](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**Možnosti certifikátu:**

- [Seznam důvěryhodných certifikačních autorit MS](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**Vyberte metodu nasazení certifikátu.**

- [Balíčky zřizování](hololens-provisioning.md) se dají použít na místní zařízení.
- MDM se dá použít k [aplikování certifikátů s konfiguracemi zařízení](/mem/intune/protect/certificates-configure).
- Použijte [Správce certifikátů](certificate-manager.md)zařízení.

## <a name="installation-method"></a>Metoda instalace

1. Ověřte, že se zařízení nepovažuje za spravované.
1. ověřte, že zařízení HoloLens 2 je zapnuté a že jste přihlášení.
1. na svém počítači přejděte do vlastní aplikace a zkopírujte yourapp. appxbundle do yourdevicename\Internal Storage \Downloads.
    Po dokončení kopírování souboru můžete zařízení odpojit a instalaci dokončit později.
1. v zařízení HoloLens 2 otevřete **nabídku Start**, vyberte **všechny aplikace** a spusťte aplikaci **průzkumník souborů** .
1. Přejděte do složky Stažené soubory. Možná budete muset na levém panelu aplikace vybrat **Toto zařízení** jako první a pak přejít na soubory ke stažení.
1. Vyberte soubor yourapp. appxbundle.
1. Spustí se instalační program aplikace. Vyberte tlačítko **nainstalovat** a nainstalujte svou aplikaci.

Nainstalovaná aplikace se automaticky spustí po dokončení instalace.

![Instalace příkladů MRTK prostřednictvím instalačního programu aplikace.](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a>Řešení potíží s instalací

Pokud se aplikaci nepovedlo nainstalovat, Projděte si následující problémy:

- Vaše aplikace je buď hlavní Build, nebo sestavení pro vydání.
- Vaše zařízení je aktualizováno na sestavení, ve kterém je tato funkce k dispozici.
- Jste [připojení k Internetu](hololens-network.md).
- vaše [koncové body pro Microsoft Store](hololens-offline.md) jsou správně nakonfigurované.  

## <a name="web-installer"></a>Webový instalační program

Uživatelé můžou aplikaci nainstalovat přímo z webového serveru. Tento tok využívá instalační program aplikace v kombinaci s snadnou metodou stažení a instalace pro distribuci.

### <a name="how-to-set-up-web-install"></a>Jak nastavit webovou instalaci:

1. Ujistěte se, že je aplikace správně nakonfigurovaná pro instalaci.
1. Pomocí těchto [kroků Povolte instalaci z webové stránky](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).

### <a name="end-user-experience"></a>Činnost koncového uživatele:

1. Uživatel obdrží certifikát do zařízení a nainstaluje ho pomocí metody výše zvolené výše.
1. Uživatel navštíví adresu URL vytvořenou z výše uvedeného kroku.

Aplikace se teď nainstaluje do zařízení. pokud chcete najít aplikaci, otevřete **nabídka Start** a vyberte tlačítko **všechny aplikace** a najděte svou aplikaci.

- Další pomoc při řešení potíží s metodou instalace instalačního programu aplikace najdete v tématu [řešení potíží s instalačním programem aplikace](/windows/msix/app-installer/troubleshoot-appinstaller-issues).

> [!NOTE]
> Uživatelské rozhraní není během procesu aktualizace podporováno. Proto není možnost ShowPrompt na [této stránce](/windows/msix/app-installer/update-settings) a související možnosti podporována.

## <a name="sample-apps"></a>Ukázkové aplikace

Vyzkoušejte si instalační program aplikace s některou z našich dostupných ukázkových aplikací. 
> [!div class="nextstepaction"]
> [Ukázkové aplikace](/windows/mixed-reality/develop/features-and-samples)
