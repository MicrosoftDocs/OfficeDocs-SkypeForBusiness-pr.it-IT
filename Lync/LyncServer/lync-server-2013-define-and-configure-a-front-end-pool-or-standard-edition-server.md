---
title: Definire e configurare un pool Front end o un server Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a Front End pool or Standard Edition server
ms:assetid: 713fc263-23dd-414a-b001-82932e4fe966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398538(v=OCS.15)
ms:contentKeyID: 48184457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 847aeda66657b2bd665964d6fec3276dc22807ea
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531513"
---
# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a>Definire e configurare un pool Front end o un server Standard Edition in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-08_

Per questa procedura non è necessaria l'appartenenza a un gruppo di amministratori locali o di dominio privilegiato, ma è consigliabile accedere a un computer come utente standard.

Se si sta distribuendo un server Enterprise, è necessario che il numero minimo di front end server in un pool sia sempre in esecuzione. I requisiti di versione sono riassunti nella tabella seguente.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Numero totale di Front End Server nel pool</th>
<th>Numero minimo di server attivi per il funzionamento del pool</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1-2</p></td>
<td><p>1 </p></td>
</tr>
<tr class="even">
<td><p>3-4</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>5-6</p></td>
<td><p>3</p></td>
</tr>
<tr class="even">
<td><p>7-8</p></td>
<td><p>4 </p></td>
</tr>
<tr class="odd">
<td><p>9-10</p></td>
<td><p>5 </p></td>
</tr>
<tr class="even">
<td><p>11-12</p></td>
<td><p>6 </p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> Per Lync Server 2013, ogni volta che si aggiunge o si rimuove un front end server dal pool, è necessario riavviare i servizi. La rimozione e l'aggiunta di server devono essere eseguite come operazioni separate. Ad esempio, se si intende aggiungere due front end server e rimuovere due front end server, utilizzare il processo seguente: 
> <OL>
> <LI>
> <P>Rimuovere i due Front End Server</P>
> <LI>
> <P>Pubblicare e riattivare la topologia.</P>
> <LI>
> <P>Riavviare i servizi.</P>
> <LI>
> <P>Aggiungere i due Front End Server</P>
> <LI>
> <P>Pubblicare e riattivare la topologia.</P>
> <LI>
> <P>Riavviare i servizi.</P></LI></OL>



</div>

Dopo aver definito la topologia, utilizzare la procedura seguente per definire un pool Front end per il sito. Per informazioni dettagliate sulla definizione della topologia, vedere [definire e configurare una topologia in Generatore di topologie per Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).

<div>

## <a name="to-define-a-front-end-pool"></a>Per definire un pool Front End

1.  Nella pagina **Definire il nuovo pool Front End** della procedura guidata Definisci nuovo pool Front End fare clic su **Avanti**.

2.  Nella pagina **definire l'FQDN del pool Front End** immettere un nome di dominio completo (FQDN) per il pool in cui si sta creando, fare clic su **Enterprise Edition Front End pool**e quindi fare clic su **Avanti**.

3.  Nella pagina **definire i computer in questo pool** , immettere un nome di dominio completo del computer per il primo front end server nel pool e quindi fare clic su **Aggiungi**. Ripetere questo passaggio per tutti i computer aggiuntivi (fino a dodici anni) che si desidera aggiungere al pool e quindi fare clic su **Avanti**.

4.  Nella pagina **Selezionare funzionalità** selezionare le caselle di controllo corrispondenti alle caratteristiche desiderate per il pool Front End. Ad esempio, se si stanno distribuendo solo le funzionalità di messaggistica istantanea e presenza, è necessario selezionare la casella di controllo per consentire la messaggistica istantanea a più parti, ma non selezionare le caselle di controllo per le conferenze telefoniche **con accesso esterno**, **VoIP aziendale**o di **ammissione di chiamata** , perché **rappresentano le funzionalità** di conferenza vocale, video e di collaborazione.
    
      - Servizi di **conferenza**     Questa opzione consente di abilitare un set completo di funzionalità, tra cui:
        
          - Messaggistica istantanea con più di due partecipanti in una sessione
        
          - Servizio di conferenza, che include la collaborazione sui documenti, la condivisione di applicazioni e la condivisione del desktop
        
          - A/V Conferencing, che consente agli utenti di disporre di conferenze audio/video (A/V) in tempo reale senza dover utilizzare servizi esterni, come il servizio Live Meeting o un ponte audio di terze parti.
    
      - Servizi **di conferenza telefonica con accesso esterno**     (PSTN) Consente agli utenti di partecipare alla parte audio di una conferenza di Lync Server 2013 utilizzando un telefono PSTN (Public Switched Telephone Network) senza richiedere un provider di servizi di audioconferenza.
    
      - **VoIP aziendale**     Enterprise Voice è la soluzione VoIP (Voice over IP) in Lync Server 2013 che consente agli utenti di effettuare e ricevere chiamate telefoniche. Questa caratteristica viene distribuita se si prevede di utilizzare Lync Server 2013 per le chiamate vocali, la segreteria telefonica e altre funzioni che utilizzano un dispositivo hardware o un client software.
    
      - **Controllo di ammissione di chiamata (CAC)**     Il controllo di ammissione di chiamata determina, in base alla larghezza di banda di rete disponibile, se consentire la creazione di sessioni di comunicazione in tempo reale, ad esempio chiamate vocali o video. Se si distribuiscono solo le funzionalità di messaggistica istantanea e presenza, il controllo di ammissione di chiamata non è necessario, perché non è utilizzato da nessuna di queste due funzionalità.
    
      - **Archiviazione**     L'archiviazione consente di archiviare il contenuto di messaggistica istantanea, il contenuto delle conferenze (riunioni) o entrambi inviati tramite Lync Server 2013.
    
      - **Monitoraggio**     Monitoring Server consente di raccogliere dati numerici che descrivono la qualità multimediale della rete e degli endpoint, le informazioni sull'utilizzo relative alle chiamate VoIP, i messaggi di messaggistica istantanea, le conversazioni A/V, le riunioni, la condivisione di applicazioni e i trasferimenti di file e le informazioni sulla risoluzione dei problemi per le chiamate non riuscite.
    
    <div>
    

    > [!NOTE]
    > Se si desidera abilitare il servizio Controllo di ammissione di chiamata nella distribuzione, è necessario abilitarlo esattamente in un pool per ogni sito centrale. È consigliabile abilitare questo servizio quando si distribuiscono caratteristiche vocali o conferenze audio/video.

    
    </div>
    
    Nella tabella seguente vengono indicate le caratteristiche disponibili (in alto) e le funzioni offerte agli utenti (a sinistra). Le selezioni indicate nella tabella corrispondono alle opzioni che è necessario selezionare per abilitare queste caratteristiche per l'organizzazione.
    
    
    <table>
    <colgroup>
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th></th>
    <th>Conferenze</th>
    <th>Conferenze telefoniche con accesso esterno</th>
    <th>VoIP aziendale</th>
    <th>Controllo di ammissione di chiamata</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Messaggistica istantanea e presenza</p></td>
    <td><p>X</p></td>
    <td></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="even">
    <td><p>Conferenze</p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="odd">
    <td><p>A/V conferencing</p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    <td></td>
    <td><p>X</p></td>
    </tr>
    <tr class="even">
    <td><p>VoIP aziendale</p></td>
    <td></td>
    <td></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    </tr>
    </tbody>
    </table>


5.  Nella pagina **Selezione ruoli server collocato** è possibile collocare il Mediation Server nel front end server o distribuirlo come server autonomo.
    
    È possibile collocare il Mediation Server nel pool Front end.
    
      - Se si intende collocare il Mediation Server nel pool Enterprise Edition front end, verificare che sia selezionata la casella di controllo. I ruoli del server verranno distribuiti nei server del pool.
    
      - Se si intende distribuire il Mediation Server come server autonomo, deselezionare la casella di controllo appropriata. Si distribuirà Mediation Server in un passaggio di distribuzione separato dopo aver completamente distribuito il front end server.
    
    <div>
    

    > [!NOTE]
    > È consigliabile aggiungere Mediation Server nella stessa posizione, se possibile. Per informazioni dettagliate sul supporto per i Mediation Server collocati o autonomi, vedere <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">componenti e topologie per Mediation Server in Lync server 2013</A> nella documentazione relativa alla pianificazione.

    
    </div>

6.  I **ruoli del server associato con questa pagina del pool Front End** consentono di definire e associare i ruoli del server al pool Front end. È disponibile il seguente ruolo:
    
    **Abilitazione di un pool**     di server perimetrali Definisce e associa un singolo server perimetrale o un pool di server perimetrali. Un server perimetrale facilita la comunicazione e la collaborazione tra gli utenti all'interno dell'organizzazione e le persone esterne all'organizzazione, inclusi gli utenti federati.
    
    Esistono due possibili scenari che è possibile utilizzare per distribuire e associare i ruoli del server:
    
    Per il primo scenario, è necessario definire una nuova topologia per una nuova installazione. È possibile eseguire l'installazione scegliendo tra due metodi diversi:
    
      - Lasciare deselezionate tutte le caselle di controllo e continuare con la definizione della topologia. Dopo aver pubblicato, configurato e testato i ruoli del server front-end e back-end, è possibile eseguire di nuovo il generatore di topologie per aggiungere i server di ruoli alla topologia. Questa strategia consentirà di verificare il pool Front end e il server che esegue SQL Server senza ulteriori complicazioni da ruoli aggiuntivi. Dopo aver completato il testing iniziale, è possibile eseguire di nuovo il generatore di topologie per selezionare i ruoli che è necessario distribuire.
    
      - Selezionare i ruoli che è necessario installare e quindi configurare l'hardware per gestire i ruoli selezionati.
    
    Per lo scenario 2 si dispone di una distribuzione esistente e l'infrastruttura è pronta per i nuovi ruoli oppure è necessario associare i ruoli esistenti a un nuovo front end server:
    
      - In questo caso, verranno selezionati i ruoli che si intende distribuire o associare al nuovo front end server. In entrambi i casi, sarà necessario procedere con la definizione dei ruoli, la configurazione dell'hardware necessario e l'installazione.

7.  Nella pagina **Definire archivio SQL** eseguire una delle operazioni seguenti:
    
      - Per utilizzare un archivio di SQL Server esistente già definito nella topologia, selezionare **Archivio SQL**.
    
      - Per definire una nuova istanza di SQL Server per archiviare le informazioni sul pool, fare clic su **nuovo** e quindi specificare il **nome di dominio completo di SQL Server**nella finestra di dialogo **Definisci nuovo archivio SQL** .
    
      - Per specificare il nome di un'istanza di SQL Server, selezionare **Istanza denominata** e quindi specificare il nome dell'istanza.
    
      - Per utilizzare l'istanza predefinita, fare clic su **Istanza predefinita**.
    
      - Per utilizzare il mirroring SQL, selezionare **Abilita mirroring SQL** e selezionare un'istanza esistente, o creare una nuova istanza.

8.  Nella pagina **Definire condivisione file** eseguire una delle operazioni seguenti:
    
      - Per utilizzare una condivisione file già definita nella topologia, selezionare **Utilizza condivisione file definita in precedenza**.
    
      - Per definire una nuova condivisione file, selezionare **Definisci nuova condivisione file**, nella casella **FQDN file server** immettere l'FQDN del file server esistente in cui deve trovarsi la condivisione file e quindi immettere un nome per la condivisione nella casella **Condivisione file**.
    
    <div>
    

    > [!IMPORTANT]
    > La condivisione file per Lync Server 2013 non può essere posizionata nel front end server. Si noti che in questo esempio la condivisione file è stata posizionata nel server Back End Server basato su SQL Server. Questa posizione può non risultare ottimale per i requisiti dell'organizzazione e un file server può rappresentare una scelta migliore. È possibile definire la condivisione file senza che questa sia stata creata. Sarà necessario creare la condivisione file nella posizione definita prima di pubblicare la topologia.

    
    </div>

9.  Nella pagina **Specificare l'URL dei servizi Web** eseguire una o entrambe le operazioni seguenti:
    
    <div>
    

    > [!IMPORTANT]
    > L'URL di base è l'identità dei servizi Web per l'URL meno https://. Ad esempio, se l'URL completo per i servizi Web del pool è https://pool01.contoso.net , l'URL di base è pool01.contoso.NET.

    
    </div>
    
    <div>
    

    > [!WARNING]
    > Se si dispone di più di un pool Front end o front end server, l'FQDN dei servizi Web esterni deve essere univoco. Ad esempio, se si definisce l'FQDN dei servizi Web esterni di un front end server come <STRONG>pool01.contoso.com</STRONG>, non è possibile utilizzare <STRONG>pool01.contoso.com</STRONG> per un altro pool Front end o front end server.

    
    </div>
    
    1.  Se si sta configurando il bilanciamento del carico DNS, selezionare la casella di controllo **Sostituisci FQDN pool di servizi Web interni** , immettere l'URL di base interno (che deve essere diverso dall'FQDN del pool e potrebbe essere, ad esempio, Internal- \<your base URL\> ) nell' **URL di base interno**.
        
        <div>
        

        > [!WARNING]
        > Se si decide di sostituire i servizi Web interni con un FQDN autodefinito, ogni FQDN deve essere univoco da qualsiasi altro pool Front End, Director o pool di server Director. <STRONG>Utilizzare solo caratteri standard</STRONG> (tra cui a – z, a – z, 0 – 9 e trattini) per la definizione di URL o di nomi di dominio completi. Non utilizzare caratteri Unicode o di sottolineatura. I caratteri non standard in un URL o FQDN spesso non sono supportati dal DNS esterno e dalle CA pubbliche (ovvero, quando l'URL o il nome di dominio completo deve essere assegnato al nome del soggetto o all'oggetto alternativo del soggetto nel certificato).

        
        </div>
    
    2.  Facoltativamente, immettere l'URL di base esterno in **URL di base esterno**. È necessario immettere l'URL di base esterno per differenziarlo dalla denominazione di dominio interno. Si supponga, ad esempio, che il nome di dominio interno sia contoso.net e il nome di dominio esterno sia contoso.com. In questo caso, l'URL verrebbe definito con il nome di dominio contoso.com. Questo è un aspetto importante anche nel caso di un proxy inverso. Il nome di dominio dell'URL di base esterno è lo stesso del nome di dominio dell'FQDN del proxy inverso. La messaggistica istantanea e la presenza richiedono l'accesso HTTP al pool Front end.
    
    <div>
    

    > [!NOTE]
    > Per utilizzare il bilanciamento del carico DNS, è necessario creare i record DNS appropriati. Per ulteriori informazioni, vedere <A href="lync-server-2013-configure-dns-for-load-balancing.md">configurare DNS per il bilanciamento del carico in Lync Server 2013</A>.

    
    </div>

10. Se nella pagina **Selezione funzionalità** è stata selezionata l'opzione servizi di **conferenza** , nella pagina selezionare **un server Office Web Apps** selezionare **Associa pool a un server Office Web Apps** e quindi fare clic su **nuovo** (o selezionare un server Office Web Apps esistente nell'elenco a discesa).

11. Nella finestra di dialogo **Definire un nuovo server Office Web Apps** digitare il nome di dominio completo (FQDN) del computer del server Office Web Apps nella casella **FQDN server Office Web Apps**. L'URL di individuazione del server Office Web Apps dovrebbe comparire così automaticamente nella casella **URL di individuazione server Office Web Apps**.
    
    Se il server Office Web Apps è installato in locale e nella stessa area di rete di Lync Server 2013, il **Server Office Web Apps Option è distribuito in una rete esterna (ovvero perimetro/Internet)** non deve essere selezionata.
    
    Se il server Office Web Apps è distribuito all'esterno del firewall interno, allora selezionare l'opzione **Il server Office Web Apps è distribuito in una rete esterna (perimetro/Internet)**.
    
    <div>
    

    > [!NOTE]
    > Per ulteriori informazioni, vedere <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">configurazione dell'integrazione con Office Web Apps Server e Lync server 2013</A>.

    
    </div>

12. Nella pagina **Definire l'archivio SQL Server per l'archiviazione**, selezionare un'istanza SQL Server esistente, o definire una nuova istanza per l'archiviazione dei dati associati ai dati di archiviazione.

13. Nella pagina **Definire l'archivio SQL Server per il monitoraggio**, selezionare un'istanza SQL Server esistente, o definire una nuova istanza per l'archiviazione dei dati associati ai dati di monitoraggio.

14. Fare clic su **Avanti**. Se sono stati definiti altri server di ruoli nella pagina **associa ruoli server al pool Front End** , verranno aperte le pagine della configurazione guidata ruolo separate che consentono di configurare i ruoli del server. Per ulteriori dettagli, vedere:
    
    [Distribuzione dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-deploying-external-user-access.md)

15. Se non sono stati selezionati altri ruoli del server da configurare e distribuire oppure al termine della configurazione dei ruoli del server aggiuntivi, fare clic su **Fine**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

