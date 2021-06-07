---
title: Podnikový zápis zařízení HoloLens na adrese MAC s omezeným Wi-Fi prostředím
description: Postup adresy MAC pro síť na zařízeních s HoloLens 2
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
ms.openlocfilehash: a577eace62040e2d48de5d3e4cc99ef108bd006c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111379227"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a>Podnikový zápis zařízení HoloLens na adrese MAC s omezeným Wi-Fi prostředím

Tento dokument popisuje běžný scénář, který jsme identifikovali v rámci zákaznických prostředí, kde je Wi-Fi omezen adresami MAC, nebo jsou pro připojení k bezdrátovým sítím vyžadovány certifikáty.

## <a name="example-scenario"></a>Ukázkový scénář

Mnoho zákazníků v zabezpečených prostředích má omezení pro bezdrátové nebo kabelové sítě, které umožní úspěšně připojit schválená zařízení (na základě adres MAC). To může být vynutilo filtrování adres MAC v bezdrátovém přístupovém bodě nebo prostřednictvím serveru DHCP. Kromě toho je možné některé bezdrátové sítě chránit pomocí protokolu PEAP, což vyžaduje, aby se pro zařízení před ověřením v bezdrátové síti používal certifikát.

V tomto scénáři můžou dva klíčové požadavky způsobit zpoždění nebo vyžadovat ruční zásah při připojování zařízení s HoloLens k síti:

- Aby se zařízení úspěšně připojilo k bezdrátové síti, musí se k němu použít bezdrátový certifikát protokolu PEAP.
- Adresa MAC Wi-Fi adaptéru HoloLens musí být zaregistrovaná.

Základní problémy s výše uvedenými požadavky:

1. Adresa MAC se v současnosti dá identifikovat jenom z aplikace nastavení v zařízení nebo z Intune po úspěšné registraci.

2. Bez adresy MAC se nemůže zařízení připojit k síti Wi-Fi, aby bylo možné zahájit registraci.

3. Ruční alternativní řešení těchto problémů vyžadují, aby určitý pracovník komunikoval se zařízením.

## <a name="solutions"></a>Řešení

Existuje mnoho způsobů, jak tuto situaci zlepšit, v závislosti na infrastruktuře dostupné v rámci prostředí.

| Řešení | Výhody | Požadavky |
| --- | --- | --- |
| Zřizovací balíček s adaptérem Ethernet | Vylepšuje možnosti počátečního nastavení a umožňuje rychlejší práci v technikech. | Kompatibilní s rozhraním USB – rozbočovač USB-C + adaptér sítě Ethernet a technik bude stále muset pracovat se zařízením pro zachycení počítače MAC a finalizaci počátečního souboru. |
| Autopilotování pomocí registrace v Intune přes Ethernet | Toto je připojení s jedním krokem a registrace zařízení do prostředí zákazníka. Záznam MAC je možné dokončit, aniž by bylo nutné pracovat se zařízením. | Povolená Intune pro tenanta AAD zákazníka a adaptér Ethernet USB-C kompatibilní s HoloLens |
| Automatizované vytváření sestav adres MAC | Když jsou zařízení zaregistrovaná v tenantovi Intune, může skript vykázat adresu MAC technikovi. | Rutiny PowerShellu pro Intune |

## <a name="provisioning-package-with-ethernet-adaptor"></a>Zřizovací balíček s adaptérem Ethernet

> [!NOTE] 
> Pokud je v drátové síti i v závislosti na omezeních pro MAC, musí být adresa MAC rozbočovače USB-C + adaptér sítě Ethernet také předem schválená. S tímto adaptérem byste měli dbát, protože umožní přístup k síti z jiných zařízení.

### <a name="requirements"></a>Požadavky

- Port drátové sítě s přístupem k síti zákazníka
- Rozbočovač USB-C kompatibilní s HoloLens s adaptérem Ethernet – všechny adaptéry, které nevyžadují žádné další ovladače nebo instalace aplikací, by měly být vhodné.
- Zřizovací balíček obsahující:
  - Obsahující informace o bezdrátové síti a certifikát
  - Volitelně obsahující informace o registraci pro Azure AD organizace
  - Obsahující všechna další požadovaná nastavení zřizování

### <a name="process"></a>Proces

Tento proces se může lišit v závislosti na úrovni softwaru daného zařízení. Pokud má zařízení [aktualizaci květen 2004](hololens-release-notes.md#windows-holographic-version-2004), postupujte podle následujících kroků.

1. Zřizovací balíček umístěte do kořenového adresáře USB Stick a připojte se k rozbočovači.
2. Připojte kabel sítě Ethernet k adaptéru rozbočovače + Ethernet.
3. Připojte rozbočovač USB-C k zařízení HoloLens.
4. Zapněte HoloLens a vložte ho do zařízení.
5. Pro použití zřizovacího balíčku stiskněte **tlačítko dolů a vypínač** .
6. Technik se teď může dodržet na začátku počáteční hodnoty a po dokončení otevřete aplikaci nastavení, která načte adresu MAC zařízení.

Pokud má zařízení Build operačního systému před [aktualizací květen 2004](hololens-release-notes.md#windows-holographic-version-2004), postupujte podle následujících kroků.

1. Zapněte HoloLens a připojte zařízení k počítači.
2. Zařízení by se mělo zobrazit na počítači jako zařízení úložiště souborů.
3. Zkopírování zřizovacího balíčku do zařízení
4. Připojte kabel Ethernet k rozbočovači.
5. Připojte rozbočovač USB-C k zařízení HoloLens.
6. Umístit na HoloLens
7. Pro použití zřizovacího balíčku stiskněte tlačítko **dolů a vypínač** .
8. Technik se teď může dodržet na začátku počáteční hodnoty a po dokončení otevřete aplikaci nastavení, která načte adresu MAC zařízení.

### <a name="benefits"></a>Výhody

To umožní "jedinému dotyku" zařízení, použít správný zřizovací balíček a shromažďovat adresu MAC zařízení. [Zřizovací balíčky se dají vytvořit podle pokynů uvedených tady.](https://docs.microsoft.com/hololens/hololens-provisioning)

## <a name="autopilot-with-intune-enrollment"></a>Automatický pilotní nasazení pomocí Intune

### <a name="requirements"></a>Požadavky

- Port drátové sítě s přístupem k síti zákazníka
- Zařízení HoloLens s Windows holografickým 2004
- Ethernetový adaptér USB-C kompatibilní s HoloLens
- Nastavení a povolení Intune pro tenanta zákazníka
- Zařízení zaregistrované pro autopilotování a naimportované do tenanta zákazníka
- Zásady Intune definované pro zařízení:
   - Obsahující informace o bezdrátové síti a certifikát
   - Obsahující všechna další požadovaná nastavení zřizování

To umožní zákazníkovi s pokročilými požadavky na síť zaregistrovat zařízení v praxi, škálovatelný přístup

Další požadavky budete potřebovat, jak je uvedeno níže:
1. [Povolte tenanta pro verzi Preview programu autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot).
1. Vytvořte zásady HoloLens pro nahrazení zřizovacího balíčku v Intune.
1. Vytvořte zásady pro HoloLens Intune.
1. Přiřaďte zařízení ke správné skupině.

### <a name="process"></a>Proces

1. Připojte kabel sítě Ethernet k adaptéru a připojte adaptér k portu USB-C na zařízení HoloLens 2.

2. Zapněte HoloLens.

3. Zařízení by se mělo automaticky připojit k Internetu během OOBE přes adaptér sítě Ethernet. Měl by detekovat konfiguraci autopilotu a automaticky se registrovat v Azure AD a Intune.

4. Zařízení použije požadované Wi-Fi certifikáty a další konfiguraci podle potřeby prostřednictvím Intune.

5. Po dokončení může technik načíst portál Intune (správce koncových bodů) a přejít na stránku vlastností zařízení na stránce **Domů-> zařízení-> zařízení-> hardware**.

6. Adresa MAC Wi-Fi bude viditelná v portálu Intune.

   ![Adresa MAC přes Intune](images/mac-address-intune.jpg)

7. Technik přidá tuto adresu MAC jako povolené zařízení.

### <a name="benefits"></a>Výhody

Tím umožníte, aby se v Technikě v rámci nasazení v nástroji "prošly" možnosti nasazení, které zařízení dokáže přejít do služby Azure AD a Intune, aniž by bylo nutné, aby zařízení využilo zařízení nebo ručně nespolupracovalo s prostředím HoloLens.

## <a name="reporting-of-mac-addresses-to-the-technician"></a>Hlášení adres MAC technikům

### <a name="requirements"></a>Požadavky

- Autorizace "Intune Graph PowerShellu" proti klientovi zákazníka
- Instalace prostředí Intune Graph PowerShellu na stroji technici
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- Přístup pro čtení do prvků spravovaná zařízení v Intune (Operátor helpdesku nebo výše nebo vlastní role)

V současné době neexistuje jednoduchý způsob, jak aktivovat příkaz automatizace na základě registrace nového zařízení v Intune. Proto tento příkaz poskytne technikovi jednoduchý způsob, jak načíst adresu MAC, aniž by se musela přihlásit na portál a ručně ji načíst.

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

Tato akce vrátí název a adresu MAC všech zařízení HoloLens, která byla zaregistrována za posledních 30 dní.

![Adresa MAC prostřednictvím PowerShellu](images/mac-address-powershell.jpg)

### <a name="process"></a>Proces

Po dokončení registrace Intune technik spustí výše uvedený skript, který načte adresu MAC.
