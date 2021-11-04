---
title: Tabella EdgeServers in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: La tabella EdgeServers è una tabella di supporto. In ogni record vengono archiviate informazioni su un server perimetrale coinvolto nelle chiamate con record nel database.
ms.openlocfilehash: 088897094bca9d4723b6321f0fc1b2f0eba70b9b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743902"
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a>Tabella EdgeServers in Skype for Business Server 2015
 
La tabella EdgeServers è una tabella di supporto. In ogni record vengono archiviate informazioni su un server perimetrale coinvolto nelle chiamate con record nel database.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**EdgeServerId** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica il server perimetrale.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> | <br/> |Nome del server perimetrale.  <br/> |
   

