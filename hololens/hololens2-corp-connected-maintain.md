---
title: průvodce nasazením – firemní připojení HoloLens 2 s průvodcem Dynamics 365 – údržba
description: přečtěte si, jak spravovat zařízení HoloLens 2 přes podnikovou propojenou síť pomocí průvodců Dynamics 365.
keywords: HoloLens, správa, připojení k podnikové síti, příručky k Dynamics 365, AAD, Azure AD, MDM, správa mobilních zařízení
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 0176e816f167499574607bc16c8fbd6bde757daf
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032299"
---
# <a name="maintain---corporate-connected-guide"></a>Údržba – Příručka propojená s podnikem

## <a name="update-hololens"></a>Aktualizovat HoloLens

společnost Microsoft navrhla web Windows Update pro firmy, aby správcům IT poskytovala další možnosti správy zaměřené na web Windows Update, jako je například možnost nasazení aktualizací do skupin zařízení a definování oken údržby pro instalaci aktualizací.

Jednou z oblíbených metod správy aktualizací je odložení funkce po dobu 30 dnů. To správcům umožňuje aktualizovat a zobrazovat náhled nových funkcí a získat tak první znalosti a informovat vaši technickou podporu o jakýchkoli nových změnách.

naučte se [spravovat HoloLens aktualizace](/hololens/hololens-updates), včetně plánovaných dnů, naplánovaných časů a nastavení aktivních hodin v zařízení, takže se aktualizuje mimo pracovní dobu.

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>Aktualizace průvodců Dynamics 365 (a dalších aplikací ze Storu)

příručky k Dynamics 365 jsou aplikace In-Box a dají se aktualizovat prostřednictvím Microsoft Store aplikace. pro všechny aplikace, které jsou stažené prostřednictvím Microsoft Store, je možné je ručně [aktualizovat přímo pomocí aplikace Microsoft Store](/hololens/holographic-store-apps#update-apps) .

## <a name="how-to-update-lob-apps"></a>Jak aktualizovat obchodní aplikace

Obchodní aplikace je možné aktualizovat stejným způsobem jako přidaným do Intune. Aplikace se dají v Intune aktualizovat tak, že se do existující konfigurace aplikace nahraje nová aplikace s vyšším číslem verze. Když se zařízení synchronizuje s Intune, bude to mít za to, že existuje novější verze aplikace a stáhne se novější aplikace a nahradí starou aplikaci.

1. Pokud chcete nahrát novější aplikaci, přejděte do části aplikace pro aplikaci [mem Portal](https://endpoint.microsoft.com/#home)  ->   – > všech   ->  *TheNameOfYourApp*  ->  **Vlastnosti aplikace.**
2. Vedle pole informace o aplikaci vyberte **Upravit.**
3. Pro hodnotu &quot; Vybrat soubor, který se má aktualizovat &quot; , vyberte soubor.
4. Odsud pomocí místní nabídky otevřete Průzkumníka souborů a nahrajte novější verzi obchodní aplikace. Zajistěte, aby v případě potřeby zahrnovaly závislosti.

Další informace: [nasazení aplikace Intune pro HoloLens](/hololens/app-deploy-intune)

## <a name="development-plan"></a>Plán vývoje

Vaše zařízení se úspěšně zaregistrovalo, teď jste připraveni nasadit do svých zařízení další obchodní aplikace. Po dobu trvání tohoto průvodce používáme ukázkovou aplikaci, ale je pravděpodobnější, že budete chtít používat vlastní aplikace vytvořené pro potřeby vaší organizace.

Pokud už máte obchodní aplikaci, budete připraveni ji [nasadit prostřednictvím MDM](/hololens/app-deploy-intune). pokud dáváte přednost jiné metodě, přečtěte si téma [přehled nasazení aplikace HoloLens 2](/hololens/app-deploy-overview) a získejte další informace o nasazení vaší obchodní aplikace do svých zařízení.

Pokud jste ještě vytvořili svoji vlastní obchodní aplikaci nebo stále probíhá vytváření, Projděte si naše dokumenty pro vývoj hybridních realit, kde můžete [začít navrhovat a vytvářet prototypy](/windows/mixed-reality/design/design) nebo se naučit základní koncepty, které [vám pomůžou začít se smíšeným vývojem realit.](/windows/mixed-reality/discover/get-started-with-mr)

## <a name="support-plan"></a>Plán podpory

Plán podpory je vynikajícím krokem. při řešení potíží s procesem registrace na zařízeních HoloLens a také při obecném použití HoloLensho zařízení v rámci vaší organizace je užitečná podpora uživatele nebo skupiny. Abychom uživatelům umožnili rychlejší řešení jejich problémů, doporučujeme, aby proces eskalace byl zpracován podobným způsobem jako v tomto pořadí:

1. Vaše oddělení podpory.
2. váš tým odborníka na HoloLens
3. [HoloLens Docs](/hololens/)  /  [HoloLens řešení potíží s dokumenty](/hololens/hololens-troubleshooting)
4. [Kontaktujte podporu](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>Správa zařízení

Tento průvodce mluvili o nastavení správy mobilních zařízení (MDM) a používá ho k nastavení některých konfigurací zařízení a nastavení, která umožňují přístup z pohledu Wi-Fi certifikátů a proxy serveru. MDM se ale taky dá použít k použití omezení zařízení prostřednictvím CSP a zásad.

v mnoha případech můžou mít zařízení omezení připojení, například Bluetooth, VPN, USB nebo vypnutí přístupu ke kameře nebo mikrofonu. Pokud vás nějaký z těchto zájmů zajímá, doporučujeme, abyste si přečetli [Nejčastější stránku omezení pro zařízení](/hololens/hololens-common-device-restrictions).

Existují další složitější omezení zařízení, která můžete použít. Například:

- omezení stránek, které se dají zobrazit v aplikaci Nastavení, pomocí [SettingsPageVisibility](/hololens/settings-uri-list), takže uživatelé budou mít přístup jenom k nastavením, které je potřeba upravit, jako je třeba změna připojení Wi-Fi.
- Používejte [celoobrazovkový režim](/hololens/hololens-kiosk) k omezení uživatelského rozhraní prezentovaného uživatelům na zařízení. Veřejné terminály můžete nastavit tak, aby zobrazovaly jednu aplikaci nebo více aplikací s vlastní úvodní stránkou. Veřejné terminály můžou také prezentovat různá prostředí různým uživatelům.
- [Windows řízení aplikací (WDAC)](/hololens/windows-defender-application-control-wdac) , aby se zajistilo, že konkrétní aplikace nebo procesy budou zcela spouštěny.

Pokud se chcete dozvědět více o dalších metodách správy zařízení nebo omezení zařízení, proveďte další krok a přečtěte si [Přehled správy zařízení](/hololens/hololens-csp-policy-overview).





