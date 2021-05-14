---
title: Session Border Controller certificati per il routing diretto
ms.author: crowe
ms.reviewer: FilippSe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
hideEdit: true
f1.keywords:
- NOCSH
description: L'amministratore può sapere quali session border controller (SBC) sono stati certificati per il routing diretto.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4eab3bb25690c939afd2687f5a67e63a2c417a89
ms.sourcegitcommit: 272e8cf0075a566f055801433c9eb0313050530f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2021
ms.locfileid: "52486370"
---
# <a name="list-of-session-border-controllers-certified-for-direct-routing"></a>Elenco di Session Border Controller certificati per Instradamento diretto

Microsoft collabora con fornitori SBC (Session Border Controller) selezionati per certificare che i loro SBC funzionano con il routing diretto.

Microsoft collabora con ogni fornitore per:

- Collaborare ai protocolli di interconnessione SIP.
- Eseguire test intensi usando un laboratorio di terze parti. Solo i dispositivi che superano i test sono certificati.
- Eseguire test giornalieri con tutti i dispositivi certificati negli ambienti di produzione e pre-produzione. La convalida dei dispositivi in ambienti di pre-produzione garantisce che le nuove versioni del codice direct routing nel cloud funzionino con SBC certificati.
- Stabilire un processo di supporto congiunto con i fornitori SBC.

  > [!NOTE]
  > Microsoft supporta l'Sistema telefonico se uno o più dispositivi certificati sono connessi tramite Routing diretto. Microsoft si riserva il diritto di rifiutare i casi di supporto in cui un dispositivo non certificato è connesso al Sistema telefonico tramite Routing diretto. Se Microsoft determina che il problema di instradamento diretto di un cliente riguarda il dispositivo SBC di un fornitore, il cliente dovrà coinvolgere il fornitore SBC per ottenere supporto.

Le tabelle che seguono elencano i dispositivi certificati per il routing diretto. Per informazioni sui fornitori SBC che supportano l'ottimizzazione dei supporti multimediali locali, vedere Configurare l'ottimizzazione [dei supporti locali per il routing diretto.](direct-routing-media-optimization-configure.md)

[Altre informazioni su Routing diretto](https://aka.ms/dr).
Se hai domande sul programma di certificazione SBC per Direct Routing, contatta drsbccertification@microsoft.com.
<br/>

## <a name="certified-sbc-vendors"></a>Fornitori SBC certificati

|                                                       Fornitore                                                        |       Prodotto       | Bypass non multimediale | Bypass multimediale | Versione software | 911 Service Provider Capable | ELIN in grado di
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|--------------|------------------|-----------------|------------------|
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   Mediant 500 SBC   |     &#10004;     |   &#10004;    |  Supportata 7.20A.250 (scelta consigliata 7.20A.258)   | &#10004;   |  &#10004;  |
|                                                                                                                     |   Mediant 800 SBC   |     &#10004;     |   &#10004;     |  Supportata 7.20A.250 (scelta consigliata 7.20A.258)   | &#10004;   |  &#10004;  |
|                                                                                                                     |  Mediant 2600 SBC   |     &#10004;     |   &#10004;    |  Supportata 7.20A.250 (scelta consigliata 7.20A.258)   |   &#10004;   |  &#10004;  |    
|                                                                                                                     |  Mediant 4000 SBC   |     &#10004;     |   &#10004;     |  Supportata 7.20A.250 (scelta consigliata 7.20A.258)   |  &#10004;   |  &#10004;  |    
|                                                                                                                     | Mediant 1000B SBC  |     &#10004;     |   In sospeso     |  Supportata 7.20A.250 (scelta consigliata 7.20A.258)  |  &#10004;   |  &#10004;  |    
|                                                                                                                     | Mediant 9000 SBC  |     &#10004;     |   &#10004;     |  Supportata 7.20A.250 (scelta consigliata 7.20A.258)   | &#10004;     |  &#10004;  |                                                                       
|                                                                                                                     | Virtual Edition SBC |     &#10004;     |   &#10004;     |  Supportata 7.20A.250 (scelta consigliata 7.20A.258) |  &#10004;    |  &#10004;  |    
|  [Comunicazioni sulla barra multifunzione](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5100/5110       |     &#10004;     |   &#10004;    |       8.2 e 7.2 supportati (scelta consigliata 9.2)       | &#10004;   |     |    
|                                                                                                                     |      SBC 5200/5210       |     &#10004;     |  &#10004;    |       8.2 e 7.2 supportati (scelta consigliata 9.2)       |   &#10004; |    |    
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       8.2 e 7.2 supportati (scelta consigliata 9.2)       |   &#10004;  ||    
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       8.2 e 7.2 supportati (scelta consigliata 9.2)       |    &#10004;  |  |    
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       8.2 e 7.2 supportati (scelta consigliata 9.2)          |  &#10004;    |    |    
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      8.x o 9.x     |   &#10004;  |  &#10004;     |    
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     8.x o 9.x     |   &#10004;   |     &#10004;     |    
|                                                                                                                     |    SBC SWe Lite     |     &#10004;     |  &#10004;    |      8.x o 9.x    |   &#10004;    |     &#10004;     |   
| | Serie EdgeMarc |  &#10004; | | 15.6.1 | 
|                     [Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    Think 365 SBC    |     &#10004;     |           |       1.4       |     |    |    
|                     [Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |   &#10004;    |  &#10004;  |    
|    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  |  &#10004;    |  &#10004;  |    
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |    
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |    
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |   &#10004;   |  &#10004;  |                                            
|                                                                                                                    |      VME           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |   &#10004;   |  &#10004;  |    
|                     [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      Supportata 3.20 (scelta consigliata 4.0)        |  &#10004;    |  &#10004;   |    
|                     [Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)                               |     Perimeta SBC        |     &#10004;   |  |      4.7      |     |    |  
|                     [Cisco](https://www.cisco.com/c/en/us/solutions/enterprise/interoperability-portal/networking_solutions_products_genericcontent0900aecd805bd13d.html)                               |     Cisco Unified Border Element (CUBE) per router di servizi integrati serie 1000        |     &#10004;   | &#10004; |      IOS XE Amsterdam 17.2.1r supportato (scelta consigliata 17.3.2)         |    &#10004;     |   |  
|                                   |     Cisco Unified Border Element (CUBE) per router di servizi integrati della serie 4000        |     &#10004;   | &#10004; |   IOS XE Amsterdam 17.2.1r supportato (scelta consigliata 17.3.2)         |   &#10004;      |    |  
|                                   |     Cisco Unified Border Element (CUBE) per router di servizi cloud serie 1000V       |     &#10004;   | &#10004; |      IOS XE Amsterdam 17.2.1r supportato (scelta consigliata 17.3.2)         |    &#10004;     |    |  
|                                 |     Cisco Unified Border Element (CUBE) per router dei servizi di aggregazione serie 1000      |     &#10004;   | &#10004; |      IOS XE Amsterdam 17.2.1r supportato (scelta consigliata 17.3.2)         |    &#10004;     |    |
|                                 |     Cisco Unified Border Element (CUBE) per catalyst 8000 Edge Platforms      |     &#10004;   | &#10004; |      IOS XE Amsterdam 17.3.2      |    &#10004;     |    |
|                     [Avaya](https://support.avaya.com/products/P0997/avaya-session-border-controller-for-enterprise/8.1.x)|    Avaya Session Border Controller per Enterprise ( ASBCE)    |     &#10004;     |       &#10004;     |       Rilascio 8.1.1 (8.1.2 per Media Bypass)      |     |    | 
|                     [Nokia](https://documentation.nokia.com/aces/cgi-bin/chk_access.cgi/3TB30222GBAAACZZA.zip)|    Nokia Session Border Controller    |     &#10004;     |           |       19.5 (1908)       |     |    | 
|                     |    Nokia Session Border Controller    |     &#10004;     |           |       20.8       |      &#10004;        |    | 
|                     [Italtel](https://www.italtel.com/italtel-provides-direct-routing-sbc-for-microsoft-teams/)|    NetMatch-S CI     |     &#10004;     |           |       Supportata 5.0 (scelta consigliata 5.1)     |     |    | 
|                     [Ericsson](https://www.ericsson.com/en/portfolio/digital-services/cloud-communication/enterprise-communication/business-communication-services-and-enablers/sip-trunking)|    vSBC 2.16     |     &#10004;     |           |              |     |    | 
|                     [Cataleya](https://cataleya.com/orchidplatforms/)|    Collegamento orchidea    |     &#10004;     |           |      3.1        |     |    | 
|                     [ULTATEL](https://www.ultatel.com/services/direct-routing-teams-sbc)|    Teams SBC    |     &#10004;     |     &#10004;      |      1.6        |     |    | 
|                     [Atos](https://unify.com/en/solutions/voice-platforms/session-border-controller)|    Atos Unify OpenScape Session Border Controller   |     &#10004;     |          |      V10R1.2       |     |    | 
|                     [Sansay Inc.](https://www.sansay.com/solutions/microsoft-teams/)|    vmVSXi   |     &#10004;     |     &#10004;     |      10.5.1.354-vm-S-x64      |     |    |
|                     [Reti Enghouse](https://www.enghousenetworks.com/portfolio/network-infrastructure/cloud-native-session-border-controller-sbc/)|    Dialogic BorderNet SBC   |     &#10004;     |     &#10004;     |      3.9.0-786      |     |    |
|                     [Patton Electronics Co.](https://www.patton.com/microsoft/)|    Patton SmartNode eSBC   |     &#10004;     |         |      3.19.x      |     |    |

<br/>
<br/>

## <a name="direct-routing-and-analog-devices-interoperability"></a>Routing diretto e interoperabilità di dispositivi analogici

La tabella seguente elenca i dispositivi verificati per l'interoperabilità tra Routing diretto e Dispositivi analogici.

|                                                       Fornitore                                                        |       Prodotto       | Verificato
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-1](https://www.audiocodes.com/media/2373/mp-1xx-and-mp-124-datasheet.pdf)   |     &#10004;     |
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-2](https://www.audiocodes.com/media/2399/mediapack-20x-mp-20x-analog-telephone-adapters-datasheet.pdf)   |     &#10004;     | 
| [Cisco](https://www.cisco.com/c/en/us/products/collateral/unified-communications/ata-190-series-analog-telephone-adapters/datasheet-c78-740013.html) |  Adattatore telefonico analogico multipiattaforma ATA 191 |     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |   AP1100 Software Versione 8.3.0.1.2 |     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP3900 Software Versione 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP4600 Software Versione 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP6300 Software Versione 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP6350 Software Versione 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  VmE Software Versione 8.3.0.1.2 |     &#10004;     |
| [Barra multifunzione](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 1000. Versione software: 8.1.1 (build 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [Barra multifunzione](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 2000. Versione software: 8.1.1 (build 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/) |  anynode con Grandstream GXW42xx (V1.0.7.10) |     &#10004;     |
  
Per inviare feedback sui prodotti Teams, ad esempio idee per le nuove funzionalità, vedere [Uservoice.](https://microsoftteams.uservoice.com)


[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

Si noti la certificazione concessa a una versione principale. Questo significa che è supportato il firmware con qualsiasi numero nel firmware SBC che segue la versione principale.
