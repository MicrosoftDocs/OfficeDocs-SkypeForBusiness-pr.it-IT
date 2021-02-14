---
title: Aggiungere l'archivio SQL Server di backup per Conformità Persistent Chat
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
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: Configurare gli archivi di conformità SQL Server backup che forniranno i database di backup per il server Chat persistente o il server Chat persistente SQL Server archiviati.
ms.openlocfilehash: 9b380091978d62294c6ea16ffa8586b9f8d9d322
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818716"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a>Aggiungere l'archivio SQL Server di conformità di backup per Chat persistente
 
Configurare gli archivi di conformità SQL Server backup che forniranno i database di backup per il server Chat persistente o il server Chat persistente SQL Server archiviati.
  
 **SQL Server:** selezionare un'istanza esistente SQL Server e facoltativamente un'istanza per Persistent Chat.
  
Fare **clic su** Nuovo per definire un nuovo SQL Server e facoltativamente una nuova istanza per i dati di conformità del backup di Persistent Chat.
  
Selezionare la **casella di controllo SQL Server** mirroring dell'archivio per configurare un database di SQL Server e un'istanza facoltativa che forniranno un database con mirroring per i dati di conformità del backup di Persistent Chat.
  
Selezionare nell'elenco **Mirroring SQL Server archiviare** un SQL Server e un'istanza facoltativa per fungere da mirror SQL Server per la conformità del backup di Persistent Chat SQL Server.
  
Fare **clic su** Nuovo per definire una nuova SQL Server e facoltativamente una nuova istanza per il mirroring SQL Server Persistent Chat.
  
Nell'elenco **Usa controllo del mirroring di SQL Server per abilitare il failover automatico** selezionare un server SQL Server che fungerà da server di controllo negli scenari di failover. Il server di controllo non esegue il mirroring o ospita i dati per i server Chat persistente, ma garantisce che un solo SQL Server in una configurazione con mirroring sia il SQL Server attivo in qualsiasi momento.
  
Fare **clic su Nuovo** per definire un nuovo SQL Server di controllo, facoltativamente un'istanza per il controllo di conformità del backup di Persistent Chat SQL Server controllo del mirroring.
  
Fare clic su **Indietro** per tornare alla finestra di dialogo per la definizione del pool precedente.
  
Fare **clic** su Avanti dopo aver immesso le opzioni per la configurazione dell'archivio SQL Server backup del pool e per continuare con la definizione del pool del server Chat persistente.
  
Fare clic su **Annulla** per eliminare tutte le modifiche e chiudere la procedura guidata **Definisci nuovo pool Persistent Chat**.
  
Fare clic su **Guida** per accedere alla Guida sensibile al contesto, come questa pagina.
  
## <a name="see-also"></a>Vedere anche

[Pianificare il server Chat persistente in Skype for Business Server](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Requisiti del server per Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Requisiti hardware e software per il server Chat persistente in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Configurare il servizio di conformità per il server Chat persistente in Skype for Business Server 2015](../../manage/persistent-chat/configure-compliance.md)
  
[Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
