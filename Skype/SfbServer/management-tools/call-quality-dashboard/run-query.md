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
description: "Riepilogo: informazioni sull'operazione Esegui query, che fa parte dell'API dati per il dashboard qualità delle chiamate. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 860760303510b792cba70fc211ac8b7f9b994996b4937aa333ed54fcffb6eb75
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340862"
---
# <a name="run-query"></a>Run Query

**Riepilogo:** Informazioni sull'operazione Esegui query, che fa parte dell'API dati per il dashboard qualità chiamata. Call Quality Dashboard è uno strumento per Skype for Business Server.

L'operazione Esegui query fa parte dell'API dati per il dashboard qualità delle chiamate.

## <a name="run-query"></a>Run Query

L'operazione Esegui query consente di eseguire una query sul cubo in base a dimensioni, misure e filtri specificati e restituire i dati.


|**Metodo**|**URI richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|POST  <br/> |https:// \<portal\> /QoEDataService/RunQuery  <br/> |HTTP/1.1  <br/> |

 **Parametri URI** - Nessuno.

 **Intestazioni richiesta** - Nessuna intestazione aggiuntiva.

 **Corpo della richiesta:** ecco un payload di richiesta di esempio in JSON. Contiene dimensioni, filtri e misurazioni necessarie per una query.

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

 *Filtri*  - Elenco di espressioni di filtro da applicare in modo che il set di dati risultante rifletta solo il sottoinsieme di dati di interesse.

 *Dimensioni*  : elenco di dimensioni che verranno utilizzate per l'aggregazione dei dati. È necessaria almeno una dimensione, ma è possibile specificarne più per ottenere un livello aggiuntivo di aggregazioni secondarie.

 *Misurazioni*  - Elenco di misurazioni, note anche come fatti, che sono le metriche desiderate da aggregare in base alle dimensioni specificate.

 *Tendenza:*  istruzioni di controllo aggiuntive per personalizzare i dati dei risultati.

 **Risposta:** la risposta include un codice di stato HTTP e un set di intestazioni di risposta.

 **Codice di stato:** un'operazione riuscita restituisce il codice di stato 200 (OK).

 **Intestazioni di risposta** - Nessuna intestazione aggiuntiva.

 **Response Body:** di seguito è riportato un payload di risposta di esempio in JSON. Contiene una tabella di dati che contiene i dati, inoltre conterrà un meta dati, che mostra il tempo di esecuzione delle query e se i dati vengono o meno dalla cache.

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

 *Tempo di*  esecuzione - Tempo totale impiegato dal server per restituire i dati. Ciò può comportare o meno la cache.

 *Risultato dati*  - Risultato della query. È una matrice bidimensionale contenente tutte le permutazioni dei membri delle dimensioni e ogni elemento contenente i nomi dei membri delle dimensioni, nonché i valori aggregati delle misure specificate.

 *Result is From Cache*  - Per la diagnostica. Indica se il risultato proveniva dalla cache o dal cubo QoE.
