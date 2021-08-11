---
title: HoloLens 2 implementace a řešení potíží se spravovanými zařízeními
description: Řešení HoloLens se 2 zařízeními v Enterprise prostředí
author: JoyJaz
ms.author: v-jjaswinski
ms.date: 6/22/2021
ms.topic: article
keywords: řešení potíží
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: f038cbf58b6dfaef0395a1ea5b406cce23e4e3fe0464c6bfc1162518f9caf3ff
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2021
ms.locfileid: "115659783"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a>Řešení potíží s implementací a spravovanými zařízeními 

Tento článek popisuje, jak vyřešit několik problémů nebo zodpovědět otázky týkající se implementace a správy HoloLens 2.

>[!IMPORTANT]
> Než začnete s řešením potíží, ujistěte se, že je vaše zařízení naúčtované **na 20 až 40** % kapacity baterie, pokud je to možné. Indikátory [baterie umístěné](hololens2-setup.md#lights-that-indicate-the-battery-level) pod tlačítkem napájení jsou rychlým způsobem, jak ověřit kapacitu baterie bez přihlášení k zařízení.


<a id="list"></a>
- [Řešení potíží s protokolem EAP](#eap-troubleshooting)
- [Řešení potíží s Wi-Fi](#wi-fi-troubleshooting)
- [Řešení potíží se sítí](#network-troubleshooting)
- [Není možné se přihlásit k dříve vytvořenému HoloLens zařízení](#cant-sign-in-to-a-previously-setup-hololens-device)
- [Po aktualizaci na Holographic 21H1 se Windows přihlásit](#cant-login-after-updating-to-windows-holographic-21h1)
- [Řešení potíží s Autopilotem](#autopilot-troubleshooting)
- [Nejčastější dotazy HoloLens spravovaných zařízeních](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a>Řešení potíží s protokolem EAP
1. Zkontrolujte, Wi-Fi má profil správné nastavení:
    - Typ protokolu EAP je správně nakonfigurovaný, běžné typy protokolu EAP: EAP-TLS (13), EAP-TTLS (21) a PEAP (25).
    - Wi-Fi SSID je správný a shoduje se s hexaxim řetězcem.
    - Pro EAP-TLS obsahuje TrustedRootCA hodnotu hash SHA-1 certifikátu důvěryhodné kořenové certifikační autority serveru. V Windows PC "certutil.exe -dump cert_file_name" se zobrazí řetězec hash SHA-1 certifikátu.
2. Shromáždíte zachytávání síťových paketů v protokolech přístupového bodu, kontroleru nebo serveru AAA a zjistěte, kde relace protokolu EAP selže.
    - Pokud se identita protokolu EAP poskytnutá HoloLens neočekává, zkontrolujte, jestli byla identita správně zřízená prostřednictvím Wi-Fi profilu nebo klientského certifikátu.
    - Pokud server odmítne HoloLens klientský certifikát, zkontrolujte, jestli byl požadovaný klientský certifikát v zařízení zřízen.
    - Pokud HoloLens odmítne certifikát serveru, zkontrolujte, jestli je pro server certifikát kořenové certifikační autority HoloLens.
3. Pokud je podnikový profil zřízen prostřednictvím zřizovacího Wi-Fi, zvažte použití zřizovacího balíčku na počítači Windows 10 počítači. Pokud také selže v Windows 10 počítači, postupujte podle průvodce odstraňováním potíží Windows klienta 802.1X.
4. Pošlete nám svůj názor prostřednictvím Centrum Feedback.

[Zpět na seznam](#list)

## <a name="wi-fi-troubleshooting"></a>Wi-Fi potíží

Tady je několik věcí, které můžete vyzkoušet, pokud nemůžete připojit HoloLens k Wi-Fi síti:

1. Ujistěte se, Wi-Fi je zapnuté. Zkontrolujte to tak, že použijete gesto Spustit a pak vyberete Nastavení > Network & Internet > Wi-Fi. Pokud Wi-Fi, zkuste ho vypnout a znovu zas.
2. Přesuňte se blíže ke směrovači nebo přístupovému bodu.
3. Restartujte směrovač Wi-Fi a pak restartujte HoloLens. Zkuste se připojit znovu.
4. Pokud nic z toho nefunguje, zkontrolujte, že váš směrovač používá nejnovější firmware. Tyto informace najdete na webu výrobce.

Když se na zařízení přihlásíte k podnikovému účtu nebo účtu organizace, může to také použít zásadu Mobile Správa zařízení (MDM), pokud ji nakonfiguroval správce IT.

[Zpět na seznam](#list)

## <a name="network-troubleshooting"></a>Řešení potíží se sítí
Pokud problémy se sítí brání úspěšnému nasazení a používání HoloLens 2 ve vaší organizaci, nakonfigurujte Fiddler nebo Wireshark tak, aby zachycoval a analyzoval provoz HTTP/HTTPS. 

### <a name="configure-fiddler-to-capture-http-traffic"></a>Konfigurace Fiddleru pro zachytávání provozu HTTP
Fiddler je proxy webový ladicí program, který se používá k řešení potíží s http(S). Zachycuje všechny požadavky HTTP, které počítač vytvoří, a zaznamenává všechny související požadavky. Odhalení problémů s ověřováním koncových uživatelů pro vaše aplikace HTTPS zvyšuje produktivitu a efektivitu pro vaše cílové HoloLens 2 případy použití. 

#### <a name="prerequisites"></a>Požadavky
 
- HoloLens 2 a váš počítač musí být ve stejné síti.
- Poznamenejte si IP adresu počítače.

#### <a name="install-and-configure-fiddler"></a>Instalace a konfigurace Fiddleru

1. Na počítači – [nainstalujte a](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) spusťte Fiddler.  
1. Na počítači – Nakonfigurujte Fiddler tak, aby se mohly připojovat vzdálené počítače.
    1. Přejděte na Fiddler Nastavení -> Connections.
    1. Poznamenejte si port naslouchání pro Fiddler (výchozí hodnota je 8866).
    1. Zaškrtněte políčko Povolit vzdáleným počítačům připojení.
    1. Kliknutí na Uložit
3. Na počítači HoloLens 2 – nakonfigurujte Fiddler jako proxy server<sup>1:</sup>
    1. Otevřete nabídka Start a vyberte Nastavení
    1. Vyberte Network & Internet a pak v nabídce vlevo vyberte Proxy.
    1. Posuňte se dolů na Ruční nastavení proxy serveru a přepněte Použít proxy server na On (Zapnout).
    1. Zadejte IP adresu počítače, na kterém je nainstalovaný Fiddler.
    1. Zadejte výše uvedené číslo portu (výchozí hodnota je 8866).
    1. Kliknutí na Uložit

<sup>1</sup> Pro buildy 20279.1006+ (Insiders a nadcházející verze) nakonfigurujte proxy server pomocí následujících kroků:
1. Otevřete nabídka Start a přejděte na Wi-Fi vlastnosti vaší sítě. 
1. Posuňte se dolů na Proxy.
1. Změna na ruční nastavení
1. Zadejte IP adresu počítače, na kterém je nainstalovaný Fiddler.
1. Zadejte číslo portu, které jste si už všimli. (výchozí hodnota je 8866)
1. Klikněte na Použít.
    
#### <a name="decrypt-https-traffic-from-hololens-2"></a>Dešifrování provozu HTTPS z HoloLens 2

1. Na počítači – exportujte certifikát Fiddleru.
    1. Přejděte na Fiddler Nastavení -> HTTPS a rozbalte Upřesnit Nastavení
    2. Klikněte na Exportovat certifikát Fiddleru. Uloží se na plochu.
    3. Přesuňte certifikát do složky Stažené soubory ve vaší HoloLens 2.

2.  Na počítači HoloLens 2 – importujte certifikát Fiddleru.
    1. Přejděte na Nastavení -> Update and Security -> Certificates.
    2. Klikněte na Nainstalovat certifikát, přejděte do složky Stažené soubory a vyberte certifikát Fiddleru.
    3. Změňte Umístění úložiště na Místní počítač.
    4. Změna úložiště certifikátů na root
    5. Vyberte Nainstalovat.
    6. Ověřte, že se certifikát zobrazuje v seznamu certifikátů. Pokud ne, opakujte výše uvedené kroky.

#### <a name="inspect-https-sessions"></a>Kontrola relací HTTP(S)

Na počítači fiddler zobrazí HoloLens 2 živé relace HTTP(S). Panel Inspektory ve Fiddleru může zobrazit požadavky a odpovědi HTTP(S) v různých zobrazeních – například zobrazení Raw zobrazuje nezpracovaný požadavek nebo odpověď ve formátu prostého textu. 

### <a name="configure-wireshark-to-capture-network-traffic"></a>Konfigurace Wiresharku pro zachytávání síťového provozu
Wireshark je analyzátor síťového protokolu, který slouží ke kontrole provozu TCP/UDP z a do zařízení HoloLens 2. To usnadňuje identifikaci, jaký provoz přechází přes vaši síť do HoloLens 2, jak velkou část provozu, jak často, jak často je latence mezi určitými segmenty směrování a tak dále.

#### <a name="prerequisites"></a>Požadavky:
- Počítač musí mít přístup k internetu a podporovat sdílení internetu přes Wi-Fi

#### <a name="install-and-configure-wireshark"></a>Instalace a konfigurace Wiresharku
1. Na svém počítači – nainstalujte [Wireshark.](https://www.wireshark.org/#download) 
1. Na počítači – povolte Možnost Mobilní hotspot, abyste sdíleli připojení k internetu z Wi-Fi.
1. Na počítači spusťte Wireshark a zachyťte provoz z rozhraní Mobilní hotspot. 
1. Na počítači HoloLens 2 – změňte Wi-Fi síť na Mobilní hotspot počítače. HoloLens wiresharku se zobrazí přenosy IP adres 2.

#### <a name="analyze-wireshark-logs"></a>Analýza protokolů Wiresharku
Filtry nástroje Wireshark můžou přispět k odfiltrování paketů zájmů. 

Podívejte se na původní [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458).

[Zpět na seznam](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a>nepovedlo se přihlásit k dřív nastavenému HoloLens zařízení.

Pokud jste zařízení dříve nastavili pro někoho jiného, buď pro klienta, nebo pro bývalého zaměstnance, a nemáte heslo k odemknutí zařízení, můžete pomocí Intune vzdáleně [Vymazat](/intune/remote-actions/devices-wipe) zařízení. Zařízení se pak znovu zabliká.  
> [!IMPORTANT]
> Když zařízení vymažete, nezapomeňte ponechat **stav registrace a účet uživatele** nezaškrtnutý.

[Zpět na seznam](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a>po aktualizaci na Windows holografické 21H1 se nedá přihlásit.

### <a name="symptoms"></a>Příznaky
- Po zadání správného kódu PIN se přihlášení pomocí kódu PIN nezdaří.
- Po úspěšném přihlášení na webové stránce se použití metody přihlášení k webu nezdaří.
- zařízení není uvedené jako "Azure AD join" v [Azure Portal](https://portal.azure.com/) > zařízení Azure Active Directory >.

### <a name="cause"></a>Příčina
Ovlivněné zařízení mohlo být odstraněno z tenanta Azure AD. K tomu může dojít například z těchto důvodů:

- Správce nebo uživatel zařízení odstranil v Azure Portal nebo pomocí PowerShellu.
- Zařízení se odebralo z tenanta Azure AD kvůli nečinnosti. Pro efektivní spravované prostředí typicky doporučujeme správcům IT [odebírat ze svého tenanta Azure AD zastaralé neaktivní zařízení](/azure/active-directory/devices/manage-stale-devices).

Když se zasažené zařízení pokusí kontaktovat tenanta Azure AD znovu po jeho odstranění, nepodaří se mu ověřit pomocí Azure AD. Tento efekt je často neviditelný pro uživatele zařízení, protože přihlášení do mezipaměti prostřednictvím kódu PIN bude dál umožňovat přihlášení uživatele.

### <a name="mitigation"></a>Omezení rizik
v současné době neexistuje způsob, jak přidat odstraněné HoloLens zařízení zpátky do služby Azure AD. Ovlivněná zařízení bude potřeba vyčistit, a to podle pokynů při [přeblikání zařízení](hololens-recovery.md#clean-reflash-the-device).

[Zpět na seznam](#list)

## <a name="autopilot-troubleshooting"></a>Řešení potíží s autopilotem

následující články můžou být užitečným prostředkem, abyste si mohli přečíst další informace a řešit problémy s výkonem pro autopilot, ale pamatujte na to, že tyto články jsou založené na Windows 10 desktopu a ne všechny informace se mohou vztahovat na HoloLens:

- [Windows Autopilot – známé problémy](/mem/autopilot/known-issues)
- [řešení potíží s registrací zařízení Windows v Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot – konflikty zásad](/mem/autopilot/policy-conflicts)

[Zpět na seznam](#list)

## <a name="managed-hololens-devices-faqs"></a>nejčastější dotazy týkající se spravovaných HoloLens zařízení

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a>můžu pomocí System Center Configuration Manager (SCCM) spravovat HoloLens zařízení?

No. ke správě HoloLensch zařízení je nutné použít systém MDM.

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a>můžu ke správě HoloLens uživatelských účtů použít Active Directory Domain Services (služba AD DS)?

No. k řízení uživatelských účtů pro HoloLens zařízení musíte použít Azure Active Directory (Azure AD).

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a>je HoloLens schopným automatickým zápisem automaticky registrovat systémy (assd) automatizovaného sběru dat?

No.

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a>dá se HoloLens zúčastnit integrovaného Windowsho ověřování?

No.

### <a name="does-hololens-support-branding"></a>podporuje HoloLens branding?

No. Tento problém ale můžete obejít pomocí jednoho z následujících přístupů:

- Vytvořte vlastní aplikaci a pak [Povolte celoobrazovkový režim](hololens-kiosk.md). Vlastní aplikace může mít branding a může spouštět jiné aplikace (například vzdálenou pomoc).  
- Změňte všechny obrázky profilů uživatelů ve službě Azure AD na logo vaší společnosti. To však nemusí být žádoucí pro všechny scénáře.

### <a name="what-logging-capabilities-does-hololens-2-offer"></a>jaké možnosti protokolování nabízí HoloLens 2?

Protokolování je omezené na trasování, která se dají zachytit ve scénářích vývoje nebo řešení potíží, nebo telemetrie, kterou zařízení odesílají na servery Microsoftu.

## <a name="questions-about-securing-hololens-devices"></a>dotazy týkající se zabezpečení zařízení HoloLens

podívejte se na [naše informace o zabezpečení HoloLens 2](security-overview.md).
pro HoloLens 1. generace se podívejte na [tyto nejčastější dotazy](hololens1-faq-security.yml).

[Zpět na seznam](#list)
