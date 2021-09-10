---
title: průvodce nasazením – Cloud připojený HoloLens 2 ke škálování pomocí funkce Remote Assist – nasazení
description: zjistěte, jak ověřit registraci a vzdálenou pomoc pro zařízení HoloLens přes síť propojenou s cloudem.
keywords: HoloLens, správa, připojení k cloudu, vzdálená pomoc, AAD, Azure AD, MDM, správa mobilních zařízení
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
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428749"
---
# <a name="deploy---cloud-connected-guide"></a>Nasazení – Průvodce připojením k cloudu

Teď, když máte všechno nakonfigurované, byste měli být připraveni k distribuci zařízení. Nyní je však třeba nejprve ověřit instalaci. Nejprve je třeba ověřit proces registrace služby Azure AD a registraci MDM a potom ověřit, zda je možné umístit vzdálené volání funkce Remote Assist.

## <a name="enrollment-validation"></a>Ověřování registrace

Teď, když je všechno správně nakonfigurované pro Azure AD a registraci MDM, by teď mělo být funkce REST přichycená. &#39;potřebujete připojení Wi-Fi a HoloLens zařízení a také jeden z dříve konfigurovaných uživatelských účtů AAD.

Pokud zařízení není v současné době ve stavu nastavení továrny&#39;, teď by bylo vhodné čas [zařízení znovu zablikat](/hololens/hololens-recovery#clean-reflash-the-device).

1. Jakmile je zařízení v POČÁTEČNÍm prostředí,&#39;vše musí začít interaktivně pracovat a postupovat podle výzev. 
1. po zobrazení výzvy **Kdo vlastní této HoloLens** , zobrazí se kritická výzva? Vyberte možnost **Moje práce nebo škola, kterou vlastní** , a zadejte své přihlašovací údaje k účtu Azure AD.
1. Po úspěšné registraci se&#39;zobrazí výzva k nastavení kódu PIN. Tento kód PIN je pro tohoto uživatele unikátní pro toto zařízení. Také budete vyzváni k zobrazení Iris, hlasových dat a nastavení telemetrie a nakonec&#39;plně se naučíte, jak otevřít nabídku Start a dokončit nástroj OOBE.
1. jakmile se rozhodnete na domovské stránce smíšené reality, otevřete nabídka Start pomocí **gesta Start** , které jste právě naučili.
1. vyberte aplikaci **Nastavení** a vyberte možnost **systém.** první část informací, které&#39;te, najdete v části je název vašeho zařízení, který pro vaše zařízení HoloLens 2 bude mít &quot; HoloLens a &quot; za ním následuje šest znakového řetězce.
1. Tento název si poznamenejte.

![HoloLens 2 Nastavení-o.](./images/hololens2-settings-about.jpg)

7. můžete ověřit, jestli je vaše zařízení úspěšně zaregistrované ve službě Azure AD v rámci aplikace Nastavení. z **Nastavení** vyberte **účty**  ->  **přístup do práce nebo do školy**. Z této obrazovky můžete ověřit, že jste úspěšně zaregistrovali, zobrazením &quot; připojení k _nameofAAD_&#39;s Azure AD. Připojeno pomocí _uživatelské_jméno_ @ _nameofAAD_. onmicrosoft.com &quot; .


pokud chcete ověřit, že je zařízení připojené ke službě Azure AD, můžete zkontrolovat Azure Active Directory ze [Azure Portal](https://portal.azure.com/#home)  ->  **Azure Active Directory**  ->  **zařízení**  ->  **všechna zařízení** a vyhledat název zařízení. &#39;vše je možné vidět, že zařízení je součástí Azure Active Directory.


![Azure Active Directory – zařízení](./images/aad-enrollment.png)

dál&#39;vše se musí přihlašovat do [centra pro správu Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home). Přihlaste se a vyberte **zařízení** a potom **všechna zařízení**. tady můžete vyhledat HoloLens zařízení&#39;s názvem. měli byste být schopni zobrazit vaše HoloLens uvedené v intune.

![Intune – zařízení.](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a>Ověřování volání vzdálené pomoci

Jakmile se&#39;ověříte, že je vaše zařízení zaregistrované v AAD i MDM,&#39;čas, kdy se má uskutečnit test vzdáleného asistenčního volání. pro toto ověření potřebujete&#39;HoloLens zařízení a Windows 10 počítač a také druhý uživatelský účet Azure AD pro počítač.

Tento krok ověření předpokládá, že jste dřív dokončili poslední krok ověření a vaše zařízení je zaregistrované a uživatel Azure AD je na zařízení.


1. pokud ještě nemáte na svém počítači nainstalovanou Microsoft Teams, můžete [si Teams stáhnout tady](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app).
2. přihlaste se Teams pomocí druhého uživatelského účtu Azure AD, než je ten, který je aktuálně přihlášený k vašemu HoloLens. Po přihlášení k počítači budete připraveni přijmout volání.
3. odemkněte HoloLens a přihlaste se.
4. Pokud chcete spustit aplikaci Vzdálená pomoc, otevřete **nabídku Start** a vyberte **Vzdálená pomoc**. funkce Remote Assist není určená jenom jako aplikace doručené pošty, ale připnuté do nabídky start HoloLens 2&#39;s. v případě, že se&#39;t, že se zobrazuje jako připnuté na nabídka Start, otevřete seznam **všechny aplikace** a vyhledejte ho.
5. Po spuštění funkce Vzdálená pomoc by měl uživatel zařízení identifikovat pomocí [jednotného přihlašování](/azure/active-directory/manage-apps/what-is-single-sign-on) a přihlásit se k aplikaci.
6. V aplikaci vyberte **Hledat** a vyhledejte druhého uživatele na počítači. Vyberte uživatele pro spuštění volání.
7. Z počítače odpovězte na volání.

Gratulujeme,&#39;se úspěšně připojili a jsou na svém volání vzdáleného asistence. Ujistěte se, že jste si vyzkoušeli konkrétní funkce vzdálené pomoci, jako je například použití:

- [Rukopisné poznámky](/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [Sdílení souboru a zobrazení ve smíšené realitě](/dynamics365/mixed-reality/remote-assist/display-save-files)
- [získat pomoc v jiné aplikaci HoloLens](/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a>Další krok

> [!div class="nextstepaction"]
> [Nasazení propojené s cloudem – údržba](hololens2-cloud-connected-maintain.md)