---
title: odemčení funkcí Windows Holographic for Business
description: když upgradujete na Windows Holographic for Business, HoloLens poskytuje další funkce, které jsou navržené pro firmy.
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: c6d1225dc6da1c039a34fc2782f23330ae40f280
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427651"
---
# <a name="unlock-windows-holographic-for-business-features"></a>odemčení funkcí Windows Holographic for Business

> [!IMPORTANT]
> tato stránka se vztahuje pouze na HoloLens 1. generace.

Microsoft HoloLens je dostupná ve *verzi pro vývoj*, která se spouští Windows holografická (edice Windows 10, která je navržená pro HoloLens), a v [komerční sadě](hololens-commercial-features.md), která poskytuje další funkce navržené pro firmy.

po zakoupení komerční sady obdržíte licenci, která upgraduje Windows holografickou Windows Holographic for Business. Tuto licenci můžete na zařízení použít buď pomocí [poskytovatele správy mobilních zařízení (MDM)](#edition-upgrade-by-using-mdm) organizace, nebo [zřizovacího balíčku](#edition-upgrade-by-using-a-provisioning-package).

> [!TIP]
> v Windows 10 verze 1803 můžete kliknutím na **Nastavení** systém ověřit, že HoloLens upgradována na edici business edition  >  .

## <a name="edition-upgrade-by-using-mdm"></a>Upgrade edice pomocí MDM

Licenci Enterprise může použít libovolný poskytovatel MDM, který podporuje [poskytovatele služby WindowsLicensing Configuration Service Provider (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx). Nejnovější verze rozhraní Microsoft MDM API bude podporovat WindowsLicensing CSP.

podrobné pokyny pro upgrade HoloLens pomocí Microsoft Intune najdete v tématu [Upgrade zařízení s Windows holografickou na Windows Holographic for Business](/intune/holographic-upgrade).

 U jiných poskytovatelů MDM se můžou konkrétní kroky pro nastavení a nasazení zásad lišit.

## <a name="edition-upgrade-by-using-a-provisioning-package"></a>Upgrade edice pomocí zřizovacího balíčku

zřizovací balíčky jsou soubory vytvořené nástrojem pro návrháře konfigurace Windows, které pro zařízení používají zadanou konfiguraci.

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a>vytvoření zřizovacího balíčku, který upgraduje Windows holografické edice

1. [Vytvořte zřizovací balíček pro HoloLens.](hololens-provisioning.md)
1. Přejít na **nastavení modulu runtime**  >  **EditionUpgrade** a vyberte **EditionUpgradeWithLicense**.

    ![Je vybrána možnost upgradovat edici s nastavením licence.](images/icd1.png)

1. Vyhledejte soubor s licencí XML, který jste zadali při nákupu komerční sady.

    > [!NOTE]
    > [Další nastavení můžete nakonfigurovat v balíčku zřizování](hololens-provisioning.md).

1. V nabídce **File** (Soubor) vyberte **Save** (Uložit). 

1. Přečtěte si upozornění, že soubory projektu můžou obsahovat citlivé informace a klikněte na **OK**.

    > [!IMPORTANT]
    > Při vytváření zřizovacího balíčku můžete zahrnout citlivé informace do souborů projektu a soubor zřizovacího balíčku (. ppkg). I když máte možnost zašifrovat soubor. ppkg, soubory projektu nejsou šifrovány. Soubory projektu byste měli ukládat na bezpečném místě a odstraňovat soubory projektu, pokud už je nepotřebujete.

1. V nabídce **Export** vyberte **zřizovací balíček**.

1. Změňte **vlastníka** na **správce IT**, který nastaví prioritu tohoto zřizovacího balíčku tak, aby byla vyšší než jiné použité pro toto zařízení z různých zdrojů, a pak vyberte **Další**.

1. Nastavte hodnotu pro **verzi balíčku**.

    > [!TIP]
    > Můžete provádět změny stávajících balíčků a změnit číslo verze na aktualizace dřív použitých balíčků.

1. V **části vybrat podrobnosti zabezpečení pro zřizovací balíček** vyberte **Další**.

1. Výběrem možnosti **Další** zadejte umístění výstupu, kde má zřizovací balíček přejít po sestavení. ve výchozím nastavení používá Windows ICD jako výstupní umístění složku projektu.

    Volitelně můžete vybrat možnost **Procházet** a změnit výchozí umístění výstupu.

1. Vyberte **Další**.

1. Vyberte **sestavení** pro zahájení sestavování balíčku. Na stránce Build (sestavení) se zobrazí informace o projektu a indikátor průběhu indikuje stav sestavení.

1. Po dokončení sestavení vyberte **Dokončit**.

### <a name="apply-the-provisioning-package-to-hololens"></a>Použití zřizovacího balíčku na HoloLens

1. Připojte zařízení k počítači pomocí kabelu USB. Spusťte zařízení, ale nepokračujte za stránku **přizpůsobení** počátečního nastavení (první stránka s modrým polem). v počítači se HoloLens v průzkumníkovi souborů zobrazí jako zařízení.

    > [!NOTE]
    > pokud HoloLens zařízení běží Windows 10 verze 1607 nebo starší, otevřete průzkumníka souborů tak, že na zařízení krátce **vypínáte** a uvolníte tlačítka hlasitosti a **napájení** .

1. V Průzkumníku souborů přetáhněte zřizovací balíček (. ppkg) do úložiště zařízení.

1. i když je HoloLens stále na stránce **přizpůsobit** , krátce potiskněte a uvolněte **i tlačítko pro vypnutí a vypnutí** **hlasitosti** .

1. HoloLens vás vyzve k tomu, kdybyste balíček důvěřovali a chtěli byste ho použít. Potvrďte, že balíček důvěřujete.

1. Zobrazí se informace o tom, zda byl balíček úspěšně použit, nebo nikoli. Pokud se nepovedlo úspěšně použít, můžete balíček opravit a zkuste to znovu. V případě úspěchu pokračujte v nastavení zařízení.
