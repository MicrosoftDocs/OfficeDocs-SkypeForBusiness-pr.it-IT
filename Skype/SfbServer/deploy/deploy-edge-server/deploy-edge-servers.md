---
title: Distribuire server perimetrali in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 63c7251c-080a-4175-99a6-f86d0266d6bc
description: "Riepilogo: informazioni su come distribuire server perimetrali nell'ambiente di Skype for Business Server."
ms.openlocfilehash: 8e23e157d4eb86f5b3d2bd5fa3ab3a54fd8aadc8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804376"
---
# <a name="deploy-edge-servers-in-skype-for-business-server"></a>Distribuire server perimetrali in Skype for Business Server
 
**Riepilogo:** Informazioni su come distribuire server perimetrali nell'ambiente di Skype for Business Server.
  
Le sezioni seguenti contengono passaggi che devono essere seguiti dopo la revisione della documentazione relativa al piano di Skype for Business Server [per le distribuzioni di server perimetrali in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) . I passaggi di distribuzione sono i seguenti:
  
- Interfacce di rete
    
- Installazione
    
- Certificati
    
- Avvio dei server perimetrali
    
## <a name="network-interfaces"></a>Interfacce di rete

Come indicato nella pianificazione, è necessario configurare l'interfaccia di rete con DNS nella rete perimetrale che ospita i server Edge o senza DNS nella rete perimetrale.
  
### <a name="interface-configuration-with-dns-servers-in-the-perimeter-network"></a>Configurazione dell'interfaccia con i server DNS nella rete perimetrale

1. Installare due schede di rete per ogni server perimetrale, uno per l'interfaccia interna e uno per l'interfaccia esterna.
    
    > [!NOTE]
    > Le subnet interna ed esterna non devono essere vicendevolmente instradabili. 
  
2. Nell'interfaccia esterna verrà configurata **una** delle opzioni seguenti:
    
   a. Tre indirizzi IP statici sulla subnet della rete perimetrale esterna e puntare il gateway predefinito all'interfaccia interna del firewall esterno. Configurare le impostazioni DNS della scheda in modo che puntino a una coppia di server DNS perimetrali.
    
   b. Un indirizzo IP statico sulla subnet della rete perimetrale esterna e puntare il gateway predefinito all'interfaccia interna del firewall esterno. Configurare le impostazioni DNS della scheda in modo che puntino a una coppia di server DNS perimetrali. Questa configurazione è accettabile solo se in precedenza è stata configurata la topologia in modo da avere valori non standard nelle assegnazioni delle porte, che sono descritte nell'articolo [creare la topologia perimetrale per Skype for Business Server](create-your-edge-topology.md) .
    
3. Nell'interfaccia interna, configurare un indirizzo IP statico nella subnet della rete perimetrale interna e non impostare un gateway predefinito. Configurare le impostazioni DNS dell'adattatore in modo che puntino ad almeno un server DNS, ma preferibilmente una coppia di server DNS perimetrali.
    
4. Creare route statiche persistenti nell'interfaccia interna a tutte le reti interne in cui risiedono client, Skype for Business Server e server di messaggistica unificata di Exchange.
    
### <a name="interface-configuration-without-dns-servers-in-the-perimeter-network"></a>Configurazione dell'interfaccia senza server DNS nella rete perimetrale

1. Installare due schede di rete per ogni server perimetrale, uno per l'interfaccia interna e uno per l'interfaccia esterna.
    
    > [!NOTE]
    > Le subnet interna ed esterna non devono essere vicendevolmente instradabili. 
  
2. Nell'interfaccia esterna verrà configurata **una** delle opzioni seguenti:
    
   a. Tre indirizzi IP statici sulla subnet della rete perimetrale esterna. È inoltre necessario configurare il gateway predefinito sull'interfaccia esterna, ad esempio la definizione del router con connessione Internet o del firewall esterno come gateway predefinito. Configurare le impostazioni DNS della scheda in modo che puntino a un server DNS esterno, idealmente una coppia di server DNS esterni.
    
   b. Un indirizzo IP statico sulla subnet della rete perimetrale esterna. È inoltre necessario configurare il gateway predefinito sull'interfaccia esterna, ad esempio la definizione del router con connessione Internet o del firewall esterno come gateway predefinito. Configurare le impostazioni DNS della scheda in modo che puntino a un server DNS esterno o idealmente una coppia di server DNS esterni. Questa configurazione è accettabile solo se in precedenza è stata configurata la topologia in modo da avere valori non standard nelle assegnazioni delle porte, che sono descritte nell'articolo [creare la topologia perimetrale per Skype for Business Server](create-your-edge-topology.md) .
    
3. Nell'interfaccia interna, configurare un indirizzo IP statico nella subnet della rete perimetrale interna e non impostare un gateway predefinito. Lasciare anche le impostazioni DNS dell'adapter vuote.
    
4. Creare route statiche persistenti nell'interfaccia interna a tutte le reti interne in cui risiedono client, Skype for Business Server e server di messaggistica unificata di Exchange.
    
5. Modificare il file HOST in ogni server perimetrale in modo che contenga un record per il server hop successivo o l'indirizzo IP virtuale (VIP). Questo record sarà il server Director, Standard Edition o il pool Front end configurato come indirizzo dell'hop successivo del server perimetrale in Generatore di topologie. Se si utilizza il bilanciamento del carico DNS, includere una riga per ogni membro del pool di hop successivo.
    
## <a name="installation"></a>Installazione

Per eseguire correttamente questa procedura, è necessario eseguire la procedura descritta nell'articolo [creare la topologia perimetrale per Skype for Business Server](create-your-edge-topology.md) .
  
1. Accedere al server in cui è stata configurata per il ruolo del server perimetrale con un account che si trova nel gruppo dell'amministratore locale.
    
2. È necessario il file di configurazione della topologia copiato alla fine della documentazione relativa alla topologia del server perimetrale in questo computer. Accedere al supporto esterno a cui è stato applicato il file di configurazione (come un'unità USB o una condivisione).
    
3. Avviare la **distribuzione guidata**.
    
4. Dopo l'apertura della procedura guidata, fare clic su **Installa o aggiorna il sistema di Skype for Business Server**.
    
5. Verrà eseguita la procedura guidata per controllare se è già installato qualcosa. Poiché questa è la prima volta che si esegue la procedura guidata, è necessario iniziare dal **passaggio 1. Installare l'archivio di configurazione locale.**
    
6. Verrà visualizzata la finestra **di dialogo Configura la replica locale dell'archivio di gestione centrale** . È necessario fare clic su **Importa da un file (consigliato per i server perimetrali)**.
    
7. Da qui, passare al percorso della topologia esportata in precedenza, selezionare il file con estensione zip, fare clic su **Apri** e quindi fare clic su **Avanti**.
    
8. La distribuzione guidata leggerà il file di configurazione e scriverà il file di configurazione XML nel computer locale.
    
9. Al termine del processo **Esecuzione comandi in corso**, fare clic su **Fine**.
    
10. Nella distribuzione guidata fare clic su **passaggio 2. Installare o rimuovere componenti di Skype for Business Server**. La procedura guidata installerà quindi i componenti perimetrali di Skype for Business Server specificati nel file di configurazione XML archiviato nel computer locale.
    
11. Una volta completata l'installazione, è possibile passare alla procedura descritta nella sezione **Certificates** seguente.
    
## <a name="certificates"></a>Certificati

I requisiti dei certificati per il server perimetrale sono disponibili nella documentazione relativa alla pianificazione dei certificati perimetrali. I passaggi per la configurazione dei certificati sono riportati di seguito.
  
> [!NOTE]
> Quando si esegue la configurazione guidata certificati, è necessario essere connessi come account con le autorizzazioni corrette per il tipo di modello di certificato che si intende utilizzare. Per impostazione predefinita, una richiesta di certificato di Skype for Business Server utilizzerà il modello di certificato del server Web. Se si è connessi con un account membro del gruppo RTCUniversalServerAdmins per richiedere un certificato tramite questo modello, verificare che al gruppo siano state assegnate le autorizzazioni di registrazione per l'utilizzo di tale modello. 
  
### <a name="internal-edge-interface-certificates"></a>Certificati dell'interfaccia perimetrale interna

 
### <a name="1-download-or-export-the-ca-certification-chain"></a>1. scaricare o esportare la catena di certificazione CA

 
#### <a name="nbspnbspnbsp-a-download-using-certsrv-web-site"></a>&nbsp;&nbsp;&nbsp; un. Scaricare tramite il sito Web di certsrv

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i. Accedere a un server Skype for business nella rete interna come membro del gruppo Administrators locale.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Aprire **Start** ed **eseguire** (o **cercare** ed **eseguire** ) e quindi digitare quanto segue:
    
  ```console
  https://<NAME OF YOUR ISSUING CA SERVER>/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Per esempio:
    
  ```console
  https://ca01/contoso.com/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;III. Nella pagina Web certsrv della CA emittente, in **selezionare un'attività**, fare clic su **Scarica un certificato CA, la catena di certificati o un CRL**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IV. In **Scarica un certificato CA, una catena di certificati o un CRL** fare clic su **Scarica catena di certificati CA**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v. Nella casella **Download file** fare clic su **Salva**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi. Salvare il file. p7b nell'unità disco rigido del server e quindi copiarlo in una cartella in ognuno dei server perimetrali.
    
### <a name="nbspnbspnbspb-export-using-mmc"></a>&nbsp;&nbsp;&nbsp;b. Esporta tramite MMC

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i. È possibile esportare il certificato radice della CA da qualsiasi computer aggiunto al dominio utilizzando MMC. Andare a **avviare** ed **eseguire** o aprire la **ricerca** e digitare **MMC** per aprirlo.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Nella console MMC, fare clic su **file**, quindi fare clic su **Aggiungi/Rimuovi snap-in**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;III. Nell'elenco **Aggiungi o Rimuovi snap-** in, scegliere **certificati** e quindi fare clic su **Aggiungi**. Quando richiesto, selezionare **account computer** e quindi fare clic su **Avanti**. Nella finestra di dialogo **Selezione computer** selezionare **Computer locale**. Fare clic su **fine** e quindi su **OK**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IV. Espandere **certificati (computer locale)**. Espandere **Autorità di certificazione radice attendibili**. Selezionare **certificati**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v. Fare clic sul certificato radice emesso dalla CA. Fare clic con il pulsante destro del mouse sul certificato, scegliere **tutte le attività** dal menu e quindi selezionare **Esporta**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi. Verrà visualizzata la **procedura guidata di esportazione dei certificati** . Fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VII. Nella finestra di dialogo **formato file di esportazione** scegliere il formato in cui si desidera eseguire l'esportazione. La nostra raccomandazione è la **sintassi dei messaggi di crittografia standard-PKCS #7 Certificates (P7b)**. Se questa è la scelta migliore, ricordarsi di selezionare anche la casella di controllo **Includi tutti i certificati nel percorso di certificazione, se possibile, in** quanto esporterà anche la catena di certificati, incluso il certificato della CA radice e tutti i certificati intermedi. Fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VIII. Nella finestra **di dialogo file da esportare** Digitare il percorso e il nome del file (l'estensione predefinita è p7b) per il certificato esportato nella voce nome file. Se è più semplice, scegliere il pulsante **Sfoglia** per passare al percorso in cui si desidera salvare il certificato esportato e denominare il certificato esportato. Fare clic su **Salva** e quindi su **Avanti** quando si è pronti.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IX. Esaminare il riepilogo delle azioni e fare clic su **fine** per completare l'esportazione del certificato. Fare clic su **OK** per confermare l'avvenuta esecuzione dell'esportazione.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;x. Copiare il file con estensione p7b in ognuno dei server perimetrali.
    
### <a name="2-import-the-ca-certification-chain"></a>2. importare la catena di certificazione CA

&nbsp;&nbsp;&nbsp;un. In ogni server perimetrale, aprire MMC (fare clic su **Avvia** ed **Esegui** oppure su **Cerca** e digitare **MMC** per aprire).
    
&nbsp;&nbsp;&nbsp;b. Scegliere **Aggiungi/Rimuovi snap-in** dal menu **file** e quindi fare clic su **Aggiungi**.
    
&nbsp;&nbsp;&nbsp;c. Nella casella **Aggiungi o Rimuovi snap-** in fare clic su **certificati** e quindi su **Aggiungi**.
    
&nbsp;&nbsp;&nbsp;d. Nella finestra di dialogo **Snap-in certificati** fare clic su **Account del computer** e quindi su **Avanti**.
    
&nbsp;&nbsp;&nbsp;e. Nella finestra di dialogo **Seleziona computer** verificare che sia selezionata la casella di controllo computer **locale (il computer su cui è in esecuzione questa console)** e quindi fare clic su **fine**.
    
&nbsp;&nbsp;&nbsp;f. Fare clic su **Chiudi** e quindi su **OK**.
    
&nbsp;&nbsp;&nbsp;g. Nell'albero della console espandere **certificati (computer locale)**, fare clic con il pulsante destro del mouse su **autorità di certificazione radice attendibili**, accedere a **tutte le attività** e quindi fare clic su **Importa**.
    
&nbsp;&nbsp;&nbsp;h. Nella procedura guidata visualizzata, nel **file per importare** TextBox, specificare il nome del file del certificato (il nome assegnato al file. p7b nella sezione precedente). Fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;i. Lasciare il pulsante di opzione sul **posto tutti i certificati nel seguente archivio, come dovrebbero essere selezionate le autorità di certificazione radice attendibili** . Fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;j. Esaminare il riepilogo e fare clic su **fine** per completare l'importazione.
    
&nbsp;&nbsp;&nbsp;k. Sarà necessario eseguire questa operazione per ogni server perimetrale che si sta distribuendo.
    
### <a name="3-create-the-certificate-request"></a>3. creare la richiesta di certificato

&nbsp;&nbsp;&nbsp;un. Accedere a uno dei server perimetrali, avviare la distribuzione guidata e al **passaggio 3: richiedere, installare o assegnare certificati**, fare clic su **Esegui** (o **Esegui di nuovo**, se è già stata eseguita la procedura guidata).
    
&nbsp;&nbsp;&nbsp;b. Nella pagina **richiesta di certificato** verificare che sia selezionata l'opzione **certificato perimetrale interno** e fare clic su **Richiedi**.
    
&nbsp;&nbsp;&nbsp;c. Nella pagina **richieste immediate o ritardate** fare clic su **Invia immediatamente la richiesta a un'autorità di certificazione online** se si ha accesso a un utente dall'ambiente perimetrale oppure se si **prepara la richiesta in un secondo momento, ma** in caso contrario.
    
&nbsp;&nbsp;&nbsp;d. Nella pagina **file richiesta di certificato** , immettere la parte completa e il nome del file in cui verrà salvato il file (ad esempio c:\SkypeInternalEdgeCert.cer). Fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;e. Nella pagina **Specifica modello di certificato alternativo** , per utilizzare un modello diverso da quello predefinito del modello webserver, selezionare la casella di controllo **utilizza modello di certificato alternativo per l'autorità di certificazione selezionata** . In caso contrario, non eseguire alcuna operazione.
    
&nbsp;&nbsp;&nbsp;f. Nella pagina Impostazioni nome e sicurezza eseguire le operazioni seguenti:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i. In **nome descrittivo**, immettere un nome visualizzato per il certificato, ad esempio perimetro interno.
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  II. In **lunghezza bit**, scegliere la lunghezza del bit (il valore predefinito è 2048, è possibile andare più in alto ed essere più sicuro, ma renderà le prestazioni rallentate).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  III. Se è necessario un certificato esportabile, è necessario controllare la casella **di controllo Contrassegna come esportabile la chiave privata del certificato** .
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  IV. Fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;g. Nella pagina **informazioni sull'organizzazione** , immettere il nome per l'organizzazione e l'unità organizzativa (OU). È possibile immettere la divisione o il reparto (ad esempio,).
    
&nbsp;&nbsp;&nbsp;h. Nella pagina **informazioni geografiche** , immettere le informazioni sulla posizione.
    
&nbsp;&nbsp;&nbsp;i. Nella pagina **nome soggetto/nomi soggetto alternativi** questo dovrebbe essere popolato automaticamente dalla procedura guidata.
    
&nbsp;&nbsp;&nbsp;j. Nella pagina **Configura nomi soggetto** alternativi aggiuntivi è necessario aggiungere eventuali nomi alternativi del soggetto aggiuntivi necessari.
    
&nbsp;&nbsp;&nbsp;k. Nella pagina **Riepilogo richieste** esaminare le informazioni sul certificato che verranno utilizzate per generare la richiesta. Se è necessario apportare modifiche, tornare indietro e farlo ora.
    
&nbsp;&nbsp;&nbsp;l. Quindi fare clic su **Avanti** per generare il file CSR che sarà necessario fornire all'autorità di certificazione (è anche possibile fare clic su **Visualizza registro** per esaminare il log per la richiesta di certificato).
    
&nbsp;&nbsp;&nbsp;m. Una volta che la richiesta è stata generata, è possibile fare clic su **Visualizza** per esaminare il certificato e **terminare** per chiudere la finestra. I contenuti del file CSR devono essere assegnati alla CA, in modo che possano generare un certificato da importare nel computer nella sezione successiva.
    

### <a name="4-import-the-certificate"></a>4. importare il certificato

&nbsp;&nbsp;&nbsp;un. Accedere, come membro del gruppo Administrators locale, al server perimetrale in cui è stata effettuata la richiesta di certificato nell'ultima procedura.
    
&nbsp;&nbsp;&nbsp;b. Nella distribuzione guidata, accanto a **passaggio 3. Richiedere, installare o assegnare certificati**, fare clic su **Riesegui**.
    
&nbsp;&nbsp;&nbsp;c. Nella pagina **attività certificati disponibili** fare clic su **Importa un certificato da a. P7b, file con estensione pfx o CER**.
    
&nbsp;&nbsp;&nbsp;d. Nella pagina **import certificate** Digitare il percorso completo e il nome di file del certificato ottenuto nella sezione precedente (oppure fare clic su **Sfoglia** per individuare e scegliere il file in questo modo).
    
&nbsp;&nbsp;&nbsp;e. Se si importano i certificati per gli altri membri del pool di server perimetrali e il certificato contiene una chiave privata, assicurarsi di selezionare la casella di controllo file del certificato contenente la **chiave privata del certificato** e specificare la password. Fare clic su **Avanti** per continuare.
    
&nbsp;&nbsp;&nbsp;f. Nella pagina **Riepilogo** , fare clic su **Avanti** dopo aver confermato le informazioni e **terminare** una volta che il certificato è stato importato correttamente.
    
 
### <a name="5-export-the-certificate"></a>5. esportare il certificato

&nbsp;&nbsp;&nbsp;un. Assicurarsi di aver eseguito l'accesso al server perimetrale in cui è stato importato il certificato in precedenza, come membro del gruppo Administrators locale.
    
&nbsp;&nbsp;&nbsp;b. Fare clic sul pulsante **Start**, scegliere **Esegui** (o Apri **ricerca** ) e quindi digitare **MMC**.
    
&nbsp;&nbsp;&nbsp;c. Dalla console MMC, fare clic su **file**, quindi fare clic su **Aggiungi/Rimuovi snap-in**.
    
&nbsp;&nbsp;&nbsp;d. Nella casella **Aggiungi o Rimuovi snap-** in fare clic su **certificati** e quindi su **Aggiungi**.
    
&nbsp;&nbsp;&nbsp;e. Nella finestra di dialogo snap-in **certificati** scegliere **account computer**. Fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;f. Nella finestra di dialogo **Seleziona computer** selezionare **computer locale: (il computer in cui è in esecuzione questa console)**. Fare clic su **Fine**. Fare clic su **OK** e la configurazione della console MMC è stata completata.
    
&nbsp;&nbsp;&nbsp;g. Fare doppio clic su **Certificati (computer locale)** per espandere gli archivi certificati. Fare doppio clic su **personale** e quindi su **certificati**.
    
  > [!NOTE]
  > È possibile che tu sia presente e che non vengano visualizzati certificati nell'archivio personale dei certificati del computer locale. Non è necessario eseguire la ricerca, se la chiave non è presente, il certificato importato non dispone di una chiave privata associata. Provare a eseguire la richiesta e importare i passaggi precedenti e, se si è sicuri di aver ottenuto tutto questo diritto, rivolgersi all'amministratore o al provider CA. 
  
&nbsp;&nbsp;&nbsp;h. Nell' **archivio personale certificati** del computer locale fare clic con il pulsante destro del mouse sul certificato che si sta esportando. Selezionare **tutte le attività** dal menu risultante, quindi fare clic su **Esporta**.
    
&nbsp;&nbsp;&nbsp;i. Nell'**Esportazione guidata certificati** fare clic su **Avanti**. Selezionare **Sì, esporta la chiave privata**. Fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;j. Nella finestra di dialogo **formati file di esportazione** selezionare **scambio di informazioni personali-PKCS # 12 (. PFX)** e quindi selezionare le opzioni seguenti:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i. Includere tutti i certificati nel percorso di certificazione, se possibile.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   II. Esporta tutte le proprietà estese.
    
   > [!NOTE]
   > **Non selezionare mai** **Elimina la chiave privata se l'esportazione ha esito positivo**. Significa che è necessario reimportare nuovamente il certificato e la chiave privata su questo server perimetrale.
  
&nbsp;&nbsp;&nbsp;k. Se si desidera assegnare una password per proteggere la chiave privata, è possibile digitare una password per la chiave privata. Immettere di nuovo la password per confermare e quindi fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;l. Digitare un percorso e un nome di file per il certificato esportato, utilizzando un'estensione di file **PFX**. Il percorso deve essere accessibile dagli altri server perimetrali nel pool oppure è necessario spostare il file tramite un supporto esterno, ad esempio un'unità USB. Fare clic su **Avanti** quando si è scelto.
    
&nbsp;&nbsp;&nbsp;m. Esaminare il riepilogo nella finestra di dialogo **completamento esportazione guidata certificati** e quindi fare clic su **fine**.
    
&nbsp;&nbsp;&nbsp;n. Fare clic su **OK** nella finestra di dialogo di conclusione dell'esportazione.
    
 
### <a name="6-assign-the-certificate"></a>6. assegnare il certificato

&nbsp;&nbsp;&nbsp;un. In ogni server perimetrale, nella distribuzione guidata, accanto a **passaggio 3. Richiedere, installare o assegnare certificati**, fare clic su **Riesegui**.
    
&nbsp;&nbsp;&nbsp;b. Nella pagina **attività certificati disponibili** fare clic su **assegna un certificato esistente**.
    
&nbsp;&nbsp;&nbsp;c. Nella pagina **Assegnazione certificato** selezionare **Edge Server interno** nell'elenco.
    
&nbsp;&nbsp;&nbsp;d. Nella pagina **archivio certificati** selezionare il certificato importato per il server perimetrale interno (dalla sezione precedente).
    
&nbsp;&nbsp;&nbsp;e. Nella pagina **Riepilogo assegnazione certificato** , esaminare le impostazioni, quindi fare clic su **Avanti** per assegnare il certificato.
    
&nbsp;&nbsp;&nbsp;f. Nella pagina finale della procedura guidata fare clic su **Fine**.
    
&nbsp;&nbsp;&nbsp;g. Dopo aver completato questa procedura, è consigliabile aprire lo snap-in MMC certificati in ogni server perimetrale, espandere **certificati (computer locale)**, espandere **personale**, fare clic su **certificati** e verificare che il certificato perimetrale interno sia elencato nel riquadro dei dettagli.
    
### <a name="external-edge-interface-certificates"></a>Certificati dell'interfaccia perimetrale esterna

 
### <a name="1-create-the-certificate-request"></a>1. creare la richiesta di certificato

&nbsp;&nbsp;&nbsp;un. Accedere a uno dei server perimetrali, avviare la distribuzione guidata e al **passaggio 3: richiedere, installare o assegnare certificati, fare clic su Esegui** (o **Esegui di nuovo**, se è già stata eseguita la procedura guidata).
    
&nbsp;&nbsp;&nbsp;b. Nella pagina **Attività certificato disponibili** fare clic su **Crea una nuova richiesta di certificato**.
    
&nbsp;&nbsp;&nbsp;c. Nella pagina **richiesta di certificato** verificare che sia selezionata l'opzione **certificato perimetrale esterno** e quindi fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;d. Nella pagina **Richieste immediate o ritardate** fare clic su **Prepara la richiesta per l'invio posticipato**.
    
&nbsp;&nbsp;&nbsp;e. Nella pagina **file richiesta di certificato** , immettere la parte completa e il nome del file in cui verrà salvato il file (ad esempio c:\SkypeInternalEdgeCert.cer). Fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;f. Nella pagina **Specifica modello di certificato alternativo** , per utilizzare un modello diverso da quello predefinito del modello webserver, selezionare la casella di controllo **utilizza modello di certificato alternativo per l'autorità di certificazione selezionata** .
    
&nbsp;&nbsp;&nbsp;g. Nella pagina Impostazioni nome e sicurezza eseguire le operazioni seguenti:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i. In **nome descrittivo**, immettere un nome visualizzato per il certificato, ad esempio perimetro esterno.
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  II. In **lunghezza bit**, scegliere la lunghezza del bit (il valore predefinito è 2048, è possibile andare più in alto ed essere più sicuro, ma renderà le prestazioni rallentate).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  III. Se è necessario un certificato esportabile, è necessario controllare la casella **di controllo Contrassegna come esportabile la chiave privata del certificato** .
    
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; IV. Fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;h. Nella pagina **informazioni sull'organizzazione** , immettere il nome per l'organizzazione e l'unità organizzativa (OU). È possibile immettere la divisione o il reparto (ad esempio,).
    
&nbsp;&nbsp;&nbsp;i. Nella pagina **informazioni geografiche** , immettere le informazioni sulla posizione.
    
&nbsp;&nbsp;&nbsp;j. Nella pagina **nome soggetto/nomi soggetto alternativi** le informazioni necessarie devono essere popolate automaticamente dalla procedura guidata.
    
&nbsp;&nbsp;&nbsp;k. Nella pagina **impostazione del dominio SIP su nomi soggetto alternativi (San)** selezionare la casella di controllo Domain per aggiungere un SIP.<sipdomain> voce all'elenco dei nomi alternativi del soggetto.
    
&nbsp;&nbsp;&nbsp;l. Nella pagina **Configura nomi soggetto** alternativi aggiuntivi è necessario aggiungere eventuali nomi alternativi del soggetto aggiuntivi necessari.
    
&nbsp;&nbsp;&nbsp;m. Nella pagina **Riepilogo richieste** esaminare le informazioni sul certificato che verranno utilizzate per generare la richiesta. Se è necessario apportare modifiche, tornare indietro e farlo ora.
    
&nbsp;&nbsp;&nbsp;n. Quando si è pronti, fare clic su **Avanti** per generare il file CSR che sarà necessario fornire all'autorità di certificazione (è anche possibile fare clic su **Visualizza registro** per esaminare il log per la richiesta di certificato).
    
&nbsp;&nbsp;&nbsp;o. Una volta che la richiesta è stata generata, è possibile fare clic su **Visualizza** per esaminare il certificato e **terminare** per chiudere la finestra. I contenuti del file CSR devono essere assegnati alla CA, in modo che possano generare un certificato da importare nel computer nella sezione successiva.
    
&nbsp;&nbsp;&nbsp;p. OPTIONAL Quando si inviano i contenuti della RSI, è possibile richiedere alcune informazioni, come indicato di seguito (le CA variano notevolmente, pertanto potrebbe non essere necessario):
    
  - **Microsoft** come piattaforma server
    
  - **IIS** come versione
    
  - **Server Web** come tipo di utilizzo
    
  - **PKCS7** come formato di risposta
    
 
### <a name="2-import-the-certificate"></a>2. importare il certificato

&nbsp;&nbsp;&nbsp;un. Accedere, come membro del gruppo Administrators locale, al server perimetrale in cui è stata effettuata la richiesta di certificato nell'ultima procedura.
    
&nbsp;&nbsp;&nbsp;b. Nella distribuzione guidata, accanto a **passaggio 3. Richiedere, installare o assegnare certificati**, fare clic su **Riesegui**.
    
&nbsp;&nbsp;&nbsp;c. Nella pagina **attività certificati disponibili** fare clic su **Importa un certificato da a. P7b, file con estensione pfx o CER**.
    
&nbsp;&nbsp;&nbsp;d. Nella pagina **import certificate** Digitare il percorso completo e il nome di file del certificato ottenuto nella sezione precedente (oppure fare clic su **Sfoglia** per individuare e scegliere il file in questo modo). Se il certificato contiene una chiave privata, selezionare il file del certificato **contiene la chiave privata del certificato** e immettere la password per la chiave privata. Quando pronto, fare clic su **Avanti** .
    
&nbsp;&nbsp;&nbsp;e. Nella pagina **Importa Riepilogo del certificato** , esaminare le informazioni di riepilogo e fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;f. Nella pagina **esecuzione dei comandi** è possibile esaminare il risultato dell'importazione al termine del completamento facendo clic su **Visualizza registro**. Fare clic su **fine** per completare l'importazione del certificato.
    
&nbsp;&nbsp;&nbsp;g. Se si dispone di altri server perimetrali in un pool, è necessario seguire anche le due procedure successive. Se si tratta di un server perimetrale autonomo, è necessario eseguire i certificati esterni.
    
 
### <a name="3-export-the-certificate"></a>3. esportare il certificato

&nbsp;&nbsp;&nbsp;un. Assicurarsi di aver eseguito l'accesso al server perimetrale in cui è stato importato il certificato come amministratore locale.
    
&nbsp;&nbsp;&nbsp;b. Fare clic sul pulsante **Start**, scegliere **Esegui** (o Apri **ricerca** ) e quindi digitare **MMC**.
    
&nbsp;&nbsp;&nbsp;c. Dalla console MMC, fare clic su **file**, quindi fare clic su **Aggiungi/Rimuovi snap-in**.
    
&nbsp;&nbsp;&nbsp;d. Nella casella **Aggiungi o Rimuovi snap-** in fare clic su **certificati** e quindi su **Aggiungi**.
    
&nbsp;&nbsp;&nbsp;e. Nella finestra di dialogo snap-in **certificati** scegliere **account computer**. Fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;f. Nella finestra di dialogo **Seleziona computer** selezionare **computer locale: (il computer in cui è in esecuzione questa console)**. Fare clic su **Fine**. Fare clic su **OK** e la configurazione della console MMC è stata completata.
    
&nbsp;&nbsp;&nbsp;g. Fare doppio clic su **Certificati (computer locale)** per espandere gli archivi certificati. Fare **doppio clic su personale** e quindi su **certificati**.
    
   > [!NOTE]
   > È possibile che tu sia presente e che non vengano visualizzati certificati nell'archivio personale dei certificati del computer locale. Non è necessario eseguire la ricerca, se la chiave non è presente, il certificato importato non dispone di una chiave privata associata. Provare a eseguire la richiesta e importare i passaggi precedenti e, se si è sicuri di aver ottenuto tutto questo diritto, rivolgersi all'amministratore o al provider CA. 
  
&nbsp;&nbsp;&nbsp;h. Nell' **archivio personale certificati** del computer locale fare clic con il pulsante destro del mouse sul certificato che si sta esportando. **Selezionare tutte le attività** dal menu risultante, quindi fare clic su **Esporta**.
    
&nbsp;&nbsp;&nbsp;i. Nell'**Esportazione guidata certificati** fare clic su **Avanti**. Selezionare **Sì, esporta la chiave privata**. Fare clic su **Avanti**.
    
   > [!NOTE]
   > Se **Sì, esportare la chiave privata** non è disponibile, la chiave privata per il certificato non è stata contrassegnata per l'esportazione prima di ottenerla. È necessario richiedere di nuovo il certificato dal provider, con la chiave privata impostata su Export, prima di procedere correttamente.
  
&nbsp;&nbsp;&nbsp;j. Nella finestra di dialogo formati file di esportazione selezionare scambio di informazioni personali-PKCS # 12 (. PFX) e quindi selezionare le opzioni seguenti:
    
 &nbsp;&nbsp;&nbsp;  i. Includere tutti i certificati nel percorso di certificazione, se possibile.
    
 &nbsp;&nbsp;&nbsp;  II. Esporta tutte le proprietà estese.
    
   > [!NOTE]
   > **Non selezionare mai** **Elimina la chiave privata se l'esportazione ha esito positivo**. Significa che è necessario reimportare nuovamente il certificato e la chiave privata su questo server perimetrale.
  
&nbsp;&nbsp;&nbsp;k. Se si desidera assegnare una password per proteggere la chiave privata, è possibile digitare una password per la chiave privata. Immettere di nuovo la password per confermare e quindi fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;l. Digitare un percorso e un nome di file per il certificato esportato, utilizzando un'estensione di file **PFX**. Il percorso deve essere accessibile dagli altri server perimetrali nel pool oppure è necessario spostare il file tramite un supporto esterno, ad esempio un'unità USB. Fare clic su **Avanti** quando si è scelto.
    
&nbsp;&nbsp;&nbsp;m. Esaminare il riepilogo nella finestra di dialogo **completamento esportazione guidata certificati** e quindi fare clic su **fine**.
    
&nbsp;&nbsp;&nbsp;n. Fare clic su **OK** nella finestra di dialogo di conclusione dell'esportazione.
    
&nbsp;&nbsp;&nbsp;o. È ora necessario tornare alla sezione Import the certificate prima di questo e importare il certificato in tutti i server perimetrali rimanenti, quindi procedere con l'assegnazione, in basso.
    
 
### <a name="4-assign-the-certificate"></a>4. assegnare il certificato

&nbsp;&nbsp;&nbsp;un. In **ogni** server perimetrale, nella distribuzione guidata, accanto a **passaggio 3. Richiedere, installare o assegnare certificati**, fare clic su **Riesegui**.
    
&nbsp;&nbsp;&nbsp;b. Nella pagina **attività certificati disponibili** fare clic su **assegna un certificato esistente**.
    
&nbsp;&nbsp;&nbsp;c. Nella pagina **assegnazione certificato** selezionare **perimetro esterno** nell'elenco.
    
&nbsp;&nbsp;&nbsp;d. Nella pagina **archivio certificati** selezionare il certificato importato per il perimetro esterno (dalla sezione precedente).
    
&nbsp;&nbsp;&nbsp;e. Nella pagina **Riepilogo assegnazione certificato** , esaminare le impostazioni, quindi fare clic su **Avanti** per assegnare il certificato.
    
&nbsp;&nbsp;&nbsp;f. Nella pagina finale della procedura guidata fare clic su **Fine**.
    
&nbsp;&nbsp;&nbsp;g. Dopo aver completato questa procedura, è consigliabile aprire lo snap-in MMC certificati in ogni server, espandere **certificati (computer locale)**, espandere **personale**, fare clic su **certificati** e verificare che il certificato perimetrale interno sia elencato nel riquadro dei dettagli.
    
   > [!NOTE]
   > Sarà inoltre necessario configurare i certificati per il server proxy inverso. 
  
## <a name="starting-the-edge-servers"></a>Avvio dei server perimetrali

Dopo aver completato la configurazione, è necessario avviare i servizi in ogni server perimetrale della distribuzione:
  
1. In ogni server perimetrale, nella **distribuzione guidata**, accanto a **passaggio 4: Avvia servizi**, fare clic su **Esegui**.
    
2. Nella pagina **Avvia i servizi di Skype for Business Server** , esaminare l'elenco dei servizi e quindi fare clic su **Avanti** per avviare i servizi.
    
3. Dopo l'avvio dei servizi, è possibile fare clic su **fine** per chiudere la procedura guidata.
    
4. Optional Ancora in **passaggio 4: avviare i servizi**, fare clic su **stato Servizi**.
    
5.  Nella **console MMC Servizi** su ogni server, verificare che tutti i servizi di Skype for Business Server siano in esecuzione.
    

