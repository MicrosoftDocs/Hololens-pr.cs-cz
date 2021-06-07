---
title: Průvodce nasazením – Firemní zařízení HoloLens 2 s dynamics 365 Guides – údržba
description: Zjistěte, jak udržovat zařízení HoloLens 2 přes firemní připojenou síť pomocí průvodců Dynamics 365.
keywords: HoloLens, management, corporate connected, Dynamics 365 Guides, AAD, Azure AD, MDM, Mobile Správa zařízení
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
ms.openlocfilehash: f231e65e17ab053e34e7174e1ed7ff6e7a0a56b8
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377634"
---
# <a name="maintain---corporate-connected-guide"></a>Údržba – Průvodce propojením s podnikem

## <a name="update-hololens"></a>Aktualizace HoloLens

Společnost Microsoft navrhla Windows Update pro firmy, aby správcům IT poskytovala další možnosti správy zaměřené na služba Windows Update, jako je například možnost nasazovat aktualizace do skupin zařízení a definovat intervaly údržby pro instalaci aktualizací.

Jednou z oblíbených metod správy aktualizací je odložení funkce na 30 dnů. To správcům umožňuje aktualizovat a zobrazit nové funkce ve verzi Preview, získat z první ruky znalosti a informovat váš tým podpory o všech nových změnách.

Zjistěte, jak spravovat aktualizace [HoloLens,](https://docs.microsoft.com/hololens/hololens-updates)včetně plánovaných dnů, naplánovaného času a nastavení aktivních hodin v zařízení, aby se aktualizace řešly mimo pracovní dobu.

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>Aktualizace průvodců Dynamics 365 (a dalších aplikací pro Store)

Příručky Dynamics 365 jsou In-Box aplikace, které je možné aktualizovat prostřednictvím Microsoft Store aplikace. Pro všechny aplikace, které jsou staženy prostřednictvím Microsoft Store, je možné je aktualizovat prostřednictvím [Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) aplikace ručně.

## <a name="how-to-update-lob-apps"></a>Aktualizace obchodních aplikací

Obchodní aplikace je možné aktualizovat stejným způsobem, jakým byly přidány do Intune. Aplikace je možné v Intune aktualizovat tak, že novou aplikaci nahrajete s vyšším číslem verze do stávající konfigurace aplikace. Když se zařízení synchronizuje s Intune, bude sledovat, že existuje novější verze aplikace, a novější aplikace se stáhne a nahradí starou aplikaci.

1. Pokud chcete nahrát novější aplikaci, přejděte na portál [MEM](https://endpoint.microsoft.com/#home)  ->  **Aplikace** -> Všechny **aplikace** Vlastnosti  ->  *aplikaceOfYourApp.*  ->  
2. Vedle položky Informace o aplikaci vyberte **Upravit.**
3. Jako hodnotu &quot; Select file to update (Vybrat soubor &quot; k aktualizaci) vyberte soubor.
4. Tady pomocí místní nabídky otevřete průzkumníka souborů a nahrajte novější verzi obchodní aplikace. Podle potřeby zajistěte zahrnutí závislostí.

Další informace: [Nasazení aplikací Intune pro HoloLens](https://docs.microsoft.com/hololens/app-deploy-intune)

## <a name="development-plan"></a>Plán vývoje

Když je zařízení úspěšně zaregistrované, jste teď připraveni nasadit do zařízení více obchodních aplikací. Po dobu trvání této příručky používáme ukázkovou aplikaci, ale je pravděpodobnější, že budete chtít používat vlastní aplikace vytvořené pro potřeby vaší organizace.

Pokud už obchodní aplikaci máte, jste připraveni k nasazení [aplikace prostřednictvím MDM.](https://docs.microsoft.com/hololens/app-deploy-intune) Pokud dáváte přednost jiné metodě, přečtěte si přehled nasazení aplikace pro [HoloLens 2,](https://docs.microsoft.com/hololens/app-deploy-overview) abyste se dozvěděli další metody nasazení obchodní aplikace do zařízení.

Pokud jste ještě ještě vytvořili vlastní obchodní aplikaci nebo jste stále v procesu vytváření, přečtěte si naše dokumenty k vývoji hybridní reality, kde můžete začít s návrhem a [vytvářením prototypů](https://docs.microsoft.com/windows/mixed-reality/design/design) nebo se se seznamovat se základními koncepty a začít s vývojem hybridní [reality.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)

## <a name="support-plan"></a>Plán podpory

Plán podpory je skvělá věc, kterou je třeba mít. Je užitečné mít někoho nebo skupinu natrénované na řešení potíží s procesem registrace na zařízeních HoloLens a také obecné použití zařízení HoloLens ve vaší organizaci. Pokud chcete uživatelům umožnit rychlejší řešení problémů, doporučujeme, aby se proces eskalace zpracovával podobným způsobem jako v tomto pořadí:

1. Váš tým podpory.
2. Váš tým HoloLens Expert
3. [HoloLens Docs](https://docs.microsoft.com/hololens/)  /  [Dokumentace k řešení potíží s HoloLens](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [Kontaktovat podporu](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>Správa zařízení

Tento průvodce mluvil o nastavení Mobile Správa zařízení (MDM) a jeho použití k nastavení některých konfigurací zařízení a použití nastavení pro povolení přístupu z hlediska Wi-Fi certifikátů a proxy serveru. MDM se ale také může použít k použití omezení zařízení prostřednictvím CSP a zásad.

V mnoha případech mohou mít zařízení omezení připojení, jako je Bluetooth, VPN nebo USB, nebo dokonce vypnout přístup k fotoaparátu nebo mikrofonu. Pokud vás některý z těchto problémů zajímá, doporučujeme, abyste si přečetli naši běžnou [stránku omezení zařízení.](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

Existují i další složitější omezení zařízení, která můžete použít. Například:

- Omezení stránek, které je možné zobrazit v aplikaci Nastavení, pomocí [NastaveníStránkaVisibility,](https://docs.microsoft.com/hololens/settings-uri-list)což uživatelům umožňuje přístup jenom k nastavením, která potřebují upravit, jako je například změna Wi-Fi připojení.
- Pomocí [bezobrazovkového režimu](https://docs.microsoft.com/hololens/hololens-kiosk) omezte uživatelské rozhraní, které se zobrazí uživatelům na zařízení. Bezobrazovkové terminály můžete nastavit tak, aby se jedna aplikace nebo několik aplikací s vlastní úvodní stránkou zobrazují. Kiosky mohou také různým uživatelům prezentovat různá prostředí.
- [Řízení aplikací systému Windows (WDAC), aby](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) se určité aplikace nebo procesy zcela nespouštěl.

Pokud se chcete dozvědět víc o dalších metodách správy zařízení nebo omezeních zařízení, udělejte další krok a přečtěte si náš [Správa zařízení .](https://docs.microsoft.com/hololens/hololens-csp-policy-overview)





