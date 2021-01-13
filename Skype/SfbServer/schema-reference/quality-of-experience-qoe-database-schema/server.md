---
title: Tabella server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 7f26ed9053c65acb8cfd2e586edbd77fdfa7472b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802706"
---
# <a name="server-table"></a>Tabella server
 
La tabella server è una tabella di supporto. Ogni record rappresenta un server. 
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica il server.  <br/> |
|**FQDNOrIP** <br/> |nvarchar (256)  <br/> |Indice  <br/> |Stringa dell'indirizzo MAC.  <br/> |
|**ServerType** <br/> |int  <br/> |Stranieri  <br/> |1: Mediation Server  <br/> 2: a/V Conferencing Server16394: A/V Edge service32769: gateway  <br/> |
|**PoolName** <br/> |nvarchar (512)  <br/> ||Pool a cui appartiene il server. Applicabile solo per l'A/V Conferencing Server.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Solo per uso interno.  <br/> |
   

