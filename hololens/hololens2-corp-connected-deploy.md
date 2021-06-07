---
title: Průvodce nasazením – Průvodci pro HoloLens 2 připojené k podnikové síti s Dynamics 365 – nasazení
description: Zjistěte, jak nastavit nasazení zařízení HoloLens 2 přes podnikovou připojenou síť pomocí průvodců Dynamics 365.
keywords: HoloLens, management, corporate connected, Dynamics 365 Guides, AAD, Azure AD, MDM, Mobile Správa zařízení
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: febf56f94a5cab623fd7ad08ae7abf7050224717
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377595"
---
# <a name="deploy---corporate-connected-guide"></a>Nasazení – Průvodce připojeným podnikem

Důležitou součástí každého nasazení je zajistit správné nastavení nasazení před tím, než ho sami otestujete, abyste zajistili bezproblémové prostředí pro koncového uživatele.

Vzhledem k tomu, že nasazujete certifikát Wi-Fi přes MDM, budeme muset nejprve nastavit HoloLens a zaregistrovat zařízení v otevřené síti Wi-Fi nebo v síti, která certifikát nevyžaduje. Jakmile HoloLens dokončí OOBE a zaregistroval se, zařízení obdrží síťový certifikát a obchodní soubor nakonfigurovaný dříve a my budeme moct ověřit, že zařízení obojí přijalo.

Potom budete moct potvrdit, že můžete vytvořit a provozovat testovací příručku.

## <a name="enrollment-validation"></a>Ověření registrace

Teď, když je všechno správně nakonfigurované pro azure AD a registraci MDM, by teď mělo být všechno v pořádku. Budete potřebovat připojení Wi-Fi zařízení HoloLens a jeden z dříve nakonfigurovaných uživatelských účtů Azure AD.

Pokud zařízení aktuálně není ve stavu továrního nastavení, je teď vhodné ho [namítt.](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)

1. Jakmile bude zařízení v OOBE, budete muset začít pracovat a postupovat podle pokynů.

2. Připojte se k Wi-Fi síti, která nevyžaduje pro připojení k Wi-Fi certifikáty. To umožní zařízení stáhnout certifikát, který se má po počátečním nastavení Wi-Fi v organizaci.

3. Kritická výzva se zobrazí, když se zobrazí dotaz **Kdo je vlastnit tuto holoLens?** Vyberte **Můj pracovní nebo školní účet vlastní a** zadejte své přihlašovací údaje k účtu Azure AD.

4. Po úspěšné registraci se zobrazí výzva k nastavení kódu PIN. Tento PIN kód je pro tohoto uživatele jedinečný pro toto zařízení. Budete také vyzváni k zadání nastavení kontroly Iris, hlasových dat a telemetrie a nakonec se dozvíte, jak otevřít nabídku Start a dokončit OOBE.

5. Jakmile se vrátíte na domovskou Mixed Reality, otevřete nabídka Start pomocí gesta **Start,** které jste se právě naučili.

6. Vyberte aplikaci **Nastavení** a vyberte **Systém.** První z informací, které uvidíte, je název vašeho zařízení, který pro zařízení HoloLens 2 bude HOLOLENS– následovaný řetězcem se šesti &quot; &quot; znaky.

7. Poznamenejte si tento název.

    ![Obrazovka Nastavení HoloLens 2](./images/hololens2-settings-about.jpg)

8. Ověřte, že je vaše zařízení úspěšně připojené k Azure AD. Existují dva způsoby:

    1.  Aplikace Nastavení. V **Nastavení vyberte** Účty **Přístup** do práce nebo do  ->  **školy.** Na této obrazovce můžete ověřit, že jste úspěšně zaregistrovaní. Zobrazí se stránka Připojeno k &quot;&#39;Azure AD. Připojeno přes *yourusername@nameofAAD.onmicrosoft.com* . Tím ověříte, že je vaše zařízení připojené k vaší organizaci&#39;Azure AD.

    1. Na [Azure Portal](https://portal.azure.com/#home). Přejděte na **Azure Active Directory**  ->    ->  **Zařízení Všechna zařízení** a vyhledejte název zařízení. V části Typ spojení se zobrazí text Připojeno k Azure AD.
        ![Ověření typu připojení v Azure AD](./images/hololens2-devices-all-devices.png)

9. Ověřte, že je zařízení zaregistrované v MDM. Existují dva způsoby:

    1. V **Nastavení** vyberte Účty **Přístup do** práce nebo do  ->  **školy.** Na této obrazovce můžete ověřit, že jste úspěšně zaregistrovaní. Zobrazí se stránka Připojeno k &quot;&#39;Azure AD. Připojeno přes *yourusername@nameofAAD.onmicrosoft.com* . Z tohoto přístupového pracovního nebo školního účtu vyberte Připojeno k &quot; názvuAAD&#39;Azure AD. Connected by yourusername@nameofAAD.onmicrosoft.com &quot; (Připojeno pomocí) **a vyberte tlačítko Info** (Informace).

    1. [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/#home). Přihlaste se a **vyberte Zařízení a** pak Všechna **zařízení.** Tady můžete vyhledat název zařízení HoloLens&#39;názvu. Měli byste vidět holoLens uvedený v Intune.

        ![Ověření správy pomocí Intune v Azure AD](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Wi-Fi certifikátu

Zařízení by teď mělo mít přijatý Wi-Fi certifikát. Nejjednodušším ověřením, které můžete provést, je pokus o připojení Wi-Fi, pro které jste&#39;obdrželi certifikát. Otevřete aplikaci **Nastavení,** přejděte na **Síť &amp; Internet**  ->  **Wi-Fi** a vyberte připojení Wi-Fi. Po připojení otevřete aplikaci Microsoft Edge a potvrďte, že můžete přejít na web.

Pokud chcete potvrdit, že jste certifikát obdrželi na zařízení, můžete použít [Správce certifikátů](https://docs.microsoft.com/hololens/certificate-manager).

## <a name="validate-lob-app-install"></a>Ověření instalace obchodní aplikace

Pokud chcete zobrazit průběh instalace spravované aplikace, buď uvidíte, jestli je aplikace nainstalovaná, nebo zaškrtněte Nastavení. Když nakonfigurujete obchodní aplikaci jako požadovanou instalaci pro naši skupinu, po registraci HoloLens s uživatelem v přiřazené skupině se aplikace automaticky stáhne do HoloLens.

Otevřete nabídka Start a vyberte **Všechny aplikace**. V závislosti na počtu aplikací možná budete muset  použít tlačítka pro zobrazení stránky nahoru nebo **dolů.**

Pokud chcete ověřit instalaci aplikace na zařízení, můžete to udělat přes Nastavení Účty Přístup do práce nebo do školy , vyberte účet, pak tlačítko Informace a posuňte se dolů, abyste viděli různé konfigurace a aplikace použité pro zařízení z  ->    ->  MDM. 

Pokud chcete ověřit instalaci z Intune, přejděte na stránku Stav instalace zařízení [MEM](https://endpoint.microsoft.com/#home)-> Všechny  ->     -> *aplikaceNázevOfNázevAuch*  ->  **zařízení.**

Další informace: [Nasazení aplikací Intune pro HoloLens](https://docs.microsoft.com/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>Ověření průvodců Dynamics 365

Existují režimy pro aplikaci Guides na HoloLens, vytváření a provoz. Před jeho provozováním budete muset dokončit průvodce vytvářením.

### <a name="authoring-the-guide"></a>Vytváření příručky

Pro toto rychlé ověření toho moc dělat nemusíme. Stačí vybrat průvodce, který jste připravili na svém počítači. Kvůli rychlému ověření [budete](https://docs.microsoft.comdynamics365/mixed-reality/guides/hololens-app-anchor)muset průvodce ukotvit, abyste mohli použít holografické ukotvení. Potom byste měli umístit [kroky a modely](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-orientation).

>[!NOTE]
> K přihlášení **k počítači a** autorovi na HoloLens budete potřebovat roli Vytváření. Role Operátor je jen pro čtení a nemá přístup k aplikaci pro počítače.

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>Použití příručky

Jakmile jsou hologramy na místě, můžete otestovat provoz průvodce. 
- Výběr **režimu operátora**
- Proklikejte se kroky průvodce.

Podrobnější pokyny k provozování průvodce najdete v těchto zdrojích informací:

[Přehled provozu průvodce v příručkách Dynamics 365](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-overview)

[Získejte orientaci na kartě Krok jako operátor v příručkách Dynamics 365.](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>Další krok 
> [!div class="nextstepaction"]
> [Nasazení připojené k podnikové síti – údržba](hololens2-corp-connected-maintain.md)
