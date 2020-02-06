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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: La tabella degli elementi multimediali è una tabella statica in cui è archiviato l'elenco di vari tipi di elementi multimediali.
ms.openlocfilehash: 7742baf17240ca810268721c0e47e37f17e555cd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815034"
---
# <a name="medialist-table"></a>Tabella MediaList
 
La tabella degli elementi multimediali è una tabella statica in cui è archiviato l'elenco di vari tipi di elementi multimediali.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**MediaId** <br/> |tinyint  <br/> |Principale  <br/> |Valori: 1-7  <br/> |
|**Contenuti multimediali** <br/> |nvarchar (256)  <br/> || Mapping statico di valori MediaID e media: <br/>  1--MESSAGGISTICA ISTANTANEA <br/>  2-trasferimento di file <br/>  3-assistenza remota <br/>  4-condivisione delle applicazioni <br/>  5--audio <br/>  6--video <br/>  7-invito all'app <br/> |
   
Se si sta provando a determinare il tipo di modalità per i valori in LcsCDR. SessionDetailsView. MediaTypes, è necessario usare il frammento di join seguente: 
  
```json
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
