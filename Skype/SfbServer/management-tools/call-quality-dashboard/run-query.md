---
title: Run Query
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: "Riepilogo: informazioni sull'operazione di esecuzione di query, che fa parte dell'API dei dati per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: bff24ca5a4d651ba276b4b0d795afabce3c6d0dd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803116"
---
# <a name="run-query"></a>Run Query

**Riepilogo:** Informazioni sull'operazione di esecuzione di query, che fa parte dell'API dei dati per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server.

L'operazione di esecuzione query fa parte dell'API Data per il dashboard qualità chiamata.

## <a name="run-query"></a>Run Query

L'operazione Esegui query consente di eseguire una query sul cubo in base alle dimensioni, alle misure e ai filtri specificati e di restituire i dati.


|**Metodo**|**URI della richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|POST  <br/> |https:// \<portal\> /QoEDataService/RunQuery  <br/> |HTTP/1.1  <br/> |

 **Parametri URI** -None.

 **Intestazioni richieste** -nessuna intestazione aggiuntiva.

 **Corpo richiesta** : questo è un payload di richiesta di esempio in JSON. Contiene dimensioni, filtri e misura necessari per una query.

```json
{
"Filters": [{
"DataModelName": "[StartDate].[Month]",
"Caption": "July 2013",
"Value": "[2015-03-01T00:00:00]",
"Operand": 0,
"UnionGroup": ""
}],
"Dimensions": [{
"DataModelName": "[StartDate].[Month]"
}],
"Measurements": [{
"DataModelName": "[Measures].[Audio Good Streams Count]"
},
{
"DataModelName": "[Measures].[Audio UnClassified Streams Count]"
},
{
"DataModelName": "[Measures].[Audio Poor Streams Count]"
},
{
"DataModelName": "[Measures].[AudioPoorPercentage]"
}],
"Trend": {
"EnableTrend": true,
"SpanCount": 7,
"TrendDate": "2015-3",
"Type": 0
}
}
```

 *Filtri*  : un elenco di espressioni di filtro da applicare in modo che il set di dati risultante rifletta solo il sottoinsieme dei dati di interesse.

 *Dimensions*  -elenco delle dimensioni che verranno utilizzate per l'aggregazione dei dati. È richiesta almeno una dimensione, ma è possibile specificare più dimensioni per ottenere un livello aggiuntivo di sottoaggregazioni.

 *Misure*  : un elenco di misure, note anche come fact, che sono le metriche desiderate da aggregare in base alle dimensioni specificate.

 *Trend*  -ulteriori istruzioni di controllo per personalizzare i dati dei risultati.

 **Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.

 **Codice di stato** -un'operazione completata restituisce il codice di stato 200 (OK).

 **Intestazioni di risposta** -Nessun intestazioni aggiuntive.

 **Corpo di risposta** -di seguito è riportato un payload di risposta di esempio in JSON. Contiene una tabella di dati contenente i dati, che conterrà anche un meta dati, che Visualizza il tempo di esecuzione delle query e se i dati vengono o meno dalla cache.

```json
{
"ExecutionTime": "00:00:00.2102630",
"DataResult": [["September 2014",
        1792,
        34,
        78,
        4.171],
        ["October 2014",
        37017,
        1731,
        3305,
        8.197],
        ["November 2014",
        79184,
        3033,
        5556,
        6.557],
        ["December 2014",
        122253,
        4050,
        5444,
        4.263],
        ["January 2015",
        31246,
        1069,
        1342,
        4.118]],
"ResultIsFromCache": false,
"ErrorType": 0
}
```

 *Tempo di esecuzione*  : il tempo totale impiegato dal server per restituire i dati. Questo può o non può implicare la cache.

 *Risultato dei dati*  -il risultato della query. Si tratta di una matrice bidimensionale contenente tutte le permutazioni dei membri delle dimensioni e di ogni elemento contenente i nomi dei membri delle dimensioni, nonché i valori aggregati delle misure specificate.

 Il *risultato è dalla cache* per la diagnostica. Indica se il risultato è stato ottenuto dalla cache o dal cubo QoE.
