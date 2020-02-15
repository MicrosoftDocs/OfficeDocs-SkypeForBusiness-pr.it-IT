---
title: Configurare il gateway XMPP in Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: c70282e0-b502-47e2-a0be-a32eb1faf99d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721881(v=OCS.15)
ms:contentKeyID: 49733816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5d75f2e52daed2968d264a2a3eef1bf16bc35b1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a>Configurare il gateway XMPP in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-10-28_

I passaggi finali per la migrazione del gateway XMPP sono la configurazione dei certificati per il server perimetrale di Lync Server 2013, la distribuzione del gateway XMPP di Lync Server 2013 e l'aggiornamento dei record DNS per il gateway XMPP. Queste operazioni devono essere eseguite in parallelo per ridurre al minimo il tempo di inattività del gateway XMPP. Prima di eseguire questa procedura, è necessario spostare tutti gli utenti nella distribuzione di Microsoft Lync Server 2013.

<div class=" ">


> [!IMPORTANT]  
> La Federazione XMPP non è supportata per gli utenti ospitati in Survivable Branch Appliance. Ciò vale sia per la visualizzazione delle informazioni sulla presenza che per lo scambio di messaggi di messaggistica istantanea.



</div>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a>Configurare i certificati del gateway XMPP nel server perimetrale Lync Server 2013

1.  Nel server perimetrale fare clic su **Riesegui** nella Distribuzione guidata accanto a **Passaggio 3: Richiesta, installazione o assegnazione dei certificati**.
    
    <div class=" ">
    

    > [!TIP]  
    > Se si distribuisce il server perimetrale per la prima volta, sarà disponibile il pulsante Esegui anziché Riesegui.

    
    </div>

2.  Nella pagina **Attività certificato disponibili** fare clic su **Crea una nuova richiesta di certificato**.

3.  Nella pagina **Richiesta di certificato** fare clic su **Certificato perimetro esterno**.

4.  Nella pagina **Richieste immediate o ritardate** selezionare la casella di controllo **Prepara la richiesta per l'invio posticipato**.

5.  Nella pagina **file richiesta di certificato** Digitare il percorso completo e il nome del file in cui deve essere salvata la richiesta (ad esempio, c:\\CERT\_esterni\_Edge. cer).

6.  Nella pagina **Specifica modello di certificato alternativo**, per utilizzare un modello diverso dal modello Web Server predefinito selezionare la casella di controllo **Utilizza modello di certificato alternativo per l'autorità di certificazione selezionata**.

7.  Nella pagina **Impostazioni nome e sicurezza** eseguire le operazioni seguenti:
    
    1.  In **Nome descrittivo** digitare un nome visualizzato per il certificato.
    
    2.  In **Lunghezza bit** specificare la lunghezza in bit (in genere il valore predefinito 2048).
    
    3.  Verificare che la casella di controllo **Contrassegna come esportabile la chiave di certificato privata** sia selezionata.

8.  Nella pagina **Informazioni sull'organizzazione** digitare il nome dell'organizzazione e dell'unità organizzativa, ad esempio una divisione o un reparto.

9.  Nella pagina **Dati geografici** specificare le informazioni sulla posizione.

10. Nella pagina **Nome soggetto / Nomi soggetto alternativi** verranno visualizzate le informazioni compilate automaticamente dalla procedura guidata. Se sono necessari ulteriori nomi alternativi soggetto, specificarli nei prossimi due passaggi.

11. Nella pagina **impostazione dominio SIP su nomi soggetto alternativi (San)** selezionare la casella di controllo Domain per aggiungere un SIP. \<voce\> SipDomain all'elenco dei nomi alternativi del soggetto.

12. Nella pagina **Configura nomi alternativi soggetto aggiuntivi** specificare eventuali nomi alternativi del soggetto aggiuntivi necessari.
    
    <div class=" ">
    

    > [!TIP]  
    > Se è installato il proxy XMPP, per impostazione predefinita le voci SAN vengono popolate con il nome di dominio, ad esempio contoso.com. Se sono necessarie ulteriori voci, aggiungerle in questo passaggio.

    
    </div>

13. Nella pagina **Riepilogo richiesta** esaminare le informazioni sul certificato da utilizzare per generare la richiesta.

14. Dopo l'esecuzione del comando, è possibile scegliere **Visualizza Log** oppure fare clic su Avanti per continuare.

15. Nella pagina **File richiesta di certificato** è possibile visualizzare il file di richiesta di firma del certificato (CSR) generato facendo clic su **Visualizza** oppure uscire dalla Configurazione guidata certificati facendo clic su **Fine**.

16. Copiare il file di richiesta e inviarlo all'autorità di certificazione pubblica.

17. Dopo aver ricevuto, importato e assegnato il certificato pubblico, è necessario arrestare e riavviare i servizi del server perimetrale. A tale scopo, digitare quanto segue nella console di gestione di Lync Server:
    
        Stop-CsWindowsService

      &nbsp;
    
        Start-CsWindowsService

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a>Configurare un nuovo gateway XMPP di Lync Server 2013

1.  Aprire il Pannello di controllo di Lync Server.

2.  Sulla barra di spostamento sinistra fare clic su **Federazione e accesso esterno** e quindi su **Partner federati XMPP**.

3.  Per creare una nuova configurazione, fare clic su **Nuovo**.

4.  Definire le impostazioni seguenti:

5.  **Dominio primario (**     obbligatorio). Il dominio primario è il dominio di base del partner XMPP. Ad esempio, è necessario immettere **fabrikam.com** per il nome di dominio del partner XMPP. Questa voce è obbligatoria.

6.  **Descrizione**   la descrizione è relativa alle note o ad altre informazioni di identificazione per la configurazione specifica. Questa voce è facoltativa.

7.  **Domini aggiuntivi**   ulteriori domini sono domini che fanno parte del dominio del partner XMPP che deve essere incluso come parte della comunicazione XMPP consentita. Se ad esempio il dominio primario è **fabrikam.com**, sarà necessario elencare tutti gli altri domini inclusi in fabrikam.com con cui si comunicherà mediante XMPP.

8.  **Tipo di partner**   il **tipo di partner** è un'impostazione obbligatoria. È necessario selezionare una delle opzioni seguenti per descrivere e applicare i contatti che possono essere aggiunti. È possibile selezionare le opzioni seguenti:
    
      - **Federata**   un tipo di partner **federato** rappresenta un livello elevato di attendibilità tra la distribuzione di Lync Server e il partner XMPP.Questo tipo di partner è consigliato per la federazione con i server XMPP della stessa azienda o in scenari di rapporti professionali consolidati.I contatti XMPP nei partner federati possono eseguire le operazioni seguenti:
        
        1.  Aggiungere contatti Lync e visualizzare le relative informazioni sulla presenza senza autorizzazione esplicita da parte dell'utente Lync.
        
        2.  Inviare messaggi istantanei a contatti Lync indipendentemente dal fatto che siano stati aggiunti nell'elenco contatti dell'utente Lync.
        
        3.  Visualizzare le note sullo stato di un utente Lync.
    
      - **Public Verified**   un partner **verificato** pubblico è un provider XMPP pubblico che è attendibile per verificare l'identità dei propri utenti.I contatti XMPP nelle reti di tipo Verificato pubblico possono aggiungere contatti Lync, visualizzare le relative informazioni sulla presenza e inviare loro messaggi istantanei senza autorizzazione esplicita degli utenti Lync.I contatti XMPP nelle reti di tipo Verificato pubblico non visualizzano mai le note sullo stato di un utente Lync.Questa impostazione non è consigliata.
    
      - **Pubblico non verificato**   un partner **pubblico non verificato** è un provider XMPP pubblico che non è attendibile per verificare l'identità dei propri utenti.Gli utenti XMPP delle reti di tipo Non verificato pubblico non possono comunicare con gli utenti Lync a meno che non siano stati esplicitamente autorizzati dall'utente Lync con l'aggiunta nell'elenco contatti.Gli utenti XMPP nelle reti di tipo Non verificato pubblico non visualizzano mai le note sullo stato degli utenti Lync.Questa impostazione è consigliata per le federazioni con provider XMPP pubblici come Google Talk.

9.  **Tipo di connessione** Consente di definire le diverse regole e impostazioni di dialback.
    
      - **La negoziazione**   TLS definisce le regole di negoziazione TLS. Un servizio XMPP può richiedere la negoziazione TLS, può definirla come facoltativa oppure l'utente può specificare che la negoziazione TLS non è supportata. Se si seleziona Facoltativa, l'eventuale obbligatorietà della negoziazione viene decisa dal servizio XMPP. Per visualizzare tutte le impostazioni e i dettagli possibili per la negoziazione SASL, TLS e richiamata, incluse le configurazioni degli errori non valide e note, vedere [impostazioni di negoziazione per i partner federati XMPP in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).
        
          - <span></span>  
            **Required**   il servizio XMPP richiede la negoziazione TLS.
        
          - <span></span>  
            **Facoltativo**   il servizio XMPP indica che TLS è obbligatorio per la negoziazione.
        
          - <span></span>  
            **Non supportato**   il servizio XMPP non supporta TLS.
    
      - **La negoziazione**   SASL Definisce le regole di negoziazione SASL. Un servizio XMPP può richiedere la negoziazione SASL, può definirla come facoltativa oppure l'utente può specificare che la negoziazione SASL non è supportata. Se si seleziona Facoltativa, l'eventuale obbligatorietà della negoziazione viene decisa dal servizio XMPP del partner.
        
          - <span></span>  
            **Required**   il servizio XMPP richiede la negoziazione SASL.
        
          - <span></span>  
            **Facoltativo**   il servizio XMPP indica che SASL è obbligatorio per la negoziazione.
        
          - <span></span>  
            **Non supportato**   il servizio XMPP non supporta SASL.
    
      - **Negoziazione richiamata del server di supporto** Il processo di negoziazione del server di supporto richiamata utilizza il DNS (Domain Name System) e un server autorevole per verificare che la richiesta provenisse da un partner XMPP valido. A tale scopo, il server di origine crea un messaggio di un tipo specifico con una chiave richiamata generata e cerca il server di ricezione in DNS. Il server di origine invia la chiave in un flusso XML alla ricerca DNS risultante, presumibilmente il server di ricezione. Al ricevimento della chiave tramite il flusso XML, il server di ricezione non risponde al server di origine, ma invia la chiave a un server autorevole noto. Il server autorevole verifica che la chiave sia valida o non valida. Se non è valido, il server di ricezione non risponde al server di origine. Se la chiave è valida, il server di ricezione informa il server di origine che l'identità e la chiave sono valide e che la conversazione può iniziare.
        
        Sono disponibili due stati validi per la negoziazione di tipo **Dialback**:
        
          - <span></span>  
            **True**   il server XMPP è configurato per l'utilizzo della negoziazione richiamata se una richiesta deve essere ricevuta da un server di origine.
        
          - <span></span>  
            **False**   il server XMPP non è configurato per l'utilizzo della negoziazione richiamata e se una richiesta deve essere ricevuta da un server di origine, verrà ignorata.

10. Fare clic su **Commit** per salvare le modifiche apportate ai criteri utente o sito.

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a>Aggiornare i record DNS per il gateway XMPP di Lync Server 2013

1.  Per configurare DNS per la Federazione XMPP, è necessario aggiungere il record SRV seguente al DNS esterno\_: XMPP-server. \_TCP. \<nome\> di dominio il record SRV verrà risolto nell'FQDN del server perimetrale di Access Edge, con un valore di porta pari a 5269.

</div>

</div>

<span> </span>

</div>

</div>

</div>

