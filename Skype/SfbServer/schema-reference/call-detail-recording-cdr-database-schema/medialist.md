---
title: Tabella media
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: La tabella MediaList è una tabella statica in cui è archiviato l'elenco di diversi tipi di elementi multimediali.
ms.openlocfilehash: 6f593876a1b42163b6f2e75dbe44c1eb26b2ff16
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813136"
---
# <a name="medialist-table"></a>Tabella media
 
La tabella MediaList è una tabella statica in cui è archiviato l'elenco di diversi tipi di elementi multimediali.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**MediaId** <br/> |tinyint  <br/> |Principale  <br/> |Valori: 1-7  <br/> |
|**Contenuti multimediali** <br/> |nvarchar (256)  <br/> || Mapping statico dei valori di MediaID e media: <br/>  1 -- Messaggistica istantanea <br/>  2-trasferimento file <br/>  3-assistenza remota <br/>  4-condivisione di applicazioni <br/>  5 -- Audio <br/>  6 -- Video <br/>  7-app invite <br/> |
   
Se si sta tentando di determinare il tipo di modalità per i valori in LcsCDR. SessionDetailsView. MediaTypes, è necessario utilizzare il seguente frammento di join: 
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
