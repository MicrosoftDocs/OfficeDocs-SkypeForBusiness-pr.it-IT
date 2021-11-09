---
title: Tabella Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: c061176c7a3dbb30fbbe696241fccd54db8dc9b2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834924"
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
   

