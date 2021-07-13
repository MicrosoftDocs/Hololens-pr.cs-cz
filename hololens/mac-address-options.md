---
title: Enterprise Registrace zařízení HoloLens v prostředí s omezenými adresami MAC Wi-Fi Prostředí
description: Jak adresou MAC pro síť na zařízeních HoloLens 2
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: mata
ms.topic: article
ms.localizationpriority: high
ms.date: 10/01/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 7938a433921a096913986f5eccff953fd17f1534
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639433"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a>Enterprise Registrace zařízení HoloLens v prostředí s omezenými adresami MAC Wi-Fi Prostředí

Tento dokument popisuje běžný scénář, který jsme identifikovali v zákaznických prostředích, kde je Wi-Fi omezený adresami MAC, nebo jsou vyžadovány certifikáty pro připojení k bezdrátovým sítím.

## <a name="example-scenario"></a>Ukázkový scénář

Mnoho zákazníků v zabezpečených prostředích má omezení v bezdrátových nebo drátových sítích, která umožní úspěšné připojení jenom schváleným zařízením (na základě adres MAC). To může být vynuceno prostřednictvím filtrování adres MAC v bezdrátovém přístupového bodu nebo prostřednictvím serveru DHCP. Kromě toho některé bezdrátové sítě mohou být chráněny protokolem PEAP, který vyžaduje, aby certifikát se použil na zařízení před ověřením v bezdrátové síti.

V tomto scénáři mohou dva klíčové požadavky způsobit zpoždění nebo vyžadovat ruční zásah HoloLens zařízení k síti:

- Certifikát protokolu PEAP bezdrátové sítě musí být použita na zařízení před úspěšné připojení zařízení k bezdrátové síti.
- Adresa MAC adaptéru HoloLens Wi-Fi musí být zaregistrovaná.

Základní problémy s výše uvedenými požadavky jsou následující:

1. Adresu MAC je aktuálně možné identifikovat pouze z Nastavení zařízení nebo z Intune po úspěšné registraci.

2. Bez adresy MAC se zařízení nemůže připojit ke Wi-Fi Network a zahájit registraci.

3. Ruční alternativní řešení těchto problémů vyžadují, aby technik se zařízením komunikoval.

## <a name="solutions"></a>Řešení

V závislosti na infrastruktuře dostupné v rámci prostředí existuje mnoho způsobů, jak tuto situaci vylepšit.

| Řešení | Výhody | Požadavky |
| --- | --- | --- |
| Zřizovací balíček s adaptérem sítě Ethernet | Vylepšuje prostředí pro OOBE a umožňuje rychlejší prostředí techniků. | HoloLens adaptérem USB-C Hub + Ethernet a technik bude muset se zařízením stále pracovat kvůli zachycení mac a finalizaci OOBE. |
| Autopilot s registrací Přes Ethernet v Intune | Jedná se o jednokrokové připojení a registraci zařízení do prostředí zákazníka. Zachytávání maců je možné dokončit bez nutnosti interakce se zařízením. | Služba Intune povolená pro tenanta AAD zákazníka a HoloLens adaptér sítě Ethernet KOMPATIBILNÍ s USB-C |
| Automatizované generování sestav adres MAC | Když jsou zařízení zaregistrovaná v tenantovi Intune, skript může adresu MAC nahlásit technikovi. | Rutiny PowerShellu pro Intune |

## <a name="provisioning-package-with-ethernet-adaptor"></a>Zřizovací balíček s adaptérem sítě Ethernet

> [!NOTE] 
> Pokud se na drátovou síť vztahují také omezení MAC, bude také potřeba předem schválit adresu MAC rozbočovače USB-C a ethernetového adaptéru. Tento adaptér je třeba pečovat, protože umožňuje přístup k síti z jiných zařízení.

### <a name="requirements"></a>Požadavky

- Port drátové sítě s přístupem k síti zákazníka
- HoloLens Kompatibilní rozbočovač USB-C s ethernetovým adaptérem – Jakýkoli adaptér, který nevyžaduje žádné další ovladače nebo instalaci aplikací, by měl být vhodný.
- Zřizovací balíček obsahující:
  - Obsahující informace o bezdrátové síti a certifikát
  - Volitelně obsahující informace o registraci pro Azure AD organizace
  - Obsahuje další požadovaná nastavení zřizování.

### <a name="process"></a>Proces

Proces se může lišit v závislosti na úrovni softwaru zařízení. Pokud má zařízení aktualizaci [z května 2004,](hololens-release-notes.md#windows-holographic-version-2004)postupujte podle následujících kroků.

1. Umístěte zřizovací balíček do kořenového adresáře USB flash disku a připojte se k rozbočovači.
2. Připojení Ethernetový kabel k rozbočovači + ethernetovému adaptéru.
3. Připojení Rozbočovač USB-C HoloLens zařízení.
4. Zapněte HoloLens zařízení.
5. Stisknutím tlačítka **Volume Down (Snížení objemu)** a Power (Napájení) použijte zřizovací balíček.
6. Technik teď může postupovat podle pokynů pro OOBE a po dokončení otevřít aplikaci Nastavení a načíst adresu MAC zařízení.

Pokud má zařízení build operačního systému před aktualizací z května [2004,](hololens-release-notes.md#windows-holographic-version-2004)postupujte následovně.

1. Zapněte počítač HoloLens připojte zařízení k počítači.
2. Zařízení by se mělo v počítači zobrazit jako zařízení úložiště souborů.
3. Zkopírování zřizovacího balíčku do zařízení
4. Připojení Ethernetový kabel k rozbočovači.
5. Připojení Rozbočovač USB-C HoloLens zařízení.
6. Dejte na HoloLens
7. Stisknutím tlačítka **Volume Down (Snížení objemu)** a Power (Napájení) použijte zřizovací balíček.
8. Technik teď může postupovat podle pokynů pro OOBE a po dokončení otevřít aplikaci Nastavení a načíst adresu MAC zařízení.

### <a name="benefits"></a>Výhody

To umožní jedinému dotykovému ovládání zařízení použít správný zřizovací balíček a shromáždit adresu MAC zařízení. [Zřizovací balíčky můžete vytvořit podle těchto pokynů.](hololens-provisioning.md)

## <a name="autopilot-with-intune-enrollment"></a>Autopilot s registrací do Intune

### <a name="requirements"></a>Požadavky

- Port drátové sítě s přístupem k síti zákazníka
- HoloLens zařízení s Windows Holographic 2004
- HoloLens Kompatibilní ethernetový adaptér USB-C
- Nastavení a povolení Intune pro tenanta zákazníka
- Zařízení zaregistrované pro Autopilot a importované do tenanta zákazníka
- Zásady Intune definované pro zařízení:
   - Obsahující informace o bezdrátové síti a certifikát
   - Obsahuje další požadovaná nastavení zřizování.

To umožní zákazníkovi s pokročilými požadavky na síť zaregistrovat zařízení pomocí hands-off a škálovatelného přístupu.

Budete potřebovat další požadavky, jak je uvedeno níže:
1. [Povolte tenanta pro Autopilot Preview.](hololens2-autopilot.md)
1. Vytvořte zásady HoloLens, které nahradí zřizovací balíček v Rámci Intune.
1. Vytvořte HoloLens Intune.
1. Přiřaďte zařízení ke správné skupině.

### <a name="process"></a>Proces

1. Připojení ethernetový kabel k adaptéru a připojte adaptér k portu USB-C na HoloLens 2.

2. Zapněte HoloLens.

3. Zařízení by se mělo automaticky připojit k internetu během OOBE přes ethernetový adaptér. Měla by zjistit konfiguraci Autopilotu a automaticky se zaregistrovat v Azure AD a Intune.

4. Zařízení použije požadované certifikáty Wi-Fi a další konfiguraci podle potřeby prostřednictvím Intune.

5. Po dokončení může technik načíst portál Intune (Endpoint Manager) a přejít na stránku vlastností zařízení na domovské stránce **-> Devices -> DeviceName -> Hardware**.

6. Adresa MAC Wi-Fi zobrazí na portálu Intune.

   ![Adresa MAC přes Intune](images/mac-address-intune.jpg)

7. Technik přidá tuto adresu MAC jako povolené zařízení.

### <a name="benefits"></a>Výhody

To technikovi umožní nasazení "bez problémů", kdy zařízení může přejít z krabice do Azure AD a Intune, aniž by technik museli zařízení používat nebo ručně pracovat s HoloLens prostředím.

## <a name="reporting-of-mac-addresses-to-the-technician"></a>Hlášení adres MAC technikovi

### <a name="requirements"></a>Požadavky

- Autorizace "Intune Graph PowerShellu" vůči zákaznickému tenantovi
- Instalace Intune Graph PowerShellu na počítači techniků.
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- Přístup pro čtení k prvkům "Spravovaná zařízení" v Intune. (Operátor help desky nebo vyšší nebo vlastní role)

V současné době neexistuje žádný "jednoduchý" způsob aktivace příkazu automatizace na základě registrace nového zařízení v Intune. Tento příkaz proto technikovi poskytne jednoduchý způsob, jak získat adresu MAC, aniž by se muset přihlásit k portálu a ručně ji načíst.

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

Vrátí se název a adresa MAC všech zařízení HoloLens která byla zaregistrovaná během posledních 30 dnů.

![Adresa MAC přes PowerShell](images/mac-address-powershell.jpg)

### <a name="process"></a>Proces

Po dokončení registrace Intune technik spustí výše uvedený skript, který načte adresu MAC.
