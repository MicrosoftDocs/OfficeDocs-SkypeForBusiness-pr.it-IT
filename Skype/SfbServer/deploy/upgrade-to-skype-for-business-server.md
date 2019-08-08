---
title: Aggiornamento a Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: "Riepilogo: informazioni su come eseguire l'aggiornamento da Lync Server 2013 a Skype for Business Server 2015. Scaricare una versione di valutazione gratuita di Skype for Business Server 2015 presso Microsoft Evaluation Center all' https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverIndirizzo:."
ms.openlocfilehash: c34cbc7ce1d755f093ac14bc85d78106216c450b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237859"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a>Aggiornamento a Skype for Business Server 2015
 
**Riepilogo:** Informazioni su come eseguire l'aggiornamento da Lync Server 2013 a Skype for Business Server 2015. Scaricare una versione di valutazione gratuita di Skype for Business Server 2015 dal [Microsoft Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Usare le procedure descritte in questo documento per eseguire l'aggiornamento da Lync Server 2013 a Skype for Business Server 2015 usando il generatore di topologia di Skype for Business Server e la nuova funzionalità di aggiornamento sul posto. Se si vuole eseguire l'aggiornamento da Lync Server 2010 o Office Communications Server 2007 R2, vedere [pianificare l'aggiornamento a Skype for Business Server 2015](../plan-your-deployment/upgrade.md).

> [!NOTE]
> Gli aggiornamenti sul posto sono disponibili in Skype for Business Server 2015, ma non sono più supportati in Skype for Business Server 2019. La coesistenza affiancata è supportata, vedere [migrazione a Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) per altre informazioni.
  
## <a name="upgrade-from-lync-server-2013"></a>Eseguire l'aggiornamento da Lync Server 2013

L'aggiornamento di Lync Server 2013 a Skype for Business Server 2015 prevede l'installazione del software prerequisito, usando il generatore di topologia di Skype for Business Server per aggiornare i database nel pool e l'uso dell'aggiornamento sul posto di Skype for Business Server su ogni Server associati al pool. Per completare l'aggiornamento, fare clic su otto passaggi in questo argomento.
  
### <a name="before-you-begin"></a>Prima di iniziare

- Rivedere il [piano per l'aggiornamento a Skype for Business Server 2015](../plan-your-deployment/upgrade.md).
    
- Rivedere [i requisiti del server per Skype for Business server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- [Installare prerequisiti per Skype for Business Server 2015](install/install-prerequisites.md) .
    
- [Installare Skype for Business Server 2015](install/install.md) .
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a>Passaggio 1: installare gli strumenti di amministrazione e scaricare la topologia

1. Connettersi al computer nella topologia in cui non è installato Lync OCSCore o altri componenti Lync.
    
2. Dal supporto di installazione di Skype for Business Server 2015, eseguire **Setup. exe** da **OCS_Volume\Setup\AMD64**. 
    
3. Fare clic su **Installa**. 
    
4. Accettare il contratto di licenza.
    
5. Nella distribuzione guidata fare clic su **installa strumenti di amministrazione**e seguire la procedura da installare.
    
     ![Schermata della distribuzione guidata con il collegamento agli strumenti di amministratore di installazione richiamati.](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. Nella schermata Start di Windows aprire Generatore di topologia di Skype for Business Server.
    
7. Fare clic su **Scarica topologia da distribuzione esistente**e quindi su **Avanti**.
    
8. Immettere un nome per la topologia e fare clic su **Salva**.
    
9. Accedere alla posizione in cui è stata salvata la topologia e creare una copia della topologia.
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a>Passaggio 2: aggiornare e pubblicare la topologia usando generatore di topologie

Prima di avviare il processo di aggiornamento, è necessario che tutti i servizi siano in esecuzione per i pool che si prevede di eseguire l'aggiornamento. In questo modo le modifiche della topologia verranno replicate nel database locale dei server nel pool.
  
> [!IMPORTANT]
>  Salvare una copia del file della topologia prima di eseguire l'aggiornamento. Dopo l'aggiornamento, non sarà possibile eseguire il downgrade della topologia. > se i servizi si trovano nello stesso server dei database, ad esempio il servizio chat persistente si trova nello stesso server del database della chat persistente, ignorare questo passaggio e passare al passaggio 4. Dopo aver smesso i servizi, eseguire la configurazione di aggiornamento sul posto in ogni server per aggiornare i database locali.
  
> [!NOTE]
> Se la topologia include un database back-end con mirroring, viene visualizzato sia l'oggetto Principal che i database con mirroring visualizzati **quando si pubblica la topologia** tramite Generatore di topologie. Assicurarsi che tutti i database siano in uso nell'entità e selezionare solo l'entità, non lo specchio, quando si pubblica la topologia in caso contrario verrà visualizzato un avviso dopo la pubblicazione della topologia.
  
Selezionare una delle opzioni seguenti per aggiornare e pubblicare una nuova topologia usando il generatore di topologia di Skype for Business Server 2015. Dopo aver completato la procedura e pubblicato la topologia aggiornata, passare al passaggio 3 in questo argomento.
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a>Opzione 1: aggiornare un pool di front end isolato e gli archivi di archiviazione e monitoraggio associati

Se il pool che si sta aggiornando ha una dipendenza dell'archivio di archiviazione e monitoraggio, quando si usano i passaggi seguenti, verrà aggiornato anche l'archivio archiviazione e monitoraggio.
  
1. In Generatore di topologie fare clic con il pulsante destro del mouse su un pool di Lync Server 2013, scegliere **Aggiorna a Skype for Business server 2015**e seguire la procedura. 
    
     ![Screenshot del menu di scelta rapida con l'opzione di aggiornamento per Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. In Generatore di topologie fare clic su **azione** > **Pubblica topologia** o**topologia** > di **azione** > **pubblica**. 
    
     ![Schermata del menu azione con l'opzione Pubblica topologia in Generatore di topologie.](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. Durante la pubblicazione, scegliere di installare un database nell'archivio archiviazione e monitoraggio.
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a>Opzione 2: aggiornare il pool Front-end senza aggiornare gli archivi di archiviazione e monitoraggio

Se si usano i passaggi seguenti, l'archiviazione e il monitoraggio per il pool selezionato sono disabilitati. Dopo l'aggiornamento, il pool non avrà archivi di archiviazione e monitoraggio.
  
1. In Generatore di topologie selezionare il pool di Lync Server 2013 che si desidera aggiornare.
    
2. Rimuovere la dipendenza dagli archivi di archiviazione e monitoraggio di Lync Server 2013. 
    
   - Vai alle **** > **proprietà modifica**azione.
    
   - Deselezionare la casella di controllo **archiviazione** .
    
     ![Screenshot della casella di controllo archiviazione nella finestra di dialogo Modifica proprietà.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - Deselezionare la casella di controllo **monitoraggio** .
    
     ![Screenshot della finestra di dialogo Modifica proprietà che mostra la casella di controllo monitoraggio.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Fare clic con il pulsante destro del mouse sul pool di Lync Server 2013, scegliere **Aggiorna a Skype for Business server 2015**e seguire la procedura. 
    
     ![Screenshot del menu di scelta rapida con l'opzione di aggiornamento per Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. In Generatore di topologie fare clic su **azione** > **Pubblica topologia** o**topologia** > di **azione** > **pubblica**. 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a>Opzione 3: aggiornare il pool Front-end e associarlo ai nuovi archivi di archiviazione e monitoraggio di Skype for Business Server 2015

Se si usano i passaggi seguenti, l'archiviazione e il monitoraggio si arresteranno nello Store precedente e inizieranno nel nuovo Store creato. 
  
1. In Generatore di topologie selezionare il pool di Lync Server 2013 che si desidera aggiornare. 
    
2. Rimuovere la dipendenza dagli archivi di archiviazione e monitoraggio di Lync Server 2013. 
    
   - Vai alle **** > **proprietà modifica**azione.
    
   - Deselezionare la casella di controllo **archiviazione** .
    
     ![Screenshot della casella di controllo archiviazione nella finestra di dialogo Modifica proprietà.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - Deselezionare la casella di controllo **monitoraggio** .
    
     ![Screenshot della finestra di dialogo Modifica proprietà che mostra la casella di controllo monitoraggio.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Fare clic con il pulsante destro del mouse sul pool di Lync Server 2013, scegliere **Aggiorna a Skype for Business server 2015**e seguire la procedura. 
    
     ![Screenshot del menu di scelta rapida con l'opzione di aggiornamento per Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. Creare un nuovo archivio SQL per l'archiviazione. 
    
   - Selezionare le proprietà di **** > **modifica**del pool e dell'azione. 
    
   -  Selezionare la casella di controllo **archiviazione** .
    
   - Fare clic su **nuovo**.
    
     ![Screenshot della finestra di dialogo Modifica proprietà che mostra il pulsante nuovo nella sezione archiviazione.](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. Creare un nuovo archivio SQL per il monitoraggio. 
    
   - Selezionare le proprietà di **** > **modifica**del pool e dell'azione. 
    
   -  Selezionare la casella di controllo **monitoraggio** .
    
   - Fare clic su **nuovo**.
    
     ![Screenshot della finestra di dialogo Modifica proprietà che mostra il pulsante nuovo nella sezione monitoraggio.](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. In Generatore di topologie fare clic su **azione** > **Pubblica topologia** o**topologia** > di **azione** > **pubblica**. 
    
7. Durante la pubblicazione, scegliere di installare il database nel nuovo archivio archiviazione e monitoraggio.
    
### <a name="step-3-wait-for-replication"></a>Passaggio 3: attendere la replica

Assegna un po' di tempo alla replica per pubblicare la topologia aggiornata in tutti i server dell'ambiente.
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a>Passaggio 4: arrestare tutti i servizi in pool per l'aggiornamento

In ogni server che sta servendo il pool che si vuole aggiornare, eseguire il cmdlet seguente in PowerShell:
  
```
Disable-CsComputer -Scorch
```

È consigliabile usare Disable-CsComputer perché potrebbe essere necessario riavviare il server durante il processo di aggiornamento sul posto. Se si usa Stop-CsWindowsService, è possibile che alcuni servizi vengano riavviati automaticamente dopo un riavvio. In questo modo l'aggiornamento sul posto potrebbe non riuscire.
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a>Passaggio 5: aggiornare i pool Front-end e i server pool non front-end

> [!NOTE]
>  Prima di eseguire l'aggiornamento, installare tutti i nuovi prerequisiti necessari per Skype for Business Server 2015 che includono: > almeno 32GB di spazio disponibile prima di provare un aggiornamento. Inoltre, assicurati che l'unità sia un'unità locale fissa, che non sia connessa tramite USB o FireWire, sia formattata con il file system NTFS, non sia compressa e non contenga un file di pagina. > versione di PowerShell 6.2.9200.0 o successive. > l'ultimo Lync Server 2013 Aggiornamento cumulativo installato. > SQL Server 2012 SP1 installato. > installato la Knowledge Base seguente (installato automaticamente se si usa Microsoft Update): > Windows Server 2008 R2-[KB2533623](https://support.microsoft.com/kb/2533623)> windows Server 2012-[KB2858668](https://support.microsoft.com/kb/2858668)> Windows Server 2012 R2-[KB2982006](https://support.microsoft.com/kb/2982006)
  
Usare l'aggiornamento sul posto in ogni server per aggiornare il pool Front-End, il pool di Edge, il Mediation Server e il pool di chat persistente.
  
1. In ogni server eseguire **Setup. exe** da **OCS_Volume\Setup\amd64** nel supporto di installazione di Skype for Business Server 2015.
    
2. Accettare il contratto di licenza e seguire le istruzioni per l'aggiornamento sul posto.
    
3. Ripetere questi passaggi per ogni server nel pool Front-end e in ogni server del pool non front-end.
    
> [!NOTE]
> Potrebbe essere richiesto di riavviare il server durante l'aggiornamento sul posto. Va bene. Dopo il riavvio, l'aggiornamento sul posto continuerà da dove è stato interrotto. 
  
Quando l'aggiornamento sul posto viene completato correttamente, viene visualizzato il messaggio seguente.
  
![Screenshot che mostra l'aggiornamento sul posto completato correttamente.](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a>Passaggio 6: riavviare i servizi in tutti i server aggiornati

> [!NOTE]
> Prima di riavviare i servizi, assicurati che%ProgramData%\WindowsFabric non sia presente in tutti i server front-end. Se esiste, eliminarlo prima di avviare i servizi. 
  
- Dopo aver aggiornato tutti i server nel pool Front-End, riavviare i servizi usando il comando di PowerShell seguente: 
    
  ```
  Start-CsPool
  ```

    > [!NOTE]
    > Se è già necessario riavviare il sistema in sospeso prima di iniziare a eseguire l'aggiornamento sul posto, l'aggiornamento sul posto non richiederà il riavvio alla fine dell'installazione. In questo modo verranno generate alcune eccezioni di assembly rispetto al primo server front-end quando si tenta di avviare i servizi usando il cmdlet Start-CSPool. Per risolvere questi errori, riavviare tutti i server del pool ed eseguire di nuovo il cmdlet. 
  
- Nei server pool non front-end riavviare i servizi usando il comando seguente:
    
  ```
  Start-CsWindowsService
  ```

Dopo aver fatto clic su **OK** nella pagina di aggiornamento sul posto, viene visualizzato il promemoria seguente per completare questo passaggio.
  
![Screenshot che mostra i passaggi successivi dopo il completamento dell'aggiornamento sul posto.](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a>Passaggio 7: verificare il funzionamento delle funzionalità di Skype for business

Per verificare che l'aggiornamento sia stato eseguito correttamente, per il pool aggiornato, provare Skype for business per verificare che la funzionalità funzioni come previsto. 
  
### <a name="step-8-upgrade-secondary-pools"></a>Passaggio 8: aggiornare i pool secondari

Ripetere i passaggi descritti in questo argomento per aggiornare gli eventuali pool aggiuntivi presenti nell'ambiente.
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a>Risolvere i problemi relativi all'aggiornamento sul posto

Se l'aggiornamento sul posto non riesce, è possibile che venga visualizzato un messaggio simile a quello dell'immagine seguente. 
  
![Schermata che mostra il mancato aggiornamento sul posto perché non è installato un aggiornamento cumulativo obbligatorio.](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
Esaminare il messaggio completo nella parte inferiore della pagina per facilitare la risoluzione del problema. Fare clic su **Visualizza registri** per ottenere maggiori dettagli.
  
Se l'aggiornamento sul posto non riesce a **verificare la disponibilità dell'aggiornamento** o l' **installazione di prerequisiti mancanti**, verificare che il server disponga di tutti gli aggiornamenti più recenti di Windows Server, Lync Server e SQL Server e che tutti i software e i ruoli necessari siano installato. Per un elenco delle informazioni necessarie, vedere [requisiti del server per Skype for Business server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) e [installare i prerequisiti per Skype for Business Server 2015](install/install-prerequisites.md).
  
## <a name="see-also"></a>Vedere anche

[Pianificare l'aggiornamento a Skype for Business Server 2015](../plan-your-deployment/upgrade.md)
  
[Requisiti server di Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Installare prerequisiti per Skype for Business Server 2015](install/install-prerequisites.md)
  
[Installare Skype for Business Server 2015](install/install.md)
