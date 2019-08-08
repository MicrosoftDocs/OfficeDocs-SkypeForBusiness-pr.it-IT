---
title: Creare e pubblicare una nuova topologia in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 451c41a1-b8c5-4dc3-9e48-0da9ed5381a1
description: "Riepilogo: informazioni su come creare, pubblicare e verificare una nuova topologia prima di installare Skype for Business Server. Scaricare una versione di valutazione gratuita di Skype for Business Server dal Microsoft Evaluation Center all' https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverIndirizzo:."
ms.openlocfilehash: c62e2ae061f02f195d0a9560d08234c452543d88
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245007"
---
# <a name="create-and-publish-new-topology-in-skype-for-business-server"></a>Creare e pubblicare una nuova topologia in Skype for Business Server
 
**Riepilogo:** Informazioni su come creare, pubblicare e verificare una nuova topologia prima di installare Skype for Business Server. Scaricare una versione di valutazione gratuita di Skype for Business Server dal Microsoft Evaluation Center all' [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)Indirizzo:.
  
Prima di poter installare il sistema Skype for Business Server in ognuno dei server della topologia, è necessario creare una topologia e pubblicarla. Quando si pubblica una topologia, si caricano le informazioni sulla topologia nel database Central Management store. Se si tratta di un pool di Enterprise Edition, la prima volta che si pubblica una nuova topologia si crea il database Central Management store. Se si tratta di Standard Edition, sarà necessario eseguire il processo di preparazione del primo server Standard Edition dalla distribuzione guidata prima di pubblicare una topologia. Questa operazione viene preparata per la versione standard con l'installazione di un'istanza di SQL Server Express Edition e la creazione di Central Management store. È possibile eseguire i passaggi da 1 a 5 in qualsiasi ordine. Tuttavia, è necessario eseguire i passaggi 6, 7 e 8 in ordine e dopo i passaggi da 1 a 5, come illustrato nel diagramma. La procedura per creare e pubblicare una nuova topologia è descritta nel passaggio 6 di 8.
  
![Diagramma di panoramica](../../media/c5c09ba2-c98b-4194-9857-7c3087c5560e.png)
  
## <a name="create-and-publish-new-topology"></a>Create and publish new topology

Puoi usare il generatore di topologia di Skype for Business Server per progettare, definire, configurare e pubblicare le topologie. Questo strumento è stato installato quando sono stati installati gli strumenti di amministrazione precedenti nell'articolo. Quando si crea una topologia, è possibile eseguire diverse scelte. In questa procedura verrà creata una topologia di base con servizi di conferenza.
  
> [!IMPORTANT]
> Skype for Business Server richiede SQL Server per l'uso. I database primari sono noti come Central Management store. Se si sta distribuendo Enterprise Edition, questi database vengono creati quando si pubblica la topologia usando la procedura seguente. In questo caso, generatore di topologie richiederà le informazioni sulla connessione a un'installazione di SQL Server. Se si prevede di distribuire Standard Edition, sarà necessario installare SQL Server Express Edition prima di definire e pubblicare la nuova topologia. Per installare SQL Server Express Edition, è necessario aprire la distribuzione guidata nel server che fungerà da front-end e quindi eseguire preparare il primo server Standard Edition. Quando si fa clic su prepara primo server Standard Edition, la distribuzione guidata installa automaticamente SQL Server Express Edition e crea i database di Central Management store. 
  
### <a name="create-a-new-topology"></a>Creare una nuova topologia

1. Accedere come utente standard con accesso a Generatore di topologie.
    
2. Aprire Generatore di topologia di Skype for Business Server.
    
3. Selezionare **nuova topologia**e quindi fare clic su **OK**.
    
4. Selezionare un percorso e un nome di file per il file di configurazione della topologia.
    
    > [!NOTE]
    > La configurazione della topologia viene salvata come file XML di generatore di topologia (con estensione tbxml). Quando si pubblica una topologia, si stanno spingendo le informazioni di configurazione dal file al database di SQL Server. Quando si apre Generatore di topologie in futuro, è possibile scaricare la configurazione esistente da SQL Server direttamente in Generatore di topologia e pubblicarla di nuovo in SQL Server o salvarla come file di configurazione del generatore di topologia. 
  
5. Nella **schermata Definisci il dominio principale**immettere il **dominio SIP principale**e fare clic su **Avanti**. In questo esempio si usa **contoso. local**, come illustrato nella figura.
    
     ![Definire il dominio SIP principale.](../../media/353e6b38-485f-4042-8585-aefa6c74b554.png)
  
6. Aggiungere altri domini SIP supportati e quindi fare clic su **Avanti**.
    
7. Immettere un **nome** e una **Descrizione** per il primo sito (posizione), quindi fare clic su **Avanti**, come illustrato nella figura.
    
     ![Definire il primo sito (posizione).](../../media/d8b6c54a-2011-4efb-97fb-a4de0f11303c.png)
  
8. Immettere il codice **città**, **stato/provincia**e **paese/area geografica** per il sito e quindi fare clic su **Avanti**.
    
9. Fare clic su **fine** per completare il processo di definizione di una nuova topologia. Viene avviata automaticamente la nuova procedura guidata front-end.
    
### <a name="define-a-front-end-pool-or-standard-edition-server"></a>Definire un pool Front-end o un server Standard Edition

1. Rivedere i prerequisiti della procedura guidata e quindi fare clic su **Avanti**.
    
2. Immettere il nome di dominio completo (FQDN) del pool e selezionare **Enterprise Edition Front End pool** o **Standard Edition server**e quindi fare clic su **Avanti**, come illustrato nella figura.
    
    > [!TIP]
    > Skype for Business Server Enterprise Edition può includere più server che lavorano insieme per ottenere il ruolo di front-end. Quando si usano più server per completare il ruolo, viene chiamato pool. Quindi, più server che lavorano insieme per specificare il ruolo di front-end viene indicato anche come pool Front-end. Skype for Business Server Standard Edition può includere solo un singolo server per il ruolo di front-end. È comune fare riferimento al pool Front-end anche se solo un singolo server fornisce il ruolo. 
  
     ![Definire il pool Front-end.](../../media/c1447557-261e-4260-a362-ab8d19070eb9.png)
  
3. Immettere i nomi di dominio completi (FQDN) di tutti i computer del pool e quindi fare clic su **Avanti** come illustrato nella figura.
    
     ![Definire i computer nel pool.](../../media/1106b4f3-8745-485b-b495-f885a5dfefda.png)
  
4. Selezionare le caratteristiche che verranno incluse in questa topologia e quindi fare clic su **Avanti** come illustrato nella figura.
    
    > [!NOTE]
    > Skype for Business Server include numerose funzionalità avanzate. Esaminare la documentazione relativa alla pianificazione e alla distribuzione per ogni specifica caratteristica che si vuole usare. 
  
     ![Selezionare le caratteristiche per la distribuzione.](../../media/77257588-d0e1-4517-a12a-869ffe009353.png)
  
5. Nella pagina **Selezione ruoli server collocato** è possibile scegliere di collocare il Mediation Server nel server front-end oppure scegliere di distribuirlo come server autonomo.
    
    Se si intende collocare il Mediation Server nel pool Enterprise Edition front-end, verificare che la casella di controllo sia selezionata. Il ruolo del server verrà distribuito nei server del pool. Se si intende distribuire il server di mediazione come server autonomo, deselezionare la casella di controllo appropriata. Si distribuirà il server Mediation in un passaggio di distribuzione distinto dopo aver distribuito completamente il server front-end. Per informazioni sulla pianificazione di una collocazione, vedere Nozioni di [base sulla topologia per Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md).
    
6. Utilizzando i **ruoli del server associato con questa pagina del pool Front-End** , è possibile definire e associare ruoli del server al pool Front-end. Il ruolo seguente è disponibile:
    
    **Abilitare un pool di bordi** Definisce e associa un singolo Edge Server o un pool di Edge Server. Un Edge Server facilita la comunicazione e la collaborazione tra gli utenti all'interno dell'organizzazione e le persone esterne all'organizzazione, inclusi gli utenti federati.
    
    Esistono due scenari possibili che è possibile usare per distribuire e associare i ruoli del server.
    
    Per scenario uno, si sta definendo una nuova topologia per una nuova installazione. È possibile avvicinarsi all'installazione in uno dei due modi seguenti:
    
   - Abbandonare la casella di controllo e definire la topologia. Dopo aver pubblicato, configurato e testato i ruoli del server front-end e back-end, è possibile eseguire di nuovo il generatore di topologia per aggiungere i server dei ruoli alla topologia. Usando questa strategia, puoi testare il pool Front end e il server che usa SQL Server senza ulteriori complicazioni da ruoli aggiuntivi. Dopo aver completato il test iniziale, è possibile eseguire di nuovo il generatore di topologia per selezionare i ruoli che è necessario distribuire.
    
   - Selezionare i ruoli che è necessario installare e quindi configurare l'hardware in grado di ospitare i ruoli selezionati.
    
     Per lo scenario due è disponibile una distribuzione esistente e l'infrastruttura è pronta per i nuovi ruoli oppure è necessario associare i ruoli esistenti a un nuovo server front-end.
    
   - In questo caso, selezionare i ruoli che si desidera distribuire o associare al nuovo server front-end. In entrambi i casi, procedere con la definizione dei ruoli, configurare l'hardware necessario e procedere con l'installazione.
    
7. Verrà quindi definito l'archivio di SQL Server che verrà usato con la topologia. In questo esempio usiamo l'istanza predefinita. Per altre informazioni sulle caratteristiche di SQL Server, ad esempio l'elevata disponibilità, vedere [pianificare l'elevata disponibilità e il ripristino di emergenza in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
    
   - Per usare un archivio di SQL Server esistente già definito nella topologia, selezionare un'istanza da **SQL Store**.
    
   - Per definire una nuova istanza di SQL Server per archiviare le informazioni sul pool, fare clic su **nuovo**e quindi specificare il **nome di dominio completo di SQL Server** nella finestra di dialogo Definisci **nuovo archivio SQL** .
    
   - Per specificare il nome di un'istanza di SQL Server, selezionare **istanza denominata**e quindi specificare il nome dell'istanza.
    
   - Per usare l'istanza predefinita, fare clic su **istanza predefinita**.
    
   - Per usare il mirroring SQL, selezionare **Abilita il mirroring SQL**e selezionare un'istanza esistente oppure creare una nuova istanza.

     > [!NOTE]
     > Il mirroring SQL è disponibile in Skype for Business Server 2015 ma non è più supportato in Skype for Business Server 2019. I gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn (FCI) e i metodi di clustering di failover SQL sono preferiti con Skype for Business Server 2019.
    
     Per questo esempio, immettiamo il **nome di dominio completo di SQL Server**e configuriamo tutte le impostazioni relative a disponibilità elevata e quindi fai clic su **OK**, come illustrato nella figura.
    
     ![Creare un archivio di SQL Server.](../../media/12822cf9-8608-43c0-94ce-2ca8b3a0ffd5.png)
  
8. Decidere se si vuole abilitare il mirroring di SQL Server Store o il witness di SQL Server mirroring e quindi fare clic su **Avanti**.
    
9. Definire la condivisione di file che si vuole usare.
    
   - Per usare una condivisione file già definita nella topologia, selezionare **Usa una condivisione file definita in precedenza**.
    
   - Per definire una nuova condivisione file, selezionare **Definisci una nuova condivisione file**, nella casella **FQDN file server** immettere il nome di dominio completo del file server esistente in cui si trova la condivisione file e quindi immettere un nome per la condivisione file nella casella **condivisione file** .
    
     Per questo esempio, fare clic su **Definisci un nuovo archivio di file**, immettere l' **FQDN del file server** e la **condivisione file**e quindi fare clic su **Avanti**.
    
     > [!NOTE]
     > La condivisione file per Skype for Business Server può essere collocata ma non è consigliabile per motivi di prestazioni. Si noti che in questo esempio la condivisione file si trova in un singolo server dedicato che fungerà da condivisione file. Si consigliano tuttavia altri sistemi di condivisione file più affidabili, come DFS che usa Windows Server 2012 R2. Per informazioni dettagliate sui sistemi di condivisione file supportati, vedere [requisiti per l'ambiente Skype for business](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md). Per altre informazioni sulla creazione della condivisione file, vedere [creare una condivisione file in Skype for Business Server](create-a-file-share.md). È possibile definire la condivisione file senza che la condivisione file sia stata creata. Sarà necessario creare la condivisione file nella posizione definita prima di pubblicare la topologia. 
  
10. Nella pagina specificare l'URL dei servizi Web è necessario decidere se è necessario eseguire l'override dell'URL di base del pool di servizi Web interni. Il motivo per cui questo override ha a che fare con il bilanciamento del carico. Il traffico SIP di base può essere caricato in modo equilibrato tramite il semplice bilanciamento del carico DNS. Tuttavia, il traffico di rete HTTP/S Web Services deve usare una soluzione di bilanciamento del carico hardware o software supportata. Per gli operatori di bilanciamento del carico supportati, Vedi [infrastruttura per Skype for business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways). In questo esempio è stato usato il bilanciamento del carico DNS per il traffico SIP e una soluzione di bilanciamento del carico software supportata. Poiché stiamo dividendo il traffico in questo modo, è necessario eseguire l'override del nome FQDN del pool di servizi Web interni. In alternativa, se si dispone di un servizio di bilanciamento del carico di linea superiore e si invia tutto il traffico tramite il bilanciamento del carico DNS per il traffico SIP, non è necessario eseguire l'override dell'URL dei servizi Web. 
    
    Nella sezione DNS di questo argomento è stato creato un record A per webint. contoso. local. Questo è l'URL usato per il traffico HTTP/S dei servizi Web e deve passare attraverso il servizio di bilanciamento del carico software supportato configurati. Quindi, in questo esempio, eseguiamo l'override dell'URL per consentire a Skype for Business Server di sapere che tutto il traffico HTTP/S deve andare a webint. contoso. local invece di pool. contoso. local, come illustrato nella figura. Per altre informazioni sul bilanciamento del carico, vedere [requisiti di bilanciamento del carico per Skype for business](../../plan-your-deployment/network-requirements/load-balancing.md).
    
    > [!IMPORTANT]
    > L'URL di base è l'identità dei servizi Web per l'URL, meno il https://. Ad esempio, se l'URL completo per i servizi Web del pool è https://webint.contoso.local, l'URL di base è webint. contoso. local. 
  
    - Se si sta configurando il bilanciamento del carico DNS, come in questo esempio, selezionare la casella di controllo Sostituisci il **nome completo del pool di servizi Web interni** e immettere l'URL di base interno (che deve essere diverso dal nome FQDN del pool) nell' **URL di base interno**. 
    
    > [!CAUTION]
    > Se si decide di ignorare i servizi Web interni con un nome di dominio completo definito autonomamente, ogni FQDN deve essere univoco da qualsiasi altro pool di front end, Director o Director. **Usare solo caratteri standard** (inclusi gli A-Z, a-z, 0-9 e i trattini) quando si definiscono URL o nomi di dominio completi. Non usare caratteri Unicode o carattere di sottolineatura. I caratteri non standard in un URL o FQDN spesso non sono supportati da autorità di certificazione pubbliche e DNS esterne (CAs), ovvero quando l'URL o il nome di dominio completo deve essere assegnato al nome dell'oggetto o all'oggetto alternativo nel certificato.
  
    - Facoltativamente, immettere l'URL della base esterna nell' **URL di base esterno**. Immettere l'URL della base esterna per differenziarlo dal nome di dominio interno. Ad esempio, il dominio interno è contoso. local, ma il nome di dominio esterno è contoso.com. Definiresti l'URL usando il nome di dominio contoso.com perché deve essere risolvibile da DNS pubblico. Questo è importante anche nel caso di un proxy inverso. Il nome di dominio dell'URL di base esterno corrisponde al nome di dominio dell'FQDN del proxy inverso. L'accesso HTTP al pool Front-End è necessario per la messaggistica istantanea e la presenza nei client mobili.
    
      ![Eseguire l'override dei servizi Web.](../../media/8f95313c-2df4-4885-adc5-9fc9ea775406.png)
  
11. Se è stata selezionata l'opzione servizi di **conferenza** nella pagina **Seleziona caratteristiche** , verrà chiesto di selezionare un server di Office Web Apps. Fare clic su **nuovo** per avviare la finestra di dialogo.
    
12. Nella finestra di dialogo **Definisci nuovo server Office Web Apps** Digitare il nome di dominio completo del server di Office Web Apps nella casella **FQDN server di Office Web Apps** . Quando si esegue questa operazione, l'URL di individuazione del server di Office Web Apps deve essere automaticamente immesso nella casella **URL individuazione server di Office Web Apps** .
    
    Se il server Office Web Apps è installato in locale e nella stessa area di rete di Skype for Business Server, non selezionare l'opzione il **Server Office Web Apps è distribuito in una rete esterna (ovvero perimetro/Internet)**.
    
    Se il server Office Web Apps è distribuito all'esterno del firewall interno, selezionare l'opzione **Office Web Apps Server è distribuito in una rete esterna (ovvero perimetro/Internet)**.
    
13. Fare clic su **fine** per completare la configurazione. Se sono stati definiti altri server di ruoli nei **ruoli del server associato con questa pagina del pool Front-End** , verranno aperte le pagine della configurazione guidata dei ruoli, in cui è possibile configurare i ruoli del server. In questo esempio abbiamo scelto solo i servizi di conferenza.
    
### <a name="configure-simple-urls"></a>Configurare gli URL semplici

1. In Generatore di topologie fare clic con il pulsante destro del mouse sul nodo principale **di Skype for Business Server** e quindi scegliere **modifica proprietà**, come illustrato nella figura.
    
     ![Fare clic con il pulsante destro del mouse su Skype for Business Server e scegliere Modifica proprietà.](../../media/692c18dd-8e99-4239-ae7b-5e855d866afa.png)
  
2. Nel riquadro **URL semplici** selezionare **URL di accesso telefonico:** (chiamata in ingresso) o URL delle **riunioni: (riunione** ) per modificare e quindi fare clic su **modifica URL**.
    
3. Aggiornare l'URL con il valore desiderato e quindi fare clic su **OK** per salvare l'URL modificato. È consigliabile configurare l'URL semplice usando il dominio SIP esterno in modo che gli utenti esterni possano partecipare alle riunioni, ad esempio contoso.com, che è esterno, anziché contoso. local, che è un dominio interno. Il dominio SIP dovrebbe quindi essere in grado di essere risolto dal DNS esterno.
    
4. Modificare l'URL di riunione usando la stessa procedura, se necessario.
    
### <a name="to-define-the-optional-admin-simple-url"></a>Per definire l'URL semplice amministratore facoltativo

1. In Generatore di topologie fare clic con il pulsante destro del mouse sul nodo **di Skype for Business Server** e quindi scegliere **modifica proprietà**.
    
2. Nella casella **URL di accesso amministrativo** immettere il semplice URL desiderato per l'accesso amministrativo al pannello di controllo di Skype for Business Server e quindi fare clic su **OK**.
    
    > [!TIP]
    > È consigliabile usare l'URL più semplice possibile per l'URL di amministratore. L'opzione più semplice è https://admin. _ \<domain\>_. L'URL di amministratore può essere un dominio interno o esterno, ad esempio contoso. local o contoso.com, purché entrambi i record siano risolvibili in DNS interno. 
  
    > [!IMPORTANT]
    > Se si modifica un URL semplice dopo la distribuzione iniziale, è necessario essere consapevoli delle modifiche che incidono sui record DNS (Domain Name System) e sui certificati per gli URL semplici. Se la modifica ha un impatto sulla base di un URL semplice, è necessario modificare anche i record e i certificati DNS. Ad esempio, passando da https://sfb.contoso.com/Meet per https://meet.contoso.com cambiare l'URL di base da SFB.contoso.com a meet.contoso.com, è necessario modificare i record DNS e i certificati per fare riferimento a meet.contoso.com. Se è stato modificato l'URL https://sfb.contoso.com/Meet semplice https://sfb.contoso.com/Meetings, l'url di base di SFB.contoso.com rimane invariato, quindi non sono necessarie modifiche DNS o di certificato. Ogni volta che si modifica un nome di URL semplice, è necessario eseguire il cmdlet **Enable-CsComputer** su ogni Director e front end server per registrare la modifica.
  
### <a name="publish-and-verify-the-topology"></a>Pubblicare e verificare la topologia

1. Verificare che tutti gli URL semplici siano configurati correttamente.
    
2. Verificare che il server basato su SQL Server sia online e disponibile per il computer in cui è installato Generatore di topologia, incluse le regole del firewall necessarie.
    
3. Verificare che la condivisione file sia disponibile e che siano definite le autorizzazioni appropriate.
    
4. Verificare che i ruoli del server corretti che soddisfano i requisiti di distribuzione siano definiti nella topologia.
    
5. Verificare che i server siano presenti in servizi di dominio Active Directory. Questo problema si verifica automaticamente quando si uniscono i server al dominio.
    
    Dopo aver verificato la topologia e non sono presenti errori di convalida, è necessario essere pronti per pubblicare la topologia. Se sono presenti errori di convalida, è necessario correggerli prima di poter pubblicare la topologia.
    
6. Fare clic con il pulsante destro del mouse sul nodo **di Skype for Business Server** e quindi scegliere **Pubblica topologia**.
    
7. Nella pagina **pubblica la topologia** fare clic su **Avanti**.
    
8. Nella pagina **Seleziona server di gestione centrale** selezionare un pool di front-end, come illustrato nella figura.
    
    > [!NOTE]
    > È possibile fare clic su **Avanzate** per configurare i percorsi di file di database.
  
     ![Selezionare Server Central Management store.](../../media/764478b5-8480-42c5-854f-649bb121cd94.png)
  
9. Nella pagina **Selezione database** selezionare i database che si desidera pubblicare.
    
    > [!NOTE]
    > Se non si hanno i diritti appropriati per creare i database, è possibile deselezionare le caselle di controllo accanto a tali database e un utente con diritti appropriati può creare i database in un secondo momento. Per informazioni dettagliate sui requisiti, vedere [requisiti del server per Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md). 
  
10. Facoltativamente, fare clic su **Avanzate**. Usando le opzioni avanzate di posizionamento dei file di dati di SQL Server, è possibile selezionare le opzioni seguenti: 
    
    - **Determinare automaticamente il percorso del file di database** : questa opzione determina le migliori prestazioni operative in base alla configurazione del disco nel server basato su SQL Server distribuendo il log e i file di dati nella posizione migliore.
    
    - **Usare le impostazioni predefinite dell'istanza di SQL Server** : questa opzione consente di inserire file di log e di dati nel server basato su SQL Server tramite le opzioni di istanza. Questa opzione non usa la funzionalità operativa del server basato su SQL Server per determinare le posizioni ottimali per i registri e i dati. L'amministratore di SQL Server sposterebbe in genere il log e i file di dati in posizioni appropriate per le procedure di gestione dell'organizzazione e del server basato su SQL Server.
    
    Fare clic su **OK**e quindi su **Avanti**. 
    
11. Facoltativamente, fare clic su **Avanzate**. Usando le opzioni avanzate di posizionamento dei file di dati di SQL Server, è possibile selezionare le opzioni seguenti: 
    
    - **Determinare automaticamente il percorso del file di database** : questa opzione determina le migliori prestazioni operative in base alla configurazione del disco nel server basato su SQL Server distribuendo il log e i file di dati nella posizione migliore.
    
    - **Usare le impostazioni predefinite dell'istanza di SQL Server** : questa opzione consente di inserire file di log e di dati nel server basato su SQL Server tramite le opzioni di istanza. Questa opzione non usa la funzionalità operativa del server basato su SQL Server per determinare le posizioni ottimali per i registri e i dati. L'amministratore di SQL Server sposterebbe in genere il log e i file di dati in posizioni appropriate per le procedure di gestione dell'organizzazione e del server basato su SQL Server.
    
    Fare clic su **OK**.
    
12. Fare clic su **Avanti** per completare il processo di pubblicazione.
    
    > [!NOTE]
    > Un errore comune per questo passaggio consiste nel fatto che non è possibile creare i database di SQL Server. Quando il processo non può essere completato, viene fornito un errore, come illustrato nella figura. La causa più probabile è che l'utente che tenta di creare il database non disponga delle autorizzazioni appropriate oppure che non sia possibile contattare il sistema SQL Server a causa di un firewall o di un altro problema di rete. 
  
     ![Errore durante la creazione di Central Management store.](../../media/558bd2e4-2721-422d-9986-df86f642e6a1.png)
  
13. Al termine del processo di pubblicazione, viene visualizzato un collegamento per aprire un elenco dei passaggi successivi. Fare clic **su fare clic qui per aprire l'elenco attività** per visualizzare i passaggi successivi e quindi fare clic su **fine**. 
    
    Il messaggio "completato con avvisi" per la creazione del database non significa che si è verificato un errore. Il processo di installazione deve modificare le impostazioni in SQL Server per Skype for Business Server per funzionare correttamente. Quando un'impostazione viene modificata in SQL Server, viene registrata come avviso in modo che gli amministratori di SQL Server possano comprendere esattamente il completamento del processo di installazione. Se viene visualizzato un avviso, è possibile selezionare il record e quindi fare clic su **Visualizza registri** per visualizzare i dettagli dell'avviso.
    
    Quando la topologia è stata pubblicata correttamente, è possibile iniziare a installare una replica locale di Central Management store in ogni server che esegue Skype for Business Server nella topologia. È consigliabile iniziare con il primo pool Front-end. 
    

