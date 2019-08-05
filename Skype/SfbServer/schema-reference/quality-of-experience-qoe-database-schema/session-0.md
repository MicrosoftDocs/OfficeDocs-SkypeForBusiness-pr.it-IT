---
title: Visualizzazione sessione
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
description: La visualizzazione sessione archivia le informazioni sulle sessioni che hanno record nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: b24afdff32b5223725aa4f8ff0b7d875199713c7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194582"
---
# <a name="session-view"></a>Visualizzazione sessione
 
La visualizzazione sessione archivia le informazioni sulle sessioni che hanno record nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |DateTime  <br/> |A cui si fa riferimento dalla Tabella MediaLine.  <br/> |
|ConferenceURI  <br/> |nvarchar (450)  <br/> |URI conferenza se si tratta di una conferenza o di DialogID se si tratta di una sessione peer-to-peer.  <br/> |
|Correlazione  <br/> |varchar (max)  <br/> |ID correlazione della sessione.  <br/> |
|DialogCategory  <br/> |po'  <br/> |Categoria finestra di dialogo; 0 è Skype for Business Server to Mediation Server Leg; 1 è Mediation Server per la gamba del gateway PSTN.  <br/> |
|MediationServerBypassFlag  <br/> |po'  <br/> |Indica se la chiamata è stata ignorata o meno.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |Questo campo, se presente, indica perché una chiamata non è stata ignorata anche se gli ID di bypass corrispondono. Per Skype for Business Server è definito un solo valore:  <br/> 0x0001-ID bypass sconosciuto per la scheda di rete predefinita  <br/> |
|StartTime  <br/> |DateTime  <br/> |Chiama ora di inizio.  <br/> |
|EndTime  <br/> |DateTime  <br/> |Ora di fine chiamata.  <br/> |
|CallerPool  <br/> |nvarchar (256)  <br/> |FQDN del pool chiamante.  <br/> |
|CalleePool  <br/> |nvarchar (256)  <br/> |Nome di dominio completo del pool di chiamate.  <br/> |
|CallerPAI  <br/> |nvarchar (450)  <br/> |URI di identità p-asserito dal chiamante.  <br/> |
|CalleePAI  <br/> |nvarchar (450)  <br/> |URI di identità p-Asserted del chiamato.  <br/> |
|CallerEndpoint  <br/> |nvarchar (256)  <br/> |Nome dell'endpoint del chiamante.  <br/> |
|CalleeEndpoint  <br/> |nvarchar (256)  <br/> |Nome dell'endpoint del chiamante.  <br/> |
|CallerUserAgent  <br/> |nvarchar (256)  <br/> |Stringa agente utente del chiamante.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Tipo di agente utente del chiamante. Per informazioni dettagliate, vedere la [tabella UserAgent](useragent.md) . <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |Categoria dell'agente utente del chiamante. Per informazioni dettagliate, vedere la [Tabella UserAgentDef (QoE)](useragentdef-qoe.md) . <br/> |
|CalleeUserAgent  <br/> |nvarchar (256)  <br/> |Stringa agente utente del chiamato.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Tipo di agente utente per il chiamato. Per informazioni dettagliate, vedere la [tabella UserAgent](useragent.md) . <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |Categoria agente utente per il chiamato. Per informazioni dettagliate, vedere la [Tabella UserAgentDef (QoE)](useragentdef-qoe.md) . <br/> |
|CallerURI  <br/> |nvarchar (450)  <br/> |URI del chiamante.  <br/> |
|CalleeURI  <br/> |nvarchar (450)  <br/> |URI del chiamato.  <br/> |
|CallPrioirty  <br/> |int  <br/> |Priorità della chiamata.  <br/> |
   

