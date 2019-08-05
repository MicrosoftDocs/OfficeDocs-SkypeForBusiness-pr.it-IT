---
title: Aggiungere l'archivio SQL Server di backup per Conformità chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: Si configurano gli archivi di SQL Server per la conformità del backup che forniranno database di backup per il server di chat persistente o per gli archivi di SQL Server di Persistent Chat
ms.openlocfilehash: 457874f87266453939c75cdef50d30231d8610bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187958"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a>Aggiungere l'archivio SQL Server di backup per Conformità chat persistente
 
Si configurano gli archivi di SQL Server per la conformità del backup che forniranno database di backup per il server di chat persistente o per gli archivi di SQL Server di Persistent Chat
  
 **SQL Server Store**: selezionare un server SQL esistente e, facoltativamente, un'istanza per la chat persistente.
  
Fare clic su **nuovo** per definire un nuovo SQL Server e facoltativamente una nuova istanza per i dati di conformità del backup della chat persistente.
  
Selezionare la casella di controllo **Abilita mirroring di SQL Server Store** per configurare un database di SQL Server e un'istanza facoltativa che fornirà un database con mirroring per i dati di conformità del backup della chat persistente.
  
Selezionare nell'elenco mirroring di **SQL Server archiviare** un'istanza di SQL Server e facoltativa per fungere da mirror di SQL Server per la conformità a SQL Server per il backup della chat persistente.
  
Fare clic su **nuovo** per definire un nuovo SQL Server e, facoltativamente, una nuova istanza per il mirroring della chat persistente in SQL Server.
  
Nell'elenco **Usa controllo del mirroring di SQL Server per abilitare il failover automatico** selezionare un server SQL Server che fungerà da server di controllo negli scenari di failover. Il server di controllo non rispecchia né ospita i dati per i server di chat persistenti, ma garantisce che solo un server SQL in una configurazione con mirroring sia il server SQL attivo in qualsiasi momento.
  
Fare clic su **nuovo** per definire una nuova testimonianza di SQL Server facoltativamente un'istanza per il witness di SQL Server mirroring di conformità della chat persistente.
  
Fare clic su **Indietro** per tornare alla precedente finestra di dialogo per la definizione del pool.
  
Fare clic su **Avanti** dopo aver completato l'immissione delle opzioni per la configurazione del backup di SQL Server Store di questo pool e per procedere con la definizione del pool del server di chat persistente.
  
Fare clic su **Annulla** per eliminare tutte le modifiche e chiudere la procedura guidata **Definisci nuovo pool di Chat persistente**.
  
Fare clic su **?** per accedere alla Guida sensibile al contesto, come questa pagina.
  
## <a name="see-also"></a>Vedere anche

[Pianificare il server Chat persistente in Skype per Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Requisiti server di Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Requisiti hardware e software per il server Chat persistente](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Configurare il servizio Conformità per il server Chat persistente](../../manage/persistent-chat/configure-compliance.md)
  
[Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
