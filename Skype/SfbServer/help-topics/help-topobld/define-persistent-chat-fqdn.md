---
title: Definire l'FQDN di Persistent Chat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: È possibile creare un nuovo server Chat persistente o un pool di server Chat persistente utilizzando la procedura guidata Definisci nuovo pool Persistent Chat. Selezionare l'opzione desiderata tra Pool di più computer o Pool computer singolo. Se si seleziona un pool di computer singolo e successivamente è necessario un pool di più computer, sarà necessario rimuovere il pool di computer singolo e quindi definire un pool di più computer.
ms.openlocfilehash: 61851656b70b85db47fdad01dff0101217262dda
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217552"
---
# <a name="define-persistent-chat-fqdn"></a>Definire l'FQDN di Persistent Chat
 
È possibile creare un nuovo server Chat persistente o un pool di server Chat persistente utilizzando la procedura guidata **Definisci nuovo pool Persistent Chat** . Selezionare l'opzione desiderata tra **Pool di più computer** o **Pool computer singolo**. Se si seleziona un pool di computer singolo e successivamente è necessario un pool di più computer, sarà necessario rimuovere il pool di computer singolo e quindi definire un pool di più computer.
  
È inoltre necessario definire un **FQDN del pool** per il server Chat persistente o per il pool di server Chat persistente. Il nome di dominio completo (FQDN) del pool per un pool con un singolo computer deve essere lo stesso dell'FQDN del computer che costituisce il pool. Per un pool di più computer, l'FQDN deve essere il nome scelto per rappresentare questo pool ed è definito in DNS da un record host A (e AAAA se si usa IPv6).
  
## <a name="see-also"></a>Vedere anche

[Pianificare il server Chat persistente in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Aggiungere il server Chat persistente alla topologia di Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
