---
title: Registrace HoloLens MDM
description: Zjistěte, jak zaregistrovat HoloLens ve správě mobilních zařízení (MDM), abyste usnadnili správu více zařízení.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/15/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9f466abe45a1a9ad676f8dd6a94244473c084be7
ms.sourcegitcommit: 38b5e4d92da6fc5d6a6a2ef875644d6db2cce822
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2021
ms.locfileid: "130202875"
---
# <a name="enroll-hololens-in-mdm"></a>Registrace HoloLens MDM

Pomocí řešení, jako je Microsoft HoloLens , můžete spravovat několik Microsoft Intune zařízení [současně.](/intune/windows-holographic-for-business) Budete moct spravovat nastavení, vybrat aplikace pro instalaci a nastavení konfigurací zabezpečení přizpůsobených potřebám vaší organizace. Viz Správa zařízení se [systémem Windows Holographic s Microsoft Intune](/intune/windows-holographic-for-business), poskytovatelé konfiguračních služeb [(CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens)podporovaní v Windows Holographic a zásady podporované [službou Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> Správa mobilních zařízení (MDM), včetně funkcí VPN, BitLockeru a bezobrazovkovém režimu, je dostupná jenom při upgradu na [Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## <a name="requirements"></a>Požadavky

 Aby bylo možné spravovat zařízení s Správa zařízení mobilními zařízeními, musí mít vaše organizace HoloLens mobilní zařízení. Váš poskytovatel MDM může být Microsoft Intune třetí strany, který používá rozhraní MICROSOFT MDM API.

## <a name="different-ways-to-enroll"></a>Různé způsoby registrace

V závislosti na typu [identity zvolené](hololens-identity.md) při OOBE nebo po přihlášení existují různé metody registrace.

- Pokud je identita Azure AD, pak buď během hotového Nastavení **nebo** během pracovního nebo školního  ->    ->  **Připojení** aplikace.
    - Automatická registrace [MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) v Azure AD nastane jenom v případě, že je v Azure AD nakonfigurované adresy URL pro registraci.

- Pokud je identita Azure AD a zařízení je předem zaregistrované na serveru MdM Intune s přiřazeným konkrétním konfiguračním profilem, pak během spuštění počítače dojde k azure AD-Join a automatické registraci [MDM.](hololens-enroll-mdm.md#auto-enrollment-in-mdm)
    - Také se nazývá [tok Autopilot](hololens2-autopilot.md) Dostupný v [buildech verze 19041.1103 nebo více.](hololens-release-notes.md#windows-holographic-version-2004)


- Pokud je Identita MSA, pak **Nastavení tlačítko Pro přístup** do práce nebo  ->    ->  **Připojení** aplikace.
    - Říká se mu také tok Přidat pracovní účet (AWA).
- Pokud je Identita místní uživatel, pak pomocí **Nastavení Přístup** do aplikace nebo Školní registrace jenom v odkazu  ->    ->  **na správu** zařízení.
    - Říká se jim také čistý tok registrace MDM.

Jakmile je zařízení zaregistrované na serveru MDM, aplikace Nastavení bude odrážet, že je zařízení zaregistrované ve správě zařízení.

## <a name="auto-enrollment-in-mdm"></a>Automatická registrace v MDM

Pokud má vaše organizace předplatné [Azure Premium](https://azure.microsoft.com/overview/), používá službu Azure Active Directory (Azure AD) a řešení MDM, které přijímá token Azure AD pro ověřování (v současné době se podporuje pouze v Microsoft Intune a AirWatchu), může správce IT nakonfigurovat Službu Azure AD tak, aby automaticky povoluje registraci MDM poté, co se uživatel přihlásí pomocí služby Azure AD. Účet. [Přečtěte si, jak nakonfigurovat registraci Azure AD a](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) integraci Azure Active Directory s [MDM,](/windows/client-management/mdm/azure-active-directory-integration-with-mdm) kde najdete podrobné základní informace.

Pokud je povolená automatická registrace, není potřeba žádná další ruční registrace. Když se uživatel přihlásí pomocí účtu Azure AD, zařízení se po dokončení prvního spuštění zapíše do MDM.

Pokud je zařízení připojené k Azure AD, může to mít vliv na to, kdo ho považuje [za vlastníka.](security-adminless-os.md#device-owner)

## <a name="unenroll-hololens-from-intune"></a>Zrušení registrace HoloLens Intune

V závislosti na metodě registrace nemusí být zrušení registrace zařízení k dispozici.

Pokud bylo vaše zařízení zaregistrované pomocí účtu Azure AD nebo Autopilotu, není možné zrušit jeho registrace v Intune. Pokud se chcete ke službě Azure AD HoloLens nebo se k ní znovu připojit k jinému tenantovi Azure AD, musíte zařízení resetovat [nebo odkazovat](hololens-recovery.md#restart-the-device) na něj.

Pokud bylo vaše zařízení zaregistrované z účtu MSA, který přidal pracovní účet, nebo z místního účtu, který se zaregistroval jenom ve správě zařízení, můžete registraci zařízení zrušit. Otevřete okno nabídka Start pak vyberte Nastavení **App**  ->  **Access Work nebo School**  ->    ->  **YourAccount Disconnect.**

## <a name="enrollment-troubleshooting"></a>Řešení potíží s registrací

### <a name="ensure-device-is-successfully-connected-to-internet-before-attempting-enrollment-post-oobe"></a>Před pokusem o registraci po spuštění spuštění zařízení se ujistěte, že je zařízení úspěšně připojené k internetu.

Jakmile se uživatel přihlásil, zajistěte připojení k internetu tak, že na zařízení prochádíte jakýkoli internetový web.

### <a name="ensure-that-azure-active-directory-aad-join-is-not-disabled-in-your-aad-tenant"></a>Ujistěte se, Azure Active Directory (AAD) není ve vašem tenantovi AAD zakázáno.

Informace o [dostupných možnostech najdete v](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) tématu Konfigurace nastavení zařízení v Azure Portal.

### <a name="ensure-valid-license-is-assigned-to-the-user"></a>Ujistěte se, že je uživateli přiřazená platná licence.

Přečtěte [si](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors) článek Řešení Windows problémů s registrací zařízení Microsoft Intune konkrétně v následujících částech, [tj.](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#check-device-type-restrictions) Kontrola omezení typů zařízení a Přiřazení platné licence [uživateli.](/troubleshoot/mem/intune/troubleshoot-windows-enrollment-errors#assign-a-valid-license-to-the-user)

### <a name="ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>Ujistěte se, že registrace MDM není blokovaná pro Windows zařízení.

Aby registrace byla úspěšná, musíte zajistit, aby se vaše HoloLens mohli zaregistrovat. Vzhledem HoloLens, že se Windows zařízení, nebude nutné mít žádná omezení registrace, která by mohla vaše nasazení blokovat. [Zkontrolujte tento seznam omezení a](/mem/intune/enrollment/enrollment-restrictions-set) ujistěte se, že budete moct zaregistrovat zařízení.
