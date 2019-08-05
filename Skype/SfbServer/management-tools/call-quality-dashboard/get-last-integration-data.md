---
title: Ottenere gli ultimi dati di integrazione
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e7967dd9-0d6a-4a80-8b59-b8fc2e5615f8
description: "Riepilogo: informazioni su come ottenere l'ultima operazione di integrazione dei dati, che fa parte dell'API dati per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: d110bdc1fe88a9fe7f77abe7f7b9ed47a3324eb0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186917"
---
# <a name="get-last-integration-data"></a>Ottenere gli ultimi dati di integrazione
 
**Riepilogo:** Informazioni sull'operazione Get last Integration data, che fa parte dell'API dati per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server.
  
L'operazione Get last Integration data fa parte dell'API Data per il dashboard della qualità delle chiamate.
  
## <a name="get-last-integration-data"></a>Ottenere gli ultimi dati di integrazione

Ottenere l'ultima operazione di integrazione dei dati restituisce l'elenco degli ultimi 5 successo/errore dell'archiviazione e dell'elaborazione dei cubi.
  
Questa caratteristica è disabilitata per impostazione predefinita e deve essere abilitata configurando l'API dati.
  

|**Metodo**|**URI di richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|Ottieni  <br/> |/QoEDataService/IntegrationLog/status\<portale\>https://  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI** -None.
  
 **Richiedi intestazioni** -nessuna intestazione aggiuntiva.
  
 **Richiedi corpo** -nessuno.
  
 **Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
 **Codice di stato** : un'operazione riuscita restituisce il codice di stato 200 (OK).
  
 **Intestazioni di risposta** -nessuna intestazione aggiuntiva.
  
 **Corpo risposta** : di seguito è riportato un esempio di stato del log.
  
```
{
"LastSuccessIntegrations": ["01/18/2015 10:30:13",
"01/18/2015 10:28:29",
"01/17/2015 15:15:17",
"01/17/2015 15:00:17",
"01/17/2015 14:45:13"],
"LastSuccessCubeProcessings": ["01/17/2015 15:16:40",
"01/17/2015 15:01:41",
"01/17/2015 14:47:19",
"01/17/2015 14:31:40",
"01/17/2015 14:17:01"],
"LastFailedIntegrations":  ,
"LastFailedCubeProcessings": ["01/18/2015 10:30:58",
"01/18/2015 10:29:28",
"01/17/2015 10:02:20",
"01/15/2015 20:01:56",
"01/15/2015 19:45:50"],
"LastDataIntegrationStart": null,
"LastCubeProcessingStart": "01/18/2015 10:30:16"
}
```
