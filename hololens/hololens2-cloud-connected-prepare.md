---
title: průvodce nasazením – Cloud připojený HoloLens 2 ve velkém měřítku s využitím funkce Remote Assist – příprava
description: naučte se, jak připravit registraci zařízení HoloLens přes cloudovou propojenou síť pomocí azure active directory a správy identit.
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
ms.openlocfilehash: 21fffdc24f8682bc44779e1cebe8cd6eacb59619
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639654"
---
# <a name="prepare---cloud-connected-guide"></a>Příprava – Průvodce připojením k cloudu

Na konci tohoto článku jste nastavili Azure AD, MDM a porozuměli vám s používáním účtů Azure AD a síťových požadavků. tato část průvodce vám pomůže a vaše organizace se připraví na nasazení HoloLens 2 do cloudu a používání služby Dynamics 365 Remote Assist. To bude mít význam pro jednotlivé části vaší infrastruktury a také poskytuje odkazy na příručky, které vám pomůžou tyto části nastavit podle potřeby.

## <a name="infrastructure-essentials"></a>Základy infrastruktury

pro scénáře osobního i podnikového nasazení je systém MDM základní infrastrukturou, která je nutná k nasazení a správě Windows 10 Holographicch zařízení. Předplatné Azure AD Premium se doporučuje jako zprostředkovatel identity a vyžaduje se pro podporu určitých možností.

### <a name="azure-active-directory"></a>Azure Active Directory

Azure AD je cloudová adresářová služba, která poskytuje správu identit a přístupů. organizace, které používají Microsoft Office 365 nebo intune, už používají Azure AD, které mají tři edice: Free, Premium P1 a Premium P2 (viz [edice Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-editions).) všechny edice podporují registraci zařízení Azure AD, ale Premium P1 se vyžaduje k povolení automatického zápisu MDM, který v této příručce použijeme později.

> [!IMPORTANT]
> je nutné mít Azure Active Directory jako HoloLens zařízení nepodporují místní službu AD join. pokud&#39;t už máte nastavenou Azure Active Directory, [v Azure Active Directory vytvořit nového tenanta](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).

## <a name="identity-management"></a>Správa identit

Zaměstnanci můžou použít jenom jeden účet k inicializaci zařízení, aby&#39;s imperativně, že vaše organizace řídí, který účet je povolený jako první. Vybraný účet určí, kdo bude řídit zařízení a ovlivňuje možnosti správy.

v této příručce jsme zvolili, že pro použitou [identitu](/hololens/hololens-identity) použijeme účty Azure AD nebo účty Azure Active Directory. Pro účty Azure AD, které bychom chtěli použít, je k dispozici několik výhod:

- Zaměstnanci používají svůj účet Azure AD k registraci zařízení v Azure AD a automaticky ho zaregistrovali pomocí řešení&#39;s MDM pro organizaci (Azure AD + MDM – vyžaduje Azure AD Premium).
- Účty Azure AD podporují [jednotné přihlašování](/azure/active-directory/manage-apps/what-is-single-sign-on). Když se uživatel přihlásí ke službě Remote Assist, rozpozná se jejich identita z přihlášeného uživatele Azure AD a uživatel se přihlásí do aplikace, aby se zjednodušilo.
- účty Azure AD mají další [možnosti ověřování](/hololens/hololens-identity) prostřednictvím [Windows Hello pro firmy](/windows/security/identity-protection/hello-for-business/hello-identity-verification). Kromě přihlášení Iris se uživatelé můžou přihlásit z jiného zařízení nebo použít bezpečnostní klíče FIDO.

### <a name="mobile-device-management"></a>Správa mobilních zařízení

Microsoft [intune](/mem/intune/fundamentals/what-is-intune), součást Enterprise Mobility + Security, je cloudový systém MDM, který spravuje zařízení připojená k vašemu tenantovi. podobně jako Office 365 intune používá službu Azure AD pro správu identit, takže zaměstnanci používají stejné přihlašovací údaje k registraci zařízení v intune, které používají pro přihlášení k Office 365. Intune také podporuje zařízení s jinými operačními systémy, jako jsou iOS a Android, a poskytuje tak kompletní řešení MDM. pro účely tohoto průvodce&#39;vše se zaměřením na použití intune, aby bylo možné povolit cloudové nasazení ve velkém měřítku s HoloLens 2.

> [!IMPORTANT]
> Je nutné mít správu mobilních zařízení. Pokud už&#39;t, postupujte podle pokynů v této příručce a začněte [s Intune](/mem/intune/fundamentals/free-trial-sign-up).

> [!NOTE]
> víc systémů MDM podporuje Windows 10 a podporuje i většinu scénářů nasazení osobních i podnikových zařízení. mezi poskytovatele MDM podporující Windows 10 Holographic aktuálně patří: MobileIron a další. Většina špičkových dodavatelů MDM už podporuje integraci s Azure AD. Dodavatelé MDM, kteří podporují Azure AD, najdete v [Azure Marketplace](https://azure.microsoft.com/marketplace/).

## <a name="network"></a>Síť

v tomto nastavení předpokládáme, že HoloLens 2 zařízení, která se připojují k internetu, z jakékoli dostupné otevřené Wi-Fi sítě. vzhledem k tomu, že uživatel může potřebovat změnit připojení k síti na základě umístění, musí se naučit, jak [připojit zařízení HoloLens k Wi-Fi.](/hololens/hololens-network)

Pro funkci Vzdálená pomoc pro Dynamics 365 existuje celá řada stavů sítě, včetně šířky pásma, latence, kolísání a ztráty paketů. to může mít vliv na možnosti volání videa. I když může být možné zvukové a obrazové hovory v prostředích s omezenou šířkou pásma, může docházet k degradaci funkcí. při používání vzdálené pomoci Dynamics 365 na HoloLens tady jsou požadavky na síť, které je potřeba vzít v úvahu:

Pro video typu peer-to-peer s rozlišením HD 1080p při 30 FPS se vyžaduje **minimum** : 1,5 MB/s.

**Optimální:** Pro video typu peer-to-peer HD s rozlišením HD 1080p by se mělo očekávat 4-5 MB/s.

Další informace:

- [Požadavky sítě](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [Doporučení pro optimalizaci sítě](/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a>volitelné: Připojení HoloLens do sítě VPN.

Zařízení, která se připojují k této příručce, se budou připojovat k síti přes a externí cloudovou síť. Je možné, že budete mít přístup k prostředkům společnosti, které&#39;potřebuje k připojení zařízení přes VPN. Existuje několik různých způsobů, jak připojit zařízení k síti VPN, kde se koncový uživatel může připojit prostřednictvím uživatelského rozhraní zařízení, nebo můžete zařízení spravovat a přijímat profil sítě VPN z PPKG nebo MDM. postup nastavení vyžádaného připojení k síti VPN&#39;t v tomto článku, takže pokud&#39;d chcete získat další informace o různých protokolech sítě vpn nebo způsobech správy sítě vpn, navštivte [tyto příručky, kde najdete informace o HoloLens a VPN.](/hololens/hololens-network#vpn)

## <a name="next-step"></a>Další krok

> [!div class="nextstepaction"]
> [Nasazení propojené s cloudem – konfigurace](hololens2-cloud-connected-configure.md)
