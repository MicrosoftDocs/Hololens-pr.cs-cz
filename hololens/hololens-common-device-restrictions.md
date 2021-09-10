---
title: Běžná omezení zařízení
description: Udržujte si častá omezení a nastavení zařízení pro zařízení HoloLens hybridní realitou.
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
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428696"
---
# <a name="common-device-restrictions"></a>Běžná omezení zařízení 

Tato příručka pomáhá IT specialistům pochopit nejčastěji používané možnosti správy dostupné pro Windows 10 Holographic operační systém v podniku. Informace o tom, jak tyto zásady povolil váš dodavatel MDM, najdete v dokumentaci k systému MDM. Ne všechny systémy MDM podporují všechna nastavení popsaná v tomto průvodci. Některé podporují vlastní zásady prostřednictvím souborů XML OMA-URI. Viz [Microsoft Intune podpory vlastních zásad.](/mem/intune/configuration/custom-settings-windows-10) Zásady vytváření názvů se také můžou u jednotlivých dodavatelů MDM lišit.

## <a name="prevent-changing-of-settings"></a>Zabránění změně nastavení
Zaměstnanci mají obvykle povoleno změnit určitá nastavení osobních zařízení, která můžete chtít uzamknout na firemních zařízeních. Zaměstnanci mohou interaktivně upravovat určitá nastavení HoloLens prostřednictvím uživatelského rozhraní nastavení. Pomocí MDM můžete omezit, co mohou uživatelé měnit. Následující seznam uvádí běžně používaná nastavení MDM, která Windows 10 Holographic konfigurace omezení nastavení:
-   [Povolit síť VPN:](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Umožňuje uživateli změnit nastavení sítě VPN.
-   [Povolit ruční konfiguraci WiFi:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Umožňuje uživatelům vytvářet Wi-Fi mimo zřízené sítě MDM.
-   [Povolit ruční zrušení registrace MDM](/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Jestli mají uživatelé povoleno odstranit pracovní účet (tj. zrušit registraci zařízení v systému MDM)

Přidáno [Windows Holographic verze 20H2](hololens-release-notes.md#windows-holographic-version-20h2) pro HoloLens 2:
- [Povolit přidání zřizovacího balíčku:](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Přepněte, pokud uživatelé mohou přidat nové zřizovací balíčky a přepsat je novými hodnotami.
- [Povolit odebrání zřizovacího balíčku:](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Přepněte, pokud uživatelé mohou odebrat zřizovací balíčky, což jim umožní přepínat dříve uzamčená nastavení.

Další podrobnosti o možnostech zásad najdete v tématu HoloLens [podporovaných csP zásad.](/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## <a name="hardware-restrictions"></a>Hardwarová omezení
Windows 10 Holographic používají moderní technologii, která zahrnuje oblíbené hardwarové funkce, jako jsou fotoaparáty, mikrofony, mluvčí, rozhraní USB, Bluetooth rozhraní a Wi-Fi. K řízení dostupnosti těchto funkcí můžete použít hardwarová omezení.
Následující seznam uvádí běžně používaná nastavení MDM, která Windows 10 Holographic konfigurace hardwarových omezení:

> [!NOTE]
> Některá z těchto hardwarových omezení ovlivňují připojení a pomáhají při ochraně dat.

-   [Povolit Wi-Fi:](/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Určuje, jestli uživatelé mohou na svých zařízeních povolit a používat přepínač Wi-Fi.
-   [Povolit připojení USB:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Jestli je povolené připojení USB (nemá vliv na usb flash disk)
-   [Povolit Bluetooth:](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Určuje, jestli uživatelé na svých zařízeních Bluetooth používat přepínač.
-   [Omezit kameru:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Určuje, jestli Windows budou mít aplikace přístup k fotoaparátu.
-   [Omezit mikrofony:](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Určuje, jestli Windows aplikace mají přístup k mikrofonu.

Přidáno [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) pro HoloLens 2. 
- [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) Nastavte dobu, po kterou se displej vypne, a vypnutím displeje zařízení uzamkne. 
- [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) Nastavte dobu, po kterou se displej vypne, a vypnutím displeje zařízení uzamkne. 
