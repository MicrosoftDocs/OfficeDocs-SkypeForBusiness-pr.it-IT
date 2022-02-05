---
title: Distribuire server perimetrali in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - Strat_SB_Hybrid
ms.custom: null
ms.assetid: 63c7251c-080a-4175-99a6-f86d0266d6bc
description: 'Riepilogo: informazioni su come distribuire i server perimetrali nell''Skype for Business Server locale.'
---

# <a name="deploy-edge-servers-in-skype-for-business-server"></a>Distribuire server perimetrali in Skype for Business Server
 
**Riepilogo:** Informazioni su come distribuire i server perimetrali nell'Skype for Business Server locale.
  
Le sezioni seguenti contengono i passaggi che devono essere seguiti dopo la revisione del piano di Skype for Business Server [per](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) le distribuzioni di server perimetrali nella documentazione Skype for Business Server informazioni. I passaggi di distribuzione sono i seguenti:
  
- Interfacce di rete
    
- Installazione
    
- Certificati
    
- Avvio dei server perimetrali
    
## <a name="network-interfaces"></a>Interfacce di rete

Come illustrato in Pianificazione, l'interfaccia di rete verrà configurata con DNS nella rete perimetrale che ospita i server perimetrali o senza DNS nella rete perimetrale.
  
### <a name="interface-configuration-with-dns-servers-in-the-perimeter-network"></a>Configurazione dell'interfaccia con i server DNS nella rete perimetrale

1. Installare due schede di rete per ogni server perimetrale, una per l'interfaccia con connessione interna e una per l'interfaccia esterna.
    
    > [!NOTE]
    > Le subnet interna ed esterna non devono essere vicendevolmente instradabili. 
  
2. Nell'interfaccia esterna verrà configurata **una** delle opzioni seguenti:
    
   a. Tre indirizzi IP statici nella subnet della rete perimetrale esterna e puntano il gateway predefinito all'interfaccia interna del firewall esterno. Configurare le impostazioni DNS della scheda in modo che puntino a una coppia di server DNS perimetrali.
    
   b. Un indirizzo IP statico nella subnet della rete perimetrale esterna e puntare il gateway predefinito all'interfaccia interna del firewall esterno. Configurare le impostazioni DNS della scheda in modo che puntino a una coppia di server DNS perimetrali. Questa configurazione è accettabile SOLO se in precedenza la topologia è stata configurata in modo da avere valori non standard nelle assegnazioni delle porte, come illustrato nell'articolo Creare la topologia [Edge](create-your-edge-topology.md) per Skype for Business Server.
    
3. Nell'interfaccia interna configurare un IP statico nella subnet della rete perimetrale interna e non impostare un gateway predefinito. Configurare le impostazioni DNS della scheda in modo che puntino ad almeno un server DNS, ma preferibilmente a una coppia di server DNS perimetrali.
    
4. Creare route statiche persistenti nell'interfaccia interna a tutte le reti interne in cui risiedono client, Skype for Business Server e Exchange messaggistica unificata.
    
### <a name="interface-configuration-without-dns-servers-in-the-perimeter-network"></a>Configurazione dell'interfaccia senza server DNS nella rete perimetrale

1. Installare due schede di rete per ogni server perimetrale, una per l'interfaccia con connessione interna e una per l'interfaccia esterna.
    
    > [!NOTE]
    > Le subnet interna ed esterna non devono essere vicendevolmente instradabili. 
  
2. Nell'interfaccia esterna verrà configurata **una** delle opzioni seguenti:
    
   a. Tre indirizzi IP statici nella subnet della rete perimetrale esterna. Sarà inoltre necessario configurare il gateway predefinito nell'interfaccia esterna, ad esempio definendo il router con connessione Internet o il firewall esterno come gateway predefinito. Configurare le impostazioni DNS della scheda in modo che puntino a un server DNS esterno, idealmente una coppia di server DNS esterni.
    
   b. Un indirizzo IP statico nella subnet della rete perimetrale esterna. Sarà inoltre necessario configurare il gateway predefinito nell'interfaccia esterna, ad esempio definendo il router con connessione Internet o il firewall esterno come gateway predefinito. Configurare le impostazioni DNS della scheda in modo che puntino a un server DNS esterno o idealmente a una coppia di server DNS esterni. Questa configurazione è accettabile SOLO se in precedenza la topologia è stata configurata in modo da avere valori non standard nelle assegnazioni delle porte, come illustrato nell'articolo Creare la topologia [Edge](create-your-edge-topology.md) per Skype for Business Server.
    
3. Nell'interfaccia interna configurare un IP statico nella subnet della rete perimetrale interna e non impostare un gateway predefinito. Lasciare vuote anche le impostazioni DNS della scheda.
    
4. Creare route statiche persistenti nell'interfaccia interna a tutte le reti interne in cui risiedono client, Skype for Business Server e Exchange messaggistica unificata.
    
5. Modificare il file HOST in ogni server perimetrale in modo che contenga un record per il server hop successivo o l'IP virtuale (VIP). Questo record sarà il server Director, edizione Standard server o il pool Front End configurato come indirizzo dell'hop successivo del server perimetrale in Generatore di topologie. Se si utilizza il bilanciamento del carico DNS, includere una riga per ogni membro del pool dell'hop successivo.
    
## <a name="installation"></a>Installazione

Per completare correttamente questi passaggi, è necessario seguire i passaggi descritti nell'articolo Creare la topologia [edge per Skype for Business Server](create-your-edge-topology.md).
  
1. Accedere al server configurato per il ruolo Server perimetrale con un account presente nel gruppo dell'amministratore locale.
    
2. Sarà necessario il file di configurazione della topologia copiato alla fine della documentazione relativa alla topologia di server perimetrali nel computer. Accedi al supporto esterno in cui hai inserito il file di configurazione (ad esempio un'unità USB o una condivisione).
    
3. Avviare la **Distribuzione guidata**.
    
4. Una volta aperta la procedura guidata, fare **clic su Installa o aggiorna Skype for Business Server sistema**.
    
5. La procedura guidata eseguirà controlli per verificare se è già installato qualcosa. Poiché questa è la prima volta che si esegue la procedura guidata, è necessario iniziare dal **passaggio 1. Installare l'archivio di configurazione locale.**
    
6. Verrà **visualizzata la finestra di dialogo Configura replica** locale dell'archivio di gestione centrale. È necessario fare clic **su Importa da un file (consigliato per i server perimetrali)**.
    
7. Da qui passare al percorso della topologia esportata in precedenza, selezionare il file .zip, fare **clic su Apri** e quindi su **Avanti**.
    
8. La Distribuzione guidata leggerà il file di configurazione e scriverà il file di configurazione XML nel computer locale.
    
9. Al termine del processo **Esecuzione comandi in corso**, fare clic su **Fine**.
    
10. Nella Distribuzione guidata fare clic **su Passaggio 2. Installazione o rimozione di Skype for Business Server componenti.** La procedura guidata installerà quindi i Skype for Business Server Edge specificati nel file di configurazione XML archiviato nel computer locale.
    
11. Al termine dell'installazione, è possibile passare ai passaggi descritti nella **sezione Certificati** riportata di seguito.
    
## <a name="certificates"></a>Certificati

I requisiti dei certificati per il server perimetrale sono disponibili nella documentazione relativa alla pianificazione dei certificati perimetrali. Di seguito è riportata la procedura per la configurazione dei certificati.
  
> [!NOTE]
> Quando si esegue la Configurazione guidata certificati, è necessario essere connessi come account con le autorizzazioni corrette per il tipo di modello di certificato che si sta per utilizzare. Per impostazione predefinita, Skype for Business Server richiesta di certificato verrà utilizzato il modello di certificato server Web. Se si è connessi con un account membro del gruppo RTCUniversalServerAdmins per richiedere un certificato tramite questo modello, verificare che al gruppo siano state assegnate le autorizzazioni di registrazione per l'utilizzo di tale modello. 
  
### <a name="internal-edge-interface-certificates"></a>Certificati dell'interfaccia perimetrale interna

 
### <a name="1-download-or-export-the-ca-certification-chain"></a>1. Scaricare o esportare la catena di certificazione CA

 
#### <a name="nbspnbspnbsp-a-download-using-certsrv-web-site"></a>&nbsp;&nbsp;&nbsp; a. Download tramite il sito Web certsrv

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i. Accedere a un Skype for Business Server nella rete interna come membro del gruppo Administrators locale.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ii. Aprire **Start**, **Esegui** (o **Cerca** ed **esegui** ), quindi digitare quanto segue:
    
  ```console
  https://<NAME OF YOUR ISSUING CA SERVER>/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Per esempio:
    
  ```console
  https://ca01/contoso.com/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii. Nella pagina Web certsrv della CA emittente **, in Selezionare** un'attività, fare clic su Scarica un certificato CA, una catena di certificati **o un CRL**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv. In **Scarica un certificato CA, una catena di certificati o un CRL** fare clic su **Scarica catena di certificati CA**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v. Nella casella **Download file** fare clic su **Salva**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi. Salvare il file p7b nell'unità disco rigido del server e quindi copiarlo in una cartella in ognuno dei server perimetrali.
    
### <a name="nbspnbspnbspb-export-using-mmc"></a>&nbsp;&nbsp;&nbsp;b. Esportare tramite MMC

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i. È possibile esportare il certificato radice della CA da qualsiasi computer aggiunto a un dominio tramite MMC. Passare a **Start** ed **Esegui** oppure aprire **Ricerca** e digitare **MMC** da aprire.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ii. Nella console MMC fare clic su **File** e quindi su **Aggiungi/Rimuovi snap-in**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii. **Nell'elenco Della finestra di dialogo Aggiungi o rimuovi snap-in** scegliere **Certificati** e quindi fare clic su **Aggiungi**. Quando richiesto, selezionare **Account computer** e quindi **Avanti**. Nella finestra di dialogo **Selezione computer** selezionare **Computer locale**. Fare **clic su** Fine e quindi **su OK**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv. Espandere **Certificati (computer locale).**. Espandere **Autorità di certificazione radice attendibili**. Selezionare **Certificati**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v. Fare clic sul certificato radice emesso dalla CA. Fare clic con il pulsante destro del mouse **sul certificato,** scegliere Tutte le attività dal menu **e quindi esporta**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi. Verrà **visualizzata l'Esportazione guidata** certificati. Scegliere **Avanti**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vii. Nella finestra **di dialogo Esporta formato file** scegliere il formato in cui si desidera eseguire l'esportazione. Il nostro consiglio è **Cryptographic Message Syntax Standard - PKCS #7 Certificates (P7b)**. Se anche questa è la scelta giusta, ricordarsi di selezionare anche la casella di controllo Includi tutti i certificati nel percorso di certificazione, se possibile, **in** quanto verrà esportata anche la catena di certificati, incluso il certificato CA radice e gli eventuali certificati intermedi. Scegliere **Avanti**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;viii. Nella finestra **di dialogo** File da esportare digitare un percorso e un nome di file (l'estensione predefinita è p7b) per il certificato esportato. Se è più facile, scegliere il pulsante Sfoglia per  passare al percorso in cui si desidera salvare il certificato esportato e assegnare un nome al certificato esportato qui. Fare **clic** su Salva e **quindi** su Avanti quando si è pronti.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ix. Esaminare il riepilogo delle azioni e fare clic su **Fine** per completare l'esportazione del certificato. Fare clic su **OK** per confermare l'avvenuta esecuzione dell'esportazione.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;x. Copiare il file p7b in ognuno dei server perimetrali.
    
### <a name="2-import-the-ca-certification-chain"></a>2. Importare la catena di certificazione CA

&nbsp;&nbsp;&nbsp;a. In ogni server perimetrale, aprire MMC (scegliere **Start** ed **Esegui** o **Cerca** e digitare **MMC** da aprire).
    
&nbsp;&nbsp;&nbsp;b. Scegliere Aggiungi **/Rimuovi snap-in dal** menu **File** e quindi scegliere **Aggiungi**.
    
&nbsp;&nbsp;&nbsp;c. Nella casella **Aggiungi o rimuovi snap-in fare** clic su **Certificati** e quindi su **Aggiungi**.
    
&nbsp;&nbsp;&nbsp;d. Nella finestra di dialogo **Snap-in certificati** fare clic su **Account del computer** e quindi su **Avanti**.
    
&nbsp;&nbsp;&nbsp;e. Nella finestra **di dialogo** Seleziona computer verificare che la casella di controllo **Computer locale: (il computer** in cui è in esecuzione la console) sia selezionata e quindi fare clic su **Fine**.
    
&nbsp;&nbsp;&nbsp;f. Fare **clic su** Chiudi e quindi **su OK**.
    
&nbsp;&nbsp;&nbsp;g. Nell'albero della console espandere **Certificati (computer locale),** fare clic con il pulsante destro del mouse su Autorità di certificazione radice **attendibili, passare** a **Tutte** le attività e quindi fare clic su **Importa**.
    
&nbsp;&nbsp;&nbsp;h. Nella casella di testo **File da** importare della procedura guidata visualizzata specificare il nome file del certificato, ovvero il nome del file p7b nella sezione precedente. Scegliere **Avanti**.
    
&nbsp;&nbsp;&nbsp;i. Lasciare il pulsante di opzione **Inseriamo tutti i certificati nel seguente archivio,** in quanto è necessario selezionare Autorità di certificazione radice attendibili. Scegliere **Avanti**.
    
&nbsp;&nbsp;&nbsp;j. Esaminare il riepilogo e fare clic su **Fine** per completare l'importazione.
    
&nbsp;&nbsp;&nbsp;k. Questa operazione dovrà essere eseguita per ogni server perimetrale che si sta distribuendo.
    
### <a name="3-create-the-certificate-request"></a>3. Creare la richiesta di certificato

&nbsp;&nbsp;&nbsp;a. Accedere a uno dei server perimetrali, avviare la Distribuzione guidata e, nel passaggio **3: Richiesta,** installazione o assegnazione di certificati, fare clic su **Esegui (o** Esegui di **nuovo, se** è già stata eseguita questa procedura guidata).
    
&nbsp;&nbsp;&nbsp;b. Nella pagina **Richiesta di certificato** verificare che **l'opzione Certificato edge interno** sia selezionata e fare clic su **Richiesta**.
    
&nbsp;&nbsp;&nbsp;c. Nella pagina **Richieste** ritardate o immediate scegliere Invia la richiesta immediatamente a un'autorità di certificazione **online** se si ha accesso a una richiesta dall'ambiente Edge oppure Preparare la richiesta ora **,** ma inviarla in un secondo momento in caso contrario.
    
&nbsp;&nbsp;&nbsp;d. Nella pagina **File di richiesta** di certificato immetti la parte completa e il nome del file per il quale verrà salvato il file (ad esempio c:\SkypeInternalEdgeCert.cer). Scegliere **Avanti**.
    
&nbsp;&nbsp;&nbsp;e. Nella pagina **Specifica modello di certificato** alternativo, per utilizzare un modello diverso dal modello WebServer predefinito, selezionare la casella di controllo Usa modello di certificato alternativo per l'autorità di **certificazione** selezionata. In caso contrario, non eseguire alcuna operazione.
    
&nbsp;&nbsp;&nbsp;f. Nella pagina Impostazioni nome e sicurezza eseguire le operazioni seguenti:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i. In **Nome descrittivo** immettere un nome visualizzato per il certificato, ad esempio Perimetro interno.
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  ii. In **Lunghezza in** bit scegli la lunghezza in bit (il valore predefinito è 2048, puoi andare più in alto ed essere più sicuro, ma le prestazioni rallentano).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iii. Se è necessario un certificato esportabile, è necessario selezionare la **casella di** controllo Contrassegna la chiave privata del certificato come esportabile.
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iv. Scegliere **Avanti**.
    
&nbsp;&nbsp;&nbsp;g. Nella pagina **Informazioni organizzazione** immettere il nome dell'organizzazione e dell'unità organizzativa. È possibile immettere la divisione o il reparto ,ad esempio IT.
    
&nbsp;&nbsp;&nbsp;h. Nella pagina **Informazioni geografiche** immettere le informazioni sulla posizione.
    
&nbsp;&nbsp;&nbsp;i. Nella pagina **Nome soggetto/Nomi soggetto alternativi** deve essere popolato automaticamente dalla procedura guidata.
    
&nbsp;&nbsp;&nbsp;j. Nella pagina **Configura nomi soggetto alternativi** aggiuntivi è necessario aggiungere eventuali nomi alternativi soggetto aggiuntivi necessari.
    
&nbsp;&nbsp;&nbsp;k. Nella pagina **Riepilogo richieste** esaminare le informazioni sul certificato che verranno utilizzate per generare la richiesta. Se è necessario apportare modifiche, tornare indietro e farlo ora.
    
&nbsp;&nbsp;&nbsp;l. Fare quindi **clic** su Avanti per generare il file CSR che sarà necessario fornire all'autorità di certificazione (è anche  possibile fare clic su Visualizza registro per esaminare il registro per la richiesta di certificato).
    
&nbsp;&nbsp;&nbsp;m. Dopo aver generato la richiesta, è possibile fare **clic su Visualizza** per esaminare il certificato e **su Fine** per chiudere la finestra. Il contenuto del file CSR deve essere assegnato all'autorità di certificazione, in modo che possa generare un certificato da importare nel computer nella sezione successiva.
    

### <a name="4-import-the-certificate"></a>4. Importare il certificato

&nbsp;&nbsp;&nbsp;a. Accedere, come membro del gruppo Administrators locale, al server perimetrale da cui è stata effettuata la richiesta di certificato nell'ultima procedura.
    
&nbsp;&nbsp;&nbsp;b. Nella Distribuzione guidata, accanto al **passaggio 3. Richiedere, installare o assegnare certificati**, fare clic **su Esegui di nuovo**.
    
&nbsp;&nbsp;&nbsp;c. Nella pagina **Attività certificati disponibili** fare clic su **Importa un certificato da un . File P7b, pfx o cer**.
    
&nbsp;&nbsp;&nbsp;d. Nella pagina **Importa** certificato digitare il percorso completo e il nome del file del certificato ottenuto nella sezione precedente oppure fare clic su Sfoglia per trovare e  scegliere il file in questo modo.
    
&nbsp;&nbsp;&nbsp;e. Se si importano certificati per altri membri del pool di server perimetrali e il certificato contiene una chiave privata, assicurarsi di  selezionare la casella di controllo File di certificato contenente la chiave privata del certificato e specificare la password. Fare clic su **Avanti** per continuare.
    
&nbsp;&nbsp;&nbsp;f. Nella **paginaSummary** fare clic su **Avanti** dopo aver confermato le informazioni e su Fine dopo aver  importato correttamente il certificato.
    
 
### <a name="5-export-the-certificate"></a>5. Esportare il certificato

&nbsp;&nbsp;&nbsp;a. Assicurarsi di aver effettuato l'accesso al server perimetrale in cui è stato importato il certificato in precedenza, come membro del gruppo Administrators locale.
    
&nbsp;&nbsp;&nbsp;b. Fare **clic sul pulsante Start****, scegliere** Esegui (o **aprire Ricerca**) e digitare **MMC**.
    
&nbsp;&nbsp;&nbsp;c. Nella console MMC fare clic su **File** e **quindi su Aggiungi/Rimuovi snap-in**.
    
&nbsp;&nbsp;&nbsp;d. Nella casella **Aggiungi o rimuovi snap-in fare** clic su **Certificati** e quindi su **Aggiungi**.
    
&nbsp;&nbsp;&nbsp;e. Nella finestra **di dialogo** Snap-in Certificati scegliere **Account computer**. Scegliere **Avanti**.
    
&nbsp;&nbsp;&nbsp;f. Nella finestra **di dialogo Seleziona computer** selezionare **Computer locale: (computer in cui è in esecuzione la console)**. Fare clic su **Fine**. Fare **clic su OK** e la configurazione della console MMC è stata completata.
    
&nbsp;&nbsp;&nbsp;g. Fare doppio clic su **Certificati (computer locale)** per espandere gli archivi certificati. Fare doppio clic **su Personale** e quindi su **Certificati**.
    
  > [!NOTE]
  > È possibile che l'utente sia presente e che non sia presente alcun certificato nell'archivio personale certificati per il computer locale. Non è necessario eseguire la ricerca, se la chiave non è presente, al certificato importato non è associata una chiave privata. Provare la richiesta e importare i passaggi precedenti una volta e, se si è certi di aver ottenuto tutto ciò che è giusto, contattare l'amministratore o il provider della CA. 
  
&nbsp;&nbsp;&nbsp;h. **Nell'archivio personale certificati** per il computer locale fare clic con il pulsante destro del mouse sul certificato che si sta esportando. Selezionare **Tutte le attività** dal menu risultante e quindi fare clic su **Esporta**.
    
&nbsp;&nbsp;&nbsp;i. Nell'**Esportazione guidata certificati** fare clic su **Avanti**. Selezionare **Sì, esporta la chiave privata**. Fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;j. Nella finestra **di dialogo Esporta** formati file selezionare **Informazioni personali Exchange - PKCS#12 (. PFX)**, quindi selezionare quanto segue:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i. Includere tutti i certificati nel percorso di certificazione, se possibile.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   ii. Esportare tutte le proprietà estese.
    
   > [!NOTE]
   > **NON selezionare** MAI **Elimina la chiave privata se l'esportazione ha esito positivo**. Significa che devi reimportare il certificato e la chiave privata in questo server perimetrale.
  
&nbsp;&nbsp;&nbsp;k. Se si desidera assegnare una password per proteggere la chiave privata, è possibile digitare una password per la chiave privata. Immettere di nuovo la password per confermare e quindi fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;l. Digitare un percorso e un nome di file per il certificato esportato, utilizzando l'estensione **pfx**. Il percorso deve essere accessibile dagli altri server perimetrali del pool oppure è necessario spostare il file tramite supporti esterni ,ad esempio un'unità USB. Fare **clic** su Avanti dopo aver effettuato la scelta.
    
&nbsp;&nbsp;&nbsp;m. Esaminare il riepilogo nella finestra **di dialogo Completamento esportazione guidata** certificati e quindi fare clic su **Fine**.
    
&nbsp;&nbsp;&nbsp;n. Fare clic su **OK** nella finestra di dialogo di conclusione dell'esportazione.
    
 
### <a name="6-assign-the-certificate"></a>6. Assegnare il certificato

&nbsp;&nbsp;&nbsp;a. In OGNI server perimetrale, nella Distribuzione guidata, accanto al **passaggio 3. Richiedere, installare o assegnare certificati**, fare clic **su Esegui di nuovo**.
    
&nbsp;&nbsp;&nbsp;b. Nella pagina **Attività certificati disponibili** fare clic su **Assegna un certificato esistente**.
    
&nbsp;&nbsp;&nbsp;c. Nella pagina **Assegnazione certificato** selezionare **Edge Server interno** nell'elenco.
    
&nbsp;&nbsp;&nbsp;d. Nella pagina **Archivio certificati** selezionare il certificato importato per il server perimetrale interno (dalla sezione precedente).
    
&nbsp;&nbsp;&nbsp;e. Nella pagina **Riepilogo assegnazione certificato** esaminare le impostazioni e quindi fare clic su **Avanti** per assegnare il certificato.
    
&nbsp;&nbsp;&nbsp;f. Nella pagina finale della procedura guidata fare clic su **Fine**.
    
&nbsp;&nbsp;&nbsp;g. Dopo aver completato questa procedura, è una buona idea aprire lo snap-in MMC Certificati in ogni server perimetrale, espandere **Certificati (computer locale),** espandere **Personale**, fare clic su Certificati e verificare che il certificato perimetrale interno sia elencato nel riquadro dei dettagli.
    
### <a name="external-edge-interface-certificates"></a>Certificati dell'interfaccia perimetrale esterna

 
### <a name="1-create-the-certificate-request"></a>1. Creare la richiesta di certificato

&nbsp;&nbsp;&nbsp;a. Accedere a uno dei server perimetrali, avviare la Distribuzione guidata e, nel passaggio **3: Richiesta,** installazione o assegnazione di certificati, fare clic su Esegui (o Esegui di **nuovo, se** è già stata eseguita questa procedura guidata).
    
&nbsp;&nbsp;&nbsp;b. Nella pagina **Attività certificato disponibili** fare clic su **Crea una nuova richiesta di certificato**.
    
&nbsp;&nbsp;&nbsp;c. Nella pagina **Richiesta di certificato** verificare che **l'opzione Certificato perimetrale** esterno sia selezionata e fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;d. Nella pagina **Richieste immediate o ritardate** fare clic su **Prepara la richiesta per l'invio posticipato**.
    
&nbsp;&nbsp;&nbsp;e. Nella pagina **File di richiesta** di certificato immetti la parte completa e il nome del file per il quale verrà salvato il file (ad esempio c:\SkypeInternalEdgeCert.cer). Scegliere **Avanti**.
    
&nbsp;&nbsp;&nbsp;f. Nella pagina **Specifica modello di certificato** alternativo, per utilizzare un modello diverso dal modello WebServer predefinito, selezionare la casella di controllo Usa modello di certificato alternativo per l'autorità di **certificazione** selezionata.
    
&nbsp;&nbsp;&nbsp;g. Nella pagina Impostazioni nome e sicurezza eseguire le operazioni seguenti:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i. In **Nome descrittivo** immettere un nome visualizzato per il certificato, ad esempio Edge esterno.
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  ii. In **Lunghezza in** bit scegli la lunghezza in bit (il valore predefinito è 2048, puoi andare più in alto ed essere più sicuro, ma le prestazioni rallentano).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iii. Se è necessario un certificato esportabile, è necessario selezionare la **casella di** controllo Contrassegna la chiave privata del certificato come esportabile.
    
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; iv. Scegliere **Avanti**.
    
&nbsp;&nbsp;&nbsp;h. Nella pagina **Informazioni organizzazione** immettere il nome dell'organizzazione e dell'unità organizzativa. È possibile immettere la divisione o il reparto ,ad esempio IT.
    
&nbsp;&nbsp;&nbsp;i. Nella pagina **Informazioni geografiche** immettere le informazioni sulla posizione.
    
&nbsp;&nbsp;&nbsp;j. Nella pagina **Nome soggetto/Nomi soggetto alternativi** le informazioni necessarie devono essere popolate automaticamente dalla procedura guidata.
    
&nbsp;&nbsp;&nbsp;k. Nella pagina **Impostazione dominio SIP nei nomi soggetto alternativi (SAN, Subject Alternate Names)** selezionare la casella di controllo dominio per aggiungere un sip.\<sipdomain> nell'elenco dei nomi alternativi soggetto.
    
&nbsp;&nbsp;&nbsp;l. Nella pagina **Configura nomi soggetto alternativi** aggiuntivi è necessario aggiungere eventuali nomi alternativi soggetto aggiuntivi necessari.
    
&nbsp;&nbsp;&nbsp;m. Nella pagina **Riepilogo richieste** esaminare le informazioni sul certificato che verranno utilizzate per generare la richiesta. Se è necessario apportare modifiche, tornare indietro e farlo ora.
    
&nbsp;&nbsp;&nbsp;n. Quando si è pronti, fare clic  su Avanti per generare il file CSR che sarà necessario fornire all'autorità di certificazione (è anche possibile  fare clic su Visualizza registro per esaminare il registro per la richiesta di certificato).
    
&nbsp;&nbsp;&nbsp;o. Dopo aver generato la richiesta, è possibile fare **clic su Visualizza** per esaminare il certificato e **su Fine** per chiudere la finestra. Il contenuto del file CSR deve essere assegnato all'autorità di certificazione, in modo che possa generare un certificato da importare nel computer nella sezione successiva.
    
&nbsp;&nbsp;&nbsp;p. (FACOLTATIVO) Quando invii il contenuto della csr, potresti richiedere alcune informazioni, come indicato di seguito (le CA variano notevolmente, quindi potrebbe non essere necessario):
    
  - **Microsoft** come piattaforma server
    
  - **IIS** come versione
    
  - **Server Web** come tipo di utilizzo
    
  - **PKCS7** come formato di risposta
    
 
### <a name="2-import-the-certificate"></a>2. Importare il certificato

&nbsp;&nbsp;&nbsp;a. Accedere, come membro del gruppo Administrators locale, al server perimetrale da cui è stata effettuata la richiesta di certificato nell'ultima procedura.
    
&nbsp;&nbsp;&nbsp;b. Nella Distribuzione guidata, accanto al **passaggio 3. Richiedere, installare o assegnare certificati**, fare clic **su Esegui di nuovo**.
    
&nbsp;&nbsp;&nbsp;c. Nella pagina **Attività certificati disponibili** fare clic su **Importa un certificato da un . File P7b, pfx o cer**.
    
&nbsp;&nbsp;&nbsp;d. Nella pagina **Importa** certificato digitare il percorso completo e il nome del file del certificato ottenuto nella sezione precedente oppure fare clic su Sfoglia per trovare e  scegliere il file in questo modo. Se il certificato contiene una chiave privata, assicurarsi di selezionare **File** di certificato contenente la chiave privata del certificato e immettere la password per la chiave privata. Fai **clic su Avanti** quando sei pronto.
    
&nbsp;&nbsp;&nbsp;e. Nella pagina **Importa riepilogo certificato** esaminare le informazioni di riepilogo e fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;f. Nella pagina **Esecuzione comandi in** esecuzione è possibile esaminare il risultato dell'importazione al termine dell'importazione facendo clic **su Visualizza registro**. Fare **clic su** Fine per completare l'importazione del certificato.
    
&nbsp;&nbsp;&nbsp;g. Se in un pool sono presenti altri server perimetrali, sarà necessario seguire anche le due procedure seguenti. Se si tratta di un server perimetrale autonomo, i certificati esterni sono stati evasi.
    
 
### <a name="3-export-the-certificate"></a>3. Esportare il certificato

&nbsp;&nbsp;&nbsp;a. Assicurati di aver effettuato l'accesso al server perimetrale in cui hai importato il certificato come amministratore locale.
    
&nbsp;&nbsp;&nbsp;b. Fare **clic sul pulsante Start****, scegliere** Esegui (o **aprire Ricerca**) e digitare **MMC**.
    
&nbsp;&nbsp;&nbsp;c. Nella console MMC fare clic su **File** e quindi su **Aggiungi/Rimuovi snap-in**.
    
&nbsp;&nbsp;&nbsp;d. Nella casella **Aggiungi o rimuovi snap-in fare** clic su **Certificati** e quindi su **Aggiungi**.
    
&nbsp;&nbsp;&nbsp;e. Nella finestra **di dialogo** Snap-in Certificati scegliere **Account computer**. Scegliere **Avanti**.
    
&nbsp;&nbsp;&nbsp;f. Nella finestra **di dialogo Seleziona computer** selezionare **Computer locale: (computer in cui è in esecuzione la console)**. Fare clic su **Fine**. Fare **clic su OK** e la configurazione della console MMC è stata completata.
    
&nbsp;&nbsp;&nbsp;g. Fare doppio clic su **Certificati (computer locale)** per espandere gli archivi certificati. **Fare doppio clic su Personale** e quindi su **Certificati**.
    
   > [!NOTE]
   > È possibile che l'utente sia presente e che non sia presente alcun certificato nell'archivio personale certificati per il computer locale. Non è necessario eseguire la ricerca, se la chiave non è presente, al certificato importato non è associata una chiave privata. Provare la richiesta e importare i passaggi precedenti una volta e, se si è certi di aver ottenuto tutto ciò che è giusto, contattare l'amministratore o il provider della CA. 
  
&nbsp;&nbsp;&nbsp;h. **Nell'archivio personale certificati** per il computer locale fare clic con il pulsante destro del mouse sul certificato che si sta esportando. **Selezionare Tutte le attività** dal menu risultante e quindi fare clic su **Esporta**.
    
&nbsp;&nbsp;&nbsp;i. Nell'**Esportazione guidata certificati** fare clic su **Avanti**. Selezionare **Sì, esporta la chiave privata**. Fare clic su **Avanti**.
    
   > [!NOTE]
   > Se **sì, l'esportazione della** chiave privata non è disponibile, la chiave privata per questo certificato non è stata contrassegnata per l'esportazione prima di averla. È necessario richiedere di nuovo il certificato al provider, con la chiave privata impostata per l'esportazione, prima di procedere correttamente.
  
&nbsp;&nbsp;&nbsp;j. Nella finestra di dialogo Esporta formati file selezionare Informazioni personali Exchange - PKCS#12 (. PFX) e quindi selezionare quanto segue:
    
 &nbsp;&nbsp;&nbsp;  i. Includere tutti i certificati nel percorso di certificazione, se possibile.
    
 &nbsp;&nbsp;&nbsp;  ii. Esportare tutte le proprietà estese.
    
   > [!NOTE]
   > **NON selezionare** MAI **Elimina la chiave privata se l'esportazione ha esito positivo**. Significa che devi reimportare il certificato e la chiave privata in questo server perimetrale.
  
&nbsp;&nbsp;&nbsp;k. Se si desidera assegnare una password per proteggere la chiave privata, è possibile digitare una password per la chiave privata. Immettere di nuovo la password per confermare e quindi fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;l. Digitare un percorso e un nome di file per il certificato esportato, utilizzando l'estensione **pfx**. Il percorso deve essere accessibile dagli altri server perimetrali del pool oppure è necessario spostare il file tramite supporti esterni ,ad esempio un'unità USB. Fare **clic** su Avanti dopo aver effettuato la scelta.
    
&nbsp;&nbsp;&nbsp;m. Esaminare il riepilogo nella finestra **di dialogo Completamento esportazione guidata** certificati e quindi fare clic su **Fine**.
    
&nbsp;&nbsp;&nbsp;n. Fare clic su **OK** nella finestra di dialogo di conclusione dell'esportazione.
    
&nbsp;&nbsp;&nbsp;o. È ora necessario tornare alla sezione Importare il certificato prima di questo e importare il certificato in tutti i server perimetrali rimanenti, quindi procedere con l'assegnazione, di seguito.
    
 
### <a name="4-assign-the-certificate"></a>4. Assegnare il certificato

&nbsp;&nbsp;&nbsp;a. In **OGNI** server perimetrale, nella Distribuzione guidata, accanto al **passaggio 3. Richiedere, installare o assegnare certificati**, fare clic **su Esegui di nuovo**.
    
&nbsp;&nbsp;&nbsp;b. Nella pagina **Attività certificati disponibili** fare clic su **Assegna un certificato esistente**.
    
&nbsp;&nbsp;&nbsp;c. Nella pagina **Assegnazione certificato** selezionare **Edge External** nell'elenco.
    
&nbsp;&nbsp;&nbsp;d. Nella pagina **Archivio certificati** selezionare il certificato importato per il server perimetrale esterno (dalla sezione precedente).
    
&nbsp;&nbsp;&nbsp;e. Nella pagina **Riepilogo assegnazione certificato** esaminare le impostazioni e quindi fare clic su **Avanti** per assegnare il certificato.
    
&nbsp;&nbsp;&nbsp;f. Nella pagina finale della procedura guidata fare clic su **Fine**.
    
&nbsp;&nbsp;&nbsp;g. Dopo aver completato questa procedura, è una buona idea aprire lo snap-in MMC Certificati in ogni server, espandere **Certificati (computer locale),** espandere **Personale**, fare clic su Certificati e verificare che il certificato perimetrale interno sia elencato nel riquadro dei dettagli.
    
   > [!NOTE]
   > Sarà inoltre necessario configurare i certificati per il server proxy inverso. 
  
## <a name="starting-the-edge-servers"></a>Avvio dei server perimetrali

Al termine dell'installazione, è necessario avviare i servizi in ogni server perimetrale della distribuzione:
  
1. In ogni server perimetrale, nella **Distribuzione guidata**, accanto a **Passaggio 4: Avviare i servizi**, fare clic su **Esegui**.
    
2. Nella pagina **Start Skype for Business Server Services** esaminare l'elenco dei servizi e quindi fare clic su **Avanti** per avviare i servizi.
    
3. Dopo aver avviato i servizi, è possibile fare clic **su Fine** per chiudere la procedura guidata.
    
4. (Facoltativo) Sempre in **Passaggio 4: Avviare i servizi**, fare clic su **Stato servizi**.
    
5.  In **MMC Servizi** in ogni server, verificare che tutti i servizi Skype for Business Server siano in esecuzione.
    

