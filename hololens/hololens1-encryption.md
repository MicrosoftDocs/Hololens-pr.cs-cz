---
title: HoloLens Šifrování BitLockeru
description: naučte se, jak povolit šifrování zařízení pomocí nástroje BitLocker k ochraně souborů uložených ve vašich zařízeních HoloLens hybridní realitu.
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/26/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: d5cf7385dd0a53c6b17f79e16364e84ab6ec867d
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427028"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a>šifrování bitlockeru HoloLens (1. generace)

HoloLens (1. generace) a HoloLens 2 podporují šifrování zařízení pomocí nástroje bitlocker, ale nástroj bitlocker je vždy povolený v HoloLens 2.

tento článek vám pomůže s povolením a správou nástroje BitLocker na HoloLens (1. generace).

v HoloLens (1. generace) můžete povolit šifrování zařízení pomocí nástroje BitLocker ručně nebo pomocí správy mobilních zařízení (MDM). Pomocí těchto pokynů povolte [šifrování zařízení s nástrojem BitLocker](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) k ochraně souborů a informací uložených v HoloLens. Šifrování zařízení pomáhá chránit vaše data pomocí metody šifrování AES-CBC 128, která je ekvivalentní [EncryptionMethodByDriveType metodě 3](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) ve zprostředkovateli kryptografických služeb (CSP) nástroje BitLocker. Pracovníci, kteří mají správný šifrovací klíč (například heslo), ho můžou dešifrovat nebo obnovení dat provést.

## <a name="enable-device-encryption-using-mdm"></a>Povolení šifrování zařízení pomocí MDM

Pomocí poskytovatele správy mobilních zařízení (MDM) můžete použít zásadu, která vyžaduje šifrování zařízení. Zásady, které se mají použít, jsou [nastavení zabezpečení/RequireDeviceEncryption](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) ve zprostředkovateli kryptografických služeb v zásadách.

[Přečtěte si pokyny pro povolení šifrování zařízení pomocí Microsoft Intune.](/intune/compliance-policy-create-windows#windows-holographic-for-business)

Další informace o dalších nástrojích MDM najdete v dokumentaci poskytovatele MDM. Pokud poskytovatel MDM vyžaduje pro šifrování zařízení vlastní identifikátor URI, použijte následující konfiguraci:

- **Název**: název dle vašeho výběru.
- **Popis**: volitelné
- **OMA-URI**: `./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- **Datový typ**: celé číslo
- **Hodnota**: `1`

## <a name="enable-device-encryption-using-a-provisioning-package"></a>Povolení šifrování zařízení pomocí zřizovacího balíčku

zřizovací balíčky jsou soubory vytvořené nástrojem pro návrháře konfigurace Windows, které pro zařízení používají zadanou konfiguraci. 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a>vytvoření zřizovacího balíčku, který upgraduje Windows holografickou edici a povoluje šifrování

1. [Vytvořte zřizovací balíček pro HoloLens.](hololens-provisioning.md)
1. Přejít na **nastavení modulu runtime**  >  **zásady**  >  **zabezpečení** a vyberte **RequireDeviceEncryption**.

    ![Vyžadovat nastavení šifrování zařízení nakonfigurované na Ano.](images/device-encryption.png)

1. Vyhledejte soubor s licencí XML, který jste zadali při nákupu komerční sady.

1. Vyhledejte a vyberte soubor s licencí XML, který jste zadali při nákupu komerční sady.
    > [!NOTE]
    > [Další nastavení můžete nakonfigurovat v balíčku zřizování](hololens-provisioning.md).

1. V nabídce **File** (Soubor) klikněte na **Save** (Uložit). 

1. Přečtěte si upozornění, které vysvětluje, že soubory projektu můžou obsahovat citlivé informace a klikněte na **OK**.

    > [!IMPORTANT]
    > Při vytváření zřizovacího balíčku můžete zahrnout citlivé informace do souborů projektu a soubor zřizovacího balíčku (. ppkg). I když máte možnost zašifrovat soubor. ppkg, soubory projektu nejsou šifrovány. Soubory projektu byste měli ukládat na bezpečném místě a odstraňovat soubory projektu, pokud už je nepotřebujete.

1. V nabídce **exportovat** klikněte na **zřizovací balíček**.
1. Změňte **vlastníka** na **správce IT**, který nastaví prioritu tohoto zřizovacího balíčku vyšší než zřizovací balíčky použité pro toto zařízení z jiných zdrojů a pak vyberte **Další**.
1. Nastavte hodnotu pro **verzi balíčku**.

    > [!TIP]
    > Můžete provádět změny stávajících balíčků a změnit číslo verze na aktualizace dřív použitých balíčků.

1. V části **Vybrat podrobnosti zabezpečení pro zřizovací balíček** klikněte na **Další**.
1. Klikněte na tlačítko **Další** a zadejte umístění výstupu, kde má zřizovací balíček přejít po sestavení. ve výchozím nastavení používá Windows ICD jako výstupní umístění složku projektu.

    Případně můžete kliknout na tlačítko Procházet a změnit výchozí umístění výstupu.

1. Klikněte na **Next** (Další).
1. Kliknutím na **sestavit** zahajte sestavování balíčku. Informace o projektu se zobrazí na stránce sestavení a indikátor průběhu indikuje stav sestavení.
1. Po dokončení sestavení klikněte na **Dokončit**.

### <a name="apply-the-provisioning-package-to-hololens"></a>Použití zřizovacího balíčku na HoloLens

1. Připojení zařízení přes USB do počítače a spusťte zařízení, ale nepokračujte za stránku **přizpůsobit** úvodním nastavením (první stránka s modrým polem).
1. Krátce stiskněte a uvolněte tlačítka **hlasitosti** a **napájení** současně.
1. HoloLens se v průzkumníku souborů na počítači zobrazí jako zařízení.
1. V Průzkumníku souborů přetáhněte zřizovací balíček (. ppkg) do úložiště zařízení.
1. Krátce stiskněte a uvolněte tlačítka **hlasitosti** a **napájení** na stránce **přizpůsobit** .
1. Zařízení vás vyzve, pokud zadáte důvěryhodný balíček a chcete ho použít. Potvrďte, že balíček důvěřujete.
1. Zobrazí se informace o tom, zda byl balíček úspěšně použit, nebo nikoli. Pokud se nezdařila, můžete balíček opravit a akci opakujte. V případě úspěchu pokračujte v nastavení zařízení.

> [!NOTE]
> Pokud se zařízení nakoupilo před 2016. srpna, budete se muset k zařízení přihlásit pomocí účet Microsoft, získat nejnovější aktualizaci operačního systému a potom obnovit operační systém, aby se zřizovací balíček mohl použít.

## <a name="verify-device-encryption"></a>Ověření šifrování zařízení

Šifrování je v HoloLens tiché. Ověření stavu šifrování zařízení:

- v HoloLens se o systému **Nastavení**  >  **systém**  >  . **BitLocker** je **povolený** , pokud je zařízení zašifrované. 

    ![O obrazovce s povoleným nástrojem BitLocker.](images/about-encryption.png)
