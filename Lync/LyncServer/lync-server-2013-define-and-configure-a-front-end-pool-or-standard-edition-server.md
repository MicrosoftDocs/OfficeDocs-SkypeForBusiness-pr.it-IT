---
title: Definire e configurare un pool Front End o un server Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define and configure a Front End pool or Standard Edition server
ms:assetid: 713fc263-23dd-414a-b001-82932e4fe966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398538(v=OCS.15)
ms:contentKeyID: 48184457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ac840cb40da71f81a24501f3d9caa53fb316e86
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a>Definire e configurare un pool Front End o un server Standard Edition in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-03-08_

Questa procedura non richiede l'appartenenza a un amministratore locale o a un gruppo di domini privilegiati. È necessario accedere a un computer come utente standard.

Se si distribuisce un server aziendale, è necessario che un numero minimo di server front-end in un pool sia sempre in uso. Nella tabella seguente vengono riepilogati questi requisiti.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Numero totale di server front-end nel pool</th>
<th>Numero di server che devono essere in uso per il pool per essere funzionali</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1-2</p></td>
<td><p>1</p></td>
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
<td><p>4</p></td>
</tr>
<tr class="odd">
<td><p>9-10</p></td>
<td><p>5</p></td>
</tr>
<tr class="even">
<td><p>11-12</p></td>
<td><p>6</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> Per Lync Server 2013 ogni volta che si aggiunge o si rimuove un server front-end dal pool, è necessario riavviare i servizi. La rimozione e l'aggiunta di server devono essere eseguite come operazioni separate. Se ad esempio si vuole aggiungere due server front-end e rimuovere due server front-end, usare il processo seguente: 
> <OL>
> <LI>
> <P>Rimuovere i due server front-end.</P>
> <LI>
> <P>Pubblicare e riattivare la topologia.</P>
> <LI>
> <P>Riavviare i servizi</P>
> <LI>
> <P>Aggiungere i due server front-end.</P>
> <LI>
> <P>Pubblicare e riattivare la topologia.</P>
> <LI>
> <P>Riavviare i servizi.</P></LI></OL>



</div>

Dopo avere definito la topologia, usare la procedura seguente per definire un pool Front-end per il sito. Per informazioni dettagliate sulla definizione della topologia, vedere [definire e configurare una topologia in Generatore di topologie per Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).

<div>

## <a name="to-define-a-front-end-pool"></a>Per definire un pool Front-End

1.  Nella procedura guidata Definisci nuovo pool, nella pagina **Definisci il nuovo pool di front-end** fare clic su **Avanti**.

2.  Nella pagina **Definisci il** nome di dominio completo del pool di front-end immettere un FQDN (Fully Qualified Domain Name) per il pool da creare, fare clic su **pool Enterprise Edition front-end**e quindi fare clic su **Avanti**.

3.  Nella pagina **Definisci i computer in questo pool** immettere un nome di dominio completo del computer per il primo server front-end nel pool e quindi fare clic su **Aggiungi**. Ripetere questo passaggio per tutti i computer aggiuntivi (fino a dodici) che si desidera aggiungere al pool e quindi fare clic su **Avanti**.

4.  Nella pagina **selezionare le caratteristiche** selezionare le caselle di controllo relative alle caratteristiche desiderate in questo pool di front-end. Ad esempio, se si stanno distribuendo solo le funzionalità di messaggistica istantanea e presenza, è necessario selezionare la casella di controllo **conferenza** per consentire la messaggistica istantanea in più parti, ma non selezionare le caselle di controllo per i servizi di conferenza telefonica con **accesso esterno**, **VoIP aziendale**o di **ammissione alle chiamate** , perché rappresentano le caratteristiche di conferenza telefonica vocale, video e collaborazione.
    
      - **Conferenza**   questa selezione consente di creare una vasta gamma di funzionalità, tra cui:
        
          - Messaggistica istantanea con più di due parti in una sessione di messaggistica istantanea.
        
          - Servizi di conferenza, che includono la collaborazione tra documenti, la condivisione delle applicazioni e la condivisione desktop.
        
          - A/V Conferencing, che consente agli utenti di avere conferenze audio/video (A/V) in tempo reale senza la necessità di servizi esterni, come il servizio Live Meeting o un bridge audio di terze parti.
    
      - **Le conferenze**   telefoniche con accesso esterno (PSTN) consentono agli utenti di partecipare alla parte audio di una conferenza di Lync Server 2013 usando un telefono PSTN (Public Switched Telephone Network) senza richiedere un provider di servizi di audioconferenza.
    
      - **Enterprise Voice**   Enterprise Voice è la soluzione VoIP (Voice over IP) in Lync Server 2013 che consente agli utenti di effettuare e ricevere chiamate telefoniche. Questa funzionalità verrà distribuita se si prevede di usare Lync Server 2013 per le chiamate vocali, la segreteria telefonica e altre funzioni che usano un dispositivo hardware o un client software.
    
      - **Controllo di ammissione di chiamata (CAC)**   CAC determina, in base alla larghezza di banda della rete disponibile, se consentire la creazione di sessioni di comunicazioni in tempo reale, ad esempio chiamate vocali o videochiamate. Se è stata distribuita solo la messaggistica istantanea e la presenza, il CAC non è necessario perché nessuna delle due caratteristiche USA CAC.
    
      - **L'archiviazione dell'**   archiviazione consente di archiviare il contenuto di messaggistica istantanea, i contenuti di conferenza (riunione) o entrambi inviati tramite Lync Server 2013.
    
      - **Il monitoraggio**   del server di monitoraggio consente di raccogliere dati numerici che descrivono la qualità multimediale della rete e degli endpoint, le informazioni sull'utilizzo relative alle chiamate VoIP, i messaggi istantanei, le conversazioni a/V, le riunioni, la condivisione delle applicazioni e i trasferimenti di file e le informazioni sulla risoluzione dei problemi per le chiamate non riuscite.
    
    <div>
    

    > [!NOTE]
    > Se si vuole abilitare CAC nella distribuzione, è necessario abilitare CAC in un unico pool per ogni sito centrale. Il comando CAC è consigliato se si distribuiscono le funzionalità vocali o i servizi di conferenza A/V.

    
    </div>
    
    La tabella seguente mostra le funzionalità disponibili (inizio) e le funzioni offerte agli utenti (a sinistra). Le selezioni nella tabella sono quelle da selezionare per abilitare tali funzionalità per l'organizzazione.
    
    
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
    <th>Servizi di conferenza</th>
    <th>Servizi di conferenza telefonica con accesso esterno</th>
    <th>VoIP aziendale</th>
    <th>Controllo ammissione chiamata</th>
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
    <td><p>Servizi di conferenza</p></td>
    <td><p>X</p></td>
    <td><p>X</p></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="odd">
    <td><p>Servizi di conferenza A/V</p></td>
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


5.  Nella pagina **Selezione ruoli server collocato** è possibile collocare il Mediation Server nel server front-end o distribuirlo come server autonomo.
    
    È possibile collocare il Mediation Server nel pool Front-end.
    
      - Se si intende collocare il Mediation Server nel pool Enterprise Edition front-end, verificare che la casella di controllo sia selezionata. Il ruolo del server verrà distribuito nei server del pool.
    
      - Se si intende distribuire il server di mediazione come server autonomo, deselezionare la casella di controllo appropriata. Si distribuirà Mediation Server in un passaggio di distribuzione distinto dopo la distribuzione completa del server front-end.
    
    <div>
    

    > [!NOTE]
    > È consigliabile collocare il Mediation Server, se possibile. Per informazioni dettagliate sul supporto per i server di mediazione collocati o autonomi, vedere <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">componenti e topologie per Mediation Server in Lync server 2013</A> nella documentazione relativa alla pianificazione.

    
    </div>

6.  I **ruoli del server associato con questa pagina del pool Front-End** consentono di definire e associare i ruoli del server al pool Front-end. Il ruolo seguente è disponibile:
    
    **Abilitare un pool**   Edge definisce e associa un singolo Edge Server o un pool di Edge Server. Un Edge Server facilita la comunicazione e la collaborazione tra gli utenti all'interno dell'organizzazione e le persone esterne all'organizzazione, inclusi gli utenti federati.
    
    Esistono due scenari possibili che è possibile usare per distribuire e associare i ruoli del server:
    
    Per scenario uno, si sta definendo una nuova topologia per una nuova installazione. Puoi avvicinarti all'installazione in uno dei due modi seguenti:
    
      - Uscire dalla casella di controllo e procedere con la definizione della topologia. Dopo aver pubblicato, configurato e testato i ruoli del server front-end e back-end, è possibile eseguire di nuovo il generatore di topologia per aggiungere i server dei ruoli alla topologia. Questa strategia consentirà di testare il pool Front end e il server che eseguirà SQL Server senza ulteriori complicazioni da ruoli aggiuntivi. Dopo aver completato il test iniziale, è possibile eseguire di nuovo il generatore di topologia per selezionare i ruoli che è necessario distribuire.
    
      - Selezionare i ruoli che è necessario installare e quindi configurare l'hardware in grado di ospitare i ruoli selezionati.
    
    Per lo scenario due è disponibile una distribuzione esistente e l'infrastruttura è pronta per i nuovi ruoli oppure è necessario associare i ruoli esistenti a un nuovo server front-end:
    
      - In questo caso, selezionare i ruoli che si desidera distribuire o associare al nuovo server front-end. In entrambi i casi, procedere con la definizione dei ruoli, configurare l'hardware necessario e procedere con l'installazione.

7.  Nella pagina **Definisci l'archivio SQL** eseguire una delle operazioni seguenti:
    
      - Per usare un archivio di SQL Server esistente già definito nella topologia, selezionare un'istanza da **SQL Store**.
    
      - Per definire una nuova istanza di SQL Server per archiviare le informazioni sul pool, fare clic su **nuovo** e quindi specificare il **nome di dominio completo di SQL Server**nella finestra di dialogo **Definisci nuovo archivio SQL** .
    
      - Per specificare il nome di un'istanza di SQL Server, selezionare **istanza denominata**e quindi specificare il nome dell'istanza.
    
      - Per usare l'istanza predefinita, fare clic su **istanza predefinita**.
    
      - Per usare il mirroring SQL, selezionare **Abilita il mirroring SQL** e selezionare un'istanza esistente o creare una nuova istanza.

8.  Nella pagina **Definisci la condivisione file** eseguire una delle operazioni seguenti:
    
      - Per usare una condivisione file già definita nella topologia, selezionare **Usa una condivisione file definita in precedenza**.
    
      - Per definire una nuova condivisione file, selezionare **Definisci una nuova condivisione file**, nella casella **FQDN file server** immettere il nome di dominio completo del file server esistente in cui si trova la condivisione file e quindi immettere un nome per la condivisione file nella casella **condivisione file** .
    
    <div>
    

    > [!IMPORTANT]
    > La condivisione file per Lync Server 2013 non può essere posizionata nel server front-end. Si noti che in questo esempio la condivisione file si trova nel server back-end basato su SQL Server. Potrebbe non essere una posizione ottimale per i requisiti dell'organizzazione e un file server potrebbe essere una scelta migliore. È possibile definire la condivisione file senza che la condivisione file sia stata creata. Sarà necessario creare la condivisione file nella posizione definita prima di pubblicare la topologia.

    
    </div>

9.  Nella pagina **specificare l'URL dei servizi Web** eseguire una o entrambe le operazioni seguenti:
    
    <div>
    

    > [!IMPORTANT]
    > L'URL di base è l'identità dei servizi Web per l'URL, meno il https://. Ad esempio, se l'URL completo per i servizi Web del pool è https://pool01.contoso.net, l'URL di base è pool01.contoso.NET.

    
    </div>
    
    <div>
    

    > [!WARNING]
    > Se si dispone di più di un pool Front-end o di un server front-end, l'FQDN dei servizi Web esterni deve essere univoco. Se ad esempio si definisce il nome di dominio completo dei servizi Web esterni di un front end server come <STRONG>pool01.contoso.com</STRONG>, non è possibile usare <STRONG>pool01.contoso.com</STRONG> per un altro pool Front-end o front end server.

    
    </div>
    
    1.  Se si sta configurando il bilanciamento del carico DNS, selezionare la casella di controllo **Sostituisci il nome completo del pool di servizi Web interni** , immettere l'URL di base interno (che deve essere diverso dall'FQDN del\<pool e potrebbe\>essere, ad esempio, l'URL di base interno) nell' **URL di base interno**.
        
        <div>
        

        > [!WARNING]
        > Se si decide di ignorare i servizi Web interni con un nome di dominio completo definito autonomamente, ogni nome di dominio completo deve essere univoco da qualsiasi altro pool di front-end, direttore o pool di Director. Quando si definiscono URL o nomi di dominio completi, <STRONG>usare solo caratteri standard</STRONG> (tra cui a-z, a-z, 0-9 e segni meno). Non usare caratteri Unicode o carattere di sottolineatura. I caratteri non standard in un URL o FQDN spesso non sono supportati dal DNS esterno e dalle CA pubbliche, ovvero quando l'URL o il nome di dominio completo deve essere assegnato al nome dell'oggetto o all'oggetto alternativo nel certificato.

        
        </div>
    
    2.  Facoltativamente, immettere l'URL della base esterna nell' **URL di base esterno**. Si immetterebbe l'URL della base esterna per differenziarlo dalla denominazione interna del dominio. Ad esempio, il dominio interno è contoso.net, ma il nome di dominio esterno è contoso.com. Definiresti l'URL usando il nome di dominio contoso.com. Questo è importante anche nel caso di un proxy inverso. Il nome di dominio dell'URL di base esterno corrisponde al nome di dominio dell'FQDN del proxy inverso. La messaggistica istantanea e la presenza richiedono l'accesso HTTP al pool Front-end.
    
    <div>
    

    > [!NOTE]
    > Per usare il bilanciamento del carico DNS, è necessario creare i record DNS appropriati. Per informazioni dettagliate, vedere <A href="lync-server-2013-configure-dns-for-load-balancing.md">configurare il DNS per il bilanciamento del carico in Lync Server 2013</A>.

    
    </div>

10. Se è stata selezionata l'opzione servizi di **conferenza** nella pagina **Seleziona funzionalità** , nella pagina **selezionare un server di Office Web Apps** selezionare **Associa pool a un server di Office Web Apps** e quindi fare clic su **nuovo** (o selezionare un server di Office Web Apps esistente nell'elenco a discesa).

11. Nella finestra di dialogo **Definisci nuovo server Office Web Apps** Digitare il nome di dominio completo (FQDN) del computer Office Web Apps Server nella casella **FQDN server di Office Web Apps** . Quando si esegue questa operazione, l'URL di individuazione del server di Office Web Apps deve essere automaticamente immesso nella casella **URL individuazione server di Office Web Apps** .
    
    Se il server Office Web Apps è installato in locale e nella stessa area di rete di Lync Server 2013, l'opzione **Office Web Apps Server è distribuita in una rete esterna, ovvero perimetro/Internet,** non deve essere selezionata.
    
    Se il server Office Web Apps è distribuito all'esterno del firewall interno, selezionare l'opzione **Office Web Apps Server è distribuito in una rete esterna (ovvero perimetro/Internet)**.
    
    <div>
    

    > [!NOTE]
    > Per informazioni dettagliate, vedere <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">configurazione dell'integrazione con Office Web Apps Server e Lync server 2013</A>.

    
    </div>

12. Nella pagina **Definisci archiviazione SQL Store** selezionare un'istanza o un server SQL esistente oppure definire una nuova istanza per archiviare i dati associati ai dati di archiviazione.

13. Nella pagina **Definisci il monitoraggio dell'archivio SQL** selezionare un'istanza o un server SQL esistente oppure definire una nuova istanza per archiviare i dati associati al monitoraggio dei dati.

14. Fare clic su **Avanti**. Se sono stati definiti altri server di ruoli nei **ruoli del server associato con questa pagina del pool Front-End** , le pagine della configurazione guidata ruolo separato verranno aperte per consentire la configurazione dei ruoli del server. Per informazioni dettagliate, vedere quanto segue:
    
    [Distribuzione dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-deploying-external-user-access.md)

15. Se non è stato selezionato ruoli server aggiuntivi per la configurazione e la distribuzione oppure quando è stata completata l'installazione di altri server dei ruoli, fare clic su **fine**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

