---
title: Průvodce nasazením – nasazení HoloLens 2 připojené ke cloudu ve velkém měřítku pomocí nástroje Remote Assist – příprava
description: Zjistěte, jak se připravit na registraci zařízení HoloLens přes síť připojenou ke cloudu pomocí azure active directory a správy identit.
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
ms.openlocfilehash: 067917396631f9a89a50b13ef1b7dcca8b631f52
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377597"
---
# <a name="prepare---cloud-connected-guide"></a>Příprava – Průvodce připojeným ke cloudu

Na konci tohoto článku nastavíte Azure AD, MDM a lépe pochopíte použití účtů Azure AD a požadavků na síť. Tato část průvodce vám a vaší organizaci pomůže připravit se na nasazení HoloLens 2 do cloudu a použití Dynamics 365 Remote Assistu. Projdeme si důležitost jednotlivých částí infrastruktury a také poskytne odkazy na příručky, které vám pomůžou tyto části podle potřeby nastavit.

## <a name="infrastructure-essentials"></a>Základy infrastruktury

Pro osobní i firemní nasazení je systém MDM základní infrastrukturou, která je nutná k nasazení a správě Windows 10 Holographic zařízení. Jako zprostředkovatel identity se doporučuje předplatné Azure AD Premium, které je potřeba k podpoře určitých funkcí.

### <a name="azure-active-directory"></a>Azure Active Directory

Azure AD je cloudová adresářová služba, která poskytuje správu identit a přístupu. Organizace, které používají systém Microsoft Office 365 nebo Intune, už používají Azure AD se třemi edicemi: Free, Premium P1 a Premium P2 (viz edice [Azure Active Directory).](https://azure.microsoft.com/documentation/articles/active-directory-editions) Všechny edice podporují registraci zařízení v Azure AD, ale k povolení automatické registrace MDM, kterou budeme později používat v této příručce, se vyžaduje Premium P1.

> [!IMPORTANT]
> Je nezbytné mít základní Azure Active Directory protože zařízení HoloLens nepodporují připojení k místní službě AD. Pokud ještě&#39;nemáte nastavený Azure Active Directory postupujte podle pokynů na tomto odkazu, abyste začali a vytvořili nového [tenanta](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)v Azure Active Directory .

## <a name="identity-management"></a>Správa identit

Zaměstnanci mohou k inicializaci zařízení použít pouze jeden účet,&#39;je nezbytné, aby vaše organizace nejdřív vyhotivěl, který účet je povolený. Zvolený účet určí, kdo zařízení řídí, a ovlivní možnosti správy.

V této příručce jsme zvolili, že pro použitou [identitu](https://docs.microsoft.com/hololens/hololens-identity) použijeme účty Azure AD nebo Azure Active Directory účty. Pro účty Azure AD, které bychom chtěli použít, existuje několik výhod, například:

- Zaměstnanci používají svůj účet Azure AD k registraci zařízení v Azure AD&#39;jeho automatické registraci v řešení MDM organizace (Azure AD + MDM – vyžaduje Azure AD Premium).
- Účty Azure AD podporují [jednotné přihlašování.](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) Když se uživatel přihlásí ke vzdálenému pomoci, rozpozná se jeho identita od přihlášené uživatele Azure AD a uživatel se přihlásí do aplikace, aby se zjednodušil.
- Účty Azure AD mají další [možnosti ověřování](https://docs.microsoft.com/hololens/hololens-identity) prostřednictvím [Windows Hello pro firmy](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification). Kromě přihlášení Iris se uživatelé mohou přihlašovat z jiného zařízení nebo používat klíče zabezpečení FIDO.

### <a name="mobile-device-management"></a>Správa mobilních zařízení

Microsoft [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune), součást Enterprise Mobility + Security, je cloudový systém MDM, který spravuje zařízení připojená k vašemu tenantovi. Stejně jako Office 365 používá Intune ke správě identit Azure AD, takže zaměstnanci používají stejné přihlašovací údaje k registraci zařízení v Intune, která používají pro přihlášení k Office 365. Intune také podporuje zařízení s jinými operačními systémy, jako je iOS a Android, a poskytuje tak kompletní řešení MDM. Pro účely této příručky se zaměříme&#39;intune pro povolení škálování cloudového nasazení pomocí HoloLens 2.

> [!IMPORTANT]
> Je nezbytné mít Mobile Správa zařízení. Pokud ho ještě&#39;, postupujte podle pokynů v této příručce a [v příručce Začínáme s Intune.](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)

> [!NOTE]
> Několik systémů MDM podporuje Windows 10 většina podporuje scénáře nasazení osobních a firemních zařízení. Mezi poskytovatele MDM, kteří Windows 10 Holographic v současné době patří: AirWatch, MobileIron a další. Většina špičkových dodavatelů MDM už integraci s Azure AD podporuje. Dodavatele MDM, kteří podporují Azure AD, najdete v [Azure Marketplace](https://azure.microsoft.com/marketplace/).

## <a name="network"></a>Síť

V tomto nastavení očekáváme, že zařízení HoloLens 2 se připojují k internetu z jakékoli dostupné Wi-Fi sítě. Vzhledem k tomu, že uživatel může potřebovat změnit síťové připojení podle umístění, měl by se dozvědět, jak připojit zařízení [HoloLens k Wi-Fi.](https://docs.microsoft.com/hololens/hololens-network)

Pro Dynamics 365 Remote Assist existuje řada síťových podmínek, včetně šířky pásma, latence, zpoždění a ztráty paketů, které mohou mít vliv na videohovory. I když v prostředích s omezenou šířkou pásma můžou být možná zvuková volání a volání videa, může dojít ke snížení výkonu funkcí. Při použití Dynamics 365 Remote Assistu na HoloLens tady jsou požadavky na síť, které je dobré mít na paměti:

**Minimum:** Pro volání videa ve vysoké kvalitě peer-to-peer s rozlišením HD 1080p při 30 fps se vyžaduje 1,5 Mb/s nahoru/dolů.

**Optimální:** V případě videohooku v kvalitě HD peer-to-peer s rozlišením HD 1080p by se mělo očekávat 4–5 Mb/s nahoru nebo dolů.

Další informace:

- [Požadavky sítě](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [Doporučení pro optimalizaci sítě](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a>Volitelné: Připojení HoloLens k síti VPN

Zařízení připojená k této příručce se budou připojovat k síti přes externí cloudovou síť. Je možné, že pro přístup k prostředkům společnosti&#39;budete muset připojit zařízení přes síť VPN. Existuje několik různých způsobů připojení zařízení k síti VPN, kde se koncový uživatel může připojit přes uživatelské rozhraní zařízení, nebo zařízení lze spravovat a přijímat profil VPN z PPKG nebo MDM. Informace o nastavení sítě VPN&#39;, které tento článek nepokryje, takže pokud chcete získat další informace o různých protokolech VPN nebo způsobech správy sítě VPN&#39;, přečtěte si tyto příručky o [HoloLens](https://docs.microsoft.com/hololens/hololens-network#vpn) a VPN.

## <a name="next-step"></a>Další krok

> [!div class="nextstepaction"]
> [Nasazení připojené ke cloudu – Konfigurace](hololens2-cloud-connected-configure.md)
