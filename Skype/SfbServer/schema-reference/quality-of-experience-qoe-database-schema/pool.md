---
title: Tabella Pool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: La tabella pool è una tabella di supporto in cui sono archiviate informazioni sui diversi pool di front-end. Ogni record nella tabella rappresenta un pool.
ms.openlocfilehash: c101a10d40292c89c29e108739195a97fa22e5c0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194595"
---
# <a name="pool-table"></a>Tabella Pool
 
La tabella pool è una tabella di supporto in cui sono archiviate informazioni sui diversi pool di front-end. Ogni record nella tabella rappresenta un pool.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica questo pool.  <br/> |
|**PoolName** <br/> |nvarchar (256)  <br/> |Univoci  <br/> |FQDN del pool.  <br/> |
   

