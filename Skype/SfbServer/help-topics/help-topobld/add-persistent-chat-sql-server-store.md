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
ms.localizationpriority: medium
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: Configurare gli archivi SQL Server che forniranno database per il server Chat persistente o il pool di server Chat persistente.
ms.openlocfilehash: 7d3f9754e402c6049c4d0fd8cec9dd97758b5d32
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58630840"
---
# <a name="add-persistent-chat-sql-server-store"></a>Aggiungere l'archivio SQL Server per Chat persistente
 
Configurare gli archivi SQL Server che forniranno database per il server Chat persistente o il pool di server Chat persistente.
  
 **SQL Server archivio:** selezionare un SQL Server esistente e facoltativamente un'istanza per Persistent Chat.
  
Fare **clic su** Nuovo per definire una nuova SQL Server e facoltativamente una nuova istanza per i dati di Persistent Chat.
  
Selezionare la **casella di controllo Abilita mirroring** SQL Server archivio per configurare un database di SQL Server e un'istanza facoltativa che fornirà un database con mirroring per i dati di Persistent Chat.
  
Selezionare nell'elenco **Mirroring SQL Server archiviare** un'SQL Server e un'istanza facoltativa per fungere da mirror SQL Server per il SQL Server persistente.
  
Fare **clic su** Nuovo per definire una nuova SQL Server e facoltativamente una nuova istanza per il mirroring SQL Server Persistent Chat.
  
Nell'elenco **Usa controllo del mirroring di SQL Server per abilitare il failover automatico** selezionare un server SQL Server che fungerà da server di controllo negli scenari di failover. Il server di controllo non esegue il mirroring o ospita i dati per i server Chat persistente, ma garantisce che solo un SQL Server in una configurazione con mirroring sia il SQL Server attivo in qualsiasi momento.
  
Fare **clic su** Nuovo per definire un nuovo SQL Server di controllo, facoltativamente un'istanza per il controllo del mirroring SQL Server chat persistente.
  
Fare clic su **Indietro** per tornare alla finestra di dialogo per la definizione del pool precedente.
  
Fare **clic** su Avanti dopo aver immesso le opzioni per la configurazione dell SQL Server store del pool e per procedere con la definizione del pool di server Chat persistente.
  
Fare clic su **Annulla** per eliminare tutte le modifiche e chiudere la procedura guidata **Definisci nuovo pool Persistent Chat**.
  
Fare clic su **Guida** per accedere alla Guida sensibile al contesto, come questa pagina.
  
## <a name="see-also"></a>Vedere anche

[Pianificare il server Chat persistente in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Aggiungere il server Chat persistente alla topologia Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Requisiti hardware e software per il server Chat persistente in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Requisiti del server per Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Nozioni di base sulla topologia Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
