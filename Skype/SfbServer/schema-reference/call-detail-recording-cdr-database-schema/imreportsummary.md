---
title: Tabella IMReportSummary in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: La tabella IMReportSummaryTable offre un rapporto complessivo sulle sessioni di messaggistica istantanea eseguite in un'organizzazione. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 6a80918376440c13d60e059744d88c09c2705853
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821526"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>Tabella IMReportSummary in Skype for Business Server
 
La tabella IMReportSummaryTable offre un rapporto complessivo sulle sessioni di messaggistica istantanea eseguite in un'organizzazione. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**StartTime** <br/> |datetime  <br/> |Principale  <br/> |Data e ora di inizio della sessione di messaggistica istantanea.  <br/> |
|**TimePeriod** <br/> |char(1)  <br/> |Principale  <br/> ||
|**PoolFQDN** <br/> |nvarchar(257)  <br/> |Principale  <br/> |Nome di dominio completo del pool che ospita la sessione.  <br/> |
|**AuthType** <br/> |int  <br/> |Principale  <br/> |Priorità della chiamata, ad esempio urgente o non urgente. Le informazioni sulla priorità vengono archiviate nella [tabella CallPriorities in Skype for Business Server 2015.](callpriorities.md)  <br/> |
|**SessionCount** <br/> |bigint  <br/> |||
|**MsgCount** <br/> |bigint  <br/> ||Numero totale di messaggi istantanei scambiati durante la sessione.  <br/> |
   

