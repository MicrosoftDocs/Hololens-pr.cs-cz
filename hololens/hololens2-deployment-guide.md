---
title: nasazení cloudu připojeného HoloLens 2 k externím klientům
description: průvodce nasazením pro HoloLens 2 pro externí klienty (s příkladem vzdálené pomoci)
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/6/2021
ms.custom: ''
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: d5cd9c380e0d276f0a8aa9efac14cf44885446e5
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190323"
---
# <a name="deploy-cloud-connected-hololens-2-to-external-clients"></a>nasazení cloudu připojeného HoloLens 2 k externím klientům

Tato příručka je doplňkem [Průvodce nasazením připojeného ke cloudu](hololens2-cloud-connected-overview.md). používá se v situacích, kdy vaše organizace chce dodávat zařízení HoloLens 2 k zařízení externího klienta pro krátkodobé nebo dlouhodobé použití. externí klient se k zařízení HoloLens 2 přihlásí pomocí přihlašovacích údajů, které poskytla vaše organizace, a pomocí [vzdálené pomoci](/dynamics365/mixed-reality/remote-assist/ra-overview) se obraťte na odborníky. tato příručka obsahuje [obecná doporučení pro nasazení HoloLens 2](#general-deployment-recommendations) , která platí pro většinu vnějších scénářů nasazení HoloLens 2 a [běžné obavy](#common-external-client-deployment-concerns) , že zákazníci mají při nasazování vzdálené pomoci pro externí použití. 

## <a name="prerequisites"></a>Požadavky

následující infrastruktura by měla být zavedena v rámci [průvodce nasazením připojeného ke cloudu](hololens2-cloud-connected-overview.md) , aby se nasadila HoloLens 2 externě.

- Připojení ke službě Azure AD s automatickým zápisem MDM – spravovaná přes MDM (Intune)
- Uživatelé se přihlásí pomocí vlastního podnikového účtu (Azure AD).
    - Podporuje se jeden nebo víc uživatelů na zařízení.

### <a name="remote-assist-licensing-and-requirements"></a>Licencování a požadavky vzdálené pomoci

- Účet Azure AD (potřebný pro zakoupení předplatného a přiřazování licencí)
- [Předplatné vzdálené pomoci](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (nebo [zkušební verze vzdáleného asistence](/dynamics365/mixed-reality/remote-assist/try-remote-assist))

Přečtěte si další [informace o funkci Vzdálená pomoc](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist).

### <a name="dynamics-365-remote-assist-user"></a>Uživatel funkce Remote Assist pro uživatele Dynamics 365

- Licence pro vzdálenou pomoc
- Připojení k síti

### <a name="microsoft-teams-user"></a>Microsoft Teams uživatel

- Microsoft Teams nebo [Teams Freemium](https://products.office.com/microsoft-teams/free)
- Připojení k síti

## <a name="general-deployment-recommendations"></a>Obecná doporučení k nasazení

pro nasazení externích HoloLens 2 doporučujeme použít následující postup:

1. použijte [nejnovější verzi HoloLens operačního systému](https://aka.ms/hololens2download) jako sestavení směrného plánu.
1. Přiřaďte licence založené na uživateli nebo zařízení pomocí následujících kroků:
    1. [vytvořte v AAD skupinu a přidejte do ní členy](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) HoloLens/RA uživatelé.
    1. Přiřaďte k této skupině licence založené na [zařízení nebo uživatele](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) .
    1. Volitelné Cílové skupiny pro zásady [správy mobilních zařízení (MDM)](hololens-enroll-mdm.md) .

1. Připojte zařízení AAD k vašemu tenantovi, [automatické registraci](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)a konfiguraci prostřednictvím automatického [pilotního nasazení](/hololens/hololens2-autopilot). Další informace najdete v tématu [vlastník zařízení](/hololens/security-adminless-os#device-owner).
    1. Prvním uživatelem na zařízení bude vlastník zařízení.
    1. Pokud je zařízení připojené k AAD, uživatel, který provedl připojení, provede vlastníka zařízení.
    
1. [Tenant zamkne](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) zařízení, aby ho bylo možné propojit jenom s vaším klientem.
    1. Viz také [CSP zámku tenanta](/windows/client-management/mdm/tenantlockdown-csp).

1. [Nakonfigurujte celoobrazovkový režim pomocí globálního přiřazeného přístupu](/hololens/hololens-global-assigned-access-kiosk).

1. Zakažte následující (volitelné) možnosti:
    1. Možnost umístit zařízení do vývojářského [režimu.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)
    1. možnost připojit HoloLens k počítači ke kopírování data a [zakázat USB](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection).
       > [!NOTE]
        > Pokud nechcete zakázat USB, ale chcete mít možnost použít zřizovací balíček na zařízení pomocí USB, postupujte podle [pokynů, jak povolit instalaci balíčku](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage).

1. k povolení nebo blokování aplikací na zařízení HoloLens 2 použijte [Windows Defender řízení aplikací (WDAC)](/hololens/windows-defender-application-control-wdac) .
1. Aktualizujte vzdálenou pomoc na nejnovější verzi jako součást instalace. Vezměte v úvahu tyto dvě možnosti:
    1. přejít na Windows **Microsoft Store--> vzdálená pomoc – > a aktualizovat aplikaci**.
    1. [ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) – povoluje automatické aktualizace aplikací – je ve výchozím nastavení povolená. Nechejte zařízení napájené ze sítě a získávat aktualizace.
1. [Zakažte všechny stránky nastavení](/hololens/settings-uri-list) s výjimkou nastavení sítě, aby se uživatelé mohli připojit k sítím hostů v klientských lokalitách.
1. [správa aktualizací HoloLens](/hololens/hololens-updates)
    1. Možnost [řízení aktualizací operačního systému](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) nebo umožnění bezchodového toku.
1. Nastavte [běžná omezení zařízení](/hololens/hololens-common-device-restrictions).

teď jsou vaši externí klienti připraveni použít jejich HoloLens 2.

## <a name="common-external-client-deployment-concerns"></a>Obecné otázky k nasazení externích klientů

- [Zajistěte, aby klienti mezi sebou nekomunikovali.](#ensure-that-external-clients-cant-communicate-with-one-another)
- [Zajištění, že klienti nemají přístup k prostředkům společnosti](#ensure-that-clients-wont-have-access-to-company-resources)
- [Skrytí nebo omezení aplikací](#hidden-or-restricted-apps)
- [Správa hesel pro klienty](#password-management-for-your-clients) 
- [Zajistěte, aby klienti nemohli přistupovat k historii konverzací.](#ensure-that-clients-wont-have-access-to-chat-history)

### <a name="ensure-that-external-clients-cant-communicate-with-one-another"></a>Ujistěte se, že externí klienti nemůžou komunikovat navzájem

vzdálená pomoc HoloLens pro HoloLens volání nejsou podporovaná. Klienti mohou hledat, ale nemohou vzájemně komunikovat. [bariéry s informacemi v Microsoft 365](/microsoft-365/compliance/information-barriers) mohou dále omezit, se kterými může klient hledat a volat. další možností je použít [Microsoft Teams prohledávání adresářů v oboru](/MicrosoftTeams/teams-scoped-directory-search).

 > [!NOTE]
> vzhledem k tomu, že je povoleno jednotné přihlašování, je důležité zakázat prohlížeč pomocí [ovládacího prvku Windows Defender aplikace (WDAC)](/hololens/windows-defender-application-control-wdac). pokud externí klient otevře prohlížeč a použije webovou verzi Teams, bude mít klient přístup k vaší historii chatu.

### <a name="ensure-that-clients-wont-have-access-to-company-resources"></a>Zajistěte, aby klienti nemuseli mít přístup k prostředkům společnosti.

Je potřeba vzít v úvahu dvě možnosti.

První možností je Vícenásobný přístup:

1. Přiřaďte jenom licence, které uživatel potřebuje. pokud nepřiřadíte OneDrive, Outlook, SharePoint, Yammer atd., uživatel nebude mít k těmto prostředkům přístup. Jedinými licencemi, které budou uživatelé potřebovat, jsou služby Remote Assist, Intune a AAD, které se mají začít.
1. Blokovat aplikace (třeba e-mail), ke kterým nechcete, aby klienti měli přístup (viz [aplikace jsou skryté nebo omezené](#apps are hidden or restricted)).
1. Nesdílejte uživatelské jméno ani heslo pomocí klientů. k přihlášení do HoloLens 2 se vyžaduje e-mail a číselný PIN kód.

Druhou možností je vytvořit samostatného tenanta, který je hostitelem klientů (viz obrázek 1,1).

**Obrázek 1,1**

![Obrázek klienta služby](./images/hololens-service-tenant-image.png)

### <a name="hidden-or-restricted-apps"></a>Skryté nebo omezené aplikace

WDAC ( [celoobrazovkový režim](/hololens/hololens-kiosk) ) a/nebo [Windows Defender application Control (správa aplikací)](/hololens/windows-efender-application-control-wdac) jsou možnosti pro skrývání a/nebo omezení aplikací.

### <a name="password-management-for-your-clients"></a>Správa hesel pro klienty

1. Odeberte vypršení platnosti hesla. Tato možnost však může zvýšit riziko, že dojde k ohrožení bezpečnosti účtu. Doporučení NIST hesla mění hesla každých 30-90 dní.
1. prodlužte platnost hesla pro zařízení HoloLens 2 tak, aby překročila 90 dní.
1. Zařízení by se měla vrátit do vaší organizace, aby se změnila hesla. Tato možnost však může způsobit problémy, pokud se očekává, že se zařízení nacházejí v klientském zařízení po dobu 90 dní.  
1. U zařízení, která se odesílají do více klientů, resetujte hesla před expedicí zařízení klientům.

### <a name="ensure-that-clients-wont-have-access-to-chat-history"></a>Zajistěte, aby klienti nemuseli mít přístup k historii chatu.

Funkce Remote Assist po každé relaci vymaže historii chatu. k dispozici je ale historie chatu pro Microsoft Teams uživatele.

> [!NOTE]
> vzhledem k tomu, že je povoleno jednotné přihlašování, je důležité zakázat prohlížeč pomocí [ovládacího prvku Windows Defender aplikace (WDAC)](/hololens/windows-defender-application-control-wdac).  pokud externí klient otevře prohlížeč a použije webovou verzi Teams, bude mít klient přístup k historii volání/konverzace.
