---
title: tblLastChatId
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
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId contiene l'ultimo ID chat generato (e utilizzato nella tabella tblChat) per ogni utente.
ms.openlocfilehash: a69c8ee112d507359a5582464ce39b7cbae89f4c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60838438"
---
# <a name="tbllastchatid"></a>tblLastChatId
 
tblLastChatId contiene l'ultimo ID chat generato (e utilizzato nella tabella tblChat) per ogni utente.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, not null  <br/> |ID nodo (solo di tipo chat room).  <br/> |
|lastChatID  <br/> |bigint, non null  <br/> |ULTIMO ID chat usato.  <br/> |
   
**Tasti**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|\<nodeID, lastChatID\>  <br/> |Chiave primaria (solo nodeID è sufficiente per l'elaborazione).  <br/> |
|nodeID  <br/> |Chiave esterna con ricerca nella tabella tblNode.nodeID.  <br/> |
   
## <a name="see-also"></a>Vedere anche

[tblChat](tblchat.md)
