---
title: Implementace HoloLens 2 a řešení potíží se spravovaným zařízením
description: Řešení potíží s zařízeními HoloLens 2 v podnikovém prostředí
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
ms.openlocfilehash: 911e5b9494eae00ace8007ee6a29b30e6aaf98dd
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961634"
---
# <a name="troubleshooting-implementation-and-managed-devices"></a>Řešení potíží s implementací a spravovanými zařízeními 

Tento článek popisuje, jak vyřešit několik problémů nebo zodpovědět otázky týkající se implementace a správy HoloLens 2.

>[!IMPORTANT]
> Než začnete s postupem řešení potíží, ujistěte se, že se na zařízení účtuje **20 až 40 procent** kapacity baterie, pokud je to možné. [Indikátory baterie](hololens2-setup.md#lights-that-indicate-the-battery-level) umístěné pod tlačítkem napájení jsou rychlým způsobem, jak ověřit kapacitu baterie bez přihlášení do zařízení.


<a id="list"></a>
- [Řešení potíží s protokolem EAP](#eap-troubleshooting)
- [Řešení potíží Wi-Fi](#wi-fi-troubleshooting)
- [Řešení potíží se sítí](#network-troubleshooting)
- [Nejde se přihlásit k dřív nastavenému zařízení HoloLens.](#cant-sign-in-to-a-previously-setup-hololens-device)
- [Po aktualizaci na holografickou 21H1 se nedá přihlásit.](#cant-login-after-updating-to-windows-holographic-21h1)
- [Řešení potíží s autopilotem](#autopilot-troubleshooting)
- [Nejčastější dotazy ke spravovaným zařízením HoloLens](#managed-hololens-devices-faqs)

## <a name="eap-troubleshooting"></a>Řešení potíží s protokolem EAP
1. Dvojitá check Wi-Fi profil má správné nastavení:
    - Typ protokolu EAP je správně nakonfigurovaný, běžné typy protokolu EAP: EAP-TLS (13), EAP-TTLS (21) a PEAP (25).
    - Název SSID Wi-Fi je vpravo a odpovídá řetězci HEX.
    - Pro EAP-TLS obsahuje TrustedRootCA hodnotu hash SHA-1 certifikátu důvěryhodné kořenové certifikační autority serveru. V počítači s Windows "certutil.exe-dump cert_file_name" příkaz zobrazí řetězec hash SHA-1 certifikátu.
2. Shromažďovat Zachytávání síťových paketů v protokolech přístupového bodu nebo řadiči serveru AAA, kde zjistíte, kde se relace protokolu EAP nezdařila.
    - Pokud není očekávána Identita protokolu EAP poskytovaná pomocí HoloLens, ověřte, zda byla identita správně zajištěna prostřednictvím profilu Wi-Fi nebo klientského certifikátu.
    - Pokud server odmítne klientský certifikát HoloLens, ověřte, jestli je na zařízení požadovaný klientský certifikát zřízený.
    - Pokud HoloLens odmítne certifikát serveru, ověřte, jestli je certifikát kořenové certifikační autority serveru zřízený na HoloLens.
3. Pokud se profil Enterprise zřídí prostřednictvím balíčku pro Wi-Fi zřizování, zvažte použití zřizovacího balíčku na počítači s Windows 10. Pokud se to nepovede i na počítači s Windows 10, postupujte podle Průvodce odstraňováním potíží s ověřováním klienta ve Windows 802.1 X.
4. Pošlete nám svůj názor prostřednictvím centra zpětné vazby.

[Zpět na seznam](#list)

## <a name="wi-fi-troubleshooting"></a>Řešení potíží s Wi-Fi

Tady je několik věcí, které můžete vyzkoušet, pokud nemůžete připojit svoji HoloLens k Wi-Fi síti:

1. Ujistěte se, že je zapnutá Wi-Fi. Chcete-li kontrolu ověřit, použijte gesto Start a pak vyberte nastavení > síť & Internet > Wi-Fi. Pokud je Wi-Fi zapnutá, zkuste ji vypnout a znovu zapnout.
2. Posuňte se blíž ke směrovači nebo přístupovému bodu.
3. Restartujte směrovač Wi-Fi a pak restartujte HoloLens. Zkuste se znovu připojit.
4. Pokud žádná z těchto věcí nefunguje, zkontrolujte, zda směrovač používá nejnovější firmware. Tyto informace najdete na webu výrobce.

Když se na zařízení přihlašujete k podnikovému nebo organizačnímu účtu, může taky použít zásady správy mobilních zařízení (MDM), pokud je zásada nakonfigurovaná správcem IT.

## <a name="network-troubleshooting"></a>Řešení potíží se sítí
Pokud jsou problémy se sítí překážkou úspěšného nasazení a používání HoloLens 2 ve vaší organizaci, přečtěte si, jak vám dva dobře známé nástroje pro diagnostiku sítě, Fiddler a Wireshark můžou pomoci při prohledávání, diagnostice a identifikaci problémů. Další podrobnosti najdete na tomto [blogu](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/diagnose-hololens-2-network-issues-with-fiddler-and-wireshark/ba-p/2322458) .

[Zpět na seznam](#list)

## <a name="cant-sign-in-to-a-previously-setup-hololens-device"></a>Nejde se přihlásit k dřív nastavenému zařízení HoloLens.

Pokud jste zařízení dříve nastavili pro někoho jiného, buď pro klienta, nebo pro bývalého zaměstnance, a nemáte heslo k odemknutí zařízení, můžete pomocí Intune vzdáleně [Vymazat](https://docs.microsoft.com/intune/remote-actions/devices-wipe) zařízení. Zařízení se pak znovu zabliká.  
> [!IMPORTANT]
> Když zařízení vymažete, nezapomeňte ponechat **stav registrace a účet uživatele** nezaškrtnutý.
[Zpět na seznam](#list)

## <a name="cant-login-after-updating-to-windows-holographic-21h1"></a>Po aktualizaci na holografickou 21H1 se nedá přihlásit.

### <a name="symptoms"></a>Příznaky
- Po zadání správného kódu PIN se přihlášení pomocí kódu PIN nezdaří.
- Po úspěšném přihlášení na webové stránce se použití metody přihlášení k webu nezdaří.
- Zařízení není uvedené jako "Azure AD JOIN" v [Azure Portal](https://portal.azure.com/) > zařízení Azure Active Directory >.

### <a name="cause"></a>Příčina
Ovlivněné zařízení mohlo být odstraněno z tenanta Azure AD. K tomu může dojít například z těchto důvodů:

- Správce nebo uživatel zařízení odstranil v Azure Portal nebo pomocí PowerShellu.
- Zařízení se odebralo z tenanta Azure AD kvůli nečinnosti. Pro efektivní spravované prostředí typicky doporučujeme správcům IT [odebírat ze svého tenanta Azure AD zastaralé neaktivní zařízení](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices).

Když se zasažené zařízení pokusí kontaktovat tenanta Azure AD znovu po jeho odstranění, nepodaří se mu ověřit pomocí Azure AD. Tento efekt je často neviditelný pro uživatele zařízení, protože přihlášení do mezipaměti prostřednictvím kódu PIN bude dál umožňovat přihlášení uživatele.

### <a name="mitigation"></a>Omezení rizik
V současné době neexistuje způsob, jak přidat odstraněné zařízení HoloLens zpátky do služby Azure AD. Ovlivněná zařízení bude potřeba vyčistit, a to podle pokynů při [přeblikání zařízení](hololens-recovery.md#clean-reflash-the-device).

## <a name="autopilot-troubleshooting"></a>Řešení potíží s autopilotem

Následující články můžou být užitečným prostředkem, abyste si mohli přečíst další informace a řešit problémy s výkonem pro autopilot, ale pamatujte na to, že tyto články jsou založené na Windows 10 desktopu a ne všechny informace se můžou vztahovat na HoloLens:

- [Windows autopilot – známé problémy](https://docs.microsoft.com/mem/autopilot/known-issues)
- [Řešení potíží s registrací zařízení s Windows v Microsoft Intune](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows autopilot – konflikty zásad](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <a name="managed-hololens-devices-faqs"></a>Nejčastější dotazy ke spravovaným zařízením HoloLens

### <a name="can-i-use-system-center-configuration-manager-sccm-to-manage-hololens-devices"></a>Můžu pomocí System Center Configuration Manager (SCCM) spravovat zařízení HoloLens?

No. Ke správě zařízení HoloLens je nutné použít systém MDM.

### <a name="can-i-use-active-directory-domain-services-ad-ds-to-manage-hololens-user-accounts"></a>Můžu k správě uživatelských účtů HoloLens použít Active Directory Domain Services (služba AD DS)?

No. K řízení uživatelských účtů pro zařízení HoloLens je nutné použít Azure Active Directory (Azure AD).

### <a name="is-hololens-capable-of-automated-data-capture-systems-adcs-auto-enrollment"></a>Podporuje automatické registrace systému HoloLens (Automated data Capture)?

No.

### <a name="can-hololens-participate-in-integrated-windows-authentication"></a>Je možné použít HoloLens v integrovaném ověřování systému Windows?

No.

### <a name="does-hololens-support-branding"></a>Podporuje HoloLens pracovní značku?

No. Tento problém ale můžete obejít pomocí jednoho z následujících přístupů:

- Vytvořte vlastní aplikaci a pak [Povolte celoobrazovkový režim](hololens-kiosk.md). Vlastní aplikace může mít branding a může spouštět jiné aplikace (například vzdálenou pomoc).  
- Změňte všechny obrázky profilů uživatelů ve službě Azure AD na logo vaší společnosti. To však nemusí být žádoucí pro všechny scénáře.

### <a name="what-logging-capabilities-does-hololens-2-offer"></a>Jaké možnosti protokolování nabízí možnost HoloLens 2?

Protokolování je omezené na trasování, která se dají zachytit ve scénářích vývoje nebo řešení potíží, nebo telemetrie, kterou zařízení odesílají na servery Microsoftu.

## <a name="questions-about-securing-hololens-devices"></a>Dotazy týkající se zabezpečení zařízení HoloLens

Podívejte se na [informace o zabezpečení HoloLens 2](security-overview.md).
V případě HoloLens 1 pro obecné zařízení si přečtěte [Tyto nejčastější dotazy](hololens1-faq-security.md).

[Zpět na seznam](#list)
