---
title: Aggiungere l'archivio SQL Server di backup per Conformità Persistent Chat
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
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: È possibile configurare gli archivi SQL Server di conformità di backup che forniranno i database di backup per il server Chat persistente o per gli archivi SQL Server di conformità di Persistent Chat Server.
ms.openlocfilehash: 9251c322560d06652c4eefe80b6c05a51aa9f922
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218697"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a>Aggiungere l'archivio SQL Server di backup per Conformità Persistent Chat
 
È possibile configurare gli archivi SQL Server di conformità di backup che forniranno i database di backup per il server Chat persistente o per gli archivi SQL Server di conformità di Persistent Chat Server.
  
 **Archivio SQL Server**: selezionare un SQL Server esistente e facoltativamente un'istanza per la chat persistente.
  
Fare clic su **nuovo** per definire un nuovo SQL Server e, se lo si desidera, una nuova istanza per i dati di conformità di backup Persistent Chat.
  
Selezionare la casella di controllo **Abilita mirroring dell'archivio SQL Server** per configurare un database di SQL Server e un'istanza facoltativa che fornirà un database con mirroring per i dati di conformità di backup di Persistent Chat.
  
Selezionare dall'elenco **mirroring di SQL Server archivio** un SQL Server e un'istanza facoltativa che funga da mirror di SQL Server per la conformità a SQL Server per il backup di Persistent Chat.
  
Fare clic su **nuovo** per definire un nuovo SQL Server e, se lo si desidera, una nuova istanza per il mirroring di SQL server Chat persistente.
  
Nell'elenco **Usa controllo del mirroring di SQL Server per abilitare il failover automatico** selezionare un server SQL Server che fungerà da server di controllo negli scenari di failover. Il server di controllo non specchia o ospita i dati per i server Chat persistente, ma garantisce che un solo SQL Server in una configurazione con mirroring sia il SQL Server attivo in qualsiasi momento.
  
Fare clic su **nuovo** per definire un nuovo controllo di SQL Server facoltativamente un'istanza per il controllo del mirroring di SQL Server di conformità di backup di Persistent Chat.
  
Fare clic su **Indietro** per tornare alla finestra di dialogo per la definizione del pool precedente.
  
Fare clic su **Avanti** dopo aver immesso le opzioni per la configurazione dell'archivio SQL Server di backup di questo pool e per continuare con la definizione del pool di server Chat persistente.
  
Fare clic su **Annulla** per eliminare tutte le modifiche e chiudere la procedura guidata **Definisci nuovo pool Persistent Chat**.
  
Fare clic su **Guida** per accedere alla Guida sensibile al contesto, come questa pagina.
  
## <a name="see-also"></a>Vedere anche

[Pianificare il server Chat persistente in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Requisiti del server per Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Requisiti hardware e software per il server Chat persistente in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Configurare il servizio di conformità per il server Chat persistente in Skype for Business Server 2015](../../manage/persistent-chat/configure-compliance.md)
  
[Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
