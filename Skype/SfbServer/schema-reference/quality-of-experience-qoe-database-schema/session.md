---
title: Tabella session
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: Ogni record rappresenta una sessione che include audio o audio e video. Contiene informazioni generali sulla sessione. Una sessione è definita come una finestra di dialogo SIP (Session Initiation Protocol) audio o video tra due endpoint.
ms.openlocfilehash: bc81bb3c67f91b975643929170354c7b152d2237
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768324"
---
# <a name="session-table"></a>Tabella session
 
Ogni record rappresenta una sessione che include audio o audio e video. Contiene informazioni generali sulla sessione. Una sessione è definita come una finestra di dialogo SIP (Session Initiation Protocol) audio o video tra due endpoint.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Principale  <br/> |Riferimento dalla [tabella Dialog](dialog.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principale  <br/> |Riferimento dalla [tabella Dialog](dialog.md).  <br/> |
|**ConferenceKey** <br/> |int  <br/> |Foreign  <br/> |Tasto conferenza. Riferimento dalla [tabella Conferenze](conference.md).  <br/> |
|**CorrelationKey** <br/> |int  <br/> |Foreign  <br/> |Chiave di correlazione. Riferimento dalla [tabella SessionCorrelation](sessioncorrelation.md).  <br/> |
|**DialogCategory** <br/> |bit  <br/> | <br/> |Categoria finestra di dialogo; 0 è Skype for Business Server a Mediation Server. 1 è il passaggio da Mediation Server a gateway PSTN.  <br/> |
|**MediationServerBypassFlag** <br/> |bit  <br/> ||Flag che indica se la chiamata è stata o meno ignorata.  <br/> |
|**MediaBypassWarningFlag** <br/> |int  <br/> ||Questo campo, se presente, indica il motivo per cui una chiamata non è stata ignorata anche in caso di corrispondenza degli ID bypass. Ad Skype for Business Server viene definito un solo valore.  <br/> 0x0001 - ID bypass sconosciuto per la scheda di rete predefinita.  <br/> |
|**StartTime** <br/> |datetime  <br/> | <br/> |Ora di inizio della chiamata.  <br/> |
|**EndTime** <br/> |datetime  <br/> | <br/> |Ora di fine della chiamata.  <br/> |
|**CallerPool** <br/> |int  <br/> |Foreign  <br/> |Pool del chiamante. Riferimento dalla [tabella Pool](pool.md).  <br/> |
|**CalleePool** <br/> |int  <br/> |Foreign  <br/> |Pool del destinatario della chiamata. Riferimento dalla [tabella Pool](pool.md).  <br/> |
|**CalleePAI** <br/> |int  <br/> |Foreign  <br/> |URI SIP nell'identità p-asserted SIP (PAI) dell'endpoint di ricezione. Riferimento dalla [tabella User](user-0.md).  <br/> |
|**CallerURI** <br/> |int  <br/> |Foreign  <br/> |URI del chiamante. Riferimento dalla [tabella User](user-0.md).  <br/> |
|**CallerEndpoint** <br/> |int  <br/> |Foreign  <br/> |Endpoint del chiamante. Riferimento dalla [tabella Endpoint](endpoint.md).  <br/> |
|**CallerUserAgent** <br/> |bit  <br/> |Foreign  <br/> |Agente utente del chiamante. Riferimento dalla [tabella UserAgent](useragent.md).  <br/> |
|**CallPriority** <br/> |smallint  <br/> ||Priorità di questa chiamata.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Questa colonna è deprecata e non viene utilizzata in Skype for Business Server. Al contrario, queste informazioni vengono riportate in base a una linea di base multimediale. Per ulteriori informazioni, fare riferimento alla tabella [MediaLine.](medialine-0.md) <br/> |
|**CallerPAI** <br/> |int  <br/> |Foreign  <br/> |P-Asserted-Identity dell'utente che ha effettuato la chiamata. L'identità P-Asserted-Identity (PAI) viene utilizzata per comunicare la vera identità dell'utente che ha effettuato la chiamata.  <br/> |
|**CalleeEndpoint** <br/> |int  <br/> |Foreign  <br/> |Endpoint che ha ricevuto la chiamata.  <br/> |
|**CalleeUserAgent** <br/> |int  <br/> |Foreign  <br/> |Agente utente impiegato dall'utente che ha ricevuto la chiamata. Gli agenti utente rappresentano il dispositivo endpoint client.  <br/> |
|**CalleeUri** <br/> |int  <br/> |Foreign  <br/> |URI SIP dell'utente che ha ricevuto la chiamata.  <br/> |
   

