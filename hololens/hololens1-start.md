---
title: Nastavení HoloLens (1. generace)
description: Zjistěte, jak poprvé nastavit HoloLens (1. generace) přes síť Wi-Fi pomocí účtu Microsoft (MSA) nebo Azure Active Directory (AAD).
ms.assetid: 0136188e-1305-43be-906e-151d70292e87
ms.prod: hololens
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.date: 8/12/2019
manager: jarrettr
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 06b7142be471d0db3f45812654288a33425abd60
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189864"
---
# <a name="set-up-your-hololens-1st-gen"></a>Nastavení HoloLens (1. generace)

Při prvním zapnutí zařízení HoloLens provedete tím, že zařízení nastavíte a přihlásíte se.  Tento článek vás provede HoloLens (1. generace) při prvním spuštění a nastavení.

V další části se dozvíte, jak pracovat s hologramy HoloLens pracovat s hologramy. Pokud chcete přeskočit k článku, podívejte se na článek Začínáme [HoloLens (1. generace).](hololens1-basic-usage.md)

## <a name="before-you-start"></a>Než začnete

Než začnete, ujistěte se, že máte k dispozici následující:

**Připojení Wi-Fi .** Abyste ji nastavili, budete HoloLens k Wi-Fi sítě. Při prvním připojení budete potřebovat otevřenou síť nebo síť chráněnou heslem, která nevyžaduje přechod na web ani používání certifikátů pro připojení. [Přečtěte si další informace o webech, HoloLens používá](hololens-offline.md).

**Účet účet Microsoft nebo pracovní účet**. K přihlášení do služby budete účet Microsoft (nebo pracovní účet, pokud vaše organizace vlastní zařízení) HoloLens. Pokud nemáte vlastní účet Microsoft, přejděte na [account.microsoft.com](https://account.microsoft.com) a nastavte si ho zdarma.

**Bezpečný a dobře rozsvícený prostor bez nebezpečí při vyjetí.** [Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).

**Volitelné příslušenství pro komfort,** které se HoloLens, které vám pomůže s co nejpohodlnějším fitem. [Další informace o fitu a komfortu.](https://support.microsoft.com/help/12632/hololens-fit-your-hololens)

> [!NOTE]
>  
> - Při prvním použití aplikace HoloLens je [Cortana](hololens-cortana.md) připravena vás navede (nebude ale moct reagovat na vaše otázky, dokud nenastavíte zařízení). Toto nastavení Cortana v nastaveních Cortana kdykoli vypnout.
> - Pokud chcete přepnout na čínštinu nebo japonštinu HoloLens, budete si muset stáhnout sestavení pro jazyk na počítači a pak ho nainstalovat na HoloLens. Další informace najdete v tématu [Instalace lokalizovaných verzí HoloLens (1. generace).](hololens1-install-localized.md)

## <a name="start-your-hololens-and-set-up-windows"></a>Spusťte Hololens a nastavte Windows

Při prvním spuštění HoloLens je vaším prvním úkolem nastavit Windows Holographic na zařízení.

1. Připojení k internetu (HoloLens vás provede výběrem Wi-Fi sítě).

1. Přihlaste se ke svému uživatelskému účtu. Vyberte **si, jestli je** můj pracovní nebo školní vlastnit **a vlastním ho.**
    - Když zvolíte **Možnost Můj pracovní nebo školní účet** vlastní , přihlásíte se pomocí účtu Azure AD. Pokud vaše organizace používá Azure AD Premium a nakonfiguroval automatickou registraci MDM, HoloLens se do MDM automaticky zaregistruje. Pokud vaše organizace tuto Azure AD Premium, automatická registrace MDM není k dispozici, takže budete muset aplikaci zaregistrovat HoloLens [správě zařízení.](hololens-enroll-mdm.md#different-ways-to-enroll) Pokud se chcete k zařízení přihlásit poprvé pomocí pracovního nebo školního účtu, postupujte takto:
        1. Zadejte informace o účtu organizace.
        1. Přijměte prohlášení o zásadách ochrany osobních údajů.
        1. Přihlaste se pomocí svých přihlašovacích údajů azure AD. To se může přesměrovat na přihlašovací stránku vaší organizace.
        1. Pokračujte v nastavování zařízení.
    - Když zvolíte **Možnost vlastnit**, přihlásíte se pomocí účet Microsoft. Po dokončení instalace můžete ručně zaregistrovat [HoloLens ve správě zařízení.](hololens-enroll-mdm.md#different-ways-to-enroll)
        1. Zadejte své účet Microsoft údaje.
        1. Zadejte svoje heslo. Pokud váš účet Microsoft vyžaduje [dvoukrokové](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)ověřování , dokončete proces ověřování.

1. Zařízení nastaví časové pásmo na základě informací, které získá z Wi-Fi sítě.

## <a name="calibration"></a>Kalibrace

Po Cortana se sám zavede, je dalším krokem nastavení tento krok. Pokud chcete HoloLens prostředí, měli byste během nastavování dokončit proces zpracování.

HoloLens (1. generace) používá vzdálenost mezi zornicemi (IPD nebo [interpupilární](https://en.wikipedia.org/wiki/Interpupillary_distance)vzdálenost) k srozumitelnosti a snadné interakci hologramů. Pokud IPD není správné, hologramy se mohou jeví jako nestabilní nebo v nesprávné vzdálenosti.

Během průběhu HoloLens vás požádá o zarovnání prstu s řadou šesti cílů na oko. HoloLens tento proces používá k nastavení správné IPD pro vaše oči. Pokud je potřeba u nového uživatele aktualizovat nebo upravit noví uživateli, může nový uživatel spustit aplikaciČísi mimo nastavení.

![Obrazovka pro zarovnání prstu s IPD ve druhém kroku.](./images/ipd-finger-alignment-300px.jpg)

*Obrazovka pro zarovnání prstu IPD ve druhém kroku*

Gratulujeme! Instalace je dokončená a můžete začít používat HoloLens.

## <a name="next-steps"></a>Další kroky

> [!div class="nextstepaction"]
> [Začínáme s HoloLens (1. generace)](hololens1-basic-usage.md)
