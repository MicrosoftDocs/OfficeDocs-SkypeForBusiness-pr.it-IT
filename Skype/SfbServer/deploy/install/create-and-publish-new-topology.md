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
description: "Riepilogo: informazioni su come creare, pubblicare e verificare una nuova topologia prima di installare Skype for Business Server. Scaricare una versione di valutazione gratuita di Skype for Business Server dal Centro di valutazione Microsoft all'indirizzo: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server ."
ms.openlocfilehash: c18d0340c48a8bf07771d0892bed4d0740c63186
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812146"
---
# <a name="create-and-publish-new-topology-in-skype-for-business-server"></a>Creare e pubblicare una nuova topologia in Skype for Business Server
 
**Riepilogo:** Informazioni su come creare, pubblicare e verificare una nuova topologia prima di installare Skype for Business Server. Scaricare una versione di valutazione gratuita di Skype for Business Server dal Centro di valutazione Microsoft all'indirizzo: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) .
  
Prima di installare il sistema Skype for Business Server in ognuno dei server della topologia, è necessario creare una topologia e pubblicarla. Quando si pubblica una topologia, le informazioni sulla topologia vengono caricate nel database dell'archivio di gestione centrale. Se si tratta di un pool Enterprise Edition, il database dell'archivio di gestione centrale verrà creato la prima volta che si pubblica una nuova topologia. Se si tratta di Standard Edition, sarà necessario eseguire il processo Prepare First Standard Edition Server dalla Distribuzione guidata prima di pubblicare una topologia. In questo modo viene preparata la versione Standard Edition installando un'SQL Server Express Edition e creando l'archivio di gestione centrale. È possibile eseguire i passaggi da 1 a 5 in qualsiasi ordine. È tuttavia necessario eseguire i passaggi 6, 7 e 8 nell'ordine e dopo i passaggi da 1 a 5, come illustrato nel diagramma. Come creare e pubblicare una nuova topologia, vedere il passaggio 6 di 8.
  
![Diagramma di panoramica](../../media/c5c09ba2-c98b-4194-9857-7c3087c5560e.png)
  
## <a name="create-and-publish-new-topology"></a>Creare e pubblicare una nuova topologia

È possibile utilizzare Generatore di topologie di Skype for Business Server per progettare, definire, configurare e pubblicare topologie. Questo strumento è stato installato durante l'installazione degli Strumenti di amministrazione in precedenza nell'articolo. Quando si crea una topologia, è possibile scegliere tra diverse opzioni. In questa procedura verrà creata una topologia di base con le conferenze.
  
> [!IMPORTANT]
> Skype for Business Server richiede SQL Server per funzionare. I database principali sono noti come Archivio di gestione centrale. Se si distribuisce Enterprise Edition, questi database vengono creati quando si pubblica la topologia utilizzando la procedura seguente. In questo caso, Generatore di topologie richiederà le informazioni di connessione a un SQL Server installazione. Se si prevede di distribuire standard edition, sarà necessario installare SQL Server Express Edition prima di definire e pubblicare la nuova topologia. Per installare SQL Server Express Edition, è necessario aprire la Distribuzione guidata nel server che fungerà da Front End e quindi eseguire Prepare First Standard Edition Server. Quando si fa clic su Prepara primo server Standard Edition, la distribuzione guidata installa automaticamente SQL Server Express Edition e crea i database dell'archivio di gestione centrale. 
  
### <a name="create-a-new-topology"></a>Creare una nuova topologia

1. Accedere come utente standard con accesso a Generatore di topologie.
    
2. Aprire Generatore di topologie di Skype for Business Server.
    
3. Selezionare **Nuova topologia e** fare clic su **OK.**
    
4. Selezionare un percorso e un nome di file per il file di configurazione della topologia.
    
    > [!NOTE]
    > La configurazione della topologia viene salvata come file XML (con estensione tbxml) di Generatore di topologie. Quando si pubblica una topologia, si esegue il push delle informazioni di configurazione dal file al database SQL Server database. Quando si apre Generatore di topologie in futuro, è possibile scaricare la configurazione esistente da SQL Server direttamente in Generatore di topologie e pubblicarla nuovamente in SQL Server o salvarla come file di configurazione di Generatore di topologie. 
  
5. Nella schermata **Definire il dominio primario immettere** il dominio SIP **primario** e fare clic su **Avanti.** In questo esempio viene utilizzato **contoso.local,** come illustrato nella figura.
    
     ![Definire il dominio SIP primario.](../../media/353e6b38-485f-4042-8585-aefa6c74b554.png)
  
6. Aggiungere eventuali altri domini SIP supportati e quindi fare clic su **Avanti.**
    
7. Immettere un **nome** e **una descrizione** per il primo sito (posizione), quindi fare clic su **Avanti**, come illustrato nella figura.
    
     ![Definire il primo sito (posizione).](../../media/d8b6c54a-2011-4efb-97fb-a4de0f11303c.png)
  
8. Immettere il **codice città,**  **provincia e** paese per il sito e quindi fare clic su **Avanti.**
    
9. Fare **clic** su Fine per completare il processo di definizione di una nuova topologia. La Creazione guidata nuovo front-end viene avviata automaticamente.
    
### <a name="define-a-front-end-pool-or-standard-edition-server"></a>Definire un pool Front End o un server Standard Edition

1. Esaminare i prerequisiti della procedura guidata e quindi fare clic su **Avanti.**
    
2. Immettere il nome di dominio completo (FQDN) del pool e selezionare Pool **Enterprise Edition Front End** o Server Standard **Edition** e quindi fare clic su **Avanti,** come illustrato nella figura.
    
    > [!TIP]
    > Skype for Business Server Enterprise Edition può includere più server che collaborano per fornire il ruolo Front End. Quando vengono utilizzati più server per svolgere il ruolo, viene chiamato pool. Di conseguenza, più server che collaborano per fornire il ruolo Front End vengono definiti anche pool Front End. Skype for Business Server Standard Edition può includere un solo server per fornire il ruolo Front End. È comune fare riferimento al pool Front End anche se solo un singolo server fornisce il ruolo. 
  
     ![Definire il pool front-end.](../../media/c1447557-261e-4260-a362-ab8d19070eb9.png)
  
3. Immettere i nomi di dominio completi (FQDN) di tutti i computer del pool e quindi fare clic su Avanti **come** illustrato nella figura.
    
     ![Definire i computer nel pool.](../../media/1106b4f3-8745-485b-b495-f885a5dfefda.png)
  
4. Selezionare le funzionalità che verranno incluse in questa topologia e quindi fare clic su **Avanti** come illustrato nella figura.
    
    > [!NOTE]
    > Skype for Business Server include molte funzionalità avanzate. Esaminare la documentazione relativa alla pianificazione e alla distribuzione per ogni funzionalità specifica che si desidera utilizzare. 
  
     ![Selezionare le funzionalità per la distribuzione.](../../media/77257588-d0e1-4517-a12a-869ffe009353.png)
  
5. Nella pagina **Selezione ruoli server collocati** è possibile scegliere di collocare il Mediation Server nel Front End Server oppure di distribuirlo come server autonomo.
    
    Se si intende collocare il Mediation Server nel pool Enterprise Edition Front End, verificare che la casella di controllo sia selezionata. I ruoli del server verranno distribuiti nei server del pool. Se si intende distribuire il Mediation Server come server autonomo, deselezionare la casella di controllo appropriata. Il Mediation Server verrà distribuito in un passaggio di distribuzione separato dopo aver distribuito completamente il Front End Server. Per informazioni dettagliate sulla collocazione, vedere [Topology Basics for Skype for Business Server.](../../plan-your-deployment/topology-basics/topology-basics.md)
    
6. Utilizzando la **pagina Associa ruoli del server a questo pool Front End,** è possibile definire e associare ruoli del server al pool Front End. È disponibile il seguente ruolo:
    
    **Abilitare un pool di server perimetrali** Definisce e associa un singolo server perimetrale o un pool di server perimetrali. Un server perimetrale facilita la comunicazione e la collaborazione tra gli utenti interni all'organizzazione e le persone esterne all'organizzazione, inclusi gli utenti federati.
    
    Esistono due possibili scenari che è possibile utilizzare per distribuire e associare i ruoli del server.
    
    Per il primo scenario, è necessario definire una nuova topologia per una nuova installazione. È possibile affrontare l'installazione in uno dei due modi seguenti:
    
   - Lasciare deselezionata la casella di controllo e definire la topologia. Dopo aver pubblicato, configurato e testato i ruoli Front End Server e Server back-end, è possibile eseguire di nuovo Generatore di topologie per aggiungere i server dei ruoli alla topologia. Utilizzando questa strategia, è possibile testare il pool Front End e il server che esegue SQL Server senza ulteriori complicazioni da altri ruoli. Dopo aver completato il test iniziale, è possibile eseguire di nuovo Generatore di topologie per selezionare i ruoli da distribuire.
    
   - Selezionare i ruoli che è necessario installare e quindi configurare l'hardware per gestire i ruoli selezionati.
    
     Per lo scenario 2, si dispone di una distribuzione esistente e l'infrastruttura è pronta per i nuovi ruoli oppure è necessario associare i ruoli esistenti a un nuovo Front End Server.
    
   - In questo caso, verranno selezionati i ruoli che si intende distribuire o associare al nuovo Front End Server. In entrambi i casi, sarà necessario procedere con la definizione dei ruoli, la configurazione dell'hardware necessario e l'installazione.
    
7. Successivamente, verrà definito l SQL Server di archiviazione che verrà utilizzato con la topologia. In questo esempio viene utilizzata l'istanza Default. Per ulteriori informazioni sulle SQL Server, ad esempio Disponibilità elevata, vedere Pianificare la disponibilità elevata e il ripristino di emergenza [in Skype for Business Server.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
    
   - Per utilizzare un archivio di SQL Server esistente già definito nella topologia, selezionare **Archivio SQL**.
    
   - Per definire una nuova istanza SQL Server in cui archiviare le informazioni sul pool, fare clic su Nuovo e quindi specificare **l'FQDN** SQL Server nella finestra di dialogo Definisci nuovo **SQL Store.**
    
   - Per specificare il nome di un'istanza di SQL Server, selezionare **Istanza denominata** e quindi specificare il nome dell'istanza.
    
   - Per utilizzare l'istanza predefinita, fare clic su **Istanza predefinita**.
    
   - Per usare SQL mirroring, selezionare **Abilita SQL mirroring** e selezionare un'istanza esistente oppure creare una nuova istanza.

     > [!NOTE]
     > SQL mirroring è disponibile in Skype for Business Server 2015, ma non è più supportato in Skype for Business Server 2019. I gruppi di disponibilità AlwaysOn, le istanze del cluster di failover AlwaysOn e i metodi di clustering di failover SQL sono preferiti con Skype for Business Server 2019.
    
     Per questo esempio, immettiamo il nome di dominio completo **SQL Server** e configureremo le eventuali impostazioni di disponibilità elevata rilevanti e quindi facciamo clic su **OK,** come illustrato nella figura.
    
     ![Creare un SQL Server store.](../../media/12822cf9-8608-43c0-94ce-2ca8b3a0ffd5.png)
  
8. Decidere se abilitare il mirroring dell SQL Server o il SQL Server mirroring e quindi fare clic su **Avanti.**
    
9. Definire la condivisione file che si desidera utilizzare.
    
   - Per utilizzare una condivisione file già definita nella topologia, selezionare **Utilizza condivisione file definita in precedenza**.
    
   - Per definire una nuova condivisione file, selezionare **Definisci nuova condivisione file**, nella casella **FQDN file server** immettere l'FQDN del file server esistente in cui deve trovarsi la condivisione file e quindi immettere un nome per la condivisione nella casella **Condivisione file**.
    
     Per questo esempio, fare clic su Definisci un nuovo **archivio file,** immettere l'FQDN e la condivisione **file** **del file server** e quindi fare clic su **Avanti.**
    
     > [!NOTE]
     > La condivisione file per Skype for Business Server può essere collocata, ma non è consigliabile per motivi di prestazioni. Si noti che in questo esempio la condivisione file si trova in un singolo server dedicato che fungerà da condivisione file. Tuttavia, sono consigliati altri sistemi di condivisione file più affidabili, ad esempio DFS con Windows Server 2012 R2. Per informazioni dettagliate sui sistemi di condivisione file supportati, vedere [Requisiti per l'ambiente Skype for Business.](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) Per ulteriori informazioni sulla creazione della condivisione file, vedere [Creare una condivisione file in Skype for Business Server.](create-a-file-share.md) È possibile definire la condivisione file senza che questa sia stata creata. Sarà necessario creare la condivisione file nella posizione definita prima di pubblicare la topologia. 
  
10. Nella pagina Specifica URL servizi Web è necessario decidere se sostituire l'URL di base del pool di servizi Web interno. Il motivo di questa sostituzione è associato al bilanciamento del carico. Il traffico SIP di base può essere bilanciato tramite un semplice bilanciamento del carico DNS. Tuttavia, il traffico di rete dei servizi Web HTTP/S deve utilizzare una soluzione di bilanciamento del carico hardware o software supportata. Per i servizi di bilanciamento del carico supportati, vedere [Infrastruttura per Skype for Business.](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) In questo esempio è stato utilizzato il bilanciamento del carico DNS per il traffico SIP e una soluzione di bilanciamento del carico software supportata. Poiché il traffico viene diviso in questo modo, è necessario sostituire l'FQDN interno del pool di servizi Web. In alternativa, se si disponesse di un servizio di bilanciamento del carico di linea superiore e si invii tutto il traffico attraverso di esso invece di utilizzare il bilanciamento del carico DNS per il traffico SIP, non sarebbe necessario sostituire l'URL dei servizi Web. 
    
    Nella sezione DNS di questo argomento è stato creato un record A per webint.contoso.local. Questo è l'URL che viene utilizzato per il traffico HTTP/S dei servizi Web e deve passare attraverso il servizio di bilanciamento del carico software supportato configurato. Pertanto, in questo esempio, viene eseguito l'override dell'URL per instradare Skype for Business Server che tutto il traffico HTTP/S deve passare a webint.contoso.local anziché a pool.contoso.local, come illustrato nella figura. Per ulteriori informazioni sul bilanciamento del carico, vedere [Requisiti di bilanciamento del carico per Skype for Business.](../../plan-your-deployment/network-requirements/load-balancing.md)
    
    > [!IMPORTANT]
    > L'URL di base è l'identità dei servizi Web per l'URL meno https://. Se ad esempio l'URL completo per i servizi Web del pool è https://webint.contoso.local , l'URL di base sarà webint.contoso.local. 
  
    - Se si sta configurando il bilanciamento del carico DNS, come in questo esempio, selezionare la casella di controllo Sostituisci FQDN pool di servizi **Web** interni e immettere l'URL di base interno (che deve essere diverso dall'FQDN del pool) in **URL di base interno.** 
    
    > [!CAUTION]
    > Se si decide di sostituire i servizi Web interni con un FQDN autodefinito, ogni FQDN deve essere univoco da qualsiasi altro pool Front End, Director o pool di server Director. **Utilizzare solo caratteri standard** (inclusi A-Z, a-z, 0-9 e trattini) quando si definiscono URL o nomi di dominio completi. Non utilizzare caratteri Unicode o di sottolineatura. I caratteri non standard in un URL o FQDN spesso non sono supportati da DNS esterni e da autorità di certificazione (CA) pubbliche, ovvero quando l'URL o il nome di dominio completo deve essere assegnato al nome soggetto o al nome alternativo del soggetto nel certificato.
  
    - Facoltativamente, immettere l'URL di base esterno in **URL di base esterno.** Immettere l'URL di base esterno per distinguerlo dal nome di dominio interno. Ad esempio, il dominio interno è contoso.local, ma il nome di dominio esterno è contoso.com. È necessario definire l'URL utilizzando contoso.com di dominio poiché deve essere risolvibile dal DNS pubblico. Questo è un aspetto importante anche nel caso di un proxy inverso. Il nome di dominio dell'URL di base esterno corrisponderebbe al nome di dominio dell'FQDN del proxy inverso. L'accesso HTTP al pool Front End è necessario per la messaggistica istantanea e la presenza nei client mobili.
    
      ![Eseguire l'override dei servizi Web.](../../media/8f95313c-2df4-4885-adc5-9fc9ea775406.png)
  
11. Se nella pagina **Selezione** **funzionalità** è stata selezionata l'opzione Servizio di conferenza, verrà richiesto di selezionare un server Office Web Apps. Fare **clic su** Nuovo per avviare la finestra di dialogo.
    
12. Nella finestra **di dialogo Definisci nuovo server Office Web Apps** digitare il nome di dominio completo del server Office Web Apps nella casella FQDN server Office Web **Apps.** Quando si esegue questa operazione, l'URL di individuazione del server Office Web Apps deve essere immesso automaticamente nella casella URL di individuazione del **server Office Web Apps.**
    
    Se il server Office Web Apps è installato in locale e nella stessa area di rete di Skype for Business Server, non selezionare l'opzione Server Office Web Apps distribuita in una rete **esterna( perimetro/Internet).**
    
    Se il server Office Web Apps viene distribuito all'esterno del firewall interno, selezionare l'opzione Server Office Web Apps distribuito in una rete esterna, ovvero **perimetro/Internet.**
    
13. Fare **clic su** Fine per completare la configurazione. Se nella pagina Associa ruoli server a questo **pool Front End** sono stati definiti altri server di ruolo, verranno aperte pagine separate della configurazione guidata dei ruoli in cui è possibile configurare i ruoli del server. In questo esempio è stata scelta solo la funzionalità di conferenza.
    
### <a name="configure-simple-urls"></a>Configurare GLI URL semplici

1. In Generatore di topologie fare clic con il pulsante destro del mouse sul nodo principale di **Skype for Business Server** e quindi scegliere Modifica proprietà , come illustrato nella figura. 
    
     ![Fai clic con il pulsante destro del mouse su Skype for Business Server e scegli Modifica proprietà.](../../media/692c18dd-8e99-4239-ae7b-5e855d866afa.png)
  
2. Nel riquadro **URL semplici,** selezionare URL di accesso **telefonico:** (accesso esterno) o URL **riunione:** (Riunione) per modificare, quindi fare clic su **Modifica URL.**
    
3. Aggiornare l'URL in base al valore desiderato e quindi fare clic su **OK** per salvare l'URL modificato. È consigliabile configurare l'URL semplice utilizzando il dominio SIP esterno in modo che gli utenti esterni possano partecipare alle riunioni, ad esempio contoso.com, che è esterno, anziché contoso.local, che è un dominio interno. Pertanto, il dominio SIP deve essere in grado di essere risolto da DNS esterno.
    
4. Se necessario, modificare l'URL riunione eseguendo la stessa procedura.
    
### <a name="to-define-the-optional-admin-simple-url"></a>Per definire l'URL semplice facoltativo per l'accesso amministrativo

1. In Generatore di topologie fare clic con il pulsante destro del mouse sul nodo **Skype for Business Server** e quindi scegliere Modifica **proprietà.**
    
2. Nella casella **URL accesso** amministrativo immettere l'URL semplice desiderato per l'accesso amministrativo al Pannello di controllo di Skype for Business Server e quindi fare clic su **OK.**
    
    > [!TIP]
    > È consigliabile utilizzare l'URL più semplice possibile per l'accesso amministrativo. L'opzione più semplice è https://admin _\<domain\>_ ... L'URL di amministrazione può essere un dominio interno o esterno, ad esempio contoso.local o contoso.com, purché uno dei due record sia risolvibile nel DNS interno. 
  
    > [!IMPORTANT]
    > Se si modifica un URL semplice dopo la distribuzione iniziale, è necessario considerare quali modifiche influiscono sui record DNS (Domain Name System) e sui certificati per gli URL semplici. Se la modifica influisce sulla base di un URL semplice, è necessario modificare anche i record DNS e i certificati. Ad esempio, se si cambia l'URL di base da sfb.contoso.com a meet.contoso.com, è necessario modificare i record DNS e i certificati per fare riferimento a https://sfb.contoso.com/Meet https://meet.contoso.com meet.contoso.com. Se è stato modificato l'URL semplice da a , l'URL di base di sfb.contoso.com rimane lo stesso, quindi non sono necessarie modifiche al https://sfb.contoso.com/Meet https://sfb.contoso.com/Meetings DNS o al certificato. Ogni volta che si modifica un nome DI URL semplice, tuttavia, è necessario eseguire il cmdlet **Enable-CsComputer** in ogni Server Director e Front End Server per registrare la modifica.
  
### <a name="publish-and-verify-the-topology"></a>Pubblicare e verificare la topologia

1. Controllare che tutti gli URL semplici siano configurati in modo corretto.
    
2. Verificare che il server basato SQL Server sia online e disponibile per il computer in cui è installato Generatore di topologie, incluse le eventuali regole firewall necessarie.
    
3. Verificare che la condivisione file sia disponibile e che siano definite le autorizzazioni appropriate.
    
4. Verificare che nella topologia siano definiti i ruoli del server corretti conformi ai requisiti della distribuzione.
    
5. Verificare che i server esistano in Servizi di dominio Active Directory. Ciò avviene automaticamente quando si uniscono i server al dominio.
    
    Dopo aver verificato la topologia e stabilito che non sono presenti errori di convalida, è possibile procedere con la pubblicazione della topologia. Se si verificano errori di convalida, è necessario correggerli prima di pubblicare la topologia.
    
6. Fare clic con il pulsante destro del mouse sul nodo **Skype for Business Server** e quindi scegliere Pubblica **topologia.**
    
7. Nella pagina **Pubblicare la topologia** fare clic su **Avanti**.
    
8. Nella pagina **Selezione server di gestione** centrale selezionare un pool Front End, come illustrato nella figura.
    
    > [!NOTE]
    > È possibile fare clic **su Avanzate** per configurare i percorsi dei file di database.
  
     ![Selezionare il server dell'archivio di gestione centrale.](../../media/764478b5-8480-42c5-854f-649bb121cd94.png)
  
9. Nella pagina **Selezione database** selezionare i database che si desidera pubblicare.
    
    > [!NOTE]
    > Se non si dispone dei diritti appropriati per creare i database, è possibile deselezionare le caselle di controllo accanto a tali database e un utente con i diritti appropriati potrà successivamente creare i database. Per informazioni dettagliate sui requisiti, vedere [Requisiti del server per Skype for Business Server.](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) 
  
10. Facoltativamente, fare clic su **Avanzate**. Utilizzando le opzioni avanzate SQL Server posizionamento dei file di dati, è possibile scegliere tra le opzioni seguenti: 
    
    - **Determinare automaticamente** il percorso dei file di database: questa opzione determina le migliori prestazioni operative in base alla configurazione del disco nel server basato su SQL Server distribuendo i file di registro e di dati nel percorso migliore.
    
    - **Usa SQL Server predefinite dell'istanza:** questa opzione inserisce i file di registro e di dati nel server basato SQL Server utilizzando le impostazioni dell'istanza. Non utilizza la funzionalità operativa del server basato su SQL Server di determinazione dei percorsi ottimali per i registri e i dati. L'amministratore di SQL Server in genere sposta i file di registro e di dati nei percorsi appropriati per le procedure di gestione del server basato su SQL Server e dell'organizzazione.
    
    Fare clic su **OK** e quindi su **Avanti**. 
    
11. Facoltativamente, fare clic **su Avanzate.** Utilizzando le opzioni avanzate SQL Server posizionamento dei file di dati, è possibile scegliere tra le opzioni seguenti: 
    
    - **Determinare automaticamente** il percorso dei file di database: questa opzione determina le migliori prestazioni operative in base alla configurazione del disco nel server basato su SQL Server distribuendo i file di registro e di dati nel percorso migliore.
    
    - **Usa SQL Server predefinite dell'istanza:** questa opzione inserisce i file di registro e di dati nel server basato SQL Server utilizzando le impostazioni dell'istanza. Non utilizza la funzionalità operativa del server basato su SQL Server di determinazione dei percorsi ottimali per i registri e i dati. L'amministratore di SQL Server in genere sposta i file di registro e di dati nei percorsi appropriati per le procedure di gestione del server basato su SQL Server e dell'organizzazione.
    
    Fare clic su **OK**.
    
12. Fare clic su **Avanti** per completare il processo di pubblicazione.
    
    > [!NOTE]
    > Un errore comune per questo passaggio è che non è possibile creare SQL Server database. Quando il processo non può essere completato, viene visualizzato un errore, come illustrato nella figura. La causa più probabile è che l'utente che tenta di creare il database non dispone delle autorizzazioni appropriate oppure che il sistema SQL Server non può essere contattato a causa di un firewall o di un altro problema di rete. 
  
     ![Errore durante la creazione dell'archivio di gestione centrale.](../../media/558bd2e4-2721-422d-9986-df86f642e6a1.png)
  
13. Al termine del processo di pubblicazione, viene visualizzato un collegamento per aprire un elenco dei passaggi successivi. Fare **clic qui per aprire l'elenco** attività per visualizzare i passaggi successivi e quindi fare clic su **Fine.** 
    
    Il messaggio "Completato con avvisi" per la creazione del database non indica che si è verificato un errore. Il processo di installazione deve modificare le impostazioni in SQL Server per il corretto funzionamento di Skype for Business Server. Quando un'impostazione viene modificata in SQL Server, viene registrata come avviso in modo che SQL Server amministratori possano comprendere esattamente cosa è stato completato il processo di installazione. Se viene visualizzato un avviso, è possibile selezionare il record e quindi fare clic su **Visualizza** registri per visualizzare i dettagli dell'avviso.
    
    Una volta pubblicata correttamente la topologia, è possibile iniziare a installare una replica locale dell'archivio di gestione centrale in ogni server che esegue Skype for Business Server nella topologia. È consigliabile iniziare con il primo pool Front End. 
    

