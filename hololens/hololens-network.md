---
title: Připojení HoloLens k síti
description: naučte se, jak nastavit a připojit se k internetu pomocí HoloLens a jak identifikovat IP adresu zařízení.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, wi-fi, bezdrátové sítě, internet, ip adresa, ip adresa
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: a230538a2bbf33481ef33c992a5b6c76107bb3829774744bc7e9a888f9102692
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663147"
---
# <a name="connect-hololens-to-a-network"></a>Připojení HoloLens k síti

k provedení většiny věcí v HoloLens musíte být připojeni k síti. HoloLens obsahuje síť s podporou standardu standardu standardu (Wi-Fi 2x2) a připojení k síti je podobná připojení Windows 10 počítače nebo mobilního zařízení k Wi-Fi síti. Tato příručka vám pomůže:

- Připojení k síti pomocí Wi-Fi nebo jenom HoloLens 2, Wi-Fi Direct nebo Ethernet over USB-C
- Zakázat a znovu povolit Wi-Fi

přečtěte si další informace o [použití HoloLens offline](hololens-offline.md).

## <a name="connecting-for-the-first-time"></a>První připojení

při prvním použití HoloLens vás provedete připojením k Wi-Fi síti. Pokud máte potíže s připojením k Wi-Fi během instalace, ujistěte se, že je vaše síť buď otevřená, chráněná heslem, nebo síť s jedním portálem. Ověřte také, že síť nevyžaduje, abyste k připojení použili certifikát. Po instalaci se můžete připojit k jiným typům Wi-Fi sítí.

na zařízeních HoloLens 2 může uživatel [použít také adaptér USB-C pro ethernetové](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) připojení přímo k Wi-Fi, který vám pomůže při nastavení zařízení. Jakmile zařízení nastaví uživatel, může ho i nadále používat, jinak může odpojit zařízení od adaptéru a [po nastavení se připojit k síti Wi-Fi](hololens-network.md#connecting-to-wi-fi-after-setup). 

## <a name="connecting-to-wi-fi-after-setup"></a>Připojení k Wi-Fi po instalaci

1. předformátujte **gesto Start** a vyberte **Nastavení**. aplikace Nastavení bude automaticky umístěna před vás.
1. Vyberte **Network & Internet**  >  **Wi-Fi**. Zkontrolujte, jestli je zapnuté Wi-Fi. Pokud síť nevidíte, přejděte v seznamu dolů.
1. vyberte síť a pak vyberte **Připojení**.
1. Pokud se zobrazí výzva k zadání hesla k síti, zadejte ho a pak vyberte **Další**.

![nastavení Wi-Fi HoloLens](./images/hololens-2-wifi-settings.jpg)

Pokud chcete ověřit, že jste připojení k síti Wi-Fi, zkontrolujte stav Wi-Fi v nabídce **Start** :

1. Otevřete nabídku **Start** .
1. Podívejte se do levého horního rohu nabídky **Start** pro stav Wi-Fi. Zobrazí se stav Wi-Fi a bude zobrazen identifikátor SSID připojené sítě.

> [!TIP]
> Pokud Wi-Fi není k dispozici, můžete [se také připojit k mobilním a 5g sítím](hololens-cellular.md).

> [!IMPORTANT]
> uživatelé nemůžou sestavovat Wi-Fi roamingu HoloLens 2 – jediným způsobem, jak **seznam Wi-Fi aktualizovat, je přepnout Wi-Fi vypnuto a zapnuto**. Tím se zabrání hodně problémům, třeba když zařízení zůstane zablokované na přístupový bod, jakmile je mimo rozsah.

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a>Připojení HoloLens na Enterprise Wi-Fi síti

profily Wi-Fi Enterprise používají k ověřování Wi-Fi připojení protokol eap (Extensible authentication Protocol). profil HoloLens Enterprise Wi-Fi můžete nakonfigurovat prostřednictvím správy mobilních zařízení (MDM) nebo zřizovacího balíčku vytvořeného pomocí [návrháře konfigurace Windows](/windows/configuration/provisioning-packages/provisioning-packages).

pokud Microsoft Intune spravované zařízení, přečtěte si pokyny pro konfiguraci v [intune](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) .

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

- WLANv1Profile schéma: [[MS-GPWL]: Wireless LAN Profile v1 Schema | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)
- EAP-TLS – schéma: [[MS-GPWL]: schéma Microsoft EAP TLS | Microsoft Docs](/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)

Pokud máte problémy s připojením k síti Wi-Fi, Projděte si naši stránku [řešení potíží](hololens2-enterprise-troubleshooting.md#) .

## <a name="configure-network-proxy"></a>Konfigurace síťového proxy serveru

tato část se zabývá síťovým proxy serverem pro aplikace HoloLens OS a Univerzální platforma Windows (UWP) pomocí Windows zásobníku HTTP. aplikace, které používají non-Windows zásobník HTTP, můžou mít vlastní konfiguraci a manipulaci s proxy serverem. 

### <a name="proxy-configurations"></a>Konfigurace proxy 

- Skript automatické konfigurace proxy serveru (PAC): [soubor PAC](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (otevře se na webu, který není Microsoft) obsahuje funkci JavaScriptu FindProxyForURL (URL, hostitel). 
- Statický proxy server: ve formě serveru: port.  
- Protokol WPAD (Web Proxy Auto-Discovery Protocol): zadejte adresu URL konfiguračního souboru proxy serveru prostřednictvím protokolu DHCP nebo DNS. 

### <a name="proxy-provisioning-methods"></a>Metody zřizování proxy 
Existují tři způsoby, jak zřídit proxy:

 

1.  **Nastavení ROZHRANÍ** 
    1. Proxy pro jednotlivé uživatele (20H2 nebo starší):
        1. otevřete nabídka Start a vyberte Nastavení.
        2. V nabídce vlevo vyberte Network & Internet a pak proxy.
        3. Přejděte dolů na ruční nastavení proxy serveru a přepínač použít proxy server na zapnuto.
        4. Zadejte IP adresu proxy server.
        5. Zadejte číslo portu.
        6. Klikněte na Uložit.
      1. Proxy Wi-Fi (21H1 nebo vyšší):
          1. otevřete nabídka Start a přejdete na stránku vlastností vaší sítě Wi-Fi.
          1. Posunout dolů na proxy
          1. Změnit na ruční instalaci
          1. Zadejte IP adresu proxy server.
          1. Zadejte číslo portu.
          1. Klikněte na použít.
        
 2. **MDM** 
     1. Intune – pomocí těchto [kroků](/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) nakonfigurujete proxy server v Intune. Budete se muset posunout k dolní části oddílu.
     1. Další řešení MDM třetí strany – použijte [zprostředkovatele CSP pro Wi-Fi](/windows/client-management/mdm/wifi-csp).

3. **PPKG** 
    1. otevřít Windows návrháře konfigurace
    1. klikněte na rozšířené zřizování, zadejte název pro nový Project a klikněte na další.
    1. vyberte Windows holografické (HoloLens 2) a klikněte na další.
    1. Importujte PPKG (volitelné) a klikněte na Dokončit.
    1. rozbalte modul Runtime Nastavení-> profily připojení – Proxy > wlan-> wlan.
    1. Zadejte identifikátor SSID vaší Wi-Fi sítě a klikněte na Přidat.
    1. V levém okně vyberte svou Wi-Fiovou síť a zadejte požadované vlastní nastavení. Povolená přizpůsobení se zobrazí tučně v levé nabídce.
    1. Klikněte na Uložit a ukončit.
    1. [Použijte](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) zřizovací balíček na HoloLens.

poskytovatelé [csp](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) jsou za mnoha úlohami správy a zásadami pro Windows 10, a to jak v Microsoft Intune, tak i v jiných poskytovatelích služeb Microsoft MDM. pomocí [nástroje Windows Configuration Designer](/windows/configuration/provisioning-packages/provisioning-install-icd) můžete také vytvořit [zřizovací balíček](/windows/configuration/provisioning-packages/provisioning-packages) a použít ho pro HoloLens 2.
nejpravděpodobnější csp, které budou aplikovány na vaše HoloLens 2:

- [Zprostředkovatel](/windows/client-management/mdm/wifi-csp)připojení k Wi-Fi: pro profil Wi-Fi proxy 

[další zprostředkovatelé csp podporované v zařízeních HoloLens](/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a>Síť VPN
Připojení VPN vám může pomáhat zajistit bezpečnější připojení a přístup k síti vaší společnosti a k Internetu. HoloLens 2 podporuje integrovaný modul plug-in vpn klienta a Univerzální platforma Windows (UWP). 

Podporované integrované protokoly sítě VPN:
- IKEv2
- L2TP
- PPTP

Pokud se certifikát používá k ověřování integrovaného klienta VPN, musí se požadovaný klientský certifikát přidat do úložiště certifikátů uživatele. pokud chcete zjistit, jestli modul plug-in VPN třetí strany podporuje HoloLens 2, přejděte do storu a vyhledejte aplikaci vpn a ověřte, jestli je HoloLens uvedená jako podporované zařízení, a na stránce požadavky na systém aplikace podporuje architekturu ARM nebo ARM64. HoloLens podporuje jenom Univerzální platforma Windows aplikace pro VPN třetích stran.

 síť VPN může spravovat MDM prostřednictvím [Nastavení/AllowVPN](/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)a nastavuje se prostřednictvím [zásad podpora vpnv2-csp](/windows/client-management/mdm/vpnv2-csp).

Přečtěte si další informace o [tom, jak nakonfigurovat síť VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) pomocí [těchto průvodců](/windows/security/identity-protection/vpn/vpn-guide).  

### <a name="vpn-via-ui"></a>VPN přes uživatelské rozhraní

Síť VPN není ve výchozím nastavení povolená, ale můžete ji povolit ručně tak, že Nastavení aplikaci a přejdete na **Síť & Internet -> VPN.** 
1. Vyberte poskytovatele sítě VPN.
1. Vytvořte název připojení. 
1. Zadejte název nebo adresu serveru.
1. Vyberte typ sítě VPN.
1. Vyberte typ přihlašovacích údajů. 
1. Volitelně přidejte uživatelské jméno a heslo.
1. Použijte nastavení sítě VPN. 

![HoloLens Nastavení sítě VPN](./images/vpn-settings-ui.jpg)

### <a name="vpn-set-via-provisioning-package"></a>Síť VPN nastavená prostřednictvím zřizovacího balíčku

> [!TIP] 
> V našem Windows Holographic verze 20H2 jsme opravili problém s konfigurací proxy serveru pro připojení VPN. Pokud chcete tento tok používat, zvažte upgrade zařízení na toto sestavení.

1. Spusťte Windows Configuration Designer.
1. Klikněte **na HoloLens zařízení a** pak vyberte cílové zařízení a **Další.**
1. Zadejte název a cestu balíčku.
1. Klikněte **na Přepnout do rozšířeného editoru.**
1. Otevřete **Nastavení modulu runtime**  ->  **PřipojeníProfily** VPN  ->    ->  **VPNNastavení**.
1. Konfigurace VPNProfileName
1. Vyberte ProfileType (Typ profilu): **Native (Nativní)** **nebo Third Party (Třetí strana).**
    1. V části Nativní profil vyberte **NativeProtocolType** a pak nakonfigurujte server, zásady směrování, typ ověřování a další nastavení.
    1. Pro profil třetí strany nakonfigurujte adresu URL serveru, název skupiny balíčků aplikací modulů plug-in VPN (jenom 3 předdefinované) a vlastní konfigurace.
1. Exportujte balíček.
1. Připojení svůj HoloLens a zkopírujte do zařízení soubor .ppkg. 
1. Na HoloLens použijte soubor VPN .ppkg tak, že otevřete **nabídka Start a** vyberete přístup k účtu Nastavení do práce nebo do školy. Přidejte nebo odeberte zřizovací balíček  ->    ->    ->   –> Vyberte balíček VPN.


### <a name="setting-up-vpn-via-intune"></a>Nastavení sítě VPN přes Intune
Pokud chcete začít, postupujte podle dokumentů Intune. Při použití těchto kroků mějte na paměti integrované protokoly VPN, které HoloLens zařízení podporují. 

[Vytvořte profily VPN pro připojení k serverům VPN v Intune.](/mem/intune/configuration/vpn-settings-configure)

[Windows 10 a Windows zařízení Holographic přidejte připojení VPN pomocí Intune.](/mem/intune/configuration/vpn-settings-windows-10)

Až to bude hotové, [nezapomeňte profil přiřadit](/mem/intune/configuration/device-profile-assign).

### <a name="vpn-via-3rd-party-mdm-solutions"></a>Síť VPN prostřednictvím řešení MDM třetích stran
Příklad připojení VPN třetí strany:
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

Příklad nativní sítě IKEv2 VPN:
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

### <a name="using-the-settings-app-on-hololens"></a>Použití Nastavení aplikace v HoloLens

1. Otevřete **nabídku** Start.
1. V **Nastavení** **Start** nebo v seznamu **Všechny** aplikace na pravé straně nabídky Start vyberte **požadovanou** aplikaci. Aplikace **Nastavení** se automaticky umístí před vás.
1. Vyberte **Network & Internet**.
1. Výběrem Wi-Fi posuvníku ho přesuňte do pozice **Vypnuto.** Tím vypnete součásti RF rádia Wi-Fi a zakážete všechny funkce Wi-Fi na HoloLens.

    > [!WARNING]
    > Pokud je Wi-Fi přepínač vypnutý, HoloLens nebudou moct automaticky načíst [mezery.](hololens-spaces.md)

1. Přepínač posuvníku **přesuňte** do polohy Zap. a zapněte přepínač Wi-Fi přepínač a obnovte Wi-Fi na Microsoft HoloLens. Vybraný přepínač Wi-Fi (**On** nebo **Off**) se zachová napříč restartováními.

## <a name="identifying-the-ip-address-of-your-hololens-on-the-wi-fi-network"></a>Identifikace IP adresy vašeho HoloLens v Wi-Fi síti

### <a name="by-using-the-settings-app"></a>Pomocí aplikace Nastavení

1. Otevřete **nabídku** Start.
1. V **Nastavení** **Start** nebo v seznamu **Všechny** aplikace na pravé straně nabídky Start vyberte **požadovanou** aplikaci. Aplikace **Nastavení** se automaticky umístí před vás.
1. Vyberte **Network & Internet**.
1. Posuňte se dolů pod seznam dostupných virtuálních Wi-Fi a vyberte **Hardwarové vlastnosti**.

    ![Vlastnosti hardwaru v Wi-Fi hardwaru](./images/wifi-hololens-hwdetails.jpg)

   IP adresa se zobrazí vedle **IPv4 adresy**.

### <a name="by-using-voice-commands"></a>Pomocí hlasových příkazů

V závislosti na sestavení zařízení můžete k zobrazení IP adresy použít předdefinované hlasové příkazy nebo Cortana ip adresu. V buildech po [roce 19041.1103](hololens-release-notes.md#windows-holographic-version-2004) vyslovte "What's my IP address?" (Jaká je moje IP adresa?) a zobrazí se. U předchozích buildů nebo HoloLens (1. generace) řekněte "Cortana, jaká je moje IP adresa?" a Cortana zobrazí a přečte vaši IP adresu.

### <a name="by-using-windows-device-portal"></a>Pomocí Windows Portál zařízení

1. Ve webovém prohlížeči na počítači otevřete portál [zařízení](/windows/mixed-reality/using-the-windows-device-portal.md#networking).
1. Přejděte do **části** Sítě.  
   V této části se zobrazí vaše IP adresa a další informace o síti. Pomocí této metody můžete zkopírovat a vložit IP adresu na vývojovém počítači.

## <a name="change-ip-address-to-static-address"></a>Změna IP adresy na statickou adresu
### <a name="by-using-settings"></a>Pomocí Nastavení
 
1. Otevřete **nabídku** Start.
1. V **Nastavení** **Start** nebo v seznamu **Všechny** aplikace na pravé straně nabídky Start vyberte **požadovanou** aplikaci. Aplikace **Nastavení** se automaticky umístí před vás.
1. Vyberte **Network & Internet**.
1. Posuňte se dolů pod seznam dostupných virtuálních Wi-Fi a vyberte **Hardwarové vlastnosti**.
1. V okně **Upravit nastavení IP** adresy změňte první pole na **Ruční**.
1. Do zbývajících polí zadejte požadovanou konfiguraci IP adresy a pak klikněte na **Uložit.**

### <a name="by-using-windows-device-portal"></a>Pomocí Windows Portál zařízení

1. Ve webovém prohlížeči na počítači otevřete portál [zařízení](/windows/mixed-reality/using-the-windows-device-portal.md#networking).
1. Přejděte do **části** Sítě.
1. Vyberte tlačítko **Konfigurace IPv4.**
1. Vyberte **Použít následující IP adresu a** zadejte požadovanou konfiguraci protokolu TCP/IP.
1. Vyberte **Použít následující adresy serveru DNS** a v případě potřeby zadejte adresy upřednostňovaného a alternativního serveru DNS.
1. Klikněte na **Uložit**. 
