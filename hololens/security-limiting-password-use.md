---
title: Omezení použití hesla
description: omezení použití hesla pro HoloLens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, limiting password use, password, hololens password, sign-in, signing in, windows hello, hello, windows account manager, FIDO2 sign in, FIDO 2, WEBAUTHN, local account, hololens security
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 24cd9b81d0d99afaa0479787b846b423310c6739
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036008"
---
# <a name="limiting-password-use"></a>Omezení použití hesla

Většina počítačových systémů dnes využívá přihlašovací údaje uživatelů jako základ zabezpečení, díky nimž jsou závislé na znovu použitelných a uživatelem vytvořených heslech. Výsledkem je, že hesla se také stávají nejčastější příčinou ohrožení zabezpečení účtu a porušení zabezpečení dat. Jako příklad toho je možné hesla zachytit při přenosu nebo odcizení ze serveru (útoky phishing nebo password spray) a ohrozit je, aby získala přístup k uživatelskému účtu.

Za účelem zlepšení zabezpečení a ochrany účtů má HoloLens 2 možnost povolit silné hardwarově chráněné přihlašovací údaje bez hesla (včetně Windows Hello) pro přihlašování zařízení a nabízí bezproblémový přístup ke cloudu Microsoftu.

## <a name="signing-in-from-another-device"></a>Přihlaste se z jiného zařízení

HoloLens 2 nabízí možnosti vzdáleného přihlášení zařízení pro pracovní účty Azure Active Directory během počátečního nastavení zařízení Azure Active Directory přihlašování uživatelů, aby se snížila potřeba zapisovat složitá hesla Azure Active Directory minimalizovala se potřeba hesel jako přihlašovacích údajů. Uživatelé a organizace, které k ověřování používají čipové karty, mají potíže s používáním těchto přihlašovacích údajů na zařízeních, jako je HoloLens 2, a organizace často vyvíjejí složité systémy a nákladné procesy pro řešení problému. Azure AD nabízí pro řešení tohoto problému dvě možnosti pro přihlašování bez hesla na HoloLens 2.

První metoda ověřování spoléhá na nové funkce v aplikaci Microsoft Authenticator, aby poskytovala ověřování na základě klíčů, které umožňuje přihlašovací údaje uživatele vázané na zařízení. Po povolení v tenantovi správcem se uživatelům během nastavování HoloLens zobrazí zpráva s oznámením, že mají na své aplikaci klepnout na číslo. Potom musí odpovídat číslu v ověřovací aplikaci, zvolit Schválit, zadat PIN kód nebo biometrické údaje a dokončit ověření, aby jejich HoloLens mohli pokračovat. To je podrobněji popsáno v části o přihlašování [bez hesla.](/azure/active-directory/authentication/howto-authentication-passwordless-phone)

Druhým je tok kódu zařízení, který je pro uživatele intuitivní a nevyžaduje žádnou další infrastrukturu.  Toto chování při vzdáleném přihlašování spoléhá na jiné důvěryhodné zařízení, které podporuje upřednostňovaný mechanismus ověřování organizace, a po dokončení se tokeny vystaví zpět do HoloLens pro dokončení přihlášení nebo nastavení zařízení. Postup v tomto toku je následující:

  1. Uživateli, který prochází počátečním nastavením zařízení nebo přihlášením na OOBE, se zobrazí odkaz Přihlásit se z jiného zařízení a klepne na něj. Tím se zahájí relace vzdáleného přihlášení.
  1. Uživateli se pak zobrazí stránka cyklického dotazování, která obsahuje krátký identifikátor URI ( ), který odkazuje na koncový bod ověřování zařízení služby [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin) tokenů zabezpečení (STS) Azure AD. Uživateli se také zobrazí jeden kód, který se bezpečně vygeneruje v cloudu a má maximální životnost 15 minut. Spolu s generováním kódu azure AD také vytvoří šifrovanou relaci při zahájení žádosti o vzdálené přihlášení v předchozím kroku a společně se identifikátor URI a kód používají ke schválení žádosti o vzdálené přihlášení.
  1. Uživatel pak přejde na identifikátor URI z jiného zařízení a zobrazí se výzva k zadání kódu zobrazeného na jeho zařízení HoloLens 2.
  1. Jakmile uživatel zadá kód, služba Azure AD STS zobrazí stránku s oznámením, že zařízení uživatele HoloLens 2 aktivující žádost o vzdálené přihlášení a požadované generování kódu. Uživateli se zobrazí výzva k potvrzení, aby se zabránilo útokům phishing.
  1. Pokud se uživatel rozhodne pokračovat v přihlašování k zobrazené aplikaci, služba Azure AD STS vyzve uživatele k zadání přihlašovacích údajů. Po úspěšném ověření služba Azure AD STS aktualizuje vzdálenou relaci v mezipaměti jako schválenou spolu s autorizačním kódem.
  1. Nakonec stránka cyklického dotazování na zařízení uživatele HoloLens 2 obdrží od Azure AD odpověď Autorizované a pokračuje ověřením uživatelského kódu, přidruženého uloženého autorizačního kódu a vygeneruje tokeny OAuth podle požadavku na dokončení nastavení zařízení. Vytvořený ověřovací token je platný po dobu 1 hodiny a obnovovací token má životnost 90 dnů.

Algoritmy generování kódu a šifrování použité v tomto toku jsou kompatibilní se standardem FIPS. HoloLens 2 využívají čip TPM k zabezpečení klíčů zařízení a šifrování tokenů generovaných po ověření uživatele pomocí klíčů chráněných hardwarem. Další informace o zabezpečení tokenů v HoloLens 2 najdete v článku Co je primární [obnovovací token (PRT).](/azure/active-directory/devices/concept-primary-refresh-token)

## <a name="device-sign-in-with-windows-hello"></a>Přihlášení zařízení pomocí Windows Hello

[Windows Hello](/windows/security/identity-protection/hello-for-business/hello-identity-verification) nabízí možnosti bez hesla integrované přímo do operačního systému, které uživatelům povolují přihlášení k zařízení pomocí Iris nebo PIN kódu. PIN kód je vždy k dispozici jako přihlašovací údaje a vyžaduje se pro nastavení zařízení, zatímco Iris je volitelná a může se přeskočit. Uživatelé se mohou přihlásit k HoloLens pomocí svého osobního účet Microsoft nebo Azure Active Directory účtu bez [zadání hesla.  ](/azure/active-directory/authentication/concept-authentication-passwordless) Tyto možnosti nabízejí uživatelům rychlý a zabezpečený přístup k jejich kompletnímu Windows, aplikacím, datům, webům a službám. Tady je podrobná strategie Microsoftu pro prostředí bez hesla.

Při Windows Hello přihlašovacích údajů vytvoří důvěryhodný vztah se zprostředkovatelem identity a vytvoří asymetrický pár klíčů pro ověřování. Gesto Windows Hello (například iris nebo PIN) poskytuje entropii k dešifrování privátního klíče pomocí čipu TPM (specifikace TPM (Trusted Platform Module) zařízení). Tento privátní klíč se pak použije k podepisování požadavků odeslaných na ověřovací server a po úspěšném ověření je uživateli udělen přístup k e-mailu, obrázkům a dalším nastavením účtu.

Další informace najdete v následující infografice:

  ![Windows Hello Přihlaste se.](images/security-hello-sign-in.png)
  
Na obrázku uvedeném výše si všimněte, že nonce je zkratka pro "number once" (číslo jednou) a je náhodné nebo částečně náhodné vygenerované číslo. Po nastavení Windows Hello biometrických údajů nebo přihlašovacích údajů PIN kódu se zařízení, na kterém je zřízené, nikdy neopustí. I v případě, že Windows Hello pin kód uživatele, například prostřednictvím útoku phishing, je bez fyzického zařízení uživatele [nepoužitelný.](/windows/security/identity-protection/hello-for-business/hello-why-pin-is-better-than-password)

Kvůli vyššímu zabezpečení jsou přihlašovací údaje Windows Hello chráněné čipem specifikace TPM (Trusted Platform Module) (TPM), aby byly přihlašovací údaje odolné vůči neoprávněné manipulaci, a doplněné o ochranu proti poškození několika nesprávných položek a škodlivou ochranu softwaru, která brání odhalení. Další informace o metodách jednotného Sign-On (SSO) najdete v tomto přehledu metod [jednotného přihlašování.](/azure/active-directory/manage-apps/what-is-single-sign-on)

Ověřování Iris se vrátí zpět k PIN kódu. Aby uživatel mohl v zařízení nastavit nový PIN (silný ověřovací kód), musí nedávno projít vícefaktorovým ověřováním [(MFA),](/azure/active-directory/authentication/concept-mfa-howitworks) aby mohl proces dokončit.

## <a name="single-sign-on-with-web-account-manager"></a>Jednotné přihlašování s Správce webových účtů

Jednotné přihlašování umožňuje uživatelům bez hesla přihlásit se k zařízení s využitím osobního účtu uživatele nebo jeho pracovního nebo školního účtu. Uživatel je automaticky autorizován pomocí jednotného přihlašování ve všech integrovaných aplikacích a službách [prostřednictvím Správce webových účtů API.](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true)

Jakmile je identita přidána prostřednictvím jedné aplikace, může být se souhlasem uživatele dostupná všem aplikacím a službám pomocí integrace na úrovni systému. Tím se výrazně snižuje zatížení přihlašování k aplikacím a poskytuje uživatelům bezproblémové prostředí pro identitu.

Další informace o implementaci rozhraní SPRÁVCE WEBOVÝCH ÚČTŮ API najdete v Správce webových účtů [rozhraní API.](/windows/uwp/security/web-account-manager)

  ![Rozhraní API pro zabezpečení.](images/security-api-img.png)
  
U sad aplikací se zvláštními požadavky na ověřování je Správce webových účtů (WAM) rozšiřitelná na vlastní zprostředkovatele identity. Uživatelé si mohou z webu Microsoft Store stáhnout vlastního zprostředkovatele identity zabalený jako aplikaci univerzální platformy Windows Platform (UPW), aby bylo možné jednotné přihlašování v jiných aplikacích integrovaných s tímto zprostředkovatelem identity.

Další informace o implementaci vlastních zprostředkovatelů identity WAM najdete v referenčních informacích k rozhraní [API vlastního zprostředkovatele identity WAM.](/uwp/api/Windows.Security.Authentication.Web.Provider?view=winrt-19041&preserve-view=true)

## <a name="windows-hello-and-fido2-sign-in-with-webauthn"></a>Windows Hello a FIDO2 pomocí WebAuthn

HoloLens 2 můžete použít přihlašovací údaje uživatele bez hesla (například klíče zabezpečení Windows Hello nebo FIDO2) k zabezpečenému přihlášení na webu přes Microsoft Edge a k webům, které podporují WebAuthn. FIDO2 umožňuje přihlašovacím údajům uživatelů využívat k ověřování zařízení založených na standardech online služby.

> [!Note]
> Specifikace [WebAuthn a](https://www.w3.org/TR/webauthn/) FIDO2 [CTAP2](https://fidoalliance.org/specs/fido-v2.0-ps-20190130/fido-client-to-authenticator-protocol-v2.0-ps-20190130.html) jsou implementované do služeb. Podepsaná metadata zadaná pomocí WebAuthn a FIDO2 poskytují informace ( například to, jestli byl uživatel přítomen ) a ověřuje ověřování prostřednictvím místního gestu.

Stejně jako u Windows Hello i když uživatel vytvoří a zaregistruje přihlašovací údaje FIDO2, zařízení (HoloLens 2 nebo klíč zabezpečení FIDO2) na zařízení vygeneruje privátní a veřejný klíč. Privátní klíč je bezpečně uložený v zařízení a je možné ho použít až po odemknutí pomocí místního gestu, jako je biometrika nebo PIN. Když je privátní klíč uložený, veřejný klíč se odesílá účet Microsoft systému v cloudu a zaregistrován pomocí přidruženého uživatelského účtu.

Po přihlášení pomocí účtu MSA a Azure AD systém odešle vygenerované číslo nebo datovou proměnnou do zařízení HoloLens 2 nebo FIDO2. Zařízení HoloLens 2 používá k podepsání identifikace privátní klíč. Podepsaná identifikace a metadata se odesílat zpět účet Microsoft systému a ověřovat pomocí veřejného klíče.

Windows Hello a FIDO2 implementují přihlašovací údaje na základě HoloLens zařízení, konkrétně integrované specifikace TPM (Trusted Platform Module) zabezpečené enklávy. Enkláva TPM ukládá privátní klíč a k odemknutí vyžaduje biometrii nebo PIN kód. Podobně je bezpečnostní klíč FIDO2 malé externí zařízení s integrovanou zabezpečenou enklávou, která ukládá privátní klíč a k odemknutí vyžaduje biometrii nebo PIN kód.

Obě možnosti nabízejí dvojfaktorové ověřování v jednom kroku, které k úspěšnému přihlášení vyžaduje zaregistrované zařízení i biometrické nebo PIN. Další informace najdete v následujícím obrázku a procesu silného ověřování pomocí klíče zabezpečení FIDO2.

### <a name="strong-authentication-with-fido2-security-key"></a>Silné ověřování s klíčem zabezpečení FIDO2

  ![FIDO img.](images/security-fido2-whfb-smaller.png)

1. Uživatel zapojuje klíč zabezpečení FIDO2 do HoloLens 2.
1. Windows detekuje klíč zabezpečení FIDO2
1. HoloLens odešle žádost o ověření.
1. Azure AD odesílá zpět nece.
1. Uživatel dokončí gesto pro odemknutí úložišť privátních klíčů v zabezpečené enklávě klíče zabezpečení.
1. Klíč zabezpečení FIDO2 podepíše nece privátním klíčem
1. Žádost o token PRT s podepsanou nece se odesílá do Azure AD.
1. Azure AD ověřuje klíč FIDO
1. Azure AD vrací PRT a TGT, aby byl umožněn přístup k prostředkům.

MSA a Azure AD patří mezi první předávající strany, které implementují WebAuthn a podporují ověřování bez hesla.

Další informace o používání WebAuthn s aplikacemi a/nebo sdk najdete v článku Rozhraní [API WebAuthn,](/windows/security/identity-protection/hello-for-business/webauthnapis)ve které najdete informace o ověřování bez hesla na Windows 10 .

HoloLens 2 podporuje zařízení zabezpečení FIDO2, která jsou implementovaná tak, aby byla speciovaná Azure Active Directory splňovala požadavky uvedené v části o přihlašování bez hesla – měly by se podporovat klíče zabezpečení [FIDO2.](/azure/active-directory/authentication/concept-authentication-passwordless#fido2-security-keys)

## <a name="local-accounts"></a>Místní účty

Pro nasazení v offline režimu je možné nakonfigurovat jeden místní účet. Místní účty nejsou ve výchozím nastavení povolené a musí se nakonfigurovat během zřizování zařízení. Musí se přihlásit pomocí hesla a nepodporují alternativní metody ověřování (například [Windows Hello pro](/windows/security/identity-protection/hello-for-business/hello-overview) firmy [nebo Windows Hello](/windows-hardware/design/device-experiences/windows-hello)).

Další podrobnosti o HoloLens uživatelských účtech najdete na HoloLens [Identity.](hololens-identity.md)

Správci IT upravují, jestli uživatel může používat účet MSA pro ověřování připojení a služby nesouvisecí s e-mailem, prostřednictvím [allowMicrosoftAccountConnection.](/windows/client-management/mdm/policy-csp-accounts#accounts-allowmicrosoftaccountconnection) Zásady konfigurace hesel, zásady idingu a zásady zamykací obrazovky najdete v tématu [Zámek zařízení.](/windows/client-management/mdm/policy-csp-devicelock)
