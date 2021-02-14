---
title: Espansione delle impostazioni generali di Persistent Chat
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
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 'È possibile modificare le impostazioni generali per il server Chat persistente o il pool di server Chat persistente configurando o definendo queste proprietà:'
ms.openlocfilehash: 5c0884f4877e622a82b58ea914ffa934eecc3291
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823855"
---
# <a name="persistent-chat-general-settings-expander"></a>Espansione delle impostazioni generali di Persistent Chat
 
È possibile modificare **le impostazioni** generali per il server Chat persistente o il pool di server Chat persistente configurando o definendo queste proprietà:
  
 **Generale**
  
- **FQDN:** modificare questa impostazione per definire il nome di dominio completo del server Chat persistente o del pool di server Chat persistente
    
- **Nome visualizzato del pool Persistent Chat**: definire questa impostazione del server o del pool specificando un nome facile da leggere e comprendere per gli utenti. Questa impostazione agevola l'associazione di un determinato server Chat persistente o pool di server Chat persistente in base al nome visualizzato anziché a un nome di dominio completo più difficile da comprendere.
    
- **Porta Persistent Chat**: specificare la porta da usare per la chat persistente.
    
È possibile modificare **le impostazioni** delle associazioni per il server Chat persistente o il pool di server Chat persistente configurando o definendo queste proprietà:
  
 **Associazioni**
  
- **SQL Server store:** selezionare l'SQL Server store e l'istanza denominata facoltativa dall'elenco.
    
    Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa.
    
- Selezionare la **casella di controllo SQL Server mirroring dell'archivio** se si desidera abilitare il mirroring per l'SQL Server principale.
    
    Se si è scelto di abilitare SQL Server mirroring dell'archivio, selezionare l'archivio e l'istanza nell'elenco **Mirroring SQL Server store.**
    
    Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa.
    
- Selezionare la **casella di SQL Server controllo del mirroring** per abilitare il failover automatico se si desidera il failover automatico dell'SQL Server principale.
    
    Se si è scelto di abilitare il SQL Server mirroring dell'archivio per abilitare il failover automatico, selezionare l'archivio e l'istanza nell'elenco.
    
    Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa per l'archivio di controllo.
    
- Selezionare la **casella di controllo Usa archivi SQL Server backup** per abilitare il ripristino di emergenza se si desidera abilitare l'utilizzo SQL Server ripristino di emergenza
    
    Se si è scelto di abilitare il ripristino di emergenza, selezionare un archivio e un'istanza nell'elenco **Archivio SQL Server backup**.
    
    Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa.
    
- Selezionare la **casella di SQL Server di mirroring** dell'archivio se si desidera abilitare il mirroring per l'SQL Server di mirroring di backup.
    
    Se si è scelto di abilitare il mirroring dell SQL Server di archiviazione, selezionare l'archivio e l'istanza nell'elenco **Backup SQL Server mirror dell'archivio.**
    
    Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa.
    
- Selezionare la **casella di SQL Server controllo del mirroring** per abilitare il failover automatico se si desidera il failover automatico dell'archivio SQL Server backup.
    
    Se si è scelto di abilitare il SQL Server mirroring dell'archivio per abilitare il failover automatico, selezionare l'archivio e l'istanza nell'elenco.
    
    Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa per l'archivio di controllo.
    
- Selezionare la casella di controllo **Abilita conformità** per consentire l'uso di un database di conformità.
    
    Se si è scelto di abilitare la conformità, selezionare un archivio e un'istanza nell'elenco **Archivio SQL Server conformità**.
    
    Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa.
    
- Selezionare la **casella di controllo SQL Server mirroring dell'archivio** se si desidera abilitare il mirroring per l'archivio SQL Server conformità.
    
    Se si è scelto di abilitare il mirroring SQL Server store, selezionare l'archivio e l'istanza nell'elenco **SQL Server mirror dell'archivio.**
    
    Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa.
    
- Selezionare la **casella di SQL Server controllo del mirroring** per abilitare il failover automatico se si desidera il failover automatico dell'archivio SQL Server conformità.
    
    Se si è scelto di abilitare il SQL Server mirroring dell'archivio per abilitare il failover automatico, selezionare l'archivio e l'istanza nell'elenco.
    
    Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa per l'archivio di controllo.
    
- Se si è scelto di abilitare la conformità, selezionare un archivio e un'istanza nell'elenco **Archivio SQL Server conformità backup**.
    
    Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa.
    
- Selezionare la **casella di controllo SQL Server mirroring dell'archivio** se si desidera abilitare il mirroring per l'archivio SQL Server conformità.
    
    Se si è scelto di abilitare il mirroring SQL Server dell'archivio, selezionare l'archivio e l'istanza nell'elenco **Backup SQL Server mirror dell'archivio.**
    
    Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa.
    
- Selezionare la **casella di SQL Server controllo del mirroring** per abilitare il failover automatico se si desidera il failover automatico dell'archivio di conformità SQL Server backup.
    
    Se si è scelto di abilitare il SQL Server mirroring dell'archivio per abilitare il failover automatico, selezionare l'archivio e l'istanza nell'elenco.
    
    Fare clic su **Nuovo** per definire un nuovo archivio SQL Server e una nuova istanza facoltativa per l'archivio di controllo.
    
- **Archivio file** Selezionare un percorso di archivio file nell'elenco oppure fare clic su **Nuovo** per creare un nuovo archivio file.
    
  **OK** Accetta le modifiche apportate nella finestra di dialogo e ne esegue il commit.
  
  **Annulla** Rimuove le modifiche e chiude la finestra di dialogo.
  
  **?** Visualizza questa schermata della Guida.
  
## <a name="see-also"></a>Vedere anche

[Pianificare il server Chat persistente in Skype for Business Server](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Aggiungere il server Chat persistente alla topologia di Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
