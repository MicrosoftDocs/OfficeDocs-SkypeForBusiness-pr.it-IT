---
title: Definire l'FQDN di Persistent Chat
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: È possibile creare un nuovo server Chat persistente o un nuovo pool di server Chat persistente utilizzando la procedura guidata Definisci nuovo pool di Chat persistente. Selezionare l'opzione desiderata tra Pool di più computer o Pool computer singolo. Se si seleziona un pool di computer singolo e in un secondo momento è necessario un pool di più computer, sarà necessario rimuovere il pool a computer singolo e quindi definire un pool di più computer.
ms.openlocfilehash: e96cc1f3c71dee7bab50d3101281596c17084207
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818446"
---
# <a name="define-persistent-chat-fqdn"></a>Definire il nome di dominio completo (FQDN) di Chat persistente
 
È possibile creare un nuovo server Chat persistente o un nuovo pool di server Chat persistente utilizzando la procedura guidata Definisci nuovo **pool di Chat** persistente. Selezionare l'opzione desiderata tra **Pool di più computer** o **Pool computer singolo**. Se si seleziona un pool di computer singolo e in un secondo momento è necessario un pool di più computer, sarà necessario rimuovere il pool a computer singolo e quindi definire un pool di più computer.
  
È inoltre necessario definire un **FQDN del pool** per il server Chat persistente o il pool di server Chat persistente. Il nome di dominio completo (FQDN) del pool per un pool con un singolo computer deve essere lo stesso dell'FQDN del computer che costituisce il pool. Per un pool di più computer, l'FQDN deve essere il nome scelto per rappresentare questo pool ed è definito in DNS da un record host A (e AAAA se si usa IPv6).
  
## <a name="see-also"></a>Vedere anche

[Pianificare il server Chat persistente in Skype for Business Server](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Aggiungere il server Chat persistente alla topologia di Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
