---
title: Správa identity a přihlášení uživatelů pro HoloLens
description: Naučte se spravovat identitu uživatelů, podporu více uživatelů, zabezpečení, podnikové ověřování a přihlášení pro zařízení HoloLens.
keywords: HoloLens, uživatel, účet, AAD, Azure AD, ADFS, účet Microsoft, MSA, přihlašovací údaje, reference
ms.assetid: 728cfff2-81ce-4eb8-9aaa-0a3c3304660e
author: scooley
ms.author: scooley
ms.date: 10/6/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: fbef357053900f6495cb59f52cba8669f0d0a3db
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924413"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>Správa identity a přihlášení uživatelů pro HoloLens

> [!NOTE]
> Tento článek je technickým odkazem na odborníky v oblasti IT a na techničtí nadšeni. Pokud hledáte pokyny pro nastavení HoloLens, přečtěte si téma[Nastavení HoloLens (1. generace)](hololens1-start.md)nebo[Nastavení HoloLens 2](hololens2-start.md).

Podobně jako u jiných zařízení s Windows funguje HoloLens vždy v kontextu uživatele. Vždy je k dispozici identita uživatele. HoloLens zpracovává identitu téměř stejným způsobem jako ostatní zařízení s Windows 10. Tento článek je obsáhlý podrobněý odkaz na identitu na HoloLens a zaměřuje se na to, jak se HoloLens liší od ostatních zařízení s Windows 10.

HoloLens podporuje několik druhů identit uživatelů. K přihlášení můžete použít jeden nebo více uživatelských účtů. Tady je přehled typů identit a možností ověřování na HoloLens:

| Typ identity | Účty na zařízení | Možnosti ověřování |
| --- | --- | --- |
| [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/)<sup>1</sup>  | 64 | <ul><li>Poskytovatel přihlašovacích údajů webu Azure</li><li>Aplikace Azure Authenticator</li><li>Biometrika (IRIS) &ndash; HoloLens 2 pouze<sup>2</sup> </li><li>PIN kód &ndash; volitelný pro HoloLens (1. generace), vyžadovaný pro HoloLens 2</li><li>Heslo</li></ul> |
| [Účet Microsoft (MSA)](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Biometrika (IRIS) – &ndash; pouze HoloLens 2</li><li>PIN kód &ndash; volitelný pro HoloLens (1. generace), vyžadovaný pro HoloLens 2</li><li>Heslo</li></ul> |
| [Místní účet](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts) | 1 | Heslo |

Účty propojené s cloudem (Azure AD a MSA) nabízejí více funkcí, protože můžou používat služby Azure.  
> [!IMPORTANT]
> 1 Azure AD Premium se k přihlášení k zařízení nevyžaduje. Vyžaduje se ale pro jiné funkce cloudového nasazení s nízkým dotykem, jako je automatické registrace a autopilot.

> [!NOTE]
> 2 – zatímco zařízení HoloLens 2 může podporovat až 64 účtů Azure AD, v ověřování Iris se můžou zaregistrovat jenom 10 těchto účtů. To je zarovnáno s dalšími [možnostmi biometrik ověřování pro Windows Hello pro firmy](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer).

## <a name="setting-up-users"></a>Nastavení uživatelů

Nejběžnější způsob, jak nastavit nového uživatele, je během předběžného prostředí (OOBE) HoloLens. Během instalace se zobrazí výzva pro uživatele, aby se přihlásili pomocí účtu, který chtějí na zařízení použít. Tento účet může být příjemcem účet Microsoft nebo podnikovým účtem, který je nakonfigurovaný v Azure. Viz nastavení [HoloLens (1. generace)](hololens1-start.md) nebo [HoloLens 2](hololens2-start.md).

Stejně jako Windows na jiných zařízeních se při přihlášení během instalace vytvoří na zařízení profil uživatele. Profil uživatele ukládá aplikace a data. Stejný účet také poskytuje jednotné přihlašování pro aplikace, jako je například Edge nebo Microsoft Store, pomocí rozhraní API Správce účtů systému Windows.  

Pokud k přihlášení k HoloLens použijete podnikový nebo organizační účet, zaregistruje se HoloLens v infrastruktuře IT organizace. Tato registrace umožňuje správci IT nakonfigurovat správu mobilních zařízení (MDM), aby odesílala zásady skupiny na HoloLens.

Ve výchozím nastavení, stejně jako u jiných zařízení s Windows 10, se budete muset znovu přihlásit, když se restartuje nebo obnoví z úsporného režimu. Toto chování můžete změnit pomocí aplikace nastavení nebo můžete chování řídit pomocí zásad skupiny.

### <a name="linked-accounts"></a>Propojené účty

Stejně jako v případě verze Windows na ploše můžete propojit další přihlašovací údaje webového účtu s vaším účtem HoloLens. Takové propojení usnadňuje přístup k prostředkům v aplikacích nebo v rámci aplikací (jako je úložiště) nebo ke kombinování přístupu k osobním a pracovním prostředkům. Po připojení účtu k zařízení můžete udělit oprávnění k používání zařízení pro aplikace, abyste se k jednotlivým aplikacím nemuseli přihlašovat jednotlivě.

Propojování účtů nedělí data uživatelů vytvořená v zařízení, například obrázky nebo soubory ke stažení.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Nastavení podpory více uživatelů (jenom Azure AD)

HoloLens podporuje více uživatelů ze stejného tenanta služby Azure AD. Pokud chcete tuto funkci použít, musíte k nastavení zařízení použít účet, který patří do vaší organizace. Následně se ostatní uživatelé ze stejného tenanta můžou přihlásit k zařízení z přihlašovací obrazovky nebo klepnutím na dlaždici uživatele na panelu Start. V jednom okamžiku může být přihlášen pouze jeden uživatel. Když se uživatel přihlásí, HoloLens odhlásí předchozího uživatele. První uživatel v zařízení je považován za vlastníka zařízení, s výjimkou případu, kdy se služba Azure AD JOIN týká vlastníků [zařízení](security-adminless-os.md#device-owner).

Všichni uživatelé můžou používat aplikace nainstalované na zařízení. Každý uživatel ale má vlastní data a předvolby aplikace. Odebráním aplikace ze zařízení ji odeberete pro všechny uživatele.  

Zařízení nastavená s účty Azure AD neumožní přihlášení k zařízení pomocí účtu Microsoft. Všechny následující účty musí být účty Azure AD ze stejného tenanta jako zařízení. K aplikacím, které ji podporují (například Microsoft Store), se můžete stále [přihlašovat pomocí účtu Microsoft](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) . Pokud chcete změnit použití účtů Azure AD na účty Microsoft pro přihlášení k zařízení, musíte [zařízení znovu zablikat](hololens-recovery.md#clean-reflash-the-device).

> [!NOTE]
> **HoloLens (1. generace)** začala podporovat více uživatelů Azure AD ve [Windows 10. dubna 2018 aktualizace](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) jako součást [Windows holografické pro firmy](hololens-upgrade-enterprise.md).

### <a name="multiple-users-listed-on-sign-in-screen"></a>Více uživatelů uvedených na přihlašovací obrazovce

Předchozí přihlašovací obrazovka zobrazila pouze posledního přihlášeného uživatele a vstupní bod jiného uživatele. Dostali jsme zpětnou vazbu od zákazníků, pokud se k zařízení přihlásilo více uživatelů. Pořád se vyžadovalo, aby znovu zapisovali své uživatelské jméno atd.

Zavedená ve [Windows holografické verzi 21H1](hololens-release-notes.md#windows-holographic-version-21h1)při výběru **dalšího uživatele** , který se nachází napravo od pole pro zadání kódu PIN, zobrazí se na přihlašovací obrazovce více uživatelů, kteří se k zařízení dříve přihlásili. To umožňuje uživatelům vybrat svůj profil uživatele a pak se přihlašovat pomocí svých přihlašovacích údajů Windows Hello. Do zařízení můžete přidat nového uživatele pomocí tlačítka **Přidat účet** na stránce ostatní uživatelé.

Když v nabídce ostatní uživatelé přejdete na tlačítko ostatní uživatelé, zobrazí se poslední uživatel přihlášený k zařízení. Kliknutím na toto tlačítko se vrátíte na přihlašovací obrazovku pro tohoto uživatele.

![Výchozí přihlašovací obrazovka](./images/multiusers1.jpg)

<br>

![Přihlašovací obrazovka jiní uživatelé](./images/multiusers2.jpg)

## <a name="removing-users"></a>Odebírání uživatelů

Uživatele můžete ze zařízení odebrat tak, že kliknete na **Nastavení**  >  **účty**  >  **ostatní lidé**. Tato akce také uvolní místo tím, že se ze zařízení odeberou všechna data aplikací daného uživatele.  

## <a name="using-single-sign-on-within-an-app"></a>Použití jednotného přihlašování v rámci aplikace

Jako vývojář aplikací můžete využít výhod propojených identit na HoloLens pomocí [rozhraní API Správce účtů systému Windows](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.Web.Core), stejně jako na jiných zařízeních s Windows. Některé ukázky kódu pro tato rozhraní API jsou k dispozici na GitHubu: [Ukázka správy webových účtů](https://go.microsoft.com/fwlink/p/?LinkId=620621).

Případné přerušení účtu, ke kterému může dojít, například vyžádání souhlasu uživatele pro informace o účtu, dvojúrovňové ověřování a tak dále, musí být zpracovány, když aplikace požaduje ověřovací token.

Pokud vaše aplikace vyžaduje konkrétní typ účtu, který nebyl dříve propojen, může aplikace požádat systém, aby vyzvat uživatele, aby ho přidal. Tato žádost aktivuje podokno nastavení účtu, které se spustí jako modální dítě vaší aplikace. V případě 2D aplikací se toto okno vykreslí přímo přes střed vaší aplikace. V případě aplikací Unity tato žádost krátce převezme uživatele z vaší holografické aplikace, aby vygenerovalo podřízené okno. Informace o přizpůsobení příkazů a akcí v tomto podokně naleznete v tématu [Třída WebAccountCommand](https://docs.microsoft.com/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand).

## <a name="enterprise-and-other-authentication"></a>Podnikové a jiné ověřování

Pokud vaše aplikace používá jiné typy ověřování, jako je například protokol NTLM, Basic nebo Kerberos, můžete k shromažďování, zpracování a ukládání přihlašovacích údajů uživatele použít [uživatelské rozhraní přihlašovacích údajů systému Windows](https://docs.microsoft.com/uwp/api/Windows.Security.Credentials.UI) . Uživatelské prostředí shromažďování těchto přihlašovacích údajů se velmi podobá jiným cloudovým přerušením účtů a zobrazuje se jako podřízená aplikace na 2D aplikaci nebo krátce pozastaví aplikaci Unity, aby zobrazovala uživatelské rozhraní.

## <a name="deprecated-apis"></a>Zastaralá rozhraní API

Jedním ze způsobů, jak se vyvíjí pro HoloLens, se liší od vývoje pro stolní počítače, protože rozhraní [OnlineIDAuthenticator](https://docs.microsoft.com/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) API není plně podporované. I když rozhraní API vrátí token, pokud je primární účet v dobrém umístění, přerušení, jako jsou ty popsané v tomto článku, nezobrazují žádné uživatelské rozhraní pro uživatele a nepodaří se mu správně ověřit účet.

## <a name="frequently-asked-questions"></a>Nejčastější dotazy

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>Podporuje se Windows Hello pro firmy na HoloLens (1. generace)?

Windows Hello pro firmy (podporující používání kódu PIN pro přihlášení) se podporuje pro HoloLens (1. generace). Povolení přihlášení PIN Windows Hello pro firmy na HoloLens:

1. Zařízení HoloLens musí být [spravované přes MDM](hololens-enroll-mdm.md).
1. Pro zařízení musíte povolit Windows Hello pro firmy. ([Viz pokyny pro Microsoft Intune.](https://docs.microsoft.com/intune/windows-hello))
1. Na HoloLens může uživatel potom použít   >  **Možnosti přihlášení** nastavení  >  **přidat kód** PIN a nastavit PIN kód.

> [!NOTE]
> Uživatelé, kteří se přihlásí pomocí účet Microsoft můžou také nastavit PIN kód v   >  **možnosti přihlašování** nastavení  >  **přidat kód PIN**. Tento kód PIN je přidružen k [Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello)místo [Windows Hello pro firmy](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>Jak je v HoloLens 2 implementováno ověřování Iris – biometrika?

HoloLens 2 podporuje ověřování Iris. Iris je založen na technologii Windows Hello a je podporován pro použití Azure Active Directory i účtů Microsoft. Iris je implementováno stejným způsobem jako jiné technologie Windows Hello a dosahuje zabezpečení biometrikae daleko od 1/100 tisíc.

Další informace najdete v článku o [biometrických požadavcích a specifikacích pro Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) . Přečtěte si další informace o [Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) a [Windows Hello pro firmy](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification). 

### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>Jak má typ účtu vliv na chování přihlášení?

Pokud použijete zásady pro přihlášení, zásada se vždycky dodržuje. Pokud se nepoužije žádná zásada pro přihlášení, jedná se o výchozí chování každého typu účtu:

- **Azure AD**: požádá o ověřování ve výchozím nastavení a dá se nakonfigurovat podle **Nastavení** , aby už nevyžadovala ověřování.
- **Účet Microsoft**: chování zámku je jiné, což umožňuje automatické odemknutí, ale při restartování se pořád vyžaduje přihlášení k ověřování.
- **Místní účet**: vždy žádá o ověření ve formě hesla a nedá se konfigurovat v **nastaveních** .

> [!NOTE]
> Časovače nečinnosti se aktuálně nepodporují, což znamená, že zásady **AllowIdleReturnWithoutPassword** se respektují jenom v případě, že zařízení přejde do úsporného režimu.

## <a name="additional-resources"></a>Další zdroje informací

Další informace o ochraně identity uživatelů a ověřování najdete v [dokumentaci k zabezpečení a identitě Windows 10](https://docs.microsoft.com/windows/security/identity-protection/).

Další informace o nastavení infrastruktury hybridní identity najdete v [dokumentaci k Azure Hybrid identity](https://docs.microsoft.com/azure/active-directory/hybrid/).
