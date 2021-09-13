---
title: Registrace HoloLens MDM
description: Zjistěte, jak zaregistrovat HoloLens ve správě mobilních zařízení (MDM), abyste usnadnili správu více zařízení.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/06/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: a368c622c137374ea9cc544490d3492fa9d3f8c1
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032164"
---
# <a name="enroll-hololens-in-mdm"></a>Registrace HoloLens MDM

Pomocí řešení, jako je Microsoft HoloLens , můžete spravovat několik Microsoft Intune zařízení [současně.](/intune/windows-holographic-for-business) Budete moct spravovat nastavení, vybrat aplikace pro instalaci a nastavení konfigurací zabezpečení přizpůsobených potřebám vaší organizace. Viz Správa zařízení se systémem [Windows Holographic s Microsoft Intune](/intune/windows-holographic-for-business), poskytovatelé konfiguračních služeb [(CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)podporovaní v Windows Holographic a zásady podporované [službou Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> Správa mobilních zařízení (MDM), včetně funkcí VPN, BitLockeru a bezobrazovkovém režimu, je dostupná jenom při upgradu na [Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## <a name="requirements"></a>Požadavky

 Aby bylo možné spravovat zařízení s Správa zařízení mobilními zařízeními, musí mít vaše organizace HoloLens mobilní zařízení. Váš poskytovatel MDM může být Microsoft Intune třetí strany, který používá rozhraní MICROSOFT MDM API.

## <a name="different-ways-to-enroll"></a>Různé způsoby registrace

V závislosti na typu [identity zvolené](hololens-identity.md) při OOBE nebo po přihlášení existují různé metody registrace.

- Pokud je identita Azure AD, pak buď během hotového Nastavení **aplikace,** pracovního nebo školního přístupu Připojení  ->    ->   tlačítko.
    - Automatická registrace [MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) v Azure AD nastane jenom v případě, že je v Azure AD nakonfigurované adresy URL pro registraci.

- Pokud je identita Azure AD a zařízení je předem zaregistrované na serveru MdM Intune s přiřazeným konkrétním konfiguračním profilem, pak během spuštění počítače dojde k azure AD-Join a automatické registraci [MDM.](hololens-enroll-mdm.md#auto-enrollment-in-mdm)
    - Také se nazývá [tok Autopilot](hololens2-autopilot.md) Dostupný v [buildech verze 19041.1103 nebo více.](hololens-release-notes.md#windows-holographic-version-2004)


- Pokud je Identita MSA, Nastavení **tlačítko Pro** přístup do Připojení  ->    ->   aplikace.
    - Říká se mu také tok Přidat pracovní účet (AWA).
- Pokud je Identita místní uživatel, pak pomocí **Nastavení App** Access Work nebo  ->  **School**  ->  **Enroll jenom v odkazu na správu** zařízení.
    - Říká se jim také čistý tok registrace MDM.

Jakmile je zařízení zaregistrované na serveru MDM, aplikace Nastavení bude odrážet, že je zařízení zaregistrované ve správě zařízení.

## <a name="auto-enrollment-in-mdm"></a>Automatická registrace v MDM

Pokud má vaše organizace předplatné [Azure Premium](https://azure.microsoft.com/overview/), používá službu Azure Active Directory (Azure AD) a řešení MDM, které přijímá token Azure AD pro ověřování (v současné době se podporuje pouze v Microsoft Intune a AirWatchu), může správce IT nakonfigurovat službu Azure AD tak, aby po přihlášení uživatele pomocí svého účtu Azure AD automaticky povoluje registraci MDM. [Zjistěte, jak nakonfigurovat registraci Azure AD.](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Pokud je povolená automatická registrace, není potřeba žádná další ruční registrace. Když se uživatel přihlásí pomocí účtu Azure AD, zařízení se po dokončení prvního spuštění zapíše do MDM.

Pokud je zařízení připojené k Azure AD, může to mít vliv na to, kdo ho považuje [za vlastníka.](security-adminless-os.md#device-owner)

## <a name="unenroll-hololens-from-intune"></a>Zrušení registrace HoloLens Intune

V závislosti na metodě registrace nemusí být zrušení registrace zařízení k dispozici.

Pokud bylo vaše zařízení zaregistrované pomocí účtu Azure AD nebo Autopilotu, není možné zrušit jeho registrace v Intune. Pokud se chcete ke službě Azure AD HoloLens nebo se k ní znovu připojit k jinému tenantovi Azure AD, musíte zařízení resetovat nebo na něj [odkazovat.](hololens-recovery.md#reset-the-device)

Pokud bylo vaše zařízení zaregistrované z účtu MSA, který přidal pracovní účet, nebo z místního účtu, který se zaregistroval jenom ve správě zařízení, můžete registraci zařízení zrušit. Otevřete okno nabídka Start a pak vyberte Nastavení **App**  ->  **Access Work nebo School**  ->    ->  **YourAccount Disconnect.**

## <a name="ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>Ujistěte se, že registrace MDM není blokovaná pro Windows zařízení.

Aby registrace byla úspěšná, musíte zajistit, aby se vaše HoloLens mohli zaregistrovat. Vzhledem HoloLens, že se Windows zařízení, nebude nutné mít žádná omezení registrace, která by mohla vaše nasazení zablokovat. [Zkontrolujte tento seznam omezení a](/mem/intune/enrollment/enrollment-restrictions-set) ujistěte se, že budete moct zaregistrovat zařízení.