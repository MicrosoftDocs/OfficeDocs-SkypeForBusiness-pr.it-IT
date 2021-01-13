---
title: tblLastChatId
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
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: LastChatId contiene l'ultimo ID chat generato (e utilizzato nella tabella tblChat) per ogni utente.
ms.openlocfilehash: 80664d6b296fce9b4909674f9d21b1aa13285826
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816006"
---
# <a name="tbllastchatid"></a>tblLastChatId
 
LastChatId contiene l'ultimo ID chat generato (e utilizzato nella tabella tblChat) per ogni utente.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, not null  <br/> |ID nodo (solo di tipo chat).  <br/> |
|Dalla LastChatId  <br/> |bigint, non null  <br/> |Ultimo ID chat utilizzato.  <br/> |
   
**Chiavi**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|\<nodeID, lastChatID\>  <br/> |Chiave primaria (solo nodeID è sufficiente per l'elaborazione).  <br/> |
|nodeID  <br/> |Chiave esterna con ricerca nella tabella tblNode.nodeID.  <br/> |
   
## <a name="see-also"></a>Vedere anche

[tblChat](tblchat.md)
