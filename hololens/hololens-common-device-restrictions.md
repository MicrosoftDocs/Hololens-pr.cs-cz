---
title: Běžná omezení zařízení
description: udržujte si aktuální omezení a nastavení zařízení pro zařízení HoloLens mixed reality.
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 769cacc1803af9d9e9bf1079f8cd5671f194c3bc
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032236"
---
# <a name="common-device-restrictions"></a>Běžná omezení zařízení 

tato příručka pomáhá odborníkům v oblasti IT pochopit nejčastěji používané možnosti správy, které jsou dostupné pro Windows 10 Holographic operační systém v podniku. Informace o tom, jak jsou tyto zásady povolené vaším dodavatelem MDM, najdete v dokumentaci k systému MDM. Ne všechny systémy MDM podporují všechna nastavení popsaná v této příručce. Některé podporují vlastní zásady prostřednictvím souborů XML OMA-URI. další informace najdete v tématu [podpora Microsoft Intune pro vlastní zásady](/mem/intune/configuration/custom-settings-windows-10). Konvence pojmenování se můžou taky měnit mezi dodavateli MDM.

## <a name="prevent-changing-of-settings"></a>Zabránit změně nastavení
Zaměstnanci obvykle můžou měnit určitá nastavení osobních zařízení, která můžete chtít uzamknout v podnikových zařízeních. zaměstnanci můžou interaktivně upravovat určitá nastavení HoloLens prostřednictvím uživatelského rozhraní nastavení. Pomocí MDM můžete omezit, co můžou uživatelé měnit. následující seznam běžně používá nastavení MDM, které Windows 10 Holographic podporuje ke konfiguraci omezení nastavení:
-   [Povolení sítě VPN:](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Povolí uživateli změnit nastavení sítě VPN.
-   [Povolení ruční konfigurace Wi-Fi:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Umožňuje uživatelům vytvářet Wi-Fi připojení mimo zřízené sítě MDM.
-   [Povolení ručního zrušení registrace MDM](/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Jestli mají uživatelé povoleno odstranit pracovní účet (tj. zrušit registraci zařízení ze systému MDM)

přidáno do [Windows holografické verze 20H2](hololens-release-notes.md#windows-holographic-version-20h2) pro zařízení HoloLens 2:
- [Povolení přidávání zřizovacího balíčku:](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Přepínač, pokud uživatelé mohou přidávat nové zřizovací balíčky a přepsat je novými hodnotami.
- [Povolení odebrání zřizovacího balíčku:](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Přepínač, pokud uživatelé mohou odebrat zřizovací balíčky, což jim umožní přepnout dříve zamčená nastavení.

přečtěte si další podrobnosti o možnostech zásad v HoloLens podporovaných [zásadách csp](/windows/client-management/mdm/policy-csps-supported-by-hololens2) .

## <a name="hardware-restrictions"></a>Omezení hardwaru
Windows 10 Holographic zařízení využívají špičkovou technologii, která zahrnuje oblíbené funkce hardwaru, jako jsou kamery, mikrofony, reproduktory, rozhraní USB, Bluetooth rozhraní a Wi-Fi. K řízení dostupnosti těchto funkcí můžete použít hardwarová omezení.
následující seznam obsahuje běžně používaná nastavení MDM, která Windows 10 Holographic podporuje ke konfiguraci omezení hardwaru:

> [!NOTE]
> Některá z těchto hardwarových omezení mají vliv na připojení a pomáhají v ochraně dat.

-   [Povolení Wi-Fi:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Určuje, jestli uživatelé můžou na svých zařízeních povolit a používat radiostanici Wi-Fi.
-   [Povolení připojení USB:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Zda je povoleno připojení USB (neovlivňuje zpoplatnění přes rozhraní USB)
-   [Povolení Bluetooth:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) zda uživatelé mohou na svých zařízeních povolit a použít přepínač Bluetooth.
-   [Omezit fotoaparát:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) určuje, jestli aplikace Windows mají přístup ke kameře.
-   [Omezit mikrofony:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) určuje, jestli aplikace Windows mají přístup k mikrofonu.

přidáno v [Windows holografické verze virtualizačního 20H2](hololens-release-notes.md#windows-holographic-version-20h2) pro zařízení HoloLens 2. 
- [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) Nastavte dobu, po které se zobrazení vypne, a vypnutím displeje zamkne zařízení. 
- [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) Nastavte dobu, po které se zobrazení vypne, a vypnutím displeje zamkne zařízení. 
