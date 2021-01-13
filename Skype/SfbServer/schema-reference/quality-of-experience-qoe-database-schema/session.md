---
title: Tabella Session
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: Ogni record rappresenta una sessione che coinvolge audio o audio e video. Contiene informazioni generali sulla sessione. Una sessione è definita come una finestra di dialogo SIP (Session Initiation Protocol) audio o video tra due endpoint.
ms.openlocfilehash: cdf639e7360248e02378c66eb68a60d49acb9749
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802676"
---
# <a name="session-table"></a>Tabella Session
 
Ogni record rappresenta una sessione che coinvolge audio o audio e video. Contiene informazioni generali sulla sessione. Una sessione è definita come una finestra di dialogo SIP (Session Initiation Protocol) audio o video tra due endpoint.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Principale  <br/> |A cui viene fatto riferimento dalla [tabella delle finestre di dialogo](dialog.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principale  <br/> |A cui viene fatto riferimento dalla [tabella delle finestre di dialogo](dialog.md).  <br/> |
|**ConferenceKey** <br/> |int  <br/> |Stranieri  <br/> |Chiave di conferenza. A cui viene fatto riferimento dalla [tabella conferenze](conference.md).  <br/> |
|**CorrelationKey** <br/> |int  <br/> |Stranieri  <br/> |Chiave di correlazione. Riferimento dalla [tabella SessionCorrelation](sessioncorrelation.md).  <br/> |
|**DialogCategory** <br/> |po'  <br/> | <br/> |Categoria della finestra di dialogo; 0 è Skype for Business Server to Mediation Server Leg; 1 è Mediation Server per la gamba del gateway PSTN.  <br/> |
|**MediationServerBypassFlag** <br/> |po'  <br/> ||Flag che indica se la chiamata è stata o meno ignorata.  <br/> |
|**MediaBypassWarningFlag** <br/> |int  <br/> ||Questo campo, se presente, indica il motivo per cui una chiamata non è stata ignorata anche in caso di corrispondenza degli ID bypass. Per Skype for Business Server, viene definito un solo valore.  <br/> 0x0001-ID bypass sconosciuto per la scheda di rete predefinita.  <br/> |
|**StartTime** <br/> |datetime  <br/> | <br/> |Ora di inizio della chiamata.  <br/> |
|**EndTime** <br/> |datetime  <br/> | <br/> |Ora di fine della chiamata.  <br/> |
|**CallerPool** <br/> |int  <br/> |Stranieri  <br/> |Il pool del chiamante. A cui viene fatto riferimento dalla [tabella del pool](pool.md).  <br/> |
|**CalleePool** <br/> |int  <br/> |Stranieri  <br/> |Il pool del destinatario della chiamata. A cui viene fatto riferimento dalla [tabella del pool](pool.md).  <br/> |
|**CalleePAI** <br/> |int  <br/> |Stranieri  <br/> |URI SIP nell'identità p-Asserted SIP (PAI) dell'endpoint di ricezione. A cui viene fatto riferimento dalla [tabella user](user-0.md).  <br/> |
|**CallerURI** <br/> |int  <br/> |Stranieri  <br/> |URI del chiamante. A cui viene fatto riferimento dalla [tabella user](user-0.md).  <br/> |
|**CallerEndpoint** <br/> |int  <br/> |Stranieri  <br/> |Endpoint del chiamante. A cui viene fatto riferimento dalla [tabella endpoint](endpoint.md).  <br/> |
|**CallerUserAgent** <br/> |po'  <br/> |Stranieri  <br/> |Agente utente del chiamante. A cui viene fatto riferimento dalla [tabella UserAgent](useragent.md).  <br/> |
|**CallPriority** <br/> |smallint  <br/> ||Priorità della chiamata.  <br/> |
|**ClassifiedPoorCall** <br/> |po'  <br/> ||Questa colonna è obsoleta e non viene utilizzata in Skype for Business Server. Invece, queste informazioni vengono riportate in base alle linee per i media. Per ulteriori informazioni, fare riferimento alla [Tabella MediaLine](medialine-0.md) . <br/> |
|**CallerPAI** <br/> |int  <br/> |Stranieri  <br/> |P-Asserted-Identity dell'utente che ha effettuato la chiamata. L'identità P-Asserted-Identity (PAI) viene utilizzata per trasmettere la vera identità dell'utente che ha effettuato la chiamata.  <br/> |
|**CalleeEndpoint** <br/> |int  <br/> |Stranieri  <br/> |Endpoint che ha ricevuto la chiamata.  <br/> |
|**CalleeUserAgent** <br/> |int  <br/> |Stranieri  <br/> |Agente utente impiegato dall'utente che ha ricevuto la chiamata. Gli agenti utente rappresentano il dispositivo endpoint client.  <br/> |
|**CalleeUri** <br/> |int  <br/> |Stranieri  <br/> |URI SIP dell'utente che ha ricevuto la chiamata.  <br/> |
   

