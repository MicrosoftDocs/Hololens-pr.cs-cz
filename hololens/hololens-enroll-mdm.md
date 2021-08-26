---
title: registrace HoloLens v MDM
description: naučte se, jak zaregistrovat HoloLens ve správě mobilních zařízení (MDM) pro snazší správu více zařízení.
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
ms.openlocfilehash: 5ded375d88740b9367eec87e4e902c423f131689
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/25/2021
ms.locfileid: "122858979"
---
# <a name="enroll-hololens-in-mdm"></a>registrace HoloLens v MDM

pomocí řešení jako [Microsoft Intune](/intune/windows-holographic-for-business)můžete spravovat více Microsoft HoloLens zařízení současně. Budete moct spravovat nastavení, vybrat aplikace, které chcete nainstalovat, a nastavit konfigurace zabezpečení přizpůsobené potřebám vaší organizace. přečtěte si téma [správa zařízení se systémem Windows holografická s Microsoft Intune](/intune/windows-holographic-for-business), [poskytovateli konfiguračních služeb (csp), které jsou podporovány v Windowsových holografickích](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), a [zásady podporované Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).

> [!NOTE]
> Správa mobilních zařízení (MDM), včetně funkcí sítě VPN, BitLocker a celoobrazovkového režimu, je k dispozici pouze při [upgradu na Windows Holographic for Business](hololens1-upgrade-enterprise.md).

## <a name="requirements"></a>Požadavky

 aby bylo možné spravovat HoloLens zařízení, bude nutné, aby vaše organizace měla nastavenou správu mobilních zařízení (MDM). váš poskytovatel MDM může být Microsoft Intune nebo poskytovatel třetí strany, který používá rozhraní Microsoft MDM api.

## <a name="different-ways-to-enroll"></a>Různé způsoby registrace

V závislosti na typu [identity](hololens-identity.md) , který jste zvolili při počátečním spuštění nebo po přihlášení, existují různé metody registrace.

- pokud se jedná o službu Azure AD, pak buď během počátečního nastavení, nebo v aplikaci **Nastavení**  ->  **accessového nebo školním**  ->  tlačítku **Připojení** .
    - V případě Azure AD dojde k [automatické registraci MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) jenom v případě, že je služba Azure AD nakonfigurovaná s adresami URL pro zápis.

- Pokud je identita Azure AD a u zařízení se systémem Intune MDM, ke kterému je přiřazený určitý nakonfigurovaný profil, používá předregistrovaná identita, pak při spuštění služby Azure AD-Join a [automatické registraci MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) dojde k zápisu v rámci služby OOBE.
    - Také označovaný jako [autopilot Flow](hololens2-autopilot.md) dostupný v [sestaveních 19041.1103 +](hololens-release-notes.md#windows-holographic-version-2004).


- pokud je identita MSAá, použijte   ->  tlačítko pro **přístup k práci nebo škole**  ->  **Připojení** aplikace Nastavení.
    - Také se nazývá AWA (Přidat pracovní účet).
- pokud je identita místní uživatel, pak pomocí aplikace **Nastavení**  ->  **přístup k aplikaci v pracovním nebo školním**  ->  **zápisu jenom v odkazu správa zařízení** .
    - Označuje se taky jako čistý tok zápisu MDM.

jakmile je zařízení zaregistrované ve vašem serveru MDM, Nastavení aplikace teď odrážejí, že je zařízení zaregistrované ve správě zařízení.

## <a name="auto-enrollment-in-mdm"></a>Automatické registrace v MDM

pokud má vaše organizace [předplatné azure Premium](https://azure.microsoft.com/overview/), používá Azure Active Directory (Azure ad) a řešení MDM, které přijímá token Azure AD pro ověřování (v současné době se podporuje jenom v Microsoft Intune a sledování), může správce IT nakonfigurovat službu Azure ad tak, aby po přihlášení uživatele k účtu azure ad automaticky povolovala registraci MDM. [Přečtěte si, jak nakonfigurovat registraci Azure AD.](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

Pokud je povolená Automatická registrace, nevyžaduje se žádná další ruční registrace. Když se uživatel přihlásí pomocí účtu Azure AD, zařízení se zaregistruje do MDM po dokončení prvního spuštění prostředí.

Když je zařízení připojené k Azure AD, může to mít vliv na to, kdo posuzuje [vlastníka zařízení](security-adminless-os.md#device-owner).

## <a name="unenroll-hololens-from-intune"></a>zrušit registraci HoloLens v intune

V závislosti na metodě registrace možná nebude k dispozici zrušení registrace zařízení.

Pokud je vaše zařízení zaregistrované s účtem služby Azure AD nebo s automatickým pilotním, nedá se zrušit jeho registrace v Intune. pokud chcete zrušit připojení HoloLens z Azure ad nebo ho znovu připojit k jinému klientovi Azure ad, musíte zařízení [resetovat nebo znovu zablikat](hololens-recovery.md#reset-the-device) .

Pokud bylo zařízení zaregistrováno z účtu MSA, který přidal pracovní účet, nebo z místního účtu, který byl zaregistrován pouze ve správě zařízení, můžete zrušit registraci zařízení. otevřete nabídka Start a pak klikněte na tlačítko přístup k **aplikaci Nastavení**  ->  **Work nebo School**  ->  *YourAccount*  ->  **disconnect** .

## <a name="ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>ujistěte se, že registrace MDM není pro zařízení Windows blokovaná.

aby mohl automatický pilotní postup úspěšně proběhnout, musíte zajistit, aby se zařízení HoloLens mohla zaregistrovat. vzhledem k tomu, že se HoloLens považuje za Windows zařízení, bude nutné, aby nedocházelo k omezením registrace, která by mohla blokovat nasazení. [Projděte si tento seznam omezení](/mem/intune/enrollment/enrollment-restrictions-set) a ujistěte se, že budete moci zaregistrovat svá zařízení.