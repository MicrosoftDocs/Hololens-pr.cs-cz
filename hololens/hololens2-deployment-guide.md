---
title: Průvodce nasazením externích klientů
description: Průvodce nasazením HoloLens 2 pro externí klienty (jako příklad s vzdálenou asistencí)
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: medium
ms.date: 1/12/2021
ms.custom: ''
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 495be858c235931ed591b097e6b5951f7197c3f7a62bd1aaa16bea65a4e3885f
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2021
ms.locfileid: "115659879"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a>Nasazení HoloLens 2 do externích klientů pomocí vzdálené pomoci

Tato příručka pomáhá IT specialistům s následujícími cíli nasadit Microsoft HoloLens 2 zařízení v organizaci:

1. Připojení ke cloudu HoloLens 2 zařízení
1. Půjčování HoloLens 2 zařízením externím klientům k použití
1. Zabezpečená půjčovaná zařízení

Tato příručka bude poskytovat obecná doporučení k nasazení HoloLens [2,](#general-deployment-recommendations-and-instructions) která se vztahují [](#common-concerns) na většinu scénářů nasazení HoloLens 2, a běžné obavy zákazníků při nasazování vzdálené pomoci pro externí použití.

## <a name="scenario-description"></a>Popis scénáře

Pro účely tohoto dokumentu chce společnost Contoso odeslat zařízení HoloLens 2 do závodu externího klienta pro krátkodobé nebo dlouhodobé použití. Když klient potřebuje pomoc se servisními technikami, klient se přihlásí k zařízení HoloLens 2 pomocí přihlašovacích údajů poskytnutých společností Contoso a pomocí vzdálené pomoci kontaktuje odborníky společnosti Contoso.

Další informace o vzdálené pomoci [najdete tady.](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)

### <a name="requirements-for-this-scenario"></a>Požadavky pro tento scénář

1. [Azure AD](/azure/active-directory/fundamentals/active-directory-whatis)
1. Mobilní Správce zařízení – například [Intune](/mem/intune/fundamentals/free-trial-sign-up)
1. Licence Remote Assistu
    1. [Nákup remote assistu](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [Zkušební verze Remote Assistu](/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a>Běžné obavy

- [Jak zajistit, že externí klienti nebudou mít možnost vzájemně komunikovat](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [Jak zajistit, aby klienti nemají přístup k prostředkům společnosti](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [Omezení aplikací](#how-to-restrict-apps)
- [Správa hesel](#how-to-manage-passwords)
- [Jak zajistit, aby klienti nemají přístup k historii chatu](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a>Jak zajistit, že externí klienti nebudou mít možnost vzájemně komunikovat

Vzhledem k tomu, HoloLens HoloLens vzdálená pomoc není podporována, klienti mohou vyhledávat ,ale nemohou spolu komunikovat. Aby bylo možné dále omezit, kdo klienti mohou vyhledávat a volat, mohou informační  [bariéry](/microsoft-365/compliance/information-barriers) omezit, s kým klient může komunikovat. Další možností, která je třeba zvážit, je použití [vyhledávání v adresáři s vymezenou oborem.](/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> Vzhledem k tomu, že je povolené jednotné přihlašování, je důležité zakázat prohlížeč pomocí nástroje [**WDAC.**](/hololens/windows-defender-application-control-wdac) Pokud externí klient otevře prohlížeč a použije webovou verzi Teams, bude mít klient přístup k historii volání nebo chatu.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a>Jak zajistit, aby klienti nemají přístup k prostředkům společnosti

Je třeba zvážit dvě možnosti.

První možností je vícevrstvý přístup:

1. Přiřaďte pouze licence, které uživatel vyžaduje. Pokud uživateli nepřiřadíte OneDrive, Outlook, SharePoint, Yammer atd., nebude k těmito prostředkům mít přístup. Jediné licence, které budou uživatelé potřebovat, jsou licence Remote Assistu, Intune a AAD.
1. Blokovat aplikace (například e-mail), ke které nechcete klientům přistupovat (viz [Jak omezit aplikace).](#how-to-restrict-apps)
1. NESDÍLEJTE s klienty uživatelská jména ani hesla. Pro přihlášení k HoloLens 2 se vyžaduje e-mail a číselný PIN kód.

Druhou možností je vytvořit samostatného tenanta, který je hostitelem klientů (viz Obrázek 1.1).

**Obrázek 1.1**

![Image tenanta služby](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a>Omezení aplikací

[Kiosk Mode](/hololens/hololens-kiosk) a/nebo [WDAC (Windows Defender Application Control)](/hololens/windows-defender-application-control-wdac) jsou možnosti pro omezení aplikací.

### <a name="how-to-manage-passwords"></a>Správa hesel

1. Odeberte vypršení platnosti hesla. Tím se ale zvyšuje pravděpodobnost ohrožení zabezpečení účtu. Doporučení pro hesla NIST se mění každých 30 až 90 dnů.
1. Prodloužení platnosti hesla pro HoloLens 2 zařízení na více než 90 dnů.
1. Pokud chcete změnit hesla, měla by se zařízení vrátit společnosti Contoso. To ale může způsobit problémy, pokud se očekává, že budou zařízení v továrně klienta na více než 90 dnů.  
1. U zařízení odesílaných více klientům před odesláním zařízení klientům resetujte hesla.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a>Jak zajistit, aby klienti nemají přístup k historii chatu

Remote Assist vymaže historii chatu po každé relaci. Historie chatu ale bude k dispozici pro Microsoft Teams uživatele.

> [!NOTE]
> Vzhledem k tomu, že je povolené jednotné přihlašování, je důležité zakázat prohlížeč pomocí nástroje [**WDAC.**](/hololens/windows-defender-application-control-wdac) Pokud externí klient otevře prohlížeč a použije webovou verzi Teams, bude mít klient přístup k historii volání nebo chatu.

## <a name="general-deployment-recommendations-and-instructions"></a>Obecné pokyny a Recommendations nasazení

Pro následující kroky nasazení HoloLens následující:

1. Jako základní [sestavení HoloLens nejnovější verzi operačního](https://aka.ms/hololens2download) systému.
1. Přiřazení uživatelských licencí nebo licencí na základě zařízení:
    1. Licence založené na uživatelích i na zařízeních postupuje následovně:
        1. [Vytvořte skupinu v AAD a přidejte členy](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) pro uživatele HoloLens/RA.
        1. [Přiřaďte této skupině](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) licence na základě zařízení nebo uživatelů.
        1. (Volitelné) Můžete cílit na skupiny pro zásady MDM.

1. Zařízení by měla být připojená [](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)k vašemu tenantovi, automaticky zaregistrovaná a nakonfigurovaná prostřednictvím [automatického pilotního projektu](/hololens/hololens2-autopilot).
    1. Upozorňujeme, že první uživatel v zařízení bude vlastníkem zařízení.
    1. Upozorňujeme, že pokud je zařízení připojené k AAD, uživatel, který připojení provedl, je vlastníkem zařízení.
    1. Další informace najdete v tématu [Vlastník zařízení.](/hololens/security-adminless-os#device-owner)
1. [Tenant zařízení](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) uzamkne, aby se k vašemu tenantovi mohl pouze připojil.
    1. **Další odkaz:** [Tenant lock CSP](/windows/client-management/mdm/tenantlockdown-csp).
1. Nakonfigurujte bezobrazovkové terminály pomocí globálního přiřazeného [přístupu k .](/hololens/hololens-global-assigned-access-kiosk)
1. Doporučujeme zakázat následující (volitelné) možnosti:
    1. Možnost zařízení přetát do vývojářského [režimu tady.](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)
    1. Možnost připojení zařízení HoloLens počítači a zkopírování data [zakažte USB.](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
       > [!NOTE]
        > Pokud nechcete zakázat USB, ale chcete mít možnost použít zřizovací balíček pro zařízení pomocí USB, postupujte podle pokynů uvedených [**tady.**](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)

1. Pomocí [nástroje WDAC](/hololens/windows-defender-application-control-wdac) povolte nebo zablokujte aplikace na HoloLens 2.
1. V rámci instalace aktualizujte aplikaci Remote Assist na nejnovější verzi. Můžete to provést dvěma způsoby:
    1. Můžete to udělat tak, že Windows **Microsoft Store -> Remote Assist --> a Update App**.
    1. [Ve výchozím nastavení je povolená možnost ApplicationManagement/AllowAppStoreAutoUpdate,](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) která umožňuje automatické aktualizace aplikací. Pokud chcete dostávat aktualizace, nechte zařízení připojené k napájení.
1. [Zakažte všechny stránky nastavení](/hololens/settings-uri-list) kromě nastavení sítě, aby se uživatelé v klientských lokalitách připojovat k sítím hostů.
1. [Správa HoloLens aktualizací](/hololens/hololens-updates)
    1. Možnost řízení [aktualizací operačního systému](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) nebo povolení volného toku.
1. [Běžná omezení zařízení](/hololens/hololens-common-device-restrictions).
