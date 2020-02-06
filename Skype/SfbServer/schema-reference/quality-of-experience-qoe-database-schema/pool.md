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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: La tabella pool è una tabella di supporto in cui sono archiviate informazioni sui diversi pool di front-end. Ogni record nella tabella rappresenta un pool.
ms.openlocfilehash: 2b6dfb924c3e7a79a323ebbabd90e74ba08ebf04
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807404"
---
# <a name="pool-table"></a>Tabella Pool
 
La tabella pool è una tabella di supporto in cui sono archiviate informazioni sui diversi pool di front-end. Ogni record nella tabella rappresenta un pool.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica questo pool.  <br/> |
|**PoolName** <br/> |nvarchar (256)  <br/> |Univoci  <br/> |FQDN del pool.  <br/> |
   

