---
title: průvodce nasazením – Cloud připojený HoloLens 2 ke škálování pomocí programu vzdálená pomoc – konfigurace
description: naučte se, jak nastavit konfigurace pro registraci HoloLens zařízení přes cloudovou síť připojenou ke škálování pomocí funkce vzdálená pomoc.
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
ms.openlocfilehash: eb96f1cdc799551297c0373268e8cc8f35c6bd06
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635139"
---
# <a name="configure---cloud-connected-guide"></a>Konfigurace – Průvodce připojením k cloudu

V této části příručky&#39;vše, jak nastavit automatický zápis pro vašeho tenanta a jak používat licence pro Intune i vzdálenou pomoc.

## <a name="azure-users-and-groups"></a>Uživatelé a skupiny Azure

Azure a Intune pomocí tohoto rozšíření využívají uživatele a skupiny, které vám pomůžou přiřadit konfigurace a licence. Pro účely ověření tohoto toku nasazení a umožnění vzdáleného volání pomoci od jednoho uživatele k jinému&#39;potřebujete, aby byly dva uživatelské účty.

Pro účely přiřazování licencí můžeme vytvořit jednu skupinu uživatelů. Oba uživatele můžeme připojit ke stejné skupině a použít licenci pro Intune a vzdálenou pomoc k této skupině.

Pokud nemáte&#39;t už máte přístup ke dvěma účtům Azure AD ve skupině uživatelů, můžete použít. Tady jsou Úvodní příručky pro:

- [Postup vytvoření uživatele](/mem/intune/fundamentals/quickstart-create-user)
- [Vytvoření skupiny](/mem/intune/fundamentals/quickstart-create-group)
- [Přidat uživatele do skupiny](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – přidat vytvořené uživatele k vytvoření skupiny
- [Konfigurace služby Azure AD tak, aby povolovala skupině uživatelů připojení zařízení](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – zajistěte, aby nová skupina uživatelů měla oprávnění k registraci zařízení do Azure AD.

## <a name="auto-enrollment-on-hololens-2"></a>automatický zápis na HoloLens 2

aby bylo možné zajistit hladké a bezproblémové prostředí, nastavení Azure Active Directory Join (AADJ) a automatický zápis do intune pro HoloLens 2 zařízení je možné přejít. Uživatelé tak budou moct během spuštění OOBE zadat přihlašovací údaje pro své organizace a automaticky se zaregistrovat ve službě Azure AD a zaregistrovat zařízení do MDM.

pomocí [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home)můžeme vybrat služby a přejít na několik stránek, dokud si nebudeme moct vybrat získat Premium zkušební verzi. můžete si všimnout, že je k dispozici Azure Active Directory Premium 1 a 2, pokud je automatický zápis P1 dostačující. Můžeme vybrat Intune a vybrat obor uživatele pro automatický zápis a vybrat skupinu, která byla dřív vytvořená.

Úplné podrobnosti a kroky najdete v průvodci, [Jak povolit automatický zápis pro Intune](/mem/intune/enrollment/quickstart-setup-auto-enrollment).

## <a name="application-licenses"></a>Licence k aplikacím

Licence aplikace umožňuje uživateli instalovat aplikace zakoupené firmou nebo upgradovat z bezplatné zkušební verze na plnou verzi aplikace. Licence k aplikacím lze použít pro uživatele, skupiny uživatelů nebo skupiny zařízení. Pro uživatele ve vaší organizaci, kteří používají vzdálenou pomoc, je&#39;nutné licence pro vzdálenou pomoc. Pro účely tohoto průvodce přiřadíte licence Remote Assist ke skupině uživatelů, kterou jsme vytvořili výše v [Azure Users and Groups](hololens2-cloud-connected-configure.md#azure-users-and-groups).

Požadavky na licence se můžou lišit v závislosti na tom, jestli bude uživatel provádět volání vzdálené pomoci ze zařízení, nebo se může jednat o vzdáleného spolupracovníka z Microsoft Teams. ve výchozím nastavení jsou zaškrtávací políčka vzdálená pomoc a Teams označena jako. Pro účely tohoto průvodce doporučujeme ponechat zaškrtnutá výchozí políčka.

1. Přečtěte si další informace o různých [licencích a požadavcích na produkt na roli](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role). Existuje několik různých typů licencí na vzdálenou pomoc, takže si nezapomeňte získat správné požadavky.
2. Musíte&#39;[získat licenci](/dynamics365/mixed-reality/remote-assist/buy-remote-assist).
3. [Použijte své licence](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) na skupinu.

## <a name="next-step"></a>Další krok

> [!div class="nextstepaction"]
> [Nasazení propojené s cloudem – nasazení](hololens2-cloud-connected-deploy.md)