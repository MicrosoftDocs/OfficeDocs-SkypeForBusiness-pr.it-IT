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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId contiene l'ultimo ID chat generato (e usato nella tabella tblChat) per ogni utente.
ms.openlocfilehash: 95498f077948e1b400d0a370762c121def703e8c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814584"
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
