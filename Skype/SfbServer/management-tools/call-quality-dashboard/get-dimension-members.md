---
title: Get Dimension Members
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
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: "Riepilogo: informazioni sull'operazione Get Dimension Members. L'operazione Get Dimension Members fa parte dell'API dei dati per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 3a0c01b310ed60c4b0808d669b553391277f3877bff4c4800bea1b5b765bf5b7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54278714"
---
# <a name="get-dimension-members"></a>Get Dimension Members
 
**Riepilogo:** Informazioni sull'operazione Get Dimension Members. L'operazione Get Dimension Members fa parte dell'API dei dati per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server.
  
L'operazione Get Dimension Members fa parte dell'API dei dati per call quality dashboard.
  
## <a name="get-dimension-members"></a>Get Dimension Members

L'operazione Get Dimension Members restituisce l'elenco dei membri di una dimensione specifica. Offre anche la possibilità di filtrare l'elenco dei membri e ottenere un sottoinsieme, per ridurre il costo di trasferimento dei fili.
  

|**Metodo**|**URI richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|POST  <br/> |https:// \<portal\> /QoEDataService/DimensionMembers  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI** - Nessuno.
  
 **Intestazioni richiesta** - Nessuna intestazione aggiuntiva.
  
 **Request Body** - Contiene il nome della dimensione per cui si desiderano i membri. Inoltre, il numero massimo di membri restituiti, oltre a poter specificare un filtro per limitare i membri restituiti.
  
```json
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}
```

 **Risposta:** la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
 **Codice di stato:** un'operazione riuscita restituisce il codice di stato 200 (OK).
  
 **Intestazioni di risposta** - Nessuna intestazione aggiuntiva.
  
 **Response Body:** di seguito è riportato un payload di risposta di esempio in JSON in risposta a una richiesta di "[StartDate]. Dimensione [Mese]".
  
> [!NOTE]
> L'elenco mostra solo una piccola parte dell'elenco. 
  
```json
{
"MembersCount": 493,
"Members": [["[1990-01-01T00:00:00]",
"January 1990"],
["[1990-02-01T00:00:00]",
"February 1990"],
["[1990-03-01T00:00:00]",
"March 1990"],
 
    ...
    
["[2030-10-01T00:00:00]",
"October 2030"],
["[2030-11-01T00:00:00]",
"November 2030"],
["[2030-12-01T00:00:00]",
"December 2030"],
["[2031-01-01T00:00:00]",
"January 2031"]]
}
```
