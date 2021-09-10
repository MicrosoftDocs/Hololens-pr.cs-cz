---
title: běžné scénáře – Offline zabezpečené HoloLens 2
description: přečtěte si, jak nastavit offline nasazení zabezpečeného nasazení a nasazení aplikací se zřizováním pro HoloLens zařízení.
keywords: HoloLens, správa, offline, offline zabezpečení
ms.date: 9/25/2020
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 10d1955249630202a05fbf2057e1d175855ce0b5
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428160"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>běžné scénáře – Offline zabezpečené HoloLens 2

## <a name="overview"></a>Přehled

tato příručka poskytuje pokyny pro použití ukázkového zřizovacího balíčku, který bude uzamknout HoloLens 2 pro použití v zabezpečených prostředích s těmito omezeními:

-   Zakáže Wi-Fi.
-   Zakáže BlueTooth.
-   Zakáže mikrofony.
-   Znemožní přidávání nebo odebírání zřizovacích balíčků.
-   Žádný uživatel nemůže povolit žádnou z výše uvedených součástí s omezením.

[![Zabezpečený scénář offline. ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)

## <a name="prepare"></a>Příprava

Windows 10 Instalace počítače
1. [stáhněte si nejnovější soubor HoloLens 2 OS](https://aka.ms/hololens2download) přímo do počítače. 
   1. Podpora této konfigurace je součástí buildu 19041,1117 a vyššího.
1. stáhněte si nebo nainstalujte nástroj průvodce pro pokročilou obnovu (oblouk) [z Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) do počítače.
1. stáhněte si nebo nainstalujte nejnovější nástroj [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) z Microsoft Store do vašeho počítače.
1. [Stáhněte složku OfflineSecureHL2_Sample se soubory projektu](https://aka.ms/HoloLensDocs-SecureOfflineSample) pro sestavení ppkg.
1. Připravte svou online [obchodní aplikaci pro nasazení ppkg](app-deploy-provisioning-package.md). 


## <a name="configure"></a>Konfigurace

Vytvoření balíčku pro zřizování zabezpečené konfigurace

1. Spusťte na svém počítači nástroj WCD.
1. Vyberte **soubor – > otevřít projekt**.
  1. Přejděte do umístění dříve uložené složky OfflineSecureHL2_Sample a vyberte: OfflineSecureHL2_Sample.icdproj.xml
1. Projekt by se měl otevřít a teď byste měli mít k dispozici seznam dostupných úprav:

   > [!div class="mx-imgBorder"]
   > ![Snímek obrazovky konfiguračního balíčku otevřený v WCD](images/offline-secure-sample-wcd.png)

   Konfigurace nastavené v tomto zřizovacím balíčku:
   
   |     Položka                                                |     Nastavení                       |     Popis                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     Účty/uživatelé                                    |     Místní uživatelské jméno & heslo    |     U těchto offline zařízení bude nutné nastavit a sdílet jedno uživatelské jméno a heslo všemi uživateli zařízení.          |
   |     první zkušenosti/HoloLens/SkipCalibration       |     Ano                          |     Při počátečním nastavení zařízení přeskočí kalibraci.                                                                             |
   |     první zkušenosti/HoloLens/SkipTraining          |     Ano                          |     Při počátečním nastavení zařízení přeskočí školení zařízení.                                                                              |
   |     první zkušenosti/HoloLens/wi-fi                  |     Ano                          |     Při počátečním nastavení zařízení přeskočí Wi-Fi config.                                                                                 |
   |     Zásady/připojení/AllowBluetooth                |     No                            |     Zakáže Bluetooth                                                                                                             |
   |     Zásady/zkušenosti/AllowCortana                    |     No                            |     zakáže Cortana (aby se vyloučily potenciální problémy, protože mikrofony jsou zakázané).                                          |
   |     Zásady/MixedReality/MicrophoneDisabled            |     Yes                           |     Zakáže mikrofon.                                                                                                            |
   |     Zásady/ochrana osobních údajů/LetAppsAccessLocation              |     Vynutit odepření                    |     Zabraňuje aplikacím v pokusu o přístup k datům o poloze (aby se vyloučily potenciální problémy, protože sledování umístění je zakázané).    |
   |     Zásady/ochrana osobních údajů/LetAppsAccessMicrophone            |     Vynutit odepření                    |     Zabraňuje aplikacím v pokusu o přístup k mikrotelefonům (aby se vyloučily potenciální problémy, protože mikrofony jsou zakázané).           |
   |     Zásady/zabezpečení/AllowAddProvisioningPackage       |     No                            |     Zabrání komukoli v přidávání zřizovacích balíčků, které se můžou pokusit přepsat uzamčené zásady.                         |
   |     Zásady/zabezpečení/AllowRemoveProvisioningPackage    |     No                            |     Znemožní komukoli odebrat tento uzamčený zřizovací balíček.                                                           |
   |     Zásady/systém/AllowLocation                       |     No                            |     Zabrání zařízení v pokusu o sledování dat o poloze.                                                                        |
   |     Zásady/Wi-Fi/AllowWiFi                             |     No                            |     Zakáže Wi-Fi                                                                                                                 |

1. v části modul Runtime Nastavení vyberte **účty/uživatelé/uživatelské jméno: Holo/heslo**.

   Poznamenejte si heslo a v případě potřeby ho obnovte.

1. Přejděte na UniversalAppInstall/UserContextApp a [nakonfigurujte obchodní aplikaci](app-deploy-provisioning-package.md) , kterou budete nasazovat do těchto zařízení.

   > [!div class="mx-imgBorder"]
   > ![Snímek obrazovky s přidáním aplikace v WCD](images/offline-secure-sample-wcd-usercontextapp2.png)

1. Po dokončení klikněte na tlačítko Exportovat a proveďte všechny výzvy, dokud nebude vytvořen zřizovací balíček.

   > [!div class="mx-imgBorder"]
   > ![Snímek obrazovky s tlačítkem exportovat pro tento balíček v WCD](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>Nasadit

1. Připojení HL2 k počítači s Windows 10 prostřednictvím kabelu USB.
1. spusťte nástroj ARC a vyberte **HoloLens 2** .

   ![úvodní obrazovka HoloLens 2 čistého formátu](images/ARC2.png)

1. Na další obrazovce vyberte možnost **Manuální výběr balíčku**.

   ![HoloLens 2 – obrazovka s informacemi o ARC](images/arc_device_info.png)

1. Přejděte na dříve stažený soubor. FFU a vyberte **otevřít**.
1. Na stránce s upozorněním vyberte **pokračovat**.

   ![HoloLens 2 výstražná obrazovka ARC.](images/arc_warning.png)

1. počkejte, než nástroj ARC dokončí instalaci operačního systému HoloLens 2.
1. Jakmile zařízení dokončí zálohování instalace a spuštění, přejděte z počítače na příkaz Průzkumník souborů a zkopírujte dříve uložený soubor PPKG do složky zařízení.

   > [!div class="mx-imgBorder"]
   > ![Soubor PPKG na počítači v okně Průzkumníka souborů.](images/offline-secure-file-explorer.png)

1. v HoloLens 2 stiskněte následující rozevírací seznam pro spuštění zřizovacího balíčku: klepněte na tlačítko **snížit hlasitost** a **napájení** .
1. Zobrazí se výzva k použití zřizovacího balíčku, vyberte **Potvrdit** .
1. Po dokončení zřizovacího balíčku vyberte **OK**.
1. Pak se zobrazí výzva, abyste se přihlásili do zařízení pomocí sdíleného místního účtu a hesla.

## <a name="maintain"></a>Údržba

V této konfiguraci se doporučuje restartovat proces výše a znovu ho rozsvítit pomocí nástroje ARC a použít nový PPKG k provedení jakékoli aktualizace operačního systému nebo aplikací.
