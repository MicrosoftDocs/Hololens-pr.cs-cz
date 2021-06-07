---
title: Průvodce nasazením externích klientů
description: Průvodce nasazením HoloLens 2 pro externí klienty (s příkladem vzdáleného asistence)
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
ms.openlocfilehash: 56930ceea05cd5713b9c7eb57e0967a9d0cd4988
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377594"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a>Nasazení HoloLens 2 na externí klienty pomocí vzdálené pomoci

Tato příručka pomáhá odborníkům v oblasti IT s následujícími cíli nasazení zařízení Microsoft HoloLens 2 v jejich organizaci:

1. Cloudová připojení zařízení HoloLens 2
1. Vypůjčení zařízení HoloLens 2 k externím klientům pro použití
1. Zabezpečená zapůjčená zařízení

Tato příručka obsahuje [Obecná doporučení pro nasazení HoloLens 2](#general-deployment-recommendations-and-instructions) , která se vztahují na většinu scénářů nasazení HoloLens 2 a [běžné obavy](#common-concerns) , že zákazníci mají nasazovat vzdálenou pomoc pro externí použití.

## <a name="scenario-description"></a>Popis scénáře

Pro účely tohoto dokumentu společnost Contoso chce dodávat zařízení HoloLens 2 do závodu externího klienta pro krátkodobé nebo dlouhodobé použití. Když klient potřebuje pomoc při obsluze, přihlásí se k zařízení HoloLens 2 pomocí přihlašovacích údajů, které poskytla společnost Contoso, a pomocí programu Remote Assist kontaktujte odborníky společnosti Contoso.

Další informace o funkci Remote Assist najdete [tady](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist).

### <a name="requirements-for-this-scenario"></a>Požadavky pro tento scénář

1. [Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. Mobilní Správce zařízení – například [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)
1. Licence pro vzdálenou pomoc
    1. [Koupit vzdálenou pomoc](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [Zkušební verze vzdáleného asistence](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a>Běžné obavy

- [Jak zajistit, aby externí klienti nemohly komunikovat mezi sebou](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [Jak zajistit, aby klienti neměli přístup k firemním prostředkům](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [Jak omezit aplikace](#how-to-restrict-apps)
- [Správa hesel](#how-to-manage-passwords)
- [Jak zajistit, aby klienti neměli přístup k historii chatu](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a>Jak zajistit, aby externí klienti nemohly komunikovat mezi sebou

Vzhledem k tomu, že volání funkce Remote Assist do HoloLens nejsou podporovaná, klienti můžou hledat, ale nemůžou vzájemně komunikovat. Chcete-li dále omezit, kteří klienti mohou hledat a volat, mohou  [překážky v informacích](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) omezit, se kterými může klient komunikovat. Další možností, jak zvážit, je použití [prohledávání adresářů v oboru](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)

 > [!NOTE]
> Vzhledem k tomu, že je povolené jednotné přihlašování, je důležité zakázat prohlížeč pomocí [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac). Pokud externí klient otevře prohlížeč a použije webovou verzi týmů, bude mít klient přístup k historii volání/konverzace.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a>Jak zajistit, aby klienti neměli přístup k firemním prostředkům

Je potřeba vzít v úvahu dvě možnosti.

První možností je Vícenásobný přístup:

1. Přiřaďte jenom licence, které uživatel potřebuje. Pokud k uživateli nepřiřadíte OneDrive, Outlook, SharePoint, Yammer atd., nebude mít k těmto prostředkům přístup. Jedinými licencemi, které budou uživatelé potřebovat, jsou služby Remote Assist, Intune a AAD, které se mají začít.
1. Blokovat aplikace (jako je e-mail), ke kterým nechcete, aby klienti měli přístup (viz [jak omezit aplikace](#how-to-restrict-apps)).
1. Nesdílejte uživatelské jméno ani heslo pomocí klientů. Pro přihlášení k HoloLens 2 se vyžaduje e-mail a číselný PIN kód.

Druhou možností je vytvořit samostatného tenanta, který je hostitelem klientů (viz obrázek 1,1).

**Obrázek 1,1**

![Obrázek klienta služby](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a>Jak omezit aplikace

[Režim celoobrazovkového režimu](https://docs.microsoft.com/hololens/hololens-kiosk) a/nebo [WDAC (řízení aplikací v programu Windows Defender)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) jsou možnosti pro omezení aplikací.

### <a name="how-to-manage-passwords"></a>Správa hesel

1. Odeberte vypršení platnosti hesla. To však zvyšuje pravděpodobnost, že dojde k ohrožení bezpečnosti účtu. Doporučení NIST hesla mění hesla každých 30-90 dní.
1. Prodlužte platnost hesla pro zařízení HoloLens 2 na více než 90 dní.
1. Zařízení by se měla vrátit do společnosti Contoso, aby se změnila hesla. To však může způsobit problémy, pokud se očekává, že zařízení budou v zařízení klienta po dobu 90 dní.  
1. U zařízení, která se odesílají do více klientů, resetujte hesla před expedicí zařízení klientům.

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a>Jak zajistit, aby klienti neměli přístup k historii chatu

Funkce Remote Assist po každé relaci vymaže historii chatu. Pro uživatele Microsoft Teams bude ale k dispozici historie chatu.

> [!NOTE]
> Vzhledem k tomu, že je povolené jednotné přihlašování, je důležité zakázat prohlížeč pomocí [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac). Pokud externí klient otevře prohlížeč a použije webovou verzi týmů, bude mít klient přístup k historii volání/konverzace.

## <a name="general-deployment-recommendations-and-instructions"></a>Obecná doporučení a pokyny pro nasazení

Pro kroky nasazení HoloLens 2 doporučujeme následující:

1. Použijte [nejnovější verzi operačního systému HoloLens](https://aka.ms/hololens2download) jako základní sestavení.
1. Přiřazení licencí založených na uživatelích nebo zařízeních:
    1. Licence založené na uživatelích a zařízeních: postupujte podle následujících kroků:
        1. [Vytvořte v AAD skupinu a přidejte do ní členy](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) pro uživatele HOLOLENS/RA.
        1. Přiřaďte k této skupině licence založené na [zařízení nebo uživatele](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) .
        1. Volitelné Můžete cílit na skupiny pro zásady MDM.

1. Zařízení by měla být AAD připojená k vašemu tenantovi, [automaticky zaregistrovaná](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)a nakonfigurovaná prostřednictvím [automatického pilotního nasazení](https://docs.microsoft.com/hololens/hololens2-autopilot).
    1. Všimněte si, že první uživatel na zařízení bude vlastníkem zařízení.
    1. Upozorňujeme, že pokud je zařízení připojené k AAD, uživatel, který provedl připojení, ho provede vlastníkem zařízení.
    1. Další informace najdete v tématu [vlastník zařízení](https://docs.microsoft.com/hololens/security-adminless-os#device-owner).
1. [Tenant zamkne](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) zařízení, aby se mohl připojit jenom k vašemu tenantovi.
    1. **Další odkaz: CSP pro** [Zámek tenanta](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp).
1. Nakonfigurujte beznabídkový přístup pomocí globálního přiřazeného přístupu [sem](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk).
1. Doporučujeme zakázat následující (volitelné) možnosti:
    1. Možnost umístit zařízení do vývojářského [režimu.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)
    1. Možnost připojit HoloLens k počítači ke zkopírování data [zakázání USB](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)
       > [!NOTE]
        > Pokud nechcete zakázat USB, ale chcete mít možnost použít zřizovací balíček na zařízení pomocí USB, postupujte podle pokynů uvedených [**tady**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage).

1. Použijte [WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) k povolení nebo blokování aplikací na zařízení HoloLens 2.
1. Aktualizujte vzdálenou pomoc na nejnovější verzi jako součást instalace. To můžete provést dvěma způsoby:
    1. To se dá udělat tak, že do Windows **Microsoft Store--> Vzdálená pomoc – > a aktualizujete aplikaci**.
    1. [ApplicationManagement/AllowAppStoreAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) – povoluje automatické aktualizace aplikací – je ve výchozím nastavení povolená. Nechejte zařízení napájené ze sítě a získávat aktualizace.
1. [Zakažte všechny stránky nastavení](https://docs.microsoft.com/hololens/settings-uri-list) s výjimkou nastavení sítě, aby se uživatelé mohli připojit k sítím hostů v klientských lokalitách.
1. [Správa aktualizací HoloLens](https://docs.microsoft.com/hololens/hololens-updates)
    1. Možnost [řízení aktualizací operačního systému](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) nebo umožnění bezchodového toku.
1. [Běžná omezení zařízení](https://docs.microsoft.com/hololens/hololens-common-device-restrictions).
