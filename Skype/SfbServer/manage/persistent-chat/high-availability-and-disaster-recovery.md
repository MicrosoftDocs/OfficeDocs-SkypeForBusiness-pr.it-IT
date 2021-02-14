---
title: Gestire la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 'Riepilogo: informazioni su come gestire la disponibilità elevata e il ripristino di emergenza del server Chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: 7ec7182d8fe2866499f731b43df712a69c44bc42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815046"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Gestire la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server 2015
 
**Riepilogo:** Informazioni su come gestire la disponibilità elevata e il ripristino di emergenza del server Chat persistente in Skype for Business Server 2015.
  
In questo argomento viene descritto come eseguire il failover e il fail back del server Chat persistente. Prima di leggere questo argomento, leggere Pianificare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente [in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) e Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business Server [2015.](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

> [!NOTE]
> La chat persistente è disponibile in Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019. Le stesse funzionalità sono disponibili in Teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft Teams.](/microsoftteams/upgrade-start-here) Se è necessario usare Chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità a Teams o continuare a usare Skype for Business Server 2015. 
  
## <a name="fail-over-persistent-chat-server"></a>Failover del server Chat persistente

Il failover per il server Chat persistente è progettato principalmente come processo manuale.
  
La procedura di failover si basa sul presupposto che il data center secondario sia operativo, ma i servizi del server Chat persistente in cui si trova il database principale di Persistent Chat non sono completamente disponibili, tra cui:
  
- Il database primario del server Chat persistente e il database mirror del server Chat persistente non sono disponibili.
    
- Skype for Business Server Front End Server non è disponibile.
    
La procedura prevede due passaggi di base:
  
- Ripristinare il database principale di Persistent Chat (mgc).
    
- Configurazione del mirroring per il nuovo database primario.
    
Il database di conformità di Persistent Chat (mgccomp) non viene superato. Il contenuto di questo database è temporaneo e viene eliminato durante l'elaborazione dei dati nell'adattatore di conformità. L'amministratore di Persistent Chat deve gestire correttamente l'output dell'adattatore per evitare perdite di dati.
  
Per eseguire il failover del server Chat persistente:
  
1. Rimuovere il log shipping dal database di log shipping di backup del server Chat persistente.
    
   - Utilizzando SQL Server Management Studio, connettersi all'istanza del database in cui si trova il database mgc di backup del server Chat persistente.
    
   - Aprire una finestra di query nel database master.
    
   - Usare questo comando per eliminare la distribuzione dei log:
    
   ```SQL
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. Copiare i file di backup non copiati dalla condivisione di backup nella cartella di destinazione della copia del server di backup.
    
3. Applicare i backup dei log delle transazioni non applicati in sequenza al database secondario. Per informazioni dettagliate, vedere Procedura: Applicare un backup del log delle transazioni [(Transact-SQL).](https://go.microsoft.com/fwlink/p/?linkid=247428)
    
4. Connettere il database mgc di backup. Usando la finestra di query aperta al passaggio 1b, eseguire le operazioni seguenti:
    
   - Terminare tutte le connessioni al database mgc, se disponibili:
    
   - **exec sp_who2** identificare le connessioni al database mgc.
    
   - **kill \<spid\>** per terminare queste connessioni.
    
   - Connettere il database:
    
   - **restore database mgc with recovery**.
    
5. In Skype for Business Server Management Shell, utilizzare il comando **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** per eseguire il failover al database di backup mgc. Assicurarsi di sostituire il nome di dominio completo del pool di Persistent Chat per atl-cs-001.litwareinc.com.
    
    Il database mgc di backup funge ora da database primario.
    
6. In Skype for Business Server Management Shell, utilizzare il cmdlet **Install-CsMirrorDatabase** per stabilire un mirror a disponibilità elevata per il database di backup che ora funge da database primario. Usare l'istanza del database di backup come database primario e l'istanza del database mirror di backup come istanza mirror. Questo mirror non corrisponde al mirror configurato inizialmente per il database primario durante l'installazione.
    
7. Impostare i server attivi del server Chat persistente. Da Skype for Business Server Management Shell, utilizzare il cmdlet **Set-CsPersistentChatActiveServer** per impostare l'elenco dei server attivi.
    
    > [!IMPORTANT]
    > Tutti i server attivi devono trovarsi all'interno dello stesso data center del nuovo database primario o in un data center con una connessione a bassa latenza/larghezza di banda elevata al database. 
  
    A questo punto, il failover dal database primario del server Chat persistente al database di backup del server Chat persistente viene completato correttamente.
    
## <a name="fail-back-persistent-chat-server"></a>Fail back del server Chat persistente

In questa procedura vengono descritti i passaggi necessari per il ripristino da un errore del server Chat persistente e per ristabilire le operazioni dal data center principale.
  
Durante un errore del server Chat persistente, si verifica un'interruzione completa del data center principale e i database primario e mirror non sono più disponibili. Il centro dati principale esegue il failover al server di backup.
  
La procedura seguente consente di ripristinare l'operatività normale dopo il backup del centro dati principale e la ricostruzione dei server. Nella procedura si presuppone che il data center principale sia stato ripristinato dall'interruzione totale e che il database mgc e il database mgccomp siano stati ricostruiti e reinstallati utilizzando Generatore di topologie.
  
Nella procedura si presuppone inoltre che non siano stati distribuiti nuovi server mirror e di backup durante il periodo di failover e che l'unico server distribuito sia il server di backup e il relativo server mirror, come definito in precedenza in Failover del server Chat persistente.
  
Questi passaggi sono pensati per consentite il ripristino della configurazione esistente prima della situazione di emergenza che ha causato il failover dal server primario a quello di backup.
  
1. Cancellare tutti i server dall'elenco Active Server di Chat persistente utilizzando il cmdlet **Set-CsPersistentChatActiveServer** da Skype for Business Server Management Shell. Questo impedisce a tutti i server Chat persistente di connettersi al database mgc e al database mgccomp durante il failback.
    
    > [!IMPORTANT]
    > L'SQL Server sul server back-end del server Chat persistente secondario deve essere in esecuzione con un account privilegiato. In particolare, l'account deve disporre di: 
  
   - Accesso in lettura alla condivisione di rete in cui vengono posizionati i backup.
    
   - Accesso in scrittura alla directory locale specifica in cui vengono copiati i backup.
    
2. Disabilitare il mirroring nel database mgc di backup:
    
   - Utilizzando SQL Server Management Studio, connettersi all'istanza mgc di backup.
    
   - Fare clic con il pulsante destro del mouse sul database mgc, scegliere **Attività** e quindi fare clic su **Server mirror**.
    
   - Fare clic su **Rimuovi mirroring**.
    
   - Fare clic su **OK**.
    
   - Eseguire gli stessi passaggi con il database mgccomp.
    
3. Eseguire il backup del database mgc in modo che possa essere ripristinato nel nuovo database primario:
    
   - Utilizzando SQL Server Management Studio, connettersi all'istanza mgc di backup.
    
   - Fare clic con il pulsante destro del mouse sul database mgc, scegliere **Attività** e quindi fare clic su **Backup**. Verrà visualizzata la finestra di dialogo **Backup database**.
    
   - In **Tipo backup** selezionare **Completo**.
    
   - In **Componente di cui eseguire il backup** fare clic su **Database**.
    
   - Accettare il nome del set di backup predefinito indicato in **Nome** oppure immettere un nome diverso per il set di backup.
    
   -  *\<Optional\>*  In **Descrizione** immettere una descrizione del set di backup.
    
   - Rimuovere il percorso di backup predefinito dall'elenco di destinazione.
    
   - Aggiungere un file all'elenco utilizzando il percorso della posizione condivisa stabilita per il log shipping. Questo percorso è disponibile per il database primario e quello di backup.
    
   - Fare clic su **OK** per chiudere la finestra di dialogo e avviare il processo di backup.
    
4. Ripristinare il database primario utilizzando il database di backup creato nel passaggio precedente.
    
   - Usando SQL Server Management Studio, connettersi all'istanza mgc principale.
    
   - Fare clic con il pulsante destro del mouse sul database mgc, scegliere **Attività**, **Ripristina** e quindi fare clic su **Database**. Verrà visualizzata la finestra di dialogo **Ripristina database**.
    
   - Selezionare **Dispositivo di origine**.
    
   - Fare clic sul pulsante Sfoglia per aprire la finestra di dialogo **Seleziona backup**. In **Supporti di backup** selezionare **File**. Fare clic su **Aggiungi**, selezionare il file di backup creato nel passaggio 3 e quindi fare clic su **OK**.
    
   - In **Selezionare i set di backup da ripristinare** selezionare il backup.
    
   - Fare clic su **Opzioni** nel riquadro **Selezione pagina**.
    
   - In **Opzioni di ripristino** selezionare **Sovrascrivi il database esistente**.
    
   - In **Stato di recupero** selezionare **Lascia il database pronto per l'utilizzo**.
    
   - Fare clic su **OK** per avviare il processo di ripristino.
    
5. Configurare SQL Server log shipping per il database primario. Seguire le procedure descritte in Configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente [in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) per stabilire il log shipping per il database mgc primario.
    
6. Impostare i server attivi del server Chat persistente. Da Skype for Business Server Management Shell, utilizzare il cmdlet **Set-CsPersistentChatActiveServer** per impostare l'elenco dei server attivi.
    
    > [!IMPORTANT]
    > Tutti i server attivi devono trovarsi all'interno dello stesso data center del nuovo database primario o in un data center con una connessione a bassa latenza/larghezza di banda elevata al database. 
  
Per ripristinare lo stato normale del pool, eseguire il comando Windows PowerShell seguente:
  
```PowerShell
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsPersistentChatState.](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps)
  

