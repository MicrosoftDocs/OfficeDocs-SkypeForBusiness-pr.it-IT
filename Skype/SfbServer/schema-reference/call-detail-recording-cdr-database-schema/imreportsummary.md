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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: IMReportSummaryTable fornisce un report globale sulle sessioni di messaggistica istantanea svolte in un'organizzazione. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: f845a882bb8bd6ba5ca434ffc42a34725cfeac51
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815144"
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
   

