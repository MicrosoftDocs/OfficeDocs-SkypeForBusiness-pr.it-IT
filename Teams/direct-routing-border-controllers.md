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
description: Partner Microsoft con fornitori di SBC selezionati per certificare il lavoro di SBCs con il routing diretto.
ms.openlocfilehash: 529b0b550d60123a94b36944e8f1831acb09839a
ms.sourcegitcommit: dc240b123efb03d5ab0545d650a973bf60d04506
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2019
ms.locfileid: "40069427"
---
# <a name="list-of-session-border-controllers-certified-for-direct-routing"></a>Elenco di Session Border Controller certificati per Instradamento diretto

Partner Microsoft con i fornitori SBC (Session Border Controller) selezionati per certificare che il proprio SBCs funziona con il routing diretto. 

Con ogni fornitore, Microsoft: 

- Funziona in collaborazione con i fornitori SBC nei protocolli di interconnessione SIP.
- Esegue test intensi tramite un laboratorio di terze parti; solo i dispositivi che hanno superato i test sono certificati. 
- Esegue test giornalieri con tutti i dispositivi certificati negli ambienti di produzione e di pre-produzione. La convalida dei dispositivi in ambienti di pre-produzione garantisce che le nuove versioni del codice di routing diretto nel cloud funzioneranno con i SBCs certificati. 
- Ha un processo di supporto congiunto con i fornitori SBC.


  > [!NOTE]
  > Microsoft supporta solo il sistema telefonico se un dispositivo o dispositivi certificati sono connessi tramite routing diretto. Microsoft si riserva il diritto di rifiutare i casi di supporto in cui un dispositivo non certificato è connesso al sistema telefonico tramite routing diretto. 

La tabella seguente elenca i dispositivi certificati per il routing diretto. 

Leggi [altre informazioni sul routing diretto](https://aka.ms/dr). In caso di domande sul programma di certificazione SBC per l'instradamento diretto, inviare un messaggio di posta elettronica a drsbccertification@microsoft.com


|                                                       Fornitore                                                        |       Prodotto       | Bypass non multimediale | Bypass multimediale | Versione software | Vaidated con provider E911 | In grado di ELIN
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|--------------|------------------|-----------------|------------------|
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   SBC 500 medium   |     &#10004;     |   &#10004;    |  7.20 a. 250   |
|                                                                                                                     |   SBC 800 Medium   |     &#10004;     |   &#10004;     |  7.20 a. 250   |    |    |
|                                                                                                                     |  SBC 2600 medium   |     &#10004;     |   &#10004;    |  7.20 a. 250   |     |    |    
|                                                                                                                     |  SBC 4000 medium   |     &#10004;     |   &#10004;     |  7.20 a. 250   |     |    |    
|                                                                                                                     | SBC 1000B medium  |     &#10004;     |   In sospeso     |  7.20 a. 250  |    |    |    
|                                                                                                                     | SBC 9000 medium  |     &#10004;     |   &#10004;     |  7.20 a. 250   |    |    |                                                                       
|                                                                                                                     | SBC Edition virtuale |     &#10004;     |   &#10004;     |  7.20 a. 250 |    |    |    
|  [Comunicazioni della barra multifunzione](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5110       |     &#10004;     |   &#10004;    |       V 6.2       |  Intrado ERS <br>Intrado EGW |   No |    
|                                                                                                                     |      SBC 5210       |     &#10004;     |  &#10004;    |       V 6.2       |   Intrado ERS <br>Intrado EGW  | No   |    
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       V 6.2       |  Intrado ERS <br>Intrado EGW    |No|    
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       V 6.2       |   Intrado ERS <br>Intrado EGW  |  No  |    
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       V 6.2       |   Intrado ERS <br>Intrado EGW |   No |    
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      v 8.0.1     |     |    |    
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     v 8.0.1     |    |    |    
|                                                                                                                     |    SBC SWe Lite     |     &#10004;     |  &#10004;    |      v 8.0.1    |     |    |    
|                     [Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    Think 365 SBC    |     &#10004;     |   In sospeso    |       V 1.4       |     |    |    
|                     [Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |    |    |    
|                                                                                                                    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  |    |    |    
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |   |    |    
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |   |    |    
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |        |    |                                            
|                                                                                                                    |      VME           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |    |    |    
|                     [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      v 3.16.2      |     |    |    

Per darci feedback sui prodotti sui team, ad esempio idee per le nuove caratteristiche, visita [UserVoice](https://microsoftteams.uservoice.com) nota la certificazione concessa a una versione principale. Ciò significa che il firmware con qualsiasi numero nel firmware SBC successivo alla versione principale è supportato.
