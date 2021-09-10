---
title: HoloLens první (obecná) zpráva k vydání verze
description: seznamte se s aktualizacemi v každé nové verzi HoloLens.
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
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428936"
---
# <a name="hololens-1st-gen-release-notes"></a>HoloLens první (obecná) zpráva k vydání verze

## <a name="hololens-1st-gen-long-term-servicing"></a>dlouhodobá údržba HoloLens (1. generace)
HoloLens (1. generace) vstoupil stav LTS (Long Term Servicing). budoucí aktualizace se soustředí na opravy problémů a zabezpečení a zároveň zachovávají paritu funkcí Windows 10 Holographic verze 1809 pro HoloLens (1. generace).

pro vývojáře to znamená, že HoloLens (1. generace) aplikace nebudou podporovat rozhraní OpenXR API.  Tato náhlavní souprava zůstanou podporovaná v Unity 2019 LTS s back-endu rozhraní API WinRT pro úplný životní cyklus Unity 2019 LTS až Mid-2022.

### <a name="windows-10-holographic-version-1809"></a>Windows 10 Holographic verze 1809

> **platí pro:** HoloLens (1. generace)

| Funkce | Podrobnosti |
|---|---|
| **Nabídka rychlé akce** | Když jste v aplikaci, gesto Bloom nyní otevře nabídku rychlé akce, která vám poskytne rychlý přístup k často používaným systémovým funkcím, aniž by bylo nutné aplikaci opustit. <br> informace o nabídce rychlé akce v celoobrazovkovém režimu najdete v tématu [nastavení HoloLens v celoobrazovkovém režimu](hololens-kiosk.md) .<br><br> |
| **Zastavení zachytávání videa z nabídky Start nebo rychlé akce** | pokud spustíte digitalizaci videa z nabídky nabídka Start nebo rychlá akce, budete moct zastavit nahrávání ze stejného místa. (Nezapomeňte, že to můžete provést vždycky pomocí hlasových příkazů.) |
| **Project k zařízení s podporou Miracast** | pokud používáte adaptér Microsoft Display, Projectte obsah HoloLens na nejbližší plochu zařízení nebo televizi/Monitor.  v nabídce **Start** vyberte **Připojení** a pak vyberte zařízení, do kterého chcete projekt zamítnout. **Poznámka:** HoloLens můžete nasadit pro použití Miracast projekce bez povolení režimu pro vývojáře. |
| **Nová oznámení** | podívejte se na informační zprávy oznámení na HoloLens a odpovězte na ně stejně jako v počítači. Pohledu na jejich reakci nebo jejich zrušení (nebo pokud jste v moderním prostředí, použijte gesto Bloom). |
| **překrytí HoloLens**<br>(výběr souborů, klávesnice, dialogy atd.) | Po použití aplikací pro moderní aplikace se teď budou zobrazovat překryvy, jako je klávesnice, dialogová okna, výběr souborů atd. |
| **Uživatelské rozhraní pro překrytí vizuálních názorů pro změnu svazku** | když na svém HoloLens použijete tlačítka hlasitosti, zobrazí se vizuální zobrazení na úrovni svazku. |
| **Nové uživatelské rozhraní pro spuštění zařízení** | Během procesu spouštění byl přidán indikátor načítání, který poskytuje vizuální zpětnou vazbu, kterou systém načítá. restartujte zařízení, aby se zobrazil nový ukazatel načítání – je mezi zprávou hello a logem Windows boot. |
| **Okolní sdílení** | přidání Windows okolního prostředí pro sdílení, které vám umožní sdílet zachytávání s okolním Windowsm zařízením. když zachytíte fotografii nebo video na HoloLens (nebo použijte tlačítko sdílet z aplikace, jako je například Microsoft Edge), vyberte sousední Windows zařízení, se kterým chcete sdílet. |
| **Sdílet z Microsoft Edge** | tlačítko sdílet je teď k dispozici v Microsoft Edge windows v HoloLens. v Microsoft Edge vyberte **sdílet**. pomocí nástroje pro výběr sdílené složky HoloLens sdílejte webový obsah. |

#### <a name="for-international-customers"></a>Pro mezinárodní zákazníky

| Funkce | Podrobnosti |
| --- | --- |
| Lokalizovaná čínská a japonská sestavení | používejte HoloLens s lokalizovaným uživatelským rozhraním pro zjednodušenou čínštinu nebo japonštinu, včetně lokalizovaných příkazů, diktování a hlasových příkazů pchin-jin.<br>[Naučte se instalovat čínské a japonské verze HoloLens.](hololens1-install-localized.md) |
| Syntéza řeči (TTS) | Funkce pro syntézu řeči teď podporuje čínštinu, japonštinu a angličtinu. |

#### <a name="for-administrators"></a>Pro správce

| Funkce |  Podrobnosti  |
|---|----|
| [Povolit zřizování po instalaci](hololens-provisioning.md) | nyní můžete použít zřizovací balíček modulu runtime pomocí **Nastavení**. |
| Přiřazený přístup ke skupinám Azure AD | pomocí skupin Azure AD teď můžete nakonfigurovat Windows přiřazený přístup k nastavení konfigurace veřejného terminálu pro jednu nebo více aplikací. |
| Připnout přihlášení k přepínači profil z přihlašovací obrazovky | Přihlášení k PIN kódu je teď k dispozici pro **jiného uživatele**. |
| Přihlaste se pomocí poskytovatele přihlašovacích údajů webu pomocí hesla. | Teď můžete vybrat možnost přihlásit se k Internetu a spustit webové přihlašování pomocí hesla. Na přihlašovací obrazovce vyberte **Možnosti přihlášení** a vyberte možnost glóbus pro spuštění webového přihlášení. V případě potřeby zadejte své uživatelské jméno a pak heslo. <br>**Poznámka:** Po zobrazení výzvy během přihlašování k webu můžete zvolit, že se budou zobrazovat libovolné možnosti kódu PIN a SmartCard. |
| Číst informace o hardwaru zařízení prostřednictvím MDM, takže zařízení je možné sledovat podle sériového čísla | správci IT můžou v konzole MDM zobrazit a sledovat HoloLens podle sériového čísla zařízení. V dokumentaci k MDM najdete informace o dostupnosti a pokynech pro funkce. |
| nastavit HoloLens název zařízení prostřednictvím MDM (přejmenování) | správci IT můžou v konzole MDM zobrazit a přejmenovat zařízení HoloLens. V dokumentaci k MDM najdete informace o dostupnosti a pokynech pro funkce. |

### <a name="windows-10-version-1803-for-microsoft-hololens"></a>Windows 10 verze 1803 pro Microsoft HoloLens

> **platí pro:** HoloLens (1. generace)

Windows 10 verze 1803 je první aktualizace funkcí, která se Windows Holographic for Business od jejich vydání v Windows 10, verze 1607. Tato aktualizace zavádí tyto změny:

- dřív jste mohli ověřit, že se na zařízení HoloLens použila licence pro upgrade pro komerční sadu, a to tak, že zkontroluje, jestli byla v zařízení dostupná možnost VPN. nyní se **Nastavení**  >  **systém** po použití licence pro upgrade zobrazí **Windows Holographic for Business** . [naučte se, jak odemknout funkce Windows Holographic for Business](hololens1-upgrade-enterprise.md).

- číslo sestavení operačního systému můžete zobrazit ve vlastnostech zařízení v aplikaci průzkumník souborů a v [nástroji Windows pro obnovení zařízení (WDRT)](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq).
- zřízení HoloLensho zařízení je teď snazší pomocí průvodce novým **zřizováním HoloLensch zařízení** v nástroji pro návrháře konfigurace Windows. V průvodci můžete nakonfigurovat prostředí pro nastavení a připojení k síti, nastavit režim pro vývojáře a získat hromadné tokeny Azure AD. [Naučte se používat jednoduchého průvodce zřizováním pro HoloLens](hololens-provisioning.md#provisioning-package-hololens-wizard).

- Když v zřizovacím balíčku vytvoříte místní účet, heslo už nebude vypršet každých 42 dní.

- HoloLens můžete [nakonfigurovat jako veřejný terminál s jednou aplikací nebo s více aplikacemi](hololens-kiosk.md). celoobrazovkový režim s více aplikacemi umožňuje nastavit HoloLens, aby se spouštěly jenom aplikace, které zadáte, a zabráníte uživatelům v provádění změn.

- je povolený protokol MTP (Media Transfer Protocol), abyste mohli zařízení HoloLens připojit k počítači přes USB a přenášet soubory mezi HoloLens a počítačem. K přesunutí a odstranění souborů z HoloLens můžete použít taky aplikaci Průzkumník souborů.

- dříve jste po přihlášení k zařízení pomocí účtu Azure Active Directory (Azure AD) museli **přidat přístup** k prostředkům v **Nastavení** a získat tak přístup k podnikovým prostředkům. Nyní se přihlašujete pomocí účtu Azure AD a registrace proběhne automaticky.

- Než se přihlásíte, můžete vybrat ikonu sítě pod polem heslo a vybrat jinou síť Wi-Fi pro připojení. Můžete se také připojit k hostované síti, jako je například Hotel, konferenční centrum nebo podnik.

- pomocí účtů Azure AD teď můžete snadno [sdílet HoloLens s více lidmi](hololens-multiple-users.md) .

- Pokud se instalace nebo přihlášení nepovede, vyberte možnost nové **informace o shromažďování** , abyste získali diagnostické protokoly pro řešení potíží.

- Jednotliví uživatelé můžou synchronizovat své podnikové e-maily bez registrace jejich zařízení ve správě mobilních zařízení (MDM). Zařízení můžete používat s účtem Microsoft, stáhnout a nainstalovat poštovní aplikaci a přidat e-mailový účet přímo.

- můžete kontrolovat stav synchronizace MDM pro zařízení v **Nastavení**  >  **účty**  >  **přístup k pracovním nebo školním**  >  **informacím**. V části **stav synchronizace zařízení** můžete spustit synchronizaci, zobrazit oblasti spravované MDM a vytvořit a exportovat pokročilou sestavu diagnostiky.
