---
title: Tabella MediaList
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: La tabella MediaList è una tabella statica in cui è archiviato l'elenco di diversi tipi di elementi multimediali.
ms.openlocfilehash: 643c373eb7e6a73cf8755f14ea0f5497efee6fed
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60849629"
---
# <a name="medialist-table"></a>Tabella MediaList
 
La tabella MediaList è una tabella statica in cui è archiviato l'elenco di diversi tipi di elementi multimediali.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**MediaId** <br/> |tinyint  <br/> |Principale  <br/> |Valori: 1-7  <br/> |
|**Contenuti multimediali** <br/> |nvarchar(256)  <br/> || Mapping statico dei valori MediaID e Media: <br/>  1 -- Messaggistica istantanea <br/>  2 - Trasferimento file <br/>  3 - Assistenza remota <br/>  4 - Condivisione applicazioni <br/>  5 -- Audio <br/>  6 -- Video <br/>  7 - Invito app <br/> |
   
Se si sta tentando di determinare il tipo di modalità per i valori in LcsCDR.SessionDetailsView.MediaTypes, è necessario utilizzare il frammento join seguente: 
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
