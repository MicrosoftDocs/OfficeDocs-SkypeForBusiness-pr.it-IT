---
title: Tabella Session
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: Ogni record rappresenta una sessione che include audio o audio e video. Contiene informazioni generali sulla sessione. Una sessione viene definita come una finestra di dialogo SIP (Session Initiation Protocol) audio o video tra due endpoint.
ms.openlocfilehash: e0cd6a4523b09d8bcb7f74d6c796b46bf99ece8e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194577"
---
# <a name="session-table"></a>Tabella Session
 
Ogni record rappresenta una sessione che include audio o audio e video. Contiene informazioni generali sulla sessione. Una sessione viene definita come una finestra di dialogo SIP (Session Initiation Protocol) audio o video tra due endpoint.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateTime  <br/> |Principale  <br/> |A cui si fa riferimento dalla [tabella della finestra di dialogo](dialog.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principale  <br/> |A cui si fa riferimento dalla [tabella della finestra di dialogo](dialog.md).  <br/> |
|**ConferenceKey** <br/> |int  <br/> |Esterna  <br/> |Tasto Conferenza. A cui si fa riferimento dalla [tabella conferenze](conference.md).  <br/> |
|**CorrelationKey** <br/> |int  <br/> |Esterna  <br/> |Chiave di correlazione. A cui si fa riferimento dalla [tabella SessionCorrelation](sessioncorrelation.md).  <br/> |
|**DialogCategory** <br/> |po'  <br/> | <br/> |Categoria finestra di dialogo; 0 è Skype for Business Server to Mediation Server Leg; 1 è Mediation Server per la gamba del gateway PSTN.  <br/> |
|**MediationServerBypassFlag** <br/> |po'  <br/> ||Contrassegno che indica se la chiamata è stata ignorata o meno.  <br/> |
|**MediaBypassWarningFlag** <br/> |int  <br/> ||Questo campo, se presente, indica perché una chiamata non è stata ignorata anche se gli ID di bypass corrispondono. Per Skype for Business Server, viene definito un solo valore.  <br/> 0x0001-ID di bypass sconosciuto per la scheda di rete predefinita.  <br/> |
|**StartTime** <br/> |DateTime  <br/> | <br/> |Chiama ora di inizio.  <br/> |
|**EndTime** <br/> |DateTime  <br/> | <br/> |Ora di fine chiamata.  <br/> |
|**CallerPool** <br/> |int  <br/> |Esterna  <br/> |Pool del chiamante. A cui si fa riferimento dalla [tabella pool](pool.md).  <br/> |
|**CalleePool** <br/> |int  <br/> |Esterna  <br/> |Pool del destinatario della chiamata. A cui si fa riferimento dalla [tabella pool](pool.md).  <br/> |
|**CalleePAI** <br/> |int  <br/> |Esterna  <br/> |URI SIP nell'identità con asserzione p (PAI) SIP dell'endpoint di destinazione. A cui si fa riferimento dalla [tabella utente](user-0.md).  <br/> |
|**CallerURI** <br/> |int  <br/> |Esterna  <br/> |URI del chiamante. A cui si fa riferimento dalla [tabella utente](user-0.md).  <br/> |
|**CallerEndpoint** <br/> |int  <br/> |Esterna  <br/> |Endpoint del chiamante. A cui si fa riferimento dalla [tabella endpoint](endpoint.md).  <br/> |
|**CallerUserAgent** <br/> |po'  <br/> |Esterna  <br/> |Agente utente del chiamante. A cui si fa riferimento dalla [tabella UserAgent](useragent.md).  <br/> |
|**CallPriority** <br/> |smallint  <br/> ||Priorità di questa chiamata.  <br/> |
|**ClassifiedPoorCall** <br/> |po'  <br/> ||Questa colonna è stata deprecata e non viene usata in Skype for Business Server. Queste informazioni vengono invece segnalate in base a una riga per media. Per altre informazioni, vedere la [Tabella MediaLine](medialine-0.md) . <br/> |
|**CallerPAI** <br/> |int  <br/> |Esterna  <br/> |P-asserzione-identità dell'utente che ha effettuato la chiamata. Il P-Asserted-Identity (PAI) viene usato per comunicare l'identità effettiva dell'utente che ha effettuato la chiamata.  <br/> |
|**CalleeEndpoint** <br/> |int  <br/> |Esterna  <br/> |Endpoint che ha ricevuto la chiamata.  <br/> |
|**CalleeUserAgent** <br/> |int  <br/> |Esterna  <br/> |Agente utente impiegato dall'utente che ha ricevuto la chiamata. Gli agenti utente rappresentano il dispositivo endpoint client.  <br/> |
|**CalleeUri** <br/> |int  <br/> |Esterna  <br/> |URI SIP dell'utente che ha ricevuto la chiamata.  <br/> |
   

