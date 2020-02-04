---
title: 'Lync Server 2013: Configurare le regole di pubblicazione Web per un singolo pool interno'
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
ms.openlocfilehash: 6ea798f3d5cefa3b65194eb8afcb6e9b35aaa9c1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-publishing-rules-for-a-single-internal-pool-in-lync-server-2013"></a>Configurare le regole di pubblicazione Web per un singolo pool interno in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-07-07_

Microsoft Forefront Threat Management Gateway 2010 e Internet Information Server Application Request Routing (IIS ARR) usa le regole di pubblicazione Web per pubblicare risorse interne, ad esempio un URL di riunione, per gli utenti su Internet.

Oltre agli URL dei servizi Web per le directory virtuali, devi anche creare regole di pubblicazione per URL semplici, l'URL LyncDiscover e il server Office Web Apps. Per ogni URL semplice, devi creare una singola regola nel proxy inverso che punta a tale URL semplice.

Se si sta distribuendo la mobilità e si usa l'individuazione automatica, è necessario creare una regola di pubblicazione per l'URL del servizio di rilevamento automatico esterno. L'individuazione automatica richiede anche regole di pubblicazione per l'URL dei servizi Web Lync Server esterni per il pool di Director e per il pool Front-end. Per informazioni dettagliate sulla creazione delle regole di pubblicazione Web per l'individuazione automatica, vedere [configurazione del proxy inverso per la mobilità in Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).

Usare le procedure seguenti per creare regole di pubblicazione Web.

<div>


> [!NOTE]  
> Queste procedure presuppongono che sia stata installata la versione standard di Forefront Threat Management Gateway (TMG) 2010 o che sia stato installato e configurato Internet Information Server con l'estensione di IIS ARR (Application Request Routing). Si usa TMG o IIS ARR.



</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-tmg-2010"></a>Per creare una regola di pubblicazione del server Web nel computer che utilizza TMG 2010

1.  Fare clic sul pulsante **Start**, selezionare **programmi**, **Microsoft Forefront TMG**e quindi fare clic su **gestione di Forefront TMG**.

2.  Nel riquadro sinistro espandere **nomeserver**, fare clic con il pulsante destro del mouse su **criteri firewall**, scegliere **nuovo**e quindi fare clic su **regola pubblicazione sito Web**.

3.  Nella pagina **Welcome to the New Web Publishing Rule** Digitare un nome visualizzato per la regola di pubblicazione, ad esempio LyncServerWebDownloadsRule.

4.  Nella pagina **selezionare l'azione di regola** selezionare **Consenti**.

5.  Nella pagina **tipo di pubblicazione** selezionare **pubblica un singolo sito Web o bilanciamento del carico**.

6.  Nella pagina **sicurezza connessione server** selezionare **Usa SSL per connettersi al server Web pubblicato o alla server farm**.

7.  Nella pagina **Internal Publishing Details** Digitare il nome di dominio completo (FQDN) della Web farm interna che ospita il contenuto della riunione e la Rubrica nella casella **nome sito interno** .
    
    <div>
    

    > [!NOTE]  
    > Se il server interno è un server Standard Edition, il nome completo è il nome di dominio completo del server Standard Edition. Se il server interno è un pool Front-End, il nome completo è un IP virtuale (VIP) di bilanciamento del carico hardware che bilancia il carico dei server della Web farm interna. Il server TMG deve essere in grado di risolvere il nome di dominio completo nell'indirizzo IP del server Web interno. Se il server TMG non è in grado di risolvere il nome di dominio completo con l'indirizzo IP corretto, è possibile selezionare Usa l'indirizzo <STRONG>IP del computer per connettersi al server pubblicato</STRONG>e quindi digitare l'indirizzo IP del server Web interno nella casella <STRONG>nome computer o</STRONG> <STRONG>indirizzo IP</STRONG> . In questo caso, devi assicurarti che la porta 53 sia aperta nel server TMG e che possa raggiungere un server DNS che risiede nella rete perimetrale. È anche possibile usare le voci nel file hosts locale per specificare la risoluzione dei nomi.

    
    </div>

8.  Nella casella **percorso (facoltativo)** della pagina ** / ** **Internal Publishing Details** Digitare il percorso della cartella da pubblicare.
    
    <div>
    

    > [!NOTE]  
    > Nella pubblicazione guidata sito Web è possibile specificare solo un percorso. I percorsi aggiuntivi possono essere aggiunti modificando le proprietà della regola.

    
    </div>

9.  Nella pagina **Public Name Details** verificare che il **nome di dominio** sia selezionato in **accetta richieste per**digitare l'FQDN dei servizi Web esterni nella casella **nome pubblico** .

10. Nella pagina **Seleziona listener Web** fare clic su **nuovo** per aprire la creazione guidata nuova definizione listener Web.

11. Nella pagina **Introduzione alla creazione guidata nuovo listener Web** Digitare un nome per il listener Web nella casella **nome listener Web** , ad esempio LyncServerWebServers.

12. Nella pagina **sicurezza connessione client** selezionare **Richiedi connessioni protette SSL con i client**.

13. Nella pagina **indirizzo IP del listener Web** selezionare **esterno**e quindi fare clic su **Seleziona indirizzi IP**.

14. Nella pagina di **Selezione IP del listener esterno** selezionare l' **indirizzo IP specificato nel computer Forefront TMG nella rete selezionata**, selezionare l'indirizzo IP appropriato, fare clic su **Aggiungi**.

15. Nella pagina **certificati SSL listener** selezionare **assegna un certificato per ogni indirizzo IP**, selezionare l'indirizzo IP associato al nome FQDN Web esterno e quindi fare clic su **Seleziona certificato**.

16. Nella pagina **Seleziona certificato** selezionare il certificato che corrisponde ai nomi pubblici specificati nel passaggio 9, fare clic su **Seleziona**.

17. Nella pagina **impostazione autenticazione** selezionare **Nessuna autenticazione**.

18. Nella pagina **Single Sign on setting** fare clic su **Avanti**.

19. Nella pagina **completamento della creazione guidata listener Web** verificare che le impostazioni del **listener Web** siano corrette e quindi fare clic su **fine**.

20. Nella pagina **Delega autenticazione** selezionare **Nessuna delega, ma il client può eseguire l'autenticazione direttamente**.

21. Nella pagina **set di utenti** fare clic su **Avanti**.

22. Nella pagina **completamento della nuova creazione guidata regola Web Publishing** verificare che le impostazioni della regola di pubblicazione Web siano corrette e quindi fare clic su **fine**.

23. Fare clic su **applica** nel riquadro dei dettagli per salvare le modifiche e aggiornare la configurazione.

</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-iis-arr"></a>Per creare una regola di pubblicazione del server Web nel computer in cui è in uso IIS ARR

1.  Associa il certificato che userai per il proxy inverso al protocollo HTTPS. Fare clic sul pulsante **Start**, selezionare **programmi**, **strumenti di amministrazione**e quindi fare clic su **Gestione Internet Information Services (IIS)**.
    
    <div>
    

    > [!NOTE]  
    > Ulteriori informazioni, schermate e indicazioni per la distribuzione e la configurazione di IIS ARR sono disponibili nell'articolo NextHop <A href="http://go.microsoft.com/fwlink/?linkid=293391">con IIS ARR come proxy inverso per Lync Server 2013</A>.

    
    </div>

2.  Se non è già stato fatto, importare il certificato che verrà usato per il proxy inverso. In **Gestione Internet Information Services (IIS)** fare clic sul nome del server proxy inverso nella dimensione sinistra della console. Al centro della console in **IIS** individuare i **certificati server**. Fare clic con il pulsante destro del mouse su **certificati server** e scegliere **Apri funzionalità**.

3.  Sul lato destro della console fare clic su **Importa...**. Digitare il percorso e il nome del file del certificato con l'estensione oppure fare clic su **...** per cercare il certificato. Selezionare il certificato e fare clic su **Apri**. Specificare la password usata per proteggere la chiave privata (se è stata assegnata una password durante l'esportazione del certificato e della chiave privata). Fare clic su **OK**. Se l'importazione del certificato è stata eseguita correttamente, il certificato verrà visualizzato come voce nel centro della console come voce in **certificati server**.

4.  Assegnare il certificato per l'uso da parte di HTTPS. Sul lato sinistro della console selezionare il **sito Web predefinito** del server IIS. Sul lato destro fare clic su **Binding...**. Nella finestra di dialogo **Associazioni sito** fare clic su **Aggiungi...**. Nella finestra di dialogo **Aggiungi binding sito** in **tipo:** Selezionare **https**. La selezione di HTTPS consente di selezionare il certificato da usare per HTTPS. In **certificato SSL:** selezionare il certificato importato per il proxy inverso. Fare clic su **OK**. Quindi fare clic su **Chiudi**. Il certificato è ora associato al proxy inverso per Secure Socket Layer (SSL) e Transport Layer Security (TLS).
    
    <div>
    

    > [!IMPORTANT]  
    > Se viene visualizzato un messaggio di avviso quando si chiudono le finestre di dialogo Binding che mancano ai certificati intermedi, è necessario individuare e importare il certificato autorità di certificazione radice pubblica e gli eventuali certificati intermedi della CA. Consultare le istruzioni della CA pubblica a cui è stato richiesto il certificato e seguire le istruzioni per richiedere e importare una catena di certificati. Se il certificato è stato esportato dall'Edge Server, è possibile esportare il certificato della CA radice e gli eventuali certificati intermedi della CA associati al server perimetrale. Importare il certificato della CA radice nel computer (da non confondere con l'archivio degli utenti) archiviare le autorità di certificazione radice attendibili e i certificati intermedi nell'archivio delle autorità di certificazione intermedi del computer.

    
    </div>

5.  Sul lato sinistro della console sotto il nome del server IIS fare clic con il pulsante destro del mouse su **Server** Farms e quindi scegliere **Crea server farm...**.
    
    <div>
    

    > [!NOTE]  
    > Se il nodo <STRONG>Server Farms</STRONG> non è visibile, è necessario installare il routing delle richieste di applicazione. Per informazioni dettagliate, vedere <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">configurazione di server proxy inversa per Lync Server 2013</A>.

    
    </div>
    
    Nella finestra di dialogo **Crea server farm** in **nome server farm**digitare il nome (può essere un nome descrittivo per scopi di identificazione) per il primo URL. Fare clic su **Avanti**.

6.  Nella finestra di dialogo **Aggiungi server** in **Indirizzo server**digitare il nome di dominio completo (FQDN) dei servizi Web esterni nel server front-end. I nomi che verranno usati qui ad esempio per scopi sono gli stessi usati nella sezione pianificazione per il proxy inverso, il [proxy di riepilogo del certificato in Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md). Facendo riferimento alla pianificazione del proxy inverso, digitiamo il nome `webext.contoso.com`di dominio completo. Verificare che la casella di controllo accanto a **online** sia selezionata. Fare clic su **Aggiungi** per aggiungere il server al pool di server Web per questa configurazione.
    
    <div>
    

    > [!WARNING]  
    > Lync Server usa i dispositivi di bilanciamento del carico hardware per il pool Director e i server front end per il traffico HTTP e HTTPS. Verrà fornito un nome di dominio completo solo quando si aggiunge un server alla server farm di IIS ARR. Il nome di dominio completo sarà il server front-end o il Director nelle configurazioni del server non in pool o il nome di dominio completo del bilanciamento del carico hardware configurato per i pool di server. L'unico metodo supportato per caricare il traffico HTTP e HTTPS tramite il bilanciamento del carico hardware.

    
    </div>

7.  Nella finestra di dialogo **Aggiungi server** fare clic su **Impostazioni avanzate.** Verrà aperta una finestra di dialogo che consente di definire il routing delle richieste di applicazioni per il nome di dominio completo configurato. Lo scopo è quello di ridefinire quale porta viene usata quando la richiesta viene elaborata da IIS ARR.
    
    Per impostazione predefinita, la porta HTTP di destinazione deve essere definita come 8080. Fare clic su accanto alla corrente **httpPort 80** e impostare il valore su **8080**. Fare clic su accanto alla corrente **httpsPort 443** e impostare il valore su **4443**. Abbandonare il parametro **Weight** in 100. Se necessario, è possibile ridefinire i pesi per una determinata regola dopo avere statistiche di base. Fare clic su **fine** per completare questa parte della configurazione della regola.

8.  Potrebbe essere visualizzata una finestra di dialogo di riscrittura delle regole che informa che Gestione IIS può creare una regola di riscrittura URL per instradare automaticamente tutte le richieste in arrivo alla server farm. Fare clic su **Sì**. Le regole verranno modificate manualmente, ma selezionando Sì viene impostata la configurazione iniziale.

9.  Fare clic sul nome della server farm appena creato. In **server farm** in visualizzazione funzionalità di gestione IIS fare doppio clic su **memorizzazione nella cache**. Deselezionare **Attiva cache disco**. Fare clic su **applica** sul lato destro.

10. Fare clic sul nome della server farm. In **server farm** in visualizzazione funzionalità di gestione IIS fare doppio clic su **proxy**. Nella pagina impostazioni proxy modificare il valore per il **timeout (secondi)** in un valore appropriato per la distribuzione. Fare clic su **applica** per salvare la modifica.
    
    <div>
    

    > [!IMPORTANT]  
    > Il valore di timeout del proxy è un numero che può variare dalla distribuzione alla distribuzione. È consigliabile monitorare la distribuzione e modificare il valore per l'esperienza ottimale per i client. Potresti essere in grado di impostare il valore in basso come 200. Se si supportano client mobili Lync nell'ambiente, è necessario impostare il valore su 960 per consentire il timeout delle notifiche push da Office 365 che hanno un valore di timeout di 900. È molto probabile che sia necessario aumentare il valore di timeout per evitare la disconnessione del client quando il valore è troppo basso o ridurre il numero se le connessioni tramite il proxy non si disconnettono e si cancellano molto dopo la disconnessione del client. Il monitoraggio e la fodera di base ciò che è normale per l'ambiente è l'unico mezzo preciso per determinare la posizione corretta per questo valore.

    
    </div>

11. Fare clic sul nome della server farm. In **server farm** in visualizzazione funzionalità di gestione IIS fare doppio clic su **regole di routing**. Nella finestra di dialogo regole di routing in routing deselezionare la casella di controllo accanto a Consenti ripartizione del carico SSL. Se la possibilità di deselezionare la casella di controllo non è disponibile, selezionare l'opzione per l' **uso della riscrittura URL per esaminare le richieste in arrivo**. Fare clic su **applica** per salvare le modifiche.
    
    <div>
    

    > [!WARNING]  
    > La ripartizione dello scarico SSL tramite il proxy inverso non è supportata.

    
    </div>

12. Ripetere i passaggi 5-11 per ogni URL che deve passare tramite il proxy inverso. Un elenco comune dovrebbe essere il seguente:
    
      - Servizi Web front-end server esterni: webext.contoso.com (già configurato tramite la passeggiata iniziale)
    
      - Director Web Services esterni per Director: webdirext.contoso.com (facoltativo se un amministratore è distribuito)
    
      - URL semplice riunione: meet.contoso.com
    
      - Dialin URL semplice: dialin.contoso.com
    
      - URL di individuazione automatica di Lync: lyncdiscover.contoso.com
    
      - URL del server Office Web Apps: officewebapps01.contoso.com
        
        <div>
        

        > [!IMPORTANT]  
        > L'URL per il server Office Web Apps userà un indirizzo httpsPort diverso. Nel passaggio 7 Definisci <STRONG>httpsPort</STRONG> come <STRONG>443</STRONG> e <STRONG>httpport</STRONG> come porta <STRONG>80</STRONG>. Tutte le altre impostazioni di configurazione sono le stesse.

        
        </div>

13. Sul lato sinistro della console fare clic sul nome del server IIS. Al centro della console individuare la **riscrittura URL** in **IIS**. Fare doppio clic su Riscrivi URL per aprire la configurazione delle regole di riscrittura degli URL. Dovresti vedere le regole per ogni server farm creata nei passaggi precedenti. In caso contrario, verificare di aver fatto clic sul nome del **server IIS** immediatamente sotto il nodo **pagina iniziale** nella console Internet Information Server Manager.

14. Nella finestra di dialogo **URL riscrittura** , usando webext.contoso.com come esempio, il nome completo della regola visualizzata è **\_arr webext.contoso.com\_loadbalance\_SSL**.
    
      - Fare doppio clic sulla regola per aprire la finestra di dialogo **Modifica regola in ingresso** .
    
      - Fare clic su **Aggiungi...** nella finestra di dialogo **condizioni** .
    
      - Nella condizione **Add** in **input Condition:** digitare **{http\_host}**. (Durante la digitazione viene visualizzata una finestra di dialogo che consente di selezionare la condizione). in **Controlla se stringa di input:** seleziona **corrisponde allo schema**. Nel tipo **\*** di **input pattern** . La **distinzione tra maiuscole e minuscole** deve essere selezionata. Fare clic su **OK**.
    
      - Scorrere verso il basso nella finestra di dialogo **Modifica regola in entrata** per individuare la finestra di dialogo **azione** . **Tipo di azione:** deve essere impostato su **route to server farm**, **Scheme:** set to **https://**, **server farm:** impostato sull'URL a cui è applicata la regola. Per questo esempio, questo deve essere impostato su **webext.contoso.com**. **Path:** è impostato su **/{R: 0}**
    
      - Fare clic su **applica** per salvare le modifiche. Fare clic su **Torna alle regole** per tornare alle regole di riscrittura degli URL.

15. Ripetere la procedura definita nel passaggio 14 per ognuna delle regole di riscrittura SSL definite, una per ogni URL della farm server.
    
    <div>
    

    > [!WARNING]  
    > Per impostazione predefinita, vengono create anche le regole HTTP e sono contrassegnate dalla denominazione simile alle regole SSL. Per l'esempio corrente, la regola HTTP sarà denominata <STRONG>ARR_webext. contoso. com_loadbalance</STRONG>. Per queste regole non sono necessarie modifiche e possono essere ignorate in modo sicuro.

    
    </div>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-tmg-2010"></a>Per modificare le proprietà della regola di pubblicazione Web in TMG 2010

1.  Fare clic sul pulsante **Start**, scegliere **programmi**, **Microsoft Forefront TMG**e quindi fare clic su **gestione di Forefront TMG**.

2.  Nel riquadro sinistro espandere **nomeserver**e quindi fare clic su **criteri firewall**.

3.  Nel riquadro dei dettagli fare clic con il pulsante destro del mouse sulla regola di pubblicazione del server Web creata nella procedura precedente, ad esempio LyncServerExternalRule, e quindi scegliere **Proprietà**.

4.  Nella scheda **da** della pagina **Proprietà** eseguire le operazioni seguenti:
    
      - In **questa regola si applica al traffico proveniente da questi** elenchi di origini, fare clic in un **punto qualsiasi**e quindi fare clic su **Rimuovi**.
    
      - Fare clic su **Aggiungi**.
    
      - In **Aggiungi entità di rete**espandere **reti**, fare clic su **esterno**, fare clic su **Aggiungi**e quindi su **Chiudi**.

5.  Nella scheda **a** verificare che la casella di controllo **Inoltra l'intestazione host originale invece di quella effettiva** sia selezionata.

6.  Nella scheda **bridging** selezionare la casella di controllo **reindirizza la richiesta alla porta SSL** e quindi specificare la porta **4443**.

7.  Nella scheda **nome pubblico** aggiungere gli URL semplici, ad esempio meet.contoso.com e dialin.contoso.com.

8.  Fare clic su **applica** per salvare le modifiche e quindi fare clic su **OK**.

9.  Fare clic su **applica** nel riquadro dei dettagli per salvare le modifiche e aggiornare la configurazione.

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-iis-arr"></a>Per modificare le proprietà della regola di pubblicazione Web in IIS ARR

1.  Fare clic sul pulsante **Start**, selezionare **programmi**, **strumenti di amministrazione**e quindi fare clic su **Gestione Internet Information Services (IIS)**.

2.  Sul lato sinistro della console fare clic sul nome del server IIS.

3.  Al centro della console individuare la **riscrittura URL** in **IIS**. Fare doppio clic su Riscrivi URL per aprire la configurazione delle regole di riscrittura degli URL.

4.  Fare doppio clic sulla regola che è necessario modificare. Apportare le modifiche necessarie, in corrispondenza di **URL**, **condizioni**, **variabili del server** o **azione**.

5.  Fare clic su **applica** per eseguire il commit delle modifiche. Fare clic su **Torna alle regole** per modificare altre regole oppure chiudere la console di **Gestione IIS** , se è stata completata la modifica.

</div>

</div>

<span> </span>

</div>

</div>

</div>

