---
title: Správa aktualizací HoloLens
description: Zjistěte, jak můžou správci používat správu mobilních zařízení ke správě aktualizací zařízení HoloLens.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
audience: ITPro
ms.topic: article
ms.localizationpriority: high
ms.date: 10/13/2020
ms.reviewer: jarrettr
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.custom:
- CI 116337
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: faa6bb2b095d69c3538063b1c042c5ce5e215d33
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924073"
---
# <a name="manage-hololens-updates"></a>Správa aktualizací HoloLens

HoloLens používá služba Windows Update stejným způsobem jako ostatní Windows 10 zařízení. Když je k dispozici aktualizace, automaticky se stáhne a nainstaluje při příštím připojení zařízení k internetu. Tento článek popisuje, jak spravovat aktualizace v podnikovém nebo jiném spravovaném prostředí. Informace o správě aktualizací jednotlivých zařízení HoloLens najdete v tématu [Aktualizace HoloLens.](hololens-update-hololens.md)

## <a name="manage-updates-automatically"></a>Automatická správa aktualizací

### <a name="managing-updates-by-using-windows-update-for-business"></a>Správa aktualizací pomocí Windows Update pro firmy

Windows Holographic for Business ke správě [Windows Update pro firmy](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) můžete použít nástroj . Všechna zařízení HoloLens 2 používejte Windows Holographic for Business. Ujistěte se, že Windows Holographic for Business sestavení 10.0.18362.1042 nebo novější. Pokud máte zařízení HoloLens (1. generace), musíte je upgradovat tak, aby [Windows Holographic for Business](hololens1-upgrade-enterprise.md) spravovat jejich aktualizace.

Windows Update pro firmy zařízení HoloLens přímo ke službě služba Windows Update. Pomocí Windows Update pro firmy můžete řídit několik aspektů procesu aktualizace, to znamená, která zařízení chystá aktualizace &mdash; v jaké době. Můžete například pro účely testování zacílíte aktualizace podmnožiny zařízení a později aktualizace zbývajících zařízení. Nebo můžete definovat různé plány aktualizací pro různé typy aktualizací.

> [!NOTE]  
> Pro zařízení HoloLens můžete automaticky spravovat aktualizace funkcí (vydané dvakrát ročně) a aktualizace kvality (vydané každý měsíc nebo podle potřeby, včetně důležitých aktualizací zabezpečení). Další informace o typech aktualizací najdete v tématu [Typy aktualizací spravované Windows Update pro firmy](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).

Nastavení Windows Update pro firmy HoloLens můžete nakonfigurovat pomocí zásad v řešení MDM (Mobile Správa zařízení), jako je Microsoft Intune.

### <a name="managing-windows-update-for-business-by-using-microsoft-intune"></a>Správa Windows Update pro firmy pomocí Microsoft Intune

Podrobný popis použití Intune ke konfiguraci Windows Update pro firmy najdete v tématu Správa [Windows 10 aktualizací softwaru v Intune.](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure) Další informace o konkrétních funkcích Intune, které HoloLens podporuje, najdete v tématu Funkce správy aktualizací [Intune, které HoloLens podporuje.](#intune-update-management-functions-that-hololens-supports)

> [!IMPORTANT]  
> Intune poskytuje dva typy zásad pro správu aktualizací: *Windows 10 aktualizační okruh* *a Windows 10 aktualizace funkcí*. Typ Windows 10 aktualizace funkcí je v tuto chvíli ve verzi Public Preview a holoLens ho nepodporuje.
>  
> Ke správě aktualizací Windows 10 HoloLens 2 můžete použít zásady aktualizačního okruhu.

### <a name="configure-update-policies-for-hololens-2-or-hololens-1st-gen"></a>Konfigurace zásad aktualizace pro HoloLens 2 nebo HoloLens (1. generace)

Tato část popisuje zásady, které můžete použít ke správě aktualizací pro HoloLens 2 nebo HoloLens (1. generace). Další informace o funkcích, které jsou k dispozici pro HoloLens 2, najdete v tématu Plánování a konfigurace kumulativních aktualizací [pro HoloLens 2.](#plan-and-configure-update-rollouts-for-hololens-2)

[CsP zásad – Aktualizace](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) definuje zásady, které konfigurují Windows Update pro firmy.

> [!NOTE]  
> Seznam konkrétních poskytovatelů konfiguračních služeb zásad podporovaných konkrétními edicemi HoloLens najdete v tématu Poskytovatelé CSP zásad podporovaní [zařízeními HoloLens.](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices)

#### <a name="configure-automatic-checks-for-updates"></a>Konfigurace automatických kontrol aktualizací

Zásady **Update/AllowAutoUpdate** můžete použít ke správě chování automatických aktualizací, jako je kontrola, stahování a instalace aktualizací. Další informace o dostupných nastaveních pro tuto zásadu najdete v tématu [Aktualizace/AllowAutoUpdate.](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)

> [!NOTE]  
> V Microsoft Intune můžete tuto zásadu  změnit pomocí chování automatické aktualizace. Další informace najdete v tématu [Správa Windows 10 aktualizací softwaru v Intune.](https://docs.microsoft.com/intune/windows-update-for-business-configure)

#### <a name="configure-an-update-schedule"></a>Konfigurace plánu aktualizací

Pokud chcete nakonfigurovat, jak a kdy se mají aktualizace použít, použijte následující zásady:

- [Update/ScheduledInstallDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - Hodnoty: **0–7**(0 = každý den, 1 = neděle, 7 = sobota)
  - Výchozí hodnota: **0** (každý den)
- [Update/ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - Hodnoty: 0–23 (0 = půlnoc, 23 = 21 PM)
  - Výchozí hodnota: 3:00

#### <a name="configure-active-hours"></a>Konfigurace aktivních hodin
Od [Windows Holographic verze 20H2](hololens-release-notes.md#windows-holographic-version-20h2) může správce IT určit rozsah aktivních hodin pro zařízení HoloLens 2.

Aktivní hodiny identifikují časové období, kdy očekáváte, že se zařízení bude používat. Automatické restartování po aktualizaci se projeví mimo aktivní hodiny. Zadaný rozsah se bude počítat od počátečního času aktivních hodin. Můžete použít MDM, jak je popsáno v tématu [Konfigurace aktivních hodin pomocí MDM.](https://docs.microsoft.com/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm) MDM používá nastavení Update/ActiveHoursStart a Update/ActiveHoursEnd a Update/ActiveHoursMaxRange v csP zásad ke konfiguraci aktivních hodin.

-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend) – tato hodnota nastaví čas ukončení. Od počátečního času je k dispozici maximálně 12 hodin.
    -   Podporované hodnoty jsou 0–23, kde 0 je 12:00, 1 je 1:00 atd.
    -   Výchozí hodnota je 17 (17:00).
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) – Tato hodnota nastaví maximální počet aktivních hodin od počátečního času.
    -   Podporované hodnoty jsou 8 až 18.
    -   Výchozí hodnota je 18 (hodiny).
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart) – Tato hodnota nastaví čas spuštění. Od koncového času je k dispozici maximálně 12 hodin.
    -   Podporované hodnoty jsou 0–23, kde 0 je 12:00, 1 je 1:00 atd.
    -   Výchozí hodnota je 8 (8:00).

#### <a name="for-devices-that-run-windows-10-version-1607-only"></a>Pouze pro zařízení s Windows 10 verze 1607

Následující zásady aktualizací můžete použít ke konfiguraci zařízení pro získání aktualizací ze služby Windows Server Update Service (WSUS) místo ze služby služba Windows Update:

- [Update/AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Aktualizace/RequireUpdateApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <a name="plan-and-configure-update-rollouts-for-hololens-2"></a>Plánování a konfigurace aktualizací pro HoloLens 2

HoloLens 2 podporuje více funkcí pro automatizaci aktualizací než HoloLens (1. generace). To platí zejména v případě, že Microsoft Intune ke správě Windows Update pro firmy zásad. Tyto funkce usnadňují plánování a implementaci zavedení aktualizací v celé organizaci.

#### <a name="plan-the-update-strategy"></a>Plánování strategie aktualizace

Aktualizace Windows pro firmy podporují zásady odložení. Po vydání aktualizace můžete pomocí zásad odložení definovat, jak dlouho se má čekat před instalací této aktualizace na zařízeních. Když přidružíte podmnožiny vašich zařízení (označované také jako aktualizační okruhy) k různým zásadám odložení, můžete koordinovat strategii pro zasouvání aktualizací pro vaši organizaci.

Představte si například organizaci, která má 1 000 zařízení a musí je aktualizovat v pěti vlnách. Organizace může vytvořit pět aktualizačních okruhů, jak je znázorněno v následující tabulce.

|Group (Skupina) |Počet zařízení |Odložení (dny) |
| ---| :---: | :---: |
|Grp 1 (pracovníci IT) |5 |0 |
|Grp 2 (ti, kteří si ho osvojí v rané fázi) |50 |60 |
|Grp 3 (hlavní 1) |250 |120 |
|Grp 4 (hlavní 2) |300 |150 |
|Grp 5 (hlavní 3) |395 |180 |

Tady je postup, jak se bude v průběhu času zavánět do celé organizace.

![Časová osa pro nasazení aktualizací](./images/hololens-updates-timeline.png)

#### <a name="configure-an-update-deferral-policy"></a>Konfigurace zásad odložení aktualizací

Zásada odložení určuje počet dní mezi datem, kdy se aktualizace stane dostupnou, a datem, kdy se aktualizace zařízení nabízí.

Můžete nakonfigurovat různé odložení aktualizací funkcí a aktualizací kvality. V následující tabulce jsou uvedeny konkrétní zásady, které se mají použít pro jednotlivé typy, a maximální počet odložení pro každý z nich.

|Kategorie |Zásady |Maximální odložení |
| --- | --- | --- |
|Aktualizace funkcí |DeferFeatureUpdatesPeriodInDays |365 dní |
|Aktualizace kvality |DeferQualityUpdatesPeriodInDays |30 dní |

#### <a name="pause-updates-via-device"></a>Pozastavit aktualizace přes zařízení

Pokud uživatel nemá přístup k MDM, může ručně pozastavit aktualizace až 35 dní na zařízení HoloLens 2 na buildu [Windows holografick, verze 2004](hololens-release-notes.md#windows-holographic-version-2004) nebo novější. Uživatelé můžou toto nastavení dosáhnout tak, že přejdete na **nastavení > aktualizace & zabezpečení > rozšířené možnosti** posuňte se dolů a vyberete **datum, do** kterého budou aktualizace pozastaveny. Jakmile uživatel dosáhne limitu pozastavení, zařízení bude potřebovat nové aktualizace, než bude moct znovu pozastavit. 

Od [Windows holografické verze 20H2](hololens-release-notes.md#windows-holographic-version-20h2)se dá tuto funkci Pozastavení aktualizací spravovat pro zařízení HoloLens 2. 
- [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess).
    - 0 (výchozí) – povoleno
    - 1 – zakázáno

#### <a name="intune-update-management-functions-that-hololens-supports"></a>Funkce správy aktualizací Intune, které funkce HoloLens podporuje

Ke správě aktualizací pro HoloLens můžete použít následující funkce správy aktualizací Intune.

- **Vytvořit** a **přiřadit**: tyto funkce přidají aktualizační kanál Windows 10 do seznamu aktualizačních kanálů. Další informace najdete v tématu [Vytvoření a přiřazení aktualizačních kroužků](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings).

- **Pozastavení**: Pokud narazíte na problém při nasazení funkce nebo aktualizace kvality, můžete aktualizaci pozastavit na 35 dní (od zadaného data). Toto pozastavení zabraňuje instalaci aktualizace jiným zařízením, dokud problém nevyřešíte nebo nesnížíte. Pokud pozastavíte aktualizaci funkcí, jsou stále nabízeny aktualizace kvality, aby bylo zajištěno, že zůstanou v bezpečí. Když je typ aktualizace pozastaven, zobrazuje podokno přehled pro tento prstenec, kolik dní zbývá před tím, než se tento typ aktualizace obnoví. Po uplynutí zadaného času se pozastavení automaticky vyprší a proces aktualizace se obnoví.

  I když je aktualizační kanál pozastaven, můžete vybrat jednu z následujících možností:

  - **Rozšířené**: prodlužte dobu pozastavení pro typ aktualizace po dobu 35 dnů.
  - **Pokračovat**: obnovit aktualizace pro tento prstenec na aktivní operaci. Aktualizační kanál můžete znovu pozastavit, pokud je to nezbytné.

  > [!NOTE]  
  > Operace **odinstalace** pro aktualizační kanály není pro zařízení s HoloLens 2 podporovaná.

### <a name="delivery-optimization-preview"></a>Optimalizace doručování – náhled

[Windows holografické verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1) povolila nastavení optimalizace počáteční verze Preview pro doručování, aby se snížila spotřeba šířky pásma pro stahování z více zařízení HoloLens. Úplný popis této funkce spolu s doporučenou konfigurací sítě najdete tady: [Optimalizace doručení pro aktualizace Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization).

Následující nastavení jsou povolená jako součást plochy pro správu a [dají se nakonfigurovat z Intune](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings):

- [DOCacheHost](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Několik aspektů informací o této nabídce Preview:

- Podpora HoloLens je v této verzi Preview omezená jenom na aktualizace operačního systému.
- Windows Holografick pro firmy podporuje jenom režimy stahování HTTP a stažené soubory z [koncového bodu připojené mezipaměti Microsoftu](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache). režimy stahování peer-to-peer a přiřazení skupin se v tuto chvíli nepodporují pro zařízení HoloLens.
- HoloLens nepodporuje optimalizaci nasazení ani doručování pro koncové body Windows Server Update Services.
- Řešení potíží bude vyžadovat buď diagnostiku serveru připojené mezipaměti, nebo shromažďování trasování na HoloLens na HoloLens prostřednictvím   >  **aktualizace nastavení &**  >   **řešení potíží** se zabezpečením  >   **web Windows Update**.

## <a name="manually-check-for-updates"></a>Ručně vyhledat aktualizace

I když HoloLens pravidelně kontroluje aktualizace systému, můžou nastat okolnosti, při kterých budete chtít kontrolu provést ručně.

Pokud chcete aktualizace vyhledat ručně, vyhledejte aktualizace na webu **Nastavení**  >  **& aktualizace zabezpečení**  >  . Pokud aplikace nastavení indikuje, že vaše zařízení je aktuální, máte k dispozici všechny aktualizace, které jsou aktuálně k dispozici.

## <a name="manually-roll-back-an-update"></a>Ruční vrácení aktualizace zpět

V některých případech se můžete chtít vrátit k předchozí verzi softwaru HoloLens. Tento proces závisí na tom, zda používáte HoloLens 2 nebo HoloLens (1. generace).

### <a name="revert-to-a-previous-version-hololens-2"></a>Vrátit se k předchozí verzi (HoloLens 2)

Můžete vrátit zpět aktualizace a vrátit se k předchozí verzi HoloLens 2 pomocí [Průvodce pokročilým obnovením](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) a resetovat svoji HoloLens na předchozí verzi.

> [!NOTE]
> Návrat k předchozí verzi odstraní vaše osobní soubory a nastavení.

Chcete-li se vrátit k předchozí verzi HoloLens 2, použijte následující postup:

1. Ujistěte se, že do počítače nejsou zapojeny žádné telefony ani zařízení s Windows.
1. V počítači stáhněte z Microsoft Store [Průvodce rozšířeným obnovením](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) .
1. Stáhněte si nejnovější [verzi HoloLens 2](https://aka.ms/hololens2download).
1. Po dokončení těchto souborů ke stažení otevřete **Průzkumníka souborů**  >  , klikněte pravým tlačítkem na komprimovanou složku (.zip), kterou jste právě stáhli, a pak vyberte **Extrahovat vše**  >  **extrakce** , aby se soubor rozšířil.
1. K připojení zařízení HoloLens k počítači použijte kabel USB-A na USB-C. I v případě, že jste k připojení HoloLens používali jiné kabely, tento druh kabelu funguje nejlépe.
1. Průvodce pokročilým obnovením automaticky detekuje vaše zařízení HoloLens. Vyberte dlaždici **Microsoft HoloLens** .
1. Na další obrazovce vyberte možnost **Ruční výběr balíčku** a pak otevřete složku, kterou jste dříve rozbalili.
1. Vyberte soubor instalace (. FFU).
1. Vyberte **instalovat software** a pak postupujte podle pokynů.

### <a name="revert-to-a-previous-version-hololens-1st-gen"></a>Vrátit se k předchozí verzi (HoloLens (1. generace))

Můžete vrátit zpět aktualizace a vrátit se k předchozí verzi HoloLens (1. generace) pomocí [nástroje Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) a resetovat HoloLens na předchozí verzi.

> [!NOTE]
> Návrat k předchozí verzi HoloLens odstraní vaše osobní soubory a nastavení.

Chcete-li se vrátit k předchozí verzi HoloLens (1. generace), postupujte takto:

1. Ujistěte se, že do počítače nejsou zapojeny žádné telefony ani zařízení s Windows.
1. V počítači stáhněte [Nástroj Windows Device Recovery (WDRT)](https://support.microsoft.com/help/12379).
1. Stáhněte si [balíček pro obnovení aktualizace HoloLens výročí](https://aka.ms/hololensrecovery).
1. Po dokončení stahování otevřete **Průzkumníka souborů**  >  , klikněte pravým tlačítkem na komprimovanou složku (.zip), kterou jste právě stáhli, a pak vyberte **Extrahovat vše**  >  **extrakce** , aby se soubor rozšířil.
1. K připojení zařízení HoloLens k počítači použijte kabel Micro USB, který byl k dispozici spolu se zařízením HoloLens. I v případě, že jste k připojení svého zařízení HoloLens používali jiné kabely, je tato funkce nejvhodnější.
1. WDRT automaticky detekuje vaše zařízení HoloLens. Vyberte dlaždici **Microsoft HoloLens** .
1. Na další obrazovce vyberte možnost **Ruční výběr balíčku** a pak otevřete složku, kterou jste dříve rozbalili.
1. Vyberte soubor instalace (. FFU).
1. Vyberte **instalovat software** a pak postupujte podle pokynů.

**Pokud WDRT nerozpozná vaše zařízení**

Pokud WDRT nerozpozná vaše zařízení HoloLens, zkuste restartovat počítač. Pokud to nepomůže, vyberte **Moje zařízení se nezjistilo**, vyberte **Microsoft HoloLens** a pak postupujte podle pokynů.

## <a name="related-articles"></a>Související články

- [Poznámky k verzi HoloLens 2](https://docs.microsoft.com/hololens/hololens-release-notes)
- [Co je web Windows Update pro firmy?](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [Přiřazení zařízení k kanálům pro údržbu pro aktualizace Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Správa softwarových aktualizací Windows 10 v Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
