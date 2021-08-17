---
title: Správa identity a přihlášení uživatelů pro HoloLens
description: naučte se spravovat identitu uživatelů, podporu více uživatelů, zabezpečení, podnikové ověřování a přihlašování pro HoloLens zařízení.
keywords: HoloLens, uživatel, účet, AAD, Azure AD, adfs, účet microsoft, msa, přihlašovací údaje, reference
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
ms.openlocfilehash: 11a5680ea2b27a277bc4eb5b1dc0e62a2c602312
ms.sourcegitcommit: 5cb3230e02e703584e50358cb0f0b5f33a51b169
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/13/2021
ms.locfileid: "121858447"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>Správa identity a přihlášení uživatelů pro HoloLens

> [!NOTE]
> Tento článek je technickým odkazem na odborníky v oblasti IT a na techničtí nadšeni. pokud hledáte HoloLens pokyny pro nastavení, přečtěte si téma[nastavení HoloLens (1. generace)](hololens1-start.md)nebo[nastavení HoloLens 2](hololens2-start.md).

stejně jako u jiných Windows zařízení HoloLens vždy funguje v kontextu uživatele. Vždy je k dispozici identita uživatele. HoloLens považuje identitu za skoro stejným způsobem jako ostatní zařízení Windows. tento článek je obsáhlý podrobněý odkaz na identitu na HoloLens a zaměřuje se na to, jak se HoloLens liší od jiných Windows zařízení.

HoloLens podporuje několik druhů identit uživatelů. K přihlášení můžete použít jeden nebo více uživatelských účtů. Tady je přehled typů identit a možností ověřování na HoloLens:

| Typ identity | Účty na zařízení | Možnosti ověřování |
| --- | --- | --- |
| [Azure Active Directory](/azure/active-directory/)<sup>1</sup>  | 64 | <ul><li>Poskytovatel přihlašovacích údajů webu Azure</li><li>aplikace Azure Authenticator</li><li>biometrika (Iris) &ndash; HoloLens 2 pouze<sup>2</sup> </li><li>FIDO2 klíč zabezpečení</li><li>PIN kód &ndash; volitelný pro HoloLens (1. generace), který se vyžaduje pro HoloLens 2</li><li>Heslo</li></ul> |
| [Účet Microsoft (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>biometrika (Iris) &ndash; HoloLens pouze 2</li><li>PIN kód &ndash; volitelný pro HoloLens (1. generace), který se vyžaduje pro HoloLens 2</li><li>Heslo</li></ul> |
| [Místní účet](/windows/security/identity-protection/access-control/local-accounts)<sup>3</sup> | 1 | Heslo |

Účty propojené s cloudem (Azure AD a MSA) nabízejí více funkcí, protože můžou používat služby Azure.  
> [!IMPORTANT]
> 1 Azure AD Premium se k přihlášení k zařízení nevyžaduje. Vyžaduje se ale pro jiné funkce cloudového nasazení s nízkým dotykem, jako je automatické registrace a autopilot.

> [!NOTE]
> 2 – když zařízení HoloLens 2 může podporovat až 64 účtů Azure AD, může se v ověřování Iris zaregistrovat jenom 31 těchto účtů. to je zarovnáno s dalšími [možnostmi biometrického ověřování pro Windows Hello pro firmy](/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer).

> [!IMPORTANT]
> 3 – místní účet se dá v zařízení nastavit jenom [prostřednictvím zřizovacího balíčku během počátečního](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)nastavování. nedá se přidat později v aplikaci nastavení. Pokud chcete použít místní účet na zařízení, které už je nastavené, budete muset [zařízení znovu zablikat nebo resetovat.](hololens-recovery.md)

## <a name="setting-up-users"></a>Nastavení uživatelů

Existují dva způsoby, jak nastavit nového uživatele na HoloLens. nejběžnějším způsobem je použití spouštěného spouštěného prostředí (OOBE) HoloLens. pokud používáte Azure Active Directory, [můžou se k přihlášení](#setting-up-multi-user-support-azure-ad-only) pomocí přihlašovacích údajů Azure AD přihlásit i jiní uživatelé. HoloLens zařízení, která se zpočátku nastavují pomocí účtu MSA nebo místního účtu během vytváření počátečních počítačů, nebudou podporovat víc uživatelů. viz nastavení [HoloLens (1. generace)](hololens1-start.md) nebo [HoloLens 2](hololens2-start.md).

pokud k přihlášení k HoloLens používáte podnikový nebo organizační účet, HoloLens se zaregistruje v infrastruktuře IT organizace. Tento zápis umožňuje vašemu správci IT nakonfigurovat správu mobilních zařízení (MDM), aby odesílal zásady skupiny na HoloLens.

stejně jako Windows na jiných zařízeních, přihlášení během instalace vytvoří na zařízení profil uživatele. Profil uživatele ukládá aplikace a data. stejný účet taky poskytuje jednotné přihlašování pro aplikace, jako je například Edge nebo Microsoft Store, pomocí rozhraní api Windows správce účtů.

ve výchozím nastavení, stejně jako u jiných Windows 10 zařízení, se budete muset znovu přihlásit, když HoloLens restart nebo obnoví činnost z úsporného režimu. toto chování můžete změnit pomocí aplikace Nastavení, nebo můžete chování řídit pomocí zásad skupiny.

### <a name="linked-accounts"></a>Propojené účty

stejně jako v desktopové verzi Windows můžete propojit další přihlašovací údaje webového účtu s účtem HoloLens. Takové propojení usnadňuje přístup k prostředkům v aplikacích nebo v rámci aplikací (jako je úložiště) nebo ke kombinování přístupu k osobním a pracovním prostředkům. Po připojení účtu k zařízení můžete udělit oprávnění k používání zařízení pro aplikace, abyste se k jednotlivým aplikacím nemuseli přihlašovat jednotlivě.

Propojování účtů nedělí data uživatelů vytvořená v zařízení, například obrázky nebo soubory ke stažení.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Nastavení podpory více uživatelů (jenom Azure AD)

HoloLens podporuje více uživatelů ze stejného tenanta služby Azure AD. Pokud chcete tuto funkci použít, musíte k nastavení zařízení použít účet, který patří do vaší organizace. Následně se ostatní uživatelé ze stejného tenanta můžou přihlásit k zařízení z přihlašovací obrazovky nebo klepnutím na dlaždici uživatele na panelu Start. V jednom okamžiku může být přihlášen pouze jeden uživatel. když se uživatel přihlásí, HoloLens odhlásí předchozího uživatele. 

>[!IMPORTANT]
> První uživatel v zařízení je považován za vlastníka zařízení, s výjimkou případu, kdy se služba Azure AD JOIN týká vlastníků [zařízení](security-adminless-os.md#device-owner).

Všichni uživatelé můžou používat aplikace nainstalované na zařízení. Každý uživatel ale má vlastní data a předvolby aplikace. Odebráním aplikace ze zařízení ji odeberete pro všechny uživatele.  

Zařízení nastavená s účty Azure AD neumožní přihlášení k zařízení pomocí účtu Microsoft. Všechny následující účty musí být účty Azure AD ze stejného tenanta jako zařízení. K aplikacím, které ji podporují (například Microsoft Store), se můžete stále [přihlašovat pomocí účtu Microsoft](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) . Pokud chcete změnit použití účtů Azure AD na účty Microsoft pro přihlášení k zařízení, musíte [zařízení znovu zablikat](hololens-recovery.md#clean-reflash-the-device).

> [!NOTE]
> **HoloLens (1. generace)** začala podporovat více uživatelů Azure AD v [Windows 10 aktualizace z dubna 2018](/windows/mixed-reality/release-notes-april-2018) jako součást [Windows Holographic for Business](hololens-upgrade-enterprise.md).

### <a name="multiple-users-listed-on-sign-in-screen"></a>Více uživatelů uvedených na přihlašovací obrazovce

Předchozí přihlašovací obrazovka zobrazila pouze posledního přihlášeného uživatele a vstupní bod jiného uživatele. Dostali jsme zpětnou vazbu od zákazníků, pokud se k zařízení přihlásilo více uživatelů. Pořád se vyžadovalo, aby znovu zapisovali své uživatelské jméno atd.

v [Windows holografické 21H1 verze](hololens-release-notes.md#windows-holographic-version-21h1)se při výběru **dalšího uživatele** , který se nachází napravo od pole pro zadání kódu PIN, zobrazuje na přihlašovací obrazovce více uživatelů, kteří se k zařízení dříve přihlásili. to umožňuje uživatelům vybrat svůj profil uživatele a pak se přihlašovat pomocí svých Windows Hello přihlašovacích údajů. Do zařízení můžete přidat nového uživatele pomocí tlačítka **Přidat účet** na stránce ostatní uživatelé.

Když v nabídce ostatní uživatelé přejdete na tlačítko ostatní uživatelé, zobrazí se poslední uživatel přihlášený k zařízení. Kliknutím na toto tlačítko se vrátíte na přihlašovací obrazovku pro tohoto uživatele.

![Výchozí přihlašovací obrazovka](./images/multiusers1.jpg)

<br>

![Přihlašovací obrazovka jiní uživatelé](./images/multiusers2.jpg)

## <a name="removing-users"></a>Odebírání uživatelů

uživatele můžete ze zařízení odebrat tak, že kliknete na **Nastavení**  >  **účty**  >  **jiní lidé**. Tato akce také uvolní místo tím, že se ze zařízení odeberou všechna data aplikací daného uživatele.  

## <a name="using-single-sign-on-within-an-app"></a>Použití jednotného přihlašování v rámci aplikace

jako vývojář aplikací můžete využít výhod propojených identit v HoloLens pomocí [rozhraní api Windows správce účtů](/uwp/api/Windows.Security.Authentication.Web.Core), stejně jako na jiných Windows zařízeních. některé ukázky kódu pro tato rozhraní api jsou k dispozici v GitHub: [ukázka správy webových účtů](https://go.microsoft.com/fwlink/p/?LinkId=620621).

Případné přerušení účtu, ke kterému může dojít, například vyžádání souhlasu uživatele pro informace o účtu, dvojúrovňové ověřování a tak dále, musí být zpracovány, když aplikace požaduje ověřovací token.

Pokud vaše aplikace vyžaduje konkrétní typ účtu, který nebyl dříve propojen, může aplikace požádat systém, aby vyzvat uživatele, aby ho přidal. Tato žádost aktivuje podokno nastavení účtu, které se spustí jako modální dítě vaší aplikace. V případě 2D aplikací se toto okno vykreslí přímo přes střed vaší aplikace. V případě aplikací Unity tato žádost krátce převezme uživatele z vaší holografické aplikace, aby vygenerovalo podřízené okno. Informace o přizpůsobení příkazů a akcí v tomto podokně naleznete v tématu [Třída WebAccountCommand](/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand).

## <a name="enterprise-and-other-authentication"></a>Enterprise a jiné ověřování

pokud vaše aplikace používá jiné typy ověřování, jako je například protokol NTLM, Basic nebo Kerberos, můžete k shromažďování, zpracování a ukládání přihlašovacích údajů uživatele použít [uživatelské rozhraní Windows přihlašovací údaje](/uwp/api/Windows.Security.Credentials.UI) . Uživatelské prostředí shromažďování těchto přihlašovacích údajů se velmi podobá jiným cloudovým přerušením účtů a zobrazuje se jako podřízená aplikace na 2D aplikaci nebo krátce pozastaví aplikaci Unity, aby zobrazovala uživatelské rozhraní.

## <a name="deprecated-apis"></a>Zastaralá rozhraní API

jedním ze způsobů, jak se vývoj pro HoloLens liší od vývoje pro Desktop, je to, že rozhraní [OnlineIDAuthenticator](/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) API není plně podporované. I když rozhraní API vrátí token, pokud je primární účet v dobrém umístění, přerušení, jako jsou ty popsané v tomto článku, nezobrazují žádné uživatelské rozhraní pro uživatele a nepodaří se mu správně ověřit účet.

## <a name="frequently-asked-questions"></a>Nejčastější dotazy

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>je Windows Hello pro firmy podporovaná v HoloLens (1. generace)?

Windows Hello pro firmy (která podporuje používání kódu PIN pro přihlášení) se podporuje pro HoloLens (1. generace). povolení přihlášení PIN Windows Hello pro firmy v HoloLens:

1. zařízení HoloLens musí být [spravované pomocí MDM](hololens-enroll-mdm.md).
1. pro zařízení musíte povolit Windows Hello pro firmy. ([Viz pokyny pro Microsoft Intune.](/intune/windows-hello))
1. na HoloLens může uživatel pomocí   >  **možností přihlášení** Nastavení  >  **přidat kód** pin a nastavit pin kód.

> [!NOTE]
> uživatelé, kteří se přihlásí pomocí účet Microsoft, můžou nastavit pin kód v **Nastavení**  >  **možnosti přihlašování**  >  **přidat pin**. tento PIN kód je přidružený k [Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello)místo [Windows Hello pro firmy](/windows/security/identity-protection/hello-for-business/hello-overview).

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>jak se v HoloLens 2 implementuje biometrické ověřování Iris?

HoloLens 2 podporuje ověřování Iris. Iris je založen na technologii Windows Hello a je podporována pro použití s účty Azure Active Directory a Microsoft. Iris je implementováno stejným způsobem jako jiné technologie Windows Hello a dosahuje [zabezpečení biometrikae daleko 1/100 tisíc](/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise#has-microsoft-set-any-device-requirements-for-windows-hello).

další informace najdete v článku o [biometrických požadavcích a specifikacích pro Windows Hello](/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) . přečtěte si další informace o [Windows Hello](/windows-hardware/design/device-experiences/windows-hello) a [Windows Hello pro firmy](/windows/security/identity-protection/hello-for-business/hello-identity-verification). 

### <a name="where-is-iris-biometric-information-stored"></a>Kam se ukládají informace o biometrice Iris?

informace o biometrice Iris se ukládají místně na každé HoloLens podle [Windows Hello specifikace](/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise#where-is-windows-hello-data-stored). Není sdílený a je chráněn dvěma vrstvami šifrování. Není přístupná ostatním uživatelům, ani správci, protože na HoloLens neexistuje žádný účet správce.

### <a name="do-i-have-to-use-iris-authentication"></a>Musím používat ověřování Iris?
Ne, tento krok můžete přeskočit během instalace. 

![Nastavení Iris](./images/setup-iris.png)

HoloLens 2 poskytuje mnoho různých možností ověřování, včetně klíčů zabezpečení FIDO2.

### <a name="can-iris-information-be-removed-from-the-hololens"></a>Můžu z HoloLens odebrat informace Iris?
ano, můžete ho ručně odebrat v Nastavení.


### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>Jak má typ účtu vliv na chování přihlášení?

Pokud použijete zásady pro přihlášení, zásada se vždycky dodržuje. Pokud se nepoužije žádná zásada pro přihlášení, jedná se o výchozí chování každého typu účtu:

- **Azure AD**: požádá o ověření ve výchozím nastavení a dá se nakonfigurovat **Nastavení** , aby už nevyžadovaly ověřování.
- **Účet Microsoft**: chování zámku je jiné, což umožňuje automatické odemknutí, ale při restartování se pořád vyžaduje přihlášení k ověřování.
- **místní účet**: vždy žádá o ověření ve formě hesla, takže se nedá konfigurovat v **Nastavení**

> [!NOTE]
> Časovače nečinnosti se aktuálně nepodporují, což znamená, že zásady **AllowIdleReturnWithoutPassword** se respektují jenom v případě, že zařízení přejde do úsporného režimu.

## <a name="additional-resources"></a>Další zdroje informací

další informace o ochraně identity uživatelů a ověřování najdete v [dokumentaci k zabezpečení a identitě pro Windows 10](/windows/security/identity-protection/).

Další informace o nastavení infrastruktury hybridní identity najdete v [dokumentaci k Azure Hybrid identity](/azure/active-directory/hybrid/).
