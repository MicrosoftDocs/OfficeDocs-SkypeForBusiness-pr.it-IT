---
title: Tabella EdgeServers in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: La tabella EdgeServers è una tabella di supporto. In ogni record vengono archiviate informazioni su un server perimetrale coinvolto nelle chiamate con record nel database.
ms.openlocfilehash: 98f37ecbf976fb08ae27e080f5e9e498558131fb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813206"
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a>Tabella EdgeServers in Skype for Business Server 2015
 
La tabella EdgeServers è una tabella di supporto. In ogni record vengono archiviate informazioni su un server perimetrale coinvolto nelle chiamate con record nel database.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**EdgeServerId** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica il server perimetrale.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> | <br/> |Nome del server perimetrale.  <br/> |
   

