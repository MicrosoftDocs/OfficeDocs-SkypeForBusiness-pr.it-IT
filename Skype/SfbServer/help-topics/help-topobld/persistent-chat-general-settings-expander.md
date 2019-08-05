---
title: Espansione delle impostazioni generali di Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 'È possibile modificare le impostazioni generali per il server di chat persistente o il pool di server di chat persistente configurando o definendo queste proprietà:'
ms.openlocfilehash: c79ef61e2b7609aa344766c37cf38adaa195f23d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191642"
---
# <a name="persistent-chat-general-settings-expander"></a>Espansione delle impostazioni generali di Persistent Chat
 
È possibile modificare le impostazioni **generali** per il server di chat persistente o il pool di server di chat persistente configurando o definendo queste proprietà:
  
 **Generale**
  
- **FQDN**: modificare questa impostazione per definire il nome di dominio completo del server di chat persistente o del pool di server di chat persistente
    
- **Nome visualizzato del pool di Chat persistente**: definire questa impostazione del server o del pool specificando un nome facile da leggere e comprendere per gli utenti. Questa impostazione rende più facile per gli utenti associare un server di chat persistente o un pool di server di chat persistente in base al nome visualizzato invece di un nome di dominio completo più difficile da comprendere.
    
- **Porta di Chat persistente**: specificare la porta da usare per la chat persistente.
    
È possibile modificare le impostazioni delle **associazioni** per il server di chat persistente o il pool di server di chat persistente configurando o definendo queste proprietà:
  
 **Associazioni**
  
- **Archivio SQL Server**: selezionare l'archivio SQL Server e l'istanza denominata facoltativa nell'elenco.
    
    Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa.
    
- Selezionare la casella di controllo **Abilita mirroring di SQL Server Store** se si vuole abilitare il mirroring per l'archivio principale di SQL Server.
    
    Se si è scelto di abilitare il mirroring di SQL Server Store, selezionare lo Store e l'istanza dall'elenco mirroring di **SQL Server Store**.
    
    Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa.
    
- Selezionare la casella **di controllo Usa verifica mirroring di SQL Server per abilitare il failover automatico** se si vuole eseguire il failover automatico dell'archivio principale di SQL Server.
    
    Se si è scelto di abilitare il mirroring di SQL Server Store per consentire il failover automatico, selezionare lo Store e l'istanza nell'elenco.
    
    Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa per l'archivio di controllo.
    
- Selezionare la casella **di controllo Usa gli archivi di SQL Server di backup per abilitare il ripristino di emergenza** se si vuole abilitare l'uso del ripristino di emergenza di SQL Server
    
    Se si è scelto di abilitare il ripristino di emergenza, selezionare un archivio e un'istanza nell'elenco **Archivio SQL Server backup**.
    
    Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa.
    
- Selezionare la casella di controllo **Abilita mirroring di SQL Server Store** se si vuole abilitare il mirroring per l'archivio di mirroring di SQL Server di backup.
    
    Se si è scelto di abilitare il mirroring di SQL Server Store di backup, selezionare lo Store e l'istanza dal mirror di backup dell'elenco di **SQL Server Store**.
    
    Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa.
    
- Selezionare la casella **di controllo Usa verifica mirroring di SQL Server per abilitare il failover automatico** se si vuole eseguire il failover automatico dell'archivio di SQL Server di backup.
    
    Se si è scelto di abilitare il mirroring di SQL Server Store per consentire il failover automatico, selezionare lo Store e l'istanza nell'elenco.
    
    Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa per l'archivio di controllo.
    
- Selezionare la casella di controllo **Abilita conformità** per consentire l'uso di un database di conformità.
    
    Se si è scelto di abilitare la conformità, selezionare un archivio e un'istanza nell'elenco **Archivio SQL Server conformità**.
    
    Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa.
    
- Selezionare la casella di controllo **Abilita mirroring di SQL Server Store** se si vuole abilitare il mirroring per la conformità a SQL Server Store.
    
    Se si è scelto di abilitare il mirroring di SQL Server Store Compliance, selezionare lo Store e l'istanza dal **mirror di SQL Server Store Compliance**List.
    
    Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa.
    
- Selezionare la casella **di controllo Usa verifica mirroring di SQL Server per abilitare il failover automatico** se si vuole eseguire il failover automatico della conformità di SQL Server Store.
    
    Se si è scelto di abilitare il mirroring di SQL Server Store per consentire il failover automatico, selezionare lo Store e l'istanza nell'elenco.
    
    Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa per l'archivio di controllo.
    
- Se si è scelto di abilitare la conformità, selezionare un archivio e un'istanza nell'elenco **Archivio SQL Server conformità backup**.
    
    Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa.
    
- Selezionare la casella di controllo **Abilita mirroring di SQL Server Store** se si vuole abilitare il mirroring per la conformità a SQL Server Store.
    
    Se si è scelto di abilitare il mirroring di SQL Server Store Compliance, selezionare lo Store e l'istanza dal **mirror di SQL Server Store Compliance list backup**.
    
    Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa.
    
- Selezionare la casella **di controllo Usa il witness di mirroring di SQL Server per abilitare il failover automatico** se si vuole eseguire il failover automatico dell'archivio di SQL server Compliance backup.
    
    Se si è scelto di abilitare il mirroring di SQL Server Store per consentire il failover automatico, selezionare lo Store e l'istanza nell'elenco.
    
    Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa per l'archivio di controllo.
    
- **Archivio file** Selezionare una posizione di archivio file nell'elenco oppure fare clic su **nuovo** per creare un nuovo archivio di file.
    
  **OK** Consente di accettare e salvare le modifiche nella finestra di dialogo.
  
  **Annulla** Consente di eliminare le modifiche e di chiudere la finestra di dialogo.
  
  **Guida** Consente di visualizzare questa schermata della Guida.
  
## <a name="see-also"></a>Vedere anche

[Pianificare il server Chat persistente in Skype per Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Aggiungere il server di chat persistente alla topologia di Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
