---
title: Tabella IMReportSummary in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: IMReportSummaryTable fornisce un report globale sulle sessioni di messaggistica istantanea svolte in un'organizzazione. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 647b8dc3e48e56d126a65f524de90954b7aeca8f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194790"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>Tabella IMReportSummary in Skype for Business Server 2015
 
IMReportSummaryTable fornisce un report globale sulle sessioni di messaggistica istantanea svolte in un'organizzazione. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**StartTime** <br/> |DateTime  <br/> |Principale  <br/> |Data e ora di inizio della sessione di messaggistica istantanea.  <br/> |
|**TimePeriod** <br/> |carattere (1)  <br/> |Principale  <br/> ||
|**PoolFQDN** <br/> |nvarchar (257)  <br/> |Principale  <br/> |Nome di dominio completo del pool che ospita la sessione.  <br/> |
|**AuthType** <br/> |int  <br/> |Principale  <br/> |Priorità, ad esempio urgente o non urgente, della chiamata. Le informazioni prioritarie sono archiviate nella [Tabella CallPriorities in Skype for Business Server 2015](callpriorities.md).  <br/> |
|**SessionCount** <br/> |bigint  <br/> |||
|**MsgCount** <br/> |bigint  <br/> ||Numero totale di messaggi istantanei scambiati durante la sessione.  <br/> |
   

