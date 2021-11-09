---
title: Tabella EdgeServers in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: 98b7c29354631c0886aaa42f4f5b5c219383e3ca
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828609"
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a>Tabella EdgeServers in Skype for Business Server 2015
 
La tabella EdgeServers è una tabella di supporto. In ogni record vengono archiviate informazioni su un server perimetrale coinvolto nelle chiamate con record nel database.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**EdgeServerId** <br/> |int  <br/> |Principale  <br/> |Numero univoco che identifica il server perimetrale.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> | <br/> |Nome del server perimetrale.  <br/> |
   

