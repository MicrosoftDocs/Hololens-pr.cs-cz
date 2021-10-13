---
title: správa aktualizací HoloLens
description: naučte se, jak můžou správci používat správu mobilních zařízení ke správě aktualizací HoloLensch zařízení.
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
audience: ITPro
ms.topic: article
ms.localizationpriority: high
ms.date: 10/12/2021
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
ms.openlocfilehash: 854e867238de6c87732970fba75abdc8e1fb2c64
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924336"
---
# <a name="manage-hololens-updates"></a>správa aktualizací HoloLens

HoloLens používá web Windows Update stejným způsobem jako ostatní Windows 10 zařízení. Když je dostupná aktualizace, automaticky se stáhne a nainstaluje při příštím připojení zařízení k Internetu. Tento článek popisuje, jak spravovat aktualizace v podnikovém nebo jiném spravovaném prostředí. informace o tom, jak spravovat aktualizace pro jednotlivá HoloLens zařízení, najdete v části [Update HoloLens](hololens-update-hololens.md).

## <a name="manage-updates-automatically"></a>Spravovat aktualizace automaticky

### <a name="managing-updates-by-using-windows-update-for-business"></a>správa aktualizací pomocí web Windows Update pro firmy

Windows Holographic for Business můžou pomocí [web Windows Update pro firmy](/windows/deployment/update/waas-manage-updates-wufb) spravovat aktualizace. všechna zařízení HoloLens 2 můžou používat Windows Holographic for Business. ujistěte se, že používají Windows Holographic for Business build 10.0.18362.1042 nebo novější. pokud máte zařízení HoloLens (1. generace), je nutné [je upgradovat na Windows Holographic for Business](hololens1-upgrade-enterprise.md) , aby bylo možné spravovat jejich aktualizace.

Windows aktualizace pro firmy připojuje HoloLens zařízení přímo ke službě web Windows Update. pomocí web Windows Update pro firmy můžete řídit více aspektů procesu aktualizace, které &mdash; zařízení získávají aktualizace v daném čase. Můžete například aktualizovat podmnožinu zařízení pro testování a pak později aktualizovat zbývající zařízení. Nebo můžete definovat různé plány aktualizací pro různé typy aktualizací.

> [!NOTE]  
> u HoloLensch zařízení můžete automaticky spravovat aktualizace funkcí (vydaná dvakrát za rok) a aktualizace kvality (vydané měsíčně nebo podle potřeby, včetně důležitých aktualizací zabezpečení). další informace o typech aktualizací najdete v tématu [typy aktualizací, které jsou spravovány web Windows Update pro firmy](/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).

nastavení web Windows Update pro firmy můžete nakonfigurovat pro HoloLens pomocí zásad v řešení správy mobilních zařízení (MDM), jako je například Microsoft Intune.

### <a name="managing-windows-update-for-business-by-using-microsoft-intune"></a>správa web Windows Update pro firmy pomocí Microsoft Intune

podrobnou diskuzi o tom, jak pomocí intune nakonfigurovat web Windows Update pro firmy, najdete v tématu [správa Windows 10 aktualizací softwaru v intune](/intune/protect/windows-update-for-business-configure). další informace o konkrétních funkcích intune, které HoloLens podporuje, najdete v tématu [funkce správy aktualizací intune, které HoloLens podporuje](#intune-update-management-functions-that-hololens-supports).

> [!IMPORTANT]  
> intune nabízí dva typy zásad pro správu aktualizací: *Windows 10 aktualizace* *Windows 10 funkcí* pro aktualizace. typ zásad aktualizace funkcí Windows 10 je v současnosti ve verzi public preview a pro HoloLens se nepodporuje.
>  
> ke správě aktualizací HoloLens 2 můžete použít zásady Windows 10 update ring.

### <a name="configure-update-policies-for-hololens-2-or-hololens-1st-gen"></a>konfigurace zásad aktualizace pro HoloLens 2 nebo HoloLens (1. generace)

tato část popisuje zásady, které můžete použít ke správě aktualizací pro HoloLens 2 nebo HoloLens (1. generace). další informace o funkcích, které jsou k dispozici pro HoloLens 2, najdete v tématu [plánování a konfigurace aktualizací update uvádění pro HoloLens 2](#plan-and-configure-update-rollouts-for-hololens-2).

[zásada CSP – aktualizace](/windows/client-management/mdm/policy-csp-update) definuje zásady, které konfigurují web Windows Update pro firmy.

> [!NOTE]  
> seznam konkrétních zprostředkovatelů konfiguračních služeb (csp), které jsou podporované konkrétními edicemi HoloLens, najdete v tématu věnovaném [zprostředkovatelům csp podporovaným pomocí HoloLens zařízení](/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices).

#### <a name="configure-automatic-checks-for-updates"></a>Konfigurace automatických kontrol aktualizací

Pomocí zásad **Update/AllowAutoUpdate** můžete spravovat chování automatických aktualizací, jako je skenování, stahování a instalace aktualizací. Další informace o dostupných nastaveních pro tuto zásadu najdete v tématu [Update/AllowAutoUpdate](/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).

> [!NOTE]  
> v Microsoft Intune můžete pro změnu těchto zásad použít **chování funkce automatické aktualizace** . další informace najdete v tématu [správa aktualizací softwaru Windows 10 v intune](/intune/windows-update-for-business-configure).

#### <a name="configure-an-update-schedule"></a>Konfigurovat plán aktualizací

Pokud chcete nakonfigurovat, jak a kdy se aktualizace použijí, použijte následující zásady:

- [Aktualizovat/ScheduledInstallDay](/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - Hodnoty: **0**–**7** (0 = každý den, 1 = neděle, 7 = sobota)
  - Výchozí hodnota: **0** (každý den)
- [Aktualizovat/ScheduledInstallTime](/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - Hodnoty: 0 – 23 (0 = půlnoc, 23 = 11 odp)
  - Výchozí hodnota: 3 dop.

#### <a name="configure-active-hours"></a>Konfigurovat aktivní hodiny
od [Windows holografické verze 20H2](hololens-release-notes.md#windows-holographic-version-20h2) může správce IT určit rozsah aktivních hodin pro zařízení HoloLens 2.

Aktivní hodiny identifikují dobu, po kterou se zařízení bude používat. Automatické restartování po aktualizaci proběhne mimo aktivní hodiny. Zadaný rozsah bude počítán od počátečního času aktivní hodiny. Můžete použít MDM, jak je popsáno v tématu [Konfigurace aktivních hodin s MDM](/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm). MDM používá nastavení Update/ActiveHoursStart a Update/ActiveHoursEnd a Update/ActiveHoursMaxRange v zásadách CSP ke konfiguraci aktivních hodin.

-   [Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend) – tato hodnota nastaví čas ukončení. Od počátečního času je maximálně 12 hodin.
    -   Podporované hodnoty jsou 0-23, kde 0 je 12 DOP, 1 je 1 dop. atd.
    -   Výchozí hodnota je 17 (5 odp.).
-   [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) – tato hodnota nastaví maximální počet aktivních hodin od počátečního času.
    -   Podporované hodnoty jsou 8-18.
    -   Výchozí hodnota je 18 (hodiny).
-   [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart) – tato hodnota nastaví počáteční čas. Čas ukončení je 12 hodin.
    -   Podporované hodnoty jsou 0-23, kde 0 je 12 DOP, 1 je 1 dop. atd.
    -   Výchozí hodnota je 8 (ráno).

#### <a name="for-devices-that-run-windows-10-version-1607-only"></a>pro zařízení, která používají Windows 10 verze 1607

pomocí následujících zásad aktualizace můžete nakonfigurovat zařízení k získání aktualizací ze služby Windows Server update Service (WSUS) místo z web Windows Update:

- [Aktualizovat/AllowUpdateService](/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Aktualizovat/RequireUpdateApproval](/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Aktualizovat/UpdateServiceUrl](/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

#### <a name="improved-update-restart-detection-and-notifications"></a>Vylepšené zjišťování a oznámení o aktualizacích

- zavedeno v [Windows holografické verzi 21H2](hololens-release-notes.md#windows-holographic-version-21h2).

mezi aktivními hodinami a zásadami času instalace je možné zabránit restartování HoloLens zařízení, když se používají. Nicméně by také zpozdil přijetí aktualizací, pokud k restartování nedojde k dokončení instalace požadované aktualizace. Nyní jsme přidali zásady, které jim umožní vymáhat termíny a požadovaná restartování a zajistit, aby byla instalace aktualizace dokončena včas. Uživatelé můžou být upozorňováni před zahájením restartování a můžou zpozdit restart v souladu se zásadami IT.

Byly přidány následující zásady aktualizace:

- [Aktualizovat/AutoRestartNotificationSchedule](/windows/client-management/mdm/policy-csp-update#update-autorestartnotificationschedule)
- [Aktualizovat/AutoRestartRequiredNotificationDismissal](/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
- [Aktualizovat/ConfigureDeadlineForFeatureUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforfeatureupdates)
- [Aktualizovat/ConfigureDeadlineForQualityUpdates](/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforqualityupdates)
- [Aktualizovat/ConfigureDeadlineGracePeriod](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinegraceperiod)
- [Aktualizovat/ConfigureDeadlineNoAutoReboot](/windows/client-management/mdm/policy-csp-update#update-configuredeadlinenoautoreboot)
- [Aktualizovat/ScheduleImminentRestartWarning](/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning)
- [Aktualizovat/ScheduleRestartWarning](/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)
- [Aktualizovat/UpdateNotificationLevel](/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)

### <a name="plan-and-configure-update-rollouts-for-hololens-2"></a>plánování a konfigurace uvádění aktualizace pro HoloLens 2

HoloLens 2 podporuje více funkcí automatizace aktualizací než HoloLens (1. generace). to platí hlavně v případě, že používáte Microsoft Intune ke správě zásad web Windows Update pro firmy. Tyto funkce usnadňují plánování a implementaci uvádění aktualizací napříč vaší organizací.

#### <a name="plan-the-update-strategy"></a>Plánování strategie aktualizace

Windows Aktualizace pro firmy podporují zásady odložení. Jakmile společnost Microsoft uvolní aktualizaci, můžete použít zásadu odložení a určit, jak dlouho se má čekat před instalací této aktualizace na zařízení. Tím, že přidružíte podmnožiny zařízení (označované také jako *aktualizační* kanály) s různými zásadami odložení, můžete koordinovat strategii zavedení aktualizací pro vaši organizaci.

Představte si třeba organizaci, která má 1 000 zařízení, a musí aktualizovat zařízení v pěti vlny. Organizace může vytvořit pět aktualizačních kroužků, jak je znázorněno v následující tabulce.

|Group (Skupina) |Počet zařízení |Odložení (dny) |
| ---| :---: | :---: |
|GRP 1 (zaměstnanci oddělení IT) |5 |0 |
|GRP 2 (rané státy) |50 |60 |
|Grp 3 (hlavní 1) |250 |120 |
|Grp 4 (hlavní 2) |300 |150 |
|Grp 5 (hlavní 3) |395 |180 |

Tady je postup, jak se bude v průběhu času zavánět do celé organizace.

![Časová osa pro nasazení aktualizací](./images/hololens-updates-timeline.png)

#### <a name="configure-an-update-deferral-policy"></a>Konfigurace zásad odložení aktualizací

Zásada odložení určuje počet dní mezi datem, kdy se aktualizace stane dostupnou, a datem, kdy se aktualizace zařízení nabízí.

Můžete nakonfigurovat různé odložení aktualizací funkcí a aktualizací kvality. Následující tabulka uvádí konkrétní zásady, které se mají použít pro každý typ, a maximální odložení pro každý typ.

|Kategorie |Zásady |Maximální odložení |
| --- | --- | --- |
|Aktualizace funkcí |DeferFeatureUpdatesPeriodInDays |365 dnů |
|Aktualizace kvality |DeferQualityUpdatesPeriodInDays |30 dní |

#### <a name="pause-updates-via-device"></a>Pozastavení aktualizací přes zařízení

Pokud uživatel nemá přístup k MDM, může aktualizace na zařízení HoloLens 2 na buildu Windows [Holographic verze 2004](hololens-release-notes.md#windows-holographic-version-2004) nebo novější pozastavit na dobu až 35 dnů ručně. Uživatelé se k tomuto nastavení dostanou tak, že přechádnou Nastavení > Update &  Security > Upřesnit možnosti. Posuňte se dolů na Pozastavit aktualizace **a** vyberte datum, do kterého aktualizace pozastaví. Jakmile uživatel dosáhne limitu pozastavení, bude muset zařízení získat nové aktualizace, než se bude moci znovu pozastavit. 

Počínaje [Windows Holographic verze 20H2](hololens-release-notes.md#windows-holographic-version-20h2)se tato funkce pozastavení aktualizací může spravovat pro HoloLens 2 zařízení. 
- [Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess).
    - 0 (výchozí) – povoleno
    - 1 – Zakázáno

#### <a name="intune-update-management-functions-that-hololens-supports"></a>Funkce správy aktualizací Intune, které HoloLens podporuje

Pomocí následujících funkcí správy aktualizací Intune můžete spravovat aktualizace pro HoloLens.

- **Create** and **Assign**(Vytvořit a přiřadit): Tyto funkce Windows 10 aktualizační okruh do seznamu aktualizačních kanálů. Další informace najdete v tématu [Vytvoření a přiřazení aktualizačních okruhů.](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)

- **Pozastavit:** Pokud při nasazování funkce nebo aktualizace kvality narazíte na problém, můžete aktualizaci pozastavit na 35 dnů (od zadaného data). Toto pozastavení zabrání ostatním zařízením v instalaci aktualizace, dokud problém nevyřešíte nebo nezmírníte. Pokud aktualizaci funkcí pozastavíte, budou se zařízením pořád nabízeny aktualizace kvality, aby se zajistilo jejich zabezpečení. Když je typ aktualizace pozastavený, v podokně Přehled pro tento okruh se zobrazí, kolik dní zůstává před obnovením tohoto typu aktualizace. Po uplynutí zadané doby pozastavení automaticky vyprší a proces aktualizace se obnoví.

  Zatímco je aktualizační okruh pozastavený, můžete vybrat jednu z následujících možností:

  - **Prodloužení:** Prodloužení doby pozastavení pro typ aktualizace o 35 dnů.
  - **Obnovení:** Obnovte aktualizace pro tento okruh na aktivní operaci. Aktualizační okruh můžete v případě potřeby znovu pozastavit.

  > [!NOTE]  
  > Operace **odinstalace** aktualizačních okruhů není podporována pro HoloLens 2.

### <a name="delivery-optimization-preview"></a>Optimalizace doručení Preview

[Windows Holographic verze 21H1](hololens-release-notes.md#windows-holographic-version-21h1) umožnila v rané verzi Preview nastavení optimalizace doručení, aby se snížila spotřeba šířky pásma pro stahování z několika HoloLens zařízení. Úplný popis této funkce spolu s doporučenou konfigurací sítě najdete tady: Optimalizace doručení [pro Windows 10 aktualizace.](/windows/deployment/update/waas-delivery-optimization)

V rámci možností správy jsou povolená následující nastavení, [která je možné nakonfigurovat z Intune:](/mem/intune/configuration/delivery-optimization-settings)

- [DoCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DoCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DoDownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DoPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

Několik upozornění na tuto nabídku verze Preview:

- HoloLens verze Preview je omezená pouze na aktualizace operačního systému.
- Windows Holographic for Business podporuje pouze režimy stahování HTTP a stahování z koncového [bodu microsoft Připojená mezipaměť](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache); Režimy stahování peer-to-peer a přiřazení skupin se v HoloLens zařízení nepodporují.
- HoloLens nepodporuje optimalizaci nasazení nebo doručení pro Windows Server Update Services koncové body.
- Řešení potíží bude vyžadovat buď diagnostiku na serveru Připojená mezipaměť, nebo shromažďování trasování v HoloLens v HoloLens prostřednictvím Nastavení  >  **Update & Security**  >   **Troubleshooting** Windows  >   **Update.**

## <a name="manually-check-for-updates"></a>Ruční kontrola aktualizací

Přestože HoloLens pravidelně kontroluje aktualizace systému, mohou být okolnosti, za kterých budete chtít provést ruční kontrolu.

Pokud chcete aktualizace vyhledat ručně, přejděte na **Nastavení**  >  **Update & Security** Check for  >  **updates**. Pokud Nastavení aplikace indikuje, že je zařízení aktuální, máte k dispozici všechny aktuálně dostupné aktualizace.

## <a name="manually-roll-back-an-update"></a>Ruční vrácení aktualizace zpět

V některých případech se můžete chtít vrátit k předchozí verzi HoloLens softwaru. Proces tohoto postupu závisí na tom, jestli používáte HoloLens 2 nebo HoloLens (1. generace).

### <a name="revert-to-a-previous-version-hololens-2"></a>Zpět k předchozí verzi (HoloLens 2)

Aktualizace můžete vrátit zpět a vrátit se k předchozí verzi HoloLens 2 pomocí doplňku [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) a obnovit HoloLens na starší verzi.

> [!NOTE]
> Po návratu ke starší verzi se odstraní vaše osobní soubory a nastavení.

Pokud se chcete vrátit k předchozí verzi HoloLens 2, postupujte takto:

1. Ujistěte se, že nemáte žádné telefony ani Windows zařízení připojená k počítači.
1. Na svém počítači si z [konzoly](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) stáhněte doplněk Advanced Recovery Companion Microsoft Store.
1. Stáhněte [si nejnovější verzi HoloLens 2.](https://aka.ms/hololens2download)
1. Po dokončení těchto stahování otevřete Průzkumníka souborů Stažené soubory, klikněte pravým tlačítkem na komprimovanou složku (.zip), kterou jste právě stáhli, a pak rozbalte soubor výběrem možnosti Extrahovat  >     >   vše.
1. Pomocí kabelu USB-A na USB-C připojte HoloLens zařízení k počítači. Tento typ kabelu funguje nejlépe i v případě, že HoloLens kabely pro připojení kabely.
1. Advanced Recovery Companion automaticky rozpozná vaše HoloLens obnovení. Vyberte **dlaždici Microsoft HoloLens.**
1. Na další obrazovce vyberte **Ruční výběr balíčku** a pak otevřete složku, kterou jste předtím rozbalí.
1. Vyberte instalační soubor (.ffu).
1. Vyberte **Nainstalovat software** a pak postupujte podle pokynů.

### <a name="revert-to-a-previous-version-hololens-1st-gen"></a>Zpět k předchozí verzi (HoloLens (1. generace))

Aktualizace můžete vrátit zpět a vrátit se k předchozí verzi služby HoloLens (1. generace) pomocí nástroje [WDRT (Windows Device Recovery Tool)](https://support.microsoft.com/help/12379) a resetovat HoloLens na starší verzi.

> [!NOTE]
> Po návratu k dřívější HoloLens odstraníte osobní soubory a nastavení.

Pokud se chcete vrátit k předchozí verzi HoloLens (1. generace), postupujte takto:

1. Ujistěte se, že nemáte žádné telefony ani Windows zařízení připojená k počítači.
1. Na svém počítači si stáhněte [Windows Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379)
1. Stáhněte [si balíček HoloLens Anniversary Update pro obnovení.](https://aka.ms/hololensrecovery)
1. Po dokončení stahování otevřete Průzkumníka souborů Stažené soubory, klikněte pravým tlačítkem na komprimovanou složku (.zip), kterou jste právě stáhli, a potom rozbalte soubor výběrem možnosti Extrahovat  >     >   vše.
1. Pomocí kabelu mikro USB, který jste dodáli společně s vaším HoloLens, připojte HoloLens zařízení k počítači. I v případě, že ke svému zařízení HoloLens používáte jiné kabely, funguje to nejlépe.
1. WDRT automaticky detekuje vaše zařízení HoloLens. vyberte dlaždici **Microsoft HoloLens** .
1. Na další obrazovce vyberte možnost **Ruční výběr balíčku** a pak otevřete složku, kterou jste dříve rozbalili.
1. Vyberte soubor instalace (. FFU).
1. Vyberte **instalovat software** a pak postupujte podle pokynů.

**Pokud WDRT nerozpozná vaše zařízení**

pokud WDRT zařízení neHoloLens rozpozná, zkuste restartovat počítač. pokud to nepomůže, vyberte **moje zařízení se nezjistilo**, vyberte **Microsoft HoloLens** a pak postupujte podle pokynů.

## <a name="related-articles"></a>Související články

- [poznámky k verzi HoloLens 2](hololens-release-notes.md)
- [co je web Windows Update pro firmy?](/windows/deployment/update/waas-manage-updates-wufb)
- [přiřazení zařízení pro údržbu kanálů pro Windows 10 aktualizace](/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Správa softwarových aktualizací Windows 10 v Intune](/mem/intune/protect/windows-update-for-business-configure)
