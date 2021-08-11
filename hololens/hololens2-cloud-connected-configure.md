---
title: Průvodce nasazením – nasazení HoloLens 2 ve velkém s remote assistem – konfigurace
description: Zjistěte, jak nastavit konfigurace pro registraci HoloLens přes síť připojenou ke cloudu ve velkém měřítku pomocí remote assistu.
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
ms.openlocfilehash: 8e6999157c6f5a396812df26f748c771581b61d63709918abb2ae45063810ef8
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660562"
---
# <a name="configure---cloud-connected-guide"></a>Konfigurace – Průvodce připojeným ke cloudu

V této části příručky si&#39;, jak pro vašeho tenanta nastavit automatickou registraci a jak používat licence pro Intune i Remote Assist.

## <a name="azure-users-and-groups"></a>Uživatelé a skupiny Azure

Azure a Intune tímto rozšířením používají uživatele a skupiny k přiřazení konfigurací a licencí. Pro ověření tohoto toku nasazení a možnost volání vzdálené pomoci od jednoho uživatele k druhému budete potřebovat&#39;uživatelské účty.

Pro účely přiřazování licencí můžeme vytvořit jednu skupinu uživatelů. Oba uživatele můžeme připojit ke stejné skupině a pro tuto skupinu použít licenci pro Intune a Remote Assist.

Pokud ještě&#39;přístup ke dvěma účtům Azure AD ve skupině uživatelů, můžete použít . Tady jsou úvodní příručky pro:

- [Jak vytvořit uživatele](/mem/intune/fundamentals/quickstart-create-user)
- [Jak vytvořit skupinu](/mem/intune/fundamentals/quickstart-create-group)
- [Přidání uživatelů do skupiny](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Přidání vytvořených uživatelů k vytvoření skupiny
- [Konfigurace Azure AD tak, aby skupině uživatelů umožnila připojovat](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) se k zařízením – Ujistěte se, že nová skupina uživatelů má oprávnění k registraci zařízení do Azure AD.

## <a name="auto-enrollment-on-hololens-2"></a>Automatická registrace na HoloLens 2

Pokud chcete mít bezproblémové a bezproblémové prostředí, můžete použít nastavení AADJ (Azure Active Directory Join) a automatické registrace do Intune pro zařízení HoloLens 2. To uživatelům umožní zadat přihlašovací údaje organizace během spuštění počítače a automaticky se zaregistrovat v Azure AD a zaregistrovat zařízení do MDM.

Pomocí [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)můžeme vybrat služby a procházet několik stránek, dokud nebude možné vybrat Získat zkušební Premium verzi. Můžete si všimnout, že Azure Active Directory Premium 1 a 2, protože automatická registrace P1 je dostačující. Můžeme vybrat Intune, vybrat obor uživatele pro automatickou registraci a vybrat skupinu, která byla vytvořena dříve.

Úplné podrobnosti a kroky najdete v průvodci [povolením automatické registrace pro Intune.](/mem/intune/enrollment/quickstart-setup-auto-enrollment)

## <a name="application-licenses"></a>Licence aplikací

Licence aplikace umožňuje uživateli buď nainstalovat zakoupené aplikace společnosti, nebo upgradovat z bezplatné zkušební verze na plnou verzi aplikace. Licence aplikací je možné použít pro uživatele, skupiny uživatelů nebo skupiny zařízení. K&#39;remote assist budete potřebovat licence remote assist pro uživatele ve vaší organizaci. Pro účely této příručky přiřadíme licence Remote Assistu ke skupině uživatelů, kterou jsme vytvořili výše v části Uživatelé a [skupiny Azure.](hololens2-cloud-connected-configure.md#azure-users-and-groups)

Požadavky na licence se mohou lišit v závislosti na tom, jestli uživatel bude volat vzdálenou pomoc ze zařízení nebo bude vzdáleným spolupracovníkem z Microsoft Teams. Ve výchozím nastavení jsou políčka Remote Assist a Teams označená. Pro účely tohoto průvodce doporučujeme nechat zaškrtnutá výchozí políčka.

1. Další informace o různých [licenčních a produktových požadavcích na roli.](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role) Existuje několik různých typů licencí Remote Assistu, takže se ujistěte, že máte ty správné pro vaše potřeby.
2. Musíte&#39;licenci [získat.](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
3. [Použijte své licence](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) na skupinu.

## <a name="next-step"></a>Další krok

> [!div class="nextstepaction"]
> [Nasazení připojené ke cloudu – nasazení](hololens2-cloud-connected-deploy.md)