---
title: Tabella Pool
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: La tabella Pool è una tabella di supporto in cui vengono archiviate informazioni sui diversi pool Front End. Ogni record della tabella rappresenta un pool.
---

# <a name="pool-table"></a>Tabella Pool
 
La tabella Pool è una tabella di supporto in cui vengono archiviate informazioni sui diversi pool Front End. Ogni record della tabella rappresenta un pool.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica il pool.  <br/> |
|**PoolName** <br/> |nvarchar(256)  <br/> |Univoco  <br/> |Nome di dominio completo del pool.  <br/> |
   

