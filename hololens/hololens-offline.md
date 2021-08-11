---
title: Správa koncových bodů připojení pro HoloLens
description: naučte se, jak nastavit HoloLens přes Wi-Fi síť při správě a konfiguraci koncových bodů připojení.
keywords: HoloLens, offline, OOBE
audience: ITPro
ms.date: 07/01/2019
ms.assetid: b86f603c-d25f-409b-b055-4bbc6edcd301
author: Teresa-Motiv
ms.author: v-tea
ms.custom:
- CI 111456
- CSSTroubleshooting
manager: jarrettr
ms.topic: article
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 63c82e5b1a953ee2f69bf4c22a8442c7bca07f073cc13f1e5e573fde0ccc1976
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662934"
---
# <a name="manage-connection-endpoints-for-hololens"></a>Správa koncových bodů připojení pro HoloLens

některé součásti HoloLens, aplikace a související služby přenášejí data do koncových bodů sítě microsoftu. Tento článek obsahuje seznam různých koncových bodů a adres URL, které je potřeba povolit ve vaší konfiguraci sítě (třeba proxy nebo bráně firewall), aby tyto součásti byly funkční.    

## <a name="near-offline-setup"></a>Téměř offline instalace

HoloLens podporuje omezené množství offline prostředí pro zákazníky, kteří mají omezení síťového prostředí. HoloLens ale potřebuje síťové připojení k přechodu prostřednictvím počátečního nastavení zařízení a musí být povolené tyto adresy url:

| Účel | URL |
|------|------|
| ZPROSTŘEDKOVATELŮ identity | https://sdx.microsoft.com/frx/idps |
| [NCSI](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services#bkmk-ncsi) |  http://www.msftconnecttest.com/connecttest.txt  |
| AADv9 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/9 |
| AADv10 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/10 |
| PIN kód AAD | https://account.live.com/aadngc?uiflavor=win10&showSuccess=1 |
| MSA | https://login.live.com/ppsecure/inlineconnect.srf?id=80600 |
| MSA kód PIN | https://account.live.com/msangc?fl=enroll |

## <a name="endpoint-configuration"></a>Konfigurace koncového bodu

kromě výše HoloLens uvedeného seznamu musí být ve vaší konfiguraci sítě povolené tyto koncové body:.


| Účel | URL |
|------|------|
| Azure                                               | wd-prod-fe.cloudapp.azure.com                                       |
|                                                     | ris-prod-atm.trafficmanager.net                                     |
|                                                     | validation-v2.sls.trafficmanager.net                                |
| Vícefaktorové ověřování Azure AD                | https://secure.aadcdn.microsoftonline-p.com                         |
| Konfigurace Intune a MDM                       | activation-v2.sls.microsoft.com/*                                   |
|                                                     | cdn.onenote.net                                                     |
|                                                     | client.wns.windows.com                                              |
|                                                     | crl.microsoft.com/pki/crl/*                                         |
|                                                     | ctldl.windowsupdate.com                                             |
|                                                     | * displaycatalog.mp.microsoft.com                                    |
|                                                     | dm3p.wns.windows.com                                                |
|                                                     | *microsoft.com/pkiops/*                                             |
|                                                     | ocsp.digicert.com/*                                                 |
|                                                     | r.manage.microsoft.com                                              |
|                                                     | tile-service.weather.microsoft.com                                  |
|                                                     | settings-win.data.microsoft.com                                     |
| Certifikáty                                        | activation-v2.sls.microsoft.com/*                                   |
|                                                     | crl.microsoft.com/pki/crl/*                                         |
|                                                     | ocsp.digicert.com/*                                                 |
|                                                     | https://www.microsoft.com/pkiops/*                                          |
| Cortana a hledání                                  | Store-images. * Microsoft. com                                         |
|                                                     | www.bing.com/client                                                 |
|                                                     | www.bing.com                                                        |
|                                                     | www.bing.com/proactive                                              |
|                                                     | www.bing.com/threshold/xls.aspx                                     |
|                                                     | exo-ring.msedge.net                                                 |
|                                                     | fp.msedge.net                                                       |
|                                                     | fp-vp.azureedge.net                                                 |
|                                                     | odinvzc.azureedge.net                                               |
|                                                     | spo-ring.msedge.net                                                 |
| Ověřování zařízení                               | login.live.com *                                                     |
| Metadata zařízení                                     | dmd.metaservices.microsoft.com                                      |
| Umístění                                            | inference.location.live.net                                         |
|                                                     | location-inference-westus.cloudapp.net                              |
| Diagnostická data                                     | v10.events.data.microsoft.com                                       |
|                                                     | v10.vortex-win.data.microsoft.com/collect/v1                        |
|                                                     | https://www.microsoft.com                                                   |
|                                                     | co4.telecommand.telemetry.microsoft.com                             |
|                                                     | cs11.wpc.v0cdn.net                                                  |
|                                                     | cs1137.wpc.gammacdn.net                                             |
|                                                     | modern.watson.data.microsoft.com *                                   |
|                                                     | watson.telemetry.microsoft.com                                      |
| Licencování                                           | licensing.mp.microsoft.com                                          |
| Účet Microsoft                                   | login.msa.akadns6.net                                               |
|                                                     | us.configsvc1.live.com.akadns.net                                   |
| Microsoft Edge                                      | iecvlist.microsoft.com                                              |
| Služba přesměrování služby přesměrovaná přes propojení společnosti Microsoft (FWLink) | go.microsoft.com                                                    |
| Microsoft Store                                     | *. wns.windows.com                                                   |
|                                                     | storecatalogrevocation.storequality.microsoft.com                   |
|                                                     | IMG-prod-CMS-RT-Microsoft-com *                                      |
|                                                     | store-images.microsoft.com                                          |
|                                                     | . md.mp.microsoft.com                                                |
|                                                     | * displaycatalog.mp.microsoft.com                                    |
|                                                     | pti.store.microsoft.com                                             |
|                                                     | storeedgefd.dsx.mp.microsoft.com                                    |
|                                                     | markets.books.microsoft.com                                         |
|                                                     | share.microsoft.com                                                 |
| Indikátor stavu připojení k síti (NCSI)          | www.msftconnecttest.com *                                            |
| Office                                              | *. c-msedge.net                                                      |
|                                                     | *. e-msedge.net                                                      |
|                                                     | *. s-msedge.net                                                      |
|                                                     | nexusrules.officeapps.live.com                                      |
|                                                     | ocos-office365-s2s.msedge.net                                       |
|                                                     | officeclient.microsoft.com                                          |
|                                                     | outlook.office365.com                                               |
|                                                     | client-office365-tas.msedge.net                                     |
|                                                     | https://www.office.com                                                      |
|                                                     | onecollector.cloudapp.aria                                          |
|                                                     | v10.events.data.microsoft.com/onecollector/1.0/                     |
|                                                     | self.events.data.microsoft.com                                      |
|                                                     | to-do.microsoft.com                                                 |
| OneDrive                                            | g.live.com/1rewlive5skydrive/*                                      |
|                                                     | msagfx.live.com                                                     |
|                                                     | oneclient.sfx.ms                                                    |
| Aplikace Photos                                          | evoke-windowsservices-tas.msedge.net                                |
| Nastavení                                            | cy2.settings.data.microsoft.com.akadns.net                          |
|                                                     | settings.data.microsoft.com                                         |
|                                                     | settings-win.data.microsoft.com                                     |
| Windows Defender                                    | wdcp.microsoft.com                                                  |
|                                                     | definitionupdates.microsoft.com                                     |
|                                                     | go.microsoft.com                                                    |
|                                                     | *smartscreen.microsoft.com                                          |
|                                                     | smartscreen-sn3p.smartscreen.microsoft.com                          |
|                                                     | unitedstates.smartscreen-prod.microsoft.com                         |
| Windows Spotlight                                   | *.search.msn.com                                                    |
|                                                     | arc.msn.com                                                         |
|                                                     | g.msn.com*                                                          |
|                                                     | query.prod.cms.rt.microsoft.com                                     |
|                                                     | ris.api.iris.microsoft.com                                          |
| Windows Update                                      | *.prod.do.dsp.mp.microsoft.com                                      |
|                                                     | cs9.wac.phicdn.net                                                  |
|                                                     | emdl.ws.microsoft.com                                               |
|                                                     | *.dl.delivery.mp.microsoft.com                                      |
|                                                     | *.windowsupdate.com                                                 |
|                                                     | *.delivery.mp.microsoft.com                                         |
|                                                     | *.update.microsoft.com                                              |



## <a name="references"></a>Reference

> [!NOTE]
> Pokud nasazujete D365 Remote Assist, budete muset povolit koncové body uvedené pro SharePoint Online a OneDrive pro firmy v adresách URL Office 365 a rozsahech [IP adres](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).

- [Konfigurace Windows diagnostických dat ve vaší organizaci](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)
- [Správa koncových bodů připojení Windows 10 Enterprise, verze 1903](/windows/privacy/manage-windows-1903-endpoints)
- [Správa připojení z Windows 10 operačního systému k služby Microsoft](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services)
- [Správa připojení z Windows 10 operačního systému k služby Microsoft pomocí Microsoft Intune MDM Serveru](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services-using-mdm)
- [Požadavky na konfiguraci a šířka pásma sítě pro Intune](/intune/fundamentals/network-bandwidth-use#network-communication-requirements)
- [Koncové body sítě pro Microsoft Intune](/intune/fundamentals/intune-endpoints)
- [Adresy URL a rozsahy IP adres pro Office 365](/office365/enterprise/urls-and-ip-address-ranges)
- [Požadavky pro Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)


## <a name="hololens-limitations"></a>HoloLens omezení

Po HoloLens můžete aplikaci používat bez připojení Wi-Fi, ale aplikace, které používají připojení k internetu, budou mít při použití HoloLens offline omezené možnosti.
