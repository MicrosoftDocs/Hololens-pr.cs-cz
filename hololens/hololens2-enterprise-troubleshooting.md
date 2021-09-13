---
title: HoloLens 2 implementace a řešení potíží se spravovaným zařízením
description: řešení potíží s HoloLens 2 zařízeními v prostředí Enterprise
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
ms.openlocfilehash: 9f3950de51e4bfa2a76431a2a070d87aa81ed443
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126035959"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a>Řešení potíží s implementací a spravovanými zařízeními 

tento článek popisuje, jak vyřešit několik problémů nebo odpovědi na otázky týkající se implementace a správy HoloLens 2.

>[!IMPORTANT]
> Než začnete s postupem řešení potíží, ujistěte se, že se na zařízení účtuje **20 až 40 procent** kapacity baterie, pokud je to možné. [Indikátory baterie](hololens2-setup.md#lights-that-indicate-the-battery-level) umístěné pod tlačítkem napájení jsou rychlým způsobem, jak ověřit kapacitu baterie bez přihlášení do zařízení.


<a id="list"></a>
- [Řešení potíží s protokolem EAP](#eap-troubleshooting)
- [Řešení potíží Wi-Fi](#wi-fi-troubleshooting)
- [Řešení potíží se sítí](#network-troubleshooting)
- [nepovedlo se přihlásit k dřív nastavenému HoloLens zařízení.](#cant-sign-in-to-a-previously-setup-hololens-device)
- [po aktualizaci na Windows holografické 21H1 se nedá přihlásit.](#cant-login-after-updating-to-windows-holographic-21h1)
- [Řešení potíží s autopilotem](#autopilot-troubleshooting)
- [nejčastější dotazy týkající se spravovaných HoloLens zařízení](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a>Řešení potíží s protokolem EAP
1. Dvojitá check Wi-Fi profil má správné nastavení:
    - Typ protokolu EAP je správně nakonfigurovaný, běžné typy protokolu EAP: EAP-TLS (13), EAP-TTLS (21) a PEAP (25).
    - Název SSID Wi-Fi je vpravo a odpovídá řetězci HEX.
    - Pro EAP-TLS obsahuje TrustedRootCA hodnotu hash SHA-1 certifikátu důvěryhodné kořenové certifikační autority serveru. v Windows počítači "certutil.exe-dump cert_file_name" příkaz zobrazí řetězec hash SHA-1 certifikátu.
2. Shromažďovat Zachytávání síťových paketů v protokolech přístupového bodu nebo řadiči serveru AAA, kde zjistíte, kde se relace protokolu EAP nezdařila.
    - pokud se neočekává identita EAP, kterou poskytuje HoloLens, ověřte, jestli se identita správně zřídila prostřednictvím profilu Wi-Fi nebo klientského certifikátu.
    - pokud server odmítne HoloLens klientský certifikát, ověřte, jestli je na zařízení požadovaný klientský certifikát zřízený.
    - pokud HoloLens odmítne certifikát serveru, ověřte, zda byl certifikát kořenové certifikační autority serveru zřízený v HoloLens.
3. pokud se profil rozlehlé sítě zřídí prostřednictvím balíčku pro Wi-Fi zřizování, zvažte použití zřizovacího balíčku na počítači s Windows 10. pokud se také na Windows 10 počítači nepovede, postupujte podle příručky Windows klienta řešení potíží s ověřováním 802.1 x.
4. Pošlete nám svůj názor prostřednictvím centra zpětné vazby.

[Zpět na seznam](#list)

## <a name="wi-fi-troubleshooting"></a>Řešení potíží s Wi-Fi

tady je několik věcí, které můžete vyzkoušet, pokud nemůžete připojit HoloLens k síti Wi-Fi:

1. Ujistěte se, že je zapnutá Wi-Fi. pokud chcete kontrolu ověřit, použijte gesto Start a pak vyberte Nastavení > síti & Internet > Wi-Fi. Pokud je Wi-Fi zapnutá, zkuste ji vypnout a znovu zapnout.
2. Posuňte se blíž ke směrovači nebo přístupovému bodu.
3. Restartujte směrovač Wi-Fi a pak znovu spusťte HoloLens. Zkuste se znovu připojit.
4. Pokud žádná z těchto věcí nefunguje, zkontrolujte, zda směrovač používá nejnovější firmware. Tyto informace najdete na webu výrobce.

Když se na zařízení přihlašujete k podnikovému nebo organizačnímu účtu, může taky použít zásady správy mobilních zařízení (MDM), pokud je zásada nakonfigurovaná správcem IT.

[Zpět na seznam](#list)

## <a name="network-troubleshooting"></a>Řešení potíží se sítí
pokud jsou problémy se sítí překážkou úspěšného nasazení a používání HoloLens 2 ve vaší organizaci, nakonfigurujte Fiddler a/nebo Wireshark pro zachycení a analýzu přenosů HTTP/HTTPS. 

### <a name="configure-fiddler-to-capture-http-traffic"></a>Konfigurace Fiddler pro zachycení přenosů HTTP
Fiddler je webový ladicí proxy server, který se používá k odstraňování potíží s HTTP (S). Zachycuje všechny požadavky HTTP, které počítač provede, a zaznamená všechny přidružené k němu. řešení potíží s ověřováním koncových uživatelů pro vaše aplikace HTTPS vám umožní lépe zvýšit produktivitu a efektivitu pro cíle HoloLens 2 případy použití. 

#### <a name="prerequisites"></a>Požadavky
 
- zařízení HoloLens 2 a váš počítač musí být ve stejné síti.
- Poznamenejte si IP adresu vašeho počítače.

#### <a name="install-and-configure-fiddler"></a>Instalace a konfigurace Fiddler

1. Na počítači [nainstalujte](https://docs.telerik.com/fiddler-everywhere/get-started/installation-procedure) a spusťte Fiddler.  
1. V počítači nakonfigurujte Fiddler tak, aby umožňovaly připojení vzdálených počítačů.
    1. přejít na Fiddler Nastavení-> připojení
    1. Všimněte si, že port naslouchání pro Fiddler (výchozí je 8866)
    1. Ověřte, jestli se mají vzdálené počítače připojit.
    1. Kliknutí na Uložit
3. v HoloLens 2 – nakonfigurujte Fiddler jako proxy server<sup>1</sup>:
    1. otevřete nabídka Start a vyberte Nastavení
    1. V nabídce vlevo vyberte Network & Internet a pak proxy.
    1. Přejděte dolů na ruční nastavení proxy serveru a přepínač použít proxy server na zapnuto.
    1. Zadejte IP adresu počítače, kde je nainstalovaný Fiddler.
    1. Zadejte číslo portu, které jste si poznamenali (výchozí je 8866).
    1. Kliknutí na Uložit

<sup>1</sup> pro sestavení 20279.1006 + (Insiders a nadcházející verze) použijte následující postup ke konfiguraci proxy serveru:
1. otevřete nabídka Start a přejít na stránku vlastností vaší Wi-Fi sítě. 
1. Posunout dolů na proxy
1. Změnit na ruční instalaci
1. Zadejte IP adresu počítače, kde je nainstalovaný Fiddler.
1. Zadejte číslo portu, které jste si poznamenali výše. (výchozí hodnota je 8866)
1. Klikněte na použít.
    
#### <a name="decrypt-https-traffic-from-hololens-2"></a>dešifrování provozu HTTPS z HoloLens 2

1. V počítači – exportujte certifikát Fiddler.
    1. přejít na Fiddler Nastavení-> HTTPS a rozšířit upřesnit Nastavení
    2. Klikněte na exportovat certifikát Fiddler. Uloží se na vaši plochu.
    3. přesuňte certifikát do složky stažené soubory ve vašem HoloLens 2

2.  v HoloLens 2 – importujte certifikát Fiddler.
    1. přejít na Nastavení > aktualizace a certifikáty > zabezpečení
    2. Klikněte na nainstalovat certifikát, přejděte do složky Stažené soubory a vyberte certifikát Fiddler.
    3. Změnit umístění úložiště na místní počítač
    4. Změnit úložiště certifikátů na kořen
    5. Vybrat instalaci
    6. Potvrďte, že se certifikát zobrazuje v seznamu certifikátů. V takovém případě opakujte výše uvedené kroky.

#### <a name="inspect-https-sessions"></a>Zkontrolovat relace HTTP (S)

v počítači se v Fiddler zobrazí relace HTTP (s), které jsou v provozu HoloLens 2. Panel inspektorů v Fiddler může v různých zobrazeních zobrazit požadavek nebo odpověď HTTP – například "hrubé" zobrazení zobrazuje nezpracovaný požadavek nebo odpověď v prostém textu. 

### <a name="configure-wireshark-to-capture-network-traffic"></a>Konfigurace Wireshark pro zachycení síťového provozu
nástroj Wireshark je analyzátor síťových protokolů a slouží ke kontrole provozu TCP/UDP z a do zařízení HoloLens 2. to usnadňuje identifikaci provozu, který se předává do vaší sítě HoloLens 2, jak často se jedná o četnost latence mezi určitým segmentem směrování a tak dále.

#### <a name="prerequisites"></a>Požadavky:
- POČÍTAČ musí mít přístup k Internetu a podporovat sdílení internetu přes Wi-Fi

#### <a name="install-and-configure-wireshark"></a>Instalace a konfigurace Wireshark
1. V počítači nainstalujte nástroj [Wireshark](https://www.wireshark.org/#download) 
1. Ve vašem počítači – povolte mobilnímu hotspotu sdílení připojení k Internetu z Wi-Fi.
1. Na počítači spusťte Nástroj Wireshark a zachyťte provoz z rozhraní mobilní hotspot. 
1. v HoloLens 2 – změňte svou Wi-Fi síť na mobilní hotspot počítače. v nástroji Wireshark se zobrazí HoloLens 2 provoz IP.

#### <a name="analyze-wireshark-logs"></a>Analyzovat protokoly Wireshark
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
