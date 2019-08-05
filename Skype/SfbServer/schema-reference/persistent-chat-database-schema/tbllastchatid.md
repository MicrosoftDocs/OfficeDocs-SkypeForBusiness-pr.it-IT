---
title: tblLastChatId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId contiene l'ultimo ID chat generato (e usato nella tabella tblChat) per ogni utente.
ms.openlocfilehash: f14d8090fd3252d88ef747de93a987f51870a63b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194682"
---
# <a name="tbllastchatid"></a>tblLastChatId
 
tblLastChatId contiene l'ultimo ID chat generato (e usato nella tabella tblChat) per ogni utente.
  
**Colonne**

|**Colonna**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, not null  <br/> |ID nodo (solo chat room-tipo).  <br/> |
|Dalla LastChatId  <br/> |bigint e non null  <br/> |Ultimo ID chat usato.  <br/> |
   
**Tasti**

|**Colonna**|**Descrizione**|
|:-----|:-----|
|\<nodeID, dalla LastChatId\>  <br/> |Chiave primaria (solo nodeID è sufficiente per l'elaborazione).  <br/> |
|nodeID  <br/> |Chiave esterna con ricerca nella tabella tblNode. nodeID.  <br/> |
   
## <a name="see-also"></a>Vedere anche

[tblChat](tblchat.md)
