---
title: Omezení použití hesla
description: omezení použití hesla pro HoloLens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: zabezpečení, HoloLens, omezení používání hesla, heslo, heslo pro HoloLens, přihlášení, přihlášení, Windows Hello, Hello, správce účtů systému Windows, FIDO2 přihlášení, FIDO 2, operace WEBAUTHN, místní účet, zabezpečení HoloLens
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 24cd9b81d0d99afaa0479787b846b423310c6739
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427602"
---
# <a name="limiting-password-use"></a>Omezení použití hesla

Většina počítačových systémů dnes využívá přihlašovací údaje uživatele jako základu pro zabezpečení, které je zabezpečí na základě opakovaně použitelných hesel vytvořených uživatelem. To má za následek to, že hesla se také staly Nejběžnější příčinou ohrožení bezpečnosti a porušení zabezpečení účtů. Příkladem je, že hesla se můžou zachytit při přenosu nebo odcizení ze serveru (útokem phishing nebo proti postřiku hesla) a ohrozit tak přístup k uživatelskému účtu.

pro zvýšení zabezpečení a ochrany účtů má HoloLens 2 možnost povolit pro přihlášení k zařízení silné přihlašovací údaje s heslem bez hesla (včetně Windows Hello) a nabízí bezproblémový přístup ke cloudu microsoftu.

## <a name="signing-in-from-another-device"></a>Přihlaste se z jiného zařízení

HoloLens 2 nabízí možnosti přihlášení ke vzdálenému zařízení pro Azure Active Directory pracovní účty během počátečního nastavení zařízení a přihlašování uživatelů, aby se snížila nutnost psaní složitých hesel a minimalizovala potřeba hesla jako přihlašovací údaje. uživatelé a organizace, kteří používají čipové karty k ověřování, mají potíže s používáním těchto přihlašovacích údajů na zařízeních, jako jsou HoloLens 2, a často můžou vytvářet složité systémy a nákladné procesy pro řešení tohoto problému. k vyřešení tohoto problému Azure AD nabízí dvě možnosti pro přihlášení bez hesla HoloLens 2.

metoda prvního ověřování spoléhá na nové funkce v aplikaci Microsoft Authenticator, aby poskytovaly ověřování založené na klíčích, které povoluje přihlašovací údaje uživatele vázané na zařízení. po povolení u tenanta správcem se uživatelům zobrazí zpráva během HoloLens nastavení zařízení, která jim sdělí, že chtějí klepnout na číslo ve své aplikaci. musí se pak shodovat s číslem v ověřovací aplikaci, zvolit schválit, zadat jejich PIN kód nebo biometriku a dokončit ověřování pro jejich nastavení HoloLens, aby bylo možné pokračovat. Tato informace je podrobněji popsána v tématu [přihlášení k neheslům](/azure/active-directory/authentication/howto-authentication-passwordless-phone).

Druhým je tok kódu zařízení, který je pro uživatele intuitivní a nevyžaduje žádnou další infrastrukturu.  toto vzdálené přihlašovací chování spoléhá na jiné důvěryhodné zařízení, které podporuje preferovaný ověřovací mechanismus organizace a po jeho dokončení se tokeny vydávají zpátky do HoloLens, aby se dokončilo přihlášení nebo nastavení zařízení. Postup v tomto toku:

  1. Uživatel prochází počátečním nastavením zařízení nebo toky přihlášení na začátku se zobrazí s odkazem přihlásit z jiného zařízení a klepne na něj. Tím se spustí relace vzdáleného přihlášení.
  1. Uživateli se pak zobrazí stránka s dotazem, která obsahuje krátký identifikátor URI ( [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin) ), který odkazuje na koncový bod ověřování zařízení služby tokenů zabezpečení Azure AD. Uživatel je také zobrazen s jednorázovým kódem, který je bezpečně generován v cloudu a má maximální dobu 15 minut. Společně s generováním kódu vytvoří služba Azure AD zašifrovanou relaci při zahájení žádosti o vzdálené přihlášení v předchozím kroku a společně se k schválení žádosti o vzdálené přihlášení používá identifikátor URI a kód.
  1. uživatel pak přejde k identifikátoru URI z jiného zařízení a zobrazí se výzva k zadání kódu zobrazeného na jejich zařízení HoloLens 2.
  1. jakmile uživatel zadá kód, Azure AD STS zobrazí stránku s informacemi o zařízení uživatele HoloLens 2, které aktivovalo požadavek na vzdálené přihlášení a požadoval generování kódu. Uživatel se pak vyzve k potvrzení, aby nedocházelo k útokům phishing.
  1. Pokud se uživatel rozhodne pokračovat v přihlašování k zobrazené aplikaci, služba Azure AD STS vyzve uživatele k zadání přihlašovacích údajů. Po úspěšném ověření služba Azure AD STS aktualizuje vzdálenou relaci uloženou v mezipaměti jako schválenou společně s autorizačním kódem.
  1. nakonec stránka pro dotazování na zařízení HoloLens 2 uživatele obdrží odpověď autorizovaný od Azure AD a pokračuje v ověřování uživatelského kódu, přidruženého uloženého autorizačního kódu a vygeneruje tokeny OAuth, jak je požadováno k dokončení nastavení zařízení. Vytvořený ověřovací token je platný 1 hodina a obnovovací token má životnost 90 dní.

Algoritmy pro generování kódu a šifrování použité v tomto toku jsou kompatibilní se standardem FIPS. zařízení HoloLens 2 využívají čip TPM k zabezpečení klíčů zařízení a šifrování tokenů generovaných po ověření uživatele pomocí klíčů chráněných hardwarem. další informace o zabezpečení tokenu na HoloLens 2 se sdílí v [tom, co je primární obnovovací token (PRT)](/azure/active-directory/devices/concept-primary-refresh-token).

## <a name="device-sign-in-with-windows-hello"></a>Přihlášení zařízení pomocí Windows Hello

[Windows Hello](/windows/security/identity-protection/hello-for-business/hello-identity-verification) nabízí možnosti bez hesla vytvořené přímo do operačního systému, které uživatelům umožňují přihlašovat se k zařízení pomocí Iris nebo PIN kódu. KÓD PIN je vždy k dispozici jako přihlašovací údaje a je vyžadován pro nastavení zařízení, zatímco Iris je volitelné a může být vynecháno. uživatelé se mohou přihlašovat k HoloLens zařízení pomocí osobního účet Microsoft nebo [Azure Active Directory pracovní účet *bez* zadání hesla](/azure/active-directory/authentication/concept-authentication-passwordless). možnosti, jako jsou například tyto, nabízejí uživatelům rychlý a zabezpečený přístup k jejich úplným Windowsm, aplikacím, datům, webům a službám. Strategii Microsoftu pro prostředí, která nejsou v hesle, je podrobně popsána zde.

když se vytvoří přihlašovací údaje Windows Hello, vytvoří se důvěryhodný vztah s poskytovatelem identity a vytvoří se asymetrický pár klíčů pro ověřování. Windows Hello gesto (například iris nebo PIN) poskytuje entropii k dešifrování privátního klíče, který je zajištěný čipem TPM (Trusted Platform Module) zařízení. Tento privátní klíč se pak použije k podepisování požadavků odesílaných ověřovacímu serveru a po úspěšném ověření. uživateli se udělí přístup k e-mailu, obrázkům a dalším nastavením účtu.

Další informace najdete v následujících infografika:

  ![Windows Hello Přihlaste se.](images/security-hello-sign-in.png)
  
Na obrázku uvedeném výše si všimněte, že hodnota nonce je "Number jedenkrát" a je náhodné nebo částečně vygenerované číslo. po nastavení Windows Hello biometriky nebo PIN kódu PIN nikdy nezůstane zařízení, na kterém je zřízené. i v případě, že je kód PIN Windows Hello uživatele odcizen, například útok útokem phishing, je [bez fyzického zařízení uživatele nepoužitelné](/windows/security/identity-protection/hello-for-business/hello-why-pin-is-better-than-password).

pro zvýšení zabezpečení jsou přihlašovací údaje Windows Hello chráněny čipem TPM (Trusted Platform Module), aby přihlašovací údaje byly odolné proti chybám a byly doplněny ochranou před únikem informací proti více nesprávným položkám a ochraně před škodlivým softwarem, aby nedocházelo k expozici. Pokud chcete získat další informace o jednom Sign-On (SSO), přečtěte si tento [Přehled metod jednotného přihlašování](/azure/active-directory/manage-apps/what-is-single-sign-on).

Ověřování Iris se vrátí k PIN kódu. Aby bylo možné na zařízení nastavit nový PIN kód (silné ověřovatele), musí se uživatel nedávno dodávat prostřednictvím [vícefaktorového ověřování (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks) , aby mohl proces dokončit.

## <a name="single-sign-on-with-web-account-manager"></a>Jednotné přihlašování pomocí Správce účtů webu

Jednotné přihlašování (SSO) umožňuje uživatelům bez hesla přihlašovat se k zařízení pomocí osobního účtu uživatele nebo svého pracovního nebo školního účtu. Uživatel je automaticky autorizován pomocí jednotného přihlašování na všech integrovaných aplikacích a službách prostřednictvím [rozhraní API Správce účtů webu](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true).

Po přidání identity přes jednu aplikaci může s souhlasem uživatele být dostupná pro všechny aplikace a služby, které využívají integraci na úrovni systému. Tím se výrazně omezuje režie v přihlašování k aplikacím a poskytuje uživatelům bezproblémové prostředí identity.

Další informace o implementaci rozhraní API správce webového účtu najdete v [implementace rozhraní API správce webového účtu](/windows/uwp/security/web-account-manager).

  ![Rozhraní API pro zabezpečení](images/security-api-img.png)
  
Pro sady aplikací s požadavky na specializované ověřování je rozhraní správce účtů webu (WAM) rozšiřitelné pro vlastní zprostředkovatele identity. uživatelé můžou stáhnout vlastního zprostředkovatele identity, který se zabalí jako aplikace Univerzální platforma Windows (UWP) z Microsoft Store a povolit jednotné přihlašování v jiných aplikacích integrovaných s tímto poskytovatelem identity.

Další informace o implementaci vlastních zprostředkovatelů identity WAM najdete v tématu [vlastní Reference k rozhraní API zprostředkovatele identity poskytovatele](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true)služby WAM.

## <a name="windows-hello-and-fido2-sign-in-with-webauthn"></a>Windows Hello a FIDO2 přihlášení pomocí operace WebAuthn

HoloLens 2 může využít přihlašovací údaje uživatele bez hesla (například Windows Hello nebo FIDO2 klíče zabezpečení) k bezpečnému přihlášení na webu prostřednictvím Microsoft Edge a na weby, které podporují funkci WebAuthn. FIDO2 umožňuje uživatelským přihlašovacím údajům využít k ověření online služby k ověřování na základě standardů.

> [!Note]
> Specifikace [WebAuthn](https://www.w3.org/TR/webauthn/) a FIDO2 [CTAP2](https://fidoalliance.org/specs/fido-v2.0-ps-20190130/fido-client-to-authenticator-protocol-v2.0-ps-20190130.html) jsou implementovány do služeb. Podepsaná metadata určená parametrem WebAuthn a FIDO2 poskytují informace – například zda byl uživatel přítomen a ověřuje ověřování prostřednictvím místního gesta.

stejně jako u Windows Hello, když uživatel vytvoří a zaregistruje přihlašovací údaje FIDO2, zařízení (HoloLens 2 nebo bezpečnostní klíč FIDO2) vygeneruje na zařízení soukromý a veřejný klíč. Privátní klíč je bezpečně uložený na zařízení a dá se použít jenom po odemčení pomocí místního gesta, jako je biometrika nebo PIN. Po uložení privátního klíče se veřejný klíč pošle do systému účet Microsoft v cloudu a zaregistruje se s přidruženým uživatelským účtem.

po přihlášení pomocí účtu MSA a Azure AD pošle systém vygenerované číslo nebo datovou proměnnou do zařízení HoloLens 2 nebo FIDO2. HoloLens 2 nebo zařízení používá privátní klíč k podepsání identifikace. Podepsaná identifikace a metadata se odesílají zpátky do účet Microsoft systému a ověřují se pomocí veřejného klíče.

zařízení Windows Hello a FIDO2 implementují přihlašovací údaje na základě HoloLens zařízení, konkrétně vestavěného modulu Trusted Platform Module secure enklávy. ČIP TPM enklávy ukládá privátní klíč a vyžaduje jeho odemčení buď pomocí biometriky, nebo kódu PIN. Podobně klíč zabezpečení FIDO2 je malé externí zařízení s integrovaným zabezpečeným enklávy, které ukládá soukromý klíč a vyžaduje k jeho odemčení biometriku nebo PIN.

Obě možnosti nabízí dvojúrovňové ověřování v jednom kroku, které vyžaduje, aby se úspěšně přihlásili registrovaným zařízením a biometrickou metrikou nebo PIN. Další informace najdete v tématu silné ověřování s klíčem zabezpečení FIDO2 a s tímto postupem.

### <a name="strong-authentication-with-fido2-security-key"></a>Silné ověřování s klíčem zabezpečení FIDO2

  ![FIDO img.](images/security-fido2-whfb-smaller.png)

1. uživatel zapojuje klíč zabezpečení FIDO2 do HoloLens 2
1. Windows detekuje klíč zabezpečení FIDO2
1. HoloLens posílá žádost o ověření.
1. Azure AD odesílá zpětnou hodnoty nonce
1. Uživatel dokončí gesto pro odemknutí privátních úložišť klíčů v zabezpečeném enklávy bezpečnostního klíče.
1. FIDO2 zabezpečení podepisuje klíč hodnoty nonce pomocí privátního klíče
1. Požadavek na token PRT s podepsanou hodnotu NONCE se pošle do Azure AD.
1. Azure AD ověří klíč FIDO
1. Azure AD vrací PRT a TGT pro povolení přístupu k prostředkům.

MSA a Azure AD jsou mezi prvními předávajícími stranami, aby podporovaly ověřování bez hesla implementací operace WebAuthn.

Další informace o použití operace WebAuthn s aplikacemi a sadami SDK naleznete [v rozhraních Webauthn API pro ověřování bez hesla Windows 10](/windows/security/identity-protection/hello-for-business/webauthnapis).

HoloLens 2 podporuje bezpečnostní zařízení FIDO2, která jsou implementovaná na specifikaci a splňují požadavky uvedené v [Azure Active Directory bezpečnostní klíče FIDO2 pro přihlášení k heslům](/azure/active-directory/authentication/concept-authentication-passwordless#fido2-security-keys) , které by měly být podporované.

## <a name="local-accounts"></a>Místní účty

Pro nasazení offline režimu se dá nakonfigurovat jeden místní účet. Místní účty nejsou ve výchozím nastavení povolené a musí být nakonfigurované během zřizování zařízení. musí se přihlásit pomocí hesla a nepodporují alternativní metody ověřování (například [Windows Hello pro firmy](/windows/security/identity-protection/hello-for-business/hello-overview) nebo [Windows Hello](/windows-hardware/design/device-experiences/windows-hello)).

další podrobnosti o HoloLens uživatelských účtů najdete v [HoloLens Identity](hololens-identity.md).

Správci IT upraví, jestli má uživatel povoleno používat účet MSA pro ověřování a služby v souvislosti s Nee-maily prostřednictvím [AllowMicrosoftAccountConnection](/windows/client-management/mdm/policy-csp-accounts#accounts-allowmicrosoftaccountconnection). Zásady konfigurace hesel, zásady volnoběhu a zásady uzamčené obrazovky najdete v tématu [Zámek zařízení](/windows/client-management/mdm/policy-csp-devicelock).
