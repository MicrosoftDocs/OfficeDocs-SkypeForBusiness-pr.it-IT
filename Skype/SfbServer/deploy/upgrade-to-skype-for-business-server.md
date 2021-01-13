---
title: Eseguire l'aggiornamento a Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/14/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: "Riepilogo: informazioni su come eseguire l'aggiornamento da Lync Server 2013 a Skype for Business Server 2015. Scaricare una versione di valutazione gratuita di Skype for Business Server 2015 da Microsoft Evaluation Center all'indirizzo: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server ."
ms.openlocfilehash: cda83d03db697a0adf404af4f6fe6e350abf6b58
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820426"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a>Eseguire l'aggiornamento a Skype for Business Server 2015
 
**Riepilogo:** Informazioni su come eseguire l'aggiornamento da Lync Server 2013 a Skype for Business Server 2015. Scaricare una versione di valutazione gratuita di Skype for Business Server 2015 da  [Microsoft Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Utilizzare le procedure descritte in questo documento per eseguire l'aggiornamento da Lync Server 2013 a Skype for Business Server 2015 mediante il generatore di topologie di Skype for Business Server e la nuova funzionalità di aggiornamento In-Place. Se si desidera eseguire l'aggiornamento da Lync Server 2010 o Office Communications Server 2007 R2, vedere [plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).

> [!NOTE]
> Gli aggiornamenti sul posto sono disponibili in Skype for Business Server 2015 ma non sono più supportati in Skype for Business Server 2019. La coesistenza fianco a fianco è supportata, vedere [Migration to Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) per ulteriori informazioni.
  
## <a name="upgrade-from-lync-server-2013"></a>Eseguire l'aggiornamento da Lync Server 2013

L'aggiornamento di Lync Server 2013 a Skype for Business Server 2015 implica l'installazione del software prerequisito, l'utilizzo del generatore di topologie di Skype for Business Server per l'aggiornamento dei database nel pool e l'utilizzo dell'aggiornamento In-Place di Skype for Business Server in ogni server associato al pool. Per completare l'aggiornamento, passare attraverso gli otto passaggi di questo argomento.
  
### <a name="before-you-begin"></a>Prima di iniziare

- Esaminare il [piano per l'aggiornamento a Skype for Business Server 2015](../plan-your-deployment/upgrade.md).
    
- Esaminare [i requisiti del server per Skype for Business server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- [Installare i prerequisiti per Skype for Business Server 2015](install/install-prerequisites.md) .
    
- [Installare Skype for Business Server 2015](install/install.md) .
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a>Passaggio 1: installare gli strumenti di amministrazione e scaricare la topologia

1. Connettersi a un computer nella topologia che non dispone di Lync OCSCore o di altri componenti di Lync installati.
    
2. Dal supporto di installazione di Skype for Business Server 2015, eseguire **Setup.exe** da **OCS_Volume \Setup\amd64**. 
    
3. Fare clic su **Installa**. 
    
4. Accettare il contratto di licenza.
    
5. Nella distribuzione guidata fare clic su **installa strumenti di amministrazione** e seguire i passaggi da installare.
    
     ![Schermata della distribuzione guidata con collegamento agli strumenti di amministratore di installazione richiamati.](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. Dalla schermata Start di Windows, aprire Generatore di topologie di Skype for Business Server.
    
7. Fare clic su **Scarica topologia dalla distribuzione esistente** e quindi fare clic su **Avanti**.
    
8. Immettere un nome per la topologia e fare clic su **Salva**.
    
9. Passare alla posizione in cui è stata salvata la topologia e creare una copia della topologia.
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a>Passaggio 2: aggiornare e pubblicare la topologia tramite Generatore di topologie

Prima di avviare il processo di aggiornamento, tutti i servizi devono essere in esecuzione per i pool che si intende aggiornare. Questo è il modo in cui le modifiche alla topologia verranno replicate nel database locale dei server del pool.
  
> [!IMPORTANT]
>  Salvare una copia del file di topologia prima di eseguire l'aggiornamento. Dopo aver eseguito l'aggiornamento, non sarà possibile eseguire il downgrade della topologia. > se i servizi sono nello stesso server dei database, come il servizio chat persistente si trova nello stesso server del database di chat persistente, ignorare questo passaggio e passare al passaggio 4. Dopo aver interrotto i servizi, eseguire il programma di installazione di In-Place upgrade su ogni server per aggiornare i database locali.
  
> [!NOTE]
> Se la topologia include un database back-end con mirroring, sarà possibile visualizzare sia l'entità che i database con mirroring **quando si pubblica la topologia** tramite Generatore di topologie. Verificare che tutti i database siano in esecuzione nell'entità e selezionare solo l'entità, non il mirror, durante la pubblicazione della topologia, altrimenti verrà visualizzato un messaggio di avviso dopo la pubblicazione della topologia.
  
Scegliere una delle opzioni seguenti per eseguire l'aggiornamento e la pubblicazione di una nuova topologia utilizzando il generatore di topologie di Skype for Business Server 2015. Dopo aver completato la procedura e aver pubblicato la topologia aggiornata, passare al passaggio 3 di questo argomento.
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a>Opzione 1: aggiornare un pool Front End isolato e gli archivi associati di archiviazione e monitoraggio

Se il pool che si sta aggiornando ha una dipendenza dell'archivio di archiviazione e di monitoraggio, quando si utilizzano i passaggi seguenti, verrà aggiornato anche l'archivio di archiviazione e di monitoraggio.
  
1. In Generatore di topologie fare clic con il pulsante destro del mouse su un pool di Lync Server 2013, scegliere **Aggiorna a Skype for Business server 2015** e seguire la procedura. 
    
     ![Schermata del menu con il pulsante destro del mouse con l'opzione di aggiornamento per Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. In Generatore di topologie, fare clic su **azione** pubblicare la  >  **topologia** o la topologia di **azione**  >    >  . 
    
     ![Schermata del menu azione con opzione di pubblicazione della topologia in Generatore di topologie.](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. Durante la pubblicazione, scegliere di installare un database nell'archivio di archiviazione e monitoraggio.
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a>Opzione 2: aggiornare il pool Front end senza aggiornare gli archivi di archiviazione e monitoraggio

Se si utilizzano i passaggi seguenti, l'archiviazione e il monitoraggio per il pool selezionato sono disattivati. Dopo l'aggiornamento, il pool non avrà archivi di archiviazione e monitoraggio.
  
1. In Generatore di topologie selezionare il pool di Lync Server 2013 che si desidera aggiornare.
    
2. Rimuovere la dipendenza dagli archivi di archiviazione e monitoraggio di Lync Server 2013. 
    
   - Passare a   >  **proprietà modifica** azione.
    
   - Deselezionare la casella di controllo **archiviazione** .
    
     ![Schermata della casella di controllo archiviazione nella finestra di dialogo Modifica proprietà.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - Deselezionare la casella di controllo **monitoraggio** .
    
     ![Schermata della finestra di dialogo Modifica proprietà che Visualizza il Monitoring CheckBox.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Fare clic con il pulsante destro del mouse sul pool Lync Server 2013, scegliere **Aggiorna a Skype for Business server 2015** e seguire la procedura. 
    
     ![Schermata del menu con il pulsante destro del mouse con l'opzione di aggiornamento per Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. In Generatore di topologie, fare clic su **azione** pubblicare la  >  **topologia** o la topologia di **azione**  >    >  . 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a>Opzione 3: aggiornare il pool Front end e associarlo ai nuovi archivi di archiviazione e monitoraggio di Skype for Business Server 2015

Se si utilizzano i passaggi seguenti, l'archiviazione e il monitoraggio verranno arrestati nell'archivio precedente e iniziati nel nuovo archivio creato. 
  
1. In Generatore di topologie selezionare il pool di Lync Server 2013 che si desidera aggiornare. 
    
2. Rimuovere la dipendenza dagli archivi di archiviazione e monitoraggio di Lync Server 2013. 
    
   - Passare a   >  **proprietà modifica** azione.
    
   - Deselezionare la casella di controllo **archiviazione** .
    
     ![Schermata della casella di controllo archiviazione nella finestra di dialogo Modifica proprietà.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - Deselezionare la casella di controllo **monitoraggio** .
    
     ![Schermata della finestra di dialogo Modifica proprietà che Visualizza il Monitoring CheckBox.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Fare clic con il pulsante destro del mouse sul pool Lync Server 2013, scegliere **Aggiorna a Skype for Business server 2015** e seguire la procedura. 
    
     ![Schermata del menu con il pulsante destro del mouse con l'opzione di aggiornamento per Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. Creare un nuovo archivio SQL per l'archiviazione. 
    
   - Selezionare le proprietà di modifica del pool e dell' **azione**  >  . 
    
   -  Selezionare la casella di controllo **archiviazione** .
    
   - Fare clic su **Nuova regola**.
    
     ![Schermata della finestra di dialogo Modifica proprietà in cui viene visualizzato nuovo pulsante nella sezione archiviazione.](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. Creare un nuovo archivio SQL per il monitoraggio. 
    
   - Selezionare le proprietà di modifica del pool e dell' **azione**  >  . 
    
   -  Selezionare la casella di controllo **monitoraggio** .
    
   - Fare clic su **Nuova regola**.
    
     ![Schermata della finestra di dialogo Modifica proprietà in cui viene visualizzato nuovo pulsante nella sezione monitoraggio.](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. In Generatore di topologie, fare clic su **azione** pubblicare la  >  **topologia** o la topologia di **azione**  >    >  . 
    
7. Durante la pubblicazione, scegliere di installare il database nel nuovo archivio di archiviazione e monitoraggio.
    
### <a name="step-3-wait-for-replication"></a>Passaggio 3: attendere la replica

Fornire alla replica un po' di tempo per pubblicare la topologia aggiornata in tutti i server dell'ambiente.
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a>Passaggio 4: arrestare tutti i servizi nel pool per l'aggiornamento

In ogni server che esegue la manutenzione del pool che si desidera aggiornare, eseguire il cmdlet seguente in PowerShell:
  
```powershell
Disable-CsComputer -Scorch
```

È consigliabile utilizzare Disable-CsComputer perché potrebbe essere necessario riavviare il server durante il processo di aggiornamento In-Place. Se si utilizza Stop-CsWindowsService, è possibile che alcuni servizi vengano riavviati automaticamente dopo un riavvio. Ciò potrebbe causare l'esito negativo dell'aggiornamento In-Place.
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a>Passaggio 5: aggiornare i pool Front end e i server del pool non front-end

> [!NOTE]
>  Prima dell'aggiornamento, installare tutti i nuovi prerequisiti richiesti per Skype for Business Server 2015 che includono: > almeno 32GB di spazio libero prima di tentare un aggiornamento. Inoltre, assicurarsi che l'unità sia un'unità locale fissa, non sia connessa tramite USB o FireWire, sia formattata con file system NTFS, non è compresso e non contiene un file di paging. > versione di PowerShell 6.2.9200.0 o versioni successive. > è stato installato l'aggiornamento cumulativo più recente di Lync Server 2013. > SQL Server 2012 SP1 installato. > sono installati i seguenti KB (installati automaticamente se si utilizza Microsoft Update): > Windows Server 2008 R2-[KB2533623](https://support.microsoft.com/kb/2533623)> windows Server 2012-[KB2858668](https://support.microsoft.com/kb/2858668)> Windows Server 2012 R2-[KB2982006](https://support.microsoft.com/kb/2982006)
  
Utilizzare l'aggiornamento In-Place su ogni server per aggiornare il pool Front End, il pool di server perimetrali, il Mediation e il pool di chat persistente.
  
1. In ogni server, eseguire **Setup.exe** da **OCS_Volume \Setup\amd64** sul supporto di installazione di Skype for Business Server 2015.
    
2. Accettare il contratto di licenza e seguire le istruzioni per l'aggiornamento In-Place.
    
3. Ripetere questi passaggi per ogni server nel pool Front end e in ogni server del pool non front-end.
    
> [!NOTE]
> Potrebbe essere richiesto di riavviare il server durante l'aggiornamento del In-Place. Va bene. Dopo il riavvio, l'aggiornamento In-Place continuerà dal punto in cui è stato interrotto. 
  
Al termine dell'aggiornamento In-Place, viene visualizzato il messaggio seguente.
  
![Schermata in cui è stato eseguito l'aggiornamento sul posto.](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a>Passaggio 6: riavviare i servizi in tutti i server aggiornati

> [!NOTE]
> Prima di riavviare i servizi, verificare che%ProgramData%\WindowsFabric non esista su tutti i Front End Server. Se esiste, eliminarlo prima di avviare i servizi. 
  
- Dopo aver aggiornato tutti i server nel pool Front End, riavviare i servizi utilizzando il seguente comando di PowerShell: 
    
  ```powershell
  Start-CsPool
  ```

    > [!NOTE]
    > Se è già necessario riavviare il sistema in sospeso prima di iniziare a eseguire In-Place aggiornamento, In-Place aggiornamento non chiederà di riavviare il computer al termine dell'installazione. In questo modo vengono generate alcune eccezioni di assembly rispetto al primo front end server quando si tenta di avviare i servizi utilizzando il cmdlet Start-CSPool. Per risolvere questi errori, riavviare tutti i server del pool ed eseguire di nuovo il cmdlet. 
  
- Nei server pool non front-end, riavviare i servizi utilizzando il comando seguente:
    
  ```powershell
  Start-CsWindowsService
  ```

Dopo aver fatto clic su **OK** nella pagina aggiornamento In-Place, verrà visualizzato il seguente promemoria per completare questo passaggio.
  
![Schermata che illustra i passaggi successivi dopo il completamento dell'aggiornamento sul posto.](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a>Passaggio 7: verificare le funzionalità di Skype for business

Per assicurarsi che l'aggiornamento sia stato eseguito correttamente, per il pool aggiornato, testare Skype for business per assicurarsi che la funzionalità funzioni come previsto. 
  
### <a name="step-8-upgrade-secondary-pools"></a>Passaggio 8: aggiornare i pool secondari

Ripetere i passaggi descritti in questo argomento per aggiornare i pool aggiuntivi presenti nell'ambiente.
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a>Risoluzione dei problemi relativi all'aggiornamento In-Place

Se l'aggiornamento In-Place ha esito negativo, è possibile che venga visualizzato un messaggio analogo a quello riportato nell'immagine seguente. 
  
![Schermata in cui viene visualizzato un errore di aggiornamento sul posto, perché non è installato un aggiornamento cumulativo obbligatorio.](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
Esaminare il messaggio completo nella parte inferiore della pagina per risolvere il problema. Fare clic su **Visualizza registri** per ottenere ulteriori dettagli.
  
Se l'aggiornamento In-Place ha esito negativo sulla **Verifica della preparazione dell'aggiornamento** o dell'installazione dei **prerequisiti mancanti**, verificare che nel server siano stati applicati tutti gli aggiornamenti più recenti di Windows Server, Lync Server e SQL Server e che siano installati tutti i software e i ruoli necessari. Per un elenco di ciò che è necessario, vedere [server requirements for Skype for Business server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) e [Install Prerequisites for Skype for Business Server 2015](install/install-prerequisites.md).
  
## <a name="see-also"></a>Vedere anche

[Pianificare l'aggiornamento a Skype for Business Server 2015](../plan-your-deployment/upgrade.md)
  
[Requisiti del server per Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Installare i prerequisiti per Skype for Business Server 2015](install/install-prerequisites.md)
  
[Installare Skype for Business Server 2015](install/install.md)
