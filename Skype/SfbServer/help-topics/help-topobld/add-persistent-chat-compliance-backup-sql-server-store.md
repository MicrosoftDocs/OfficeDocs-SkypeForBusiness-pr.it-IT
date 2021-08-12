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
description: È possibile configurare gli archivi di SQL Server di backup che forniranno database di backup per il server Chat persistente o il server Chat persistente SQL Server archiviati.
ms.openlocfilehash: edcb80d798e6039560db4149b17ce7c2d2d61b9d92a4450199dcad29b12093dc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344925"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a>Aggiungere l'archivio SQL Server di conformità di backup per Chat persistente
 
È possibile configurare gli archivi di SQL Server di backup che forniranno database di backup per il server Chat persistente o il server Chat persistente SQL Server archiviati.
  
 **SQL Server archivio:** selezionare un SQL Server esistente e facoltativamente un'istanza per Persistent Chat.
  
Fare **clic su** Nuovo per definire una nuova SQL Server e facoltativamente una nuova istanza per i dati di conformità del backup di Persistent Chat.
  
Selezionare la **casella di controllo Abilita mirroring** SQL Server store per configurare un database di SQL Server e un'istanza facoltativa che fornirà un database con mirroring per i dati di conformità del backup di Persistent Chat.
  
Selezionare nell'elenco **Mirroring SQL Server archiviare** un'SQL Server e un'istanza facoltativa per fungere da mirror SQL Server per la conformità di backup di Persistent Chat SQL Server.
  
Fare **clic su** Nuovo per definire una nuova SQL Server e facoltativamente una nuova istanza per il mirroring SQL Server Persistent Chat.
  
Nell'elenco **Usa controllo del mirroring di SQL Server per abilitare il failover automatico** selezionare un server SQL Server che fungerà da server di controllo negli scenari di failover. Il server di controllo non esegue il mirroring o ospita i dati per i server Chat persistente, ma garantisce che solo un SQL Server in una configurazione con mirroring sia il SQL Server attivo in qualsiasi momento.
  
Fare **clic su** Nuovo per definire un nuovo SQL Server di controllo facoltativamente un'istanza per il controllo di conformità del backup di Persistent Chat SQL Server mirroring.
  
Fare clic su **Indietro** per tornare alla finestra di dialogo per la definizione del pool precedente.
  
Fare **clic** su Avanti dopo aver immesso le opzioni per la configurazione dell'archivio di SQL Server di backup del pool e per procedere con la definizione del pool di server Chat persistente.
  
Fare clic su **Annulla** per eliminare tutte le modifiche e chiudere la procedura guidata **Definisci nuovo pool Persistent Chat**.
  
Fare clic su **Guida** per accedere alla Guida sensibile al contesto, come questa pagina.
  
## <a name="see-also"></a>Vedere anche

[Pianificare il server Chat persistente in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Requisiti del server per Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Requisiti hardware e software per il server Chat persistente in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Configurare il servizio di conformità per il server Chat persistente in Skype for Business Server 2015](../../manage/persistent-chat/configure-compliance.md)
  
[Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
