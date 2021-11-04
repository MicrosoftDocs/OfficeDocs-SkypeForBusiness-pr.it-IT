---
title: Tabella Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: La tabella Server è una tabella di supporto. Ogni record rappresenta un server.
ms.openlocfilehash: e2a1007afa545a5b70b60f0e22f69826daebcda0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776036"
---
# <a name="server-table"></a>Tabella Server
 
La tabella Server è una tabella di supporto. Ogni record rappresenta un server. 
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica il server.  <br/> |
|**FQDNOrIP** <br/> |nvarchar(256)  <br/> |index  <br/> |Stringa dell'indirizzo MAC.  <br/> |
|**ServerType** <br/> |int  <br/> |Foreign  <br/> |1: Mediation Server  <br/> 2: A/V Conferencing Server16394: servizio A/V Edge32769: Gateway  <br/> |
|**PoolName** <br/> |nvarchar(512)  <br/> ||Pool a cui appartiene il server. Applicabile solo per A/V Conferencing Server.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Solo per uso interno.  <br/> |
   

