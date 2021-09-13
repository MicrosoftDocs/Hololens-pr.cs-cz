---
title: Průvodce nasazením – nasazení HoloLens 2 ve velkém s remote assistem – nasazení
description: Zjistěte, jak ověřit registraci a vzdálenou pomoc pro HoloLens zařízení přes síť připojenou ke cloudu.
keywords: HoloLens, správa, připojení ke cloudu, Remote Assist, AAD, Azure AD, MDM, Mobile Správa zařízení
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 519770badab9f260316fe4cfff4bf453a7c971a7
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032323"
---
# <a name="deploy---cloud-connected-guide"></a>Nasazení – Průvodce připojeným ke cloudu

Teď, když máte všechno nakonfigurované, byste měli být připravení distribuovat zařízení. Teď byste ale měli nastavení nejdřív ověřit. Nejprve by se měl ověřit proces připojení k Azure AD a registrace MDM a pak ověřit, že je možné provést volání vzdálené pomoci.

## <a name="enrollment-validation"></a>Ověření registrace

Teď, když je všechno správně nakonfigurované pro azure AD a registraci MDM, by teď zbytek měl být beze zbytku. Budete&#39;připojení Wi-Fi a HoloLens zařízení a také jeden z dříve nakonfigurovaných uživatelských účtů AAD.

Pokud zařízení není&#39;ve stavu továrního nastavení, je teď vhodné zařízení [namítt.](/hololens/hololens-recovery#clean-reflash-the-device)

1. Jakmile je zařízení v OOBE,&#39;začít pracovat a podle pokynů. 
1. Kritická výzva se zobrazí, když se zobrazí **dotaz Kdo který tento HoloLens?** Vyberte **Můj pracovní nebo školní účet vlastní a** zadejte své přihlašovací údaje k účtu Azure AD.
1. Po úspěšné registraci se&#39;výzva k nastavení kódu PIN. Tento KÓD PIN je pro tohoto uživatele jedinečný pro toto zařízení. Zobrazí se také výzva k zadání nastavení kontroly Iris, hlasových dat a telemetrie a nakonec se&#39;dozvíte, jak otevřít nabídku Start a dokončit OOBE.
1. Jakmile se vrátíte do Mixed Reality domovská stránka, otevřete nabídka Start pomocí gesta **Start,** které jste se právě naučili.
1. Vyberte aplikaci **Nastavení** a vyberte **Systém.** První informace, kterou&#39;, je název vašeho zařízení. Pro vaše zařízení HoloLens 2 bude HOLOLENS následovaný řetězcem se šesti &quot; &quot; znaky.
1. Poznamenejte si tento název.

![HoloLens 2 Nastavení – Informace.](./images/hololens2-settings-about.jpg)

7. Můžete ověřit, že je vaše zařízení úspěšně zaregistrované ve službě Azure AD v rámci Nastavení aplikace. V **Nastavení** vyberte Účty **Přístup do** práce nebo do  ->  **školy.** Na této obrazovce můžete ověřit, že jste úspěšně zaregistrovaní. Zobrazí se stránka Připojeno k názvu&#39;&quot; Azure AD.  Připojeno _pomocí uživatelského_ @ _jménanázevAAD_.onmicrosoft.com &quot; .


Abychom ověřili, že zařízení je připojené k Azure [](https://portal.azure.com/#home)AD, můžeme zkontrolovat Azure Active Directory na Azure Portal Azure Active Directory Zařízení Všechna zařízení a vyhledat  ->    ->    ->  název zařízení. Můžete&#39;, že zařízení je součástí Azure Active Directory.


![Azure Active Directory – Zařízení.](./images/aad-enrollment.png)

V dalším&#39;budete muset přihlásit do centra [Microsoft Endpoint Manager pro správu](https://endpoint.microsoft.com/#home). Přihlaste se a **vyberte Zařízení a** pak Všechna **zařízení.** Tady můžete vyhledat název vašeho HoloLens&#39;zařízení. Vaše aplikace by se měla zobrazit HoloLens v Intune.

![Intune – zařízení.](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>Ověření volání vzdálené pomoci

Jakmile&#39;, že je zařízení zaregistrované v AAD i MDM,&#39;otestovat volání vzdálené pomoci. K tomuto ověření&#39;musíte mít zařízení HoloLens, počítač Windows 10 a druhý uživatelský účet Azure AD pro počítač.

V tomto kroku ověření se předpokládá, že jste už dokončili poslední krok ověření a vaše zařízení je zaregistrované a uživatel Azure AD je na zařízení.


1. Pokud ještě nemáte na počítači Microsoft Teams, můžete si ho stáhnout Teams [tady.](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)
2. Přihlaste se Teams pomocí druhého uživatelského účtu Azure AD, než který je aktuálně přihlášený k vaší HoloLens. Po přihlášení do počítače budete připraveni přijmout volání.
3. Odemkněte HoloLens a přihlaste se.
4. Aplikaci Remote Assist spustíte tak, že **otevřete nabídku Start** a vyberete **Vzdálená pomoc.** Remote Assist je součástí nejen aplikace doručené pošty, ale také připnuté k HoloLens 2&#39;úvodní nabídce. V případě, že&#39;připnutá k nabídka Start, otevřete seznam Všechny aplikace **a** vyhledejte ho.
5. Po spuštění vzdáleného pomoci by měl uživatel zařízení identifikovat prostřednictvím [jednotného přihlašování](/azure/active-directory/manage-apps/what-is-single-sign-on) a přihlásit se k aplikaci.
6. V aplikaci vyberte **Hledat** a vyhledejte druhého uživatele na počítači. Výběrem uživatele zahájíte volání.
7. V počítači odpovězte na volání.

Blahopřejeme,&#39;jste se úspěšně připojili a jste na volání vzdálené pomoci. Nezapomeňte vyzkoušet konkrétní funkce vzdálené pomoci, například pomocí:

- [Inkování poznámek](/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Sdílení souboru a zobrazení ve smíšené realitě](/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Získání nápovědy v jiné HoloLens aplikaci](/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>Další krok

> [!div class="nextstepaction"]
> [Nasazení připojené ke cloudu – údržba](hololens2-cloud-connected-maintain.md)