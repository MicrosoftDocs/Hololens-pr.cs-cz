---
title: Správa identity uživatele a přihlášení pro HoloLens
description: Zjistěte, jak spravovat identitu uživatele, podporu více uživatelů, zabezpečení, podnikové ověřování a přihlašování pro HoloLens zařízení.
keywords: HoloLens, user, account, AAD, Azure AD, adfs, microsoft account, msa, credentials, reference
ms.assetid: 728cfff2-81ce-4eb8-9aaa-0a3c3304660e
author: qianw211
ms.author: v-qianwen
ms.date: 8/13/2021
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: sekerawa
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: c2fd7c8ee82fbf70b9eaa2b5eee1d73e1235d8b5
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032256"
---
# <a name="manage-user-identity-and-login-for-hololens"></a>Správa identity uživatele a přihlášení pro HoloLens

> [!NOTE]
> Tento článek je technickým referencem pro IT profesionály a nadšence do technologií. Pokud hledáte pokyny HoloLens, přečtěte si o nastavení[HoloLens (1. generace)](hololens1-start.md)nebo Nastavení HoloLens[2.](hololens2-start.md)

## <a name="lets-talk-about-setting-up-user-identity-for-hololens-2"></a>Promluvme si o nastavení identity uživatele pro HoloLens 2

Stejně jako Windows zařízení HoloLens vždy funguje v kontextu uživatele. Vždy existuje identita uživatele. HoloLens s identitou zachází téměř stejným způsobem jako s Windows 10 zařízením. Přihlášení během instalace vytvoří profil uživatele v HoloLens, ve které jsou uloženy aplikace a data. Stejný účet také poskytuje jednotné přihlašování pro aplikace, jako je Edge nebo Dynamics 365 Remote Assist, pomocí rozhraní API Windows Account Manageru. 

HoloLens podporuje několik druhů identit uživatelů. Můžete zvolit kterýkoli z těchto tří typů účtů, ale důrazně doporučujeme Azure AD, protože je pro správu zařízení nejlepší. Více uživatelů podporují jenom účty Azure AD. 

| Typ identity | Účty na zařízení | Možnosti ověřování |
| --- | --- | --- |
| [Azure Active Directory](/azure/active-directory/)<sup>1</sup>  | 64 | <ul><li>Poskytovatel webových přihlašovacích údajů Azure</li><li>Azure Authenticator App</li><li>Biometrika (Iris) &ndash; HoloLens<sup></sup> 2 </li><li>Klíč zabezpečení FIDO2</li><li>Pin &ndash; je volitelný pro HoloLens (1. generace) vyžadované pro HoloLens 2.</li><li>Heslo</li></ul> |
| [Účet Microsoft (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Biometrika (Iris) &ndash; HoloLens 2</li><li>Pin &ndash; je volitelný pro HoloLens (1. generace) vyžadované pro HoloLens 2.</li><li>Heslo</li></ul> |
| [Místní účet](/windows/security/identity-protection/access-control/local-accounts)<sup>3</sup> | 1 | Heslo |

Účty připojené ke cloudu (Azure AD a MSA) nabízejí více funkcí, protože mohou využívat služby Azure.  
> [!IMPORTANT]
> 1 – Azure AD Premium se k zařízení nevyžaduje přihlášení. Vyžaduje se ale pro další funkce cloudového nasazení s nízkými funkcemi, jako je automatická registrace a Autopilot.

> [!NOTE]
> 2 – I když zařízení HoloLens 2 podporuje až 64 účtů Azure AD, do ověřování Iris se může zaregistrovat jenom 31 z těchto účtů. To je v souladu s dalšími [možnostmi biometrického ověřování pro Windows Hello pro firmy.](/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)

> [!IMPORTANT]
> 3 – Místní účet je možné nastavit na zařízení pouze prostřednictvím zřizovacího balíčku během prostředí [OOBE.](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)Později ho není možné přidat do aplikace nastavení. Pokud chcete na zařízení, které je už nastavené, použít místní účet, budete ho muset [reflashovat nebo resetovat.](hololens-recovery.md)

## <a name="setting-up-users"></a>Nastavení uživatelů

Existují dva způsoby, jak nastavit nového uživatele na HoloLens. Nejběžnějším způsobem je během HoloLens prostředí při první instalace. Pokud používáte Azure Active Directory, [jinými uživateli](#setting-up-multi-user-support-azure-ad-only) se mohou přihlásit po OOBE pomocí svých přihlašovacích údajů Azure AD. HoloLens zařízení, která jsou na začátku nastavená s účtem MSA nebo místním účtem při prvním prvním nastavení, nebudou podporovat více uživatelů. Viz Nastavení HoloLens [(1. generace)](hololens1-start.md) [nebo HoloLens 2.](hololens2-start.md)

Pokud se k přihlášení k účtu organizace nebo organizace HoloLens, HoloLens se zaregistruje v infrastruktuře IT organizace. Tato registrace umožňuje správci IT nakonfigurovat Mobile Správa zařízení (MDM) tak, aby odesílala zásady skupiny do HoloLens.

Podobně Windows na jiných zařízeních vytvoří přihlášení během instalace na zařízení profil uživatele. Profil uživatele ukládá aplikace a data. Stejný účet také poskytuje jednotné přihlašování pro aplikace, jako je Edge nebo Microsoft Store, pomocí rozhraní API správce Windows účtu.

Stejně jako u jiných zařízení Windows 10 se budete muset při restartování nebo obnovení z pohotovostního HoloLens znovu přihlásit. Ke změně tohoto chování Nastavení můžete použít aplikaci pro správu nebo je možné toto chování řídit pomocí zásad skupiny.

### <a name="linked-accounts"></a>Propojené účty

Stejně jako v desktopové verzi Windows můžete propojit přihlašovací údaje jiného webového účtu se svým HoloLens účtem. Toto propojení usnadňuje přístup k prostředkům v aplikacích nebo v rámci aplikací (jako je Store) nebo kombinuje přístup k osobním a pracovním prostředkům. Po připojení účtu k zařízení můžete aplikacím udělit oprávnění k používání zařízení, abyste se k jednotlivým aplikacím nechcete přihlašovat jednotlivě.

Propojení účtů neod odděluje uživatelská data vytvořená v zařízení, jako jsou obrázky nebo soubory ke stažení.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Nastavení podpory pro více uživatelů (jenom Azure AD)

HoloLens podporuje více uživatelů ze stejného tenanta Azure AD. Pokud chcete tuto funkci použít, musíte k nastavení zařízení použít účet, který patří do vaší organizace. Další uživatelé ze stejného tenanta se k zařízení mohou přihlásit z přihlašovací obrazovky nebo klepnutím na dlaždici uživatele na panelu Start. Současně může být přihlášen pouze jeden uživatel. Když se uživatel přihlásí, HoloLens předchozího uživatele odsoudí. 

>[!IMPORTANT]
> První uživatel v zařízení je považován za vlastníka zařízení, s výjimkou případu připojení ke službě Azure AD. Další informace o vlastníkovi [zařízení.](security-adminless-os.md#device-owner)

Všichni uživatelé mohou používat aplikace nainstalované na zařízení. Každý uživatel ale má svá vlastní data a předvolby aplikace. Odebráním aplikace ze zařízení ji odeberete pro všechny uživatele.  

Zařízení nastavená pomocí účtů Azure AD neumožňují přihlášení k zařízení pomocí účtu Microsoft. Všechny následné použité účty musí být účty Azure AD ze stejného tenanta jako zařízení. Stále se můžete [přihlásit pomocí účtu Microsoft k aplikacím,](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) které ho podporují (například Microsoft Store). Pokud chcete změnit používání účtů Azure AD na účty Microsoft pro přihlášení k zařízení, musíte zařízení [odkazovat na](hololens-recovery.md#clean-reflash-the-device).

> [!NOTE]
> **HoloLens (1. generace)** začala podporovat více uživatelů Azure AD v [aktualizaci Windows 10 dubna 2018](/windows/mixed-reality/release-notes-april-2018) v [rámci Windows Holographic for Business](hololens-upgrade-enterprise.md).

### <a name="multiple-users-are-listed-on-sign-in-screen"></a>Na přihlašovací obrazovce je uvedeno více uživatelů

Na přihlašovací obrazovce se dříve objevil jenom naposledy přihlášený uživatel a vstupní bod Jiný uživatel. Dostali jsme zpětnou vazbu od zákazníků, že pokud se k zařízení přihlásilo více uživatelů, nestačí to. Stále se vyžadovalo, aby znovu zadat své uživatelské jméno atd.

Když v Windows Holographic verze [21H1](hololens-release-notes.md#windows-holographic-version-21h1)vyberete Jiný uživatel, který se nachází napravo od pole pro zadání kódu PIN, na přihlašovací obrazovce se zobrazí několik uživatelů, kteří se k zařízení už přihlásili.  To umožňuje uživatelům vybrat svůj profil uživatele a pak se přihlásit pomocí svých Windows Hello přihlašovacích údajů. Nového uživatele můžete do zařízení přidat  také ze stránky dalších uživatelů pomocí **tlačítka Přidat** účet.

V nabídce **Ostatní uživatelé** se na **tlačítku Ostatní** uživatelé zobrazí poslední uživatel přihlášený k zařízení. Výběrem tohoto tlačítka se vrátíte na přihlašovací obrazovku tohoto uživatele.

![Výchozí přihlašovací obrazovka.](./images/multiusers1.jpg)

<br>

![Přihlašovací obrazovka jiných uživatelů.](./images/multiusers2.jpg)

## <a name="removing-users"></a>Odebírání uživatelů

Uživatele ze zařízení můžete odebrat tak, že v Nastavení   >  **Účty**  >  **Ostatní lidé**. Tato akce také získá místo odebráním všech dat aplikace tohoto uživatele ze zařízení.  

## <a name="using-single-sign-on-within-an-app"></a>Použití jednotného přihlašování v rámci aplikace

Jako vývojář aplikací můžete využívat propojené identity ve službě HoloLens pomocí rozhraní API správce účtů [Windows](/uwp/api/Windows.Security.Authentication.Web.Core)stejně jako na jiných zařízeních Windows zařízení. Některé ukázky kódu pro tato rozhraní API jsou k dispozici GitHub: [Ukázka správy webových účtů](https://go.microsoft.com/fwlink/p/?LinkId=620621).

Jakákoli přerušení účtu, ke kterým může dojít, například vyžádání souhlasu uživatele s informacemi o účtu, dvojfaktorové ověřování atd., musí být zpracována, když aplikace požádá o ověřovací token.

Pokud vaše aplikace vyžaduje konkrétní typ účtu, který ještě není propojený, může aplikace požádat systém, aby uživatele požádal o jeho přidání. Tento požadavek aktivuje podokno nastavení účtu, které se spustí jako modální podřízený objekt vaší aplikace. U 2D aplikací se toto okno vykreslí přímo přes střed vaší aplikace. U aplikací Unity tato žádost uživatele krátce vyvede z holografické aplikace a vykreslí podřízené okno. Informace o přizpůsobení příkazů a akcí v tomto podokně najdete v tématu [WebAccountCommand – třída](/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand).

## <a name="enterprise-and-other-authentication"></a>Enterprise a další ověřování

Pokud vaše aplikace používá jiné typy ověřování, například NTLM, Basic nebo Kerberos, můžete použít uživatelské rozhraní [Windows Přihlašovací údaje](/uwp/api/Windows.Security.Credentials.UI) ke shromažďování, zpracování a ukládání přihlašovacích údajů uživatele. Uživatelské prostředí pro shromažďování těchto přihlašovacích údajů se podobá jiným přerušením účtu řízeným cloudem a zobrazuje se jako podřízené aplikace nad vaší 2D aplikací nebo se krátce pozastaví aplikace Unity, aby bylo možné zobrazit uživatelské rozhraní.

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

![Nastavení Iris.](./images/setup-iris.png)

HoloLens 2 poskytuje mnoho různých možností ověřování, včetně klíčů zabezpečení FIDO2.

### <a name="can-iris-information-be-removed-from-the-hololens"></a>Můžu z HoloLens odebrat informace Iris?
ano, můžete ho ručně odebrat v Nastavení.


### <a name="how-does-the-type-of-account-affect-sign-in-behavior"></a>Jak typ účtu ovlivňuje chování při přihlašování?

Pokud použijete zásady pro přihlášení, zásada se vždycky dodržuje. Pokud se nepoužije žádná zásada pro přihlášení, jedná se o výchozí chování každého typu účtu:

- **Azure AD**: požádá o ověření ve výchozím nastavení a dá se nakonfigurovat **Nastavení** , aby už nevyžadovaly ověřování.
- **Účet Microsoft**: chování zámku je jiné, což umožňuje automatické odemknutí, ale při restartování se pořád vyžaduje přihlášení k ověřování.
- **místní účet**: vždy žádá o ověření ve formě hesla, takže se nedá konfigurovat v **Nastavení**

> [!NOTE]
> Časovače nečinnosti se aktuálně nepodporují, což znamená, že zásady **AllowIdleReturnWithoutPassword** se respektují jenom v případě, že zařízení přejde do úsporného režimu.

## <a name="additional-resources"></a>Další zdroje informací

další informace o ochraně identity uživatelů a ověřování najdete v [dokumentaci k zabezpečení a identitě pro Windows 10](/windows/security/identity-protection/).

Další informace o nastavení infrastruktury hybridní identity najdete v [dokumentaci k Azure Hybrid identity](/azure/active-directory/hybrid/).