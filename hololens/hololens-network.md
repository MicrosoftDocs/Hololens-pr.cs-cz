---
title: Připojení HoloLens k síti
description: Zjistěte, jak nastavit a připojit se k internetu pomocí HoloLens a jak identifikovat IP adresu zařízení.
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, wifi, wireless, internet, ip, IP adresa
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: 8564fb0483226a16722ada345de325577cda77d6
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923597"
---
# <a name="connect-hololens-to-a-network"></a>Připojení HoloLens k síti

Pokud chcete v HoloLens dělat většinu věcí, musíte být připojení k síti. HoloLens obsahuje přepínač 2x2 Wi-Fi s podporou 802.11ac a jeho připojení k síti je podobné jako připojení zařízení Windows 10 Desktop nebo Mobile k síti Wi-Fi. Tato příručka vám pomůže:

- Připojte se k síti pomocí Wi-Fi nebo jenom pro HoloLens 2, Wi-Fi Direct nebo Ethernet přes USB-C.
- Zakázání a opětovné povolení Wi-Fi

Přečtěte si další [informace o použití HoloLens offline.](hololens-offline.md)

## <a name="connecting-for-the-first-time"></a>První připojení

Při prvním použití HoloLens vás provede připojením k Wi-Fi síti. Pokud máte potíže s připojením Wi-Fi během instalace, ujistěte se, že je vaše síť otevřená síť chráněná heslem nebo místní síť portálu. Ověřte také, že síť nevyžaduje připojení pomocí certifikátu. Po instalaci se můžete připojit k jiným typům Wi-Fi sítí.

Na zařízeních HoloLens 2 může uživatel také pomocí adaptéru [USB-C na Ethernet](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) připojit se přímo k Wi-Fi, který vám pomůže s nastavením zařízení. Po nastavení zařízení může uživatel adaptér dál používat nebo ho může odpojit od adaptéru a připojit se k [wi-fi po nastavení](hololens-network.md#connecting-to-wi-fi-after-setup). 

## <a name="connecting-to-wi-fi-after-setup"></a>Připojení k Wi-Fi po nastavení

1. Předem zformulovat **gesto Spustit a** vyberte **Nastavení**. Aplikace Nastavení se automaticky umístí před vás.
1. Vyberte **Network & Internet**  >  **Wi-Fi.** Zkontrolujte, jestli je zapnuté Wi-Fi. Pokud síť nevidíte, posuňte se v seznamu dolů.
1. Vyberte síť a pak vyberte **Připojit.**
1. Pokud se zobrazí výzva k zadání hesla k síti, zadejte ho a pak vyberte **Další.**

![Nastavení Wi-Fi HoloLens](./images/hololens-2-wifi-settings.jpg)

Pokud chcete ověřit, že jste připojení Wi-Fi síti, zkontrolujte stav Wi-Fi v **nabídce Start:**

1. Otevřete **nabídku** Start.
1. V levém horním rohu nabídky **Start vyhledejte** Wi-Fi stavu. Zobrazí se stav Wi-Fi a SSID připojené sítě.

> [!TIP]
> Pokud Wi-Fi dostupná, můžete se také připojit k mobilním sítím a [sítím 5G.](hololens-cellular.md)

> [!IMPORTANT]
> Uživatelé nemohou chování holoLensu 2 Wi-Fi doladit– jediným způsobem, jak aktualizovat seznam **Wi-Fi,** je přepnout nastavení Wi-Fi Off (Vypnuto) a On (Zapnout). Zabrání se tak mnoha problémům, jako je například to, že zařízení může zůstat "zablokované" na přístupové bodu, když je mimo rozsah.

## <a name="connect-hololens-to-enterprise-wi-fi-network"></a>Připojení HoloLens k Enterprise Wi-Fi Network

Podnikové Wi-Fi používají k ověřování připojení protokol EAP (Extensible Authentication ProtocolWi-Fi připojení. Profil holoLens Enterprise Wi-Fi nakonfigurovat prostřednictvím MDM nebo zřizovacího balíčku vytvořeného [pomocí Windows Configuration Designeru.](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages)

Pokyny Microsoft Intune spravovaném zařízení [najdete v Intune.](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)

Pokud chcete ve Wi-Fi WCD vytvořit zřizovací balíček, je Wi-Fi nakonfigurovaný soubor .xml profilu. Tady je ukázkový profil Wi-Fi pro WPA2-Enterprise s ověřováním EAP-TLS:

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


Certifikát kořenové certifikační autority serveru a klientský certifikát může být potřeba zřídit v zařízení v závislosti na typu protokolu EAP.

Další prostředky:

- Schéma WLANv1Profile: [[MS-GPWL]: Profil bezdrátové sítě LAN v1 | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/34054c93-cfcd-44df-89d8-5f2ba7532b67)
- Schéma EAP-TLS: [[MS-GPWL]: Schéma protokolu EAP | Microsoft Docs](https://docs.microsoft.com/openspecs/windows_protocols/ms-gpwl/9590925c-cba2-4ac5-b9a1-1e5292bb72cb)

Pokud máte [problémy](hololens2-enterprise-troubleshooting.md#) s připojením k Wi-Fi, podívejte se na naši stránku řešení potíží.

## <a name="configure-network-proxy"></a>Konfigurace síťového proxy serveru

Tato část se věnuje proxy serveru sítě pro operační systém HoloLens a Univerzální platforma Windows (UPW) využívající zásobník HTTP pro Windows. Aplikace používající zásobník HTTP jiné než Windows mohou mít vlastní konfiguraci a zpracování proxy serveru. 

### <a name="proxy-configurations"></a>Konfigurace proxy serveru 

- Skript PAC (Proxy Auto-Config): Soubor [PAC](https://developer.mozilla.org/en-US/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_PAC_file) (otevře web jiné společnosti než Microsoft) obsahuje funkci Jazyka JavaScript FindProxyForURL(adresa URL, hostitel). 
- Statický proxy server: ve tvaru Server:Port.  
- Protokol WPAD (Web Proxy Auto-Discovery Protocol): Zadejte adresu URL konfiguračního souboru proxy serveru prostřednictvím DHCP nebo DNS. 

### <a name="proxy-provisioning-methods"></a>Metody zřizování proxy serveru 
Existují tři způsoby, jak zřídit proxy:

 

1.  **Uživatelské rozhraní nastavení:** 
    1. Proxy server pro uživatele (20H2 nebo starší):
        1. Otevřete nabídka Start a vyberte Nastavení.
        2. Vyberte Network & Internet a pak v nabídce vlevo vyberte Proxy.
        3. Posuňte se dolů na Manual proxy setup (Ruční nastavení proxy serveru) a přepněte Use a proxy server (Použít proxy server) na On (Zapnout).
        4. Zadejte IP adresu proxy server.
        5. Zadejte číslo portu.
        6. Klikněte na Uložit.
      1. Proxy připojení WiFi (21H1 nebo vyšší):
          1. Otevřete nabídka Start a přejděte na Wi-Fi vlastností vaší sítě.
          1. Posuňte se dolů na Proxy.
          1. Změna na ruční nastavení
          1. Zadejte IP adresu proxy server.
          1. Zadejte číslo portu.
          1. Klikněte na Použít.
        
 2. **MDM** 
     1. Intune – Pomocí těchto [kroků můžete](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile) nakonfigurovat proxy server v Intune. Budete se muset posunout do dolní části oddílu.
     1. Jiná řešení MDM třetích stran – Použijte [WiFi CSP.](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp)

3. **PPKG** 
    1. Otevřete Windows Configuration Designer.
    1. Klikněte na Rozšířené zřizování, zadejte název nového projektu a klikněte na Další.
    1. Vyberte Windows Holographic (HoloLens 2) a klikněte na Další.
    1. Importujte PPKG (volitelné) a klikněte na Dokončit.
    1. Rozbalte Položku Nastavení modulu runtime -> Profily připojení -> WLAN -> Proxy WLAN.
    1. Zadejte SSID vaší Wi-Fi sítě a klikněte na Přidat.
    1. V levém Wi-Fi vyberte svou síť a zadejte požadovaná vlastní nastavení. Povolená vlastní nastavení se v nabídce vlevo zobrazí tučně.
    1. Klikněte na Uložit a ukončit.
    1. [Použijte](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup) zřizovací balíček pro HoloLens.

[Poskytovatelé cloudových](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) služeb jsou za mnoha úkoly a zásadami správy pro Windows 10, a to jak v Microsoft Intune, tak u jiných poskytovatelů služeb MDM než Microsoftu. Pomocí Návrháře konfigurace [systému Windows](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-install-icd) můžete také vytvořit [zřizovací balíček](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-packages) a použít ho na HoloLens 2.
Nejpravděpodobnějšími csP, které se použijí pro HoloLens 2, jsou:

- [WiFi CSP:](https://docs.microsoft.com/windows/client-management/mdm/wifi-csp)proxy server pro Wi-Fi profilu 

[Ostatní csP podporovaní na zařízeních HoloLens](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)





## <a name="vpn"></a>Síť VPN
Připojení VPN může pomoct zajistit bezpečnější připojení a přístup k firemní síti a internetu. HoloLens 2 podporuje integrovaného klienta VPN a Univerzální platforma Windows (UPW) VPN. 

Podporované integrované protokoly VPN:
- IKEv2
- L2TP
- PPTP

Pokud se certifikát používá k ověřování pro integrovaného klienta VPN, je potřeba požadovaný klientský certifikát přidat do úložiště uživatelských certifikátů. Pokud chcete zjistit, jestli modul plug-in VPN třetí strany podporuje HoloLens 2, přejděte do Storu, vyhledejte aplikaci VPN a zkontrolujte, jestli je HoloLens uvedené jako podporované zařízení, a na stránce Požadavky na systém aplikace podporuje architekturu ARM nebo ARM64. HoloLens podporuje Univerzální platforma Windows aplikace pro síť VPN třetí strany.

 Síť VPN je možné spravovat pomocí MDM přes [Nastavení/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)a nastavit ji prostřednictvím zásad [Vpnv2-csp.](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)

Další informace o [konfiguraci sítě VPN najdete v](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) těchto [příručkách.](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide)  

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
