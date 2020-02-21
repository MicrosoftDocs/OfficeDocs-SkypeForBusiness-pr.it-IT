---
title: Elenco di Session Border Controller certificati per Instradamento diretto
ms.author: crowe
ms.reviewer: NMuravlyannikov
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
description: Partner Microsoft con fornitori di SBC selezionati per certificare il lavoro di SBCs con il routing diretto.
ms.openlocfilehash: 3e442a2afd61c3d5c39ac8edc89fa128131ac468
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214412"
---
# <a name="list-of-session-border-controllers-certified-for-direct-routing"></a>Elenco di Session Border Controller certificati per Instradamento diretto

Partner Microsoft con i fornitori SBC (Session Border Controller) selezionati per certificare che il proprio SBCs funziona con il routing diretto. 

Microsoft collabora con ogni fornitore per: 

- Lavorare in collaborazione con i protocolli di interconnessione SIP.
- Eseguire test intensi usando un laboratorio di terze parti. Solo i dispositivi che superano i test sono certificati. 
- Eseguire test giornalieri con tutti i dispositivi certificati negli ambienti di produzione e di pre-produzione. La convalida dei dispositivi in ambienti di pre-produzione garantisce che le nuove versioni del codice di routing diretto nel cloud funzioneranno con i SBCs certificati. 
- Creare un processo di supporto congiunto con i fornitori SBC.


  > [!NOTE]
  > Microsoft supporta solo il sistema telefonico se un dispositivo o dispositivi certificati sono connessi tramite routing diretto. Microsoft si riserva il diritto di rifiutare i casi di supporto in cui un dispositivo non certificato è connesso al sistema telefonico tramite routing diretto. 

La tabella seguente elenca i dispositivi certificati per il routing diretto. 

Leggi [altre informazioni sul routing diretto](https://aka.ms/dr). In caso di domande sul programma di certificazione SBC per il routing diretto, contattare drsbccertification@microsoft.com.


|                                                       Fornitore                                                        |       Prodotto       | Bypass non multimediale | Bypass multimediale | Versione software | Convalidati con i provider di E911 | In grado di ELIN
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|--------------|------------------|-----------------|------------------|
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   SBC 500 medium   |     &#10004;     |   &#10004;    |  7.20 a. 250   |
|                                                                                                                     |   SBC 800 Medium   |     &#10004;     |   &#10004;     |  7.20 a. 250   |    |    |
|                                                                                                                     |  SBC 2600 medium   |     &#10004;     |   &#10004;    |  7.20 a. 250   |     |    |    
|                                                                                                                     |  SBC 4000 medium   |     &#10004;     |   &#10004;     |  7.20 a. 250   |     |    |    
|                                                                                                                     | SBC 1000B medium  |     &#10004;     |   In sospeso     |  7.20 a. 250  |    |    |    
|                                                                                                                     | SBC 9000 medium  |     &#10004;     |   &#10004;     |  7.20 a. 250   |    |    |                                                                       
|                                                                                                                     | SBC Edition virtuale |     &#10004;     |   &#10004;     |  7.20 a. 250 |    |    |    
|  [Comunicazioni della barra multifunzione](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5110       |     &#10004;     |   &#10004;    |       V 7.2       | <ul> <li>Intrado ERS </li> <li>Intrado EGW</li> <li> Mobilità Horizon per Sky rossa </li> </ul> |   No |    
|                                                                                                                     |      SBC 5210       |     &#10004;     |  &#10004;    |       V 7.2       |  <ul> <li>Intrado ERS </li> <li>Intrado EGW</li> <li> Mobilità Horizon per Sky rossa </li> </ul> | No   |    
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       V 7.2       |  <ul> <li>Intrado ERS </li> <li>Intrado EGW</li> <li> Mobilità Horizon per Sky rossa </li> </ul>  |No|    
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       V 7.2       |   <ul> <li>Intrado ERS </li> <li>Intrado EGW</li> <li> Mobilità Horizon per Sky rossa </li> </ul> |  No  |    
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       V 7.2       |   <ul> <li>Intrado ERS </li> <li>Intrado EGW</li> <li> Mobilità Horizon per Sky rossa </li> </ul> |   No |    
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      v 8.0.3 (Build 537)     |  <ul> <li> Intrado ERS </li> <li>Intrado EGW </li> </ul>   |         |    
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     v 8.0.3 (Build 537)     |  <ul> <li> Intrado ERS </li> <li>Intrado EGW </li> </ul>   |           |    
|                                                                                                                     |    SBC SWe Lite     |     &#10004;     |  &#10004;    |      v 8.0.3 (Build 216)    |  <ul> <li> Intrado ERS </li> <li>Intrado EGW </li> </ul>    |           |    
|                     [Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    Think 365 SBC    |     &#10004;     |           |       V 1.4       |     |    |    
|                     [Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |   <ul> <li> Intrado ERS </li> <li>Intrado EGW </li> </ul>   |    |    
|                                                                                                                    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  |  <ul> <li> Intrado ERS </li> <li>Intrado EGW </li> </ul>  |    |    
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |   <ul> <li> Intrado ERS </li> <li>Intrado EGW </li> </ul>  |    |    
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  <ul> <li> Intrado ERS </li> <li>Intrado EGW </li> </ul>   |    |    
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |   <ul> <li> Intrado ERS </li> <li>Intrado EGW </li> </ul>  |    |                                            
|                                                                                                                    |      VME           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |   <ul> <li> Intrado ERS </li> <li>Intrado EGW </li> </ul>   |    |    
|                     [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      v 3.16.2      |     |    |    

La tabella seguente elenca i dispositivi verificati per l'interoperabilità tra il routing diretto e i dispositivi analogici.

|                                                       Fornitore                                                        |       Prodotto       | Verificato
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-1](https://www.audiocodes.com/media/2373/mp-1xx-and-mp-124-datasheet.pdf)   |     &#10004;     |

Per darci feedback sui prodotti sui team, ad esempio le idee per le nuove funzionalità, Vedi [UserVoice](https://microsoftteams.uservoice.com) nota la certificazione concessa a una versione principale. Ciò significa che il firmware con qualsiasi numero nel firmware SBC successivo alla versione principale è supportato.
