---
title: Komerční funkce
description: Přečtěte si o funkcích Microsoft HoloLens komerčních sad, které usnadňují firmám správu zařízení HoloLens.
author: scooley
ms.author: scooley
ms.date: 08/26/2019
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
audience: ITPro
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
keywords: HoloLens, komerční, funkce, MDM, Správa mobilních zařízení, celoobrazovkový režim
ms.openlocfilehash: 3682a2633477d68f61dba8a674846857947a3d15
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379193"
---
# <a name="commercial-features"></a>Komerční funkce

HoloLens obsahuje funkce, které podnikům usnadňují správu zařízení HoloLens.

Každé zařízení HoloLens 2 má k dispozici komerční funkce.

HoloLens (1. generace) se dodává se dvěma možnostmi licencování, vývojářskou licencí a komerční licencí. K odemknutí komerčních možností HoloLens můžete upgradovat z vývojářské licence na komerční licenci. Pokud si chcete koupit sadu Microsoft HoloLens Commercial Suite, obraťte se na místního správce účet Microsoft.

>[!VIDEO https://www.youtube.com/embed/tNd0e2CiAkE]

## <a name="key-commercial-features"></a>Klíčové komerční funkce

- **Celoobrazovkový režim.** Můžete použít HoloLens v ukázce nebo předprezentovat prostředí pomocí celoobrazovkového režimu, abyste omezili, které aplikace se můžou spouštět.

  ![V celoobrazovkovém režimu se HoloLens spustí přímo do aplikace podle vašeho výběru.](images/201608-kioskmode-400px.png)

- **Správa mobilních zařízení (MDM) pro HoloLens** Vaše IT oddělení může spravovat víc zařízení HoloLens současně pomocí řešení, jako je Microsoft Intune. Můžete spravovat nastavení, vybrat aplikace, které chcete nainstalovat, a nastavit konfigurace zabezpečení, které jsou přizpůsobené potřebám vaší organizace.

  ![Správa mobilních zařízení na HoloLens zajišťuje správu zařízení na podnikové úrovni napříč různými zařízeními.](images/201608-enterprisemanagement-400px.png)

- **Web Windows Update pro firmy.** Web Windows Update pro firmy poskytují řízené aktualizace operačního systému pro zařízení a podporu pro kanál pro dlouhodobé obsluhy.
- **Zabezpečení dat.** Šifrování dat nástroje BitLocker je povoleno na HoloLens a poskytuje stejnou úroveň ochrany zabezpečení jako jakékoli jiné zařízení se systémem Windows.
- **Přístup k práci.** Kdokoli ve vaší organizaci se může vzdáleně připojit k podnikové síti prostřednictvím virtuální privátní sítě (VPN) na HoloLens. HoloLens má také přístup k Wi-Fi sítím, které vyžadují přihlašovací údaje.
- **Microsoft Store pro firmy.** Vaše IT oddělení může také nastavovat soukromé úložiště v podniku, které obsahuje jenom aplikace vaší společnosti pro konkrétní využití HoloLens. Zajistěte zabezpečenou distribuci podnikového softwaru na vybranou skupinu uživatelů v podniku.

## <a name="feature-comparison-between-editions"></a>Porovnání funkcí mezi edicemi

|Funkce |Vývojová edice HoloLens (1. generace) |HoloLens (1. gen) komerční sada |HoloLens 2 |
|---|:---:|:---:|:---:|
|Šifrování zařízení (BitLocker) | |✔️ |✔️ |
|Virtuální privátní síť (VPN) | |✔️ |✔️ |
|[Celoobrazovkový režim](hololens-kiosk.md) | |✔️ |✔️ |
|**Správa a nasazení** | | | |
|Správa mobilního zařízení (MDM) | |✔️ |✔️ |
|Možnost blokovat zrušení registrace | |✔️ |✔️ |
|Přístup k firemním Wi-Fi na základě certifikátu | |✔️ |✔️ |
|Microsoft Store (uživatel) |Příjemce |Filtrovat pomocí MDM |Filtrovat pomocí MDM |
|[Portál obchodu pro firmy](https://docs.microsoft.com/microsoft-store/working-with-line-of-business-apps) | |✔️ |✔️ |
|**Zabezpečení a identita** | | | |
|Přihlášení pomocí účtu Azure Active Directory (Azure AD) |✔️ |✔️ |✔️ |
|Přihlášení pomocí účtu Microsoft (MSA) |✔️ |✔️ |✔️ |
|Přihlašovací údaje nové generace s odemknutím kódu PIN |✔️ |✔️ |✔️ |
|[Zabezpečené spouštění](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot) |✔️ |✔️ |✔️ |
|**Údržba a podpora** | | | |
|Automatické aktualizace systému při jejich doručení |✔️ |✔️ |✔️ |
|[web Windows Update pro firmy](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) | |✔️ |✔️ |
|Kanál pro údržbu Long-Term (LTSC) | |✔️ |✔️ |

## <a name="enabling-commercial-features"></a>Povolení komerčních funkcí

Správce IT ve vaší organizaci může nastavit komerční funkce, například Microsoft Store pro obchodní, celoobrazovkový režim a Enterprise Wi-Fi přístup. V dokumentaci k [Microsoft HoloLens](index.yml) najdete podrobné pokyny pro registraci zařízení a instalaci aplikací z Microsoft Store pro firmy.

## <a name="see-also"></a>Viz také

- [Microsoft HoloLens](index.yml)
- [Celoobrazovkový režim](hololens-kiosk.md)
- [Na zařízeních HoloLens jsou podporovaná CSP](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)
- [Microsoft Store pro obchodní a obchodní aplikace](https://blogs.technet.microsoft.com/sbucci/2016/04/13/windows-store-for-business-and-line-of-business-applications/)
- [Práce s obchodními aplikacemi](/microsoft-store/working-with-line-of-business-apps)
