---
title: Creare e pubblicare una nuova topologia in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/15/2018
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
ms.assetid: 451c41a1-b8c5-4dc3-9e48-0da9ed5381a1
description: "Riepilogo: informazioni su come creare, pubblicare e verificare una nuova topologia prima di installare Skype for Business Server. Scaricare una versione di valutazione gratuita di Skype for Business Server da Microsoft Evaluation Center all'indirizzo: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server ."
ms.openlocfilehash: c18d0340c48a8bf07771d0892bed4d0740c63186
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812146"
---
# <a name="create-and-publish-new-topology-in-skype-for-business-server"></a>Creare e pubblicare una nuova topologia in Skype for Business Server
 
**Riepilogo:** Informazioni su come creare, pubblicare e verificare una nuova topologia prima di installare Skype for Business Server. Scaricare una versione di valutazione gratuita di Skype for Business Server da Microsoft Evaluation Center all'indirizzo: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) .
  
Prima di poter installare il sistema Skype for Business Server in ognuno dei server della topologia, è necessario creare una topologia e pubblicarla. Quando si pubblica una topologia, vengono caricate le informazioni sulla topologia nel database dell'archivio di gestione centrale. Se si tratta di un pool Enterprise Edition, si sta creando il database dell'archivio di gestione centrale al primo avvio della pubblicazione di una nuova topologia. Se si tratta di Standard Edition, sarà necessario eseguire il processo di preparazione del primo server Standard Edition dalla distribuzione guidata prima di pubblicare una topologia. Questo preparato per Standard Edition installando un'istanza di SQL Server Express Edition e creando l'archivio di gestione centrale. È possibile eseguire i passaggi da 1 a 5 in qualsiasi ordine. Tuttavia, è necessario eseguire i passaggi 6, 7 e 8 nell'ordine e dopo i passaggi da 1 a 5, come indicato nel diagramma. La procedura per la creazione e la pubblicazione di una nuova topologia è descritta nel passaggio 6 di 8.
  
![Diagramma Panoramica](../../media/c5c09ba2-c98b-4194-9857-7c3087c5560e.png)
  
## <a name="create-and-publish-new-topology"></a>Creare e pubblicare una nuova topologia

È possibile utilizzare il generatore di topologie di Skype for Business Server per progettare, definire, configurare e pubblicare topologie. Questo strumento è stato installato quando sono stati installati gli strumenti di amministrazione precedentemente presenti nell'articolo. Quando si crea una topologia, è possibile effettuare molte scelte diverse. In questa procedura viene creata una topologia di base con servizi di conferenza.
  
> [!IMPORTANT]
> Skype for Business Server richiede SQL Server per l'utilizzo. I database primari sono noti come archivio di gestione centrale. Se si sta distribuendo Enterprise Edition, questi database vengono creati quando si pubblica la topologia utilizzando la procedura seguente. In questo caso, il generatore di topologie richiederà le informazioni di connessione a un'installazione di SQL Server. Se si sta pianificando la distribuzione di Standard Edition, sarà necessario installare SQL Server Express Edition prima di definire e pubblicare la nuova topologia. Per installare SQL Server Express Edition, è necessario aprire la distribuzione guidata sul server che fungerà da front-end e quindi eseguire prepara primo server Standard Edition. Quando si fa clic su prepara primo server Standard Edition, la distribuzione guidata installa automaticamente SQL Server Express Edition e crea i database dell'archivio di gestione centrale. 
  
### <a name="create-a-new-topology"></a>Creare una nuova topologia

1. Accedere come utente standard con accesso a Generatore di topologie.
    
2. Aprire Generatore di topologie di Skype for Business Server.
    
3. Selezionare **nuova topologia** e fare clic su **OK**.
    
4. Selezionare un percorso e un nome di file per il file di configurazione della topologia.
    
    > [!NOTE]
    > La configurazione della topologia viene salvata come file XML del generatore di topologie (con estensione tbxml). Quando si pubblica una topologia, si stanno spingendo le informazioni di configurazione dal file al database di SQL Server. Quando si apre il generatore di topologie in futuro, è possibile scaricare la configurazione esistente da SQL Server direttamente in Generatore di topologie e pubblicarla di nuovo in SQL Server o salvarla come file di configurazione del generatore di topologie. 
  
5. Nella **schermata definire il dominio primario**, immettere il **dominio SIP primario** e fare clic su **Avanti**. In questo esempio viene utilizzato **contoso. local**, come illustrato nella figura.
    
     ![Definire il dominio SIP primario.](../../media/353e6b38-485f-4042-8585-aefa6c74b554.png)
  
6. Aggiungere ulteriori domini SIP supportati, quindi fare clic su **Avanti**.
    
7. Immettere un **nome** e una **Descrizione** per il primo sito (percorso) e quindi fare clic su **Avanti**, come mostrato nella figura.
    
     ![Definire il primo sito (posizione).](../../media/d8b6c54a-2011-4efb-97fb-a4de0f11303c.png)
  
8. Immettere la **città**, **lo stato/la provincia** e il **codice paese/area geografica** per il sito e quindi fare clic su **Avanti**.
    
9. Fare clic su **fine** per completare il processo di definizione di una nuova topologia. La nuova procedura guidata front end viene avviata automaticamente.
    
### <a name="define-a-front-end-pool-or-standard-edition-server"></a>Definire un pool Front end o un server Standard Edition

1. Esaminare i prerequisiti della procedura guidata e quindi fare clic su **Avanti**.
    
2. Immettere il nome di dominio completo (FQDN) del pool e selezionare il **pool Enterprise Edition front end** o il **Server Standard Edition** e quindi fare clic su **Avanti**, come mostrato nella figura.
    
    > [!TIP]
    > Skype for Business Server Enterprise Edition può includere più server che lavorano insieme per fornire il ruolo front-end. Quando si utilizzano più server per soddisfare il ruolo, viene chiamato pool. Di conseguenza, più server che collaborano per fornire il ruolo front-end è denominato anche pool Front end. Skype for Business Server Standard Edition può includere solo un singolo server per fornire il ruolo front-end. È comune fare riferimento al pool Front end anche se solo un singolo server fornisce il ruolo. 
  
     ![Definire il pool Front end.](../../media/c1447557-261e-4260-a362-ab8d19070eb9.png)
  
3. Immettere i nomi di dominio completi (FQDN) di tutti i computer nel pool e quindi fare clic su **Avanti** come mostrato nella figura.
    
     ![Definire i computer nel pool.](../../media/1106b4f3-8745-485b-b495-f885a5dfefda.png)
  
4. Selezionare le funzionalità che verranno incluse in questa topologia e quindi fare clic su **Avanti** come mostrato nella figura.
    
    > [!NOTE]
    > Skype for Business Server include numerose funzionalità avanzate. Esaminare la documentazione relativa alla pianificazione e alla distribuzione per ogni caratteristica specifica che si desidera utilizzare. 
  
     ![Selezionare funzionalità per la distribuzione.](../../media/77257588-d0e1-4517-a12a-869ffe009353.png)
  
5. Nella pagina **Selezione ruoli server collocati** è possibile scegliere di collocare il Mediation Server nel front end server oppure è possibile scegliere di distribuirlo come server autonomo.
    
    Se si intende collocare il Mediation Server nel pool Enterprise Edition front end, verificare che sia selezionata la casella di controllo. I ruoli del server verranno distribuiti nei server del pool. Se si intende distribuire il Mediation Server come server autonomo, deselezionare la casella di controllo appropriata. Il Mediation Server viene distribuito in un passaggio di distribuzione separato dopo aver distribuito completamente il front end server. Per informazioni sulla pianificazione di una collocazione, vedere [nozioni di base sulla topologia per Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md).
    
6. Utilizzando i **ruoli del server associato a questa pagina del pool Front End** , è possibile definire e associare i ruoli del server al pool Front end. È disponibile il seguente ruolo:
    
    **Abilitazione di un pool di server perimetrali** Definisce e associa un singolo server perimetrale o un pool di server perimetrali. Un server perimetrale facilita la comunicazione e la collaborazione tra gli utenti all'interno dell'organizzazione e le persone esterne all'organizzazione, inclusi gli utenti federati.
    
    Esistono due possibili scenari che è possibile utilizzare per distribuire e associare i ruoli del server.
    
    Per il primo scenario, è necessario definire una nuova topologia per una nuova installazione. È possibile accedere all'installazione in uno dei due modi seguenti:
    
   - Lasciare deselezionata la casella di controllo e definire la topologia. Dopo aver pubblicato, configurato e testato i ruoli del server front-end e back-end, è possibile eseguire di nuovo il generatore di topologie per aggiungere i server di ruoli alla topologia. Se si utilizza questa strategia, è possibile testare il pool Front end e il server che esegue SQL Server senza ulteriori complicazioni da ruoli aggiuntivi. Dopo aver completato il testing iniziale, è possibile eseguire di nuovo il generatore di topologie per selezionare i ruoli che è necessario distribuire.
    
   - Selezionare i ruoli che è necessario installare e quindi configurare l'hardware per gestire i ruoli selezionati.
    
     Per lo scenario 2 si dispone di una distribuzione esistente e l'infrastruttura è pronta per i nuovi ruoli oppure è necessario associare i ruoli esistenti a un nuovo front end server.
    
   - In questo caso, verranno selezionati i ruoli che si intende distribuire o associare al nuovo front end server. In entrambi i casi, sarà necessario procedere con la definizione dei ruoli, la configurazione dell'hardware necessario e l'installazione.
    
7. Successivamente, verrà definito l'archivio SQL Server che verrà utilizzato con la topologia. In questo esempio viene utilizzata l'istanza predefinita. Per ulteriori informazioni sulle funzionalità di SQL Server, ad esempio la disponibilità elevata, vedere [pianificare la disponibilità elevata e il ripristino di emergenza in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
    
   - Per utilizzare un archivio di SQL Server esistente già definito nella topologia, selezionare **Archivio SQL**.
    
   - Per definire una nuova istanza di SQL Server per archiviare le informazioni sul pool, fare clic su **nuovo** e quindi specificare il **nome di dominio completo di SQL Server** nella finestra di dialogo **Definisci nuovo archivio SQL** .
    
   - Per specificare il nome di un'istanza di SQL Server, selezionare **Istanza denominata** e quindi specificare il nome dell'istanza.
    
   - Per utilizzare l'istanza predefinita, fare clic su **Istanza predefinita**.
    
   - Per utilizzare il mirroring SQL, selezionare **Abilita mirroring SQL**, quindi selezionare un'istanza esistente o creare una nuova istanza.

     > [!NOTE]
     > Il mirroring SQL è disponibile in Skype for Business Server 2015 ma non è più supportato in Skype for Business Server 2019. I gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn (FCI) e i metodi di clustering di failover SQL sono preferiti con Skype for Business Server 2019.
    
     In questo esempio viene immesso il **nome di dominio completo di SQL Server** e vengono configurate le impostazioni di disponibilità elevata rilevanti e quindi fare clic su **OK**, come mostrato nella figura.
    
     ![Creare un archivio di SQL Server.](../../media/12822cf9-8608-43c0-94ce-2ca8b3a0ffd5.png)
  
8. Decidere se si desidera abilitare il mirroring dell'archivio SQL Server o il controllo del mirroring di SQL Server e quindi fare clic su **Avanti**.
    
9. Definire la condivisione file che si desidera utilizzare.
    
   - Per utilizzare una condivisione file già definita nella topologia, selezionare **Utilizza condivisione file definita in precedenza**.
    
   - Per definire una nuova condivisione file, selezionare **Definisci nuova condivisione file**, nella casella **FQDN file server** immettere l'FQDN del file server esistente in cui deve trovarsi la condivisione file e quindi immettere un nome per la condivisione nella casella **Condivisione file**.
    
     In questo esempio, si farà clic su **Definisci un nuovo archivio file**, immettere il **nome di dominio completo** e la **condivisione file** del server e quindi fare clic su **Avanti**.
    
     > [!NOTE]
     > La condivisione file per Skype for Business Server può essere collocata, ma non è consigliabile per motivi di prestazioni. Si noti che in questo esempio la condivisione file si trova in un singolo server dedicato che fungerà da condivisione file. Tuttavia, sono consigliati altri sistemi di condivisione file più robusti, ad esempio DFS con Windows Server 2012 R2. Per informazioni dettagliate sui sistemi di condivisione file supportati, vedere [requisiti per l'ambiente Skype for business](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md). Per ulteriori informazioni sulla creazione della condivisione file, vedere [creare una condivisione file in Skype for Business Server](create-a-file-share.md). È possibile definire la condivisione file senza che questa sia stata creata. Sarà necessario creare la condivisione file nella posizione definita prima di pubblicare la topologia. 
  
10. Nella pagina specificare l'URL dei servizi Web, è necessario decidere se è necessario sostituire l'URL di base del pool di servizi Web interni. Il motivo di questo override ha a che fare con il bilanciamento del carico. Il traffico SIP di base può essere bilanciato tramite bilanciamento del carico DNS semplice. Tuttavia, il traffico di rete di servizi Web HTTP/S deve utilizzare una soluzione di bilanciamento del carico hardware o software supportata. Per i server di bilanciamento del carico supportati, vedere [Infrastructure for Skype for business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways). In questo esempio, è stato utilizzato il bilanciamento del carico DNS per il traffico SIP e una soluzione di bilanciamento del carico software supportata. Poiché il traffico viene suddiviso in questo modo, è necessario eseguire l'override del nome di dominio completo del pool di servizi Web interni. In alternativa, se si dispone di un bilanciamento del carico di linea superiore e viene inviato tutto il traffico anziché utilizzare il bilanciamento del carico DNS per il traffico SIP, non è necessario sostituire l'URL dei servizi Web. 
    
    Nella sezione DNS di questo argomento è stato creato un record A per webint. contoso. local. Questo è l'URL utilizzato per il traffico HTTP/S dei servizi Web e deve passare attraverso il servizio di bilanciamento del carico software supportato configurati. Pertanto, in questo esempio, si ignora l'URL per consentire a Skype for Business Server di sapere che tutto il traffico HTTP/S deve passare a webint. contoso. local invece di pool. contoso. local, come mostrato nella figura. Per ulteriori informazioni sul bilanciamento del carico, vedere [requisiti per il bilanciamento del carico per Skype for business](../../plan-your-deployment/network-requirements/load-balancing.md).
    
    > [!IMPORTANT]
    > L'URL di base è l'identità dei servizi Web per l'URL meno https://. Ad esempio, se l'URL completo per i servizi Web del pool è https://webint.contoso.local , l'URL di base è webint. contoso. local. 
  
    - Se si sta configurando il bilanciamento del carico DNS, come in questo esempio, selezionare la casella di controllo **Sostituisci FQDN pool di servizi Web interni** e immettere l'URL di base interno (che deve essere diverso dall'FQDN del pool) nell' **URL di base interno**. 
    
    > [!CAUTION]
    > Se si decide di sostituire i servizi Web interni con un FQDN autodefinito, ogni FQDN deve essere univoco da qualsiasi altro pool Front End, Director o pool di server Director. Quando si definiscono URL o nomi di dominio completi, è possibile **utilizzare solo caratteri standard** (tra cui a-z, a-z, 0-9 e segni meno). Non utilizzare caratteri Unicode o di sottolineatura. I caratteri non standard in un URL o FQDN spesso non sono supportati da DNS esterno e autorità di certificazione pubbliche (CAs) (ovvero, quando l'URL o il nome di dominio completo deve essere assegnato al nome del soggetto o all'oggetto alternativo del soggetto nel certificato).
  
    - Facoltativamente, immettere l'URL di base esterno in **URL di base esterno**. È necessario immettere l'URL di base esterno per differenziarlo dal nome di dominio interno. Ad esempio, il dominio interno è contoso. local, ma il nome di dominio esterno è contoso.com. È possibile definire l'URL utilizzando il nome di dominio contoso.com poiché deve essere risolvibile da DNS pubblico. Questo è un aspetto importante anche nel caso di un proxy inverso. Il nome di dominio dell'URL di base esterno è lo stesso del nome di dominio dell'FQDN del proxy inverso. L'accesso HTTP al pool Front End è necessario per la messaggistica istantanea e la presenza sui client mobili.
    
      ![Eseguire l'override dei servizi Web.](../../media/8f95313c-2df4-4885-adc5-9fc9ea775406.png)
  
11. Se nella pagina **Seleziona funzionalità** è stata selezionata l'opzione servizi di **conferenza** , verrà richiesto di selezionare un server Office Web Apps. Fare clic su **nuovo** per aprire la finestra di dialogo.
    
12. Nella finestra di dialogo **Definisci nuovo server Office Web Apps** , digitare il nome di dominio completo del server Office Web Apps nella casella **FQDN server Office Web Apps** . Quando si esegue questa operazione, l'URL di individuazione del server Office Web Apps deve essere automaticamente immesso nella casella **URL individuazione server Office Web Apps** .
    
    Se il server Office Web Apps è installato in locale e nella stessa area di rete di Skype for Business Server, non selezionare l'opzione il **Server Office Web Apps è distribuito in una rete esterna (ovvero perimetro/Internet)**.
    
    Se il server Office Web Apps è distribuito all'esterno del firewall interno, selezionare l'opzione il **Server Office Web Apps è distribuito in una rete esterna (ovvero perimetro/Internet)**.
    
13. Fare clic su **fine** per completare la configurazione. Se sono stati definiti altri server di ruoli nella pagina **associa ruoli server al pool Front End** , verranno aperte le pagine della configurazione guidata ruolo separate in cui è possibile configurare i ruoli del server. In questo esempio viene scelto solo il servizio di conferenza.
    
### <a name="configure-simple-urls"></a>Configurare gli URL semplici

1. In Generatore di topologie fare clic con il pulsante destro del mouse sul nodo principale **di Skype for Business Server** e quindi scegliere **modifica proprietà**, come mostrato nella figura.
    
     ![Fare clic con il pulsante destro del mouse su Skype for Business Server e scegliere Modifica proprietà.](../../media/692c18dd-8e99-4239-ae7b-5e855d866afa.png)
  
2. Nel riquadro **URL semplici** selezionare URL di **accesso telefonico:** (chiamata in ingresso) o URL di **riunione:** (Meet) per modificare e quindi fare clic su **modifica URL**.
    
3. Aggiornare l'URL in base al valore desiderato e quindi fare clic su **OK** per salvare l'URL modificato. È consigliabile configurare l'URL semplice utilizzando il dominio SIP esterno in modo che gli utenti esterni possano partecipare a riunioni, ad esempio contoso.com, che è esterno anziché contoso. local, che è un dominio interno. Pertanto, il dominio SIP dovrebbe essere in grado di essere risolto da DNS esterno.
    
4. Se necessario, modificare l'URL riunione eseguendo la stessa procedura.
    
### <a name="to-define-the-optional-admin-simple-url"></a>Per definire l'URL semplice facoltativo per l'accesso amministrativo

1. In Generatore di topologie fare clic con il pulsante destro del mouse sul nodo **di Skype for Business Server** e quindi scegliere **modifica proprietà**.
    
2. Nella casella **URL di accesso amministrativo** immettere l'URL semplice desiderato per l'accesso amministrativo al pannello di controllo di Skype for Business Server e quindi fare clic su **OK**.
    
    > [!TIP]
    > È consigliabile utilizzare l'URL più semplice possibile per l'accesso amministrativo. L'opzione più semplice è https://admin . _\<domain\>_ . L'URL di amministratore può essere un dominio interno o esterno, ad esempio contoso. local o contoso.com, purché entrambi i record siano risolvibili in DNS interno. 
  
    > [!IMPORTANT]
    > Se si modifica un URL semplice dopo la distribuzione iniziale, è necessario considerare quali modifiche influiscono sui record DNS (Domain Name System) e sui certificati per gli URL semplici. Se la modifica incide sulla base di un URL semplice, è necessario modificare anche i record e i certificati DNS. Ad esempio, https://sfb.contoso.com/Meet se si cambia da per cambiare https://meet.contoso.com l'URL di base da sfb.contoso.com a meet.contoso.com, è necessario modificare i record DNS e i certificati in modo che facciano riferimento a meet.contoso.com. Se l'URL semplice è stato modificato da https://sfb.contoso.com/Meet a https://sfb.contoso.com/Meetings , l'URL di base di SFB.contoso.com rimane invariato, quindi non sono necessarie modifiche a DNS o certificati. Ogni volta che si modifica un nome URL semplice, è necessario eseguire il cmdlet **Enable-CsComputer** su ogni Director e front end server per registrare la modifica.
  
### <a name="publish-and-verify-the-topology"></a>Pubblicare e verificare la topologia

1. Controllare che tutti gli URL semplici siano configurati in modo corretto.
    
2. Verificare che il server basato su SQL Server sia online e disponibile per il computer in cui è installato Generatore di topologie, incluse le eventuali regole del firewall necessarie.
    
3. Verificare che la condivisione file sia disponibile e che siano definite le autorizzazioni appropriate.
    
4. Verificare che nella topologia siano definiti i ruoli del server corretti conformi ai requisiti della distribuzione.
    
5. Verificare che i server siano presenti in servizi di dominio Active Directory (AD DS). Questo accade automaticamente quando si uniscono i server al dominio.
    
    Dopo aver verificato la topologia e stabilito che non sono presenti errori di convalida, è possibile procedere con la pubblicazione della topologia. Se sono presenti errori di convalida, è necessario correggerli prima di poter pubblicare la topologia.
    
6. Fare clic con il pulsante destro del mouse sul nodo **di Skype for Business Server** , quindi fare clic su **Pubblica topologia**.
    
7. Nella pagina **Pubblicare la topologia** fare clic su **Avanti**.
    
8. Nella pagina **Seleziona server di gestione centrale** selezionare un pool Front End, come mostrato nella figura.
    
    > [!NOTE]
    > È possibile fare clic su **Avanzate** per configurare i percorsi di file di database.
  
     ![Selezionare il server dell'archivio di gestione centrale.](../../media/764478b5-8480-42c5-854f-649bb121cd94.png)
  
9. Nella pagina **Seleziona database** selezionare i database che si desidera pubblicare.
    
    > [!NOTE]
    > Se non si dispone dei diritti necessari per creare i database, è possibile deselezionare le caselle di controllo accanto a tali database e un utente con diritti opportuni può creare i database in un secondo momento. Per informazioni dettagliate sui requisiti, vedere [requisiti del server per Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md). 
  
10. Facoltativamente, fare clic su **Avanzate**. Utilizzando le opzioni avanzate di posizionamento dei file di dati di SQL Server, è possibile scegliere tra le opzioni seguenti: 
    
    - **Determina automaticamente il percorso dei file di database** -questa opzione determina le migliori prestazioni operative in base alla configurazione del disco nel server basato su SQL Server distribuendo i file di registro e di dati nella posizione migliore.
    
    - **Utilizzare le impostazioni predefinite dell'istanza di SQL Server** -questa opzione consente di inserire i file di dati e di log nel server basato su SQL Server utilizzando le opzioni di istanza. Non utilizza la funzionalità operativa del server basato su SQL Server di determinazione dei percorsi ottimali per i registri e i dati. L'amministratore di SQL Server in genere sposta i file di registro e di dati nei percorsi appropriati per le procedure di gestione del server basato su SQL Server e dell'organizzazione.
    
    Fare clic su **OK** e quindi su **Avanti**. 
    
11. Facoltativamente, fare clic su **Avanzate**. Utilizzando le opzioni avanzate di posizionamento dei file di dati di SQL Server, è possibile scegliere tra le opzioni seguenti: 
    
    - **Determina automaticamente il percorso dei file di database** -questa opzione determina le migliori prestazioni operative in base alla configurazione del disco nel server basato su SQL Server distribuendo i file di registro e di dati nella posizione migliore.
    
    - **Utilizzare le impostazioni predefinite dell'istanza di SQL Server** -questa opzione consente di inserire i file di dati e di log nel server basato su SQL Server utilizzando le opzioni di istanza. Non utilizza la funzionalità operativa del server basato su SQL Server di determinazione dei percorsi ottimali per i registri e i dati. L'amministratore di SQL Server in genere sposta i file di registro e di dati nei percorsi appropriati per le procedure di gestione del server basato su SQL Server e dell'organizzazione.
    
    Fare clic su **OK**.
    
12. Fare clic su **Avanti** per completare il processo di pubblicazione.
    
    > [!NOTE]
    > Un errore comune per questo passaggio consiste nel fatto che non è possibile creare i database di SQL Server. Al termine del processo, viene fornito un errore, come mostrato nella figura. La causa più probabile è che l'utente che tenta di creare il database non disponga delle autorizzazioni appropriate o che il sistema di SQL Server non può essere contattato a causa di un firewall o di un altro problema di rete. 
  
     ![Errore durante la creazione dell'archivio di gestione centrale.](../../media/558bd2e4-2721-422d-9986-df86f642e6a1.png)
  
13. Al termine del processo di pubblicazione, viene visualizzato un collegamento per aprire un elenco dei passaggi successivi. Fare clic **su fare clic qui per aprire l'elenco** delle operazioni da fare per visualizzare i passaggi successivi e quindi fare clic su **fine**. 
    
    Il messaggio "completata con avvisi" per la creazione del database non significa che si è verificato un errore. Il processo di installazione deve modificare le impostazioni in SQL Server per Skype for Business Server per funzionare correttamente. Quando un'impostazione viene modificata in SQL Server, viene registrata come messaggio di avviso in modo che gli amministratori di SQL Server possano comprendere esattamente il completamento del processo di installazione. Se viene visualizzato un messaggio di avviso, è possibile selezionare il record e quindi fare clic su **Visualizza registri** per visualizzare i dettagli dell'avviso.
    
    Quando la topologia è stata pubblicata correttamente, è possibile iniziare a installare una replica locale dell'archivio di gestione centrale in ogni server che esegue Skype for Business Server nella topologia. Si consiglia di iniziare con il primo pool Front end. 
    

