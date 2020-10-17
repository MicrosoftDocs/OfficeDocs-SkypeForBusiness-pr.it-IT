---
title: 'Lync Server 2013: configurare le regole di pubblicazione Web per un singolo pool interno'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web publishing rules for a single internal pool
ms:assetid: 86ff4b2a-1ba9-46a2-a175-8b19e00a49dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429712(v=OCS.15)
ms:contentKeyID: 48184725
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d159fd8fa4ade4cb2dee44da7fd7bbd2376b2a80
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520103"
---
# <a name="configure-web-publishing-rules-for-a-single-internal-pool-in-lync-server-2013"></a>Configurare le regole di pubblicazione Web per un singolo pool interno in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-07-07_

Microsoft Forefront Threat Management Gateway 2010 e Internet Information Server Application Request Routing (IIS ARR) utilizza le regole di pubblicazione Web per pubblicare risorse interne, ad esempio un URL di riunione, per gli utenti su Internet.

Oltre agli URL dei servizi Web per le directory virtuali, è inoltre necessario creare regole di pubblicazione per gli URL semplici, l'URL di LyncDiscover e il server Office Web Apps. Per ogni URL semplice, è necessario creare una singola regola nel proxy inverso che punti a tale URL semplice.

Se si sta eseguendo la distribuzione per dispositivi mobili e si utilizza l'individuazione automatica, è necessario creare una regola di pubblicazione per l'URL esterno del servizio di individuazione automatica. L'individuazione automatica richiede anche regole di pubblicazione per l'URL dei servizi Web di Lync Server esterno per il pool di Director e per il pool Front end. Per informazioni dettagliate sulla creazione delle regole di pubblicazione Web per l'individuazione automatica, vedere [configurazione del proxy inverso per i dispositivi mobili in Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).

Per creare regole di pubblicazione Web, eseguire le procedure seguenti.

<div>


> [!NOTE]  
> In queste procedure si presuppone che sia stata installata la versione Standard Edition di Forefront Threat Management Gateway (TMG) 2010 oppure che sia stato installato e configurato Internet Information Server con l'estensione del routing delle richieste di applicazioni (IIS ARR). Si utilizza TMG o IIS ARR.



</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-tmg-2010"></a>Per creare una regola di pubblicazione del server Web nel computer che esegue TMG 2010

1.  Fare clic sul pulsante **Start**, selezionare **Programmi**, **Microsoft Forefront TMG** e quindi fare clic su **Gestione Forefront TMG**.

2.  Nel riquadro sinistro espandere **NomeServer**, fare clic con il pulsante destro del mouse su **Criterio firewall**, selezionare **Nuovo** e quindi fare clic su **Regola di pubblicazione sito Web**.

3.  Nella pagina **Nuova regola di pubblicazione Web** digitare un nome visualizzato per la regola di pubblicazione, ad esempio RegolaDownloadWebLyncServer.

4.  Nella pagina **Seleziona azione regola** selezionare **Consenti**.

5.  Nella pagina **Tipo di pubblicazione** selezionare **Pubblica un singolo sito Web o un sistema di bilanciamento del carico**.

6.  Nella pagina **Protezione connessione server** selezionare **Utilizzare SSL per connettersi al server Web pubblicato o alla server farm**.

7.  Nella pagina **Dettagli pubblicazione interna** digitare il nome di dominio completo (FQDN) della Web farm interna che ospita il contenuto delle riunioni e della Rubrica nella casella **Nome sito interno**.
    
    <div>
    

    > [!NOTE]  
    > Se il server interno è un server Standard Edition, il nome di dominio completo corrisponde al nome di dominio completo del server Standard Edition. Se il server interno è un pool Front End, il nome di dominio completo corrisponde a un indirizzo VIP (Virtual IP) del servizio di bilanciamento del carico hardware che si occupa del bilanciamento del carico dei server interni della Web farm. Il server TMG deve essere in grado di risolvere il nome di dominio completo nell'indirizzo IP del server Web interno. Se il server TMG non è in grado di risolvere il nome di dominio completo con l'indirizzo IP appropriato, è possibile selezionare <STRONG>Usa un indirizzo IP o un computer per connettersi al server pubblicato</STRONG>e quindi digitare l'indirizzo IP del server Web interno nella casella <STRONG>nome computer o</STRONG> <STRONG>indirizzo IP</STRONG> . In tal caso, è necessario verificare che la porta 53 sia aperta nel server TMG e che sia possibile raggiungere un server DNS che si trova nella rete perimetrale. È anche possibile utilizzare le voci nell'host locale per la risoluzione dei nomi.

    
    </div>

8.  Nella casella **percorso (facoltativo)** della pagina **Dettagli pubblicazione interna** Digitare il **/\*** percorso della cartella da pubblicare.
    
    <div>
    

    > [!NOTE]  
    > Nella procedura guidata di pubblicazione del sito Web è possibile specificare solo un percorso. Per aggiungere altri percorsi, è necessario modificare le proprietà della regola.

    
    </div>

9.  Nella pagina **Dettagli nome pubblico** verificare che sia selezionata l'opzione **Nome dominio** in **Accetta richieste per** e digitare il nome di dominio completo esterno dei Servizi Web nella casella **Nome pubblico**.

10. Nella pagina **Scegliere Listener Web** fare clic su **Nuovo** per aprire la Creazione guidata definizione listener Web.

11. Nella pagina **Creazione guidata listener Web** digitare un nome per il listener Web nella casella **Nome listener Web**, ad esempio ServerWebLyncServer.

12. Nella pagina **Protezione di connessione client** selezionare **Richiedi connessioni SSL protette con i client**.

13. Nella pagina **Indirizzi IP del listener Web** selezionare **Esterno** e quindi fare clic su **Seleziona indirizzi IP**.

14. Nella pagina **Selezione IP listener esterno** selezionare **Indirizzo IP specificato nel computer Forefront TMG nella rete selezionata**, selezionare l'indirizzo IP appropriato e fare clic su **Aggiungi**.

15. Nella pagina **Certificati SSL listener** selezionare **Assegna un certificato a ciascun indirizzo IP**, selezionare l'indirizzo IP associato al nome FQDN Web esterno e quindi fare clic su **Seleziona certificato**.

16. Nella pagina **Seleziona certificato** selezionare il certificato corrispondente ai nomi pubblici specificati al passaggio 9 e fare clic su **Seleziona**.

17. Nella pagina **Impostazione di autenticazione** selezionare **Nessuna autenticazione**.

18. Nella pagina **Impostazioni Single Sign-On** fare clic su **Avanti**.

19. Nella pagina **Completamento della Creazione guidata listener Web** verificare che le impostazioni specificate in **Listener Web** siano corrette e quindi fare clic su **Fine**.

20. Nella pagina **Delega autenticazione** selezionare **Nessuna delega, ma il client può eseguire l'autenticazione direttamente**.

21. Nella pagina **Gruppo di utenti** fare clic su **Avanti**.

22. Nella pagina **Completamento della Creazione guidata regola di pubblicazione Web** verificare che le impostazioni della regola di pubblicazione Web siano corrette e quindi fare clic su **Fine**.

23. Nel riquadro dei dettagli fare clic su **Applica** per salvare le modifiche e aggiornare la configurazione.

</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-iis-arr"></a>Per creare una regola di pubblicazione del server Web nel computer in cui è in esecuzione IIS ARR

1.  Associare il certificato che verrà utilizzato per il proxy inverso al protocollo HTTPS. Fare clic sul pulsante **Start**, scegliere **programmi**, **strumenti di amministrazione**e quindi fare clic su **Gestione Internet Information Services (IIS)**.
    
    <div>
    

    > [!NOTE]  
    > Ulteriori informazioni, schermate e linee guida per la distribuzione e la configurazione di IIS ARR sono disponibili nell'articolo di NextHop <A href="https://go.microsoft.com/fwlink/?linkid=293391">che utilizza IIS ARR come proxy inverso per Lync Server 2013</A>.

    
    </div>

2.  Se non è stato ancora fatto, importare il certificato che verrà utilizzato per il proxy inverso. In **Gestione Internet Information Services (IIS)** fare clic sul nome del server proxy inverso sul lato sinistro della console. Al centro della console in **IIS** individuare i **certificati del server**. Fare clic con il pulsante destro del mouse su **certificati server** e scegliere **Apri funzionalità**.

3.  Sul lato destro della console, fare clic su **Importa...**. Digitare il percorso e il nome del file del certificato con l'estensione oppure fare clic su **...** per cercare il certificato. Selezionare il certificato e fare clic su **Apri**. Fornire la password utilizzata per proteggere la chiave privata (se è stata assegnata una password quando si esporta il certificato e la chiave privata). Fare clic su **OK**. Se l'importazione del certificato ha avuto esito positivo, il certificato verrà visualizzato come voce al centro della console come voce nei **certificati del server**.

4.  Assegnare il certificato per l'utilizzo da parte di HTTPS. Sul lato sinistro della console, selezionare il **sito Web predefinito** del server IIS. Sul lato destro fare clic su **Binding.** Nella finestra di dialogo **binding sito** fare clic su **Aggiungi...**. Nella finestra di dialogo **Aggiungi binding sito** in **tipo:** Selezionare **https**. Se si seleziona HTTPS, sarà possibile selezionare il certificato da utilizzare per HTTPS. In **certificato SSL:** selezionare il certificato importato per il proxy inverso. Fare clic su **OK**. Fare clic su **Chiudi**. Il certificato è ora associato al proxy inverso per Secure Socket Layer (SSL) e Transport Layer Security (TLS).
    
    <div>
    

    > [!IMPORTANT]  
    > Se viene visualizzato un messaggio di avviso durante la chiusura delle finestre di dialogo Binding che mancano i certificati intermedi, è necessario individuare e importare il certificato dell'autorità radice della CA pubblica e gli eventuali certificati intermedi della CA. Consultare le istruzioni all'autorità di certificazione pubblica di cui è stato richiesto il certificato e seguire le istruzioni per richiedere e importare una catena di certificati. Se il certificato è stato esportato dal server perimetrale, è possibile esportare il certificato della CA radice e tutti i certificati di CA intermedi associati al server perimetrale. Importare il certificato della CA radice nel computer (da non confondere con l'archivio utente) archiviare le autorità di certificazione radice attendibili e i certificati intermedi nell'archivio delle autorità di certificazione intermedie del computer.

    
    </div>

5.  Sul lato sinistro della console sotto il nome del server IIS, fare clic con il pulsante destro del mouse su **Server** farm e quindi scegliere **Crea server farm...**.
    
    <div>
    

    > [!NOTE]  
    > Se il nodo <STRONG>server farm</STRONG> non è visualizzato, è necessario installare il routing delle richieste di applicazioni. Per informazioni dettagliate, vedere <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A>.

    
    </div>
    
    Nella finestra di dialogo **Crea server farm** in **nome server farm**digitare il nome (può essere un nome descrittivo ai fini dell'identificazione) per il primo URL. Fare clic su **Avanti**.

6.  Nella finestra di dialogo **Aggiungi server** nell' **indirizzo del server**, digitare il nome di dominio completo (FQDN) dei servizi Web esterni nel server front-end. I nomi da utilizzare qui ad esempio sono gli stessi utilizzati nella sezione pianificazione per il proxy inverso, il [Riepilogo dei certificati-proxy inverso in Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md). Facendo riferimento alla pianificazione del proxy inverso, è necessario digitare il nome di dominio completo `webext.contoso.com` . Verificare che sia selezionata la casella di controllo accanto a **online** . Fare clic su **Aggiungi** per aggiungere il server al pool di server Web per la configurazione.
    
    <div>
    

    > [!WARNING]  
    > Lync Server utilizza dispositivi di bilanciamento del carico hardware per il pool di server Director e front end per il traffico HTTP e HTTPS. Si fornirà un solo FQDN quando si aggiunge un server alla server farm di IIS ARR. Il nome di dominio completo sarà il front end server o il Director nelle configurazioni del server non in pool o il nome di dominio completo del dispositivo di bilanciamento del carico hardware configurato per i pool di server. L'unico metodo supportato per il bilanciamento del carico del traffico HTTP e HTTPS consiste nell'utilizzo di dispositivi di bilanciamento del carico hardware.

    
    </div>

7.  Nella finestra di dialogo **Aggiungi server** fare clic su **Impostazioni avanzate.** In questo modo viene aperta una finestra di dialogo per definire il routing delle richieste di applicazioni per l'FQDN configurato. Lo scopo è quello di ridefinire la porta utilizzata quando la richiesta viene elaborata da IIS ARR.
    
    Per impostazione predefinita, la porta HTTP di destinazione deve essere definita come 8080. Fare clic su Avanti per il **httpPort 80** corrente e impostare il valore su **8080**. Fare clic su Avanti per il **httpsPort 443** corrente e impostare il valore su **4443**. Lasciare il parametro **Weight** su 100. Se necessario, è possibile ridefinire i pesi per una regola specificata una volta che si dispone di statistiche di base. Fare clic su **fine** per completare questa parte della configurazione della regola.

8.  È possibile che venga visualizzata una finestra di dialogo di riscrittura delle regole che informa che il responsabile di IIS può creare una regola di riscrittura degli URL per instradare automaticamente tutte le richieste in arrivo alla server farm. Fare clic su **Sì**. Le regole verranno adattate manualmente, ma se si seleziona Sì, verrà impostata la configurazione iniziale.

9.  Fare clic sul nome della server farm appena creato. In **server farm** in visualizzazione funzionalità di gestione IIS fare doppio clic su **memorizzazione nella cache**. Deselezionare **Abilita cache del disco**. Fare clic su **applica** sul lato destro.

10. Fare clic sul nome della server farm. In **server farm** in visualizzazione funzionalità di gestione IIS fare doppio clic su **proxy**. Nella pagina impostazioni proxy modificare il valore di **timeout (secondi)** su un valore appropriato per la distribuzione. Fare clic su **applica** per salvare la modifica.
    
    <div>
    

    > [!IMPORTANT]  
    > Il valore di timeout del proxy è un numero che può variare dalla distribuzione alla distribuzione. È necessario monitorare la distribuzione e modificare il valore per la migliore esperienza per i client. Potrebbe essere possibile impostare il valore come minimo di 200. Se si supportano client mobili Lync nell'ambiente, è necessario impostare il valore su 960 per consentire il timeout per le notifiche push da Office 365 che hanno un valore di timeout di 900. È molto probabile che sia necessario aumentare il valore di timeout per evitare che il client si disconnetta quando il valore è troppo basso o diminuisce il numero se le connessioni tramite il proxy non si disconnettono e si cancellano a lungo dopo la disconnessione del client. Monitoring and base-Lining ciò che è normale per l'ambiente è l'unico mezzo accurato per determinare la posizione corretta per questo valore.

    
    </div>

11. Fare clic sul nome della server farm. In **server farm** in visualizzazione funzionalità di gestione IIS fare doppio clic su **regole di routing**. Nella finestra di dialogo regole di routing in routing, deseleziona la casella di controllo accanto a attiva la ripartizione del carico di protezione SSL. Se la possibilità di deselezionare la casella di controllo non è disponibile, selezionare la casella di spunta per **utilizzare la riscrittura URL per esaminare le richieste in arrivo**. Fare clic su **applica** per salvare le modifiche.
    
    <div>
    

    > [!WARNING]  
    > La ripartizione del carico di inversione SSL tramite il proxy inverso non è supportata.

    
    </div>

12. Ripetere i passaggi 5-11 per ogni URL che deve passare attraverso il proxy inverso. Un elenco comune è il seguente:
    
      - Servizi Web front end server esterni: webext.contoso.com (già configurato tramite la passeggiata iniziale)
    
      - Servizi Web Director esterni per il server Director: webdirext.contoso.com (facoltativo se è stato distribuito un server Director)
    
      - URL semplice meet: meet.contoso.com
    
      - Dialin URL semplice: dialin.contoso.com
    
      - URL di individuazione automatica di Lync: lyncdiscover.contoso.com
    
      - URL del server Office Web Apps: officewebapps01.contoso.com
        
        <div>
        

        > [!IMPORTANT]  
        > L'URL per il server Office Web Apps utilizzerà un indirizzo httpsPort diverso. Nel passaggio 7 è possibile definire la <STRONG>httpsPort</STRONG> come <STRONG>443</STRONG> e la <STRONG>httpport</STRONG> come porta <STRONG>80</STRONG>. Tutte le altre impostazioni di configurazione sono uguali.

        
        </div>

13. Sul lato sinistro della console, fare clic sul nome del server IIS. Al centro della console, individuare la **riscrittura degli URL** in **IIS**. Fare doppio clic su URL Rewrite per aprire la configurazione delle regole di riscrittura degli URL. È necessario visualizzare le regole per ogni server farm creata nei passaggi precedenti. In caso contrario, verificare di aver fatto clic sul nome del **server IIS** subito sotto il nodo **pagina iniziale** nella console di Internet Information Server Manager.

14. Nella finestra di dialogo di **riscrittura degli URL** , usando webext.contoso.com come esempio, il nome completo della regola come visualizzato è **arr \_ webext.contoso.com \_ loadbalance \_ SSL**.
    
      - Fare doppio clic sulla regola per aprire la finestra di dialogo **Modifica regola in ingresso** .
    
      - Fare clic su **Aggiungi...** nella finestra di dialogo **condizioni** .
    
      - Nella condizione **Add** nella **condizione input:** type **{http \_ host}**. (Durante la digitazione, viene visualizzata una finestra di dialogo che consente di selezionare la condizione). in **Controlla se stringa di input:** seleziona **corrisponde al motivo**. Nel tipo di **input del modello** **\*** . L'opzione **Ignora caso** deve essere selezionata. Fare clic su **OK**.
    
      - Scorrere verso il basso nella finestra di dialogo **Modifica regola in ingresso** per individuare la finestra di dialogo **azione** . **Tipo di azione:** deve essere impostato su **route to server farm**, **Scheme:** impostare su **https://**, **server farm:** impostare l'URL a cui è applicata la regola. Per questo esempio, questa impostazione deve essere impostata su **webext.contoso.com**. **Percorso:** è impostato su **/{R: 0}**
    
      - Fare clic su **applica** per salvare le modifiche. Fare clic su **back to Rules** to return to the URL Rewrite rules.

15. Ripetere la procedura definita nel passaggio 14 per ognuna delle regole di riscrittura SSL definite, una per ogni URL della server farm.
    
    <div>
    

    > [!WARNING]  
    > Per impostazione predefinita, vengono create anche le regole HTTP e sono denotate dalla denominazione simile alle regole SSL. Per l'esempio corrente, la regola HTTP verrebbe denominata <STRONG>ARR_webext. contoso. com _loadbalance</STRONG>. Per queste regole non sono necessarie modifiche e possono essere ignorate in modo sicuro.

    
    </div>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-tmg-2010"></a>Per modificare le proprietà della regola di pubblicazione Web in TMG 2010

1.  Fare clic sul pulsante **Start**, scegliere **programmi**, **Microsoft Forefront TMG**e quindi fare clic su **gestione Forefront TMG**.

2.  Nel riquadro sinistro espandere **NomeServer** e quindi fare clic su **Criterio firewall**.

3.  Nel riquadro dei dettagli fare clic con il pulsante destro del mouse sulla regola di pubblicazione server Web creata nella procedura precedente, ad esempio RegolaEsternaLyncServer e quindi scegliere **Proprietà**.

4.  Nella scheda **Da** della pagina **Proprietà** eseguire le operazioni seguenti:
    
      - Nell'elenco **Questa regola si applica al traffico prodotto dalle seguenti origini** fare clic su **Ovunque** e quindi su **Rimuovi**.
    
      - Fare clic su **Aggiungi**.
    
      - In **Aggiungi entità di rete** espandere **Reti**, fare clic su **Esterno**, **Aggiungi** e quindi su **Chiudi**.

5.  Nella scheda **Per** verificare che la casella di controllo **Inoltra l'intestazione host originale e non quella effettiva** sia selezionata.

6.  Nella scheda **Bridging** selezionare la casella di controllo **Reindirizza richiesta a porta SSL** e quindi specificare la porta **4443**.

7.  Nella scheda **Nome pubblico** aggiungere gli URL semplici, ad esempio meet.contoso.com e dialin.contoso.com.

8.  Fare clic su **Applica** per salvare le modifiche e quindi su **OK**.

9.  Nel riquadro dei dettagli fare clic su **Applica** per salvare le modifiche e aggiornare la configurazione.

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-iis-arr"></a>Per modificare le proprietà della regola di pubblicazione Web in IIS ARR

1.  Fare clic sul pulsante **Start**, scegliere **programmi**, **strumenti di amministrazione**e quindi fare clic su **Gestione Internet Information Services (IIS)**.

2.  Sul lato sinistro della console, fare clic sul nome del server IIS.

3.  Al centro della console, individuare la **riscrittura degli URL** in **IIS**. Fare doppio clic su URL Rewrite per aprire la configurazione delle regole di riscrittura degli URL.

4.  Fare doppio clic sulla regola che è necessario modificare. Apportare le modifiche apportate, in base alle esigenze, in **URL**, **condizioni**, **variabili server** o **azione**.

5.  Fare clic su **applica** per eseguire il commit delle modifiche. Fare clic su **Torna alle regole** per modificare altre regole o chiudere la console di **Gestione IIS** se si ha a che fare con le modifiche apportate.

</div>

</div>

<span> </span>

</div>

</div>

</div>

