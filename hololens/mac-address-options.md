---
title: Enterprise registrace zařízení HoloLens v prostředí Wi-Fi s omezením adresy MAC
description: postup adresy MAC pro síť na zařízeních HoloLens 2
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
ms.openlocfilehash: d21a63aae94f5ea5269f61fe319a9036626de1b4
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428404"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a>Enterprise registrace zařízení HoloLens v prostředí Wi-Fi s omezením adresy MAC

Tento dokument popisuje běžný scénář, který jsme identifikovali v rámci zákaznických prostředí, kde je Wi-Fi omezen adresami MAC, nebo jsou pro připojení k bezdrátovým sítím vyžadovány certifikáty.

## <a name="example-scenario"></a>Ukázkový scénář

Mnoho zákazníků v zabezpečených prostředích má omezení pro bezdrátové nebo kabelové sítě, které umožní úspěšně připojit schválená zařízení (na základě adres MAC). To může být vynutilo filtrování adres MAC v bezdrátovém přístupovém bodě nebo prostřednictvím serveru DHCP. Kromě toho je možné některé bezdrátové sítě chránit pomocí protokolu PEAP, což vyžaduje, aby se pro zařízení před ověřením v bezdrátové síti používal certifikát.

v tomto scénáři můžou dva klíčové požadavky způsobit zpoždění nebo vyžadovat ruční zásah při připojení zařízení HoloLens k síti:

- Aby se zařízení úspěšně připojilo k bezdrátové síti, musí se k němu použít bezdrátový certifikát protokolu PEAP.
- adresa MAC HoloLens Wi-Fi adaptéru musí být zaregistrované.

Základní problémy s výše uvedenými požadavky:

1. adresa MAC se v současnosti dá identifikovat jenom z aplikace Nastavení v zařízení nebo v intune po úspěšné registraci.

2. Bez adresy MAC se nemůže zařízení připojit k síti Wi-Fi, aby bylo možné zahájit registraci.

3. Ruční alternativní řešení těchto problémů vyžadují, aby určitý pracovník komunikoval se zařízením.

## <a name="solutions"></a>Řešení

Existuje mnoho způsobů, jak tuto situaci zlepšit, v závislosti na infrastruktuře dostupné v rámci prostředí.

| Řešení | Výhody | Požadavky |
| --- | --- | --- |
| Zřizovací balíček s adaptérem Ethernet | Vylepšuje možnosti počátečního nastavení a umožňuje rychlejší práci v technikech. | HoloLens kompatibilní rozbočovače USB-C + adaptér Ethernet a technik bude i nadále muset pracovat se zařízením pro zachycení MAC a finalizaci počátečního souboru. |
| Autopilotování pomocí registrace v Intune přes Ethernet | Toto je připojení s jedním krokem a registrace zařízení do prostředí zákazníka. Záznam MAC je možné dokončit, aniž by bylo nutné pracovat se zařízením. | povolená intune pro tenanta AAD zákazníka a adaptér Ethernet USB-C kompatibilní s HoloLens |
| Automatizované vytváření sestav adres MAC | Když jsou zařízení zaregistrovaná v tenantovi Intune, může skript vykázat adresu MAC technikovi. | Rutiny PowerShellu pro Intune |

## <a name="provisioning-package-with-ethernet-adaptor"></a>Zřizovací balíček s adaptérem Ethernet

> [!NOTE] 
> Pokud je v drátové síti i v závislosti na omezeních pro MAC, musí být adresa MAC rozbočovače USB-C + adaptér sítě Ethernet také předem schválená. S tímto adaptérem byste měli dbát, protože umožní přístup k síti z jiných zařízení.

### <a name="requirements"></a>Požadavky

- Port drátové sítě s přístupem k síti zákazníka
- HoloLens Kompatibilní rozbočovač USB-C s adaptérem Ethernet – všechny adaptéry, které nevyžadují žádné další ovladače nebo instalace aplikací, by měly být vhodné.
- Zřizovací balíček obsahující:
  - Obsahující informace o bezdrátové síti a certifikát
  - Volitelně obsahující informace o registraci pro Azure AD organizace
  - Obsahující všechna další požadovaná nastavení zřizování

### <a name="process"></a>Proces

Tento proces se může lišit v závislosti na úrovni softwaru daného zařízení. Pokud má zařízení [aktualizaci květen 2004](hololens-release-notes.md#windows-holographic-version-2004), postupujte podle následujících kroků.

1. Zřizovací balíček umístěte do kořenového adresáře USB Stick a připojte se k rozbočovači.
2. Připojení Kabel z Ethernetu na adaptér rozbočovače + Ethernet.
3. Připojení rozbočovač USB-C pro HoloLens zařízení
4. zapněte HoloLens a umístěte je do zařízení.
5. Pro použití zřizovacího balíčku stiskněte **tlačítko dolů a vypínač** .
6. technik teď může sledovat počáteční čas a po dokončení otevřít aplikaci Nastavení, která načte adresu MAC zařízení.

Pokud má zařízení Build operačního systému před [aktualizací květen 2004](hololens-release-notes.md#windows-holographic-version-2004), postupujte podle následujících kroků.

1. zapněte HoloLens a připojte zařízení k počítači.
2. Zařízení by se mělo zobrazit na počítači jako zařízení úložiště souborů.
3. Zkopírování zřizovacího balíčku do zařízení
4. Připojení Kabel Ethernet k rozbočovači.
5. Připojení rozbočovač USB-C pro HoloLens zařízení
6. Umístit na HoloLens
7. Pro použití zřizovacího balíčku stiskněte tlačítko **dolů a vypínač** .
8. technik teď může sledovat počáteční čas a po dokončení otevřít aplikaci Nastavení, která načte adresu MAC zařízení.

### <a name="benefits"></a>Výhody

To umožní "jedinému dotyku" zařízení, použít správný zřizovací balíček a shromažďovat adresu MAC zařízení. [Zřizovací balíčky se dají vytvořit podle pokynů uvedených tady.](hololens-provisioning.md)

## <a name="autopilot-with-intune-enrollment"></a>Automatický pilotní nasazení pomocí Intune

### <a name="requirements"></a>Požadavky

- Port drátové sítě s přístupem k síti zákazníka
- HoloLens zařízení s Windows holografickou 2004
- HoloLens Kompatibilní adaptér Ethernet USB-C
- Nastavení a povolení Intune pro tenanta zákazníka
- Zařízení zaregistrované pro autopilotování a naimportované do tenanta zákazníka
- Zásady Intune definované pro zařízení:
   - Obsahující informace o bezdrátové síti a certifikát
   - Obsahující všechna další požadovaná nastavení zřizování

To umožní zákazníkovi s pokročilými požadavky na síť zaregistrovat zařízení v praxi, škálovatelný přístup

Další požadavky budete potřebovat, jak je uvedeno níže:
1. [Povolte tenanta pro verzi Preview programu autopilot](hololens2-autopilot.md).
1. vytvořte zásady HoloLens pro nahrazení zřizovacího balíčku v intune.
1. vytvořte zásady HoloLens intune.
1. Přiřaďte zařízení ke správné skupině.

### <a name="process"></a>Proces

1. Připojení kabel sítě ethernet k adaptéru a připojte adaptér k portu USB-C na zařízení HoloLens 2.

2. Zapněte HoloLens.

3. Zařízení by se mělo automaticky připojit k Internetu během OOBE přes adaptér sítě Ethernet. Měl by detekovat konfiguraci autopilotu a automaticky se registrovat v Azure AD a Intune.

4. Zařízení použije požadované Wi-Fi certifikáty a další konfiguraci podle potřeby prostřednictvím Intune.

5. po dokončení může technik načíst portál intune (Endpoint Manager) a přejít na stránku vlastností zařízení na stránce **Home-> devices-> device-> Hardware**.

6. Adresa MAC Wi-Fi bude viditelná v portálu Intune.

   ![Adresa MAC prostřednictvím Intune.](images/mac-address-intune.jpg)

7. Technik přidá tuto adresu MAC jako povolené zařízení.

### <a name="benefits"></a>Výhody

tím umožníte, aby se v technikě v rámci nasazení v nástroji "prošla" možnosti nasazení, které zařízení dokáže přejít do služby Azure AD a intune, aniž by bylo nutné, aby zařízení využilo nebo ručně spolupracovalo s HoloLensm prostředím.

## <a name="reporting-of-mac-addresses-to-the-technician"></a>Hlášení adres MAC technikům

### <a name="requirements"></a>Požadavky

- autorizace "intune Graph powershellu" proti klientovi zákazníka
- instalace intune Graph powershellu na stroji technici.
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- Přístup pro čtení do prvků spravovaná zařízení v Intune (Operátor helpdesku nebo výše nebo vlastní role)

V současné době neexistuje jednoduchý způsob, jak aktivovat příkaz automatizace na základě registrace nového zařízení v Intune. Proto tento příkaz poskytne technikovi jednoduchý způsob, jak načíst adresu MAC, aniž by se musela přihlásit na portál a ručně ji načíst.

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

tato akce vrátí název a adresu MAC všech HoloLens zařízení, která byla zaregistrována za posledních 30 dní.

![Adresa MAC prostřednictvím PowerShellu.](images/mac-address-powershell.jpg)

### <a name="process"></a>Proces

Po dokončení registrace Intune technik spustí výše uvedený skript, který načte adresu MAC.
