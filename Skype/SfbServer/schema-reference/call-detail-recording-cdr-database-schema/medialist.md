---
title: Tabella MediaList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: La tabella degli elementi multimediali è una tabella statica in cui è archiviato l'elenco di vari tipi di elementi multimediali.
ms.openlocfilehash: 308a9eee57089a02b8e3ff9924e0d9d34162f33e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194769"
---
# <a name="medialist-table"></a>Tabella MediaList
 
La tabella degli elementi multimediali è una tabella statica in cui è archiviato l'elenco di vari tipi di elementi multimediali.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**MediaId** <br/> |tinyint  <br/> |Principale  <br/> |Valori: 1-7  <br/> |
|**Media** <br/> |nvarchar (256)  <br/> || Mapping statico di valori MediaID e media: <br/>  1--MESSAGGISTICA ISTANTANEA <br/>  2-trasferimento di file <br/>  3-assistenza remota <br/>  4-condivisione delle applicazioni <br/>  5--audio <br/>  6--video <br/>  7-invito all'app <br/> |
   
Se si sta provando a determinare il tipo di modalità per i valori in LcsCDR. SessionDetailsView. MediaTypes, è necessario usare il frammento di join seguente: 
  
```
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
