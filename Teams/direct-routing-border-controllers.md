---
title: Session Border Controller certificati per l'instradamento diretto
ms.author: crowe
ms.reviewer: FilippSe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: high
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
hideEdit: true
f1.keywords:
- NOCSH
description: Scopri quali Session Border Controller (SBC) sono stati certificati per l'instradamento diretto.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3805a87171a770298e41337dfdd569c1b7d76985
ms.sourcegitcommit: 2044fdcb0c5db10dbc77c5d66e382c1b927ccdc4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/01/2022
ms.locfileid: "63039994"
---
# <a name="session-border-controllers-certified-for-direct-routing"></a>Session Border Controller certificati per l'instradamento diretto

Microsoft collabora con fornitori selezionati di Session Border Controller (SBC) per certificare che i SBC funzionano con l'instradamento diretto.

Microsoft collabora con ogni fornitore per:

- Collaborare ai protocolli di interconnessione SIP.
- Eseguire test intensi usando un laboratorio di terze parti. Solo i dispositivi che superano i test sono certificati.
- Eseguire test giornalieri con tutti i dispositivi certificati negli ambienti di produzione e pre-produzione. La convalida dei dispositivi in ambienti di pre-produzione garantisce che le nuove versioni del codice di instradamento diretto nel cloud funzionino con SBC certificati.
- Stabilire un processo di supporto congiunto con i fornitori di SBC.

  > [!NOTE]
  > Microsoft supporta solo un sistema telefonico con instradamento diretto se usato con dispositivi certificati. In caso di problemi, è necessario contattare prima l'assistenza clienti del fornitore SBC. Se necessario, il fornitore SBC invierà il problema a Microsoft tramite canali interni. Microsoft si riserva il diritto di rifiutare i casi di supporto in cui un dispositivo non certificato è connesso al sistema telefonico tramite instradamento diretto. Se Microsoft determina che il problema di instradamento diretto di un cliente riguarda un dispositivo SBC di un fornitore, il cliente dovrà contattare nuovamente il fornitore SBC per ricevere supporto.
  >
  > La certificazione viene concessa a specifiche versioni del firmware SBC. Qualsiasi versione del firmware SBC documentata di seguito è certificata e supportata. Le versioni del firmware superiori a quelle documentate sono supportate purché la versione principale.secondaria sia la stessa.
  >
  > Esempio:
  >
  > - Supportata 6.10.258 - In questo caso, Microsoft supporta la versione firmware 6.10. (258 o versioni successive).
  > - Consigliato 6.20.100 - In questo caso, Microsoft consiglia la versione firmware 6.20. (100 o versione successiva).
  > - Per domande sul supporto di una versione specifica, contattare il fornitore del SBC.

Le tabelle di seguito elencano i dispositivi certificati per l'instradamento diretto. Per informazioni sui fornitori di SBC che supportano l'ottimizzazione degli elementi multimediali locali, vedere [Configurare l'ottimizzazione degli elementi multimediali locali per l'instradamento diretto](direct-routing-media-optimization-configure.md).

[Altre informazioni sull'instradamento diretto](https://aka.ms/dr).
Per eventuali domande sul programma di certificazione di SBC per l'instradamento diretto, contattare drsbccertification@microsoft.com. Nota: non accettiamo nuove candidature per la certificazione fino a nuovo avviso.
<br/>

## <a name="certified-sbc-vendors"></a>Fornitori di SBC certificati

|                                                       Fornitore                                                        |       Prodotto       | Bypass non multimediale | Bypass multimediale | Versione software | Con supporto del provider di servizi 911* | Con supporto di ELIN |  
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|--------------|------------------|-----------------|------------------|  
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   Mediant 500 SBC   |     &#10004;     |   &#10004;    |  Supportato 7.20A.258 (consigliato 7.40A.250)   | &#10004;   |  &#10004;  |  
|                                                                                                                     |   Mediant 800 SBC   |     &#10004;     |   &#10004;     |  Supportato 7.20A.258 (consigliato 7.40A.250)   | &#10004;   |  &#10004;  |  
|                                                                                                                     |  Mediant 2600 SBC   |     &#10004;     |   &#10004;    |  Supportato 7.20A.258 (consigliato 7.40A.250)   |   &#10004;   |  &#10004;  |
|                                                                                                                     |  Mediant 4000 SBC   |     &#10004;     |   &#10004;     |  Supportato 7.20A.258 (consigliato 7.40A.250)   |  &#10004;   |  &#10004;  |
|                                                                                                                     | Mediant 1000B SBC  |     &#10004;     |   &#10004;     |  Supportato 7.20A.250 (consigliato 7.40A.250)  |  &#10004;   |  &#10004;  |
|                                                                                                                     | Mediant 9000  SBC  |     &#10004;     |   &#10004;     |  Supportato 7.20A.258 (consigliato 7.40A.250)   | &#10004;     |  &#10004;  |
|                                                                                                                     | Virtual Edition SBC |     &#10004;     |   &#10004;     |  Supportato 7.20A.258 (consigliato 7.40A.250) |  &#10004;    |  &#10004;  |   
|                                                                                                                     | Mediant Cloud Edition SBC  |     &#10004;     |   &#10004;     |  Supportato 7.20A.258 (consigliato 7.40A.250) |  &#10004;    |  &#10004;  |
|  [Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5100/5110       |     &#10004;     |   &#10004;    |       Supportata 9.2, 8.2 e 7.2 (scelta consigliata 10.1)       | &#10004;   |     |
|                                                                                                                     |      SBC 5200/5210       |     &#10004;     |  &#10004;    |       Supportata 9.2, 8.2 e 7.2 (scelta consigliata 10.1)       |   &#10004; |    |
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       Supportata 9.2, 8.2 e 7.2 (scelta consigliata 10.1)       |   &#10004;  | |
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       Supportata 9.2, 8.2 e 7.2 (scelta consigliata 10.1)       |    &#10004;  |  |
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       Supportata 9.2, 8.2 e 7.2 (scelta consigliata 10.1)          |  &#10004;    |    |
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      8.x o 9.x     |   &#10004;  |  &#10004;     |
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     8.x o 9.x     |   &#10004;   |     &#10004;     |
|                                                                                                                     |    SBC SWe Lite     |     &#10004;     |  &#10004;    |      8.x o 9.x    |   &#10004;    |     &#10004;     |
| | EdgeMarc Series |  &#10004; | | 15.6.1 | |  
|                     [Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    Think 365 SBC    |     &#10004;     |           |       1.4       |     |    |
|                     [Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |   &#10004;    |  &#10004;  |
|    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |   &#10004;   |  &#10004;  |
|                                                                                                                    |      VME           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |   &#10004;   |  &#10004;  |
|                     [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      Supportato 3.20 (consigliato 4.0)        |  &#10004;    |  &#10004;   |
|                     [Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)                               |     Perimeta SBC        |     &#10004;   | &#10004; |      4.7 (4.9 per bypass multimediale)      | &#10004; | &#10004; |  
|                     [Cisco](https://www.cisco.com/c/en/us/solutions/enterprise/interoperability-portal/networking_solutions_products_genericcontent0900aecd805bd13d.html)                               |     Cisco Unified Border Element (CUBE) for 1000 Series Integrated Services Routers        |     &#10004;   | &#10004; |      Supportato IOS XE Amsterdam 17.2.1r (consigliato 17.6.1a)         |    &#10004;     |   |  
|                                   |     Cisco Unified Border Element (CUBE) for 4000 Series Integrated Services Routers        |     &#10004;   | &#10004; |   Supportato IOS XE Amsterdam 17.2.1r (consigliato 17.6.1a)         |   &#10004;      |    |  
|                                   |     Cisco Unified Border Element (CUBE) for 1000V Series Cloud Services Router       |     &#10004;   | &#10004; |      Supportato IOS XE Amsterdam 17.2.1r (consigliato 17.3.3)         |    &#10004;     |    |  
|                                 |     Cisco Unified Border Element (CUBE) for 1000 Series Aggregation Services Routers      |     &#10004;   | &#10004; |      Supportato IOS XE Amsterdam 17.2.1r (consigliato 17.6.1a)         |    &#10004;     |    |
|                                 |     Cisco Unified Border Element (CUBE) for Catalyst 8000 Edge Platforms      |     &#10004;   | &#10004; |      IOS XE Amsterdam 17.3.2 supportato (consigliato 17.6.1a)      |    &#10004;     |    |
|                     [Avaya](https://support.avaya.com/products/P0997/avaya-session-border-controller-for-enterprise/8.1.x)|    Avaya Session Border Controller for Enterprise (ASBCE)    |     &#10004;     |       &#10004;     |       Release 8.1.1 (8.1.2 per bypass multimediale)      |     |    |
|                     [Nokia](https://documentation.nokia.com/aces/cgi-bin/chk_access.cgi/3TB30222GBAAACZZA.zip)|    Nokia Session Border Controller    |     &#10004;     |           |       19.5 (1908)       |     |    |
|                     |    Nokia Session Border Controller    |     &#10004;     |           |       20.8       |      &#10004;        |    |
|                     [Italtel](https://www.italtel.com/italtel-provides-direct-routing-sbc-for-microsoft-teams/)|    NetMatch-S CI     |     &#10004;     |      &#10004;     |       Supportata 5.0 e 5.1 (scelta consigliata 5.3)     |     |    |
|                     [Ericsson](https://www.ericsson.com/en/portfolio/digital-services/cloud-communication/enterprise-communication/business-communication-services-and-enablers/sip-trunking)|    vSBC 2.16     |     &#10004;     |           |              |     |    |
|                     [Cataleya](https://cataleya.com/orchidplatforms/)|    Orchid Link    |     &#10004;     |           |      3.1        |     |    |
|                     [ULTATEL](https://www.ultatel.com/services/direct-routing-teams-sbc)|    Teams SBC    |     &#10004;     |     &#10004;      |      1.6        |     |    |
|                     [Atos](https://unify.com/en/solutions/voice-platforms/session-border-controller)|    Atos Unify OpenScape Session Border Controller   |     &#10004;     |   &#10004;        |     V10R2.2.0     |     |    |
|                     [Sansay Inc.](https://www.sansay.com/solutions/microsoft-teams/)|    vmVSXi   |     &#10004;     |     &#10004;     |      10.5.1.354-vm-S-x64      |     |    |
|                     [Enghouse Networks](https://www.enghousenetworks.com/portfolio/network-infrastructure/cloud-native-session-border-controller-sbc/)|    Dialogic BorderNet SBC   |     &#10004;     |     &#10004;     |      3.9.0-786      |     |    |
|                     [Patton Electronics Co.](https://www.patton.com/microsoft/)|    Patton SmartNode eSBC   |     &#10004;     |         |      3.19.x      |     |    |
|                     [M5 Technologies (in precedenza noto come Media5 Corporation)](https://www.m5t.com/solutions/sentinel-sbc-ms-teams-certified/)|    Mediatrix Sentinel Series   |     &#10004;     |         |      DGW 48.0.2340 (consigliato DGW 48.1.2503)      |     |    |
|                     [Ekinops](https://www.ekinops.com/solutions/voice-data-access/microsoft-direct-routing-sbc)|    Ekinops Session Border Controller (ONeSBC)   |     &#10004;     |     &#10004;     |      6.6.1m5ha1      |     |    |
|                     |    Ekinops Virtual Session Border Controller (ONEvSBC)   |     &#10004;     |    &#10004;      |      6.6.1m5ha1      |     |    |
|                     [46 Labs LLC](https://46labs.com/docs/hcvoice/teams/)|    Hyperconverged Voice   |     &#10004;     |     &#10004;      |      HCVoice 1.0.6       |     |    |

<br/>

\* **Provider di servizi 911**

- [Instradamento della posizione dinamica della larghezza di banda](https://www.bandwidth.com/partners/microsoft-teams-direct-routing/)
- [Intrado Emergency Routing Service (ERS)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
- [Intrado Emergency Gateway (EGW)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
- [Inteliquent](https://www.inteliquent.com/services/emergency-services/e911)

<br/>

## <a name="support-for-local-media-optimization"></a>Supporto per l'ottimizzazione dei supporti multimediali locali

La tabella seguente descrive quali fornitori di SBC supportano [l'ottimizzazione dei supporti multimediali locali.](direct-routing-media-optimization.md) 

| Fornitore | Prodotto |    Versione software |
|:------------|:-------|:-------|
| [AudioCodes](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    Mediant 500 SBC |   7.20A.256 | 
|            |  Mediant 800 SBC |   Supportato 7.20A.258 (consigliato 7.40A.100)  |  
|            |  Mediant 2600 SBC |  Supportato 7.20A.258 (consigliato 7.40A.100)  |  
|            |  Mediant 4000 SBC |  Supportato 7.20A.258 (consigliato 7.40A.100)  |  
|            |  Mediant 1000B SBC | Supportato 7.20A.258 (consigliato 7.40A.100)  |  
|            |  Mediant 9000 SBC |  Supportato 7.20A.258 (consigliato 7.40A.100)  |  
|            |  Mediant Virtual Edition SBC |   Supportato 7.20A.258 (consigliato 7.40A.100)  |  
|            |  Mediant Cloud Edition SBC | Supportato 7.20A.258 (consigliato 7.40A.100)  |
| [Componente di base SBC della barra multifunzione](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  SBC 5110         | 8.2  |
|            |  SBC 5210         | 8.2  |
|            |  SBC 5400         | 8.2  |
|            |  SBC 7000         | 8.2  |
|            |  SBC SWe          | 8.2  |
| [ SBC Edge della barra multifunzione](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  SBC SWe Lite | 8.1.5 |
|               | SBC 1000 | 8.1.5  |
|               | SBC 2000 | 8.1.5  |
| [TE-SYSTEMS](https://www.anynode.de/local_media_optimization/) |  anynode          | 4.0.1+ |
| [Oracle](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | AP 1100 | 8.4.0.0.0 |
|        | AP 3900 | 8.4.0.0.0 |
|        | AP 4600 | 8.4.0.0.0 | 
|        | AP 6300 | 8.4.0.0.0 |
|        | AP 6350 | 8.4.0.0.0 | 
|        | VME     | 8.4.0.0.0 |




## <a name="direct-routing-and-analog-devices-interoperability"></a>Interoperabilità tra instradamento diretto e dispositivi analogici

Nella tabella seguente sono elencati i dispositivi verificati per l'interoperabilità tra instradamento diretto e dispositivi analogici.

|                                                       Fornitore                                                        |       Prodotto       | Verificato
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-1](https://www.audiocodes.com/media/2373/mp-1xx-and-mp-124-datasheet.pdf)   |     &#10004;     |
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-2](https://www.audiocodes.com/media/2399/mediapack-20x-mp-20x-analog-telephone-adapters-datasheet.pdf)   |     &#10004;     | 
| [Cisco](https://www.cisco.com/c/en/us/products/collateral/unified-communications/ata-190-series-analog-telephone-adapters/datasheet-c78-740013.html) |  Adattatore per telefono analogico multipiattaforma ATA 191 |     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |   Software AP1100 versione 8.3.0.1.2 |     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  Software AP3900 versione 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  Software AP4600 versione 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  Software AP6300 versione 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  Software AP6350 versione 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  Software VME versione 8.3.0.1.2 |     &#10004;     |
| [Ribbon](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 1000. Versione software: 8.1.1 (build 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [Ribbon](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 2000. Versione software: 8.1.1 (build 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [Ribbon](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 302. Versione software: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [Ribbon](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 304. Versione software: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [Ribbon](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 2900A. Versione software: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [Ribbon](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 4806. Versione software: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [Ribbon](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 4808. Versione software: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [Ribbon](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 6000. Versione software: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/) |  anynode con Grandstream GXW42xx (V1.0.7.10) |     &#10004;     |
  

La certificazione è concessa a una versione principale. Ciò significa che è supportato il firmware con qualsiasi numero nel firmware SBC che segue la versione principale.

Per inviare feedback su Teams, ad esempio idee su nuove funzionalità, vedere il [portale sui feedback Microsoft](https://feedbackportal.microsoft.com/).


