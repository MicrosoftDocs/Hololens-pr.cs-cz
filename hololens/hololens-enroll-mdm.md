---
title: Registrace HoloLens v MDM
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
ms.openlocfilehash: 624ebd17335820b1d2858f9d39cabb7032a83bfe
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377680"
---
# <a name="enroll-hololens-in-mdm"></a>Registrace HoloLens v MDM

Pomocí řešení, jako je Microsoft HoloLens , můžete spravovat [více zařízení Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business). Budete moct spravovat nastavení, vybrat aplikace pro instalaci a nastavení konfigurací zabezpečení přizpůsobených potřebám vaší organizace. Viz [Správa zařízení s Windows Holographic s Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), poskytovatelé konfiguračních služeb [(CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)podporovaní ve Windows Holographic a zásady podporované službou [Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> Správa mobilních zařízení (MDM), včetně funkcí VPN, BitLockeru a bezobrazovkovém režimu, je dostupná jenom při upgradu na [Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## <a name="requirements"></a>Požadavky

 Aby bylo možné spravovat zařízení HoloLens, musí mít vaše organizace nastavenou možnost Mobile Správa zařízení (MDM). Váš poskytovatel MDM může být Microsoft Intune třetí strany, který používá rozhraní MICROSOFT MDM API.
 
## <a name="different-ways-to-enroll"></a>Různé způsoby registrace

V závislosti na typu [identity zvolené](hololens-identity.md) při OOBE nebo po přihlášení existují různé metody registrace.

- Pokud je Identita Azure AD, pak buď během doby hotového prostředí nebo nastavení Tlačítko Přístup do aplikace do práce  ->  **nebo Do**  ->  **školy.**
    - Automatická registrace [MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) v Azure AD nastane jenom v případě, že je v Azure AD nakonfigurované adresy URL pro registraci.
     
- Pokud je identita Azure AD a zařízení je předem zaregistrované na serveru MdM Intune s přiřazeným konkrétním konfiguračním profilem, pak během spuštění počítače dojde k azure AD-Join a automatické registraci [MDM.](hololens-enroll-mdm.md#auto-enrollment-in-mdm)
    - Říká se jim [také tok Autopilot](hololens2-autopilot.md) dostupný ve [buildech verze 19041.1103 nebo více.](hololens-release-notes.md#windows-holographic-version-2004)
    

- Pokud je Identita MSA, pak pomocí tlačítka **Settings App**  ->  **Access Work nebo School**  ->  **Connect.**
    - Říká se mu také tok Přidat pracovní účet (AWA).
- Pokud je Identita místní uživatel, pomocí odkazu Nastavení **Přístup do** aplikace do práce nebo Do školy  ->    ->  **se zaregistrujte jenom ve správě** zařízení.
    - Říká se jim také čistý tok registrace MDM.

Jakmile je zařízení zaregistrované na serveru MDM, aplikace Nastavení teď bude odrážet, že je zařízení zaregistrované ve správě zařízení.

## <a name="auto-enrollment-in-mdm"></a>Automatická registrace v MDM

Pokud má vaše organizace předplatné [Azure Premium](https://azure.microsoft.com/overview/), používá službu Azure Active Directory (Azure AD) a řešení MDM, které přijímá token Azure AD pro ověřování (v současné době se podporuje pouze v Microsoft Intune a AirWatchu), může správce IT nakonfigurovat službu Azure AD tak, aby po přihlášení uživatele pomocí svého účtu Azure AD automaticky povoluje registraci MDM. [Zjistěte, jak nakonfigurovat registraci Azure AD.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Pokud je povolená automatická registrace, není potřeba žádná další ruční registrace. Když se uživatel přihlásí pomocí účtu Azure AD, zařízení se po dokončení prvního spuštění zapíše do MDM.

Pokud je zařízení připojené k Azure AD, může to mít vliv na to, kdo ho považuje [za vlastníka.](security-adminless-os.md#device-owner)

## <a name="unenroll-hololens-from-intune"></a>Zrušení registrace HoloLens v Intune

V závislosti na metodě registrace nemusí být registrace zařízení dostupná.

Pokud bylo vaše zařízení zaregistrované pomocí účtu Azure AD nebo Autopilotu, není možné jeho registrace zrušit v Intune. Pokud se chcete připojit k HoloLens z Azure AD nebo se k jinému tenantovi Azure AD připojit znovu, musíte zařízení resetovat [nebo odkazovat](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) na něj.

Pokud bylo vaše zařízení zaregistrované z účtu MSA, který přidal pracovní účet, nebo z místního účtu, který se zaregistroval jenom ve správě zařízení, můžete registraci zařízení zrušit. Otevřete okno nabídka Start pak vyberte Nastavení **Přístup k** aplikaci Do práce nebo Do školy  ->    ->  *VášÚčet*  ->  **Odpojit.**