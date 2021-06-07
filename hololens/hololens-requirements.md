---
title: Nastavení HoloLens v komerčním prostředí
description: Přečtěte si další informace o nasazení a správě HoloLens v podnikových prostředích, včetně infrastruktury, Azure Active Directory a správy mobilních zařízení.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
ms.reviewer: aboeger
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: e6aebfca076294de34068cd075d954220d7f4686
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111377639"
---
# <a name="hololens-2-enterprise-deployment-and-management"></a>Nasazení a správa HoloLens 2 v podniku

Tento přehled pomáhá IT specialistům pochopit aspekty nasazení a správy Microsoft HoloLens 2 v rámci podniku.

HoloLens 2 běží na Windows 10 Holographic, který organizacím poskytuje robustní, flexibilní integrované technologie správy mobilních zařízení a aplikací. Windows 10 Holographic podporuje koncovou správu životního cyklu zařízení, aby společnosti nad svými zařízeními, daty a aplikacemi kontrolul. HoloLens 2 je možné snadno začlenit do standardních postupů životního cyklu, od registrace zařízení, konfigurace a správy aplikací až po údržbu a vyřazení pomocí komplexního řešení pro správu mobilních zařízení.

## <a name="prepare"></a>Příprava

Při přípravě nasazení HoloLens 2 do podnikového prostředí společnosti je třeba zvážit několik hledisek, které byste měli vzít v úvahu při plánování nasazení HoloLens 2 ve velkém.

### <a name="infrastructure-essentials"></a>Základy infrastruktury

Pro HoloLens 2 ve scénáři podnikového nasazení existují určité základní služby infrastruktury potřebné k podpoře celé sady funkcí. HoloLens 2 byl vytvořen pomocí moderních mobilních [Správa zařízení](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) pro nasazení a správu. Azure AD Join + MDM je primárním prostředkem, jak toho dosáhnout u stále rostoucích mobilních pracovníků. Následující témata poskytují stručný přehled jednotlivých komponent infrastruktury, které byste měli zvážit při plánování nasazení pro HoloLens 2.

### <a name="azure-active-directory"></a>Azure Active Directory
Azure AD je cloudová adresářová služba, která poskytuje správu identit a přístupu. Můžete ho integrovat s existujícími místními adresáři a vytvořit řešení hybridní identity. Organizace, které používají systém Microsoft Office 365 nebo Intune, už používají Azure AD, která má tři edice: Free, Premium P1 a Premium P2 (viz edice [Azure Active Directory).](https://azure.microsoft.com/documentation/articles/active-directory-editions/) Všechny edice podporují registraci zařízení Azure AD, ale k povolení automatické registrace MDM se vyžaduje Premium P1. HoloLens 2 vyžaduje Azure Active Directory Join, aby bylo možné povolit většinu funkcí a funkcí na podnikové úrovni.

> [!NOTE]
> HoloLens 2 nepodporuje místní připojení ke službě Active Directory.

### <a name="mobile-device-management"></a>Správa mobilních zařízení
HoloLens 2 je navržený speciálně pro správu pomocí systémů Mobile Správa zařízení (MDM) v podnikovém prostředí. Microsoft [Intune](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune), součást Enterprise Mobility + Security, je cloudový systém MDM, který spravuje zařízení v podniku. Stejně jako Office 365 používá Intune ke správě identit Azure AD, takže zaměstnanci používají stejné přihlašovací údaje k registraci zařízení v Intune, která používají pro přihlášení k Office 365. Několik systémů MDM podporuje Windows 10 většina podporuje scénáře nasazení osobních a firemních zařízení. Systémy MDM mohou také spravovat nasazení a aktualizace aplikací pro HoloLens 2. Mezi další poskytovatele MDM, kteří podporují HoloLens 2, aktuálně patří: AirWatch, MobileIron a další. Všichni dodavatelé systémů MDM mají stejný přístup k poskytovatelům konfiguračních služeb pro správu zařízení (CSP) Windows 10 dávají IT organizacím možnost vybrat si ten, který systém nejlépe vyhovuje jejich požadavkům na správu, ať už jde o Microsoft Intune nebo produkt MDM třetí strany.

> [!NOTE]
> HoloLens 2 System Center Správce konfigurace tradiční místní systémy pro správu počítačů, jako je System Center Správce konfigurace.

### <a name="windows-update-for-business"></a>Windows Update pro firmy
Společnost Microsoft navrhla Windows Update pro firmy, aby správcům IT poskytovala další možnosti správy zaměřené na služba Windows Update, jako je například možnost nasazovat aktualizace do skupin zařízení a definovat intervaly údržby pro instalaci aktualizací. Podrobnosti o [správě aktualizací HoloLens](https://docs.microsoft.com/hololens/hololens-updates) 2 najdete v dokumentaci k aktualizacím HoloLens.

### <a name="certificates"></a>Certifikáty
HoloLens 2 podporuje nasazování certifikátů prostřednictvím MDM, pokud vaše prostředí vyžaduje certifikáty pro ověřování Wi-Fi Corp nebo přístup k jiným prostředkům. K povolení nasazení certifikátů do HoloLens 2 může být potřeba několik konfigurací infrastruktury MDM. Přečtěte si, [jak připravit certifikáty a síťové profily pro HoloLens 2.](https://docs.microsoft.com/hololens/hololens-certificates-network) Pokud používáte Intune, podívejte se na podrobnosti [o konfiguraci](https://docs.microsoft.com/mem/intune/protect/certificates-configure) certifikace.

## <a name="configure"></a>Konfigurace

Správci MDM můžou definovat a implementovat nastavení zásad na libovolném podnikovém zařízení zaregistrované v systému MDM. Nastavení konfigurace, která použijete, se budou lišit v závislosti na scénáři nasazení. V Windows 10 jsou poskytovatelé konfiguračních služeb (CSP) rozhraní pro čtení, nastavení, úpravu nebo odstranění konfiguračních nastavení na zařízení. Tato nastavení se mapovat na klíče nebo soubory registru. Další informace o zprostředkovatelích Windows 10 správy zařízení pro HoloLens 2 najdete v úplném seznamu csP podporovaných v [zařízeních HoloLens.](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)

HoloLens 2 také podporuje nastavení omezené sady konfigurací CSP prostřednictvím vlastních zřizovacích balíčků. Zřizovací balíčky se obvykle využívají pro zařízení nespravovaná pomocí MDM a vyžadují ruční použití na každé zařízení. Podrobnosti o [vytváření vlastních zřizovacích balíčků](https://docs.microsoft.com/hololens/hololens-provisioning) najdete v dokumentaci ke zřizování HoloLens.

> [!NOTE]
> HoloLens 2 [podporuje Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot), který poskytuje snadný a jednoduchý proces pro správu konfigurací podnikových Windows 10 zařízení.

### <a name="identity-management"></a>Správa identit

Zaměstnanci mohou k inicializaci zařízení použít pouze jeden účet,&#39;je nezbytné, aby vaše organizace nejdřív vyhotivěl, který účet je povolený. Zvolený účet určí, kdo zařízení řídí, a ovlivní možnosti správy. HoloLens 2 podporuje 3 typy účtů: místní uživatelský účet, osobní účet Microsoft a Azure Active Directory účty. Důrazně doporučujeme využít tento Azure Active Directory pro řešení správy podnikových identit, protože na zařízeních HoloLens 2 umožní všechny funkce. Další podrobnosti o identitách pro [HoloLens](https://docs.microsoft.com/hololens/hololens-identity) 2 najdete v tématu Identita HoloLens.

### <a name="network-and-connectivity"></a>Síť a možnosti připojení

HoloLens 2 je první cloudové zařízení, a proto se k tomu, aby byly dostupné všechny funkce a možnosti, vyžaduje síťový přístup k online prostředkům. Pokud nasazujete zařízení HoloLens 2 s připojením k podnikové intranetové síti, může být nutné aktualizovat pravidla proxy serveru nebo brány firewall, aby byl povolen přístup ke cloudovým službám HoloLens 2. Další informace najdete v seznamu běžných koncových bodů operačního systému [HoloLens 2.](https://docs.microsoft.com/hololens/hololens-offline) K úspěšnému spuštění aplikací nebo jiných cloudových služeb na HoloLens 2 může být nutný přístup k dalším koncovým bodům.

Mezi běžné služby HoloLens 2, které vyžadují další přístup ke koncovým bodům, patří:

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [Průvodci pro D365](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [D365 Remote Assist (infrastruktura O365 Teams)](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### <a name="certificate-deployment"></a>Nasazení certifikátu

Pokud jsou pro přístup k podnikovým sítím Wi-Fi nebo jiným službám v rámci vaší organizace vyžadovány certifikáty, HoloLens 2 podporuje nasazení certifikátů uživatelů a zařízení prostřednictvím MDM. Poznámka: Řešení mdm může vyžadovat další konfiguraci infrastruktury pro nasazení certifikátů do Windows 10 zařízení.

### <a name="security-review"></a>Kontrola zabezpečení

Většina podnikových IT oddělení bude vyžadovat posouzení a posouzení nových zařízení nasazených v podnikové síti. Pokud vaše organizace potřebuje bezpečnostní revize HoloLens 2, najdete další podrobnosti, které vám po pomohou [se získáním schválení zabezpečení.](https://docs.microsoft.com/hololens/security-overview)

### <a name="common-hololens-2-device-settings"></a>Běžná nastavení zařízení HoloLens 2

Při nasazování zařízení HoloLens 2 do podnikového prostředí existuje řada běžných konfigurací zařízení, které je možné zvážit při plánování nasazení HoloLens 2. Tento seznam zvýrazní konfigurace a nastavení, která jsou poměrně běžná, a nezahrnuje úplný seznam dostupných možností:

| Nastavení zařízení | Stručný popis.                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [Hardwarová omezení](hololens-requirements.md#hardware-restrictions)               | Hardwarová omezení omezují možnosti připojení a pomáhají s ochranou dat.                        |
| [Profily sítě Wi-Fi](hololens-requirements.md#wi-fi-profiles)               | Nakonfigurujte Wi-Fi profily bez zásahu uživatele nebo interakce.                              |
| [Certifikáty](hololens-requirements.md#certificates-1)               | Poskytnutí ověřování účtu nebo Wi-Fi, šifrování sítě VPN a šifrování SSL webového obsahu. |
| [Proxy server](hololens-requirements.md#proxy)              | Správa interního provozu.                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | Řízení přístupu k aplikacím a prostředkům v intranetu společnosti                               |
| [Bezobrazovový režim](hololens-requirements.md#kiosk-mode) | Omezuje aplikace prezentované uživatelům prostřednictvím uživatelského rozhraní. |

#### <a name="hardware-restrictions"></a>Hardwarová omezení

HoloLens 2 používá moderní technologii, která zahrnuje oblíbené hardwarové funkce, jako jsou fotoaparáty, mikrofony, mluvčí, rozhraní USB, rozhraní Bluetooth a Wi-Fi. K řízení dostupnosti těchto funkcí můžete použít hardwarová omezení.

Následující seznam uvádí nejčastěji používaná nastavení MDM, která HoloLens 2 podporuje při konfiguraci hardwarových omezení. Některá z těchto hardwarových omezení poskytují možnosti připojení a pomáhají při ochraně dat.

- [**Povolit Wi-Fi:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Jestli uživatelé mohou na svých zařízeních povolit a používat Wi-Fi přepínač
- [**Povolit připojení USB:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Jestli je povolené připojení USB (&#39;nemá vliv na usb flash disk)
- [**Povolit Bluetooth:**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Jestli uživatelé mohou na svých zařízeních povolit a používat přepínač Bluetooth

Přečtěte si další informace o dalších [běžných omezeních zařízení.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

#### <a name="wi-fi-profiles"></a>Profily sítě Wi-Fi

Většina podnikových Wi-Fi vyžaduje k omezení a zabezpečení uživatelského přístupu certifikáty a další složité informace. Tato pokročilá Wi-Fi konfigurace je pro typické uživatele obtížná, ale systémy MDM mohou tyto profily Wi-Fi plně nakonfigurovat bez zásahu uživatele. V systému MDM můžete Wi-Fi několika různých profilů.

Další podrobnosti o nastavení Wi-Fi pro Windows 10 najdete v tématu Nastavení [Wi-Fi profilu podniku.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)

#### <a name="certificates"></a>Certifikáty

Certifikáty zlepšují zabezpečení tím, že poskytují ověřování účtu, Wi-Fi ověřování, šifrování sítě VPN a šifrování SSL webového obsahu. I když správci můžou certifikáty na zařízeních spravovat ručně prostřednictvím zřizovacích balíčků,&#39;s osvědčenými postupy pro správu těchto certifikátů v celém celém životním cyklu – od registrace po obnovení a odvolání. Systém MDM může tyto certifikáty automaticky nasadit do zařízení&#39; úložišť certifikátů po registraci zařízení (Pokud systém MDM podporuje Simple Certificate Enrollment Protocol (SCEP) nebo standardy šifrování veřejného klíče #12 (PKCS # 12)). MDM taky může dotazovat a odstraňovat zaregistrované klientské certifikáty nebo aktivovat novou žádost o registraci před vypršením platnosti aktuálního certifikátu.

Přečtěte si další informace o [přípravě certifikátů a profilů sítě pro HoloLens 2.](https://docs.microsoft.com/hololens/hololens-certificates-network)

#### <a name="proxy"></a>Proxy server

Většina podnikových intranetových sítí využívá proxy server ke správě interního provozu. Pomocí HoloLens 2 můžete nakonfigurovat proxy server pro připojení Ethernet a Wi-Fi. Tato nastavení se nevztahují na připojení VPN.

Další podrobnosti o nastaveních proxy serveru pro Windows 10 najdete v tématu [NETWORKPROXY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp).

#### <a name="vpn"></a>Síť VPN

Organizace často používají síť VPN k řízení přístupu k aplikacím a prostředkům ve svých firemních&#39;s intranetu. HoloLens 2 podporuje připojení SSL VPN, která vyžadují modul plug-in ke stažení z Microsoft Store a jsou specifická pro dodavatele VPN podle vašeho výběru.

Další podrobnosti o profilech VPN najdete v tématu [CSP pro podpora vpnv2](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx) .

#### <a name="kiosk-mode"></a>Celoobrazovkový režim

Zařízení HoloLens 2 můžete nakonfigurovat tak, aby fungovalo jako zařízení s pevným účelem, označované taky jako terminál, a to tak, že nakonfigurujete zařízení tak, aby běželo v celoobrazovkovém režimu. Celoobrazovkový režim omezuje aplikace (nebo uživatele), které jsou v zařízení k dispozici. Celoobrazovkový režim je pohodlná funkce, kterou můžete použít k vyhradit zařízení HoloLens 2 pro obchodní aplikace nebo použít zařízení HoloLens 2 v ukázce aplikace.

Další podrobnosti o konfiguraci HoloLens 2 v celoobrazovkovém režimu najdete v tématu [Nastavení HoloLens jako veřejného terminálu](https://docs.microsoft.com/hololens/hololens-kiosk) .

## <a name="deploy"></a>Nasadit

### <a name="mdm-device-enrollment"></a>Registrace zařízení MDM

U podnikových nasazení se doporučuje [Registrovat zařízení](https://docs.microsoft.com/hololens/hololens-enroll-mdm) do MDM jako firemní zařízení jenom s připojením k Azure AD a automatickým zápisem MDM (Azure AD + MDM). To vyžaduje Azure AD Premium a podporuje automatický zápis do několika poskytovatelů MDM včetně Intune.

Přečtěte si další informace o automatickém nasazení metody registrace [autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot).

### <a name="application-deployment"></a>Nasazení aplikací

Produktivita uživatelů na mobilních zařízeních se často řídí aplikacemi.

Windows 10 umožňuje vyvíjet aplikace, které bez problémů fungují napříč různými zařízeními, a to pomocí Univerzální platforma Windows (UWP) pro aplikace pro Windows.

Existuje několik způsobů, jak nasadit aplikace na zařízení HoloLens 2. Aplikace se dají nasadit přímo přes MDM, Microsoft Store pro firmy nebo zkušebně načtené prostřednictvím zřizovacího balíčku. Další podrobnosti najdete v dokumentaci [nasazení aplikace](https://docs.microsoft.com/hololens/app-deploy-overview) .

> [!NOTE]
> HoloLens 2 podporuje pouze spouštění aplikací ARM64 pro UWP.

## <a name="maintain"></a>Údržba

V podnikových prostředích IT musí být nutnost zabezpečení a řízení nákladů vyvážená na základě přání poskytovat uživatelům nejnovější technologie. Vzhledem k tomu, že kyberútokům se stala každodenním výskytem, je důležité správně udržovat stav zařízení s Windows 10. JE potřeba řídit nastavení konfigurace, zajišťovat jejich odklad z hlediska dodržování předpisů a vymáhat, která zařízení mají přístup k interním aplikacím. HoloLens 2 přináší funkce pro správu mobilních operací, které jsou nezbytné k zajištění toho, aby zařízení byla v souladu s podnikovými zásadami.

### <a name="os-servicing-options"></a>Možnosti údržby operačního systému

**Zjednodušený proces aktualizace**

Společnost Microsoft zjednodušila vývoj a vydávání produktů v systému Windows, takže nové funkce, prostředí a funkce, které vyžadují trh, je možné doručit rychleji než kdykoli dřív. Microsoft plánuje doručovat dvě aktualizace funkcí za rok (12 měsíců). **Aktualizace funkcí** navážou Current Branch nebo a mají přidruženou verzi.

Microsoft bude také poskytovat a instalovat aktualizace pro zabezpečení a stabilitu přímo do zařízení HoloLens 2. Tyto **aktualizace kvality** vydané v rámci řízení společnosti Microsoft prostřednictvím web Windows Update jsou k dispozici měsíčně. HoloLens 2 spotřebovává aktualizace funkcí a aktualizace kvality jako součást stejného standardního procesu aktualizace.

Podnikoví zákazníci mohou spravovat možnosti a procesy aktualizace na HoloLens 2S pomocí systému MDM. Ve většině případů se zásady pro správu procesu aktualizace vztahují na aktualizace funkcí i na kvalitu. Další podrobnosti najdete v [konfiguraci MDM pro aktualizace pro HoloLens](https://docs.microsoft.com/hololens/hololens-updates).

### <a name="managing-applications"></a>Správa aplikací

Správci IT můžou řídit, které aplikace se můžou nainstalovat na HoloLens 2 a jak se mají udržovat v aktuálním stavu.

HoloLens 2 podporuje [řízení aplikací v programu Windows Defender (WDAC)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac), které umožňuje správcům vytvořit, povolit nebo zakázat seznamy aplikací z Microsoft Store. Tato funkce se rozšiřuje i na integrované aplikace. Možnost povolit nebo zamítnout aplikace pomáhá zajistit, aby uživatelé používali svá zařízení k zamýšleným účelům. Nejedná se ale vždy o snadný přístup k vyhledání rovnováhy mezi tím, co zaměstnanci potřebují, nebo žádostí a zabezpečením. Vytváření seznamů povolených nebo zakázaných aplikací také vyžaduje, aby se při Microsoft Store změnila orientace aplikace na šířku.

Další podrobnosti najdete v tématu [CSP pro řízení aplikací](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp).

### <a name="retire"></a>Vyřazení

Vyřazení zařízení je poslední fází životního cyklu zařízení. &#39;s je důležité, aby se zařízení nahrazená novějšími modely bezpečně vyhodila, protože nebudete&#39;, aby některá firemní data zůstala na zahozených zařízeních, která by mohla ohrozit důvěrnost vašich dat. Také potřebuje způsob, jak vhodně podporovat uživatele, kteří potřebují vymazat zařízení, která jsou ztracena nebo odcizena.

HoloLens 2 podporuje 3 metody vymazání zařízení.

**Vymazání továrny MDM:** Obnoví nastavení HoloLens 2 zpátky na Image Factory pomocí příkazu MDM iniciované správcem. Smaže všechna uložená data na zařízení.

**Resetování zařízení v nastavení:** Koncoví uživatelé můžou ručně resetovat HoloLens 2 v rámci aplikace nastavení na zařízení. Smaže všechna uložená data na zařízení.

**Rozšířený Průvodce obnovením (oblouk):** V počítači, na kterém je spuštěný nástroj ARC, může uživatel nebo správce pomocí kabelu USB zablikat počítač HoloLens 2 připojený k počítači. Smaže všechna uložená data na zařízení.

> [!div class="nextstepaction"]
> [Běžné scénáře nasazení](common-scenarios.md)
