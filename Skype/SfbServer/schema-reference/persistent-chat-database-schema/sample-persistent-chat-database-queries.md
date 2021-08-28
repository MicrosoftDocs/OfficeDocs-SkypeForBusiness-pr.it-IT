---
title: Query del database Chat persistente di esempio
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
description: In questa sezione sono contenute query di esempio per il database di Persistent Chat.
ms.openlocfilehash: 041726f4f9e24d9d291d73e119cd62524b0a6288
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595318"
---
# <a name="sample-persistent-chat-database-queries"></a>Query del database Chat persistente di esempio
 
In questa sezione sono contenute query di esempio per il database di Persistent Chat.
  
Utilizzare l'esempio seguente per ottenere un elenco delle chat room di Persistent Chat più attive dopo una determinata data.
  
```SQL
SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
  FROM tblChat, tblNode
  WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY nodeName
  ORDER BY ChatMessages DESC
```

Utilizzare l'esempio seguente per ottenere un elenco degli utenti più attivi dopo una certa data.
  
```SQL
SELECT prinName as Name, count(*) as ChatMessages
  FROM tblChat, tblPrincipal
  WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY prinName
  ORDER BY ChatMessages DESC
```

Utilizzare l'esempio seguente per ottenere un elenco di tutti gli utenti che hanno inviato un messaggio contenente "Hello World".
  
```SQL
SELECT nodeName as ChatRoom, prinName as Name, content as Message
  FROM tblChat, tblNode, tblPrincipal
  WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'
```

Utilizzare l'esempio seguente per ottenere un elenco delle appartenenze a gruppi per una certa entità.
  
```SQL
SELECT prinName as Name    
  FROM tblPrincipalAffiliations as pa, tblPrincipal
  where principalID = 7 and affiliationID = prinID
```

Utilizzare l'esempio seguente per ottenere un elenco di tutte le chat di cui è membro diretto l'utente Jane Dow.
  
```SQL
SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
  FROM tblPrincipalRole, tblPrincipal, tblNode
  WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'
```

Utilizzare l'esempio seguente per ottenere un elenco degli inviti ricevuti da un utente.
  
```SQL
SELECT prinName
      ,nodeName
      ,invID   
      ,createdOn
  FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
  where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
  ORDER BY invID DESC
```
