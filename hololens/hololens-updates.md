---
title: Správa aktualizací HoloLens
description: Naučte se, jak můžou správci používat správu mobilních zařízení ke správě aktualizací na zařízeních HoloLens.
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
ms.openlocfilehash: 6c9d1551b2a3348a6ff9962180c2d5552eb100f1
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379257"
---
# <a name="manage-hololens-updates"></a>Správa aktualizací HoloLens

HoloLens používá web Windows Update stejným způsobem jako ostatní zařízení s Windows 10. Když je dostupná aktualizace, automaticky se stáhne a nainstaluje při příštím připojení zařízení k Internetu. Tento článek popisuje, jak spravovat aktualizace v podnikovém nebo jiném spravovaném prostředí. Informace o tom, jak spravovat aktualizace pro jednotlivá zařízení HoloLens, najdete v tématu [aktualizace HoloLens](hololens-update-hololens.md).

## <a name="manage-updates-automatically"></a>Spravovat aktualizace automaticky

### <a name="managing-updates-by-using-windows-update-for-business"></a>Správa aktualizací pomocí web Windows Update pro firmy

Windows Holografick pro firmy může pomocí [web Windows Update pro firmy](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) spravovat aktualizace. Všechna zařízení HoloLens 2 můžou používat Windows Holografick pro firmy. Ujistěte se, že používají sestavení Windows Holografick pro firmy Build 10.0.18362.1042 nebo novější. Pokud máte zařízení HoloLens (1. gen), musíte [je upgradovat na Windows holografick pro firmy](hololens1-upgrade-enterprise.md) , aby bylo možné spravovat jejich aktualizace.

Web Windows Update for Business připojí zařízení HoloLens přímo ke službě web Windows Update. Pomocí web Windows Update pro firmy můžete řídit více aspektů procesu aktualizace, které &mdash; zařízení získávají aktualizace v daném čase. Můžete například aktualizovat podmnožinu zařízení pro testování a pak později aktualizovat zbývající zařízení. Nebo můžete definovat různé plány aktualizací pro různé typy aktualizací.

> [!NOTE]  
> V případě zařízení HoloLens můžete automaticky spravovat aktualizace funkcí (vydaná dvakrát za rok) a aktualizace kvality (vydané měsíčně nebo podle potřeby, včetně důležitých aktualizací zabezpečení). Další informace o typech aktualizací najdete v tématu [typy aktualizací, které jsou spravovány web Windows Update pro firmy](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).

Nastavení web Windows Update pro firmy pro HoloLens můžete nakonfigurovat pomocí zásad v řešení správy mobilních zařízení (MDM), jako je například Microsoft Intune.

### <a name="managing-windows-update-for-business-by-using-microsoft-intune"></a>Správa web Windows Update pro firmy pomocí Microsoft Intune

Podrobnou diskuzi o tom, jak pomocí Intune nakonfigurovat web Windows Update pro firmy, najdete v tématu [Správa aktualizací softwaru Windows 10 v Intune](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure). Další informace o konkrétních funkcích Intune, které funkce HoloLens podporuje, najdete v tématu [funkce správy aktualizací Intune, které HoloLens podporuje](#intune-update-management-functions-that-hololens-supports).

> [!IMPORTANT]  
> Intune nabízí dva typy zásad pro správu aktualizací: *Windows 10 Update Ring* a *aktualizace funkcí Windows 10*. Typ zásad aktualizace funkcí Windows 10 je v současnosti ve verzi Public Preview a pro HoloLens se nepodporuje.
>  
> Pomocí zásad Windows 10 Update Ring můžete spravovat aktualizace HoloLens 2.

### <a name="configure-update-policies-for-hololens-2-or-hololens-1st-gen"></a>Konfigurace zásad aktualizace pro HoloLens 2 nebo HoloLens (1. generace)

Tato část popisuje zásady, které můžete použít ke správě aktualizací pro HoloLens 2 nebo HoloLens (1. generace). Další informace o funkcích, které jsou k dispozici pro HoloLens 2, naleznete v tématu [Plan and Configure Update uvádění for HoloLens 2](#plan-and-configure-update-rollouts-for-hololens-2).

[Zásada CSP – aktualizace](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) definuje zásady, které konfigurují web Windows Update pro firmy.

> [!NOTE]  
> Seznam konkrétních zprostředkovatelů konfiguračních služeb (CSP), které jsou podporovány konkrétními edicemi HoloLens, najdete v tématu [Zprostředkovatelé CSP, kteří podporují zařízení HoloLens](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices).

#### <a name="configure-automatic-checks-for-updates"></a>Konfigurace automatických kontrol aktualizací

Pomocí zásad **Update/AllowAutoUpdate** můžete spravovat chování automatických aktualizací, jako je skenování, stahování a instalace aktualizací. Další informace o dostupných nastaveních pro tuto zásadu najdete v tématu [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).

> [!NOTE]  
> V Microsoft Intune můžete pro změnu těchto zásad použít **chování funkce Automatické aktualizace** . Další informace najdete v tématu [Správa aktualizací softwaru Windows 10 v Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).

#### <a name="configure-an-update-schedule"></a>Konfigurovat plán aktualizací

Pokud chcete nakonfigurovat, jak a kdy se aktualizace použijí, použijte následující zásady:

- [Aktualizovat/ScheduledInstallDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - Hodnoty: **0**–**7** (0 = každý den, 1 = neděle, 7 = sobota)
  - Výchozí hodnota: **0** (každý den)
- [Aktualizovat/ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - Hodnoty: 0 – 23 (0 = půlnoc, 23 = 11 odp)
  - Výchozí hodnota: 3 ODP.

#### <a name="configure-active-hours"></a>Konfigurovat aktivní hodiny
Od [Windows holografické verze 20H2](hololens-release-notes.md#windows-holographic-version-20h2) může správce IT zadat rozsah aktivních hodin pro zařízení HoloLens 2.

Aktivní hodiny identifikují dobu, po kterou se zařízení bude používat. Automatické restartování po aktualizaci proběhne mimo aktivní hodiny. Zadaný rozsah bude počítán od počátečního času aktivní hodiny. Můžete použít MDM, jak je popsáno v tématu [Konfigurace aktivních hodin s MDM](https://docs.microsoft.com/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm). MDM používá nastavení Update/ActiveHoursStart a Update/ActiveHoursEnd a Update/ActiveHoursMaxRange v zásadách CSP ke konfiguraci aktivních hodin.

-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend) – tato hodnota nastaví čas ukončení. Od počátečního času je maximum 12 hodin.
    -   Podporované hodnoty jsou 0-23, kde 0 je 12 DOP, 1 je 1 dop. atd.
    -   Výchozí hodnota je 17 (5 odp.).
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) – tato hodnota nastaví maximální počet aktivních hodin od počátečního času.
    -   Podporované hodnoty jsou 8-18.
    -   Výchozí hodnota je 18 (hodiny).
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart) – tato hodnota nastaví počáteční čas. Čas ukončení je 12 hodin.
    -   Podporované hodnoty jsou 0-23, kde 0 je 12 DOP, 1 je 1 dop. atd.
    -   Výchozí hodnota je 8 (ráno).

#### <a name="for-devices-that-run-windows-10-version-1607-only"></a>Pro zařízení s Windows 10 verze 1607

Pomocí následujících zásad aktualizace můžete nakonfigurovat zařízení k získání aktualizací ze služby Windows Server Update Service (WSUS) místo z web Windows Update:

- [Aktualizovat/AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Aktualizovat/RequireUpdateApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Aktualizovat/UpdateServiceUrl](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <a name="plan-and-configure-update-rollouts-for-hololens-2"></a>Plánování a konfigurace uvádění aktualizací pro HoloLens 2

HoloLens 2 podporuje více funkcí automatizace aktualizací než HoloLens (1. generace). To platí hlavně v případě, že používáte Microsoft Intune ke správě zásad web Windows Update pro firmy. Tyto funkce usnadňují plánování a implementaci uvádění aktualizací napříč vaší organizací.

#### <a name="plan-the-update-strategy"></a>Plánování strategie aktualizace

Aktualizace Windows pro firmy podporují zásady odložení. Jakmile společnost Microsoft uvolní aktualizaci, můžete použít zásadu odložení a určit, jak dlouho se má čekat před instalací této aktualizace na zařízení. Tím, že přidružíte podmnožiny zařízení (označované také jako *aktualizační* kanály) s různými zásadami odložení, můžete koordinovat strategii zavedení aktualizací pro vaši organizaci.

Představte si třeba organizaci, která má 1 000 zařízení, a musí aktualizovat zařízení v pěti vlny. Organizace může vytvořit pět aktualizačních kroužků, jak je znázorněno v následující tabulce.

|Group (Skupina) |Počet zařízení |Odložení (dny) |
| ---| :---: | :---: |
|GRP 1 (zaměstnanci oddělení IT) |5 |0 |
|GRP 2 (rané státy) |50 |60 |
|GRP 3 (hlavní 1) |250 |120 |
|GRP 4 (hlavní 2) |300 |150 |
|GRP 5 (hlavní 3) |395 |180 |

Tady je postup, jak postupovat v průběhu času na celou organizaci.

![Časová osa pro nasazování aktualizací](./images/hololens-updates-timeline.png)

#### <a name="configure-an-update-deferral-policy"></a>Konfigurace zásad odložení aktualizací

Zásada odložení určuje počet dní mezi datem, kdy bude aktualizace k dispozici a datum, kdy je aktualizace nabízena pro zařízení.

Pro aktualizace funkcí a aktualizace kvality můžete nakonfigurovat různé odložení. Následující tabulka uvádí konkrétní zásady, které se mají použít pro každý typ, a maximální odložení pro každý typ.

|Kategorie |Zásady |Maximální odložení |
| --- | --- | --- |
|Aktualizace funkcí |DeferFeatureUpdatesPeriodInDays |365 dnů |
|Aktualizace kvality |DeferQualityUpdatesPeriodInDays |30 dní |

#### <a name="pause-updates-via-device"></a>Pozastavení aktualizací přes zařízení

Pokud uživatel nemá přístup k MDM, může na zařízení HoloLens 2 na buildu [Windows Holographic verze 2004](hololens-release-notes.md#windows-holographic-version-2004) nebo novější pozastavit aktualizace po dobu až 35 dnů ručně. Uživatelé se k tomuto nastavení dostanou tak, že přechádnou nastavení **-> Update & Security -> Upřesnit** možnosti. Posuňte se dolů na Pozastavit aktualizace a vyberte datum, do kterého aktualizace pozastaví.  Jakmile uživatel dosáhne limitu pozastavení, bude muset zařízení získat nové aktualizace, protože se může pozastavit znovu. 

Od [Windows Holographic verze 20H2](hololens-release-notes.md#windows-holographic-version-20h2)je možné tuto funkci pozastavení aktualizací spravovat pro zařízení HoloLens 2. 
- [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess).
    - 0 (výchozí) – povoleno
    - 1 – Zakázáno

#### <a name="intune-update-management-functions-that-hololens-supports"></a>Funkce správy aktualizací v Intune, které HoloLens podporuje

Ke správě aktualizací pro HoloLens můžete použít následující funkce správy aktualizací Intune.

- **Vytvořit** a **přiřadit:** Tyto funkce Windows 10 aktualizační okruh do seznamu aktualizačních kanálů. Další informace najdete v tématu [Vytvoření a přiřazení aktualizačních okruhů.](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)

- **Pozastavit:** Pokud při nasazování funkce nebo aktualizace kvality narazíte na problém, můžete aktualizaci pozastavit na 35 dnů (od zadaného data). Toto pozastavení zabrání ostatním zařízením v instalaci aktualizace, dokud problém nevyřešíte nebo nezmírníte. Pokud aktualizaci funkcí pozastavíte, budou se zařízením pořád nabízeny aktualizace kvality, aby se zajistilo jejich zabezpečení. Když je typ aktualizace pozastavený, v podokně Přehled pro tento okruh se zobrazí, kolik dní zůstává před obnovením tohoto typu aktualizace. Po uplynutí zadané doby pozastavení automaticky vyprší a proces aktualizace se obnoví.

  Zatímco je aktualizační okruh pozastavený, můžete vybrat jednu z následujících možností:

  - **Prodloužení:** Prodloužení doby pozastavení pro typ aktualizace o 35 dnů.
  - **Obnovení:** Obnovte aktualizace pro tento okruh na aktivní operaci. Aktualizační okruh můžete v případě potřeby znovu pozastavit.

  > [!NOTE]  
  > Zařízení  HoloLens 2 nepodporují operaci odinstalace aktualizačních okruhů.

### <a name="delivery-optimization-preview"></a>Optimalizace doručení Preview

[Windows Holographic verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1) umožnila v rané verzi Preview nastavení optimalizace doručení, aby se snížila spotřeba šířky pásma pro stahování z několika zařízení HoloLens. Úplný popis této funkce spolu s doporučenou konfigurací sítě najdete tady: Optimalizace doručení [pro Windows 10 aktualizace.](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)

V rámci možností správy jsou povolená následující nastavení, [která je možné nakonfigurovat z Intune:](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings)

- [DoCacheHost](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DoCacheHostSource](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DoDownloadMode](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DoPercentageMaxForegroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Několik upozornění na tuto nabídku Verze Preview:

- Podpora HoloLens je v této verzi Preview omezená jenom na aktualizace operačního systému.
- Windows Holographic for Business podporuje pouze režimy stahování HTTP a stahování z koncového [bodu microsoft Připojená mezipaměť](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache); Režimy stahování peer-to-peer a přiřazení skupin se v tuto chvíli nepodporují pro zařízení HoloLens.
- HoloLens nepodporuje nasazení ani optimalizaci doručení pro Windows Server Update Services koncové body.
- Řešení potíží bude vyžadovat buď diagnostiku na serveru Připojená mezipaměť, nebo shromažďování trasování na HoloLensu na HoloLens prostřednictvím možnosti Aktualizace nastavení & Řešení potíží se  >    >     >   **zabezpečením služba Windows Update**.

## <a name="manually-check-for-updates"></a>Ruční kontrola aktualizací

I když HoloLens pravidelně kontroluje aktualizace systému, mohou být okolnosti, za kterých budete chtít provést ruční kontrolu.

Pokud chcete aktualizace vyhledat ručně, přejděte na **Nastavení**  >  **Aktualizace & Kontrola** zabezpečení  >  **aktualizací.** Pokud aplikace Nastavení indikuje, že je vaše zařízení aktuální, máte všechny aktualizace, které jsou aktuálně k dispozici.

## <a name="manually-roll-back-an-update"></a>Ruční vrácení aktualizace zpět

V některých případech se můžete chtít vrátit k předchozí verzi softwaru HoloLens. Postup závisí na tom, jestli používáte HoloLens 2 nebo HoloLens (1. generace).

### <a name="revert-to-a-previous-version-hololens-2"></a>Zpět k předchozí verzi (HoloLens 2)

Aktualizace můžete vrátit zpět a vrátit se k předchozí verzi HoloLens 2 pomocí [doplňku Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) a resetovat HoloLens na starší verzi.

> [!NOTE]
> Po návratu ke starší verzi se odstraní vaše osobní soubory a nastavení.

Pokud se chcete vrátit k předchozí verzi HoloLens 2, postupujte takto:

1. Ujistěte se, že nemáte k počítači připojené žádné telefony ani zařízení s Windows.
1. Na svém počítači si z webu [Microsoft Store.](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)
1. Stáhněte [si nejnovější verzi HoloLens 2.](https://aka.ms/hololens2download)
1. Po dokončení těchto stahování otevřete Průzkumníka souborů Stažené soubory, klikněte pravým tlačítkem na komprimovanou složku (.zip), kterou jste právě stáhli, a pak rozbalte soubor výběrem možnosti Extrahovat  >     >   vše.
1. Připojte zařízení HoloLens k počítači pomocí kabelu USB-A na USB-C. Tento typ kabelu funguje nejlépe i v případě, že k připojení HoloLens používáte jiné kabely.
1. Advanced Recovery Companion automaticky rozpozná vaše zařízení HoloLens. Vyberte **dlaždici Microsoft HoloLens.**
1. Na další obrazovce vyberte **Ruční výběr balíčku a** pak otevřete složku, kterou jste předtím rozbalí.
1. Vyberte instalační soubor (.ffu).
1. Vyberte **Nainstalovat software** a pak postupujte podle pokynů.

### <a name="revert-to-a-previous-version-hololens-1st-gen"></a>Zpět na předchozí verzi (HoloLens (1. generace))

Aktualizace můžete vrátit zpět a vrátit se k předchozí verzi HoloLens (1. generace) pomocí nástroje [WDRT (Windows Device Recovery Tool)](https://support.microsoft.com/help/12379) a resetovat HoloLens na starší verzi.

> [!NOTE]
> Po návratu ke starší verzi HoloLens se odstraní vaše osobní soubory a nastavení.

Pokud se chcete vrátit k předchozí verzi HoloLens (1. generace), postupujte takto:

1. Ujistěte se, že nemáte k počítači připojené žádné telefony ani zařízení s Windows.
1. Na svém počítači stáhněte [nástroj WDRT (Windows Device Recovery Tool).](https://support.microsoft.com/help/12379)
1. Stáhněte [si balíček pro obnovení HoloLens Anniversary Update.](https://aka.ms/hololensrecovery)
1. Po dokončení stahování otevřete Průzkumníka souborů Stažené soubory, klikněte pravým tlačítkem na komprimovanou složku (.zip), kterou jste právě stáhli, a potom rozbalte soubor výběrem možnosti Extrahovat  >     >   vše.
1. Připojte zařízení HoloLens k počítači pomocí kabelu mikro USB, který jste dodáli společně se zařízením HoloLens. I když k připojení zařízení HoloLens používáte jiné kabely, funguje to nejlépe.
1. WDRT automaticky rozpozná vaše zařízení HoloLens. Vyberte **dlaždici Microsoft HoloLens.**
1. Na další obrazovce vyberte **Ruční výběr balíčku a** pak otevřete složku, kterou jste předtím rozbalí.
1. Vyberte instalační soubor (.ffu).
1. Vyberte **Nainstalovat software** a pak postupujte podle pokynů.

**Pokud WDRT nezjistí vaše zařízení**

Pokud nástroj WDRT nezjistí vaše zařízení HoloLens, zkuste počítač restartovat. Pokud to nefunguje, vyberte **Moje zařízení** se nezjme, vyberte **Microsoft HoloLens** a pak postupujte podle pokynů.

## <a name="related-articles"></a>Související články

- [Poznámky k verzi HoloLens 2](https://docs.microsoft.com/hololens/hololens-release-notes)
- [Co je Windows Update pro firmy?](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [Přiřazení zařízení k servisním kanálům pro Windows 10 aktualizace](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Správa softwarových aktualizací Windows 10 v Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
