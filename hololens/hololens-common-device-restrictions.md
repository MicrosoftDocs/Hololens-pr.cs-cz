---
title: Běžná omezení zařízení
description: Udržujte si aktuální informace o běžných omezeních zařízení a nastaveních pro zařízení hybridní reality HoloLens.
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
ms.openlocfilehash: e9c44466da375611f8864eae1b6e6ceea3ef9b09
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377531"
---
# <a name="common-device-restrictions"></a>Běžná omezení zařízení 

Tato příručka pomáhá IT specialistům pochopit nejčastěji používané možnosti správy dostupné pro Windows 10 Holographic operační systém v podniku. Informace o tom, jak tyto zásady povolil váš dodavatel MDM, najdete v dokumentaci k systému MDM. Ne všechny systémy MDM podporují všechna nastavení popsaná v tomto průvodci. Některé podporují vlastní zásady prostřednictvím souborů XML OMA-URI. Viz [Microsoft Intune podpory vlastních zásad.](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) Zásady vytváření názvů se také můžou u jednotlivých dodavatelů MDM lišit.

## <a name="prevent-changing-of-settings"></a>Zabránění změně nastavení
Zaměstnanci mají obvykle povoleno změnit určitá nastavení osobních zařízení, která můžete chtít uzamknout na firemních zařízeních. Zaměstnanci mohou interaktivně upravovat určitá nastavení HoloLens prostřednictvím uživatelského rozhraní nastavení. Pomocí MDM můžete omezit, co mohou uživatelé měnit. Následující seznam uvádí běžně používaná nastavení MDM, Windows 10 Holographic podporuje ke konfiguraci omezení nastavení:
-   [Povolit síť VPN:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn) Umožňuje uživateli změnit nastavení sítě VPN.
-   [Povolit ruční konfiguraci WiFi:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration) Umožňuje uživatelům vytvářet Wi-Fi mimo zřízené sítě MDM.
-   [Povolit ruční zrušení registrace MDM](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience#experience-allowmanualmdmunenrollment) Jestli mají uživatelé povoleno odstranit pracovní účet (tj. zrušit registraci zařízení v systému MDM)

Přidáno [ve Windows Holographic verze 20H2](hololens-release-notes.md#windows-holographic-version-20h2) pro zařízení HoloLens 2:
- [Povolit přidání zřizovacího balíčku:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage) Přepněte, pokud uživatelé mohou přidat nové zřizovací balíčky a přepsat je novými hodnotami.
- [Povolit odebrání zřizovacího balíčku:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) Přepněte, pokud uživatelé mohou odebrat zřizovací balíčky, což jim umožní přepínat dříve uzamčená nastavení.

Další podrobnosti o možnostech zásad najdete v tématu o podporovaných csP zásad [pro HoloLens.](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## <a name="hardware-restrictions"></a>Hardwarová omezení
Windows 10 Holographic používají moderní technologii, která zahrnuje oblíbené hardwarové funkce, jako jsou fotoaparáty, mikrofony, mluvčí, rozhraní USB, rozhraní Bluetooth a Wi-Fi. K řízení dostupnosti těchto funkcí můžete použít hardwarová omezení.
Následující seznam uvádí běžně používaná nastavení MDM, Windows 10 Holographic podporuje konfiguraci hardwarových omezení:

> [!NOTE]
> Některá z těchto hardwarových omezení ovlivňují připojení a pomáhají při ochraně dat.

-   [Povolit Wi-Fi:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) Určuje, jestli uživatelé mohou na svých zařízeních povolit a používat přepínač Wi-Fi.
-   [Povolit připojení USB:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) Jestli je povolené připojení USB (nemá vliv na usb flash disk)
-   [Povolit Bluetooth:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) Jestli uživatelé mohou na svých zařízeních povolit a používat přepínač Bluetooth
-   [Omezit kameru:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesscamera) Určuje, jestli aplikace pro Windows mají přístup ke kameře.
-   [Omezit mikrofony:](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccessmicrophone) Určuje, jestli aplikace pro Windows mají přístup k mikrofonu.

Přidáno [ve Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) pro zařízení HoloLens 2. 
- [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery) Nastavte dobu, po kterou se displej vypne, a vypnutím displeje zařízení uzamkne. 
- [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin) Nastavte dobu, po kterou se displej vypne, a vypnutím displeje zařízení uzamknete. 
