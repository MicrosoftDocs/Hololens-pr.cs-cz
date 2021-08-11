---
title: HoloLens první (gen) verze
description: Přečtěte si o aktualizacích v jednotlivých nových HoloLens verzích.
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 1
ms.openlocfilehash: e332794baf20fbab8278a138ceeafb651c6fa2a06f3f41a66038e544f7a6e46b
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661829"
---
# <a name="hololens-1st-gen-release-notes"></a>HoloLens první (gen) verze

## <a name="hololens-1st-gen-long-term-servicing"></a>HoloLens (1. generace) Dlouhodobé údržba
HoloLens (1. generace) byla ve stavu Dlouhodobé údržba (LTS). Budoucí aktualizace se budou soustředit na opravy problémů a zabezpečení při zachování parity funkcí s Windows 10 Holographic, verze 1809 pro HoloLens (1. generace).

Pro vývojáře to znamená, HoloLens aplikace (1. generace) nebudou podporovat rozhraní OpenXR API.  Tyto náhlavní soupravy zůstávají podporované v Unity 2019 LTS s back-endem rozhraní WinRT API po celý životní cyklus Unity 2019 LTS až do poloviny roku 2022.

### <a name="windows-10-holographic-version-1809"></a>Windows 10 Holographic verze 1809

> **Platí pro:** HoloLens (1. generace)

| Funkce | Podrobnosti |
|---|---|
| **Nabídka Rychlé akce** | Když jste v aplikaci, gesto Bloom teď otevře nabídku Rychlé akce, která vám poskytne rychlý přístup k běžně používaným systémovým funkcím, aniž byste museli aplikaci opustit. <br> Informace [o nabídce Rychlé akce v bezobrazovkovém](hololens-kiosk.md) režimu najdete v tématu Nastavení HoloLens v bezobrazovkovém režimu.<br><br> |
| **Zastavení zachytávání videí z nabídky Spustit nebo Rychlé akce** | Pokud spustíte zachytávání videí z nabídky nabídka Start nebo rychlých akcí, budete moct nahrávání zastavit ze stejného místa. (Nezapomeňte, že to můžete dělat i pomocí hlasových příkazů.) |
| **Project k Miracast s povoleným přístupem** | Project adaptér Microsoftu HoloLens svůj obsah na nejbližší zařízení Surface nebo na tv nebo monitor.  V **nabídce** Start **vyberte Připojení** a pak vyberte zařízení, se kterou chcete projektovat. **Poznámka:** Můžete nasadit HoloLens použití Miracast projekce bez povolení vývojářského režimu. |
| **Nová oznámení** | Prohlížet informační zprávy a reagovat na ně HoloLens stejně jako na počítači. Reagovat na ně nebo je zavřít (nebo pokud jste v imerzivním prostředí, použijte gesto bloomu). |
| **HoloLens překryvné vrstvy**<br>(výběr souborů, klávesnice, dialogová okna atd.) | Při použití imerzivních aplikací teď uvidíte překryvy, jako je klávesnice, dialogová okna, výběr souborů atd. |
| **Překryvné uživatelské rozhraní vizuální zpětné vazby pro změnu svazku** | Když na svém počítači použijete tlačítka pro zvýšení nebo snížení HoloLens zobrazí se vizuální zobrazení úrovně svazku. |
| **Nové uživatelské rozhraní pro spouštění zařízení** | Během procesu spouštění byl přidán indikátor načítání, který poskytuje vizuální zpětnou vazbu, kterou systém načítá. Restartováním zařízení zobrazíte nový indikátor načítání – je to mezi zprávou "Hello" a Windows logem spuštění. |
| **Sdílení v okolí** | Přidání možnosti Windows možnosti Sdílení v okolí, což vám umožní sdílet zachytávání s blízkým Windows zařízením. Když pořizovat fotku nebo video na HoloLens (nebo použít tlačítko Sdílet z aplikace, jako je Microsoft Edge), vyberte nejbližší zařízení Windows s ním chcete sdílet. |
| **Sdílení z Microsoft Edge** | Tlačítko Sdílet je teď k dispozici Microsoft Edge oknech na HoloLens. V Microsoft Edge vyberte **Sdílet.** Ke sdílení HoloLens můžete použít nástroj pro výběr sdílené složky. |

#### <a name="for-international-customers"></a>Pro mezinárodní zákazníky

| Funkce | Podrobnosti |
| --- | --- |
| Lokalizovaná sestavení pro čínštinu a japonštinu | Používejte HoloLens s lokalizovaným uživatelským rozhraním pro zjednodušenou čínštinu nebo japonštinu, včetně lokalizované pinyinové klávesnice, diktování a hlasových příkazů.<br>[Zjistěte, jak nainstalovat čínský a japonské HoloLens.](hololens1-install-localized.md) |
| Syntéza řeči (TTS) | Funkce syntézy řeči teď podporuje čínštinu, japonštinu a angličtinu. |

#### <a name="for-administrators"></a>Pro správce

| Funkce |  Podrobnosti  |
|---|----|
| [Povolení zřizování po instalaci](hololens-provisioning.md) | Zřizovací balíček modulu runtime teď můžete kdykoli použít pomocí **nástroje Nastavení**. |
| Přiřazený přístup pomocí skupin Azure AD | Skupiny Azure AD teď můžete použít ke konfiguraci Windows přiřazeného přístupu k nastavení konfigurace veřejného terminálu s jednou nebo více aplikacemi. |
| Přepnutí profilu při přihlášení pin kódem z přihlašovací obrazovky | Přihlášení pomocí kódu PIN je teď dostupné pro **jiného uživatele.** |
| Přihlášení pomocí webového Poskytovatel pověření pomocí hesla | Teď můžete vybrat možnost přihlášení globe a spustit webové přihlášení pomocí svého hesla. Na přihlašovací obrazovce vyberte **Možnosti přihlášení** a výběrem možnosti Zeměkoule spusťte webové přihlášení. V případě potřeby zadejte své uživatelské jméno a pak heslo. <br>**Poznámka:** Po zobrazení výzvy při přihlašování k webu se můžete rozhodnout obejít všechny možnosti PIN kódu nebo čipové karty. |
| Čtení informací o hardwaru zařízení prostřednictvím MDM, aby zařízení bylo možné sledovat podle sériového čísla | Správci IT můžou zobrazit a sledovat HoloLens podle sériového čísla zařízení v konzole MDM. Pokyny a dostupnost funkcí najdete v dokumentaci k MDM. |
| Nastavení HoloLens zařízení pomocí MDM (přejmenování) | Správci IT můžou zobrazit a HoloLens zařízení ve své konzole MDM. Pokyny a dostupnost funkcí najdete v dokumentaci k MDM. |

### <a name="windows-10-version-1803-for-microsoft-hololens"></a>Windows 10 verze 1803 pro Microsoft HoloLens

> **Platí pro:** HoloLens (1. generace)

Windows 10 verze 1803 je první aktualizací funkcí nástroje Windows Holographic for Business od jejího vydání ve verzi Windows 10 1607. Tato aktualizace zavádí následující změny:

- Dříve jste mohli ověřit, že se na vaše zařízení HoloLens použila licence pro upgrade pro komerční sadu, a to tak, že jste ověřili, jestli je v zařízení dostupná možnost VPN. Po **Nastavení**  >  **licence** se **Windows Holographic for Business** zobrazí stav systému. [Zjistěte, jak odemknout Windows Holographic for Business funkce.](hololens1-upgrade-enterprise.md)

- Číslo sestavení operačního systému můžete zobrazit ve vlastnostech zařízení v aplikaci Průzkumník souborů a v nástroji [WDRT (Windows Device Recovery Tool).](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)
- Zřízení zařízení HoloLens je teď snazší pomocí nového průvodce **zřízením HoloLens zařízení** v nástroji Windows Configuration Designer. V průvodci můžete nakonfigurovat prostředí pro nastavení a síťová připojení, nastavit vývojářský režim a získat hromadné tokeny Azure AD. [Naučte se používat jednoduchého průvodce zřizováním pro HoloLens](hololens-provisioning.md#provisioning-package-hololens-wizard).

- Když vytvoříte místní účet ve zřizovacím balíčku, platnost hesla vyprší každých 42 dnů.

- Můžete nakonfigurovat HoloLens jako beziosk s jednou nebo [více aplikacemi.](hololens-kiosk.md) Bezobrazovový režim s více aplikacemi umožňuje nastavit HoloLens, aby se spouštěly jenom aplikace, které zadáte, a zabránit uživatelům v provádění změn.

- Protokol MTP (Media Transfer Protocol) je povolený, takže zařízení HoloLens můžete připojit k počítači přes USB a přenášet soubory mezi HoloLens a počítačem. Můžete také použít aplikaci Průzkumník souborů k přesunutí a odstranění souborů z HoloLens.

- Dříve jste po přihlášení k zařízení pomocí účtu Azure Active Directory (Azure AD)  museli k  získání přístupu k podnikovým prostředkům Nastavení přístup k pracovnímu přístupu. Teď se přihlásíte pomocí účtu Azure AD a registrace probíhá automaticky.

- Před přihlášením můžete zvolit ikonu sítě pod polem hesla a zvolit jinou síť, Wi-Fi se chcete připojit. Můžete se také připojit k síti hostů, jako je hotel, konferenční centrum nebo firma.

- Teď můžete snadno [sdílet HoloLens s více lidmi, kteří](hololens-multiple-users.md) používají účty Azure AD.

- Pokud se instalace nebo přihlášení nezdaří, zvolte novou možnost Shromáždit **informace** a získejte diagnostické protokoly pro řešení potíží.

- Jednotliví uživatelé mohou synchronizovat podnikový e-mail bez registrace zařízení do správy mobilních zařízení (MDM). Zařízení můžete používat s účtem Microsoft, stáhnout a nainstalovat aplikaci Pošta a přidat e-mailový účet přímo.

- Stav synchronizace MDM pro zařízení můžete zkontrolovat v části Nastavení Přístup k pracovním nebo  >    >  **školním**  >  **informacím**. V části **Stav synchronizace** zařízení můžete spustit synchronizaci, zobrazit oblasti spravované pomocí MDM a vytvořit a exportovat rozšířenou diagnostickou sestavu.
