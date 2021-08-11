---
title: Správa HoloLens aktualizací
description: Zjistěte, jak můžou správci používat správu mobilních zařízení ke správě aktualizací HoloLens zařízení.
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
ms.openlocfilehash: 635e2cc274101fcf08fd05f2b3b54ce6c2f79182011d76409a51c722ea47ecc7
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662793"
---
# <a name="manage-hololens-updates"></a>Správa HoloLens aktualizací

HoloLens používá Windows Update stejným způsobem jako ostatní Windows 10 zařízení. Když je k dispozici aktualizace, automaticky se stáhne a nainstaluje při příštím připojení zařízení k internetu. Tento článek popisuje, jak spravovat aktualizace v podnikovém nebo jiném spravovaném prostředí. Informace o tom, jak spravovat aktualizace jednotlivých zařízení HoloLens, najdete v tématu [Aktualizace HoloLens](hololens-update-hololens.md).

## <a name="manage-updates-automatically"></a>Automatická správa aktualizací

### <a name="managing-updates-by-using-windows-update-for-business"></a>Správa aktualizací pomocí Windows Update pro firmy

Windows Holographic for Business aktualizace [můžete Windows update for Business.](/windows/deployment/update/waas-manage-updates-wufb) Všechna HoloLens 2 zařízení používejte Windows Holographic for Business. Ujistěte se, že Windows Holographic for Business sestavení 10.0.18362.1042 nebo novější. Pokud máte HoloLens (1. generace), musíte je [](hololens1-upgrade-enterprise.md) upgradovat na Windows Holographic for Business spravovat jejich aktualizace.

Windows Update for Business HoloLens zařízení přímo ke službě Windows Update. Pomocí Windows Update pro firmy můžete řídit několik aspektů procesu aktualizace, což znamená, která zařízení chystá v &mdash; jaké době aktualizace. Můžete například pro účely testování zacílíte aktualizace podmnožiny zařízení a později aktualizace zbývajících zařízení. Nebo můžete definovat různé plány aktualizací pro různé typy aktualizací.

> [!NOTE]  
> Pro HoloLens zařízení můžete automaticky spravovat aktualizace funkcí (vydané dvakrát ročně) a aktualizace kvality (vydané každý měsíc nebo podle potřeby, včetně důležitých aktualizací zabezpečení). Další informace o typech aktualizací najdete v tématu [Typy aktualizací spravované službou Windows Update for Business.](/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business)

Nastavení služby Windows Update for Business pro HoloLens můžete nakonfigurovat pomocí zásad v řešení MDM (Mobile Správa zařízení), jako je Microsoft Intune.

### <a name="managing-windows-update-for-business-by-using-microsoft-intune"></a>Správa Windows Update pro firmy pomocí Microsoft Intune

Podrobný popis použití Intune ke konfiguraci služby Windows Update pro firmy najdete v tématu Správa [Windows 10 aktualizací softwaru v Intune.](/intune/protect/windows-update-for-business-configure) Další informace o konkrétních funkcích Intune, které HoloLens, najdete v tématu Funkce správy aktualizací [Intune, HoloLens podporuje](#intune-update-management-functions-that-hololens-supports).

> [!IMPORTANT]  
> Intune poskytuje dva typy zásad pro správu aktualizací: *Windows 10 aktualizační okruh* *a Windows 10 aktualizace funkcí*. Typ Windows 10 aktualizace funkcí je v tuto chvíli ve verzi Public Preview a nepodporuje se pro HoloLens.
>  
> Zásady aktualizačního okruhu Windows 10 použít ke správě aktualizací HoloLens 2.

### <a name="configure-update-policies-for-hololens-2-or-hololens-1st-gen"></a>Konfigurace zásad aktualizace pro HoloLens 2 nebo HoloLens (1. generace)

Tato část popisuje zásady, které můžete použít ke správě aktualizací pro HoloLens 2 nebo HoloLens (1. generace). Další informace o funkcích, které jsou k dispozici pro HoloLens 2, najdete v tématu Plánování a konfigurace kumulativních aktualizací [pro HoloLens 2.](#plan-and-configure-update-rollouts-for-hololens-2)

[CsP zásad – Aktualizace](/windows/client-management/mdm/policy-csp-update) definuje zásady, které konfigurují Windows Update for Business.

> [!NOTE]  
> Seznam konkrétních poskytovatelů konfiguračních služeb (CSP) zásad podporovaných konkrétními edicemi HoloLens najdete v tématu Poskytovatelé CSP zásad podporovaní HoloLens [zařízeními.](/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices)

#### <a name="configure-automatic-checks-for-updates"></a>Konfigurace automatických kontrol aktualizací

Zásady **Update/AllowAutoUpdate** můžete použít ke správě chování automatických aktualizací, jako je kontrola, stahování a instalace aktualizací. Další informace o dostupných nastaveních pro tuto zásadu najdete v tématu [Aktualizace/AllowAutoUpdate.](/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)

> [!NOTE]  
> V Microsoft Intune můžete tuto zásadu  změnit pomocí chování automatické aktualizace. Další informace najdete v tématu [Správa Windows 10 aktualizací softwaru v Intune.](/intune/windows-update-for-business-configure)

#### <a name="configure-an-update-schedule"></a>Konfigurace plánu aktualizací

Pokud chcete nakonfigurovat, jak a kdy se mají aktualizace použít, použijte následující zásady:

- [Update/ScheduledInstallDay](/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - Hodnoty: **0–7**(0 = každý den, 1 = neděle, 7 = sobota)
  - Výchozí hodnota: **0** (každý den)
- [Update/ScheduledInstallTime](/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - Hodnoty: 0–23 (0 = půlnoc, 23 = 21 PM)
  - Výchozí hodnota: 3:00

#### <a name="configure-active-hours"></a>Konfigurace aktivních hodin
Počínaje Windows Holographic může správce IT ve verzi [20H2](hololens-release-notes.md#windows-holographic-version-20h2) určit rozsah aktivních hodin pro zařízení HoloLens 2.

Aktivní hodiny identifikují časové období, kdy očekáváte, že se zařízení bude používat. Automatické restartování po aktualizaci se projeví mimo aktivní hodiny. Zadaný rozsah se bude počítat od počátečního času aktivních hodin. Můžete použít MDM, jak je popsáno v tématu [Konfigurace aktivních hodin pomocí MDM.](/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm) MDM používá nastavení Update/ActiveHoursStart a Update/ActiveHoursEnd a Update/ActiveHoursMaxRange v csP zásad ke konfiguraci aktivních hodin.

-   [Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend) – tato hodnota nastaví čas ukončení. Od počátečního času je k dispozici maximálně 12 hodin.
    -   Podporované hodnoty jsou 0–23, kde 0 je 12:00, 1 je 1:00 atd.
    -   Výchozí hodnota je 17 (17:00).
-   [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) – Tato hodnota nastaví maximální počet aktivních hodin od počátečního času.
    -   Podporované hodnoty jsou 8 až 18.
    -   Výchozí hodnota je 18 (hodiny).
-   [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart) – Tato hodnota nastaví čas spuštění. Od koncového času je k dispozici maximálně 12 hodin.
    -   Podporované hodnoty jsou 0–23, kde 0 je 12:00, 1 je 1:00 atd.
    -   Výchozí hodnota je 8 (8:00).

#### <a name="for-devices-that-run-windows-10-version-1607-only"></a>Pro zařízení se systémem Windows 10 verze 1607

Následující zásady aktualizací můžete použít ke konfiguraci zařízení pro získání aktualizací ze služby Windows Server Update Service (WSUS), a ne ze služby Windows Update:

- [Update/AllowUpdateService](/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [Aktualizace/RequireUpdateApproval](/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [Update/UpdateServiceUrl](/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <a name="plan-and-configure-update-rollouts-for-hololens-2"></a>Plánování a konfigurace kumulativních aktualizací pro HoloLens 2

HoloLens 2 podporuje více funkcí pro automatizaci aktualizací než HoloLens (1. generace). To platí hlavně v případě, že Microsoft Intune zásady Windows Update for Business používáte. Tyto funkce usnadňují plánování a implementaci zavedení aktualizací v celé organizaci.

#### <a name="plan-the-update-strategy"></a>Plánování strategie aktualizace

Windows Aktualizace pro firmy podporují zásady odložení. Po vydání aktualizace můžete pomocí zásad odložení definovat, jak dlouho se má čekat před instalací této aktualizace na zařízeních. Když přidružíte podmnožiny vašich zařízení (označované také jako aktualizační okruhy) k různým zásadám odložení, můžete koordinovat strategii pro zasouvání aktualizací pro vaši organizaci.

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

Můžete nakonfigurovat různé odložení aktualizací funkcí a aktualizací kvality. Následující tabulka uvádí konkrétní zásady, které se mají použít pro každý typ, a maximální odložení pro každý typ.

|Kategorie |Zásady |Maximální odložení |
| --- | --- | --- |
|Aktualizace funkcí |DeferFeatureUpdatesPeriodInDays |365 dnů |
|Aktualizace kvality |DeferQualityUpdatesPeriodInDays |30 dní |

#### <a name="pause-updates-via-device"></a>Pozastavení aktualizací přes zařízení

Pokud uživatel nemá přístup k MDM, může na zařízení se HoloLens 2 na buildu Windows [Holographic verze 2004](hololens-release-notes.md#windows-holographic-version-2004) nebo novější pozastavit aktualizace po dobu až 35 dnů ručně. Uživatelé se k tomuto nastavení dostanou tak, že přechádnou Nastavení > Update &  Security > **Upřesnit** možnosti. Posuňte se dolů na Pozastavit aktualizace a vyberte datum, do kterého aktualizace pozastaví. Jakmile uživatel dosáhne limitu pozastavení, bude muset zařízení získat nové aktualizace, než se bude moci znovu pozastavit. 

Počínaje [Windows Holographic verze 20H2](hololens-release-notes.md#windows-holographic-version-20h2)se tato funkce pozastavení aktualizací může spravovat pro HoloLens 2 zařízení. 
- [Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess).
    - 0 (výchozí) – povoleno
    - 1 – Zakázáno

#### <a name="intune-update-management-functions-that-hololens-supports"></a>Funkce správy aktualizací Intune, které HoloLens podporuje

Pomocí následujících funkcí správy aktualizací Intune můžete spravovat aktualizace pro HoloLens.

- **Vytvořit** a **přiřadit:** Tyto funkce přidávají aktualizační Windows 10 aktualizační okruh do seznamu aktualizačních kanálů. Další informace najdete v tématu [Vytvoření a přiřazení aktualizačních okruhů.](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)

- **Pozastavit:** Pokud při nasazování funkce nebo aktualizace kvality narazíte na problém, můžete aktualizaci pozastavit na 35 dnů (od zadaného data). Toto pozastavení zabrání ostatním zařízením v instalaci aktualizace, dokud problém nevyřešíte nebo nezmírníte. Pokud aktualizaci funkcí pozastavíte, budou se zařízením pořád nabízeny aktualizace kvality, aby se zajistilo jejich zabezpečení. Když je typ aktualizace pozastavený, v podokně Přehled pro tento okruh se zobrazí, kolik dní zůstává před obnovením tohoto typu aktualizace. Po uplynutí zadané doby pozastavení automaticky vyprší a proces aktualizace se obnoví.

  Zatímco je aktualizační okruh pozastavený, můžete vybrat jednu z následujících možností:

  - **Prodloužení:** Prodloužení doby pozastavení pro typ aktualizace o 35 dnů.
  - **Obnovit:** Obnoví aktualizace pro tento okruh na aktivní operaci. Aktualizační okruh můžete v případě potřeby znovu pozastavit.

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

Několik upozornění na tuto nabídku Verze Preview:

- HoloLens verze Preview je omezená jenom na aktualizace operačního systému.
- Windows Holographic for Business podporuje pouze režimy stahování HTTP a stahování z koncového [bodu microsoft Připojená mezipaměť](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache); Režimy stahování peer-to-peer a přiřazení skupin se v HoloLens zařízení nepodporují.
- HoloLens nepodporuje optimalizaci nasazení nebo doručení pro Windows Server Update Services koncové body.
- Řešení potíží bude vyžadovat buď diagnostiku na serveru Připojená mezipaměť, nebo shromažďování trasování pro HoloLens v HoloLens prostřednictvím služby **Nastavení**  >  **Update & Security**  >   **Troubleshooting**  >   **Windows Update.**

## <a name="manually-check-for-updates"></a>Ruční kontrola aktualizací

Přestože HoloLens pravidelně kontroluje aktualizace systému, mohou být okolnosti, za kterých budete chtít provést ruční kontrolu.

Pokud chcete aktualizace vyhledat ručně, přejděte na **Nastavení**  >  **Update & Security** Check for  >  **updates**. Pokud Nastavení aplikace indikuje, že je vaše zařízení aktuální, máte k dispozici všechny aktuálně dostupné aktualizace.

## <a name="manually-roll-back-an-update"></a>Ruční vrácení aktualizace zpět

V některých případech se můžete chtít vrátit k předchozí verzi HoloLens softwaru. Postup závisí na tom, jestli používáte HoloLens 2 nebo HoloLens (1. generace).

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
1. Na další obrazovce vyberte **Ruční výběr balíčku a** pak otevřete složku, kterou jste předtím rozbalí.
1. Vyberte instalační soubor (.ffu).
1. Vyberte **Nainstalovat software** a pak postupujte podle pokynů.

### <a name="revert-to-a-previous-version-hololens-1st-gen"></a>Zpět na předchozí verzi (HoloLens (1. generace))

Aktualizace můžete vrátit zpět a vrátit se k předchozí verzi služby HoloLens (1. generace) pomocí nástroje [WDRT (Windows Device Recovery Tool)](https://support.microsoft.com/help/12379) a resetovat HoloLens na starší verzi.

> [!NOTE]
> Po návratu k dřívější HoloLens odstraníte osobní soubory a nastavení.

Pokud se chcete vrátit k předchozí verzi HoloLens (1. generace), postupujte takto:

1. Ujistěte se, že nemáte žádné telefony ani Windows zařízení připojená k vašemu počítači.
1. Na svém počítači si stáhněte [Windows Device Recovery Tool (WDRT).](https://support.microsoft.com/help/12379)
1. Stáhněte [si balíček HoloLens Anniversary Update pro obnovení.](https://aka.ms/hololensrecovery)
1. Po dokončení stahování otevřete Průzkumníka souborů Stažené soubory, klikněte pravým tlačítkem na komprimovanou složku (.zip), kterou jste právě stáhli, a pak rozbalte soubor výběrem možnosti Extrahovat  >     >   vše.
1. Pomocí kabelu mikro USB, který jste dodáli společně s vaším HoloLens, připojte HoloLens zařízení k počítači. I v případě, že jste ke svému zařízení HoloLens kabely, funguje to nejlépe.
1. WDRT automaticky zjistí vaše HoloLens zařízení. Vyberte **dlaždici Microsoft HoloLens.**
1. Na další obrazovce vyberte **Ruční výběr balíčku a** pak otevřete složku, kterou jste předtím rozbalí.
1. Vyberte instalační soubor (.ffu).
1. Vyberte **Nainstalovat software** a pak postupujte podle pokynů.

**Pokud WDRT nezjistí vaše zařízení**

Pokud wdrt nerozpozná vaše zařízení HoloLens, zkuste počítač restartovat. Pokud to nefunguje, vyberte **Moje zařízení** se nezjme, vyberte **Microsoft HoloLens** a postupujte podle pokynů.

## <a name="related-articles"></a>Související články

- [HoloLens 2 k vydání verze](hololens-release-notes.md)
- [Co je Windows Update for Business?](/windows/deployment/update/waas-manage-updates-wufb)
- [Přiřazení zařízení k servisním kanálům pro Windows 10 aktualizace](/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [Správa softwarových aktualizací Windows 10 v Intune](/mem/intune/protect/windows-update-for-business-configure)
