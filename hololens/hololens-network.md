---
title: Připojení HoloLens k síti
description: Naučte se, jak nastavit a připojit se k Internetu pomocí HoloLens a jak identifikovat IP adresu zařízení.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, Wi-Fi, bezdrátové sítě, Internet, IP adresa, IP adresa
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: d68c75dcb2249a67f2e07c77cb1b69997eb0ae72
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2021
ms.locfileid: "111379268"
---
# <a name="connect-hololens-to-a-network"></a>Připojení HoloLens k síti

K provedení většiny věcí v HoloLens musíte být připojeni k síti. HoloLens obsahuje síť s Wi-Fi podporou standardu standardu 802.11 a připojení k síti je podobná připojení zařízení s Windows 10 Desktop nebo Mobile k síti Wi-Fi. Tato příručka vám pomůže:

- Připojení k síti pomocí Wi-Fi nebo jenom pro HoloLens 2, Wi-Fi přímé nebo ethernetové přes USB-C
- Zakázat a znovu povolit Wi-Fi

Přečtěte si další informace o [používání HoloLens offline](hololens-offline.md).

## <a name="connecting-for-the-first-time"></a>První připojení

Při prvním použití HoloLens vás provedete připojením k síti Wi-Fi. Pokud máte potíže s připojením k Wi-Fi během instalace, ujistěte se, že je vaše síť buď otevřená, chráněná heslem, nebo síť s jedním portálem. Ověřte také, že síť nevyžaduje, abyste k připojení použili certifikát. Po instalaci se můžete připojit k jiným typům Wi-Fi sítí.

Na zařízeních s HoloLens 2 může uživatel k připojení přímo k Wi-Fi [použít také adaptér USB-C pro ethernetové](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) , který vám pomůže při nastavování zařízení. Jakmile zařízení nastaví uživatel, může ho i nadále používat, jinak může odpojit zařízení od adaptéru a [po nastavení se připojit k síti Wi-Fi](hololens-network.md#connecting-to-wi-fi-after-setup). 

## <a name="connecting-to-wi-fi-after-setup"></a>Připojení k Wi-Fi po instalaci

1. Předformátujte **gesto Start** a vyberte **Nastavení**. Aplikace nastavení se automaticky umístí před vás.
1. Vyberte **Network & Internet**  >  **Wi-Fi**. Zkontrolujte, jestli je zapnuté Wi-Fi. Pokud síť nevidíte, přejděte v seznamu dolů.
1. Vyberte síť a pak vyberte **připojit**.
1. Pokud se zobrazí výzva k zadání hesla k síti, zadejte ho a pak vyberte **Další**.

![Nastavení Wi-Fi HoloLens](./images/hololens-2-wifi-settings.jpg)

Pokud chcete ověřit, že jste připojení k síti Wi-Fi, zkontrolujte stav Wi-Fi v nabídce **Start** :

1. Otevřete nabídku **Start** .
1. Podívejte se do levého horního rohu nabídky **Start** pro stav Wi-Fi. Zobrazí se stav Wi-Fi a bude zobrazen identifikátor SSID připojené sítě.

> [!TIP]
> Pokud Wi-Fi není k dispozici, můžete [se také připojit k mobilním a 5g sítím](https://docs.microsoft.com/hololens/hololens-cellular).

> [!IMPORTANT]
> Podle návrhu uživatelé nemůžou doladit Wi-Fi chování při roamingu HoloLens 2 – **jediným způsobem, jak seznam Wi-Fi aktualizovat, je přepnutí Wi-Fi vypnuto a zapnuto**. Tím se zabrání hodně problémům, třeba když zařízení zůstane zablokované na přístupový bod, jakmile je mimo rozsah.

## <a name="troubleshooting-your-connection-to-wi-fi"></a>Řešení potíží s připojením k Wi-Fi

Pokud dochází k potížím s připojením k Wi-Fi, Projděte si téma nemůžu [se připojit k Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).

Když se na zařízení přihlašujete k podnikovému nebo organizačnímu účtu, může taky použít zásady správy mobilních zařízení (MDM), pokud je zásada nakonfigurovaná správcem IT.

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a>Připojit HoloLens k podnikové Wi-Fi síti

Podnikové Wi-Fi profily používají k ověřování Wi-Fi připojení protokol EAP (Extensible Authentication Protocol). Profil pro HoloLens Enterprise Wi-Fi můžete nakonfigurovat prostřednictvím MDM nebo zřizovacího balíčku vytvořeného nástrojem [Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages).

Pokud Microsoft Intune spravované zařízení, přečtěte si pokyny pro konfiguraci v [Intune](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) .

Chcete-li vytvořit Wi-Fi zřizovací balíček v WCD, je vyžadován předem nakonfigurovaný Wi-Fi profil .xml souboru. Tady je ukázkový profil Wi-Fi pro WPA2-Enterprise s ověřováním EAP-TLS:

``` xml
<?xml version="1.0"?> 
<WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1"> 
    <name>SampleEapTlsProfile</name> 
    <SSIDConfig> 
        <SSID> 
            <hex>53616d706c65</hex> 
            <name>Sample</name> 
        </SSID> 
        <nonBroadcast>true</nonBroadcast> 
    </SSIDConfig> 
    <connectionType>ESS</connectionType> 
    <connectionMode>auto</connectionMode> 
    <autoSwitch>false</autoSwitch> 
    <MSM> 
        <security> 
            <authEncryption> 
                <authentication>WPA2</authentication> 
                <encryption>AES</encryption> 
                <useOneX>true</useOneX> 
                <FIPSMode xmlns="http://www.microsoft.com/networking/WLAN/profile/v2">false</FIPSMode> 
            </authEncryption> 
            <PMKCacheMode>disabled</PMKCacheMode> 
            <OneX xmlns="http://www.microsoft.com/networking/OneX/v1"> 
                <authMode>machine</authMode> 
                <EAPConfig> 
                    <EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                        <EapMethod> 
                            <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type> 
                            <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId> 
                            <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType> 
                            <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId> 
                        </EapMethod> 
                        <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"> 
                            <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"> 
                                <Type>13</Type> 
                                <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"> 
                                    <CredentialsSource><CertificateStore><SimpleCertSelection>true</SimpleCertSelection> 
                                        </CertificateStore> 
                                    </CredentialsSource> 
                                    <ServerValidation> 
                                        <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation> 
                                        <ServerNames></ServerNames> 
                                        <TrustedRootCA>00 01 02 03 04 05 06 07 08 09 0a 0b 0c 0d 0e 0f 10 11 12 13</TrustedRootCA> 
                                    </ServerValidation> 
                                    <DifferentUsername>false</DifferentUsername> 
                                    <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">true</PerformServerValidation> 
                                    <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName> 
                                </EapType> 
                            </Eap> 
                        </Config> 
                    </EapHostConfig> 
                </EAPConfig> 
            </OneX> 
        </security> 
    </MSM> 
</WLANProfile> 
```


Certifikát kořenové certifikační autority serveru a klientský certifikát může být potřeba v zařízení zřídit v závislosti na typu protokolu EAP.

Další prostředky:

- WLANv1Profile schéma: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)
- EAP-TLS – schéma: [[MS-GPWL]: schéma Microsoft EAP TLS | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)

## <a name="eap-troubleshooting"></a>Řešení potíží s protokolem EAP
> [!TIP]
> Většina potíží se sítí je výsledkem jednoho z následujících 3 nastavení, které je v profilu sítě Wi-FI nesprávné. 
1. Dvojitá check Wi-Fi profil má správné nastavení:
   1. Typ protokolu EAP je správně nakonfigurovaný, běžné typy protokolu EAP: EAP-TLS (13), EAP-TTLS (21) a PEAP (25).
   1. Název SSID Wi-Fi je vpravo a odpovídá řetězci HEX.
   1. Pro EAP-TLS obsahuje TrustedRootCA hodnotu hash SHA-1 certifikátu důvěryhodné kořenové certifikační autority serveru&#39;s. V počítači se systémem Windows &quot;certutil.exe – v \_ příkazu výpis názvu souboru certifikátu \_ &quot; se zobrazí řetězec s hodnotou hash SHA-1&#39;certifikátu.

2. Shromažďovat Zachytávání síťových paketů v protokolech přístupového bodu nebo řadiči serveru AAA, kde zjistíte, kde se relace protokolu EAP nezdařila.
   1. Pokud není očekávána Identita protokolu EAP poskytovaná pomocí HoloLens, ověřte, zda byla identita správně zajištěna prostřednictvím profilu Wi-Fi nebo klientského certifikátu.
   1. Pokud server odmítne klientský certifikát HoloLens, ověřte, jestli je na zařízení požadovaný klientský certifikát zřízený.
   1. Pokud HoloLens odmítne certifikát serveru, ověřte, jestli je certifikát kořenové certifikační autority serveru zřízený na HoloLens.
1. Pokud se profil Enterprise zřídí prostřednictvím balíčku pro Wi-Fi zřizování, zvažte použití zřizovacího balíčku na počítači s Windows 10. Pokud se to nepovede i na počítači s Windows 10, postupujte podle [Průvodce odstraňováním potíží s ověřováním klienta ve Windows 802.1 x](https://docs.microsoft.com/windows/client-management/advanced-troubleshooting-802-authentication).
1. Nastavte svou telemetrii na úplnou nebo volitelnou (v závislosti na vašem buildu) a pošlete nám svůj názor prostřednictvím [centra zpětné vazby](https://docs.microsoft.com/hololens/hololens-feedback).

### <a name="additional-resources"></a>Další prostředky:
- [Export nastavení Wi-Fi ze zařízení s Windows](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-import-windows-8-1#export-wi-fi-settings-from-a-windows-device)

## <a name="configure-network-proxy"></a>Konfigurace síťového proxy serveru

Tato část se zabývá síťovým proxy pro aplikace HoloLens a Univerzální platforma Windows (UWP) pomocí sady Windows HTTP Stack. Aplikace, které používají jiný zásobník HTTP než Windows, můžou mít svou vlastní konfiguraci a manipulaci s proxy serverem. 

### <a name="proxy-configurations"></a>Konfigurace proxy 

- Skript automatické konfigurace proxy serveru (PAC): [soubor PAC](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (otevře se na webu, který není Microsoft) obsahuje funkci JavaScriptu FindProxyForURL (URL, hostitel). 
- Statický proxy server: ve formě serveru: port.  
- Protokol WPAD (Web Proxy Auto-Discovery Protocol): zadejte adresu URL konfiguračního souboru proxy serveru prostřednictvím protokolu DHCP nebo DNS. 

### <a name="proxy-provisioning-methods"></a>Metody zřizování proxy 
Existují tři způsoby, jak zřídit proxy:

 

1.  **Uživatelské rozhraní nastavení:** 
    1. Proxy pro jednotlivé uživatele (20H2 nebo starší):
        1. Otevřete nabídku Start a vyberte nastavení.
        2. V nabídce vlevo vyberte Network & Internet a pak proxy.
        3. Přejděte dolů na ruční nastavení proxy serveru a přepínač použít proxy server na zapnuto.
        4. Zadejte IP adresu proxy server.
        5. Zadejte číslo portu.
        6. Klikněte na Uložit.
      1. Proxy Wi-Fi (21H1 nebo vyšší):
          1. Otevřete nabídku Start a přejděte na stránku vlastností vaší sítě Wi-Fi.
          1. Posunout dolů na proxy
          1. Změnit na ruční instalaci
          1. Zadejte IP adresu proxy server.
          1. Zadejte číslo portu.
          1. Klikněte na použít.
        
 2. **MDM** 
     1. Intune – pomocí těchto [kroků](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) nakonfigurujete proxy server v Intune. Budete se muset posunout k dolní části oddílu.
     1. Další řešení MDM třetí strany – použijte [zprostředkovatele CSP pro Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp).

3. **PPKG** 
    1. Otevřít Windows Configuration Designer
    1. Klikněte na rozšířené zřizování, zadejte název nového projektu a klikněte na další.
    1. Vyberte Windows holografické (HoloLens 2) a klikněte na další.
    1. Importujte PPKG (volitelné) a klikněte na Dokončit.
    1. Rozbalte nastavení modulu runtime-> profily připojení – proxy server WLAN > > WLAN.
    1. Zadejte identifikátor SSID vaší Wi-Fi sítě a klikněte na Přidat.
    1. V levém okně vyberte svou Wi-Fiovou síť a zadejte požadované vlastní nastavení. Povolená přizpůsobení se zobrazí tučně v levé nabídce.
    1. Klikněte na Uložit a ukončit.
    1. [Použijte](https://docs.microsoft.com/hololens/hololens-provisioning#applyremove-a-provisioning-package-to-hololens-after-setup) zřizovací balíček pro HoloLens.

Poskytovatelé [CSP](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) jsou za mnoha úlohami správy a zásadami pro Windows 10, a to jak v Microsoft Intune, tak i v jiných poskytovatelích služeb Microsoft MDM. Pomocí [nástroje Windows Configuration Designer](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) můžete také vytvořit [zřizovací balíček](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) a použít ho pro HoloLens 2.
Nejpravděpodobnějším CSP, které budou aplikovány na HoloLens 2, jsou:

- [Zprostředkovatel](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp)připojení k Wi-Fi: pro profil Wi-Fi proxy 

[Další CSP podporované v zařízeních HoloLens](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a>Síť VPN
Připojení VPN vám může pomáhat zajistit bezpečnější připojení a přístup k síti vaší společnosti a k Internetu. HoloLens 2 podporuje integrovaný modul plug-in VPN klienta a Univerzální platforma Windows (UWP). 

Podporované integrované protokoly sítě VPN:
- IKEv2
- L2TP
- PPTP

Pokud se certifikát používá k ověřování integrovaného klienta VPN, musí se požadovaný klientský certifikát přidat do úložiště certifikátů uživatele. Pokud chcete zjistit, jestli modul plug-in VPN třetí strany podporuje HoloLens 2, přejděte do Storu a Najděte aplikaci VPN a ověřte, jestli je na stránce požadavky na systém uvedená aplikace, která podporuje architekturu ARM nebo ARM64. HoloLens podporuje jenom Univerzální platforma Windows aplikace pro VPN třetích stran.

 SÍŤ VPN se dá spravovat přes MDM prostřednictvím [Nastavení/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)a nastavuje se prostřednictvím  [zásad podpora vpnv2-CSP](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).

Přečtěte si další informace o [tom, jak nakonfigurovat síť VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) pomocí [těchto průvodců](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).  

### <a name="vpn-via-ui"></a>VPN prostřednictvím uživatelského rozhraní

SÍŤ VPN není ve výchozím nastavení povolená, můžete ji ale povolit ručně otevřením **Nastavení** aplikace a přechodem na  **síť & Internet-> VPN**.
1. Vyberte poskytovatele sítě VPN.
1. Vytvořte název připojení. 
1. Zadejte název nebo adresu svého serveru.
1. Vyberte typ sítě VPN.
1. Vyberte typ přihlašovacích údajů. 
1. Volitelně můžete přidat uživatelské jméno a heslo.
1. Použijte nastavení sítě VPN. 

![Nastavení sítě VPN HoloLens](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a>Nastavení sítě VPN prostřednictvím zřizovacího balíčku

> [!TIP] 
> Ve Windows holografické verzi 20H2 jsme vyřešili problém s konfigurací proxy serveru pro připojení k síti VPN. Pokud máte v úmyslu tento tok používat, zvažte možnost upgradovat zařízení na toto sestavení.

1. Spusťte Windows Configuration Designer.
1. Klikněte na **zřídit zařízení HoloLens** a pak vyberte cílové zařízení a **Další**.
1. Zadejte název a cestu balíčku.
1. Klikněte na **Přepnout do rozšířeného editoru**.
1. Otevřete **nastavení modulu runtime**  ->  **ConnectivityProfiles**  ->  **VPN**  ->  **VPNSettings**.
1. Konfigurace VPNProfileName
1. Vyberte typ souboru: **nativní** nebo **třetí strana**.
    1. V případě nativního profilu vyberte **NativeProtocolType** a pak nakonfigurujte server, zásady směrování, typ ověřování a další nastavení.
    1. Pro profil třetí strany nakonfigurujte adresu URL serveru, modul plug-in aplikace VPN název sady balíčků (jenom 3 předdefinované) a vlastní konfigurace.
1. Exportujte balíček.
1. Připojte HoloLens a zkopírujte soubor. ppkg do zařízení. 
1. V prostředí HoloLens použijte VPN. ppkg tak, že otevřete nabídku Start a vyberete **Nastavení**  ->    ->  **přístup k účtu nebo školu**  ->  **přidáte nebo odeberete zřizovací balíček** – > vybrat balíček VPN.


### <a name="setting-up-vpn-via-intune"></a>Nastavení sítě VPN přes Intune
Stačí postupovat podle dokumentů Intune a začít. Pokud budete postupovat podle těchto kroků, pamatujte na integrované protokoly sítě VPN, které podporují zařízení HoloLens. 

[Vytvořte profily sítě VPN pro připojení k SERVERŮM VPN v Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-configure).

[Nastavení zařízení s Windows 10 a Windows holografické pro přidání připojení k síti VPN pomocí Intune](https://docs.microsoft.com/mem/intune/configuration/vpn-settings-windows-10)

Po dokončení prosím nezapomeňte [profil přiřadit](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).

### <a name="vpn-via-3rd-party-mdm-solutions"></a>VPN prostřednictvím řešení MDM jiného výrobce
Příklad připojení k síti VPN třetí strany:
```xml
<!-- Configure VPN Server Name or Address (PhoneNumber=) [Comma Separated]-->
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/ServerUrlList</LocURI>
          </Target>
          <Data>selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <!-- Configure VPN Plugin AppX Package ID (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/PluginPackageFamilyName</LocURI>
          </Target>
          <Data>TestVpnPluginApp-SL_8wekyb3d8bbwe</Data>
        </Item>
      </Add>

      <!-- Configure Microsoft's Custom XML (ThirdPartyProfileInfo=) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/PluginProfile/CustomConfiguration</LocURI>
          </Target>          <Data><pluginschema><ipAddress>auto</ipAddress><port>443</port><networksettings><routes><includev4><route><address>172.10.10.0</address><prefix>24</prefix></route></includev4></routes><namespaces><namespace><space>.vpnbackend.com</space><dnsservers><server>172.10.10.11</server></dnsservers></namespace></namespaces></networksettings></pluginschema></Data>
        </Item>
      </Add>
```

Příklad nativní IKEv2 VPN:
```xml
      <Add>
        <CmdID>10001</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Servers</LocURI>
          </Target>
          <Data>Selfhost.corp.contoso.com</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10002</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/RoutingPolicyType</LocURI>
          </Target>
          <Data>ForceTunnel</Data>
        </Item>
      </Add>

      <!-- Configure VPN Protocol Type (L2tp, Pptp, Ikev2) -->
      <Add>
        <CmdID>10003</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/NativeProtocolType</LocURI>
          </Target>
          <Data>Ikev2</Data>
        </Item>
      </Add>

      <!-- Configure VPN User Method (Mschapv2, Eap) -->
      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/UserMethod</LocURI>
          </Target>
          <Data>Eap</Data>
        </Item>
      </Add>

      <Add>
        <CmdID>10004</CmdID>
        <Item>
          <Target>
            <LocURI>./Vendor/MSFT/VPNv2/VPNProfileName/NativeProfile/Authentication/Eap/Configuration</LocURI>
          </Target>
          <Data>EAP_configuration_xml_content</Data>
        </Item>
      </Add>
```
## <a name="disabling-wi-fi-on-hololens-1st-gen"></a>Zakázání Wi-Fi na HoloLens (1. generace)

### <a name="using-the-settings-app-on-hololens"></a>Použití aplikace nastavení na HoloLens

1. Otevřete nabídku **Start** .
1. V seznamu **starts** ( **všechny aplikace** ) na pravé straně nabídky **Start** vyberte aplikace **Nastavení** . Aplikace **Nastavení** se automaticky umístí před vás.
1. Vyberte **Network & Internet**.
1. Vyberte přepínač posuvníku Wi-Fi, který chcete přesunout do **vypnuté** pozice. Tato akce vypne součásti RF Wi-Fi přepínači a zakáže všechny Wi-Fi funkce na HoloLens.

    > [!WARNING]
    > Pokud je přepínač Wi-Fi zakázán, HoloLens nebude moci automaticky načíst vaše [mezery](hololens-spaces.md).

1. Přesunutím posuvníku **na pozici zapněte funkci** Wi-Fi Radio and restore Wi-Fi on Microsoft HoloLens. Vybraný stav přepínačů Wi-Fi (**zapnuto** nebo **vypnuto**) bude v průběhu restartování zachován.

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a>Určení IP adresy HoloLens v Wi-Fi síti

### <a name="by-using-the-settings-app"></a>Pomocí aplikace nastavení

1. Otevřete nabídku **Start** .
1. V seznamu **starts** ( **všechny aplikace** ) na pravé straně nabídky **Start** vyberte aplikace **Nastavení** . Aplikace **Nastavení** se automaticky umístí před vás.
1. Vyberte **Network & Internet**.
1. Posuňte se dolů k seznamu dostupných Wi-Fi sítí a vyberte **vlastnosti hardwaru**.

    ![Vlastnosti hardwaru v nastaveních Wi-Fi](./images/wifi-hololens-hwdetails.jpg)

   IP adresa se zobrazí vedle pole **adresa IPv4**.

### <a name="by-using-voice-commands"></a>Pomocí hlasových příkazů

V závislosti na sestaveních vašich zařízení můžete pomocí integrovaných hlasových příkazů nebo Cortany zobrazit vaši IP adresu. Na buildy po [19041,1103](hololens-release-notes.md#windows-holographic-version-2004) mluvit "Co je moje IP adresa?" a zobrazí se. Pro dřívější buildy nebo HoloLens (1. generace) říká "Hey Cortana", kde je moje IP adresa? a Cortana zobrazí a přečte vaši IP adresu.

### <a name="by-using-windows-device-portal"></a>Pomocí portálu zařízení Windows

1. Ve webovém prohlížeči na počítači otevřete [portál zařízení](/windows/mixed-reality/using-the-windows-device-portal.md#networking).
1. Přejděte do části **sítě** .  
   V této části se zobrazuje vaše IP adresa a další informace o síti. Pomocí této metody můžete zkopírovat a vložit IP adresu na svém vývojovém počítači.

## <a name="change-ip-address-to-static-address"></a>Změnit IP adresu na statickou adresu
### <a name="by-using-settings"></a>Pomocí nastavení
 
1. Otevřete nabídku **Start** .
1. V seznamu **starts** ( **všechny aplikace** ) na pravé straně nabídky **Start** vyberte aplikace **Nastavení** . Aplikace **Nastavení** se automaticky umístí před vás.
1. Vyberte **Network & Internet**.
1. Posuňte se dolů k seznamu dostupných Wi-Fi sítí a vyberte **vlastnosti hardwaru**.
1. V okně **Upravit nastavení protokolu IP** změňte první pole na **Ruční**.
1. Do zbývajících polí zadejte požadovanou konfiguraci protokolu IP a pak klikněte na **Uložit**.

### <a name="by-using-windows-device-portal"></a>Pomocí portálu zařízení Windows

1. Ve webovém prohlížeči na počítači otevřete [portál zařízení](/windows/mixed-reality/using-the-windows-device-portal.md#networking).
1. Přejděte do části **sítě** .
1. Vyberte tlačítko **Konfigurace protokolu IPv4** .
1. Vyberte **použít následující IP adresu** a zadejte požadovanou konfiguraci protokolu TCP/IP.
1. Vyberte **použít následující adresy serverů DNS** a v případě potřeby zadejte upřednostňovanou a alternativní adresu serveru DNS.
1. Klikněte na **Uložit**. 