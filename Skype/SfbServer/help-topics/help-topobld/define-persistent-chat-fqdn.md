---
title: Definire l'FQDN di Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: Si crea un nuovo server di chat persistente o un pool di server di chat persistente usando la procedura guidata Definisci nuovo pool di Persistent Chat. Selezionare l'opzione desiderata tra Pool di più computer o Pool computer singolo. Se si seleziona un pool con un singolo computer e successivamente si vuole definire un pool di più computer, sarà necessario rimuovere il primo pool e poi definire un pool di più computer.
ms.openlocfilehash: 247645e5cc87d23db25784d31c2727d56fab2681
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195708"
---
# <a name="define-persistent-chat-fqdn"></a>Definire l'FQDN di Chat persistente
 
Si crea un nuovo server di chat persistente o un pool di server di chat persistente usando la procedura guidata **Definisci nuovo pool di Persistent Chat** . Selezionare l'opzione desiderata tra **Pool di più computer** o **Pool computer singolo**. Se si seleziona un pool con un singolo computer e successivamente si vuole definire un pool di più computer, sarà necessario rimuovere il primo pool e poi definire un pool di più computer.
  
Devi anche definire il **nome di dominio completo del pool** per il server di chat persistente o il pool di server di chat persistente. Il nome di dominio completo (FQDN) del pool per un pool con un singolo computer deve essere lo stesso dell'FQDN del computer che costituisce il pool. Per un pool di più computer, l'FQDN deve essere il nome scelto per rappresentare questo pool ed è definito in DNS da un record host A (e AAAA se si usa IPv6).
  
## <a name="see-also"></a>Vedere anche

[Pianificare il server Chat persistente in Skype per Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Aggiungere il server di chat persistente alla topologia di Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
