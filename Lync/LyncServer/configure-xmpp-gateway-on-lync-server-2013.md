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
ms.openlocfilehash: 2910766dbb2147fa5d1c51235f10ab2e80826bda
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a>Configurare il gateway XMPP in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-10-28_

La procedura finale per la migrazione del gateway XMPP consiste nel configurare i certificati per Lync Server 2013 Edge Server, distribuire il gateway XMPP di Lync Server 2013 e aggiornare i record DNS per il gateway XMPP. Questi passaggi devono essere eseguiti in parallelo per ridurre al minimo il tempo di discesa del gateway XMPP. Prima di eseguire questa procedura, tutti gli utenti devono essere spostati nella distribuzione di Microsoft Lync Server 2013.

<div class=" ">


> [!IMPORTANT]  
> La Federazione XMPP non è supportata per gli utenti che partecipano a Survivable Branch Appliance. Questo vale sia per vedere le informazioni sulla presenza che per scambiare messaggi di messaggistica istantanea.



</div>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a>Configurare i certificati del gateway XMPP nel server perimetrale di Lync Server 2013

1.  Nel server perimetro, nella distribuzione guidata, accanto a **passaggio 3: richiedere, installare o assegnare certificati**, fare di nuovo clic su **Esegui**.
    
    <div class=" ">
    

    > [!TIP]  
    > Se si distribuisce il server perimetrale per la prima volta, verrà visualizzato di nuovo Esegui anziché Esegui.

    
    </div>

2.  Nella pagina **attività certificato disponibili** fare clic su **Crea una nuova richiesta di certificato**.

3.  Nella pagina **richiesta certificato** fare clic su **certificato bordo esterno**.

4.  Nella pagina **richiesta posticipata o immediata** selezionare la casella di controllo **prepara la richiesta ora, ma inviarla in seguito** .

5.  Nella pagina **file di richiesta certificato** Digitare il percorso completo e il nome file del file in cui deve essere salvata la richiesta, ad esempio c:\\CERT\_exernal\_Edge. cer.

6.  Nella pagina **Specifica modello di certificato alternativo** , per usare un modello diverso da quello predefinito del modello webserver, selezionare la casella di controllo **Usa il modello di certificato alternativo per l'autorità di certificazione selezionata** .

7.  Nella pagina **impostazioni di sicurezza e nome** eseguire le operazioni seguenti:
    
    1.  In **nome descrittivo**Digitare un nome visualizzato per il certificato.
    
    2.  In **bit length**specificare la lunghezza in bit (in genere, il valore predefinito è 2048).
    
    3.  Verificare che la casella **di controllo contrassegna la chiave privata del certificato come esportabile** sia selezionata.

8.  Nella pagina **informazioni organizzazione** Digitare il nome dell'organizzazione e dell'unità organizzativa, ad esempio divisione o reparto.

9.  Nella pagina **informazioni geografiche** specificare le informazioni sulla posizione.

10. Nella pagina **nome oggetto/nomi oggetto alternativo** vengono visualizzate le informazioni che verranno inserite automaticamente dalla procedura guidata. Se sono necessari altri nomi alternativi per l'oggetto, è necessario specificarli nei due passaggi successivi.

11. Nell' **impostazione del dominio SIP nella pagina nome alternativo oggetto (sans)** selezionare la casella di controllo Domain per aggiungere un SIP. \<SipDomain\> voce nell'elenco nomi alternativi oggetto.

12. Nella pagina **Configura altri nomi alternativi oggetto** specificare eventuali altri nomi alternativi per gli argomenti necessari.
    
    <div class=" ">
    

    > [!TIP]  
    > Se il proxy XMPP è installato, per impostazione predefinita il nome di dominio, ad esempio contoso.com, viene popolato nelle voci SAN. Se sono necessarie altre voci, aggiungerle in questo passaggio.

    
    </div>

13. Nella pagina **Riepilogo richieste** verificare le informazioni sul certificato da usare per generare la richiesta.

14. Dopo che i comandi hanno terminato l'uso, è possibile **visualizzare il log**oppure fare clic su Avanti per continuare.

15. Nella pagina **file di richiesta di certificato** è possibile visualizzare il file della richiesta di firma del certificato (CSR) generato facendo clic su **Visualizza** o Esci dalla creazione guidata certificato facendo clic su **fine**.

16. Copiare il file di richiesta e inviarlo all'autorità di certificazione pubblica.

17. Dopo la ricezione, l'importazione e l'assegnazione del certificato pubblico, è necessario arrestare e riavviare i servizi Edge Server. A tale scopo, digitare la console di gestione di Lync Server:
    
        Stop-CsWindowsService

      &nbsp;
    
        Start-CsWindowsService

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a>Configurare un nuovo gateway XMPP di Lync Server 2013

1.  Aprire il pannello di controllo di Lync Server.

2.  Sulla barra di spostamento sinistra fare clic su **Federazione e accesso esterno** , quindi fare clic su **partner federati XMPP**.

3.  Per creare una nuova configurazione, fare clic su **nuovo**.

4.  Definire le impostazioni seguenti:

5.  **Dominio principale (**     obbligatorio). Il dominio principale è il dominio di base del partner XMPP. Ad esempio, immetti **Fabrikam.com** per il nome di dominio partner XMPP. Questa è una voce obbligatoria.

6.  **Descrizione**   la descrizione riguarda le note o altre informazioni di identificazione per questa particolare configurazione. Questa voce è facoltativa.

7.  **Altri**   domini i domini aggiuntivi sono domini che fanno parte del dominio del partner XMPP che deve essere incluso come parte della comunicazione XMPP consentita. Ad esempio, se il dominio principale è **Fabrikam.com**, devi elencare tutti gli altri domini in Fabrikam.com con cui comunicherai per mezzo di XMPP.

8.  **Tipo di partner**   il **tipo di partner** è un'impostazione obbligatoria. È necessario scegliere una delle opzioni seguenti per descrivere e applicare i contatti che è possibile aggiungere. È possibile selezionare una delle opzioni seguenti:
    
      - **Federati**   un tipo di partner **federato** rappresenta un livello elevato di attendibilità tra la distribuzione di Lync Server e il partner XMPP.Questo tipo di partner è consigliato per la Federazione con i server XMPP all'interno della stessa organizzazione o dove esiste una relazione commerciale stabilita.I contatti XMPP in partner federati possono:
        
        1.  Aggiungere contatti di Lync e visualizzare la presenza senza autorizzazione espressa da parte dell'utente di Lync.
        
        2.  Inviare messaggi istantanei ai contatti di Lync indipendentemente dal fatto che l'utente di Lync li abbia aggiunti nell'elenco contatti.
        
        3.  Vedere le note sullo stato di un utente di Lync.
    
      - **Public Verified**   un partner pubblico **verificato** è un provider XMPP pubblico considerato attendibile per verificare l'identità degli utenti.I contatti XMPP nelle reti pubbliche verificate possono aggiungere contatti di Lync e visualizzarne la presenza e inviare messaggi istantanei senza autorizzazione espressa degli utenti di Lync.I contatti XMPP nelle reti verificate pubbliche non vedono mai le note sullo stato degli utenti di Lync.Questa impostazione non è consigliata.
    
      - **Pubblico non verificato**   un partner **pubblico non verificato** è un provider XMPP pubblico che non è considerato attendibile per verificare l'identità degli utenti.Gli utenti XMPP su reti pubbliche non verificate non possono comunicare con gli utenti di Lync, a meno che l'utente di Lync non li abbia espressamente autorizzati aggiungendoli all'elenco contatti.Gli utenti XMPP su reti pubbliche non verificate non vedono mai le note di stato degli utenti di Lync.Questa impostazione è consigliata per qualsiasi federazione con provider XMPP pubblici, ad esempio Google Talk.

9.  **Tipo di connessione:** Definisce le varie regole e le impostazioni di richiamata.
    
      - **La negoziazione**   TLS definisce le regole di negoziazione TLS. Un servizio XMPP può richiedere TLS, può rendere facoltativo TLS oppure definire che TLS non è supportato. La scelta facoltativa lascia il requisito fino al servizio XMPP per una decisione obbligatorio-negoziare. Per visualizzare tutte le impostazioni e i dettagli possibili per la negoziazione SASL, TLS e richiamata, incluse le configurazioni di errore non valide e note, vedere [impostazioni di negoziazione per partner federati XMPP in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).
        
          - <span></span>  
            **Obbligatorio**   il servizio XMPP richiede la negoziazione TLS.
        
          - <span></span>  
            **Facoltativo**   il servizio XMPP indica che TLS è obbligatorio da negoziare.
        
          - <span></span>  
            **Non supportato**   il servizio XMPP non supporta TLS.
    
      - **La negoziazione**   SASL Definisce le regole di negoziazione SASL. Un servizio XMPP può richiedere SASL, può rendere SASL facoltativo o Definisci che SASL non è supportato. La scelta facoltativa lascia il requisito fino al servizio XMPP partner per una decisione obbligatorio-to-negotiate.
        
          - <span></span>  
            **Obbligatorio**   il servizio XMPP richiede la negoziazione SASL.
        
          - <span></span>  
            **Facoltativo**   il servizio XMPP indica che SASL è obbligatorio-negoziare.
        
          - <span></span>  
            **Non supportato**   il servizio XMPP non supporta SASL.
    
      - **Negoziazione richiamata del server di supporto** Il processo di negoziazione richiamata del server di supporto usa il DNS (Domain Name System) e un server autorevole per verificare che la richiesta provenisse da un partner XMPP valido. A questo scopo, il server di origine crea un messaggio di un tipo specifico con una chiave richiamata generata e cerca il server di ricezione nel DNS. Il server di origine invia la chiave in un flusso XML alla ricerca DNS risultante, presumibilmente il server di ricezione. Al ricevimento della chiave sul flusso XML, il server di ricezione non risponde al server di origine, ma invia la chiave a un server autorevole noto. Il server autorevole verifica che la chiave sia valida o non valida. Se non è valido, il server di ricezione non risponde al server di origine. Se la chiave è valida, il server di ricezione informa il server di origine che l'identità e la chiave sono valide e che la conversazione può iniziare.
        
        Esistono due stati validi per la **negoziazione richiamata**:
        
          - <span></span>  
            **True**   il server XMPP è configurato per l'uso della negoziazione richiamata se una richiesta deve essere ricevuta da un server di origine.
        
          - <span></span>  
            **Falso**   il server XMPP non è configurato per l'uso della negoziazione richiamata e se una richiesta deve essere ricevuta da un server di origine, verrà ignorata.

10. Fare clic su **conferma** per salvare le modifiche apportate ai criteri per il sito o per gli utenti.

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a>Aggiornare i record DNS per il gateway XMPP di Lync Server 2013

1.  Per configurare il DNS per la Federazione XMPP, è possibile aggiungere il record SRV seguente al DNS\_esterno: XMPP-server. \_TCP. \<nome\> di dominio il record SRV verrà risolto nell'FQDN di Access Edge del server Edge, con un valore di porta 5269.

</div>

</div>

<span> </span>

</div>

</div>

</div>

