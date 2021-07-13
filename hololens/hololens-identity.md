---
title: Správa identity uživatele a přihlašování pro HoloLens
description: Zjistěte, jak spravovat identitu uživatele, podporu více uživatelů, zabezpečení, podnikové ověřování a přihlašování pro HoloLens zařízení.
keywords: HoloLens, user, account, AAD, Azure AD, adfs, microsoft account, msa, credentials, reference
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
ms.openlocfilehash: 4d959d99b65085aea2a776725abdb36e27b43b81
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640385"
---
# <a name="manage-user-identity-and-sign-in-for-hololens"></a>Správa identity uživatele a přihlašování pro HoloLens

> [!NOTE]
> Tento článek je technickým referencem pro IT profesionály a nadšence do technologií. Pokud hledáte pokyny HoloLens, přečtěte si o nastavení[HoloLens (1. generace)](hololens1-start.md)nebo Nastavení HoloLens[2.](hololens2-start.md)

Stejně jako Windows zařízení HoloLens vždy funguje v kontextu uživatele. Vždy existuje identita uživatele. HoloLens s identitou zachází téměř stejně jako s jinými Windows 10 zařízeními. Tento článek obsahuje referenční informace o identitě v HoloLens a zaměřuje se na to, HoloLens se liší od ostatních Windows 10 zařízení.

HoloLens podporuje několik druhů identit uživatelů. K přihlášení můžete použít jeden nebo více uživatelských účtů. Tady je přehled typů identit a možností ověřování v HoloLens:

| Typ identity | Účty na zařízení | Možnosti ověřování |
| --- | --- | --- |
| [Azure Active Directory](/azure/active-directory/)<sup>1</sup>  | 64 | <ul><li>Poskytovatel webových přihlašovacích údajů Azure</li><li>Azure Authenticator App</li><li>Biometrika (Iris) &ndash; HoloLens 2<sup></sup> </li><li>Pin &ndash; je volitelný HoloLens (1. generace) vyžadované pro HoloLens 2.</li><li>Heslo</li></ul> |
| [Účet Microsoft (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts) | 1 | <ul><li>Biometrické údaje (Iris) &ndash; HoloLens 2</li><li>Pin &ndash; je volitelný HoloLens (1. generace) vyžadované pro HoloLens 2.</li><li>Heslo</li></ul> |
| [Místní účet](/windows/security/identity-protection/access-control/local-accounts) | 1 | Heslo |

Účty připojené ke cloudu (Azure AD a MSA) nabízejí více funkcí, protože mohou využívat služby Azure.  
> [!IMPORTANT]
> 1 – Azure AD Premium se k zařízení nevyžaduje přihlášení. Vyžaduje se ale pro další funkce cloudového nasazení s nízkými funkcemi, jako je automatická registrace a Autopilot.

> [!NOTE]
> 2 – I když zařízení HoloLens 2 podporuje až 64 účtů Azure AD, do ověřování Iris se může zaregistrovat jenom 10 z těchto účtů. To je v souladu s dalšími [možnostmi biometrického ověřování pro Windows Hello pro firmy.](/windows/security/identity-protection/hello-for-business/hello-faq#how-many-users-can-enroll-for-windows-hello-for-business-on-a-single-windows-10-computer)

## <a name="setting-up-users"></a>Nastavení uživatelů

Nejběžnějším způsobem, jak nastavit nového uživatele, je HoloLens prostředí při svém provozu. Během instalace HoloLens uživatele k přihlášení pomocí účtu, který chce na zařízení používat. Tento účet může být uživatelský účet Microsoft nebo podnikový účet nakonfigurovaný v Azure. Viz Nastavení HoloLens [(1. generace)](hololens1-start.md) [nebo HoloLens 2.](hololens2-start.md)

Podobně Windows na jiných zařízeních vytvoří přihlášení během instalace na zařízení profil uživatele. Profil uživatele ukládá aplikace a data. Stejný účet také poskytuje jednotné přihlašování pro aplikace, jako je Edge nebo Microsoft Store, pomocí rozhraní API správce Windows účtu.  

Pokud se k přihlášení k účtu organizace nebo organizace HoloLens, HoloLens se zaregistruje v infrastruktuře IT organizace. Tato registrace umožňuje správci IT nakonfigurovat Mobile Správa zařízení (MDM) tak, aby odesílala zásady skupiny do HoloLens.

Stejně jako u jiných zařízení Windows 10 se budete muset při restartování nebo obnovení z pohotovostního HoloLens znovu přihlásit. Ke změně tohoto Nastavení můžete použít aplikaci pro správu nebo toto chování můžete řídit pomocí zásad skupiny.

### <a name="linked-accounts"></a>Propojené účty

Stejně jako v desktopové verzi Windows můžete propojit další přihlašovací údaje k webovému účtu HoloLens účtu. Toto propojení usnadňuje přístup k prostředkům v aplikacích nebo v rámci aplikací (jako je Store) nebo kombinování přístupu k osobním a pracovním prostředkům. Po připojení účtu k zařízení můžete aplikacím udělit oprávnění k používání zařízení, abyste se k jednotlivým aplikacím nechcete přihlašovat jednotlivě.

Propojení účtů neod odděluje uživatelská data vytvořená v zařízení, jako jsou obrázky nebo soubory ke stažení.  

### <a name="setting-up-multi-user-support-azure-ad-only"></a>Nastavení podpory pro více uživatelů (jenom Azure AD)

HoloLens podporuje více uživatelů ze stejného tenanta Azure AD. Pokud chcete tuto funkci použít, musíte k nastavení zařízení použít účet, který patří do vaší organizace. Další uživatelé ze stejného tenanta se k zařízení mohou přihlásit z přihlašovací obrazovky nebo klepnutím na dlaždici uživatele na panelu Start. Současně může být přihlášen pouze jeden uživatel. Když se uživatel přihlásí, HoloLens předchozího uživatele odsoudí. První uživatel v zařízení je považován za vlastníka zařízení, s výjimkou případu připojení ke službě Azure AD. Další informace o vlastníkovi [zařízení.](security-adminless-os.md#device-owner)

Všichni uživatelé mohou používat aplikace nainstalované na zařízení. Každý uživatel ale má svá vlastní data a předvolby aplikace. Odebráním aplikace ze zařízení ji odeberete pro všechny uživatele.  

Zařízení nastavená pomocí účtů Azure AD neumožňují přihlášení k zařízení pomocí účtu Microsoft. Všechny následné použité účty musí být účty Azure AD ze stejného tenanta jako zařízení. Stále se můžete [přihlásit pomocí účtu Microsoft k aplikacím,](hololens-identity.md#setting-up-multi-user-support-azure-ad-only) které ho podporují (například Microsoft Store). Pokud chcete změnit používání účtů Azure AD na účty Microsoft pro přihlášení k zařízení, musíte zařízení [odkazovat na](hololens-recovery.md#clean-reflash-the-device).

> [!NOTE]
> **HoloLens (1. generace)** začala podporovat více uživatelů Azure AD v [aktualizaci Windows 10 dubna 2018](/windows/mixed-reality/release-notes-april-2018) v [rámci Windows Holographic for Business](hololens-upgrade-enterprise.md).

### <a name="multiple-users-listed-on-sign-in-screen"></a>Více uživatelů uvedených na přihlašovací obrazovce

Dříve se na obrazovce Přihlásit zobrazí jenom naposledy přihlášený uživatel a také vstupní bod Jiný uživatel. Dostali jsme zpětnou vazbu od zákazníků, že to nestačí, pokud se k zařízení přihlásilo více uživatelů. Stále se vyžadovalo, aby znovu zadat své uživatelské jméno atd.

Když v Windows Holographic verze [21H1](hololens-release-notes.md#windows-holographic-version-21h1)vyberete  Jiný uživatel, který se nachází napravo od pole pro zadání KÓDU PIN, na přihlašovací obrazovce se zobrazí několik uživatelů, kteří se k zařízení už přihlásili. To umožňuje uživatelům vybrat svůj profil uživatele a pak se přihlásit pomocí svých přihlašovacích Windows Hello uživatele. Nového uživatele můžete do zařízení přidat také z této stránky Ostatní uživatelé pomocí **tlačítka Přidat** účet.

V nabídce Ostatní uživatelé se na tlačítku Ostatní uživatelé zobrazí poslední uživatel přihlášený k zařízení. Výběrem tohoto tlačítka se vrátíte na přihlašovací obrazovku tohoto uživatele.

![Výchozí přihlašovací obrazovka](./images/multiusers1.jpg)

<br>

![Přihlašovací obrazovka – ostatní uživatelé](./images/multiusers2.jpg)

## <a name="removing-users"></a>Odebírání uživatelů

Uživatele ze zařízení můžete odebrat tak, že v **Nastavení**  >  **Účty**  >  **Ostatní lidé**. Tato akce také získá místo odebráním všech dat aplikace tohoto uživatele ze zařízení.  

## <a name="using-single-sign-on-within-an-app"></a>Použití jednotného přihlašování v rámci aplikace

Jako vývojář aplikací můžete využívat propojené identity ve službě HoloLens pomocí rozhraní API Windows [Account Manageru](/uwp/api/Windows.Security.Authentication.Web.Core), stejně jako na jiných Windows zařízeních. Některé ukázky kódu pro tato rozhraní API jsou k dispozici GitHub: [Ukázka správy webových účtů](https://go.microsoft.com/fwlink/p/?LinkId=620621).

Jakákoli přerušení účtu, ke kterým může dojít, například vyžádání souhlasu uživatele s informacemi o účtu, dvojfaktorové ověřování atd., musí být zpracována, když aplikace požádá o ověřovací token.

Pokud vaše aplikace vyžaduje konkrétní typ účtu, který ještě nebyl propojený, může aplikace požádat systém, aby uživatele požádal o jeho přidání. Tento požadavek aktivuje podokno nastavení účtu, aby se spouštěl jako modální podřízený objekt vaší aplikace. U 2D aplikací se toto okno vykreslí přímo přes střed vaší aplikace. U aplikací Unity tato žádost uživatele krátce vyvede z holografické aplikace a vykreslí podřízené okno. Informace o přizpůsobení příkazů a akcí v tomto podokně najdete v tématu [WebAccountCommand – třída](/uwp/api/Windows.UI.ApplicationSettings.WebAccountCommand).

## <a name="enterprise-and-other-authentication"></a>Enterprise a další ověřování

Pokud vaše aplikace používá jiné typy ověřování, například NTLM, Basic nebo Kerberos, můžete uživatelské [rozhraní Windows přihlašovacích](/uwp/api/Windows.Security.Credentials.UI) údajů použít ke shromažďování, zpracování Windows ukládání přihlašovacích údajů uživatele. Uživatelské prostředí pro shromažďování těchto přihlašovacích údajů je velmi podobné jiným přerušením účtu řízeným cloudem a zobrazuje se jako podřízené aplikace nad vaší 2D aplikací nebo krátce pozastaví aplikaci Unity, aby bylo možné zobrazit uživatelské rozhraní.

## <a name="deprecated-apis"></a>Zastaralá rozhraní API

Jedním ze způsobu, jak se vývoj HoloLens desktopových aplikací liší, je to, že rozhraní API [OnlineIDAuthenticator](/uwp/api/Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator) není plně podporováno. I když rozhraní API vrátí token, pokud je primární účet v pořádku, přerušení, jako jsou přerušení popsaná v tomto článku, nezobrazují uživatelské rozhraní pro uživatele a nedaří se správně ověřit účet.

## <a name="frequently-asked-questions"></a>Nejčastější dotazy

### <a name="is-windows-hello-for-business-supported-on-hololens-1st-gen"></a>Podporuje Windows Hello pro firmy HoloLens (1. generace)?

Windows Hello pro firmy (která podporuje použití kódu PIN pro přihlášení) je podporovaná pro HoloLens (1. generace). povolení přihlášení PIN Windows Hello pro firmy v HoloLens:

1. zařízení HoloLens musí být [spravované pomocí MDM](hololens-enroll-mdm.md).
1. pro zařízení musíte povolit Windows Hello pro firmy. ([Viz pokyny pro Microsoft Intune.](/intune/windows-hello))
1. na HoloLens může uživatel pomocí   >  **možností přihlášení** Nastavení  >  **přidat kód** pin a nastavit pin kód.

> [!NOTE]
> uživatelé, kteří se přihlásí pomocí účet Microsoft, můžou nastavit pin kód v **Nastavení**  >  **možnosti přihlašování**  >  **přidat pin**. tento PIN kód je přidružený k [Windows Hello](https://support.microsoft.com/help/17215/windows-10-what-is-hello)místo [Windows Hello pro firmy](/windows/security/identity-protection/hello-for-business/hello-overview).

### <a name="how-is-iris-biometric-authentication-implemented-on-hololens-2"></a>jak se v HoloLens 2 implementuje biometrické ověřování Iris?

HoloLens 2 podporuje ověřování Iris. Iris je založen na technologii Windows Hello a je podporována pro použití s účty Azure Active Directory a Microsoft. Iris je implementováno stejným způsobem jako jiné technologie Windows Hello a dosahuje zabezpečení biometrikae daleko 1/100 tisíc.

další informace najdete v článku o [biometrických požadavcích a specifikacích pro Windows Hello](/windows-hardware/design/device-experiences/windows-hello-biometric-requirements) . přečtěte si další informace o [Windows Hello](/windows-hardware/design/device-experiences/windows-hello) a [Windows Hello pro firmy](/windows/security/identity-protection/hello-for-business/hello-identity-verification). 

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
