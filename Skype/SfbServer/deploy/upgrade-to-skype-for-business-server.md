---
title: Aggiornamento a Skype for Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/14/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: "Riepilogo: informazioni su come eseguire l'aggiornamento da Lync Server 2013 a Skype for Business Server 2015."
ms.openlocfilehash: 30cd73e8c21c9ee60521e1c2bddf8bddf4d23b6f
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860567"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a>Aggiornamento a Skype for Business Server 2015
 
**Riepilogo:** Informazioni su come eseguire l'aggiornamento da Lync Server 2013 a Skype for Business Server 2015. 
  
Usare le procedure descritte in questo documento per eseguire l'aggiornamento da Lync Server 2013 a Skype for Business Server 2015 usando Skype for Business Server Generatore di topologie e la nuova funzionalità di aggiornamento In-Place. Per eseguire l'aggiornamento da Lync Server 2010 o Office Communications Server 2007 R2, vedere [Pianificare l'aggiornamento a Skype for Business Server 2015](../plan-your-deployment/upgrade.md).

> [!NOTE]
> Gli aggiornamenti sul posto erano disponibili in Skype for Business Server 2015, ma non sono più supportati in Skype for Business Server 2019. La coesistenza affiancata è supportata, vedere [Migrazione a Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) per altre informazioni.
  
## <a name="upgrade-from-lync-server-2013"></a>Eseguire l'aggiornamento da Lync Server 2013

L'aggiornamento di Lync Server 2013 a Skype for Business Server 2015 comporta l'installazione del software prerequisito, l'uso di Skype for Business Server Topology Builder per aggiornare i database nel pool e l'uso dell'aggiornamento Skype for Business Server In-Place in ognuno dei server associati a la piscina. Per completare l'aggiornamento, seguire gli otto passaggi descritti in questo argomento.
  
### <a name="before-you-begin"></a>Informazioni preliminari

- Vedere [Plan to upgrade to Skype for Business Server 2015 (Piano per l'aggiornamento a Skype for Business Server 2015](../plan-your-deployment/upgrade.md)).
    
- Esaminare [i requisiti del server per Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
    
- [Installare i prerequisiti per Skype for Business Server 2015](install/install-prerequisites.md) .
    
- [Installare Skype for Business Server 2015](install/install.md) .
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a>Passaggio 1: Installare gli strumenti di amministratore e scaricare la topologia

1. Connessione nel computer nella topologia in cui non è installato Lync OCSCore o altri componenti lync.
    
2. Da Skype for Business Server supporto di installazione 2015 eseguire **Setup.exe** da **OCS_Volume\Setup\AMD64**. 
    
3. Fare clic su **Installa**. 
    
4. Accettare il contratto di licenza.
    
5. Nella Distribuzione guidata fare clic su **Installa strumenti di amministratore** e seguire la procedura per l'installazione.
    
     ![Screenshot della Distribuzione guidata con collegamento all'opzione Install Administrator Tools evidenziata.](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. Dal Windows schermata Start aprire Skype for Business Server Generatore di topologie.
    
7. Fare clic su **Scarica topologia dalla distribuzione esistente** e quindi su **Avanti**.
    
8. Immettere un nome per la topologia e fare clic su **Salva**.
    
9. Passare alla posizione in cui è stata salvata la topologia e creare una copia della topologia.
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a>Passaggio 2: Aggiornare e pubblicare la topologia con Generatore di topologie

Prima di avviare il processo di aggiornamento, tutti i servizi devono essere in esecuzione per i pool che si prevede di aggiornare. In questo modo le modifiche alla topologia verranno replicate nel database locale dei server nel pool.
  
> [!IMPORTANT]
>  Salvare una copia del file di topologia prima dell'aggiornamento. Dopo l'aggiornamento, non sarà possibile effettuare il downgrade della topologia.> Se i servizi si trovano negli stessi server dei database, ad esempio il servizio Chat persistente si trova nello stesso server del database di Chat persistente, ignorare questo passaggio e passare al passaggio 4. Dopo aver interrotto i servizi, eseguire il programma di installazione dell'aggiornamento In-Place in ogni server per aggiornare i database locali.
  
> [!NOTE]
> Se nella topologia è presente un database back-end con mirroring, quando **si pubblica la topologia** usando Generatore di topologie verranno visualizzati sia i database principal che i database con mirroring. Assicurarsi che tutti i database siano in esecuzione nell'entità e selezionare solo l'entità, non il mirroring, quando si pubblica la topologia in caso contrario verrà visualizzato un avviso dopo la pubblicazione della topologia.
  
Selezionare una delle opzioni seguenti per aggiornare e pubblicare una nuova topologia usando il generatore di topologie Skype for Business Server 2015. Dopo aver completato i passaggi e pubblicato la topologia aggiornata, passare al passaggio 3 di questo argomento.
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a>Opzione 1: Aggiornare un pool Front End isolato e gli archivi di archiviazione e monitoraggio associati

Se il pool che si sta aggiornando ha una dipendenza dell'archivio di archiviazione e monitoraggio, quando si usano i passaggi seguenti, verrà aggiornato anche l'archivio di archiviazione e monitoraggio.
  
1. In Generatore di topologie fare clic con il pulsante destro del mouse su un pool di Lync Server 2013, scegliere **Aggiorna a Skype for Business Server 2015** e seguire questa procedura. 
    
     ![Screenshot del menu di scelta rapida con l'opzione di aggiornamento per Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. In Generatore di topologie fare clic su **Pubblicazione azione** > **topologia** o **Pubblicazione topologia** >  **azione** > **.** 
    
     ![Screenshot del menu Azione con l'opzione Pubblica topologia in Generatore di topologie.](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. Durante la pubblicazione, scegliere di installare un database nell'archivio di archiviazione e monitoraggio.
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a>Opzione 2: Aggiornare il pool Front End senza aggiornare gli archivi di archiviazione e monitoraggio

Se si usano i passaggi seguenti, l'archiviazione e il monitoraggio per il pool selezionato vengono disabilitati. Il pool non avrà archivi di archiviazione e monitoraggio dopo l'aggiornamento.
  
1. In Generatore di topologie selezionare il pool di Lync Server 2013 da aggiornare.
    
2. Rimuovere la dipendenza dagli archivi di archiviazione e monitoraggio di Lync Server 2013. 
    
   - Passare a **Proprietà modifica azione** > .
    
   - Deselezionare la casella **di controllo Archiviazione** .
    
     ![Screenshot della casella di controllo Archiviazione nella finestra di dialogo Modifica proprietà.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - Deselezionare la casella di controllo **Monitoraggio** .
    
     ![Screenshot della finestra di dialogo Modifica proprietà che mostra la casella di controllo Monitoraggio.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Fare clic con il pulsante destro del mouse sul pool di Lync Server 2013, scegliere **Aggiorna a Skype for Business Server 2015** e seguire questa procedura. 
    
     ![Screenshot del menu di scelta rapida con l'opzione di aggiornamento per Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. In Generatore di topologie fare clic su **Pubblicazione azione** > **topologia** o **Pubblicazione topologia** >  **azione** > **.** 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a>Opzione 3: Aggiornare il pool Front End e associarlo ai nuovi archivi di archiviazione e monitoraggio di Skype for Business Server 2015

Se si usano i passaggi seguenti, l'archiviazione e il monitoraggio verranno arrestati nell'archivio precedente e verranno avviati nel nuovo archivio creato. 
  
1. In Generatore di topologie selezionare il pool di Lync Server 2013 da aggiornare. 
    
2. Rimuovere la dipendenza dagli archivi di archiviazione e monitoraggio di Lync Server 2013. 
    
   - Passare a **Proprietà modifica azione** > .
    
   - Deselezionare la casella **di controllo Archiviazione** .
    
     ![Screenshot della casella di controllo Archiviazione nella finestra di dialogo Modifica proprietà.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - Deselezionare la casella di controllo **Monitoraggio** .
    
     ![Screenshot della finestra di dialogo Modifica proprietà che mostra la casella di controllo Monitoraggio.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Fare clic con il pulsante destro del mouse sul pool di Lync Server 2013, scegliere **Aggiorna a Skype for Business Server 2015** e seguire questa procedura. 
    
     ![Screenshot del menu di scelta rapida con l'opzione di aggiornamento per Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. Creare un nuovo archivio SQL per l'archiviazione. 
    
   - Selezionare le proprietà pool e **Modifica azione** > . 
    
   -  Selezionare la casella **di controllo Archiviazione** .
    
   - Fare clic su **Nuova regola**.
    
     ![Screenshot della finestra di dialogo Modifica proprietà che mostra il pulsante Nuovo nella sezione Archiviazione.](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. Creare un nuovo archivio SQL per il monitoraggio. 
    
   - Selezionare le proprietà pool e **Modifica azione** > . 
    
   -  Selezionare la casella di controllo **Monitoraggio** .
    
   - Fare clic su **Nuova regola**.
    
     ![Screenshot della finestra di dialogo Modifica proprietà che mostra il pulsante Nuovo nella sezione Monitoraggio.](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. In Generatore di topologie fare clic su **Pubblicazione azione** > **topologia** o **Pubblicazione topologia** >  **azione** > **.** 
    
7. Durante la pubblicazione, scegliere di installare il database nel nuovo archivio di archiviazione e monitoraggio.
    
### <a name="step-3-wait-for-replication"></a>Passaggio 3: Attendere la replica

Concedere alla replica un po' di tempo per pubblicare la topologia aggiornata in tutti i server nell'ambiente.
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a>Passaggio 4: Arrestare tutti i servizi nel pool per l'aggiornamento

In ogni server che gestisce il pool che si intende aggiornare, eseguire il cmdlet seguente in PowerShell:
  
```powershell
Disable-CsComputer -Scorch
```

È consigliabile usare Disable-CsComputer perché potrebbe essere necessario riavviare il server durante il processo di aggiornamento In-Place. Se si usa Stop-CsWindowsService, alcuni servizi potrebbero essere riavviate automaticamente dopo un riavvio. Ciò potrebbe causare l'esito negativo dell'aggiornamento In-Place.
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a>Passaggio 5: Aggiornare i pool Front End e i server pool non Front End

> [!NOTE]
>  Prima dell'aggiornamento, installare tutti i nuovi prerequisiti necessari per Skype for Business Server 2015 che includono:> Almeno 32 GB di spazio disponibile prima di tentare un aggiornamento. Assicurarsi inoltre che l'unità sia un'unità locale fissa, non è connesso tramite USB o Firewire, è formattato con file system NTFS, non è compresso e non contiene un file di pagina.> PowerShell versione 6.2.9200.0 o successiva.> L'aggiornamento cumulativo di Lync Server 2013 più recente installato.> SQL Server 2012 SP1 installato.> La knowledge base seguente è installata (installata automaticamente se si usa Microsoft Update): > Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)> Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)> Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)
  
Usare l'aggiornamento In-Place in ogni server per aggiornare il pool Front End, il pool di server perimetrali, il mediation server e il pool di Chat persistente.
  
1. In ogni server eseguire **Setup.exe** da **OCS_Volume\Setup\amd64** nel supporto di installazione Skype for Business Server 2015.
    
2. Accettare il contratto di licenza e seguire le istruzioni per l'aggiornamento In-Place.
    
3. Ripetere questi passaggi per ogni server nel pool Front End e in ogni server pool non Front End.
    
> [!NOTE]
> Potrebbe essere richiesto di riavviare il server durante l'aggiornamento In-Place. Va bene. Dopo il riavvio, l'aggiornamento In-Place continuerà da dove è stato interrotto. 
  
Quando l'aggiornamento In-Place viene completato correttamente, viene visualizzato il messaggio seguente.
  
![Screenshot che mostra l'aggiornamento sul posto completato correttamente.](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a>Passaggio 6: Riavviare i servizi in tutti i server aggiornati

> [!NOTE]
> Prima di riavviare i servizi, verificare che %ProgramData%\WindowsFabric non esista in tutti i Front End Server. Se esiste, eliminarlo prima di avviare i servizi. 
  
- Dopo aver aggiornato tutti i server nel pool Front End, riavviare i servizi usando il comando di PowerShell seguente: 
    
  ```powershell
  Start-CsPool
  ```

    > [!NOTE]
    > Se è già necessario un riavvio del sistema in sospeso prima di iniziare a eseguire In-Place upgrade, In-Place Upgrade non richiederà il riavvio al termine dell'installazione. Ciò causerà la generazione di alcune eccezioni di assembly sul primo server Front End quando si tenta di avviare i servizi usando il cmdlet Start-CSPool. Per risolvere questi errori, riavviare tutti i server nel pool ed eseguire di nuovo il cmdlet. 
  
- Nei server pool non Front End riavviare i servizi usando il comando seguente:
    
  ```powershell
  Start-CsWindowsService
  ```

Dopo aver fatto clic su **OK** nella pagina aggiornamento In-Place, verrà visualizzato il promemoria seguente per completare questo passaggio.
  
![Screenshot che mostra i passaggi successivi al completamento dell'aggiornamento sul posto.](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a>Passaggio 7: Verificare che la funzionalità Skype for Business funzioni

Per assicurarsi che l'aggiornamento sia stato eseguito correttamente, per il pool aggiornato, testare Skype for Business per assicurarsi che la funzionalità funzioni come previsto. 
  
### <a name="step-8-upgrade-secondary-pools"></a>Passaggio 8: Aggiornare i pool secondari

Ripetere i passaggi descritti in questo argomento per aggiornare eventuali pool aggiuntivi presenti nell'ambiente.
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a>Risolvere i problemi relativi all'aggiornamento In-Place

Se l'aggiornamento In-Place non riesce, potrebbe essere visualizzato un messaggio simile a quello dell'immagine seguente. 
  
![Screenshot che mostra l'aggiornamento sul posto non riuscito perché non è installato un aggiornamento cumulativo richiesto.](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
Esaminare il messaggio completo nella parte inferiore della pagina per risolvere il problema. Fare clic su **Visualizza log** per ottenere maggiori dettagli.
  
Se l'aggiornamento In-Place non riesce durante **la verifica dell'idoneità dell'aggiornamento** o **l'installazione dei prerequisiti mancanti**, assicurarsi che nel server siano applicati tutti gli aggiornamenti più recenti Windows Server, Lync Server e SQL Server e che siano installati tutti i ruoli e il software necessari. Per un elenco degli elementi necessari, vedere Requisiti del [server per Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) e [Installare i prerequisiti per Skype for Business Server 2015](install/install-prerequisites.md).
  
## <a name="see-also"></a>Vedere anche

[Pianificare l'aggiornamento a Skype for Business Server 2015](../plan-your-deployment/upgrade.md)
  
[Requisiti del server per Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Installare i prerequisiti per Skype for Business Server 2015](install/install-prerequisites.md)
  
[Installare Skype for Business Server 2015](install/install.md)
