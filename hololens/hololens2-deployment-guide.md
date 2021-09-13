---
title: Nasazení připojení ke cloudu HoloLens 2 k externím klientům
description: Průvodce nasazením HoloLens 2 pro externí klienty (jako příklad s vzdálenou asistencí)
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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032292"
---
# <a name="deploy-cloud-connected-hololens-2-to-external-clients"></a>Nasazení připojení ke cloudu HoloLens 2 k externím klientům

Tato příručka je doplňkem průvodce nasazením připojeným [ke cloudu.](hololens2-cloud-connected-overview.md) Používá se v situacích, kdy vaše organizace chce do zařízení externího klienta HoloLens do zařízení externího klienta pro krátkodobé nebo dlouhodobé použití. Externí klient se přihlásí k zařízení HoloLens 2 pomocí přihlašovacích údajů [](/dynamics365/mixed-reality/remote-assist/ra-overview) poskytnutých vaší organizací a pomocí vzdálené pomoci kontaktuje vaše odborníky. Tato příručka obsahuje obecná doporučení k nasazení [HoloLens 2,](#general-deployment-recommendations) která se vztahují [](#common-external-client-deployment-concerns) na většinu scénářů nasazení externího nasazení HoloLens 2, a běžné obavy zákazníků při nasazování vzdálené pomoci pro externí použití. 

## <a name="prerequisites"></a>Požadavky

Podle průvodce nasazením připojeným [](hololens2-cloud-connected-overview.md) ke cloudu by měla být zavedena následující infrastruktura, která externě nasadí HoloLens 2.

- Připojení ke službě Azure AD s automatickou registrací MDM – spravované pomocí MDM (Intune)
- Uživatelé se přihlašují pomocí vlastního podnikového účtu (Azure AD).
    - Podporuje se jeden nebo více uživatelů na zařízení.

### <a name="remote-assist-licensing-and-requirements"></a>Licencování a požadavky služby Remote Assist

- Účet Azure AD (vyžadované pro nákup předplatného a přiřazení licencí)
- [Předplatné Remote Assistu](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (nebo [zkušební verze Remote Assistu)](/dynamics365/mixed-reality/remote-assist/try-remote-assist)

Další [informace o vzdálené pomoci najdete v tématu](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist).

### <a name="dynamics-365-remote-assist-user"></a>Uživatel Dynamics 365 Remote Assistu

- Licence Remote Assistu
- Připojení k síti

### <a name="microsoft-teams-user"></a>Microsoft Teams uživatele

- Microsoft Teams nebo [Teams Freemium](https://products.office.com/microsoft-teams/free)
- Připojení k síti

## <a name="general-deployment-recommendations"></a>Obecná doporučení pro nasazení

Pro externí nasazení HoloLens 2 doporučujeme následující kroky:

1. Jako základní [sestavení HoloLens nejnovější verzi operačního](https://aka.ms/hololens2download) systému.
1. Přiřaďte licence na základě uživatele nebo zařízení pomocí následujícího postupu:
    1. [Vytvořte skupinu v AAD a přidejte členy](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) pro uživatele HoloLens/RA.
    1. [Přiřaďte této skupině](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) licence na základě zařízení nebo uživatelů.
    1. (Volitelné) Cílové skupiny pro [zásady správy mobilních zařízení (MDM).](hololens-enroll-mdm.md)

1. Připojte zařízení AAD ke svému tenantovi, [automaticky](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)se zaregistrujte a nakonfigurujte prostřednictvím [Autopilotu.](/hololens/hololens2-autopilot) Další informace najdete v tématu [vlastník zařízení.](/hololens/security-adminless-os#device-owner)
    1. První uživatel v zařízení bude vlastníkem zařízení.
    1. Pokud je zařízení připojené k AAD, uživatel, který připojení provedl, je vlastníkem zařízení.
    
1. [Tenant zařízení](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) uzamkne, aby ho mohl k zařízení jenom váš tenant spojit.
    1. Viz také [Tenant lock CSP](/windows/client-management/mdm/tenantlockdown-csp).

1. [Nakonfigurujte bezobrazovový režim pomocí globálního přiřazeného přístupu](/hololens/hololens-global-assigned-access-kiosk).

1. Zakažte následující (volitelné) možnosti:
    1. Možnost zařízení přetát do vývojářského [režimu tady.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)
    1. Možnost připojení zařízení HoloLens počítači, aby bylo možné kopírovat [datum, zakažte USB.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
       > [!NOTE]
        > Pokud nechcete zakázat USB, ale chcete mít možnost použít na zařízení zřizovací balíček pomocí USB, postupujte podle pokynů k povolení instalace zřizovacího [balíčku.](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)

1. Pomocí [Windows Defender Application Control (WDAC)](/hololens/windows-defender-application-control-wdac) povolte nebo zablokujte aplikace na HoloLens 2.
1. V rámci instalace aktualizujte aplikaci Remote Assist na nejnovější verzi. Zvažte následující dvě možnosti:
    1. Přejděte na Windows **Microsoft Store --> Remote Assist -->** a Update App .
    1. [Ve výchozím nastavení je povolená možnost ApplicationManagement/AllowAppStoreAutoUpdate,](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) která umožňuje automatické aktualizace aplikací. Pokud chcete dostávat aktualizace, nechte zařízení připojené k napájení.
1. [Zakažte všechny stránky nastavení](/hololens/settings-uri-list) kromě nastavení sítě, aby se uživatelé v klientských lokalitách připojovat k sítím hostů.
1. [Správa HoloLens aktualizací](/hololens/hololens-updates)
    1. Možnost řízení [aktualizací operačního systému](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) nebo povolení volného toku.
1. Nastavte [běžná omezení zařízení.](/hololens/hololens-common-device-restrictions)

Teď jsou externí klienti připravení používat své HoloLens 2.

## <a name="common-external-client-deployment-concerns"></a>Běžné problémy s nasazením externích klientů

- [Zajištění, že klienti spolu vzájemně nekomunikují](#ensure-that-external-clients-cant-communicate-with-one-another)
- [Zajištění, že klienti nezíská přístup k prostředkům společnosti](#ensure-that-clients-wont-have-access-to-company-resources)
- [Skrytí nebo omezení aplikací](#hidden-or-restricted-apps)
- [Správa hesel pro klienty](#password-management-for-your-clients) 
- [Zajištění, že klienti mají přístup k historii chatu](#ensure-that-clients-wont-have-access-to-chat-history)

### <a name="ensure-that-external-clients-cant-communicate-with-one-another"></a>Ujistěte se, že spolu externí klienti spolu nekomunikují.

Vzdálená HoloLens k HoloLens volání nejsou podporována. Klienti mohou vyhledávat, ale spolu navzájem nekomunikují. [Informační bariéry v Microsoft 365](/microsoft-365/compliance/information-barriers) mohou dále omezovat, s kým může klient vyhledávat a volat. Další možností je použít Microsoft Teams adresáře s [vymezenou oborem.](/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> Vzhledem k tomu, že je povolené jednotné přihlašování, je důležité zakázat prohlížeč pomocí [nástroje Windows Defender Application Control (WDAC).](/hololens/windows-defender-application-control-wdac) Pokud externí klient otevře prohlížeč a použije webovou verzi Teams, bude mít klient přístup k historii chatu.

### <a name="ensure-that-clients-wont-have-access-to-company-resources"></a>Ujistěte se, že klienti nebudou mít přístup k prostředkům společnosti.

Je třeba zvážit dvě možnosti.

První možností je vícevrstvý přístup:

1. Přiřaďte pouze licence, které uživatel vyžaduje. Pokud nepřiřadíte OneDrive, Outlook, SharePoint, Yammer atd., uživatel k těmito prostředkům nebude mít přístup. Jediné licence, které budou uživatelé potřebovat, jsou licence Remote Assistu, Intune a AAD.
1. Blokovat aplikace (například e-mail), ke které nechcete klientům přistupovat (viz [Aplikace jsou skryté nebo omezené).](#apps are hidden or restricted)
1. Nesdílejte s klienty uživatelská jména ani hesla. Pro přihlášení k HoloLens 2 se vyžaduje e-mail a číselný PIN kód.

Druhou možností je vytvořit samostatného tenanta, který je hostitelem klientů (viz Obrázek 1.1).

**Obrázek 1.1**

![Image tenanta služby.](./images/hololens-service-tenant-image.png)

### <a name="hidden-or-restricted-apps"></a>Skryté nebo omezené aplikace

[Kiosk mode](/hololens/hololens-kiosk) and/or [Windows Defender Application Control (WDAC)](/hololens/windows-efender-application-control-wdac) jsou možnosti pro skrytí nebo omezení aplikací.

### <a name="password-management-for-your-clients"></a>Správa hesel pro klienty

1. Odeberte vypršení platnosti hesla. Tato možnost však může zvýšit riziko ohrožení zabezpečení účtu. Doporučení pro hesla NIST se mění každých 30 až 90 dnů.
1. Prodloužení platnosti hesla pro HoloLens 2 zařízení na více než 90 dnů.
1. Pokud chcete změnit hesla, měla by se zařízení vrátit do vaší organizace. Tato možnost ale může způsobit problémy, pokud se očekává, že budou zařízení v továrně klienta na více než 90 dnů.  
1. U zařízení odesílaných více klientům před odesláním zařízení klientům resetujte hesla.

### <a name="ensure-that-clients-wont-have-access-to-chat-history"></a>Ujistěte se, že klienti nebudou mít přístup k historii chatu.

Remote Assist vymaže historii chatu po každé relaci. Historie chatu ale bude dostupná pro Microsoft Teams uživatele.

> [!NOTE]
> Vzhledem k tomu, že je povolené jednotné přihlašování, je důležité zakázat prohlížeč pomocí [nástroje Windows Defender Application Control (WDAC).](/hololens/windows-defender-application-control-wdac)  Pokud externí klient otevře prohlížeč a používá webovou verzi Teams, bude mít klient přístup k historii volání nebo chatu.
