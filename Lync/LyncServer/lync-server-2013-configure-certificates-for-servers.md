---
title: 'Lync Server 2013: Configurare i certificati per i server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for servers
ms:assetid: e12e59b5-a146-4859-86ec-cabfc198c7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398995(v=OCS.15)
ms:contentKeyID: 48185531
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 303724fa705fa94e9bbacacb4764bba7b918c460
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-servers-in-lync-server-2013"></a>Configurare i certificati per i server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-03-17_

Per completare correttamente questa procedura, è necessario avere effettuato l'accesso come utente membro del gruppo RTCUniversalServerAdmins o avere le autorizzazioni corrette Delegate. Per informazioni dettagliate sulla delega delle autorizzazioni, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md). A seconda dell'organizzazione e dei requisiti per richiedere i certificati, è possibile che siano necessarie altre appartenenze ai gruppi. Consultarsi con il gruppo che gestisce l'autorità di certificazione (PKI) dell'infrastruttura a chiave pubblica.

<div>


> [!NOTE]  
> Lync Server 2013 include il supporto per la famiglia SHA-2 (SHA-2 usa le lunghezze digest di 224, 256, 384 o 512 bit) dell'hash digest e gli algoritmi di firma per le connessioni dei client che usano Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista o Sistemi operativi Windows XP, oltre a Lync Phone Edition. Per supportare l'accesso esterno tramite la famiglia SHA-2, il certificato esterno viene emesso da un'autorità di certificazione pubblica che può anche emettere un certificato con lo stesso bit length digest.



</div>

<div>


> [!WARNING]  
> La selezione dell'algoritmo di firma e del digest hash dipende dai client e dai server che utilizzeranno il certificato e da altri computer e dispositivi che i client e i server comunicheranno con chi deve anche sapere come usare gli algoritmi usati nella certificato. Per informazioni sulle lunghezze del digest supportate nel sistema operativo e in alcune applicazioni client, vedere<A href="http://go.microsoft.com/fwlink/?linkid=287002">http://go.microsoft.com/fwlink/?LinkId=287002</A>.



</div>

Ogni server Standard Edition o front end server richiede fino a quattro certificati: il certificato oAuthTokenIssuer, un certificato predefinito, un certificato interno Web e un certificato esterno Web. Tuttavia, è possibile richiedere e assegnare un singolo certificato predefinito con le voci di nome alternativo soggetto appropriato e il certificato oAuthTokenIssuer. Per informazioni dettagliate sui requisiti dei certificati, vedere [requisiti per i certificati per i server interni in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md). Per informazioni dettagliate sulla richiesta, l'assegnazione e l'installazione del certificato oAuthTokenIssuer, vedere [gestione dell'autenticazione server-Server (OAuth) e delle applicazioni partner in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

Usare la procedura seguente per richiedere, assegnare e installare il server Standard Edition o i certificati del server front-end. Ripetere la procedura per ogni server front-end.

<div>


> [!IMPORTANT]  
> La procedura seguente descrive come configurare i certificati da una PKI aziendale interna distribuita dall'organizzazione e con l'elaborazione delle richieste offline. Per informazioni su come ottenere certificati da una CA pubblica, vedere <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">requisiti dei certificati per i server interni in Lync Server 2013</A> nella documentazione relativa alla pianificazione. Questa procedura descrive inoltre come richiedere, assegnare e installare i certificati durante la configurazione del server front-end. Se i certificati sono stati richiesti in anticipo, come descritto nella sezione <A href="lync-server-2013-request-certificates-in-advance-optional.md">richieste di certificati in anticipo (facoltativo) per Lync Server 2013</A> di questa documentazione di distribuzione oppure non si usa una PKI aziendale interna distribuita nell'organizzazione per ottenere i certificati, è necessario modificare questa procedura in base alle esigenze.



</div>

<div>

## <a name="to-configure-certificates-for-a-front-end-server"></a>Per configurare i certificati per un server front-end

1.  Nella distribuzione guidata di Lync Server fare clic su **Esegui** accanto al **passaggio 3: richiedere, installare o assegnare certificati**.

2.  Nella pagina **creazione guidata certificato** fare clic su **Richiedi**.

3.  Nella pagina **richiesta certificato** fare clic su **Avanti**.

4.  Nella pagina **richieste immediate o posticipate** è possibile accettare l'impostazione predefinita **Invia immediatamente la richiesta a un'autorità di certificazione online** facendo clic su **Avanti**. La CA interna con registrazione automatica online deve essere disponibile se si seleziona questa opzione. Se si sceglie l'opzione per rinviare la richiesta, verrà chiesto di specificare un nome e un percorso per salvare il file di richiesta del certificato. La richiesta di certificato deve essere presentata ed elaborata da una CA all'interno dell'organizzazione o da una CA pubblica. Sarà quindi necessario importare la risposta del certificato e assegnarla al ruolo di certificato corretto.

5.  Nella pagina **scegliere una autorità di certificazione (CA)** selezionare l'opzione **Seleziona una CA dall'elenco rilevato nell'ambiente** e quindi selezionare una CA nota (tramite registrazione in servizi di dominio Active Directory) nell'elenco. In alternativa, selezionare l'opzione **specifica un'altra autorità di certificazione** , immettere il nome di un'altra CA nella casella e quindi fare clic su **Avanti**.

6.  Nella pagina **account Authority Certificate** vengono chieste le credenziali per richiedere ed elaborare la richiesta di certificato presso la CA. Si sarebbe dovuto determinare se è necessario un nome utente e una password per richiedere un certificato in anticipo. L'amministratore della CA avrà le informazioni necessarie e potrebbe essere necessario per assisterti in questo passaggio. Se è necessario fornire credenziali alternative, selezionare la casella di controllo, specificare un nome utente e una password nelle caselle di testo e quindi fare clic su **Avanti**.

7.  Nella pagina **Specifica modello di certificato alternativo** , per usare il modello predefinito del server Web, fare clic su **Avanti**.
    
    <div>
    

    > [!NOTE]  
    > Se l'organizzazione ha creato un modello da usare come alternativa per il modello di CA del server Web predefinito, selezionare la casella di controllo e quindi immettere il nome del modello alternativo. Sarà necessario il nome del modello definito dall'amministratore della CA.

    
    </div>

8.  Nella pagina **Impostazioni nome e sicurezza** specificare un **nome descrittivo** che consenta di identificare il certificato e lo scopo. Se si lascia vuoto, verrà generato automaticamente un nome. Impostare la **lunghezza del bit** della chiave o accettare l'impostazione predefinita di 2048 bit. Selezionare il **contrassegno della chiave privata del certificato come esportabile** se si determina che il certificato e la chiave privata devono essere spostati o copiati in altri sistemi e quindi fare clic su **Avanti**.
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 offre requisiti minimi per una chiave privata esportabile. Una di queste posizioni si trova negli Edge Server in un pool, in cui il servizio di autenticazione dell'inoltro multimediale USA copie del certificato, invece dei singoli certificati per ogni istanza del pool.

    
    </div>

9.  Nella pagina **informazioni organizzazione** facoltativamente specificare le informazioni sull'organizzazione e quindi fare clic su **Avanti**.

10. Nella pagina **informazioni geografiche** specificare facoltativamente informazioni geografiche e quindi fare clic su **Avanti**.

11. Nella pagina **nome oggetto/nomi oggetto alternativo** esaminare i nomi alternativi oggetto che verranno aggiunti e quindi fare clic su **Avanti**.

12. Nella pagina **Impostazioni dominio SIP** selezionare il **dominio SIP**e quindi fare clic su **Avanti**.

13. Nella pagina **Configura altri nomi alternativi oggetto** aggiungere eventuali nomi alternativi di altri soggetti necessari, inclusi quelli eventualmente necessari per altri domini SIP in futuro e quindi fare clic su **Avanti**.

14. Nella pagina **Riepilogo richiesta di certificato** esaminare le informazioni nel riepilogo. Se le informazioni sono corrette, fare clic su **Avanti**. Se è necessario correggere o modificare un'impostazione, fare clic su **Torna** alla pagina appropriata per apportare la correzione o la modifica.

15. Nella pagina **esecuzione dei comandi** fare clic su **Avanti**.

16. Nella pagina di **stato della richiesta di certificato online** verificare le informazioni restituite. Tenere presente che il certificato è stato emesso e installato nell'archivio certificati locale. Se viene segnalato come rilasciato e installato, ma non è valido, verificare che il certificato radice della CA sia stato installato nell'archivio della CA radice attendibile del server. Vedere la documentazione della CA su come recuperare un certificato CA radice attendibile. Se è necessario visualizzare il certificato recuperato, fare clic su **Visualizza dettagli certificato**. Per impostazione predefinita, la casella di controllo **assegna il certificato agli usi dei certificati di Lync Server** è selezionata. Se si vuole assegnare manualmente il certificato, deselezionare la casella di controllo e quindi fare clic su **fine**.

17. Se è stata deselezionata la casella di controllo **assegna il certificato agli usi dei certificati di Lync Server** nella pagina precedente, verrà visualizzata la pagina **assegnazione certificato** . Fare clic su **Avanti**.

18. Nella pagina **archivio certificati** selezionare il certificato richiesto. Se si vuole visualizzare il certificato, fare clic su **Visualizza dettagli certificato**e quindi su **Avanti** per continuare.
    
    <div>
    

    > [!NOTE]  
    > Se la pagina di <STRONG>stato della richiesta di certificato online</STRONG> segnala un problema con il certificato, ad esempio il certificato non è valido, la visualizzazione del certificato effettivo può aiutare a risolvere il problema. Due problemi specifici che possono causare un certificato non valido sono il certificato della CA radice attendibile mancante menzionato in precedenza e una chiave privata mancante associata al certificato. Fare riferimento alla documentazione della CA per risolvere questi due problemi.

    
    </div>

19. Nella pagina **Riepilogo assegnazione certificati** esaminare le informazioni presentate per verificare che si tratta del certificato da assegnare e quindi fare clic su **Avanti**.

20. Nella pagina **esecuzione dei comandi** esaminare l'output del comando. Fare clic su **Visualizza log** se si vuole rivedere il processo di assegnazione o se è stato emesso un errore o un avviso. Al termine della revisione, fare clic su **fine**.

21. Nella pagina **creazione guidata certificato** verificare che lo **stato** del certificato sia "assegnato", quindi fare clic su **Chiudi**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Requisiti dell'infrastruttura dei certificati per Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

