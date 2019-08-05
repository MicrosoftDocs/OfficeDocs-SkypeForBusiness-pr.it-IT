---
title: Esegui query
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: "Riepilogo: informazioni sull'operazione Esegui query, che fa parte dell'API dati per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 0b4c44c93009e014579a53872de82297c1486573
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186869"
---
# <a name="run-query"></a>Esegui query

**Riepilogo:** Informazioni sull'operazione Esegui query, che fa parte dell'API dati per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server.

L'operazione Esegui query fa parte dell'API dati per il dashboard della qualità delle chiamate.

## <a name="run-query"></a>Esegui query

L'operazione Esegui query offre la possibilità di eseguire una query sul cubo in base a dimensioni, misure e filtri specificati e restituire i dati.


|**Metodo**|**URI di richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|Inserisci  <br/> |/QoEDataService/RunQuery\<portale\>https://  <br/> |HTTP/1.1  <br/> |

 **Parametri URI** -None.

 **Richiedi intestazioni** -nessuna intestazione aggiuntiva.

 **Richiedi corpo** : Ecco un payload di richiesta di esempio in JSON. Contiene dimensioni, filtri e misure necessarie per una query.

```
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

 *Filtri* : un elenco di espressioni di filtro da applicare in modo che il set di dati risultante rifletta solo il sottoinsieme dei dati di interesse.

 *Dimensions* : un elenco di dimensioni che verranno usate per l'aggregazione dei dati. È richiesta almeno una dimensione, ma possono essere specificate più dimensioni per ottenere un livello aggiuntivo di aggregazioni secondarie.

 *Misure* : un elenco di misurazioni, note anche come fact, che sono le metriche desiderate da aggregare in base alle dimensioni specificate.

 *Trend* -istruzioni aggiuntive per il controllo per personalizzare i dati dei risultati.

 **Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.

 **Codice di stato** : un'operazione riuscita restituisce il codice di stato 200 (OK).

 **Intestazioni di risposta** -nessuna intestazione aggiuntiva.

 **Corpo risposta** : di seguito è riportato un payload di risposta di esempio in JSON. Contiene una tabella dati che contiene i dati, inoltre conterrà un meta dati, che mostra il tempo di esecuzione della query e se i dati vengono o meno dalla cache.

```
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

 *Tempo di esecuzione* : il tempo totale impiegato per il server per la restituzione dei dati. Questo può o non può coinvolgere la cache.

 *Risultato dei dati* : il risultato della query. Si tratta di una matrice bidimensionale contenente tutte le permutazioni dei membri delle dimensioni e di ogni elemento contenente i nomi dei membri delle dimensioni e i valori aggregati delle misure specificate.

 Il *risultato è dalla cache* -per la diagnostica. Indica se il risultato proviene dalla cache o dal cubo QoE.
