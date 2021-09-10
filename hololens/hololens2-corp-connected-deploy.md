---
title: průvodce nasazením – firemní připojení HoloLens 2 s průvodcem Dynamics 365 – nasazení
description: naučte se, jak nastavit nasazení zařízení HoloLens 2 přes podnikovou propojenou síť pomocí průvodců Dynamics 365.
keywords: HoloLens, správa, připojení k podnikové síti, příručky k Dynamics 365, AAD, Azure AD, MDM, správa mobilních zařízení
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
ms.openlocfilehash: 7df2b00b2d87be7b9ad4a5d84c83251ec0ebec4d
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428789"
---
# <a name="deploy---corporate-connected-guide"></a>Nasazení – průvodce připojená k podnikové síti

Důležitou součástí každého nasazení je zajistit, aby vaše nasazení bylo správně nastaveno před tím, než je otestuje, aby bylo zajištěno hladké prostředí pro koncového uživatele.

vzhledem k tomu, že nasazujeme Wi-Fi certifikát přes MDM, musíme nejdřív nastavit HoloLens a zaregistrovat zařízení v otevřené Wi-Fi síti nebo v síti, která certifikát nevyžaduje. po dokončení počátečního nastavení a zaregistrování HoloLens zařízení obdrží síťový certifikát a objekt LOB nakonfigurovaný dříve a my bude možné ověřit, že zařízení přijali obě.

Následně budete moci potvrdit, že můžete vytvářet a používat Průvodce testováním.

## <a name="enrollment-validation"></a>Ověřování registrace

Teď, když je všechno správně nakonfigurované pro Azure AD a registraci MDM, by teď mělo být funkce REST přichycená. budete potřebovat připojení Wi-Fi a zařízení HoloLens a jeden z dříve konfigurovaných uživatelských účtů Azure AD.

Pokud vaše zařízení není v současné době ve stavu továrního nastavení, je teď vhodné [zařízení znovu zablikat](/hololens/hololens-recovery#clean-reflash-the-device).

1. Jakmile je zařízení v POČÁTEČNÍm prostředí, budete muset spustit interakci a postupovat podle výzev.

2. Připojení k otevřené síti Wi-Fi, která nevyžaduje certifikáty pro připojení k Wi-Fi. Tím umožníte, aby zařízení po počátečním nastavení stáhlo certifikát, který se má použít v Wi-Fi organizace.

3. po zobrazení výzvy **Kdo vlastní této HoloLens** , zobrazí se kritická výzva? Vyberte možnost **Moje práce nebo škola, kterou vlastní** , a zadejte své přihlašovací údaje k účtu Azure AD.

4. Po úspěšné registraci se zobrazí výzva k nastavení kódu PIN. Tento kód PIN je pro tohoto uživatele unikátní pro toto zařízení. Také budete vyzváni k zobrazení Iris, hlasových dat a nastavení telemetrie a nakonec budete moci zjistit, jak otevřít nabídku Start a dokončit nástroj OOBE.

5. jakmile se rozhodnete pro domovskou stránku hybridní Reality, otevřete nabídka Start pomocí **gesta Start** , které jste právě naučili.

6. vyberte aplikaci **Nastavení** a vyberte možnost **systém**. první část informací, které vidíte, je název vašeho zařízení, který pro vaše zařízení HoloLens 2 bude HoloLens a musí obsahovat &quot; &quot; šest znakového řetězce.

7. Tento název si poznamenejte.

    ![Nastavení obrazovka HoloLens 2.](./images/hololens2-settings-about.jpg)

8. Ověřte, jestli je vaše zařízení úspěšně připojené ke službě Azure AD. Existují dva způsoby:

    1.  aplikace Nastavení. z **Nastavení** vyberte **účty**  ->  **přístup do práce nebo do školy**. Z této obrazovky můžete ověřit, že jste úspěšně zaregistrovali, zobrazením &quot; připojení k nameofAAD&#39;s Azure AD. Připojil (a) *yourusername@nameofAAD.onmicrosoft.com* . Ověří se, jestli je vaše zařízení připojené k vaší organizaci&#39;s Azure AD.

    1. [Azure Portal](https://portal.azure.com/#home). přejít na **Azure Active Directory**  ->  **zařízení**  ->  **všechna zařízení** a vyhledejte název zařízení. V části Typ připojení se zobrazí jako "připojené k Azure AD".
        ![Ověřte typ spojení ve službě Azure AD.](./images/hololens2-devices-all-devices.png)

9. Ověřte, jestli je zařízení zaregistrované v MDM. Existují dva způsoby:

    1. z **Nastavení** vyberte **účty**  ->  **přístup do práce nebo do školy**. Z této obrazovky můžete ověřit, že jste úspěšně zaregistrovali, zobrazením &quot; připojení k nameofAAD&#39;s Azure AD. Připojil (a) *yourusername@nameofAAD.onmicrosoft.com* . Z tohoto přístupového nebo školního účtu vyberte &quot; připojení k nameofAAD&#39;s Azure AD. Propojili yourusername@nameofAAD.onmicrosoft.com &quot; a vyberte tlačítko **informace** .

    1. [Microsoft Endpoint Manager centrum pro správu](https://endpoint.microsoft.com/#home). Přihlaste se a vyberte  **zařízení**  a potom  **všechna zařízení**. odtud můžete vyhledat&#39;název HoloLens zařízení. měli byste být schopni zobrazit vaše HoloLens uvedené v intune.

        ![Ověřte, že se spravuje přes Intune ve službě Azure AD.](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a>Wi-Fi ověření certifikátu

Teď by zařízení mělo přijmout Wi-Fi certifikát. Nejjednodušším ověřováním se můžete pokusit připojit se k Wi-Fi připojení, pro které jste&#39;obdrželi certifikát. otevřete aplikaci **Nastavení** a přejděte k **síti &amp; Internet**  ->  **Wi-fi** a vyberte připojení Wi-fi. po připojení otevřete aplikaci Microsoft Edge a potvrďte, že můžete přejít na web.

Pokud chcete potvrdit, že jste certifikát obdrželi na zařízení, můžete použít [Správce certifikátů](/hololens/certificate-manager).

## <a name="validate-lob-app-install"></a>Ověřit instalaci aplikace LOB

pokud se chcete podívat na průběh instalace spravované aplikace, uvidíte buď, jestli je aplikace nainstalovaná, nebo zkontrolujte Nastavení. když nakonfigurujete aplikaci LOB jako povinnou instalaci pro naši skupinu, po registraci HoloLens s uživatelem v přiřazené skupině se aplikace automaticky stáhne do HoloLens.

otevřete nabídka Start a vyberte **všechny aplikace**. V závislosti na počtu aplikací, které máte, možná budete muset použít tlačítka **Page Up** nebo **Page Down** .

pokud chcete ověřit instalaci aplikace na zařízení, můžete to udělat prostřednictvím **Nastavení**  ->  **účtů**  ->  **přístup do práce nebo do školy**; vyberte účet a potom přejděte dolů  , abyste viděli různé konfigurace a aplikace, které se na zařízení nastavily z MDM.

Pokud chcete instalaci ověřit z Intune, přejděte na stránku [](https://endpoint.microsoft.com/#home)  ->  **aplikace** pro vyžádání portálu – > všechny **aplikace**  -> *TheNameOfYourApp*  ->  **stav instalace zařízení** .

Další informace: [nasazení aplikace Intune pro HoloLens](/hololens/app-deploy-intune)

## <a name="validate-dynamics-365-guides"></a>Ověřit Příručky k Dynamics 365

k dispozici jsou režimy pro aplikaci průvodce HoloLens, vytváření a provoz. Před tím, než začnete pracovat, bude nutné dokončit vytváření průvodce.

### <a name="authoring-the-guide"></a>Vytváření Průvodce

Pro toto rychlé ověřování nepotřebujeme spoustu. Jednoduše vyberte Průvodce, který jste připravili na počítači. Budete muset vytvořit [kotvu příručky](/dynamics365/mixed-reality/guides/hololens-app-anchor), abyste mohli rychlé ověření použít holografickou kotvu. Následně byste měli [umístit kroky a modely](/dynamics365/mixed-reality/guides/hololens-app-orientation).

>[!NOTE]
> Budete potřebovat roli **vytváření** , abyste se mohli přihlásit k počítači a vytvářet HoloLens. Role operátora je jen pro čtení a nemá přístup k aplikaci pro počítače.

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a>Provozování příručky

Až budou vaše hologramy na místě, můžete otestovat provoz vaší příručky. 
- Vybrat **režim operátoru**
- Klikněte na kroky v průvodci.

Podrobnější informace o tom, jak pracovat s příručkou, najdete v těchto zdrojích:

[Přehled operačního systému v příručkách k Dynamics 365](/dynamics365/mixed-reality/guides/operator-overview)

[Seznámení s kartou Step jako operátor v příručkách Dynamics 365](/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a>Další krok 
> [!div class="nextstepaction"]
> [Firemní připojené nasazení – údržba](hololens2-corp-connected-maintain.md)
