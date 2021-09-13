---
title: HoloLens Šifrování nástrojem BitLocker
description: Zjistěte, jak povolit šifrování zařízení nástrojem BitLocker za účelem ochrany souborů uložených HoloLens zařízeních s hybridní realitou.
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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032376"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a>HoloLens nástroje BitLocker (1. generace)

HoloLens (1. generace) i HoloLens 2 podporují šifrování zařízení pomocí BitLockeru, ale BitLocker je vždycky povolený na HoloLens 2.

Tento článek vám pomůže povolit a spravovat BitLocker na HoloLens (1. generace).

V HoloLens (1. generace) můžete šifrování zařízení nástrojem BitLocker povolit ručně nebo pomocí správy mobilních zařízení (MDM). Podle těchto pokynů povolte [šifrování zařízení nástrojem BitLocker,](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) abyste ochránili soubory a informace uložené v HoloLens. Šifrování zařízení pomáhá chránit vaše data pomocí metody šifrování AES-CBC 128, která je ekvivalentní metodě [EncryptionMethodByDriveType 3](/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) v poskytovateli konfigurační služby BitLockeru (CSP). Pracovníci, kteří mají správný šifrovací klíč (například heslo), ho mohou dešifrovat nebo provést obnovení dat.

## <a name="enable-device-encryption-using-mdm"></a>Povolení šifrování zařízení pomocí MDM

Pomocí zprostředkovatele Mobile Správa zařízení (MDM) můžete použít zásadu, která vyžaduje šifrování zařízení. Zásada, která se má použít, je [nastavení Security/RequireDeviceEncryption](/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) v CSP zásad.

[Přečtěte si pokyny k povolení šifrování zařízení pomocí Microsoft Intune.](/intune/compliance-policy-create-windows#windows-holographic-for-business)

Pokyny k dalším nástrojům MDM najdete v dokumentaci k poskytovateli MDM. Pokud váš poskytovatel MDM vyžaduje vlastní identifikátor URI pro šifrování zařízení, použijte následující konfiguraci:

- **Name**(Název): Název podle vašeho výběru.
- **Popis:** volitelné
- **OMA-URI:**`./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- **Datový typ:** celé číslo
- **Hodnota:**`1`

## <a name="enable-device-encryption-using-a-provisioning-package"></a>Povolení šifrování zařízení pomocí zřizovacího balíčku

Zřizovací balíčky jsou soubory vytvořené nástrojem Windows Configuration Designer, které pro zařízení používají zadanou konfiguraci. 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a>Vytvoření zřizovacího balíčku, který upgradu Windows edici Holographic a povolí šifrování

1. [Vytvořte zřizovací balíček pro HoloLens.](hololens-provisioning.md)
1. Přejděte na **Nastavení modulu runtime**  >  **Zabezpečení**  >  **zásad** a vyberte **VyžadovatDeviceEncryption.**

    ![Vyžadovat nastavení šifrování zařízení nakonfigurované na ano.](images/device-encryption.png)

1. Vyhledejte licenční soubor XML, který jste poskytli při nákupu komerční sady.

1. Přejděte na soubor s licencí XML, který jste poskytli při nákupu komerční sady, a vyberte ho.
    > [!NOTE]
    > V [zřizovacího balíčku můžete nakonfigurovat další nastavení.](hololens-provisioning.md)

1. V nabídce **File** (Soubor) klikněte na **Save** (Uložit). 

1. Přečtěte si upozornění s vysvětlením, že soubory projektu mohou obsahovat citlivé informace, a klikněte na **OK.**

    > [!IMPORTANT]
    > Při vytváření zřizovacího balíčku můžete do souborů projektu a souboru zřizovacího balíčku (.ppkg) zahrnout citlivé informace. I když máte možnost zašifrovat soubor .ppkg, soubory projektu nejsou zašifrované. Soubory projektu byste měli uložit na bezpečném místě a soubory projektu odstranit, pokud už je nepotřebujete.

1. V nabídce **Export** klikněte na **Zřizovací balíček**.
1. Změňte **možnost Vlastník** na Správce **IT,** která nastaví prioritu tohoto zřizovacího balíčku vyšší než zřizovací balíčky použité pro toto zařízení z jiných zdrojů, a pak vyberte **Další.**
1. Nastavte hodnotu pro **Package Version (Verze balíčku).**

    > [!TIP]
    > Můžete provádět změny existujících balíčků a změnit číslo verze tak, aby se dříve použité balíčky aktualizují.

1. V části **Vybrat podrobnosti zabezpečení pro zřizovací balíček** klikněte na **Další.**
1. Klikněte **na** Další a zadejte výstupní umístění, kam má zřizovací balíček po jeho vytváření přejít. Ve výchozím nastavení Windows ICD používá složku projektu jako výstupní umístění.

    Volitelně můžete kliknutím na Procházet změnit výchozí umístění výstupu.

1. Klikněte na **Next** (Další).
1. Kliknutím **na** Build (Sestavit) začněte vytvářet balíček. Informace o projektu se zobrazí na stránce sestavení a indikátor průběhu označuje stav sestavení.
1. Po dokončení sestavení klikněte na **Dokončit.**

### <a name="apply-the-provisioning-package-to-hololens"></a>Použijte zřizovací balíček pro HoloLens

1. Připojení zařízení připojte přes USB k počítači a spusťte ho,  ale neposoujte ho za stránku přizpůsobení prostředí počátečního nastavení (první stránka s modrým rámečem).
1. Krátce stiskněte a **uvolněte tlačítka Pro snížení** hlasitosti a Napájení současně. 
1. HoloLens se zobrazí jako zařízení v Průzkumník souborů počítači.
1. V Průzkumník souborů přetáhněte zřizovací balíček (.ppkg) do úložiště zařízení.
1. Krátce stiskněte a **uvolněte tlačítka Pro** snížení hlasitosti a Napájení současně na **stránce** Přizpůsobit. 
1. Zařízení se vás zeptá, jestli balíčku důvěřujete, a chcete ho použít. Ověřte, že balíčku důvěřujete.
1. Uvidíte, jestli se balíček úspěšně použil, nebo ne. Pokud se to nepovedlo, můžete balíček opravit a zkusit to znovu. Pokud byla úspěšná, pokračujte v nastavení zařízení.

> [!NOTE]
> Pokud bylo zařízení zakoupené před srpnem 2016, budete se k zařízení muset přihlásit pomocí účet Microsoft, získat nejnovější aktualizaci operačního systému a pak resetovat operační systém, abyste mohli použít zřizovací balíček.

## <a name="verify-device-encryption"></a>Ověření šifrování zařízení

Šifrování je v HoloLens. Ověření stavu šifrování zařízení:

- V HoloLens přejděte na **Nastavení**  >  **o systému.**  >   **BitLocker** je **povolený,** pokud je zařízení zašifrované. 

    ![Obrazovka s povoleným BitLockerem](images/about-encryption.png)
