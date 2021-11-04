---
title: Tabella Pool
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
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: La tabella Pool è una tabella di supporto in cui vengono archiviate informazioni sui diversi pool Front End. Ogni record della tabella rappresenta un pool.
ms.openlocfilehash: 501c35c6e3a8ded5d1a9c7cfab58395d91d0e653
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60740262"
---
# <a name="pool-table"></a>Tabella Pool
 
La tabella Pool è una tabella di supporto in cui vengono archiviate informazioni sui diversi pool Front End. Ogni record della tabella rappresenta un pool.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica il pool.  <br/> |
|**PoolName** <br/> |nvarchar(256)  <br/> |Univoco  <br/> |Nome di dominio completo del pool.  <br/> |
   

