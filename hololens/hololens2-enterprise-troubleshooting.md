---
title: HoloLens 2 implementace a řešení potíží se spravovanými zařízeními
description: Řešení HoloLens se 2 zařízeními v Enterprise prostředí
author: beelia
ms.author: v-beehanson
ms.date: 6/22/2021
ms.topic: article
keywords: řešení potíží
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 2e997514be5d067ce5e9bd7f3611b464d19a6fad
ms.sourcegitcommit: b9cd7ed5edb98249c609b547b90587863ea1cb9e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/01/2021
ms.locfileid: "129364586"
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
1. Ověřte, že Wi-Fi profil má správné nastavení:
    - Nakonfigurujte typ protokolu EAP správně. Běžné typy protokolu EAP jsou EAP-TLS (13), EAP-TTLS (21) a PEAP (25).
    - Zkontrolujte název Wi-Fi SSID a zkontrolujte, jestli se shoduje s řetězcem HEX.
    - Ujistěte se, že pro protokol EAP-TLS obsahuje trustedRootCA hodnotu hash SHA-1 certifikátu důvěryhodné kořenové certifikační autority serveru. Na Windows počítači příkaz "certutil.exe -dump cert_file_name" zobrazí řetězec hash SHA-1 certifikátu.
2. Shromáždíte zachytávání síťových paketů v protokolech přístupového bodu, kontroleru nebo serveru AAA, abyste zjistili, kde relace protokolu EAP selže.
    - Pokud je identita protokolu EAP poskytnutá HoloLens neočekávaná, zkontrolujte, jestli je identita správně zřízená prostřednictvím Wi-Fi profilu nebo klientského certifikátu.
    - Pokud server odmítne klientský certifikát HoloLens, zkontrolujte, jestli byl v zařízení zřízen požadovaný klientský certifikát.
    - Pokud HoloLens odmítne certifikát serveru, zkontrolujte, jestli byl v počítači zřízen certifikát kořenové certifikační autority HoloLens.
3. Pokud je podnikový profil zřízen prostřednictvím zřizovacího Wi-Fi, zvažte použití zřizovacího balíčku na Windows 10 počítači. Pokud dojde k selhání také Windows 10 počítači, postupujte podle průvodce odstraňováním potíží Windows ověřování klienta 802.1X.
4. Pošlete nám svůj názor prostřednictvím Centrum Feedback.

[Zpět na seznam](#list)

## <a name="wi-fi-troubleshooting"></a>Wi-Fi potíží

Tady je několik věcí, které můžete vyzkoušet, pokud nemůžete připojit HoloLens k Wi-Fi síti:

1. Zkontrolujte, jestli je zapnuté Wi-Fi. Ověřte to pomocí gesta Start a pak vyberte Nastavení > Network & Internet > Wi-Fi. Pokud Wi-Fi, zkuste ho vypnout a znovu zas.
2. Přesuňte se blíže ke směrovači nebo přístupovému bodu.
3. Restartujte směrovač Wi-Fi a pak restartujte HoloLens. Zkuste se připojit znovu.
4. Pokud nic z těchto věcí nefunguje, ověřte, že směrovač používá nejnovější firmware. Tyto informace najdete na webu výrobce.

Když se na zařízení přihlásíte k podnikovému účtu nebo účtu organizace, může to také použít zásadu Mobile Správa zařízení (MDM), pokud ji nakonfiguroval správce IT.

[Zpět na seznam](#list)

## <a name="network-troubleshooting"></a>Řešení potíží se sítí
Pokud problémy se sítí brání úspěšnému nasazení a používání HoloLens 2 ve vaší organizaci, nakonfigurujte Fiddler nebo Wireshark tak, aby zachycoval a analyzoval provoz HTTP/HTTPS. 

### <a name="configure-fiddler-to-capture-http-traffic"></a>Konfigurace Fiddleru pro zachytávání provozu HTTP
Fiddler je proxy webový ladicí program, který se používá k řešení potíží s http(S). Zachycuje všechny požadavky HTTP, které počítač vytvoří, a zaznamenává všechny související požadavky. Odhalení problémů s ověřováním koncových uživatelů pro vaše aplikace HTTPS zvyšuje produktivitu a efektivitu pro vaše cílové HoloLens 2 případy použití. 

#### <a name="prerequisites"></a>Požadavky
 
- HoloLens 2 zařízení a váš počítač musí být ve stejné síti.
- Poznamenejte si IP adresu počítače.

#### <a name="install-and-configure-fiddler"></a>Instalace a konfigurace Fiddleru

1. Na počítači – [nainstalujte a](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) spusťte Fiddler.  
1. Na počítači – Nakonfigurujte Fiddler tak, aby se mohly připojovat vzdálené počítače.
    1. Přejděte na Fiddler Nastavení -> Connections .)
    1. Poznamenejte si port naslouchání pro Fiddler (výchozí hodnota je 8866).
    1. Zaškrtněte políčko Povolit vzdáleným počítačům připojení.
    1. Klikněte na Uložit.
3. Na počítači HoloLens 2 – nakonfigurujte Fiddler jako proxy server<sup>1:</sup>
    1. Otevřete nabídka Start a vyberte Nastavení.
    1. Vyberte Network & Internet a pak v nabídce vlevo vyberte Proxy.
    1. Přejděte dolů na Manual proxy setup (Ruční nastavení proxy serveru) a přepněte Use a proxy server (Použít proxy server) na On (Zapnout).
    1. Zadejte IP adresu počítače, na kterém je aplikace Fiddler nainstalovaná.
    1. Zadejte výše uvedené číslo portu (výchozí je 8866).
    1. Klikněte na Uložit.

<sup>1</sup> Pro buildy 20279.1006+ (Insiders a nadcházející verze) nakonfigurujte proxy server pomocí následujících kroků:
1. Otevřete nabídka Start a přejděte na stránku Wi-Fi vlastnosti vaší sítě. 
1. Posuňte se dolů na Proxy.
1. Změňte nastavení na Ruční nastavení.
1. Zadejte IP adresu počítače, na kterém je aplikace Fiddler nainstalovaná.
1. Zadejte výše uvedené číslo portu (výchozí je 8866).
1. Klikněte na Použít.
    
#### <a name="decrypt-https-traffic-from-hololens-2"></a>Dešifrování provozu HTTPS z HoloLens 2

1. Na počítači – exportujte certifikát Fiddleru.
    1. Přejděte na Fiddler Nastavení -> HTTPS a rozbalte Upřesnit Nastavení.
    2. Klikněte na Exportovat certifikát Fiddleru. Uloží se na plochu.
    3. Přesuňte certifikát do složky Stažené soubory ve vašem HoloLens 2.

2.  Na počítači HoloLens 2 naimportujte certifikát Fiddleru.
    1. Přejděte na Nastavení -> Update and Security -> Certificates .)
    2. Klikněte na Install Certificate (Nainstalovat certifikát), přejděte do složky Downloads (Stažené soubory) a vyberte certifikát Fiddler.
    3. Změňte Umístění úložiště na Místní počítač.
    4. Změňte úložiště certifikátů na root.
    5. Vyberte Nainstalovat.
    6. Ověřte, že se certifikát zobrazuje v seznamu certifikátů. Pokud ne, opakujte tyto kroky.

#### <a name="inspect-https-sessions"></a>Kontrola relací HTTP(S)

Na počítači fiddler zobrazí HoloLens 2 živé relace HTTP(S). Panel Inspektory ve Fiddleru může zobrazit požadavek a odpověď HTTP(S) v různých zobrazeních. Například zobrazení Raw zobrazuje nezpracovaný požadavek nebo odpověď v prostém textu. 

### <a name="configure-wireshark-to-capture-network-traffic"></a>Konfigurace Wiresharku pro zachytávání síťového provozu
Wireshark je analyzátor síťového protokolu, který slouží ke kontrole provozu TCP/UDP do a ze zařízení HoloLens 2. To usnadňuje identifikaci provozu, který přechází přes síť k vaší síti HoloLens 2 – kolik je, jeho frekvence, latence mezi určitými segmenty směrování a tak dále.

#### <a name="prerequisites"></a>Požadavky:
- Počítač musí mít přístup k internetu a podporovat sdílení internetu přes Wi-Fi.

#### <a name="install-and-configure-wireshark"></a>Instalace a konfigurace Wiresharku
1. Na svém počítači nainstalujte [Wireshark.](https://www.wireshark.org/#download)
1. Na počítači – povolte Možnost Mobilní hotspot, abyste sdíleli připojení k internetu z Wi-Fi.
1. Na počítači spusťte Wireshark a zachyťte provoz z rozhraní Mobilní hotspot. 
1. Na počítači HoloLens 2 – změňte Wi-Fi síť na Mobilní hotspot počítače. HoloLens Wireshark se zobrazí přenosy IP 2.

#### <a name="analyze-wireshark-logs"></a>Analýza protokolů Wiresharku
Filtry Wireshark můžou pomoct s filtrováním paketů, které vás zajímají. 

Podívejte se na původní [blog](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458).

[Zpět na seznam](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a>Není možné se přihlásit k dříve vytvořenému HoloLens zařízení

Pokud bylo vaše zařízení dříve nastaveno pro někoho jiného, ať už pro klienta nebo pro bývalého zaměstnance, a nemáte [](/intune/remote-actions/devices-wipe) jeho heslo k odemknutí zařízení, můžete zařízení vzdáleně vymazat pomocí Intune. Zařízení se pak znovu bliká.  
> [!IMPORTANT]
> Po vymazání zařízení nechte nezaškrtnuté políčko Zachovat **stav registrace** a uživatelský účet.

[Zpět na seznam](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a>Po aktualizaci na Holographic 21H1 se Windows přihlásit

### <a name="symptoms"></a>Příznaky
- Po zadání správného KÓDU PIN se nepovede přihlásit pomocí kódu PIN.
- Použití metody přihlášení k webu po úspěšném přihlášení na webové stránce selže.
- Zařízení není uvedené v seznamu Připojeno k Azure AD [Azure Portal](https://portal.azure.com/) -> Azure Active Directory -> Zařízení.

### <a name="cause"></a>Příčina
Ovlivněné zařízení bylo pravděpodobně odstraněno z tenanta Azure AD. K tomu může dojít například z následujícího důvodu:

- Správce nebo uživatel odstranil zařízení v Azure Portal nebo pomocí PowerShellu.
- Zařízení se z tenanta Azure AD odebralo kvůli nečinnosti. V případě efektivně spravovaného prostředí obvykle doporučujeme správcům IT odebrat ze svého tenanta Azure AD zastaralá neaktivní [zařízení.](/azure/active-directory/devices/manage-stale-devices)

Když se ovlivněné zařízení pokusí po odstranění znovu kontaktovat tenanta Azure AD, ověření ve službě Azure AD se nezdaří. Tento účinek je často pro uživatele zařízení neviditelný, protože přihlášení uložené v mezipaměti prostřednictvím kódu PIN bude i nadále umožnovat přihlášení uživatele.

### <a name="mitigation"></a>Omezení rizik
V současné době neexistuje žádný způsob, jak přidat odstraněný HoloLens zařízení zpět do Azure AD. Ovlivněná zařízení se musí vyčistit a vyčistit podle pokynů k [kolikoli](hololens-recovery.md#clean-reflash-the-device)z těchto zařízení.

[Zpět na seznam](#list)

## <a name="autopilot-troubleshooting"></a>Řešení potíží s Autopilotem

Následující články mohou být užitečným zdrojem dalších informací a řešení potíží s Autopilotem. Články jsou ale založené na Windows 10 Desktopu a ne všechny informace se mohou vztahovat na HoloLens:

- [Windows Autopilot – známé problémy](/mem/autopilot/known-issues)
- [Řešení Windows problémů s registrací zařízení v Microsoft Intune](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot – Konflikty zásad](/mem/autopilot/policy-conflicts)

[Zpět na seznam](#list)

## <a name="managed-hololens-devices-faqs"></a>Nejčastější dotazy HoloLens spravovaných zařízeních

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a>Můžu ke správě System Center Configuration Manager zařízení použít HoloLens (SCCM)?

No. Ke správě zařízení v HoloLens MDM.

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a>Můžu ke správě Active Directory Domain Services účtů použít HoloLens (AD DS)?

No. Ke správě uživatelských účtů Azure Active Directory zařízení musíte použít Azure AD (HoloLens.

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a>Je HoloLens automatická registrace systémů ADCS (Automated Data Capture Systems)?

No.

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a>Můžete HoloLens integrovaného ověřování Windows ověřování?

No.

### <a name="does-hololens-support-branding"></a>Podporuje HoloLens branding?

No. Tento problém ale můžete obvyřešit pomocí jednoho z následujících přístupů:

- Vytvořte vlastní aplikaci a pak [povolte bezobrazovkové režim.](hololens-kiosk.md) Vlastní aplikace může mít branding a může spouštět další aplikace (například Remote Assist).  
- Změňte všechny profilové obrázky uživatelů v Azure AD na logo vaší společnosti. To však nemusí být žádoucí pro všechny scénáře.

### <a name="what-logging-capabilities-does-hololens-2-offer"></a>Jaké možnosti protokolování nabízí HoloLens 2?

Protokolování je omezené na trasování, která je možné zachytit ve scénářích vývoje nebo řešení potíží, nebo telemetrii, kterou zařízení odesílala na servery Microsoftu.

## <a name="questions-about-securing-hololens-devices"></a>Dotazy týkající se zabezpečení HoloLens zařízení

Podívejte [se na HoloLens 2 zabezpečení.](security-overview.md)
Další HoloLens 1. generace najdete v [nejčastějších dotazech.](hololens1-faq-security.yml)

[Zpět na seznam](#list)
