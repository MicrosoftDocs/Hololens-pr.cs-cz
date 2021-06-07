---
title: Poznámky k verzi HoloLens 1. generace
description: Přečtěte si o aktualizacích v každé nové verzi HoloLens.
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
ms.openlocfilehash: 0fb6c9ed1cd8d3ecc23975052eed54512a465bfb
ms.sourcegitcommit: 35e180e09e3938c25e4cac8e99885d7e57fa4dad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2021
ms.locfileid: "111377523"
---
# <a name="hololens-1st-gen-release-notes"></a>Poznámky k verzi HoloLens 1. generace

## <a name="hololens-1st-gen-long-term-servicing"></a>HoloLens (1. generace) Dlouhodobé údržba
HoloLens (1. generace) byl ve stavu dlouhodobé údržby (LTS). Budoucí aktualizace se zaměřují na opravy problémů a zabezpečení a zároveň udržují paritu funkcí s Windows 10 Holographic, verze 1809 pro HoloLens (1. generace).

Pro vývojáře to znamená, že aplikace HoloLens (1. generace) nebudou rozhraní OPENXR API podporovat.  Tyto náhlavní soupravy zůstávají podporované v Unity 2019 LTS s back-endem rozhraní WinRT API po celý životní cyklus Unity 2019 LTS až do poloviny roku 2022.

### <a name="windows-10-holographic-version-1809"></a>Windows 10 Holographic verze 1809

> **Platí pro:** HoloLens (1. generace)

| Funkce | Podrobnosti |
|---|---|
| **Nabídka Rychlé akce** | Když jste v aplikaci, gesto Bloom teď otevře nabídku Rychlé akce, která vám poskytne rychlý přístup k běžně používaným systémovým funkcím, aniž byste museli aplikaci opustit. <br> Informace o nabídce Rychlé akce v beznastavovém režimu najdete v tématu Nastavení [HoloLens](hololens-kiosk.md) v beznastavovém režimu.<br><br> |
| **Zastavení zachytávání videí z nabídky Spustit nebo Rychlé akce** | Pokud spustíte zachytávání videa z nabídka Start nebo rychlé akce, budete moct nahrávání zastavit ze stejného místa. (Nezapomeňte, že to můžete dělat i pomocí hlasových příkazů.) |
| **Projektování na zařízení s podporou Miracastu** | Pokud používáte adaptér Microsoft Display, můžete obsah HoloLens projektovat na nejbližší zařízení Surface nebo na tv nebo monitor.  Na **obrazovce** Start **vyberte Připojit** a pak vyberte zařízení, se kterou chcete projektovat. **Poznámka:** HoloLens můžete nasadit tak, aby se projekce Miracastu používat bez povolení vývojářského režimu. |
| **Nová oznámení** | Prohlížet informační zprávy a reagovat na ně na HoloLens stejně jako na počítači. Reagovat na ně nebo je zavřít (nebo pokud jste v imerzivním prostředí, použijte gesto bloomu). |
| **Překryvy HoloLens**<br>(výběr souborů, klávesnice, dialogová okna atd.) | Při použití imerzivních aplikací teď uvidíte překryvy, jako je klávesnice, dialogová okna, výběr souborů atd. |
| **Překryvné uživatelské rozhraní vizuální zpětné vazby pro změnu svazku** | Když použijete tlačítka pro zvýšení/snížení hlasitosti na zařízení HoloLens, uvidíte vizuální zobrazení úrovně hlasitosti. |
| **Nové uživatelské rozhraní pro spouštění zařízení** | Během procesu spouštění byl přidán indikátor načítání, který poskytuje vizuální zpětnou vazbu, kterou systém načítá. Restartováním zařízení zobrazíte nový indikátor načítání – je mezi zprávou Hello a logem spuštění Windows. |
| **Sdílení v okolí** | Přidání prostředí Pro sdílení v okolí s Windows, které umožňuje sdílet zachytávání s blízkým zařízením s Windows. Když na HoloLens pořizovat fotku nebo video (nebo použijete tlačítko Sdílet z aplikace, jako je Microsoft Edge), vyberte nejbližší zařízení s Windows, se kterým ho chcete sdílet. |
| **Sdílení z Microsoft Edge** | Tlačítko Sdílet je teď k dispozici Microsoft Edge oknech na HoloLens. V Microsoft Edge vyberte **Sdílet.** Ke sdílení webového obsahu použijte nástroj pro výběr sdílené složky HoloLens. |

#### <a name="for-international-customers"></a>Pro mezinárodní zákazníky

| Funkce | Podrobnosti |
| --- | --- |
| Lokalizovaná sestavení pro čínštinu a japonštinu | Použijte HoloLens s lokalizovaným uživatelským rozhraním pro zjednodušenou čínštinu nebo japonštinu, včetně lokalizované pinyinové klávesnice, diktování a hlasových příkazů.<br>[Zjistěte, jak nainstalovat čínštinu a japonštinu holoLens.](hololens1-install-localized.md) |
| Syntéza řeči (TTS) | Funkce syntézy řeči teď podporuje čínštinu, japonštinu a angličtinu. |

#### <a name="for-administrators"></a>Pro správce

| Funkce |  Podrobnosti  |
|---|----|
| [Povolení zřizování po instalaci](hololens-provisioning.md) | Zřizovací balíček modulu runtime teď můžete kdykoli použít pomocí **nastavení**. |
| Přiřazený přístup pomocí skupin Azure AD | Skupiny Azure AD teď můžete použít ke konfiguraci přístupu přiřazeného Windows a nastavit konfiguraci veřejného terminálu s jednou nebo více aplikacemi. |
| Přepnutí profilu při přihlášení pin kódem z přihlašovací obrazovky | Přihlášení pomocí kódu PIN je teď dostupné pro **jiného uživatele.** |
| Přihlášení pomocí webového Poskytovatel pověření pomocí hesla | Teď můžete vybrat možnost přihlášení globe a spustit webové přihlášení pomocí svého hesla. Na přihlašovací obrazovce vyberte **Možnosti přihlášení** a výběrem možnosti Zeměkoule spusťte webové přihlášení. V případě potřeby zadejte své uživatelské jméno a pak heslo. <br>**Poznámka:** Po zobrazení výzvy při přihlašování k webu se můžete rozhodnout obejít všechny možnosti PIN kódu nebo čipové karty. |
| Čtení informací o hardwaru zařízení prostřednictvím MDM, aby zařízení bylo možné sledovat podle sériového čísla | Správci IT můžou v konzole MDM zobrazit a sledovat HoloLens podle sériového čísla zařízení. Pokyny a dostupnost funkcí najdete v dokumentaci k MDM. |
| Nastavení názvu zařízení HoloLens prostřednictvím MDM (přejmenování) | Správci IT můžou zobrazit a přejmenovat zařízení HoloLens ve své konzole MDM. Pokyny a dostupnost funkcí najdete v dokumentaci k MDM. |

### <a name="windows-10-version-1803-for-microsoft-hololens"></a>Windows 10 verze 1803 pro Microsoft HoloLens

> **Platí pro:** HoloLens (1. generace)

Windows 10 verze 1803 je první aktualizací funkcí nástroje Windows Holographic for Business od jejího vydání ve verzi Windows 10 1607. Tato aktualizace zavádí následující změny:

- Dříve jste mohli ověřit, že se na zařízení HoloLens použila pouze licence pro upgrade pro Komerční sadu, a to kontrolou, jestli je v zařízení dostupná možnost VPN. Systém nastavení  >  **teď** po **Windows Holographic for Business** licence k upgradu zobrazí nové nastavení. [Zjistěte, jak odemknout Windows Holographic for Business funkce.](hololens1-upgrade-enterprise.md)

- Číslo sestavení operačního systému můžete zobrazit ve vlastnostech zařízení v aplikaci Průzkumník souborů a v nástroji [WDRT (Windows Device Recovery Tool).](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)
- Zřízení zařízení HoloLens je teď snazší díky novému průvodci **zřízením zařízení HoloLens** v nástroji Windows Configuration Designer. V průvodci můžete nakonfigurovat prostředí pro nastavení a síťová připojení, nastavit vývojářský režim a získat hromadné tokeny Azure AD. [Naučte se používat jednoduchého průvodce zřizováním pro HoloLens.](hololens-provisioning.md#provisioning-package-hololens-wizard)

- Když vytvoříte místní účet ve zřizovacím balíčku, platnost hesla vyprší každých 42 dnů.

- HoloLens můžete nakonfigurovat jako veřejného terminál s jednou nebo [více aplikacemi.](hololens-kiosk.md) Režim veřejného terminálů s více aplikacemi umožňuje nastavit HoloLens tak, aby spouštěl jenom aplikace, které zadáte, a znemožňuje uživatelům provádět změny.

- Protokol MTP (Media Transfer Protocol) je povolený, takže zařízení HoloLens můžete připojit k počítači přes USB a přenášet soubory mezi HoloLens a počítačem. Můžete také použít aplikaci Průzkumník souborů k přesunutí a odstranění souborů z HoloLens.

- Když jste se dříve přihlásili k zařízení pomocí účtu Azure Active Directory (Azure AD), museli  jste v Nastavení přidat pracovní přístup, abyste získali přístup k podnikovým prostředkům.  Teď se přihlásíte pomocí účtu Azure AD a registrace probíhá automaticky.

- Před přihlášením můžete zvolit ikonu sítě pod polem hesla a zvolit jinou síť, Wi-Fi se chcete připojit. Můžete se také připojit k síti hostů, jako je hotel, konferenční centrum nebo firma.

- HoloLens teď [můžete snadno sdílet s více lidmi pomocí](hololens-multiple-users.md) účtů Azure AD.

- Pokud se instalace nebo přihlášení nezdaří, zvolte novou možnost Shromáždit **informace** a získejte diagnostické protokoly pro řešení potíží.

- Jednotliví uživatelé mohou synchronizovat podnikový e-mail bez registrace zařízení do správy mobilních zařízení (MDM). Zařízení můžete používat s účtem Microsoft, stáhnout a nainstalovat aplikaci Pošta a přidat e-mailový účet přímo.

- Stav synchronizace MDM pro zařízení můžete zkontrolovat v **nastavení** Účty  >  **Přistupují** k pracovním nebo  >  **školním**  >  **informacím.** V části **Stav synchronizace zařízení** můžete spustit synchronizaci, zobrazit oblasti spravované pomocí MDM a vytvořit a exportovat sestavu pokročilé diagnostiky.
