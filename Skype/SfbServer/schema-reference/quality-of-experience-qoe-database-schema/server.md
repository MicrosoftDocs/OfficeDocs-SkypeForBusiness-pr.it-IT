---
title: Tabella Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: La tabella server è una tabella di supporto. Ogni record rappresenta un server.
ms.openlocfilehash: e57bb96fd715d67a5b6676a2399dc520f08bac96
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41806134"
---
# <a name="server-table"></a>Tabella Server
 
La tabella server è una tabella di supporto. Ogni record rappresenta un server. 
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica il server.  <br/> |
|**FQDNOrIP** <br/> |nvarchar (256)  <br/> |Indice  <br/> |Stringa dell'indirizzo MAC.  <br/> |
|**ServerType** <br/> |int  <br/> |Esterna  <br/> |1: Mediation Server  <br/> 2: a/V Conferencing Server16394: A/V Edge service32769: gateway  <br/> |
|**PoolName** <br/> |nvarchar (512)  <br/> ||Pool a cui appartiene il server. Applicabile solo per l'A/V Conferencing Server.  <br/> |
|**NextUpdateTS** <br/> |DateTime  <br/> ||Solo per uso interno.  <br/> |
   

