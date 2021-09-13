---
title: Běžné scénáře – Zabezpečení offline HoloLens 2
description: Zjistěte, jak nastavit scénář offline zabezpečeného nasazení a nasazení aplikací se zřizováním pro HoloLens zařízení.
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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032176"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>Běžné scénáře – Zabezpečení offline HoloLens 2

## <a name="overview"></a>Přehled

Tato příručka obsahuje pokyny k použití ukázkového zřizovacího balíčku, který uzamkne HoloLens 2 pro použití v zabezpečených prostředích s následujícími omezeními:

-   Zakažte WiFi.
-   Zakažte BlueTooth.
-   Zakažte Mikrofony.
-   Zabraňuje přidávání nebo odebírání zřizovacích balíčků.
-   Žádný uživatel nemůže povolit žádnou z výše uvedených omezených komponent.

[![Scénář zabezpečení offline: ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)

## <a name="prepare"></a>Příprava

Windows 10 Nastavení počítače
1. [Stáhněte si nejnovější HoloLens 2 operačního systému](https://aka.ms/hololens2download) přímo do počítače. 
   1. Podpora této konfigurace je součástí buildu 19041.1117 a vyššího.
1. Stažení nebo instalace nástroje Advanced Recovery Companion(ARC) [z Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) do počítače
1. Stáhněte a nainstalujte [si nejnovější Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) z Microsoft Store počítače.
1. [Stáhněte složku OfflineSecureHL2_Sample se soubory projektu a](https://aka.ms/HoloLensDocs-SecureOfflineSample) sestavte PPKG.
1. Příprava offline [obchodní aplikace pro nasazení PPKG](app-deploy-provisioning-package.md) 


## <a name="configure"></a>Konfigurace

Vytvoření zřizovacího balíčku zabezpečené konfigurace

1. Na počítači spusťte nástroj WCD.
1. Vyberte **Soubor -> Otevřít projekt.**
  1. Přejděte do umístění dříve uložené OfflineSecureHL2_Sample složky a vyberte: OfflineSecureHL2_Sample.icdproj.xml
1. Projekt by se měl otevřít a teď byste měli mít seznam dostupných přizpůsobení:

   > [!div class="mx-imgBorder"]
   > ![Snímek obrazovky s konfiguračním balíčkem otevřeným ve WCD](images/offline-secure-sample-wcd.png)

   Konfigurace nastavené v tomto zřizovacího balíčku:
   
   |     Položka                                                |     Nastavení                       |     Popis                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     Účty a uživatelé                                    |     Místní uživatelské jméno & heslo    |     U těchto offline zařízení musí všichni uživatelé zařízení nastavit a sdílet jedno uživatelské jméno a heslo.          |
   |     První prostředí / HoloLens / SkipCalibration       |     Ano                          |     Přeskočí jen počáteční nastavení zařízení.                                                                             |
   |     První zkušenosti / HoloLens / SkipTraining          |     Ano                          |     Přeskočí trénování zařízení během počátečního nastavení zařízení.                                                                              |
   |     První prostředí / HoloLens / Wi-Fi                  |     Ano                          |     Přeskočí Wi-Fi konfigurace během počátečního nastavení zařízení.                                                                                 |
   |     Zásady/Připojení/AllowBluetooth                |     No                            |     Zakáže Bluetooth                                                                                                             |
   |     Zásady/Prostředí/AllowCortana                    |     No                            |     Zakáže Cortana (aby se eliminly potenciální problémy, protože mikrofony jsou zakázané).                                          |
   |     Zásady/MixedReality/MicrophoneDisabled            |     Yes                           |     Zakáže mikrofon.                                                                                                            |
   |     Zásady/Ochrana osobních údajů/LetAppsAccessLocation              |     Vynutit odepření                    |     Brání aplikacím v pokusu o přístup k datům o poloze (aby se eliminly potenciální problémy, protože sledování polohy je zakázané).    |
   |     Zásady/Ochrana osobních údajů/LetAppsAccessMicrophone            |     Vynutit odepření                    |     Brání aplikacím v pokusu o přístup k mikrofonům (aby se eliminly potenciální problémy, protože mikrofony jsou zakázané).           |
   |     Zásady/Zabezpečení/AllowAddProvisioningPackage       |     No                            |     Zabrání komukoli v přidávání zřizovacích balíčků, které by se mohly pokusit přepsat zásady uzamčení.                         |
   |     Zásady/Zabezpečení/AllowRemoveProvisioningPackage    |     No                            |     Zabrání komukoli v odebrání tohoto uzamčeného zřizovacího balíčku.                                                           |
   |     Zásady/Systém/AllowLocation                       |     No                            |     Zabrání zařízení v pokusu o sledování dat o poloze.                                                                        |
   |     Zásady/Wi-Fi/PovolitWiFi                             |     No                            |     Zakáže Wi-Fi                                                                                                                 |

1. V části Nastavení modulu runtime vyberte **Účty / uživatelé / Uživatelské jméno: Holo / Heslo.**

   Poznamenejte si heslo a v případě potřeby resetujte.

1. Přejděte na UniversalAppInstall / UserContextApp a nakonfigurujte [obchodní aplikaci,](app-deploy-provisioning-package.md) kterou nasazujete do těchto zařízení.

   > [!div class="mx-imgBorder"]
   > ![Snímek obrazovky s přidáním aplikace do WCD](images/offline-secure-sample-wcd-usercontextapp2.png)

1. Po dokončení vyberte tlačítko Exportovat a postupujte podle všech výtek, dokud se nevytácí zřizovací balíček.

   > [!div class="mx-imgBorder"]
   > ![Snímek obrazovky s tlačítkem Exportovat pro tento balíček v WCD](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>Nasadit

1. Připojení KABELEM USB připojte HL2 Windows 10 počítači.
1. Spusťte nástroj ARC a vyberte **HoloLens 2.**

   ![HoloLens 2 úvodní obrazovky čistého zpětného lomítka.](images/ARC2.png)

1. Na další obrazovce vyberte **Ruční výběr balíčku.**

   ![HoloLens s informacemi o 2 ARC.](images/arc_device_info.png)

1. Přejděte na dříve stažený soubor .ffu a vyberte **Otevřít.**
1. Na stránce Upozornění vyberte **Pokračovat.**

   ![HoloLens upozornění 2 ARC.](images/arc_warning.png)

1. Počkejte, až nástroj ARC dokončí instalaci HoloLens 2 operačního systému.
1. Po dokončení instalace a spuštění zařízení přejděte z počítače do složky Průzkumník souborů a zkopírujte dříve uložený soubor PPKG do složky zařízení.

   > [!div class="mx-imgBorder"]
   > ![Soubor PPKG na počítači v Průzkumník souborů okně.](images/offline-secure-file-explorer.png)

1. Na obrazovce HoloLens 2 spusťte stisknutím následující kombinace tlačítek zřizovací  balíček: **Klepněte** současně na Snížení objemu a tlačítko napájení.
1. Zobrazí se výzva k použití zřizovacího balíčku a vyberte **Potvrdit.**
1. Po dokončení zřizovacího balíčku vyberte **OK.**
1. Pak byste měli být vyzváni k přihlášení k zařízení pomocí sdíleného místního účtu a hesla.

## <a name="maintain"></a>Údržba

S touto konfigurací se doporučuje restartovat výše uvedený proces a zařízení znovu zobrazit v nástroji ARC a použít nový PPKG k provádění aktualizací operačního systému nebo aplikací.
