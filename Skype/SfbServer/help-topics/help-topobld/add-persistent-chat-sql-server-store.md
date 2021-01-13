---
title: Aggiungere l'archivio SQL Server per Persistent Chat
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
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: È necessario configurare gli archivi SQL Server che forniranno i database per il server Chat persistente o per il pool di server Chat persistente.
ms.openlocfilehash: e93705e0646f1115994a61c936a5c0cb16149dfa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818656"
---
# <a name="add-persistent-chat-sql-server-store"></a>Aggiungere l'archivio SQL Server per Chat persistente
 
È necessario configurare gli archivi SQL Server che forniranno i database per il server Chat persistente o per il pool di server Chat persistente.
  
 **Archivio SQL Server**: selezionare un SQL Server esistente e facoltativamente un'istanza per la chat persistente.
  
Fare clic su **nuovo** per definire un nuovo SQL Server e facoltativamente una nuova istanza per i dati di Persistent Chat.
  
Selezionare la casella di controllo **Abilita mirroring dell'archivio SQL Server** per configurare un database di SQL Server e un'istanza facoltativa che fornirà un database con mirroring per i dati di Persistent Chat.
  
Selezionare dall'elenco **mirroring di SQL Server archivio** un SQL Server e un'istanza facoltativa che funga da mirror di SQL Server per SQL Server di chat persistente.
  
Fare clic su **nuovo** per definire un nuovo SQL Server e, se lo si desidera, una nuova istanza per il mirroring di SQL server Chat persistente.
  
Nell'elenco **Usa controllo del mirroring di SQL Server per abilitare il failover automatico** selezionare un server SQL Server che fungerà da server di controllo negli scenari di failover. Il server di controllo non specchia o ospita i dati per i server Chat persistente, ma garantisce che un solo SQL Server in una configurazione con mirroring sia il SQL Server attivo in qualsiasi momento.
  
Fare clic su **nuovo** per definire un nuovo witness di SQL Server facoltativamente un'istanza per il controllo del mirroring di SQL Server di chat persistente.
  
Fare clic su **Indietro** per tornare alla finestra di dialogo per la definizione del pool precedente.
  
Fare clic su **Avanti** dopo aver immesso le opzioni per la configurazione dell'archivio SQL Server di questo pool e per continuare con la definizione del pool di server Chat persistente.
  
Fare clic su **Annulla** per eliminare tutte le modifiche e chiudere la procedura guidata **Definisci nuovo pool Persistent Chat**.
  
Fare clic su **Guida** per accedere alla Guida sensibile al contesto, come questa pagina.
  
## <a name="see-also"></a>Vedere anche

[Pianificare il server Chat persistente in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Aggiungere il server Chat persistente alla topologia di Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Requisiti hardware e software per il server Chat persistente in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Requisiti del server per Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Nozioni di base sulla topologia per Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
