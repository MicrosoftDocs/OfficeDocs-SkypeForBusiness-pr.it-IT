---
title: 'Lync Server 2013: configurare i certificati per i server'
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
ms.openlocfilehash: 3556c9147ddf2769e6a403de9e31edf31129d796
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-servers-in-lync-server-2013"></a>Configurare i certificati per i server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-17_

Per eseguire questa procedura, è necessario accedere come utente membro del gruppo RTCUniversalServerAdmins o disporre della delega delle autorizzazioni appropriate. Per informazioni dettagliate su come delegare le autorizzazioni, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md). A seconda dell'organizzazione e dei requisiti per la richiesta dei certificati, potrebbe essere necessario appartenere ad altri gruppi. Rivolgersi al gruppo che gestisce l'Autorità di certificazione (CA) dell'infrastruttura a chiave pubblica (PKI).

<div>


> [!NOTE]  
> Lync Server 2013 include il supporto per la famiglia SHA-2 (SHA-2 utilizza la lunghezza del digest di 224, 256, 384 o 512 bit) dell'hash digest e gli algoritmi di firma per le connessioni dai client che eseguono Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista o Sistemi operativi Windows XP, oltre a Lync Phone Edition. Per supportare l'accesso esterno tramite la famiglia SHA-2, il certificato esterno viene emesso da un'autorità di certificazione pubblica che può anche emettere un certificato con lo stesso bit di lunghezza del digest.



</div>

<div>


> [!WARNING]  
> La selezione dell'algoritmo di firma e del digest hash dipende dai client e dai server che utilizzeranno il certificato e da altri computer e dispositivi che i client e i server comunicheranno con gli utenti che devono anche sapere come utilizzare gli algoritmi utilizzati nell' certificato. Per informazioni su quali lunghezze del digest sono supportate nel sistema operativo e in alcune applicazioni client<A href="https://go.microsoft.com/fwlink/?linkid=287002">https://go.microsoft.com/fwlink/?LinkId=287002</A>, vedere.



</div>

Ogni server Standard Edition o front end server richiede fino a quattro certificati: il certificato oAuthTokenIssuer, un certificato predefinito, un certificato interno Web e un certificato esterno Web. È tuttavia possibile richiedere e assegnare un singolo certificato predefinito con voci appropriate del nome alternativo del soggetto, nonché il certificato oAuthTokenIssuer. Per informazioni dettagliate sui requisiti dei certificati, vedere [requisiti dei certificati per i server interni in Lync server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md). Per informazioni dettagliate sulla richiesta, l'assegnazione e l'installazione del certificato oAuthTokenIssuer, vedere [Managing server-to-Server Authentication (OAuth) and partner Applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

Utilizzare la procedura seguente per richiedere, assegnare e installare il server Standard Edition o i certificati del server front end. Ripetere la procedura per ogni Front End Server.

<div>


> [!IMPORTANT]  
> Nella procedura seguente viene illustrato come configurare i certificati di un'infrastruttura a chiave pubblica interna distribuita dall'organizzazione e con l'elaborazione delle richieste offline. Per informazioni su come ottenere certificati da un'autorità di certificazione pubblica, vedere <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Certificate Requirements for Internal Servers in Lync server 2013</A> nella documentazione relativa alla pianificazione. Inoltre, in questa procedura viene descritto come richiedere, assegnare e installare i certificati durante la configurazione del front end server. Se sono stati richiesti in anticipo i certificati, come descritto nella sezione <A href="lync-server-2013-request-certificates-in-advance-optional.md">richiesta certificati in anticipo (facoltativo) per Lync Server 2013</A> della documentazione relativa alla distribuzione o non si utilizza un'infrastruttura PKI aziendale interna distribuita nell'organizzazione per ottenere i certificati, è necessario modificare questa procedura in base alle esigenze.



</div>

<div>

## <a name="to-configure-certificates-for-a-front-end-server"></a>Per configurare i certificati per un Front End Server

1.  Nella distribuzione guidata di Lync Server, fare clic su **Esegui** accanto a **passaggio 3: richiesta, installazione o assegnazione dei certificati**.

2.  Nella pagina **Configurazione guidata certificati** fare clic su **Richiesta**.

3.  Nella pagina **Richiesta di certificato** fare clic su **Avanti**.

4.  Nella pagina **Richieste immediate o ritardate** è possibile accettare l'opzione predefinita **Invia immediatamente la richiesta a un'autorità di certificazione online** facendo clic su **Avanti**. Se si seleziona questa opzione, deve essere disponibile la CA interna con registrazione automatica online. Se si sceglie l'opzione di ritardare la richiesta, sarà necessario specificare un nome e un percorso in cui salvare il file di richiesta di certificato. La richiesta di certificato deve essere presentata ed elaborata da una CA all'interno dell'organizzazione o da una CA pubblica. Sarà quindi necessario importare il certificato di risposta e assegnarlo al ruolo appropriato.

5.  Nella pagina **scegliere un'autorità di certificazione (CA)** selezionare l'opzione **Seleziona una CA dall'elenco rilevato nell'ambiente in uso** e quindi selezionare una CA nota (tramite registrazione in servizi di dominio Active Directory) dall'elenco. In alternativa, selezionare l'opzione **Specifica un'altra autorità di certificazione**, immettere il nome di un'altra CA e quindi fare clic su **Avanti**.

6.  Nella pagina **Account autorità di certificazione** viene richiesto di immettere le credenziali per richiedere ed elaborare la richiesta di certificato per la CA. Stabilire se è necessario specificare un nome utente e una password per richiedere un certificato in anticipo. L'amministratore della CA dispone delle informazioni necessarie per poter assistere l'utente in questo passaggio. Se è necessario fornire credenziali alternative, selezionare la casella di controllo, specificare il nome utente e la password nelle caselle di testo, quindi fare clic su **Avanti**.

7.  Nella pagina **Specifica modello di certificato alternativo** fare clic su **Avanti** per utilizzare il modello Server Web predefinito.
    
    <div>
    

    > [!NOTE]  
    > Se l'organizzazione ha creato un modello da utilizzare come alternativa al modello Server Web predefinito della CA, selezionare la casella di controllo, quindi immettere il nome del modello alternativo. È necessario specificare il nome del modello come definito dall'amministratore della CA.

    
    </div>

8.  Nella pagina **Impostazioni nome e sicurezza** specificare un valore in **Nome descrittivo** per consentire di identificare il certificato e lo scopo. Se questo campo viene lasciato vuoto, verrà generato automaticamente un nome. Impostare il valore **Lunghezza in bit** della chiave o accettare il valore predefinito di 2048 bit. Selezionare l'opzione **Contrassegna come esportabile la chiave di certificato privata** se è necessario spostare o copiare la chiave privata in altri sistemi, quindi fare clic su **Avanti**.
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 ha requisiti minimi per una chiave privata esportabile. La chiave viene esportata nei server perimetrali di un pool, dove il servizio di autenticazione del Media Relay utilizza copie del certificato anziché i singoli certificati per ogni istanza nel pool.

    
    </div>

9.  Nella pagina **Informazioni sull'organizzazione** immettere facoltativamente le informazioni sull'organizzazione e quindi fare clic su **Avanti**.

10. Nella pagina **Dati geografici** specificare facoltativamente i dati geografici e quindi fare clic su **Avanti**.

11. Nella pagina **Nome soggetto / Nomi soggetto alternativi** verificare i nomi soggetto alternativi che verranno aggiunti e quindi fare clic su **Avanti**.

12. Nella pagina **Impostazione del dominio SIP** selezionare la casella di controllo **Dominio SIP** e quindi fare clic su **Avanti**.

13. Nella pagina **Configura nomi soggetto alternativi aggiuntivi** aggiungere eventuali nomi soggetto alternativi aggiuntivi necessari, inclusi quelli potranno essere richiesti in futuro per i domini SIP aggiuntivi, quindi fare clic su **Avanti**.

14. Nella pagina **Riepilogo richiesta certificato** esaminare le informazioni. Se sono corrette, fare clic su **Avanti**. Se è necessario correggere o modificare un'impostazione, fare clic su **Indietro** fino alla pagina appropriata.

15. Nella pagina **Esecuzione comandi in corso** fare clic su **Avanti**.

16. Nella pagina On the **Stato richiesta di certificato online** esaminare le informazioni restituite. Verificare che il certificato sia stato emesso e installato nell'archivio certificati locale. Se viene segnalato come emesso e installato, ma non è valido, verificare che il certificato radice della CA sia stato installato nell'archivio CA radice attendibile del server. Per informazioni su come recuperare un certificato di CA radice attendibile, consultare la documentazione sulla CA. Se è necessario visualizzare il certificato recuperato, fare clic su **Visualizza dettagli certificato**. Per impostazione predefinita, la casella di controllo **Assegnare il certificato restituito agli utilizzi di Lync Server sul server**. Se si desidera assegnare manualmente il certificato, deselezionare la casella di controllo e quindi fare clic su **Fine**.

17. Se nella pagina precedente è stata deselezionata la casella di controllo **Assegnare il certificato restituito agli utilizzi di Lync Server sul server**, verrà visualizzata la pagina **Assegnazione certificato**. Fare clic su **Avanti**.

18. Nella pagina **Archivio certificati** selezionare il certificato richiesto. Se si desidera visualizzarlo, fare clic su **Visualizza dettagli certificato** e quindi su **Avanti** per continuare.
    
    <div>
    

    > [!NOTE]  
    > Se nella pagina <STRONG>Stato richiesta di certificato online</STRONG> viene segnalato un problema con il certificato, ad esempio che non è valido, la visualizzazione del certificato effettivo può consentire di risolverlo. In particolare, il certificato può non essere valido perché non è stato emesso da una CA radice attendibile, come accennato in precedenza, oppure perché non è associato a una chiave privata. Per risolvere questi due problemi, consultare la documentazione della CA.

    
    </div>

19. Nella pagina **Riepilogo assegnazione certificato** esaminare le informazioni presentate per assicurarsi che si tratta del certificato da assegnare e quindi fare clic su **Avanti**.

20. Nella pagina **Esecuzione comandi in corso** esaminare l'output del comando. Fare clic su **Visualizza registro** se si desidera rivedere il processo di assegnazione oppure se è stato generato un messaggio di errore o di avviso. Al termine, fare clic su **Fine**.

21. Nella pagina **Configurazione guidata certificati** verificare che lo **Stato** dei certificato sia "Assegnato" e quindi fare clic su **Chiudi**.

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

