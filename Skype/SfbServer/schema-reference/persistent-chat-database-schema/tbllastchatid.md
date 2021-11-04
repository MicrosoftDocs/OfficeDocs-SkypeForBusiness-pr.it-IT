---
title: tblLastChatId
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
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId contiene l'ultimo ID chat generato (e utilizzato nella tabella tblChat) per ogni utente.
ms.openlocfilehash: 7ab281b31869b4a761a6360978b57ec9591daaf0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741882"
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
