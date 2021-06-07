---
title: Nejčastější dotazy k zabezpečení
description: Získejte aktuální informace o nejčastějších bezpečnostních dotazech a odpovědích týkajících se zařízení hybridní reality HoloLens.
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: pawinfie
ms.author: pawinfie
ms.date: 02/19/2020
keywords: hololens, Windows Mixed Reality, security
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
manager: bradke
ms.openlocfilehash: 371c901acbf23feecfe98e72569caeaf63e2198f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2021
ms.locfileid: "111377732"
---
# <a name="frequently-asked-hololens-1st-gen-security-questions"></a>Nejčastější dotazy k zabezpečení HoloLens (1. generace)

1. **Jakou úroveň ochrany dat nabízí HoloLens 1?**
    1. Viz [HoloLens (1. generace) Šifrování nástrojem BitLocker.](hololens1-encryption.md)
1. **Jaký typ bezdrátové sítě se používá?**
    1. 802.11ac a Bluetooth 4.1 LE
1. **Jaký typ architektury je začleněný?  Například point-to-point, mesh nebo něco jiného?**
    1. Wi-Fi lze použít v režimu infrastruktury ke komunikaci s jinými bezdrátovými přístupové body.
    1. Bluetooth je možné použít ke vzájemnému navzájem peerování mezi několika zařízeními HoloLens, pokud to aplikace zákazníků podporuje nebo s jinými zařízeními Bluetooth.
1. **Co je ID FCC?**
    1. C3K1688
1. **S jakým rozsahem četnosti a kanály zařízení pracuje a je konfigurovatelné?**
    1. Wi-Fi: Rozsah četnosti není konfigurovatelný uživatelem a závisí na zemi použití. V oblasti USA Wi-Fi kanály o frekvenci 2,4 GHz (1–11) i kanály 5 GHz (36–64, 100–165).
    1. Bluetooth: Bluetooth používá standardní rozsah 2,4 až 2,48 GHz.
1. **Může zařízení povolit nebo blokovat konkrétní frekvence?**
    1. Uživatel/zařízení to nemůže ovládat.
1. **Jaká je úroveň napájení pro přenos i příjem? Jde to upravit? Jaký je rozsah operací?**
    1. Naše standardy pro testování emisí najdete [tady.](https://fccid.io/C3K1688) Rozsah operací je vysoce závislý na přístupových bodech a prostředích , ale přibližně odpovídá jiným vysoce kvalitním telefonům, tabletem nebo počítačům.
1. **Jaký je pracovní cyklus nebo doba života normálního provozu?**
    1. 2–3 hodiny aktivního použití a až dva týdny pohotovostního režimu
    1. Doba životnosti baterie není k dispozici.
1. **Co je chování při přenosu a příjmu, když nástroj není v dosahu?**
    1. Přenos a příjem zařízení HoloLens se řídí standardním vzorem Wi-Fi/Bluetooth. Na hranici svého rozsahu si pravděpodobně všimnete, že vstup se roztápí, dokud se úplně neodpojí, ale jakmile se vrátíte do dosahu, měl by se rychle znovu připojit.
1. **Co je hustota nasazení na čtvereční stopu?**
    1. To závisí na vaší síťové infrastruktuře.
1. **Může zařízení používat infrastrukturu jako klienta?**
    1. Yes
1. **Jaký protokol se používá?**
    1. HoloLens nepoužívejte žádné proprietární protokoly.
1. **Frekvence aktualizací operačního systému – Jaká je frekvence aktualizací operačního systému pro HL?  Existuje nastavený plán?  Vymyšluje Microsoft opravy zabezpečení podle potřeby atd.**
    1. Microsoft poskytuje aktualizace operačního systému pro HoloLens úplně stejným způsobem jako pro Windows 10. Za rok obvykle existují dvě hlavní aktualizace, jedna na nulu, jedna na poklesu. Vzhledem k tomu, že HoloLens je zařízení s Windows, je koncept aktualizace stejný jako u všech ostatních zařízení s Windows. Microsoft vydává opravy zabezpečení podle potřeby a dodržuje stejný koncept jako na jakémkoli jiném zařízení s Windows.
1. **Zabezpečení operačního systému – Jaké jsou možnosti pro zabezpečení operačního systému?  Můžeme odebrat nebo vypnout nepotřebné aplikace nebo služby?**
    1. HoloLens se chová jako smartphone. Je srovnatelný s jinými moderními zařízeními s Windows. HoloLens je možné spravovat pomocí Microsoft Intune nebo jiných řešení moderních Správa zařízení, jako jsou MobileIron, Airwatch nebo Soti. V těchto systémech pro správu můžete nastavit zásady zabezpečení, které nastaví zásady zabezpečení na zařízení a zabezpečí zařízení. Pokud chcete, můžete také odstranit nepotřebné aplikace.
1. **Jak se budou spravovat a aktualizovat softwarové aplikace? Jaký ovládací prvek máme k definování toho, které aplikace se načítá a jak se aktualizují aplikace pro aplikace, které se v Microsoft Storu nachází?**
    1. HoloLens získává softwarové aplikace jenom prostřednictvím Windows Storu. Je možné nainstalovat pouze balíčky aplikací Appx, které jsou vyvinuty pro použití HoloLens. Můžete to vidět na Microsoft Store s malým logem vedle aplikace, která zobrazuje zařízení HoloLens. Všechny ovládací prvek, který máte nad s právy pro správu aplikací pro Store, platí také pro HoloLens. Můžete použít koncept oficiálního obchodu nebo obchodu pro firmy. Aplikace je možné načíst bokem (ruční proces načtení aplikace na zařízení s Windows) nebo je možné je spravovat prostřednictvím MDM, aby se aplikace v případě potřeby automaticky stáhly ze Storu.
1. **Jaká je frekvence aktualizací aplikací ve Storu pro HoloLens?**
    1. Vzhledem k tomu, že dodržujeme stejný Microsoft Store a načtou aplikace odtud, je cyklus aktualizace určen vývojářem aplikace. Všechny možnosti správy, které potřebujete k řízení mechanismu aktualizace v obchodě, platí také pro HoloLens.
1. **Existuje pro HoloLens možnost zabezpečeného spouštění?**
    1. Yes
1. **Je možné zakázat nebo odpojit podporu periferních zařízení od zařízení?**
    1. Yes
1. **Je možné řídit nebo zakázat používání portů na zařízení?**
    1. HoloLens obsahuje jenom dva porty (jeden pro kabely a jeden pro účtování nebo připojení k počítačům). Kvůli funkčnosti a důvodům obnovení není možné port zakázat.
1. **Antivirový program, detekce koncových bodů, IPS, seznam povolení řízení aplikací – Libovolná schopnost spouštět antivirový program, detekci koncových bodů, IPS, seznam povolení řízení aplikací atd.**
    1. Windows Holographic for Business (komerční sada) podporuje Windows Defender Smart Screen. Pokud by antivirová společnost vytvořila aplikaci a publikoval ji do Univerzální platforma Windows, mohla by se stáhnout na HoloLens. V současné době to pro HoloLens neudělaly žádné společnosti.
    1. Povolení aplikací je možné pomocí Microsoft Enterprise Storu, kde si můžete vybrat jenom ty konkrétní aplikace, které je možné stáhnout. Prostřednictvím MDM můžete také uzamknout, které konkrétní aplikace je možné spouštět nebo dokonce zobrazit na zařízení.
1. **Můžeme zařízení umístit do karantény od prod network, dokud ho delší dobu ne aktualizačním?  Zařízení například po určitou dobu (šest měsíců) nesedí v zásuvce a neobdrželo žádné aktualizace, opravy atd.  Když se pokusí připojit k síti, můžeme ji označit příznakem a říct, že musíte před stížností na připojení k síti aktualizovat v jiné síti.**
    1. To je něco, co může být spravováno na úrovni infrastruktury pomocí MDM nebo na serveru na úrovni serveru. Zařízení může být označeno jako nevyhovující, pokud nesplňuje zadanou verzi aktualizace.
1. **Zahrnuje Microsoft nějaké zadní vratky nebo přístup ke službám, které Microsoftu umožňují připojit se k zařízení a sdílet obrazovku nebo vzdálenou podporu libovolně?**
    1. No
1. **Při vygenerování certifikátu PKI pro důvěryhodnou komunikaci chceme, aby se certifikát vygeneroval na zařízení, abychom věděli, že je jenom na tomto zařízení, je pro toto zařízení jedinečný a že ho nelze exportovat ani použít k zosobnění zařízení. Platí to pro HoloLens? Pokud ne, může dojít k omezení rizik?**
    1. CsR pro SCEP se generuje na samotném zařízení. Intune a místní konektor SCEP pomáhají zabezpečit samotné požadavky přidáním a ověřením řetězce výzvy odeslaného klientovi.
    1. Vzhledem k tomu, že HoloLens (1. generace a 2. generace) mají modul TPM, budou tyto certifikáty uložené v modulu TPM a nedaří se je extrahovat. Navíc i v případě, že by se mohly extrahovat, nešlo ověřit řetězce výzvy na jiném zařízení, takže certifikáty nebo klíče se na různých zařízeních nepoužitelné nepoužitelné.
