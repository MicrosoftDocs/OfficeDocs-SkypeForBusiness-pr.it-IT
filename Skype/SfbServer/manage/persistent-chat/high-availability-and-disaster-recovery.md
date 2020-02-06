---
title: Gestire la disponibilità elevata e il ripristino di emergenza per il server Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 'Riepilogo: informazioni su come gestire la disponibilità elevata e il ripristino di emergenza del server di chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: ea81f72dfa65fd350b7c8b8c3aaf61bee6999b34
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817227"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Gestire la disponibilità elevata e il ripristino di emergenza per il server Chat persistente
 
**Riepilogo:** Informazioni su come gestire la disponibilità elevata e il ripristino di emergenza del server di chat persistente in Skype for Business Server 2015.
  
Questo argomento descrive come eseguire il failover e il failover del server di chat persistente. Prima di leggere questo argomento, leggere [piano per la disponibilità elevata e il ripristino di emergenza per il server di chat persistente in Skype for Business server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) e [configurare l'elevata disponibilità e il ripristino di emergenza per il server di chat persistente in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).

> [!NOTE]
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015. 
  
## <a name="fail-over-persistent-chat-server"></a>Failover del server di chat persistente

Il failover per il server di chat persistente è progettato per essere principalmente un processo manuale.
  
La procedura di failover si basa sul presupposto che il data center secondario sia attivo e funzionante, ma i servizi di Persistent Chat Server in cui si trova il database principale della chat persistente sono completamente non disponibili, inclusi i seguenti:
  
- Il database primario del server Chat persistente e il database mirror del server di chat persistente non sono disponibili.
    
- Il server front-end di Skype for Business Server non è più presente.
    
La procedura si basa su due passaggi di base:
  
- Recuperare il database principale della chat persistente (MGC).
    
- Stabilire il mirroring per il nuovo database primario.
    
Il database di conformità della chat persistente (mgccomp) non viene superato. Il contenuto di questo database è temporaneo e viene eliminato quando l'adattatore di conformità elabora i dati. È tua responsabilità, come amministratore della chat persistente, gestire correttamente l'output della scheda per evitare perdite di dati.
  
Per eseguire il failover del server di chat persistente:
  
1. Rimuovere il log shipping dal database di log shipping del server di backup di Persistent Chat.
    
   - In SQL Server Management Studio connettersi all'istanza del database in cui si trova il database di backup di MGC del server di chat persistente.
    
   - Aprire una finestra di query nel database master.
    
   - Usare il comando seguente per eliminare il log shipping:
    
   ```SQL
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. Copiare i file di backup non copiati dalla condivisione di backup alla cartella di destinazione della copia del server di backup.
    
3. Applicare i backup del log delle transazioni non applicati in sequenza al database secondario. Per informazioni dettagliate, vedere [procedura: applicare un backup del log delle transazioni (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).
    
4. Porta il database di backup MGC online. Usando la finestra della query visualizzata nel passaggio 1b, eseguire le operazioni seguenti:
    
   - Terminare tutte le connessioni al database di MGC, se presenti:
    
   - **sp_who2 EXEC** per identificare le connessioni al database di MGC.
    
   - **uccidere \<SPID\> ** per terminare queste connessioni.
    
   - Porta il database online:
    
   - **ripristinare il database di MGC con il ripristino**.
    
5. In Skype for Business Server Management Shell usare il comando **Set-CsPersistentChatState-Identity "Service: atl-cs-001.litwareinc.com"-PoolState FailedOver** per eseguire il failover nel database di backup di MGC. Assicurarsi di sostituire il nome di dominio completo del pool di chat persistente per atl-cs-001.litwareinc.com.
    
    Il database di backup di MGC ora funge da database primario.
    
6. In Skype for Business Server Management Shell usare il cmdlet **Install-CsMirrorDatabase** per stabilire un mirror di disponibilità elevata per il database di backup che ora funge da database primario. Usa l'istanza del database di backup come database principale e l'istanza del database mirror di backup come istanza di mirror. Questo non è lo stesso mirror di quello inizialmente configurato per il database principale durante l'installazione.
    
7. Impostare i server attivi della chat persistente. Da Skype for Business Server Management Shell, usa il cmdlet **Set-CsPersistentChatActiveServer** per impostare l'elenco dei server attivi.
    
    > [!IMPORTANT]
    > Tutti i server attivi devono essere posizionati all'interno dello stesso centro dati del nuovo database primario o in un centro dati con una connessione a una larghezza di banda ridotta o a un'altezza elevata del database. 
  
    A questo punto, il failover dal database primario del server di chat persistente al database di backup del server di chat persistente viene completato correttamente.
    
## <a name="fail-back-persistent-chat-server"></a>Non ripristinare il server di chat persistente

Questa procedura descrive i passaggi necessari per il ripristino da un errore del server di chat persistente e per ristabilire le operazioni dal centro dati principale.
  
Durante l'errore del server di chat persistente, il centro dati principale soffre l'interruzione completa e i database primari e mirror diventano non disponibili. Il data center principale viene superato nel server di backup.
  
La procedura seguente ripristina il normale funzionamento dopo il backup del data center principale e i server sono stati ricompilati. La procedura presuppone che il centro dati principale sia stato recuperato dall'interruzione totale e che il database di MGC e il database di mgccomp siano stati ricostruiti e reinstallati usando generatore di topologie.
  
La procedura presuppone inoltre che non siano stati distribuiti nuovi mirror e server di backup durante il periodo di failover e che l'unico server distribuito sia il server di backup e il relativo server mirror, come definito in precedenza in fail over Persistent Chat Server.
  
Questi passaggi sono progettati per recuperare la configurazione come esisteva prima del disastro, causando il failover dal server primario al server di backup.
  
1. Cancellare tutti i server dall'elenco Active server Chat persistente usando il cmdlet **Set-CsPersistentChatActiveServer** di Skype for Business Server Management Shell. In questo articolo vengono arrestati tutti i server di chat persistenti che si connettono al database mgc e mgccomp durante il failback.
    
    > [!IMPORTANT]
    > L'agente SQL Server nel server di chat secondario persistente deve essere in uso in un account con privilegi. In particolare, l'account deve includere: 
  
   - Accesso in lettura alla condivisione di rete in cui vengono inseriti i backup.
    
   - Accesso in scrittura alla directory locale specifica in cui vengono copiati i backup.
    
2. Disabilitare il mirroring nel database di backup MGC:
    
   - Con SQL Server Management Studio connettersi all'istanza di backup MGC.
    
   - Fare clic con il pulsante destro del mouse sul database di MGC, scegliere **attività**e quindi fare clic su **Specchia**.
    
   - Fare clic su **Rimuovi mirroring**.
    
   - Fare clic su **OK**.
    
   - Eseguire gli stessi passaggi con il database mgccomp.
    
3. Eseguire il backup del database di MGC in modo che possa essere ripristinato nel nuovo database primario:
    
   - Con SQL Server Management Studio connettersi all'istanza di backup MGC.
    
   - Fare clic con il pulsante destro del mouse sul database di MGC, scegliere **attività**e quindi fare clic su **backup**. Verrà visualizzata la finestra di dialogo **backup database** .
    
   - In **tipo di backup**selezionare **completo**.
    
   - Per il **componente backup**fare clic su **database**.
    
   - Accettare il nome predefinito del set di backup consigliato in **nome**o immettere un nome diverso per il set di backup.
    
   -  * \<Facoltativo\> *  In **Descrizione**immettere una descrizione del set di backup.
    
   - Rimuovere la posizione di backup predefinita dall'elenco di destinazione.
    
   - Aggiungere un file all'elenco usando il percorso della posizione di condivisione stabilita per il log shipping. Questo percorso è disponibile per il database principale e per il database di backup.
    
   - Fare clic su **OK** per chiudere la finestra di dialogo e avviare il processo di backup.
    
4. Ripristinare il database principale usando il database di backup creato nel passaggio precedente.
    
   - Con SQL Server Management Studio, connettersi all'istanza di MGC primaria.
    
   - Fare clic con il pulsante destro del mouse sul database di MGC, scegliere **attività**, scegliere **Ripristina**e quindi fare clic su **database**. Verrà visualizzata la finestra di dialogo **Ripristina database** .
    
   - Selezionare **da dispositivo**.
    
   - Fare clic sul pulsante Sfoglia, che apre la finestra di dialogo **specifica backup** . In **supporto di backup**selezionare **file**. Fare clic su **Aggiungi**, selezionare il file di backup creato nel passaggio 3 e quindi fare clic su **OK**.
    
   - In **selezionare i set di backup da ripristinare**selezionare il backup.
    
   - Fare clic su **Opzioni** nel riquadro **Seleziona pagina** .
    
   - In **Opzioni di ripristino**selezionare **sovrascrivere il database esistente**.
    
   - In **stato di ripristino**selezionare **lascia il database pronto per l'uso**.
    
   - Fare clic su **OK** per avviare il processo di ripristino.
    
5. Configurare la distribuzione del log di SQL Server per il database principale. Seguire le procedure descritte in [configurare la disponibilità elevata e il ripristino di emergenza per il server di chat persistente in Skype for Business server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) per stabilire la distribuzione del log per il database mgc principale.
    
6. Impostare i server attivi della chat persistente. Da Skype for Business Server Management Shell, usa il cmdlet **Set-CsPersistentChatActiveServer** per impostare l'elenco dei server attivi.
    
    > [!IMPORTANT]
    > Tutti i server attivi devono essere posizionati all'interno dello stesso centro dati del nuovo database primario o in un centro dati con una connessione a una larghezza di banda ridotta o a un'altezza elevata del database. 
  
Per ripristinare lo stato normale del pool, eseguire il comando di Windows PowerShell seguente:
  
```PowerShell
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) .
  

