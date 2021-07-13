---
title: Insider preview pro Microsoft HoloLens
description: Naučte se, jak začít se sestaveními Insider, a poskytnout cennou zpětnou vazbu pro naši další velkou aktualizaci operačního systému pro HoloLens.
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 87b606e634d4035da02802ddd1a8e1a980f1f1d6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636083"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="71b53-103">Insider preview pro Microsoft HoloLens</span><span class="sxs-lookup"><span data-stu-id="71b53-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="71b53-104">Vítá vás nejnovější sestavení Insider Preview pro HoloLens!</span><span class="sxs-lookup"><span data-stu-id="71b53-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="71b53-105">Začít a poskytnout [cennou zpětnou vazbu](hololens-insider.md#start-receiving-insider-builds) pro naši další velkou aktualizaci operačního systému pro HoloLens.</span><span class="sxs-lookup"><span data-stu-id="71b53-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="71b53-106">Windows Poznámky k verzi Insider</span><span class="sxs-lookup"><span data-stu-id="71b53-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="71b53-107">S radostí můžeme začít s novými funkcemi, které Windows Insiderům.</span><span class="sxs-lookup"><span data-stu-id="71b53-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="71b53-108">Nové buildy budou uchytát se do kanálů pro vývoj a beta verze a budou dostávat nejnovější aktualizace.</span><span class="sxs-lookup"><span data-stu-id="71b53-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="71b53-109">Tuto stránku budeme dál aktualizovat, protože do našich buildů pro Windows Insider přidáme další funkce a aktualizace.</span><span class="sxs-lookup"><span data-stu-id="71b53-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="71b53-110">Připravte se na kombinaci těchto aktualizací do vaší reality.</span><span class="sxs-lookup"><span data-stu-id="71b53-110">Get excited and ready to mix these updates into your reality.</span></span>

| <span data-ttu-id="71b53-111">Funkce</span><span class="sxs-lookup"><span data-stu-id="71b53-111">Feature</span></span>                 | <span data-ttu-id="71b53-112">Popis</span><span class="sxs-lookup"><span data-stu-id="71b53-112">Description</span></span>                | <span data-ttu-id="71b53-113">Uživatel nebo scénář</span><span class="sxs-lookup"><span data-stu-id="71b53-113">User or Scenario</span></span> | <span data-ttu-id="71b53-114">Zavedené sestavení</span><span class="sxs-lookup"><span data-stu-id="71b53-114">Build introduced</span></span> |
|-------------------------|----------------------------|--------------|------------------|
| [<span data-ttu-id="71b53-115">Změny CSP pro generování HoloLens sestav</span><span class="sxs-lookup"><span data-stu-id="71b53-115">CSP changes for reporting HoloLens details</span></span>](#csp-changes-for-reporting-hololens-details) | <span data-ttu-id="71b53-116">Noví csp pro dotazování dat</span><span class="sxs-lookup"><span data-stu-id="71b53-116">New CSPs for to query data</span></span> | <span data-ttu-id="71b53-117">Správci IT</span><span class="sxs-lookup"><span data-stu-id="71b53-117">IT Admins</span></span>    | <span data-ttu-id="71b53-118">20348.1403</span><span class="sxs-lookup"><span data-stu-id="71b53-118">20348.1403</span></span>                 |
| [<span data-ttu-id="71b53-119">Zásady automatického přihlášení řízené poskytovatelem CSP</span><span class="sxs-lookup"><span data-stu-id="71b53-119">Auto login policy controlled by CSP</span></span>](#auto-login-policy-controlled-by-csp) | <span data-ttu-id="71b53-120">Slouží k automatickému přihlášení účtu.</span><span class="sxs-lookup"><span data-stu-id="71b53-120">Used to log in an account automatically</span></span> | <span data-ttu-id="71b53-121">Správci IT</span><span class="sxs-lookup"><span data-stu-id="71b53-121">IT Admins</span></span> | <span data-ttu-id="71b53-122">20348.1405</span><span class="sxs-lookup"><span data-stu-id="71b53-122">20348.1405</span></span> |
| [<span data-ttu-id="71b53-123">Podpora souborů PFX pro Správce certifikátů</span><span class="sxs-lookup"><span data-stu-id="71b53-123">PFX file support for Certificate Manager</span></span>](#pfx-file-support-for-certificate-manager) | <span data-ttu-id="71b53-124">Přidání certifikátu PFX prostřednictvím Nastavení uživatelského rozhraní</span><span class="sxs-lookup"><span data-stu-id="71b53-124">Add PFX certs via Settings UI</span></span> | <span data-ttu-id="71b53-125">Koncový uživatel</span><span class="sxs-lookup"><span data-stu-id="71b53-125">End User</span></span> | <span data-ttu-id="71b53-126">20348.1405</span><span class="sxs-lookup"><span data-stu-id="71b53-126">20348.1405</span></span> |
| [<span data-ttu-id="71b53-127">Zobrazení rozšířené diagnostické sestavy v Nastavení na HoloLens</span><span class="sxs-lookup"><span data-stu-id="71b53-127">View advanced diagnostic report in Settings on HoloLens</span></span>](#view-advanced-diagnostic-report-in-settings-on-hololens) | <span data-ttu-id="71b53-128">Zobrazení diagnostických protokolů MDM na zařízení</span><span class="sxs-lookup"><span data-stu-id="71b53-128">View MDM diagnostic logs on device</span></span> | <span data-ttu-id="71b53-129">Poradce při potížích</span><span class="sxs-lookup"><span data-stu-id="71b53-129">Troubleshooting</span></span> | <span data-ttu-id="71b53-130">20348.1405</span><span class="sxs-lookup"><span data-stu-id="71b53-130">20348.1405</span></span> |
| [<span data-ttu-id="71b53-131">Offline diagnostická oznámení</span><span class="sxs-lookup"><span data-stu-id="71b53-131">Offline Diagnostics notifications</span></span>](#offline-diagnostics-notifications) | <span data-ttu-id="71b53-132">Zpětná vazba k shromažďování protokolů</span><span class="sxs-lookup"><span data-stu-id="71b53-132">Audiovisual feedback for log collection</span></span> | <span data-ttu-id="71b53-133">Poradce při potížích</span><span class="sxs-lookup"><span data-stu-id="71b53-133">Troubleshooting</span></span> | <span data-ttu-id="71b53-134">20348.1405</span><span class="sxs-lookup"><span data-stu-id="71b53-134">20348.1405</span></span> |


### <a name="csp-changes-for-reporting-hololens-details"></a><span data-ttu-id="71b53-135">Změny CSP pro generování HoloLens sestav</span><span class="sxs-lookup"><span data-stu-id="71b53-135">CSP changes for reporting HoloLens details</span></span>

- <span data-ttu-id="71b53-136">Zavedeno v Windows Insider, 20348.1403</span><span class="sxs-lookup"><span data-stu-id="71b53-136">Introduced in Windows Insider build, 20348.1403</span></span>

<span data-ttu-id="71b53-137">Následující csP se aktualizovali o nové způsoby hlášení informací z vašich HoloLens zařízení.</span><span class="sxs-lookup"><span data-stu-id="71b53-137">The following CSPs have been updated with new ways to report information from your HoloLens devices.</span></span>

#### <a name="devdetail-csp---free-storage"></a><span data-ttu-id="71b53-138">DevDetail CSP – Bezplatná Storage</span><span class="sxs-lookup"><span data-stu-id="71b53-138">DevDetail CSP - Free Storage</span></span>

<span data-ttu-id="71b53-139">DevDetail CSP teď také hlásí volné místo v HoloLens zařízení.</span><span class="sxs-lookup"><span data-stu-id="71b53-139">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="71b53-140">Tato hodnota by se měla přibližně shodovat s hodnotou Nastavení na stránce Storage aplikace.</span><span class="sxs-lookup"><span data-stu-id="71b53-140">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="71b53-141">Následuje konkrétní uzel, který obsahuje tyto informace.</span><span class="sxs-lookup"><span data-stu-id="71b53-141">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="71b53-142">./DevDetail/Ext/Microsoft/FreeStorage (pouze operace GET)</span><span class="sxs-lookup"><span data-stu-id="71b53-142">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp---ssid-and-bssid"></a><span data-ttu-id="71b53-143">DeviceStatus CSP – SSID a BSSID</span><span class="sxs-lookup"><span data-stu-id="71b53-143">DeviceStatus CSP - SSID and BSSID</span></span>

<span data-ttu-id="71b53-144">DeviceStatus CSP nyní také hlásí SSID a BSSID Wi-Fi sítě, se HoloLens je aktivně připojen.</span><span class="sxs-lookup"><span data-stu-id="71b53-144">DeviceStatus CSP now also reports SSID and BSSID of Wi-Fi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="71b53-145">Níže jsou uvedené konkrétní uzly, které obsahují tyto informace.</span><span class="sxs-lookup"><span data-stu-id="71b53-145">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="71b53-146">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*adresa mac Wi-Fi adaptéru*/SSID</span><span class="sxs-lookup"><span data-stu-id="71b53-146">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="71b53-147">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*adresa MAC Wi-Fi adaptéru*/BSSID</span><span class="sxs-lookup"><span data-stu-id="71b53-147">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="71b53-148">Příklad objektu blob syncml (pro dodavatele MDM) pro dotazování na NetworkIdentifiers</span><span class="sxs-lookup"><span data-stu-id="71b53-148">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="auto-login-policy-controlled-by-csp"></a><span data-ttu-id="71b53-149">Zásady automatického přihlášení řízené poskytovatelem CSP</span><span class="sxs-lookup"><span data-stu-id="71b53-149">Auto login policy controlled by CSP</span></span>

<span data-ttu-id="71b53-150">Tato nová zásada AutoLogonUser určuje, jestli se uživatel automaticky přihlásí.</span><span class="sxs-lookup"><span data-stu-id="71b53-150">This new AutoLogonUser policy controls whether a user will be automatically logged on.</span></span> <span data-ttu-id="71b53-151">Někteří zákazníci chtějí nastavit zařízení, která jsou svázaná s identitou, ale nechcete žádné přihlašovací prostředí.</span><span class="sxs-lookup"><span data-stu-id="71b53-151">Some customers want to set up devices that are tied to an identity but don't want any sign-in experience.</span></span> <span data-ttu-id="71b53-152">Imagine vyzvednutí zařízení a okamžité použití vzdálené pomoci.</span><span class="sxs-lookup"><span data-stu-id="71b53-152">Imagine picking up a device and using remote assist immediately.</span></span> <span data-ttu-id="71b53-153">Nebo můžete mít výhodu, že dokážete rychle distribuovat HoloLens zařízení a umožnit koncovým uživatelům urychlit přihlášení.</span><span class="sxs-lookup"><span data-stu-id="71b53-153">Or have a benefit of being able to rapidly  distribute HoloLens devices and enable their end users to expedite login.</span></span>

<span data-ttu-id="71b53-154">Pokud je zásada nastavená na neprázdnou hodnotu, určuje e-mailovou adresu uživatele s automatickým přihlášením.</span><span class="sxs-lookup"><span data-stu-id="71b53-154">When the policy is set to a non-empty value, it specifies the email address of the auto-logon user.</span></span> <span data-ttu-id="71b53-155">Zadaný uživatel se musí alespoň jednou přihlásit k zařízení, aby se umožnilo automatické přihlášení.</span><span class="sxs-lookup"><span data-stu-id="71b53-155">The specified user must logon to the device at least once to enable auto-logon.</span></span>

<span data-ttu-id="71b53-156">OMA-URI nové hodnoty řetězce `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` zásad</span><span class="sxs-lookup"><span data-stu-id="71b53-156">The OMA-URI of new policy `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` String value</span></span>

- <span data-ttu-id="71b53-157">Uživatel se stejnou e-mailovou adresou bude mít povolené automatické přihlášení.</span><span class="sxs-lookup"><span data-stu-id="71b53-157">User with the same email address will have auto logon enabled.</span></span>

<span data-ttu-id="71b53-158">Na zařízení, kde je tato zásada nakonfigurovaná, se musí uživatel zadaný v zásadách alespoň jednou přihlásit.</span><span class="sxs-lookup"><span data-stu-id="71b53-158">On a device where this policy is configured, the user specified in the policy will need to logon at least once.</span></span> <span data-ttu-id="71b53-159">Při dalších restartováních zařízení po prvním přihlášení se zadaný uživatel automaticky přihlásí.</span><span class="sxs-lookup"><span data-stu-id="71b53-159">Subsequent reboots of the device after the first logon will have the specified user automatically logged on.</span></span> <span data-ttu-id="71b53-160">Podporuje se jenom jeden uživatel s automatickým přihlášením.</span><span class="sxs-lookup"><span data-stu-id="71b53-160">Only a single auto-logon user is supported.</span></span> <span data-ttu-id="71b53-161">Po povolení se automaticky přihlášený uživatel nebude moct odhlásit ručně.</span><span class="sxs-lookup"><span data-stu-id="71b53-161">Once enabled, the automatically logged on user will not be able to log out manually.</span></span> <span data-ttu-id="71b53-162">Pokud se chcete přihlásit jako jiný uživatel, musí být zásada nejprve zakázaná.</span><span class="sxs-lookup"><span data-stu-id="71b53-162">To logon as a different user, the policy must first be disabled.</span></span>

> [!NOTE]
> - <span data-ttu-id="71b53-163">Některé události, jako jsou například hlavní aktualizace operačního systému, mohou vyžadovat, aby se zadaný uživatel k zařízení znovu přihlásit, aby obnovoval chování automatického přihlášení.</span><span class="sxs-lookup"><span data-stu-id="71b53-163">Some events such as major OS updates may require the specified user to logon to the device again to resume auto-logon behavior.</span></span> 
> - <span data-ttu-id="71b53-164">Automatické přihlášení se podporuje jenom pro uživatele MSA a AAD.</span><span class="sxs-lookup"><span data-stu-id="71b53-164">Auto-logon is only supported for MSA and AAD users.</span></span>

### <a name="pfx-file-support-for-certificate-manager"></a><span data-ttu-id="71b53-165">Podpora souboru PFX pro Správce certifikátů</span><span class="sxs-lookup"><span data-stu-id="71b53-165">PFX file support for Certificate Manager</span></span>

<span data-ttu-id="71b53-166">Zavedeno v Windows Insider buildu 20348.1405.</span><span class="sxs-lookup"><span data-stu-id="71b53-166">Introduced in Windows Insider build 20348.1405.</span></span> <span data-ttu-id="71b53-167">Do Správce certifikátů jsme přidali podporu pro [použití](certificate-manager.md) certifikátů .pfx.</span><span class="sxs-lookup"><span data-stu-id="71b53-167">We’ve added support to the [Certificate Manager](certificate-manager.md) to now use .pfx certificates.</span></span> <span data-ttu-id="71b53-168">Když uživatelé **přecházou Nastavení** Update & Security Certificates a vyberou Install a certificate (Nainstalovat certifikát), uživatelské rozhraní teď podporuje soubor certifikátu  >    >    .pfx.</span><span class="sxs-lookup"><span data-stu-id="71b53-168">When users navigate to **Settings** > **Update & Security** > **Certificates**, and select **Install a certificate** the UI now supports .pfx certificate file.</span></span>
<span data-ttu-id="71b53-169">Uživatelé mohou importovat certifikát .pfx s privátním klíčem do uživatelského úložiště nebo do úložiště počítače.</span><span class="sxs-lookup"><span data-stu-id="71b53-169">Users can import .pfx certificate, with private key, to user store or machine store.</span></span>

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a><span data-ttu-id="71b53-170">Zobrazení rozšířené diagnostické sestavy v Nastavení na HoloLens</span><span class="sxs-lookup"><span data-stu-id="71b53-170">View advanced diagnostic report in Settings on HoloLens</span></span>

<span data-ttu-id="71b53-171">Pro spravovaná zařízení při řešení potíží je důležitým krokem potvrzení, že se používá očekávaná konfigurace zásad.</span><span class="sxs-lookup"><span data-stu-id="71b53-171">For managed devices when troubleshooting behavior, confirming that an expected policy configuration is applied is an important step.</span></span> <span data-ttu-id="71b53-172">Dříve se tato nová funkce musela po exportu diagnostických protokolů MDM shromážděných přes **přístup** k účtům Nastavení do práce nebo do školy provést mimo zařízení přes MDM nebo v blízkosti zařízení a vybrat Export protokolů správy a zobrazit se na okolním  ->    >  počítači. </span><span class="sxs-lookup"><span data-stu-id="71b53-172">Previously to this new feature, this had to be done off device via MDM or near the device after exporting MDM diagnostic logs gathered via **Settings** -> **Accounts** > **Access work or school**, and select **Export your management logs** and viewed on a nearby PC.</span></span>

<span data-ttu-id="71b53-173">Teď můžete diagnostiku MDM zobrazit na zařízení pomocí prohlížeče Edge.</span><span class="sxs-lookup"><span data-stu-id="71b53-173">Now the MDM Diagnostics can be viewed on device using the Edge browser.</span></span> <span data-ttu-id="71b53-174">Pokud chcete sestavu diagnostiky MDM snadněji zobrazit, přejděte na stránku Přístup do práce nebo do školy a vyberte **Zobrazit rozšířenou diagnostickou sestavu.**</span><span class="sxs-lookup"><span data-stu-id="71b53-174">To more easily view the MDM Diagnostic report navigate to the Access work or school page, and select **View advanced diagnostic report**.</span></span> <span data-ttu-id="71b53-175">Tím se sestava vygeneruje a otevře v novém okně Edge.</span><span class="sxs-lookup"><span data-stu-id="71b53-175">This will generate and open the report in a new Edge window.</span></span>

![Zobrazení rozšířené diagnostické sestavy v Nastavení aplikaci](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a><span data-ttu-id="71b53-177">Offline diagnostická oznámení</span><span class="sxs-lookup"><span data-stu-id="71b53-177">Offline Diagnostics notifications</span></span>

<span data-ttu-id="71b53-178">Tato aktualizace pro existující funkci s názvem [Offline diagnostika](hololens-diagnostic-logs.md#offline-diagnostics).</span><span class="sxs-lookup"><span data-stu-id="71b53-178">This an update for an existing feature called [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics).</span></span> <span data-ttu-id="71b53-179">Dříve se uživatelům nespouštěl žádný jasný indikátor, že aktivoval shromažďování diagnostických dat nebo že se dokončilo.</span><span class="sxs-lookup"><span data-stu-id="71b53-179">Previously, there was no clear indicator to users that they had triggered diagnostic collection or it had completed.</span></span>
<span data-ttu-id="71b53-180">V buildech Windows Insider jsou teď k dispozici dvě formy zpětné vazby k offline diagnostice.</span><span class="sxs-lookup"><span data-stu-id="71b53-180">Now added in Windows Insider builds, there are two forms of audiovisual feedback for Offline Diagnostics.</span></span> <span data-ttu-id="71b53-181">Prvními jsou informační zprávy, které se zobrazují při spuštění a dokončení shromažďování.</span><span class="sxs-lookup"><span data-stu-id="71b53-181">The first being toasts notifications displayed for both when collection starts and completes.</span></span> <span data-ttu-id="71b53-182">Ty se zobrazí, když je uživatel přihlášený a má vizuály.</span><span class="sxs-lookup"><span data-stu-id="71b53-182">These will be displayed when the user is logged in and has visuals.</span></span>

![Informační zprávy pro shromažďování protokolů](./images/logcollection1.jpg)

![Informační zpráva po dokončení shromažďování protokolů](./images/logcollection2.jpg)
 
<span data-ttu-id="71b53-185">Vzhledem k tomu, že uživatelé často používají offline diagnostiku jako záložní mechanismus shromažďování protokolů, když nemají přístup k displeji, nemůže se přihlásit nebo jsou stále v OOBE, bude se při shromažďování protokolů přehrávat také zvukové signály.</span><span class="sxs-lookup"><span data-stu-id="71b53-185">Because users often use Offline Diagnostics as a fallback log gathering mechanism for when they don’t have access to a display, can’t log-in or are still in OOBE there will also be an audio cue played when logs are gathered.</span></span> <span data-ttu-id="71b53-186">Tento zvuk se přehraje spolu s informační zprávou.</span><span class="sxs-lookup"><span data-stu-id="71b53-186">This sound will be played in addition to the toast notification.</span></span>

<span data-ttu-id="71b53-187">Tato nová funkce se povolí při aktualizaci zařízení a nemusí být povolená ani spravovaná.</span><span class="sxs-lookup"><span data-stu-id="71b53-187">This new feature will be enabled when your device updates, and doesn’t need to be enabled or managed.</span></span> <span data-ttu-id="71b53-188">Offline diagnostika se bude generovat i v případě, že tuto novou zpětnou vazbu nelze zobrazit ani slyšet.</span><span class="sxs-lookup"><span data-stu-id="71b53-188">In any event that this new feedback cannot be displayed or heard, Offline Diagnostics will still be generated.</span></span>

<span data-ttu-id="71b53-189">Doufáme, že s tímto novějším přidáním zpětné vazby k zákazníkům je snazší shromáždit diagnostická data a rychleji vyřešit vaše problémy.</span><span class="sxs-lookup"><span data-stu-id="71b53-189">We hope with this newer addition of audiovisual feedback it is easier to gather diagnostic data, and more quickly be able to troubleshoot your problems.</span></span>



### <a name="fixes-and-improvements"></a><span data-ttu-id="71b53-190">Opravy a vylepšení:</span><span class="sxs-lookup"><span data-stu-id="71b53-190">Fixes and improvements:</span></span>

- <span data-ttu-id="71b53-191">Byl opraven známý problém pro Portál zařízení, kdy se při stahování uzamčených souborů nic [nestahuje.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="71b53-191">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="71b53-192">Opravili [jsme známý problém s Portál zařízení s časovými limity nahrávání a stahování souborů.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span><span class="sxs-lookup"><span data-stu-id="71b53-192">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>


## <a name="start-receiving-insider-builds"></a><span data-ttu-id="71b53-193">Zahájení přijímání sestavení Insider</span><span class="sxs-lookup"><span data-stu-id="71b53-193">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="71b53-194">Pokud jste to ještě neudělali, restartujte zařízení, abyste aktualizovali stav a získejte nejnovější build.</span><span class="sxs-lookup"><span data-stu-id="71b53-194">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="71b53-195">Hlasový příkaz Restartovat zařízení funguje dobře.</span><span class="sxs-lookup"><span data-stu-id="71b53-195">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="71b53-196">Můžete také zvolit tlačítko restartování v Nastavení/Windows Insider Program.</span><span class="sxs-lookup"><span data-stu-id="71b53-196">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="71b53-197">Na back-endu jsme měli chybu, se kterou jste se mohli setkat, a tím se vrátíte na cestu.</span><span class="sxs-lookup"><span data-stu-id="71b53-197">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="71b53-198">Na zařízení HoloLens 2 přejděte na **Nastavení** Update & Security Windows Insider Program a  >    >   vyberte **Začínáme.**</span><span class="sxs-lookup"><span data-stu-id="71b53-198">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="71b53-199">Propojte účet, který jste použili k registraci, Windows Insider.</span><span class="sxs-lookup"><span data-stu-id="71b53-199">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="71b53-200">Windows insider se teď přesouvá na Kanály.</span><span class="sxs-lookup"><span data-stu-id="71b53-200">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="71b53-201">Kanál **Fast** se stane **vývojový** kanál, kanál **Slow** se stane **kanálem Beta kanál** a kanál verze **Preview** se stane **kanálem Release Preview**.</span><span class="sxs-lookup"><span data-stu-id="71b53-201">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="71b53-202">Toto mapování vypadá takhle:</span><span class="sxs-lookup"><span data-stu-id="71b53-202">Here is what that mapping looks like:</span></span>

![Windows Vysvětlení kanálů insider](images/WindowsInsiderChannels.png)

<span data-ttu-id="71b53-204">Další informace najdete v tématu [Představení kanálů Windows Insider na](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) Windows blogech.</span><span class="sxs-lookup"><span data-stu-id="71b53-204">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="71b53-205">Pak vyberte **Aktivní vývoj Windows,** zvolte, jestli chcete dostávat Dev **Channel** nebo Beta kanál **sestavení,** a zkontrolujte podmínky programu.</span><span class="sxs-lookup"><span data-stu-id="71b53-205">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="71b53-206">Dokončete **> Potvrdit a** restartovat.</span><span class="sxs-lookup"><span data-stu-id="71b53-206">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="71b53-207">Po restartování zařízení přejděte do Nastavení > **Update & Security >** Vyhledejte aktualizace a získejte nejnovější build.</span><span class="sxs-lookup"><span data-stu-id="71b53-207">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="71b53-208">Aktualizace 0x80070490 obchádky</span><span class="sxs-lookup"><span data-stu-id="71b53-208">Update error 0x80070490 work-around</span></span>

<span data-ttu-id="71b53-209">Pokud při aktualizaci na kanálu pro 0x80070490 nebo beta verzi dojde k chybě aktualizace, vyzkoušejte následující krátkodobé řešení.</span><span class="sxs-lookup"><span data-stu-id="71b53-209">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="71b53-210">Zahrnuje přesunutí kanálu insider, vyzvednutí aktualizace a pak přesunutí kanálu Insider zpět.</span><span class="sxs-lookup"><span data-stu-id="71b53-210">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>

#### <a name="stage-one---release-preview"></a><span data-ttu-id="71b53-211">Fáze 1 – Verze Preview</span><span class="sxs-lookup"><span data-stu-id="71b53-211">Stage one - Release Preview</span></span>

1.  <span data-ttu-id="71b53-212">Nastavení, & Security a Windows Insider Program vyberte Kanál Release **Preview.**</span><span class="sxs-lookup"><span data-stu-id="71b53-212">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>

2.  <span data-ttu-id="71b53-213">Nastavení, Aktualizace & Security, Windows Update, **Kontrola aktualizací**.</span><span class="sxs-lookup"><span data-stu-id="71b53-213">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="71b53-214">Po aktualizaci pokračujte fází 2.</span><span class="sxs-lookup"><span data-stu-id="71b53-214">After the update, continue on to Stage two.</span></span>

#### <a name="stage-two---dev-channel"></a><span data-ttu-id="71b53-215">Fáze 2 – Vývojový kanál</span><span class="sxs-lookup"><span data-stu-id="71b53-215">Stage two - Dev Channel</span></span>

1. <span data-ttu-id="71b53-216">Nastavení, Aktualizovat & Security, Windows Insider Program vyberte **Dev Channel**.</span><span class="sxs-lookup"><span data-stu-id="71b53-216">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>

2. <span data-ttu-id="71b53-217">Nastavení, Aktualizace & Security, Windows Update, **Kontrola aktualizací**.</span><span class="sxs-lookup"><span data-stu-id="71b53-217">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>

## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="71b53-218">Pokyny ke stažení ffu a flash</span><span class="sxs-lookup"><span data-stu-id="71b53-218">FFU download and flash directions</span></span>

<span data-ttu-id="71b53-219">Pokud chcete testovat pomocí ffu podepsaného letem, musíte nejprve letět s odemknutým zařízením před flash flash diskem ffu.</span><span class="sxs-lookup"><span data-stu-id="71b53-219">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>

1. <span data-ttu-id="71b53-220">Na počítači:</span><span class="sxs-lookup"><span data-stu-id="71b53-220">On PC:</span></span>
    1. <span data-ttu-id="71b53-221">Stáhněte si ffu do počítače z [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) .</span><span class="sxs-lookup"><span data-stu-id="71b53-221">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="71b53-222">Nainstalujte ARC (Advanced Recovery Companion) z Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .</span><span class="sxs-lookup"><span data-stu-id="71b53-222">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="71b53-223">Na HoloLens – Letové odemčení: Otevřete **Nastavení** Update & Security Windows Insider Program a pak  >    >   se zaregistrujte a restartujte zařízení.</span><span class="sxs-lookup"><span data-stu-id="71b53-223">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="71b53-224">Flash FFU – Nyní můžete flash diskem podepsaného letem FFU použít ARC.</span><span class="sxs-lookup"><span data-stu-id="71b53-224">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="71b53-225">Poskytnutí zpětné vazby a hlášení problémů</span><span class="sxs-lookup"><span data-stu-id="71b53-225">Provide feedback and report issues</span></span>

<span data-ttu-id="71b53-226">Pokud chcete [poskytnout zpětnou Centrum Feedback a nahlásit problémy,](hololens-feedback.md) použijte aplikaci HoloLens na svém počítači.</span><span class="sxs-lookup"><span data-stu-id="71b53-226">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="71b53-227">Pomocí Centrum Feedback zajistíte, že se zahrnou všechny potřebné diagnostické informace, které našim technikům pomůžou rychle ladit a vyřešit problém.</span><span class="sxs-lookup"><span data-stu-id="71b53-227">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="71b53-228">Problémy s čínštinou a japonštinou HoloLens by měly být hlášeny stejným způsobem.</span><span class="sxs-lookup"><span data-stu-id="71b53-228">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="71b53-229">Nezapomeňte přijmout výzvu s dotazem, jestli Centrum Feedback přístup ke složce  Dokumenty (po zobrazení výzvy vyberte Ano).</span><span class="sxs-lookup"><span data-stu-id="71b53-229">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <a name="note-for-developers"></a><span data-ttu-id="71b53-230">Poznámka pro vývojáře</span><span class="sxs-lookup"><span data-stu-id="71b53-230">Note for developers</span></span>

<span data-ttu-id="71b53-231">Vítá vás a doporučujeme, abyste si zkusili vyvíjet aplikace pomocí sestavení Insider HoloLens.</span><span class="sxs-lookup"><span data-stu-id="71b53-231">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="71b53-232">Pokud chcete [začít, HoloLens si prohlédněte dokumentaci pro](https://developer.microsoft.com/windows/mixed-reality/development) vývojáře.</span><span class="sxs-lookup"><span data-stu-id="71b53-232">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="71b53-233">Stejné pokyny fungují i se sestaveními insider HoloLens.</span><span class="sxs-lookup"><span data-stu-id="71b53-233">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="71b53-234">Můžete použít stejná sestavení Unity a Visual Studio, které už používáte pro HoloLens vývoj.</span><span class="sxs-lookup"><span data-stu-id="71b53-234">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="71b53-235">Zastavení přijímání sestavení Insider</span><span class="sxs-lookup"><span data-stu-id="71b53-235">Stop receiving Insider builds</span></span>

<span data-ttu-id="71b53-236">Pokud už nechcete dostávat buildy Insider služby Windows Holographic, můžete to vyjádřit výslovně, když HoloLens [](hololens-recovery.md) používá produkční build, nebo můžete obnovit zařízení pomocí doplňku Advanced Recovery Companion a obnovit zařízení na verzi Windows Holographic, která není z programu Insider.</span><span class="sxs-lookup"><span data-stu-id="71b53-236">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="71b53-237">Existuje známý problém, kdy se uživatelům, kteří po ruční přeinstalaci nové verze Preview buildu ruší registraci ve verzi Insider Preview, zobrazí modrá obrazovka.</span><span class="sxs-lookup"><span data-stu-id="71b53-237">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="71b53-238">Potom musí zařízení obnovit ručně.</span><span class="sxs-lookup"><span data-stu-id="71b53-238">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="71b53-239">Úplné podrobnosti o tom, jestli by vás to ovlivnilo nebo ne, najdete v dalších informacích o tomto [známém problému.](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)</span><span class="sxs-lookup"><span data-stu-id="71b53-239">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>

<span data-ttu-id="71b53-240">Pokud chcete ověřit, HoloLens vaše aplikace používá produkční sestavení:</span><span class="sxs-lookup"><span data-stu-id="71b53-240">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="71b53-241">Přejděte na **Nastavení > System > About** a vyhledejte číslo sestavení.</span><span class="sxs-lookup"><span data-stu-id="71b53-241">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="71b53-242">[Podívejte se na poznámky k verzi pro produkční čísla sestavení](hololens-release-notes.md).</span><span class="sxs-lookup"><span data-stu-id="71b53-242">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="71b53-243">Odhlášení sestavení Insider:</span><span class="sxs-lookup"><span data-stu-id="71b53-243">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="71b53-244">Na HoloLens produkčním sestavení přejděte na **Nastavení > Update & Security > Windows Insider Program** a vyberte Zastavit sestavení **Insider.**</span><span class="sxs-lookup"><span data-stu-id="71b53-244">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="71b53-245">Postupujte podle pokynů a odhlásit zařízení.</span><span class="sxs-lookup"><span data-stu-id="71b53-245">Follow the instructions to opt out your device.</span></span>
