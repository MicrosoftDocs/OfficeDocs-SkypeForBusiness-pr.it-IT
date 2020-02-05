---
title: Distribuire Edge Server in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: "Riepilogo: informazioni su come distribuire Edge Server nell'ambiente di Skype for Business Server."
ms.openlocfilehash: 5411c2934191aba1f4efb8eabf5e909c8cad710e
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768309"
---
# <a name="deploy-edge-servers-in-skype-for-business-server"></a>Distribuire Edge Server in Skype for Business Server
 
**Riepilogo:** Informazioni su come distribuire Edge Server nell'ambiente di Skype for Business Server.
  
Le sezioni seguenti contengono passaggi che devono essere seguiti dopo che il piano Skype for Business Server [per le distribuzioni di Edge Server nella documentazione di Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) è stato esaminato. I passaggi di distribuzione sono i seguenti:
  
- Interfacce di rete
    
- Installazione
    
- Certificati
    
- Avvio di Edge Server
    
## <a name="network-interfaces"></a>Interfacce di rete

Come indicato nella pianificazione, sarà necessario configurare l'interfaccia di rete con il DNS nella rete perimetrale che ospita gli Edge Server o senza DNS nella rete perimetrale.
  
### <a name="interface-configuration-with-dns-servers-in-the-perimeter-network"></a>Configurazione dell'interfaccia con i server DNS nella rete perimetrale

1. Installare due schede di rete per ogni Edge Server, uno per l'interfaccia con rivestimento interno e uno per l'interfaccia esterna.
    
    > [!NOTE]
    > Le subnet interne ed esterne non devono essere instradate tra loro. 
  
2. Nell'interfaccia esterna verrà configurata **una** delle opzioni seguenti:
    
   un. Tre indirizzi IP statici nella subnet della rete perimetrale esterna e puntare il gateway predefinito all'interfaccia interna del firewall esterno. Configurare le impostazioni DNS della scheda in maniera che puntino a una coppia di server DNS perimetrali.
    
   b. Un indirizzo IP statico nella subnet della rete perimetrale esterna e puntare il gateway predefinito all'interfaccia interna del firewall esterno. Configurare le impostazioni DNS della scheda in maniera che puntino a una coppia di server DNS perimetrali. Questa configurazione è accettabile solo se in precedenza è stata configurata la topologia per avere valori non standard nelle assegnazioni di porta, che è illustrata nella [topologia create your Edge per Skype for Business Server](create-your-edge-topology.md) .
    
3. Nell'interfaccia interna configurare un IP statico nella subnet della rete perimetrale interna e non impostare un gateway predefinito. Configurare le impostazioni DNS per l'adattatore in maniera che puntino ad almeno un server DNS, ma preferibilmente una coppia di server DNS perimetrali.
    
4. Creare route statiche permanenti sull'interfaccia interna a tutte le reti interne in cui si trovano i server client, Skype for Business Server e messaggistica UNIFICAta di Exchange.
    
### <a name="interface-configuration-without-dns-servers-in-the-perimeter-network"></a>Configurazione dell'interfaccia senza server DNS nella rete perimetrale

1. Installare due schede di rete per ogni Edge Server, uno per l'interfaccia con rivestimento interno e uno per l'interfaccia esterna.
    
    > [!NOTE]
    > Le subnet interne ed esterne non devono essere instradate tra loro. 
  
2. Nell'interfaccia esterna verrà configurata **una** delle opzioni seguenti:
    
   un. Tre indirizzi IP statici nella subnet della rete perimetrale esterna. Dovrai anche configurare il gateway predefinito nell'interfaccia esterna, ad esempio definendo il router che si affaccia su Internet o il firewall esterno come gateway predefinito. Configurare le impostazioni DNS della scheda in modo che puntino a un server DNS esterno, idealmente una coppia di server DNS esterni.
    
   b. Un indirizzo IP statico nella subnet della rete perimetrale esterna. Dovrai anche configurare il gateway predefinito nell'interfaccia esterna, ad esempio definendo il router che si affaccia su Internet o il firewall esterno come gateway predefinito. Configurare le impostazioni DNS della scheda in modo che puntino a un server DNS esterno o idealmente a una coppia di server DNS esterni. Questa configurazione è accettabile solo se in precedenza è stata configurata la topologia per avere valori non standard nelle assegnazioni di porta, che è illustrata nella [topologia create your Edge per Skype for Business Server](create-your-edge-topology.md) .
    
3. Nell'interfaccia interna configurare un IP statico nella subnet della rete perimetrale interna e non impostare un gateway predefinito. Abbandonare anche le impostazioni DNS Adapter vuote.
    
4. Creare route statiche permanenti sull'interfaccia interna a tutte le reti interne in cui si trovano i server client, Skype for Business Server e messaggistica UNIFICAta di Exchange.
    
5. Modificare il file HOST in ogni server perimetrale per contenere un record per il server hop successivo o l'IP virtuale (VIP). Questo record sarà il Director, il server Standard Edition o il pool Front-end configurato come indirizzo hop successivo di Edge Server in Generatore di topologia. Se si usa il bilanciamento del carico DNS, includere una riga per ogni membro del pool hop successivo.
    
## <a name="installation"></a>Installazione

Per completare correttamente questi passaggi, è necessario aver seguito i passaggi della [topologia create your Edge per Skype for Business Server](create-your-edge-topology.md) .
  
1. Accedere al server configurato per il ruolo Edge Server con un account nel gruppo dell'amministratore locale.
    
2. È necessario il file di configurazione della topologia copiato alla fine della documentazione della topologia di Edge Server in questo computer. Accedere al supporto esterno in cui è stato inserito il file di configurazione, ad esempio un'unità USB o una condivisione.
    
3. Avviare la **distribuzione guidata**.
    
4. Dopo l'apertura della procedura guidata, fare clic su **Installa o Aggiorna sistema di Skype for Business Server**.
    
5. La procedura guidata eseguirà i controlli per verificare se è già installato qualcosa. Poiché è la prima volta che viene eseguita la procedura guidata, è consigliabile iniziare dal **passaggio 1. Installare lo Store di configurazione locale.**
    
6. Verrà visualizzata la finestra **di dialogo Configura la replica locale di Central Management store** . È necessario fare clic su **Importa da un file (consigliato per Edge Server)**.
    
7. Da qui, passare al percorso della topologia esportata in precedenza, selezionare il file con estensione zip, fare clic su **Apri**e quindi su **Avanti**.
    
8. La distribuzione guidata leggerà il file di configurazione e scriverà il file di configurazione XML nel computer locale.
    
9. Dopo aver completato il processo di **esecuzione dei comandi** , fare clic su **fine**.
    
10. Nella distribuzione guidata fare clic su **passaggio 2. Configurare o rimuovere componenti di Skype for Business Server**. La procedura guidata installerà quindi i componenti Edge di Skype for Business Server specificati nel file di configurazione XML archiviato nel computer locale.
    
11. Una volta completata l'installazione, è possibile passare alla procedura descritta nella sezione **certificati** seguente.
    
## <a name="certificates"></a>Certificati

I requisiti di certificato per il server perimetrale sono disponibili nella documentazione relativa alla pianificazione del certificato perimetrale. I passaggi per la configurazione dei certificati sono riportati di seguito.
  
> [!NOTE]
> Quando si usa la procedura guidata certificato, è necessario avere effettuato l'accesso come account con le autorizzazioni corrette per il tipo di modello di certificato che si vuole usare. Per impostazione predefinita, una richiesta di certificato di Skype for Business Server userà il modello di certificato del server Web. Se si è effettuato l'accesso con un account che è un membro del gruppo RTCUniversalServerAdmins per richiedere un certificato tramite questo modello, verificare che il gruppo abbia assegnato le autorizzazioni di registrazione per l'uso del modello. 
  
### <a name="internal-edge-interface-certificates"></a>Certificati di interfaccia bordi interni

 
### <a name="1-download-or-export-the-ca-certification-chain"></a>1. scaricare o esportare la catena di certificazione CA

 
#### <a name="nbspnbspnbsp-a-download-using-certsrv-web-site"></a>&nbsp;&nbsp;&nbsp;un. Scaricare usando il sito Web di certsrv

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ho. Accedere a un server Skype for business nella rete interna come membro del gruppo Administrators locale.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Aprire **Start**ed **eseguire** (o **cercare** ed **eseguire** ), quindi digitare quanto segue:
    
  ```console
  https://<NAME OF YOUR ISSUING CA SERVER>/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Per esempio:
    
  ```console
  https://ca01/contoso.com/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;III. Nella pagina Web certsrv della CA emittente, in **selezionare un'attività**, fare clic su **Scarica un certificato CA, una catena di certificati o un CRL**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IV. In **scaricare un certificato CA, una catena di certificati o un CRL**fare clic su **Scarica catena di certificati CA**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v. Nella casella **Download file** fare clic su **Salva**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi. Salvare il file con estensione p7b nell'unità disco rigido del server e quindi copiarlo in una cartella di ogni server perimetrale.
    
### <a name="nbspnbspnbspb-export-using-mmc"></a>&nbsp;&nbsp;&nbsp;b. Esportare tramite MMC

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ho. È possibile esportare il certificato radice della CA da qualsiasi computer unito a un dominio tramite MMC. Passare a **Avvia** ed **Esegui**oppure aprire la **ricerca**e digitare **MMC** per aprirlo.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Nella console MMC fare clic su **file**e quindi su **Aggiungi/Rimuovi snap-in**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;III. Nell'elenco **Aggiungi o Rimuovi snap-** in selezionare **certificati**e quindi fare clic su **Aggiungi**. Quando richiesto, selezionare **account computer**e quindi **Avanti**. Nella finestra di dialogo **Seleziona computer** selezionare **computer locale**. Fare clic su **fine**e quindi su **OK**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IV. Espandere **certificati (computer locale)**. Espandere **autorità di certificazione radice attendibili**. Selezionare **certificati**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v. Fare clic sul certificato radice emesso dalla CA. Fare clic con il pulsante destro del mouse sul certificato, scegliere **tutte le attività** nel menu e quindi selezionare **Esporta**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi. Verrà visualizzata l' **esportazione guidata certificati** . Fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VII. Nella finestra di dialogo **Esporta formato file** scegliere il formato in cui si vuole esportare. La nostra raccomandazione è la **sintassi del messaggio crittografico standard-PKCS #7 certificati (P7b)**. Se è la scelta giusta, ricorda di selezionare anche la casella di controllo **Includi tutti i certificati nel percorso di certificazione, se possibile** , poiché verrà anche esportata la catena di certificati, incluso il certificato della CA radice e i certificati intermedi. Fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VIII. Nella finestra **di dialogo file da esportare** , nella voce nome file digitare un percorso e un nome file (l'estensione predefinita è p7b) per il certificato esportato. Se è più semplice, scegliere il pulsante **Sfoglia** per passare al percorso in cui si vuole salvare il certificato esportato e assegnare un nome al certificato esportato. Fare clic su **Salva**e quindi su **Avanti** quando si è pronti.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IX. Esaminare il riepilogo delle azioni e fare clic su **fine** per completare l'esportazione del certificato. Fare clic su **OK** per confermare l'esportazione riuscita.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;x. Copiare il file con estensione p7b in tutti i server perimetrali.
    
### <a name="2-import-the-ca-certification-chain"></a>2. importare la catena di certificazione CA

&nbsp;&nbsp;&nbsp;un. In ogni server perimetrale aprire la console MMC (scegliere **Avvia** ed **Esegui**oppure **Cerca**e digitare **MMC** per aprirla).
    
&nbsp;&nbsp;&nbsp;b. Nel menu **file** fare clic su **Aggiungi/Rimuovi snap-in**e quindi scegliere **Aggiungi**.
    
&nbsp;&nbsp;&nbsp;c. Nella casella **Aggiungi o Rimuovi snap-** in fare clic su **certificati**e quindi su **Aggiungi**.
    
&nbsp;&nbsp;&nbsp;3D. Nella finestra di dialogo di **snap-in certificato** fare clic su **account computer**e quindi su **Avanti**.
    
&nbsp;&nbsp;&nbsp;e. Nella finestra di dialogo **Seleziona computer** verificare che la casella di controllo computer **locale: (il computer in cui è in uso questa console)** sia selezionata e quindi fare clic su **fine**.
    
&nbsp;&nbsp;&nbsp;f. Fare clic su **Chiudi**e quindi su **OK**.
    
&nbsp;&nbsp;&nbsp;g. Nell'albero della console espandere **certificati (computer locale)**, fare clic con il pulsante destro del mouse su **autorità di certificazione radice attendibili**, scegliere **tutte le attività**e quindi fare clic su **Importa**.
    
&nbsp;&nbsp;&nbsp;h. Nella procedura guidata visualizzata, nel **file da importare** TextBox, specificare il nome del file del certificato (il nome assegnato al file p7b nella sezione precedente). Fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;Ho. Lasciare il pulsante di opzione in **posizione tutti i certificati nello Store seguente, come** dovrebbe essere selezionata l'opzione autorità di certificazione radice attendibili. Fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;j. Esaminare il riepilogo e fare clic su **fine** per completare l'importazione.
    
&nbsp;&nbsp;&nbsp;k. Questa operazione deve essere eseguita per ogni server perimetrale che si sta distribuendo.
    
### <a name="3-create-the-certificate-request"></a>3. creare la richiesta di certificato

&nbsp;&nbsp;&nbsp;un. Accedere a uno dei server perimetrali, avviare la distribuzione guidata e, al **passaggio 3: richiedere, installare o assegnare certificati**, fare clic su **Esegui** o **Esegui di nuovo**, se è già stata eseguita questa procedura guidata.
    
&nbsp;&nbsp;&nbsp;b. Nella pagina **richiesta certificato** verificare che sia selezionato il **certificato perimetrale interno** e quindi fare clic su **Richiedi**.
    
&nbsp;&nbsp;&nbsp;c. Nella pagina **richieste immediate o posticipate** scegliere **Invia immediatamente la richiesta a un'autorità di certificazione online** se si ha accesso a uno dall'ambiente Edge oppure **preparare la richiesta, ma inviarla in un secondo momento** .
    
&nbsp;&nbsp;&nbsp;3D. Nella pagina **file di richiesta di certificato** immettere la parte completa e il nome del file in cui verrà salvato il file (ad esempio c:\SkypeInternalEdgeCert.cer). Fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;e. Nella pagina **Specifica modello di certificato alternativo** per usare un modello diverso da quello predefinito del modello webserver, selezionare la casella di controllo **Usa modello di certificato alternativo per l'autorità di certificazione selezionata** . In caso contrario, non eseguire alcuna operazione.
    
&nbsp;&nbsp;&nbsp;f. Nella pagina impostazioni di sicurezza e nome eseguire le operazioni seguenti:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ho. In **nome descrittivo**immettere un nome visualizzato per il certificato, ad esempio bordo interno.
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. In **bit length**scegliere la lunghezza del bit (il valore predefinito è 2048, si può andare più in alto e renderlo più sicuro, ma il rallentamento delle prestazioni).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;III. Se è necessario un certificato esportabile, è necessario selezionare la casella **di controllo contrassegna la chiave privata del certificato come esportabile** .
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IV. Fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;g. Nella pagina **informazioni organizzazione** immettere il nome dell'organizzazione e dell'unità organizzativa. È possibile immettere la divisione o il reparto (ad esempio).
    
&nbsp;&nbsp;&nbsp;h. Nella pagina **informazioni geografiche** immettere le informazioni sulla posizione.
    
&nbsp;&nbsp;&nbsp;Ho. Nella pagina **nome oggetto/nomi di oggetto alternativo** questo deve essere popolato automaticamente dalla procedura guidata.
    
&nbsp;&nbsp;&nbsp;j. Nella pagina **Configura altri nomi alternativi** per l'oggetto è necessario aggiungere eventuali nomi alternativi di altri soggetti.
    
&nbsp;&nbsp;&nbsp;k. Nella pagina **Riepilogo richieste** esaminare le informazioni sul certificato che verranno usate per generare la richiesta. Se è necessario apportare modifiche, tornare a eseguire questa operazione ora.
    
&nbsp;&nbsp;&nbsp;l. Quindi fare clic su **Avanti** per generare il file CSR che è necessario fornire alla CA (è anche possibile fare clic su **Visualizza log** per esaminare il log per la richiesta di certificato).
    
&nbsp;&nbsp;&nbsp;m. Una volta che la richiesta è stata generata, è possibile fare clic su **Visualizza** per esaminare il certificato e **terminare** per chiudere la finestra. Il contenuto del file CSR deve essere assegnato alla CA, in modo che possa generare un certificato da importare nel computer nella sezione successiva.
    

### <a name="4-import-the-certificate"></a>4. importare il certificato

&nbsp;&nbsp;&nbsp;un. Accedere, come membro del gruppo Administrators locale, all'Edge Server in cui è stata effettuata la richiesta di certificato nell'ultima procedura.
    
&nbsp;&nbsp;&nbsp;b. Nella distribuzione guidata, accanto al **passaggio 3. Richiedere, installare o assegnare certificati**, fare di nuovo clic su **Esegui**.
    
&nbsp;&nbsp;&nbsp;c. Nella pagina **attività certificati disponibili** fare clic su **Importa un certificato da a. File di P7b, pfx o CER**.
    
&nbsp;&nbsp;&nbsp;3D. Nella pagina **Importa certificato** Digitare il percorso completo e il nome file del certificato ottenuto nella sezione precedente (oppure fare clic su **Sfoglia** per trovare e scegliere il file in questo modo).
    
&nbsp;&nbsp;&nbsp;e. Se si stanno importando certificati per altri membri del pool di Edge e il certificato contiene una chiave privata, assicurarsi di selezionare la casella di controllo **file di certificato contenente la chiave privata del certificato** e specificare la password. Fare clic su **Avanti** per continuare.
    
&nbsp;&nbsp;&nbsp;f. Nella pagina**Riepilogo** fare clic su **Avanti** dopo aver confermato le informazioni e **terminare** una volta che il certificato viene importato correttamente.
    
 
### <a name="5-export-the-certificate"></a>5. esportare il certificato

&nbsp;&nbsp;&nbsp;un. Verificare di aver eseguito l'accesso all'Edge Server in cui è stato importato il certificato in precedenza, come membro del gruppo Administrators locale.
    
&nbsp;&nbsp;&nbsp;b. Fare clic su **Start**, **Esegui** (o Apri **ricerca** ) e digitare **MMC**.
    
&nbsp;&nbsp;&nbsp;c. Nella console MMC fare clic su **file**e quindi su **Aggiungi/Rimuovi snap-in**.
    
&nbsp;&nbsp;&nbsp;3D. Nella casella **Aggiungi o Rimuovi snap-** in fare clic su **certificati**e quindi su **Aggiungi**.
    
&nbsp;&nbsp;&nbsp;e. Nella finestra di dialogo snap-in **certificati** scegliere **account computer**. Fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;f. Nella finestra di dialogo **Seleziona computer** selezionare **computer locale: (il computer in cui è in uso la console)**. Fare clic su **fine**. Fare clic su **OK**e la configurazione della console MMC è stata completata.
    
&nbsp;&nbsp;&nbsp;g. Fare doppio clic su **certificati (computer locale)** per espandere gli archivi di certificati. Fare doppio clic su **personale**e quindi su **certificati**.
    
  > [!NOTE]
  > Potrebbe essere presente e non vengono visualizzati certificati nell'archivio personale certificati per il computer locale. Non è necessario cercare in giro, se la chiave non è presente, il certificato importato non ha una chiave privata associata. Provare la richiesta e importare i passaggi sopra un'altra volta e, se si è certi di aver capito bene, rivolgersi all'amministratore o al provider della CA. 
  
&nbsp;&nbsp;&nbsp;h. Nell' **archivio personale certificati** per il computer locale fare clic con il pulsante destro del mouse sul certificato che si sta esportando. Selezionare **tutte le attività** dal menu risultante e quindi fare clic su **Esporta**.
    
&nbsp;&nbsp;&nbsp;Ho. Nell' **esportazione guidata certificati**fare clic su **Avanti**. Selezionare **Sì, esportare la chiave privata**. Fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;j. Nella finestra di dialogo **Esporta formati di file** selezionare **Personal Information Exchange-PKCS # 12 (. PFX)**, quindi selezionare le opzioni seguenti:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ho. Includere tutti i certificati nel percorso di certificazione, se possibile.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Esportare tutte le proprietà estese.
    
   > [!NOTE]
   > **Non selezionare mai** **Elimina la chiave privata se l'esportazione ha esito positivo**. Significa che è necessario reimportare nuovamente il certificato e la chiave privata in questo Edge Server.
  
&nbsp;&nbsp;&nbsp;k. Se si vuole assegnare una password per proteggere la chiave privata, è possibile digitare una password per la chiave privata. Immettere di nuovo la password per confermare e quindi fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;l. Digitare un percorso e un nome di file per il certificato esportato, usando un'estensione di file **PFX**. Il percorso deve essere accessibile dagli altri Edge Server nel pool oppure è necessario trasferire il file per mezzo di elementi multimediali esterni, ad esempio un'unità USB. Fare clic su **Avanti** dopo aver scelto.
    
&nbsp;&nbsp;&nbsp;m. Esaminare il riepilogo nella finestra di dialogo **completamento esportazione guidata certificati** e quindi fare clic su **fine**.
    
&nbsp;&nbsp;&nbsp;n. Fare clic su **OK** nella finestra di dialogo Esporta riuscita.
    
 
### <a name="6-assign-the-certificate"></a>6. assegnare il certificato

&nbsp;&nbsp;&nbsp;un. In ogni Edge Server, nella distribuzione guidata, accanto al **passaggio 3. Richiedere, installare o assegnare certificati**, fare di nuovo clic su **Esegui**.
    
&nbsp;&nbsp;&nbsp;b. Nella pagina **attività certificati disponibili** fare clic su **assegna un certificato esistente**.
    
&nbsp;&nbsp;&nbsp;c. Nella pagina **assegnazione certificato** selezionare **bordo interno** nell'elenco.
    
&nbsp;&nbsp;&nbsp;3D. Nella pagina **archivio certificati** selezionare il certificato importato per il bordo interno (dalla sezione precedente).
    
&nbsp;&nbsp;&nbsp;e. Nella pagina **Riepilogo assegnazione certificato** esaminare le impostazioni e quindi fare clic su **Avanti** per assegnare il certificato.
    
&nbsp;&nbsp;&nbsp;f. Nella pagina Completamento procedura guidata fare clic su **fine**.
    
&nbsp;&nbsp;&nbsp;g. Dopo aver completato questa procedura, è una buona idea aprire lo snap-in MMC certificati in ogni Edge Server, espandere **certificati (computer locale)**, espandere **personale**, fare clic su **certificati**e verificare che il certificato del bordo interno sia elencato nel riquadro dei dettagli.
    
### <a name="external-edge-interface-certificates"></a>Certificati di interfaccia esterni per i bordi

 
### <a name="1-create-the-certificate-request"></a>1. creare la richiesta di certificato

&nbsp;&nbsp;&nbsp;un. Accedere a uno dei server perimetrali, avviare la distribuzione guidata e, al **passaggio 3: richiedere, installare o assegnare certificati, fare clic su Esegui** o **Esegui di nuovo**, se è già stata eseguita questa procedura guidata.
    
&nbsp;&nbsp;&nbsp;b. Nella pagina **attività certificato disponibili** fare clic su **Crea una nuova richiesta di certificato**.
    
&nbsp;&nbsp;&nbsp;c. Nella pagina **richiesta certificato** verificare che sia selezionato **certificato perimetrale esterno** e quindi fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;3D. Nella pagina **richieste immediate o posticipate** fare clic su **prepara la richiesta ora, ma inviarla**in un secondo momento.
    
&nbsp;&nbsp;&nbsp;e. Nella pagina **file di richiesta di certificato** immettere la parte completa e il nome del file in cui verrà salvato il file (ad esempio c:\SkypeInternalEdgeCert.cer). Fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;f. Nella pagina **Specifica modello di certificato alternativo** per usare un modello diverso da quello predefinito del modello webserver, selezionare la casella di controllo **Usa modello di certificato alternativo per l'autorità di certificazione selezionata** .
    
&nbsp;&nbsp;&nbsp;g. Nella pagina impostazioni di sicurezza e nome eseguire le operazioni seguenti:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ho. In **nome descrittivo**immettere un nome visualizzato per il certificato, ad esempio bordo esterno.
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. In **bit length**scegliere la lunghezza del bit (il valore predefinito è 2048, si può andare più in alto e renderlo più sicuro, ma il rallentamento delle prestazioni).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;III. Se è necessario un certificato esportabile, è necessario selezionare la casella **di controllo contrassegna la chiave privata del certificato come esportabile** .
    
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IV. Fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;h. Nella pagina **informazioni organizzazione** immettere il nome dell'organizzazione e dell'unità organizzativa. È possibile immettere la divisione o il reparto (ad esempio).
    
&nbsp;&nbsp;&nbsp;Ho. Nella pagina **informazioni geografiche** immettere le informazioni sulla posizione.
    
&nbsp;&nbsp;&nbsp;j. Nella pagina **nome oggetto/nomi oggetto alternativo** le informazioni necessarie devono essere compilate automaticamente dalla procedura guidata.
    
&nbsp;&nbsp;&nbsp;k. Nell' **impostazione del dominio SIP nella pagina nome alternativo soggetto (sans)** selezionare la casella di controllo Domain per aggiungere un SIP.<sipdomain> voce nell'elenco dei nomi alternativi oggetto.
    
&nbsp;&nbsp;&nbsp;l. Nella pagina **Configura altri nomi alternativi** per l'oggetto è necessario aggiungere eventuali nomi alternativi di altri soggetti.
    
&nbsp;&nbsp;&nbsp;m. Nella pagina **Riepilogo richieste** esaminare le informazioni sul certificato che verranno usate per generare la richiesta. Se è necessario apportare modifiche, tornare a eseguire questa operazione ora.
    
&nbsp;&nbsp;&nbsp;n. Quando si è pronti, fare clic su **Avanti** per generare il file CSR che è necessario fornire alla CA (è anche possibile fare clic su **Visualizza log** per esaminare il log per la richiesta di certificato).
    
&nbsp;&nbsp;&nbsp;o. Una volta che la richiesta è stata generata, è possibile fare clic su **Visualizza** per esaminare il certificato e **terminare** per chiudere la finestra. Il contenuto del file CSR deve essere assegnato alla CA, in modo che possa generare un certificato da importare nel computer nella sezione successiva.
    
&nbsp;&nbsp;&nbsp;p. OPZIONALE Quando si inviano i contenuti della RSI, è possibile chiedere alcune informazioni, come indicato di seguito (le CA variano notevolmente, quindi potrebbe non essere necessario):
    
  - **Microsoft** come piattaforma server
    
  - **IIS** come versione
    
  - **Server Web** come tipo di utilizzo
    
  - **PKCS7** come formato di risposta
    
 
### <a name="2-import-the-certificate"></a>2. importare il certificato

&nbsp;&nbsp;&nbsp;un. Accedere, come membro del gruppo Administrators locale, all'Edge Server in cui è stata effettuata la richiesta di certificato nell'ultima procedura.
    
&nbsp;&nbsp;&nbsp;b. Nella distribuzione guidata, accanto al **passaggio 3. Richiedere, installare o assegnare certificati**, fare di nuovo clic su **Esegui**.
    
&nbsp;&nbsp;&nbsp;c. Nella pagina **attività certificati disponibili** fare clic su **Importa un certificato da a. File di P7b, pfx o CER**.
    
&nbsp;&nbsp;&nbsp;3D. Nella pagina **Importa certificato** Digitare il percorso completo e il nome file del certificato ottenuto nella sezione precedente (oppure fare clic su **Sfoglia** per trovare e scegliere il file in questo modo). Se il certificato contiene una chiave privata, assicurarsi di selezionare il **file di certificato contiene la chiave privata del certificato**e immettere la password per la chiave privata. Quando si è pronti, fare clic su **Avanti** .
    
&nbsp;&nbsp;&nbsp;e. Nella pagina **Importa Riepilogo del certificato** esaminare le informazioni di riepilogo e fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;f. Nella pagina **esecuzione dei comandi** è possibile esaminare il risultato dell'importazione al termine della procedura facendo clic su **Visualizza log**. Fare clic su **fine** per completare l'importazione del certificato.
    
&nbsp;&nbsp;&nbsp;g. Se si hanno altri Edge Server in un pool, sarà necessario seguire anche le due procedure seguenti. Se si tratta di un server perimetrale autonomo, i certificati esterni sono completati.
    
 
### <a name="3-export-the-certificate"></a>3. esportare il certificato

&nbsp;&nbsp;&nbsp;un. Verificare di aver eseguito l'accesso all'Edge Server in cui è stato importato il certificato come amministratore locale.
    
&nbsp;&nbsp;&nbsp;b. Fare clic su **Start**, **Esegui** (o Apri **ricerca** ) e digitare **MMC**.
    
&nbsp;&nbsp;&nbsp;c. Nella console MMC fare clic su **file**e quindi su **Aggiungi/Rimuovi snap-in**.
    
&nbsp;&nbsp;&nbsp;3D. Nella casella **Aggiungi o Rimuovi snap-** in fare clic su **certificati**e quindi su **Aggiungi**.
    
&nbsp;&nbsp;&nbsp;e. Nella finestra di dialogo snap-in **certificati** scegliere **account computer**. Fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;f. Nella finestra di dialogo **Seleziona computer** selezionare **computer locale: (il computer in cui è in uso la console)**. Fare clic su **fine**. Fare clic su **OK**e la configurazione della console MMC è stata completata.
    
&nbsp;&nbsp;&nbsp;g. Fare doppio clic su **certificati (computer locale)** per espandere gli archivi di certificati. Fare **doppio clic su personale**e quindi su **certificati**.
    
   > [!NOTE]
   > Potrebbe essere presente e non vengono visualizzati certificati nell'archivio personale certificati per il computer locale. Non è necessario cercare in giro, se la chiave non è presente, il certificato importato non ha una chiave privata associata. Provare la richiesta e importare i passaggi sopra un'altra volta e, se si è certi di aver capito bene, rivolgersi all'amministratore o al provider della CA. 
  
&nbsp;&nbsp;&nbsp;h. Nell' **archivio personale certificati** per il computer locale fare clic con il pulsante destro del mouse sul certificato che si sta esportando. **Selezionare tutte le attività** dal menu risultante e quindi fare clic su **Esporta**.
    
&nbsp;&nbsp;&nbsp;Ho. Nell' **esportazione guidata certificati**fare clic su **Avanti**. Selezionare **Sì, esportare la chiave privata**. Fare clic su **Avanti**.
    
   > [!NOTE]
   > Se **Sì, Esporta la chiave privata** non è disponibile, quindi la chiave privata per il certificato non è stata contrassegnata per l'esportazione prima di ottenerla. Prima di procedere correttamente, è necessario richiedere di nuovo il certificato dal provider, con la chiave privata impostata su Esporta.
  
&nbsp;&nbsp;&nbsp;j. Nella finestra di dialogo Esporta formati di file selezionare Personal Information Exchange-PKCS # 12 (. PFX) e quindi selezionare le opzioni seguenti:
    
 &nbsp;&nbsp;&nbsp;Ho. Includere tutti i certificati nel percorso di certificazione, se possibile.
    
 &nbsp;&nbsp;&nbsp;II. Esportare tutte le proprietà estese.
    
   > [!NOTE]
   > **Non selezionare mai** **Elimina la chiave privata se l'esportazione ha esito positivo**. Significa che è necessario reimportare nuovamente il certificato e la chiave privata in questo Edge Server.
  
&nbsp;&nbsp;&nbsp;k. Se si vuole assegnare una password per proteggere la chiave privata, è possibile digitare una password per la chiave privata. Immettere di nuovo la password per confermare e quindi fare clic su **Avanti**.
    
&nbsp;&nbsp;&nbsp;l. Digitare un percorso e un nome di file per il certificato esportato, usando un'estensione di file **PFX**. Il percorso deve essere accessibile dagli altri Edge Server nel pool oppure è necessario trasferire il file per mezzo di elementi multimediali esterni, ad esempio un'unità USB. Fare clic su **Avanti** dopo aver scelto.
    
&nbsp;&nbsp;&nbsp;m. Esaminare il riepilogo nella finestra di dialogo **completamento esportazione guidata certificati** e quindi fare clic su **fine**.
    
&nbsp;&nbsp;&nbsp;n. Fare clic su **OK** nella finestra di dialogo Esporta riuscita.
    
&nbsp;&nbsp;&nbsp;o. Ora dovrai tornare alla sezione importare il certificato prima di questo e importare il certificato in tutti i server perimetrali rimanenti, quindi procedere con l'assegnazione, sotto.
    
 
### <a name="4-assign-the-certificate"></a>4. assegnare il certificato

&nbsp;&nbsp;&nbsp;un. In **ogni** Edge Server, nella distribuzione guidata, accanto al **passaggio 3. Richiedere, installare o assegnare certificati**, fare di nuovo clic su **Esegui**.
    
&nbsp;&nbsp;&nbsp;b. Nella pagina **attività certificati disponibili** fare clic su **assegna un certificato esistente**.
    
&nbsp;&nbsp;&nbsp;c. Nella pagina **assegnazione certificato** selezionare **bordi esterni** nell'elenco.
    
&nbsp;&nbsp;&nbsp;3D. Nella pagina **archivio certificati** selezionare il certificato importato per il bordo esterno (dalla sezione precedente).
    
&nbsp;&nbsp;&nbsp;e. Nella pagina **Riepilogo assegnazione certificato** esaminare le impostazioni e quindi fare clic su **Avanti** per assegnare il certificato.
    
&nbsp;&nbsp;&nbsp;f. Nella pagina Completamento procedura guidata fare clic su **fine**.
    
&nbsp;&nbsp;&nbsp;g. Dopo aver completato questa procedura, è una buona idea aprire lo snap-in MMC certificati in ogni server, espandere **certificati (computer locale)**, espandere **personale**, fare clic su **certificati**e verificare che il certificato del bordo interno sia elencato nel riquadro dei dettagli.
    
   > [!NOTE]
   > Sarà inoltre necessario configurare i certificati per il server proxy inverso. 
  
## <a name="starting-the-edge-servers"></a>Avvio di Edge Server

Dopo aver completato la configurazione, è necessario avviare i servizi in ogni server perimetrale della distribuzione:
  
1. In ogni Edge Server, nella **distribuzione guidata**, accanto a **passaggio 4: avviare i servizi**, fare clic su **Esegui**.
    
2. Nella pagina **Avvia Skype for Business Server Services** esaminare l'elenco dei servizi e quindi fare clic su **Avanti** per avviare i servizi.
    
3. Dopo aver avviato i servizi, è possibile fare clic su **fine** per chiudere la procedura guidata.
    
4. Opzionale Sempre al **passaggio 4: avviare i servizi**, fare clic su **stato Servizi**.
    
5.  In **MMC Servizi** in ogni server verificare che tutti i servizi di Skype for Business Server siano in funzione.
    

