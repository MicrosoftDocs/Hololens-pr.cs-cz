---
title: Průvodce nasazením – nasazení HoloLens 2 připojené ke cloudu ve velkém měřítku pomocí nástroje Remote Assist – nasazení
description: Zjistěte, jak ověřit registraci a vzdálenou pomoc pro zařízení HoloLens přes síť připojenou ke cloudu.
keywords: HoloLens, management, cloud connected, Remote Assist, AAD, Azure AD, MDM, Mobile Správa zařízení
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
ms.openlocfilehash: 4183bde30673f5147683e16b4d625f73b063c529
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377696"
---
# <a name="deploy---cloud-connected-guide"></a>Nasazení – Průvodce připojeným ke cloudu

Teď, když máte všechno nakonfigurované, byste měli být připravení distribuovat zařízení. Teď byste ale měli nastavení nejdřív ověřit. Nejprve by se měl ověřit proces připojení k Azure AD a registrace MDM a pak ověřit, že je možné provést volání vzdálené pomoci.

## <a name="enrollment-validation"></a>Ověření registrace

Teď, když je všechno správně nakonfigurované pro azure AD a registraci MDM, by teď mělo být všechno v pořádku. Budete&#39;připojení Wi-Fi zařízení HoloLens a také jeden z dříve nakonfigurovaných uživatelských účtů AAD.

Pokud zařízení není&#39;ve stavu továrního nastavení, je teď vhodné zařízení [namítt.](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)

1. Jakmile je zařízení v OOBE,&#39;začít pracovat a podle pokynů. 
1. Kritická výzva se zobrazí, když se zobrazí dotaz **Kdo je vlastnit tuto holoLens?** Vyberte **Můj pracovní nebo školní účet vlastní a** zadejte své přihlašovací údaje k účtu Azure AD.
1. Po úspěšné registraci se&#39;výzva k nastavení kódu PIN. Tento PIN kód je pro tohoto uživatele jedinečný pro toto zařízení. Budete také vyzváni k zadání nastavení kontroly Iris, hlasových dat a telemetrie a nakonec&#39;se dozvíte, jak otevřít nabídku Start a dokončit OOBE.
1. Jakmile se vrátíte do Mixed Reality domovská stránka, otevřete nabídka Start pomocí gesta **Start,** které jste se právě naučili.
1. Vyberte aplikaci **Nastavení** a vyberte **Systém.** První informace, kterou&#39;, je název vašeho zařízení, který pro zařízení HoloLens 2 bude HOLOLENS následovaný řetězcem se šesti &quot; &quot; znaky.
1. Poznamenejte si tento název.

![Nastavení HoloLens 2 – informace](./images/hololens2-settings-about.jpg)

7. Můžete ověřit, že je vaše zařízení úspěšně zaregistrované v Azure AD v aplikaci Nastavení. V **Nastavení vyberte** Účty **Přístup** do práce nebo do  ->  **školy.** Na této obrazovce můžete ověřit, že jste úspěšně zaregistrovaní. Zobrazí se stránka Připojeno k názvu&#39;&quot; Azure AD.  Připojeno _pomocí vašeho_ @ _uživatelského jménanázevAAD_.onmicrosoft.com &quot; .


Abychom ověřili, že zařízení je připojené k Azure [](https://portal.azure.com/#home)AD, můžeme zkontrolovat Azure Active Directory v Azure Portal Azure Active Directory Zařízení Všechna zařízení a vyhledat  ->    ->    ->  název zařízení. Můžete&#39;vidět, že zařízení je součástí Azure Active Directory.


![Azure Active Directory – zařízení](./images/aad-enrollment.png)

Dále se&#39;přihlásit k Centru pro správu [Microsoftu Endpoint Manager správce.](https://endpoint.microsoft.com/#home) Přihlaste se a **vyberte Zařízení a** pak Všechna **zařízení.** Tady můžete vyhledat název zařízení HoloLens&#39;názvu. Měli byste vidět holoLens uvedený v Intune.

![Intune – zařízení](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>Ověření volání vzdálené pomoci

Jakmile&#39;, že je zařízení zaregistrované v AAD i MDM, je&#39;k otestování volání vzdálené pomoci. K tomuto ověření&#39;zařízení HoloLens a počítač Windows 10 a druhý uživatelský účet Azure AD pro počítač.

V tomto kroku ověření se předpokládá, že jste už dokončili poslední krok ověření a vaše zařízení je zaregistrované a uživatel Azure AD je na zařízení.


1. Pokud ještě nemáte na počítači nainstalovaný Microsoft Teams, můžete [Teams stáhnout tady.](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)
2. Přihlaste se k Teams pomocí druhého uživatelského účtu Azure AD, který je aktuálně přihlášený k HoloLens. Po přihlášení do počítače budete připraveni přijmout volání.
3. Odemkněte HoloLens a přihlaste se.
4. Aplikaci Remote Assist spustíte tak, že **otevřete nabídku Start** a vyberete **Vzdálená pomoc.** Remote Assist je součástí nejen aplikace doručené pošty, ale také připnuté k holoLens 2&#39;nabídce Start. V případě, že&#39;připnutá k nabídka Start, otevřete seznam Všechny aplikace **a** vyhledejte ho.
5. Jakmile remote assist spustí, měl by identifikovat uživatele zařízení prostřednictvím [jednotného přihlašování](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) a přihlásit se k aplikaci.
6. V aplikaci vyberte **Hledat** a vyhledejte druhého uživatele na počítači. Výběrem uživatele zahájíte volání.
7. V počítači odpovězte na volání.

Blahopřejeme,&#39;jste se úspěšně připojili a jste na vzdáleném volání pomoci. Nezapomeňte vyzkoušet konkrétní funkce vzdálené pomoci, například pomocí:

- [Inkování poznámek](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Sdílení souboru a zobrazení ve smíšené realitě](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [Získání nápovědy v jiné aplikaci HoloLens](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>Další krok

> [!div class="nextstepaction"]
> [Nasazení připojené ke cloudu – údržba](hololens2-cloud-connected-maintain.md)