---
title: Visualizzazione sessione
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
description: Nella visualizzazione Session sono archiviate informazioni sulle sessioni per le quali sono presenti record nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 80a275e047934bd60586c344b5487f2593fe48bb
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834914"
---
# <a name="session-view"></a>Visualizzazione sessione
 
Nella visualizzazione Session sono archiviate informazioni sulle sessioni per le quali sono presenti record nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |Riferimento dalla tabella MediaLine.  <br/> |
|ConferenceURI  <br/> |nvarchar(450)  <br/> |URI conferenza nel caso di una conferenza oppure DialogID nel caso di una sessione peer-to-peer.  <br/> |
|Correlation  <br/> |varchar(max)  <br/> |ID correlazione della sessione.  <br/> |
|DialogCategory  <br/> |bit  <br/> |Categoria finestra di dialogo; 0 è Skype for Business Server a Mediation Server. 1 è il passaggio da Mediation Server a gateway PSTN.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Indica se la chiamata è stata ignorata o meno.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |Questo campo, se presente, indica il motivo per cui una chiamata non è stata ignorata anche in caso di corrispondenza degli ID bypass. Ad Skype for Business Server viene definito un solo valore:  <br/> 0x0001 - ID bypass sconosciuto per la scheda di rete predefinita  <br/> |
|StartTime  <br/> |datetime  <br/> |Ora di inizio della chiamata.  <br/> |
|EndTime  <br/> |datetime  <br/> |Ora di fine della chiamata.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |FQDN del pool del chiamante.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |FQDN del pool del destinatario chiamata.  <br/> |
|CallerPAI  <br/> |nvarchar(450)  <br/> |URI dell'identità con asserzione p del chiamante.  <br/> |
|CalleePAI  <br/> |nvarchar(450)  <br/> |URI dell'identità con asserzione p del chiamato.  <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Nome dell'endpoint del chiamante.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Nome dell'endpoint del chiamante.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Stringa agente utente del chiamante.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Tipo di agente utente del chiamante. Per informazioni [dettagliate, vedere](useragent.md) la tabella UserAgent. <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |Categoria dell'agente utente del chiamante. Per informazioni [dettagliate, vedere la tabella UserAgentDef (QoE).](useragentdef-qoe.md) <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Stringa agente utente del chiamato.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Tipo dell'agente utente per il destinatario chiamata. Per informazioni [dettagliate, vedere](useragent.md) la tabella UserAgent. <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |Categoria dell'agente utente per il destinatario chiamata. Per informazioni [dettagliate, vedere la tabella UserAgentDef (QoE).](useragentdef-qoe.md) <br/> |
|CallerURI  <br/> |nvarchar(450)  <br/> |URI del chiamante.  <br/> |
|CalleeURI  <br/> |nvarchar(450)  <br/> |URI del chiamato.  <br/> |
|CallPrioirty  <br/> |int  <br/> |Priorità della chiamata.  <br/> |
   

