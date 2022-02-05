---
title: Aggiungere l'archivio SQL Server di backup per Persistent Chat
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.AddPersistentChatBackupSqlStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 106698e4-ce73-4a34-8fc7-e9d3208a17dc
description: Configurare gli archivi SQL Server backup che forniranno database di backup per il server Chat persistente o il pool di server Chat persistente.
---

# <a name="add-persistent-chat-backup-sql-server-store"></a>Aggiungere l'archivio SQL Server di backup per Chat persistente
 
Configurare gli archivi SQL Server backup che forniranno database di backup per il server Chat persistente o il pool di server Chat persistente.
  
 **SQL Server archivio**: selezionare un SQL Server esistente e facoltativamente un'istanza per Persistent Chat.
  
Fare **clic su** Nuovo per definire una nuova SQL Server e facoltativamente una nuova istanza per i dati di backup di Persistent Chat.
  
Selezionare la **casella di controllo Abilita mirroring SQL Server archivio** per configurare un database di SQL Server e un'istanza facoltativa che fornirà un database con mirroring per i dati di backup di Persistent Chat.
  
Selezionare nell'elenco **Mirroring SQL Server archiviare** un'SQL Server e un'istanza facoltativa per fungere da mirror SQL Server per il backup di Persistent Chat SQL Server.
  
Fare **clic su** Nuovo per definire una nuova SQL Server e, facoltativamente, una nuova istanza per il mirroring SQL Server Persistent Chat.
  
Nell'elenco **Usa controllo del mirroring di SQL Server per abilitare il failover automatico** selezionare un server SQL Server che fungerà da server di controllo negli scenari di failover. Il server di controllo non esegue il mirroring o ospita i dati per i server Chat persistente, ma garantisce che solo un SQL Server in una configurazione con mirroring sia il SQL Server attivo in qualsiasi momento.
  
Fare **clic su** Nuovo per definire un nuovo SQL Server di controllo, facoltativamente un'istanza per il backup di Persistent Chat SQL Server di mirroring.
  
Fare clic su **Indietro** per tornare alla finestra di dialogo per la definizione del pool precedente.
  
Fare **clic** su Avanti dopo aver immesso le opzioni per la configurazione dell'archivio SQL Server backup del pool e per procedere con la definizione del pool di server Chat persistente.
  
Fare clic su **Annulla** per eliminare tutte le modifiche e chiudere la procedura guidata **Definisci nuovo pool Persistent Chat**.
  
Fare clic su **Guida** per accedere alla Guida sensibile al contesto, come questa pagina.
  
## <a name="see-also"></a>Vedere anche

[Pianificare il server Chat persistente in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Requisiti del server per Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Requisiti hardware e software per il server Chat persistente in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
