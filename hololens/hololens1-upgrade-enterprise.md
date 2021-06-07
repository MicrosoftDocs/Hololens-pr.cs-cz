---
title: Odemknutí Windows Holographic for Business funkcí
description: Při upgradu na Windows Holographic for Business holoLens poskytuje další funkce, které jsou navržené pro firmy.
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
ms.openlocfilehash: 8d42c935e698f156aed894e4fa5012c9f04d8d49
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377630"
---
# <a name="unlock-windows-holographic-for-business-features"></a>Odemknutí Windows Holographic for Business funkcí

> [!IMPORTANT]
> Tato stránka se týká pouze HoloLens 1. generace.

Microsoft HoloLens je k dispozici v edici *Development Edition* s Windows Holographic (edice Windows 10, která je určená pro HoloLens), a v komerční edici [,](hololens-commercial-features.md)která poskytuje další funkce určené pro firmy.

Když si koupíte komerční sadu, obdržíte licenci, která upgradují Windows Holographic na Windows Holographic for Business. Tuto licenci můžete na zařízení použít buď pomocí poskytovatele správy mobilních zařízení [(MDM)](#edition-upgrade-by-using-mdm) organizace, nebo zřizovacího [balíčku](#edition-upgrade-by-using-a-provisioning-package).

> [!TIP]
> V Windows 10 verze 1803 můžete výběrem možnosti **Settings** System (Systém nastavení) zkontrolovat, jestli byl HoloLens upgradován na obchodní  >  **edici.**

## <a name="edition-upgrade-by-using-mdm"></a>Upgrade edice pomocí MDM

Podnikovou licenci může použít jakýkoli poskytovatel MDM, který podporuje poskytovatele konfiguračních služeb [WindowsLicensing (CSP).](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx) Nejnovější verze rozhraní MICROSOFT MDM API bude podporovat WindowsLicensing CSP.

Podrobné pokyny k upgradu HoloLens pomocí nástroje Microsoft Intune v tématu Upgrade zařízení s [Windows Holographic na Windows Holographic for Business](https://docs.microsoft.com/intune/holographic-upgrade).

 U jiných poskytovatelů MDM se konkrétní kroky pro nastavení a nasazení zásad můžou lišit.

## <a name="edition-upgrade-by-using-a-provisioning-package"></a>Upgrade edice pomocí zřizovacího balíčku

Zřizovací balíčky jsou soubory vytvořené nástrojem Windows Configuration Designer, který pro zařízení použije zadanou konfiguraci.

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a>Vytvoření zřizovacího balíčku, který upgraduuje edici Windows Holographic

1. [Vytvořte zřizovací balíček pro HoloLens.](hololens-provisioning.md)
1. Přejděte na **Nastavení modulu runtime**  >  **EditionUpgrade** a vyberte **EditionUpgradeWithLicense**.

    ![Upgrade edice s vybraným nastavením licence](images/icd1.png)

1. Vyhledejte licenční soubor XML, který jste poskytli při nákupu komerční sady.

    > [!NOTE]
    > V [zřizovacího balíčku můžete nakonfigurovat další nastavení.](hololens-provisioning.md)

1. V nabídce **File** (Soubor) vyberte **Save** (Uložit). 

1. Přečtěte si upozornění, že soubory projektu mohou obsahovat citlivé informace, a klikněte na **OK.**

    > [!IMPORTANT]
    > Při vytváření zřizovacího balíčku můžete do souborů projektu a souboru zřizovacího balíčku (.ppkg) zahrnout citlivé informace. I když máte možnost zašifrovat soubor .ppkg, soubory projektu nejsou zašifrované. Soubory projektu byste měli uložit na bezpečném místě a soubory projektu odstranit, pokud už je nepotřebujete.

1. V **nabídce Export** vyberte **Zřizovací balíček**.

1. Změňte **možnost Vlastník** na Správce **IT,** která nastaví prioritu tohoto zřizovacího balíčku tak, aby byla vyšší než jiná nastavení použitá na toto zařízení z různých zdrojů, a pak vyberte **Další.**

1. Nastavte hodnotu pro **Package Version (Verze balíčku).**

    > [!TIP]
    > Můžete provádět změny existujících balíčků a změnit číslo verze tak, aby se dříve použité balíčky aktualizují.

1. V **části Vybrat podrobnosti zabezpečení pro zřizovací balíček** vyberte **Další.**

1. Vyberte **Další** a zadejte výstupní umístění, kam má zřizovací balíček po jeho vytváření přejít. Windows ICD ve výchozím nastavení používá jako výstupní umístění složku projektu.

    Volitelně můžete vybrat Procházet **a** změnit výchozí umístění výstupu.

1. Vyberte **Další**.

1. Vyberte **Build (Sestavit)** a začněte vytvářet balíček. Na stránce sestavení se zobrazí informace o projektu a indikátor průběhu uvádí stav sestavení.

1. Po dokončení sestavení vyberte **Dokončit.**

### <a name="apply-the-provisioning-package-to-hololens"></a>Použití zřizovacího balíčku pro HoloLens

1. Pomocí kabelu USB připojte zařízení k počítači. Spusťte zařízení, ale neposířte ho za stránku přizpůsobení prostředí počátečního nastavení (první stránka s modrým rámečem).  Na počítači se HoloLens zobrazí jako zařízení v Průzkumník souborů.

    > [!NOTE]
    > Pokud zařízení HoloLens používá Windows 10 verze 1607 nebo starší, otevřete Průzkumník souborů tak, že na  zařízení  krátce stisknete a uvolníte tlačítka Pro vypnutí a Napájení.

1. V Průzkumník souborů přetáhněte zřizovací balíček (.ppkg) do úložiště zařízení.

1. Zatímco HoloLens je stále na **fitové** stránce, krátce  znovu stiskněte a uvolněte tlačítka **Pro** snížení hlasitosti a Napájení.

1. HoloLens se vás zeptá, jestli balíčku důvěřujete, a chcete ho použít. Ověřte, že balíčku důvěřujete.

1. Uvidíte, jestli se balíček úspěšně použil, nebo ne. Pokud se nepoupravil úspěšně, můžete balíček opravit a zkusit to znovu. V případě úspěchu pokračujte v nastavení zařízení.
