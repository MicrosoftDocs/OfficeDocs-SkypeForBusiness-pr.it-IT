---
title: 'Lync Server 2013: definire la topologia perimetrale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define your edge topology
ms:assetid: 787b23f1-8fa0-4c37-abf2-c516c5dd66f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398591(v=OCS.15)
ms:contentKeyID: 48184562
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55653e39086c311778335999d2e9fc2101b28d40
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-your-edge-topology-in-lync-server-2013"></a>Definire la topologia perimetrale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-28_

Per poter distribuire il server perimetrale, è necessario utilizzare Generatore di topologie per creare la topologia ed è necessario configurare almeno un pool Front End interno o un server Standard Edition. Utilizzare la procedura seguente per definire la topologia perimetrale per un singolo server perimetrale e quindi utilizzare le procedure descritte in [pubblicare la topologia in Lync server 2013](lync-server-2013-publish-your-topology.md) ed [esportare la topologia di Lync Server 2013 e copiarla su supporto esterno per l'installazione perimetrale](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) per pubblicare la topologia e renderla disponibile per il server perimetrale.

<div>


> [!NOTE]  
> Per l'interfaccia perimetrale interna e per quella esterna è necessario utilizzare lo stesso tipo di bilanciamento del carico. Non è possibile utilizzare il bilanciamento del carico DNS in un'interfaccia perimetrale e il bilanciamento del carico hardware nell'altra.



</div>

Per pubblicare, abilitare o disabilitare correttamente una topologia quando si aggiunge o rimuove un ruolo del server, è necessario aver effettuato l'accesso come membro dei gruppi RTCUniversalServerAdmins e Domain Admins. È anche possibile concedere le autorizzazioni e i diritti di amministratore necessari per l'aggiunta di ruoli del server a un account utente. Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync server 2013](lync-server-2013-delegate-setup-permissions.md) nella documentazione relativa alla distribuzione di server Standard Edition o Server Enterprise Edition. Per altre modifiche di configurazione, è necessaria solo l'appartenenza al gruppo RTCUniversalServerAdmins.

Se la topologia perimetrale è stata definita durante la definizione e la pubblicazione della topologia interna e non sono richieste modifiche alla topologia perimetrale creata in precedenza, non è necessario definirla e pubblicarla di nuovo. Utilizzare la procedura seguente solo se è necessario apportare modifiche alla topologia perimetrale. È necessario rendere disponibile la topologia precedentemente definita e pubblicata ai server perimetrali, eseguendo la procedura descritta in [esportare la topologia di Lync Server 2013 e copiarla su supporto esterno per l'installazione perimetrale](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).

<div>


> [!IMPORTANT]  
> Non è possibile eseguire Generatore di topologie da un server perimetrale. È necessario eseguirlo dal front end server o server Standard Edition.



</div>

Il processo per la definizione della topologia del server perimetrale viene effettuato in Generatore di topologie. In seguito sono elencati i tre tipi principali di topologie dei server perimetrali che è possibile pianificare e configurare:

  - Per definire la topologia per un singolo server perimetrale

  - Per definire la topologia per un pool di server perimetrali con bilanciamento del carico

  - Per definire la topologia per un pool di server perimetrali con bilanciamento del carico hardware

<div>

## <a name="to-define-the-topology-for-a-single-edge-server"></a>Per definire la topologia per un singolo server perimetrale

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.

2.  Nell'albero della console espandere il sito in cui si desidera distribuire un server perimetrale.

3.  Fare clic con il pulsante destro del mouse su pool **Edge**e quindi scegliere **nuovo pool di server perimetrali**.

4.  In **Definire il nuovo pool di server perimetrali** fare clic su **Avanti**.

5.  In **Definire l'FQDN del pool di server perimetrali** eseguire le operazioni seguenti:
    
      - In **FQDN pool** digitare il nome di dominio completo (FQDN) dell'interfaccia interna per il server perimetrale.
        
        <div>
        

        > [!IMPORTANT]  
        > Il nome specificato deve essere uguale al nome computer configurato nel server. Per impostazione predefinita, il nome di un computer non aggiunto a un dominio è un nome breve e non un FQDN. Generatore di topologie utilizza gli FQDN e non i nomi brevi. Pertanto, è necessario configurare un suffisso DNS sul nome del computer da distribuire come server perimetrale non aggiunto a un dominio. Utilizzare solo caratteri standard, ovvero A-Z, a-z, 0-9 e trattini, per assegnare FQDN dei server Lync Server, dei server perimetrali e dei pool. Non utilizzare caratteri Unicode o di sottolineatura. La presenza di caratteri non standard in un FQDN è spesso non supportata da DNS esterni e CA pubbliche (quando l'FQDN deve essere assegnato al nome soggetto nel certificato). Per informazioni dettagliate sull'aggiunta di un suffisso DNS a un nome computer, vedere <A href="lync-server-2013-configure-dns-for-edge-support.md">configure DNS for Edge support in Lync Server 2013</A>.

        
        </div>
    
      - Fare clic su **Pool computer singolo** e quindi su **Avanti**.

6.  In **Selezionare funzionalità** eseguire le operazioni seguenti:
    
      - Se si prevede di utilizzare un singolo FQDN e indirizzo IP per il servizio di accesso SIP, il servizio Web Conferencing di Lync Server 2013 e i servizi A/V Edge, selezionare la casella di controllo **utilizza un singolo FQDN e indirizzo IP** .
    
      - Se si prevede di abilitare la federazione, selezionare la casella di controllo **Abilita la federazione per questo pool di server perimetrali (porta 5061)**.
        
        <div>
        

        > [!NOTE]  
        > È possibile selezionare questa opzione, ma è possibile pubblicare esternamente per la federazione solo un pool di server perimetrali o un server perimetrale nell'organizzazione. Tutto l'accesso da parte di utenti federati, inclusi gli utenti di messaggistica istantanea pubblica, passa per lo stesso pool di server perimetrali o singolo server perimetrale. Se, ad esempio, la distribuzione include un pool di server perimetrali o un singolo server perimetrale distribuito a New York e uno distribuito a Londra e si abilita il supporto per la federazione nel pool di server perimetrali o nel server perimetrale di New York, il traffico dei segnali per gli utenti federati passerà per il pool di server perimetrali o il singolo server perimetrale di New York. Ciò vale anche per le comunicazioni con gli utenti di Londra, anche se un utente interno di Londra che chiami un utente federato di Londra utilizzerà il pool o il server perimetrale di Londra per il traffico audio/video.

        
        </div>
    
      - Se si prevede di supportare il protocollo XMPP per la distribuzione, selezionare la casella di controllo **Abilita la federazione XMPP (porta 5269)**

7.  In **Selezionare le opzioni IP** eseguire le operazioni seguenti:
    
      - **Abilita IPv4 su interfaccia interna**: selezionare questa casella di controllo se si desidera applicare un indirizzo IPv4 all'interfaccia interna del server perimetrale o del pool perimetrale
    
      - **Abilita IPv6 su interfaccia interna**: selezionare questa casella di controllo se si desidera applicare un indirizzo IPv6 all'interfaccia interna del server perimetrale o del pool perimetrale
    
      - **Abilita IPv4 su interfaccia esterna**: selezionare questa casella di controllo se si desidera applicare un indirizzo IPv4 all'interfaccia esterna del server perimetrale o del pool perimetrale
    
      - **Abilita IPv6 su interfaccia esterna**: selezionare questa casella di controllo se si desidera applicare un indirizzo IPv6 all'interfaccia esterna del server perimetrale o del pool perimetrale
    
    È inoltre possibile configurare il server perimetrale o il pool perimetrale per l'utilizzo di un indirizzo di conversione indirizzo di rete per gli indirizzi IP esterni. A tale scopo, selezionando la casella di controllo **l'indirizzo IP esterno del pool di server perimetrali viene convertito da NAT**.

8.  In **FQDN esterni** eseguire le operazioni seguenti:
    
      - Se in **Selezionare funzionalità** si è scelto di utilizzare un singolo FQDN e indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare l'FQDN esterno in **Accesso SIP**.
        
        <div>
        

        > [!NOTE]  
        > Se si sceglie di selezionare questa opzione, è necessario specificare un numero di porta diverso per ogni servizio Edge (impostazioni di porta consigliate: 5061 per il servizio Access Edge, 444 per il servizio Web Conferencing Edge e 443 per il servizio A/V Edge). Selezionando questa opzione, è possibile evitare possibili problemi di connettività e semplificare la configurazione, in quanto è quindi possibile utilizzare lo stesso numero di porta, ad esempio 443, per i tre servizi.

        
        </div>
    
      - Se in **Selezionare funzionalità** non si è scelto di utilizzare un singolo FQDN e indirizzo IP, digitare gli FQDN esterni per **Accesso SIP**, **Web Conferencing** e **Audio/Video**, mantenendo le porte predefinite.

9.  Fare clic su **Avanti**.

10. In **Definire l'indirizzo IP interno**, digitare l'indirizzo IP del server perimetrale in **Indirizzo IPv4 interno** e **Indirizzo IPv6 interno**, a seconda dei propri requisiti. Fare clic su **Avanti**.

11. In **Definire l'indirizzo IP esterno** eseguire le operazioni seguenti:
    
      - Se si è scelto di utilizzare un singolo FQDN e indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare l'indirizzo IPv4 esterno del server perimetrale in **Accesso SIP** e quindi fare clic su **Avanti**.
    
      - Se si è scelto di utilizzare indirizzi IPv6, digitare l'indirizzo IPv6 esterno del server perimetrale in **Accesso SIP**, quindi fare clic su **Avanti**.
    
      - Se non si è scelto di utilizzare un singolo FQDN e indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare gli indirizzi IPv4 esterni del server perimetrale in **Accesso SIP**, **Web Conferencing** e **A/V Conferencing** e quindi fare clic su **Avanti**.
    
      - Se si è scelto di utilizzare indirizzi IPv6 ma non si è scelto di utilizzare un singolo FQDN e indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare gli indirizzi IPv6 esterni del server perimetrale in **Accesso SIP**, **Web Conferencing** e **A/V Conferencing** e quindi fare clic su **Avanti**.
        
        <div>
        

        > [!NOTE]  
        > Se non è stato scelto di abilitare e assegnare gli indirizzi IPv6, questa finestra di dialogo non viene visualizzata.

        
        </div>

12. Se si è scelto di utilizzare NAT, viene visualizzata una finestra di dialogo. In **Indirizzo IPv4 pubblico per il servizio A/V Edge** digitare l'indirizzo IPv4 pubblico da convertire tramite NAT e quindi fare clic su **Avanti**.
    
    <div>
    

    > [!NOTE]  
    > Tale indirizzo deve corrispondere all'indirizzo IP esterno del servizio A/V Edge.

    
    </div>

13. Se si è scelto di utilizzare NAT e indirizzi IPv6, viene visualizzata una finestra di dialogo. In **Indirizzo IPv6 pubblico per il servizio A/V Edge** digitare l'indirizzo IPv6 pubblico da convertire tramite NAT e quindi fare clic su **Avanti**.
    
    <div>
    

    > [!NOTE]  
    > Tale indirizzo deve corrispondere all'indirizzo IP esterno del servizio A/V Edge.

    
    </div>

14. In **Pool hop successivo** in **Definire l'hop successivo** selezionare il nome del pool interno, che può essere un pool Front End o un pool Standard Edition. In alternativa, se la distribuzione include un server Director, selezionare il nome di questo server e quindi fare clic su **Avanti**.

15. In **Associare pool Front End** specificare uno o più pool interni, che possono includere pool Front End e server Standard Edition, da associare a questo server perimetrale, selezionando i nomi dei pool interni che utilizzeranno il server perimetrale per la comunicazione con gli utenti esterni supportati.
    
    <div>
    

    > [!NOTE]  
    > È possibile associare solo un pool di server perimetrali o un singolo server perimetrale con carico bilanciato a ogni pool interno per il traffico audio/video. Se è già stato associato un pool interno a un pool di server perimetrali o a un server perimetrale, viene visualizzato un avviso che indica che al pool interno è già associato un pool di server perimetrali o un server perimetrale. Se si seleziona un pool già associato a un altro server perimetrale, l'associazione verrà modificata.

    
    </div>

16. Fare clic su **Fine**.

17. Pubblicare la topologia.

</div>

<div>

## <a name="to-define-the-topology-for-a-dns-load-balanced-edge-server-pool"></a>Per definire la topologia per un pool di server perimetrali con bilanciamento del carico DNS

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.

2.  Nell'albero della console espandere il sito in cui si desidera distribuire i server perimetrali.

3.  Fare clic con il pulsante destro del mouse su **Pool di server perimetrali** e quindi scegliere **Nuovo pool di server perimetrali**.

4.  In **Definire il nuovo pool di server perimetrali** fare clic su **Avanti**.

5.  In **Definire l'FQDN del pool di server perimetrali** eseguire le operazioni seguenti:
    
      - In **Pool FQDN** digitare il nome di dominio completo (FQDN) della connessione interna del server perimetrale.
        
        <div>
        

        > [!IMPORTANT]  
        > Il nome specificato per il pool deve essere il nome del pool di server perimetrali interno. Questo deve essere definito come FQDN. Generatore di topologie utilizza gli FQDN e non i nomi brevi. Utilizzare solo caratteri standard, ovvero A-Z, a-z, 0-9 e trattini, per assegnare FQDN dei server Lync Server, dei server perimetrali e dei pool. Non utilizzare caratteri Unicode o di sottolineatura. La presenza di caratteri non standard in un FQDN è spesso non supportata da DNS esterni e CA pubbliche (quando l'FQDN deve essere assegnato al nome soggetto nel certificato).

        
        </div>
    
      - Fare clic su **Pool di più computer** e quindi su **Avanti**.

6.  In **Selezionare funzionalità** eseguire le operazioni seguenti:
    
      - Se si prevede di utilizzare un singolo FQDN e indirizzo IP per l'accesso SIP, il servizio Web Conferencing di Lync Server 2013 e i servizi A/V Edge, selezionare la casella di controllo **utilizza un singolo FQDN e indirizzo IP** .
    
      - Se si prevede di abilitare la federazione, selezionare la casella di controllo **Abilita la federazione per questo pool di server perimetrali (porta 5061)**. Fare clic su **Avanti**
        
        <div>
        

        > [!NOTE]  
        > È possibile selezionare questa opzione, ma è possibile pubblicare esternamente per la federazione solo un pool di server perimetrali o un server perimetrale nell'organizzazione. Tutto l'accesso da parte di utenti federati, inclusi gli utenti di messaggistica istantanea pubblica, passa per lo stesso pool di server perimetrali o singolo server perimetrale. Se, ad esempio, la distribuzione include un pool di server perimetrali o un singolo server perimetrale distribuito a New York e uno distribuito a Londra e si abilita il supporto per la federazione nel pool di server perimetrali o nel server perimetrale di New York, il traffico dei segnali per gli utenti federati passerà per il pool di server perimetrali o il singolo server perimetrale di New York. Ciò vale anche per le comunicazioni con gli utenti di Londra, anche se un utente interno di Londra che chiama un utente federato di Londra utilizzerà il pool o il server perimetrale di Londra per il traffico audio/video.

        
        </div>
    
      - Se si prevede di supportare il protocollo XMPP per la distribuzione, selezionare la casella di controllo **Abilita la federazione XMPP (porta 5269)**

7.  Fare clic su **Avanti**.

8.  In **Selezionare le opzioni IP** eseguire le operazioni seguenti:
    
      - **Abilita IPv4 su interfaccia interna**: selezionare questa casella di controllo se si desidera applicare un indirizzo IPv4 all'interfaccia interna del server perimetrale o del pool perimetrale
    
      - **Abilita IPv6 su interfaccia interna**: selezionare questa casella di controllo se si desidera applicare un indirizzo IPv6 all'interfaccia interna del server perimetrale o del pool perimetrale
    
      - **Abilita IPv4 su interfaccia esterna**: selezionare questa casella di controllo se si desidera applicare un indirizzo IPv4 all'interfaccia esterna del server perimetrale o del pool perimetrale
    
      - **Abilita IPv6 su interfaccia esterna**: selezionare questa casella di controllo se si desidera applicare un indirizzo IPv6 all'interfaccia esterna del server perimetrale o del pool perimetrale
    
    È inoltre possibile configurare il server perimetrale o il pool perimetrale per l'utilizzo di un indirizzo di conversione indirizzo di rete per gli indirizzi IP esterni. A tale scopo, selezionando la casella di controllo **l'indirizzo IP esterno del pool di server perimetrali viene convertito da NAT**.

9.  In **FQDN esterni** eseguire le operazioni seguenti:
    
      - Se in **Selezionare funzionalità** si è scelto di utilizzare un singolo FQDN e indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare l'FQDN esterno in **Accesso SIP**.
        
        <div>
        

        > [!NOTE]  
        > Se si sceglie di selezionare questa opzione, è necessario specificare un numero di porta diverso per ogni servizio Edge (impostazioni di porta consigliate: 5061 per il servizio Access Edge, 444 per il servizio Web Conferencing Edge e 443 per il servizio A/V Edge). Selezionando questa opzione, è possibile evitare possibili problemi di connettività e semplificare la configurazione, in quanto è quindi possibile utilizzare lo stesso numero di porta, ad esempio 443, per i tre servizi.

        
        </div>
    
      - Se in **Selezionare funzionalità** non si è scelto di utilizzare un singolo FQDN e indirizzo IP, digitare l'FQDN scelto per il lato pubblico del pool di server perimetrali in **Accesso SIP**. In **Web Conferencing** digitare l'FQDN scelto per il lato pubblico del pool di server perimetrali. In **Audio/Video** digitare l'FQDN scelto per il lato pubblico del pool di server perimetrali. Utilizzare le porte predefinite.

10. Fare clic su **Avanti**.

11. In **Definire i computer nel pool corrente** fare clic su **Aggiungi**.

12. In **Indirizzo IP e FQDN interni** eseguire le operazioni seguenti:
    
      - In **Indirizzo IPv4 interno**, digitare l'indirizzo IPv4 e l'**Indirizzo IPv6 interno**, a seconda dei propri requisiti, del primo server perimetrale che si desidera creare nel pool.
    
      - In **FQDN interno** digitare l'FQDN del primo server perimetrale che si desidera creare nel pool.
        
        <div>
        

        > [!NOTE]  
        > Il nome specificato deve essere uguale al nome computer configurato nel server. Per impostazione predefinita, il nome di un computer non aggiunto a un dominio è un nome breve e non un FQDN. Generatore di topologie utilizza gli FQDN e non i nomi brevi. Pertanto, è necessario configurare un suffisso DNS sul nome del computer da distribuire come server perimetrale non aggiunto a un dominio. Utilizzare solo caratteri standard, ovvero A-Z, a-z, 0-9 e trattini, per assegnare FQDN dei server Lync Server, dei server perimetrali, dei pool e degli array. Non utilizzare caratteri Unicode o di sottolineatura. La presenza di caratteri non standard in un FQDN è spesso non supportata da DNS esterni e CA pubbliche (quando l'FQDN deve essere assegnato al nome soggetto nel certificato). Per informazioni dettagliate sull'aggiunta di un suffisso DNS a un nome computer, vedere <A href="lync-server-2013-configure-dns-for-edge-support.md">configure DNS for Edge support in Lync Server 2013</A>.

        
        </div>

13. Fare clic su **Avanti**.

14. In **Definire l'indirizzo IP esterno** eseguire le operazioni seguenti:
    
      - Se si è scelto di utilizzare un singolo FQDN e indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare l'indirizzo IP esterno del server perimetrale in **Accesso SIP**.
    
      - Se non si è scelto di utilizzare un singolo FQDN e indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Conferencing, digitare l'indirizzo IP scelto per il lato pubblico di questo server del pool di server perimetrali in **Accesso SIP**. In **Web Conferencing** digitare l'indirizzo IP scelto per il lato pubblico di questo server del pool di server perimetrali. In **A/V Conferencing** digitare l'indirizzo IP scelto per il lato pubblico di questo server del pool di server perimetrali.

15. Fare clic su **Avanti**.

16. Se è stato scelto di abilitare gli indirizzi IPv6, in **Definire l'indirizzo IP esterno** eseguire le operazioni seguenti:
    
      - Se si è scelto di utilizzare un singolo FQDN e indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare l'indirizzo IPv6 esterno del server perimetrale in **Accesso SIP**.
    
      - Se non si è scelto di utilizzare un singolo FQDN e indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Conferencing, digitare l'indirizzo IPv6 scelto per il lato pubblico di questo server del pool di server perimetrali in **Accesso SIP**. In **Web Conferencing** digitare l'indirizzo IPv6 scelto per il lato pubblico di questo server del pool di server perimetrali. In **A/V Conferencing** digitare l'indirizzo IPv6 scelto per il lato pubblico di questo server del pool di server perimetrali.
    
    <div>
    

    > [!NOTE]  
    > Se non è stato scelto di abilitare e assegnare gli indirizzi IPv6, questa finestra di dialogo non viene visualizzata.

    
    </div>

17. Fare clic su **Fine**.
    
    <div>
    

    > [!NOTE]  
    > Il primo server perimetrale creato nel pool verrà ora visualizzato nella finestra di dialogo <STRONG>Definire i computer nel pool corrente</STRONG>.

    
    </div>

18. In **Definire i computer nel pool corrente** fare clic su **Aggiungi** e quindi ripetere i passaggi da 11 a 14 per il secondo server perimetrale che si desidera aggiungere al pool di server perimetrali.

19. Dopo aver ripetuto i passaggi da 11 a 14, fare clic su **Avanti** in **Definire i computer nel pool corrente**.
    
    <div>
    

    > [!NOTE]  
    > A questo punto, è possibile visualizzare entrambi i server perimetrali nel pool.

    
    </div>

20. Se si è scelto di utilizzare NAT, viene visualizzata una finestra di dialogo. In **Indirizzo IP pubblico** digitare l'indirizzo IPv4 o IPv6 pubblico (come appropriato) da convertire tramite NAT e quindi fare clic su **Avanti**.
    
    <div>
    

    > [!NOTE]  
    > Tale indirizzo deve corrispondere all'indirizzo IP esterno di A/V Edge.

    
    </div>

21. Nell'elenco **Pool hop successivo** in **Definire l'hop successivo** selezionare il nome del pool interno, che può essere un pool Front End o un pool Standard Edition. In alternativa, se la distribuzione include un server Director, selezionare il nome di questo server e quindi fare clic su **Avanti**.

22. In **Associare pool Front End** specificare uno o più pool interni, che possono includere pool Front End e server Standard Edition, da associare a questo server perimetrale, selezionando i nomi dei pool interni che utilizzeranno il server perimetrale per la comunicazione con gli utenti esterni supportati.
    
    <div>
    

    > [!NOTE]  
    > È possibile associare solo un pool di server perimetrali o un singolo server perimetrale con carico bilanciato a ogni pool interno per il traffico audio/video. Se è già stato associato un pool interno a un pool di server perimetrali o a un server perimetrale, viene visualizzato un avviso che indica che al pool interno è già associato un pool di server perimetrali o un server perimetrale. Se si seleziona un pool già associato a un altro server perimetrale, l'associazione verrà modificata.

    
    </div>

23. Fare clic su **Fine**.

24. Pubblicare la topologia.

</div>

<div>

## <a name="to-define-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a>Per definire la topologia per un pool di server perimetrali con bilanciamento del carico hardware

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.

2.  Nell'albero della console espandere il sito in cui si desidera distribuire i server perimetrali.

3.  Fare clic con il pulsante destro del mouse su **pool di server perimetrali**e quindi scegliere **nuovo pool Edge**.

4.  In **Definire il nuovo pool di server perimetrali** fare clic su **Avanti**.

5.  In **Definire l'FQDN del pool di server perimetrali** eseguire le operazioni seguenti:
    
      - In **FQDN** digitare il nome di dominio completo (FQDN) scelto per il lato interno del pool di server perimetrali.
        
        <div>
        

        > [!IMPORTANT]  
        > Il nome specificato per il pool deve essere il nome del pool di server perimetrali interno. Questo deve essere definito come FQDN. Generatore di topologie utilizza gli FQDN e non i nomi brevi. Utilizzare solo caratteri standard, ovvero A-Z, a-z, 0-9 e trattini, per assegnare FQDN dei server Lync Server, dei server perimetrali e dei pool. Non utilizzare caratteri Unicode o di sottolineatura. La presenza di caratteri non standard in un FQDN è spesso non supportata da DNS esterni e CA pubbliche (quando l'FQDN deve essere assegnato al nome soggetto nel certificato).

        
        </div>
    
    <!-- end list -->
    
      - Fare clic su **pool di più computer**e quindi su **Avanti**.

6.  In **Selezionare funzionalità** eseguire le operazioni seguenti:
    
      - Se si prevede di utilizzare un singolo FQDN e indirizzo IP per il servizio di accesso SIP, il servizio Web Conferencing di Lync Server e il servizio A/V Edge, selezionare la casella di controllo **utilizza un solo fqdn & indirizzo IP** .
    
      - Se si prevede di abilitare la federazione, selezionare la casella di controllo **Abilita federazione per pool di server perimetrali (porta 5061)**.
        
        <div>
        

        > [!NOTE]  
        > È possibile selezionare questa opzione, ma è possibile pubblicare esternamente per la federazione solo un pool di server perimetrali o un server perimetrale nell'organizzazione. Tutto l'accesso da parte di utenti federati, inclusi gli utenti di messaggistica istantanea pubblica, passa per lo stesso pool di server perimetrali o singolo server perimetrale. Se, ad esempio, la distribuzione include un pool di server perimetrali o un singolo server perimetrale distribuito a New York e uno distribuito a Londra e si abilita il supporto per la federazione nel pool di server perimetrali o nel server perimetrale di New York, il traffico dei segnali per gli utenti federati passerà per il pool di server perimetrali o il singolo server perimetrale di New York. Ciò vale anche per le comunicazioni con gli utenti di Londra, anche se un utente interno di Londra che chiami un utente federato di Londra utilizzerà il pool o il server perimetrale di Londra per il traffico audio/video.

        
        </div>
    
      - Se si prevede di supportare il protocollo XMPP per la distribuzione, selezionare la casella di controllo **Abilita la federazione XMPP (porta 5269)**

7.  Fare clic su **Avanti**.

8.  In **Selezionare le opzioni IP** eseguire le operazioni seguenti:
    
      - **Abilita IPv4 su interfaccia interna**: selezionare questa casella di controllo se si desidera applicare un indirizzo IPv4 all'interfaccia interna del server perimetrale o del pool perimetrale
    
      - **Abilita IPv6 su interfaccia interna**: selezionare questa casella di controllo se si desidera applicare un indirizzo IPv6 all'interfaccia interna del server perimetrale o del pool perimetrale
    
      - **Abilita IPv4 su interfaccia esterna**: selezionare questa casella di controllo se si desidera applicare un indirizzo IPv4 all'interfaccia esterna del server perimetrale o del pool perimetrale
    
      - **Abilita IPv6 su interfaccia esterna**: selezionare questa casella di controllo se si desidera applicare un indirizzo IPv6 all'interfaccia esterna del server perimetrale o del pool perimetrale
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>Non</STRONG> selezionare la casella di controllo <STRONG>L'indirizzo IP esterno del pool di server perimetrali è convertito da NAT</STRONG>. Network Address Translation (NAT) non è supportato quando si utilizza il bilanciamento del carico di rete hardware.

    
    </div>

9.  In **FQDN esterni** eseguire le operazioni seguenti:
    
      - Se in **Selezionare funzionalità** si è scelto di utilizzare un singolo FQDN e indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare l'FQDN esterno in **Accesso SIP**.
        
        <div>
        

        > [!NOTE]  
        > Se si sceglie di selezionare questa opzione, è necessario specificare un numero di porta diverso per ogni servizio Edge (impostazioni di porta consigliate: 5061 per il servizio Access Edge, 444 per il servizio Web Conferencing Edge e 443 per il servizio A/V Edge). Selezionando questa opzione, è possibile evitare possibili problemi di connettività e semplificare la configurazione, in quanto è quindi possibile utilizzare lo stesso numero di porta, ad esempio 443, per i tre servizi.

        
        </div>
    
      - Se in **Selezionare funzionalità** non si è scelto di utilizzare un singolo FQDN e indirizzo IP, digitare l'FQDN scelto per il lato pubblico del pool di server perimetrali in **Accesso SIP**. In **Web Conferencing** digitare l'FQDN scelto per il lato pubblico del pool di server perimetrali. In **Audio/Video** digitare l'FQDN scelto per il lato pubblico del pool di server perimetrali. Utilizzare le porte predefinite.
        
        <div>
        

        > [!NOTE]  
        > Questi saranno gli FQDN IP virtuali (VIP) del lato pubblico per il pool.

        
        </div>

10. Fare clic su **Avanti**.

11. In **Definire i computer nel pool corrente** fare clic su **Aggiungi**.

12. In **Definire l'indirizzo IP esterno** eseguire le operazioni seguenti:
    
      - Se si è scelto di utilizzare un singolo FQDN e indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare l'indirizzo IPv4 esterno del server perimetrale in **Accesso SIP** e quindi fare clic su **Avanti**.
    
      - Se non si è scelto di utilizzare un singolo FQDN e indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Conferencing, digitare l'indirizzo IP scelto per il lato pubblico di questo server del pool di server perimetrali in **Accesso SIP**. In **Web Conferencing** digitare l'indirizzo IP scelto per il lato pubblico di questo server del pool di server perimetrali. In **A/V Conferencing** digitare l'indirizzo IP scelto per il lato pubblico di questo server del pool di server perimetrali.

13. Fare clic su **Avanti**.

14. Se è stato scelto di abilitare gli indirizzi IPv6, in **Definire l'indirizzo IP esterno** eseguire le operazioni seguenti:
    
      - Se si è scelto di utilizzare un singolo FQDN e indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare l'indirizzo IPv6 esterno del server perimetrale in **Accesso SIP**.
    
      - Se non si è scelto di utilizzare un singolo FQDN e indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Conferencing, digitare l'indirizzo IPv6 scelto per il lato pubblico di questo server del pool di server perimetrali in **Accesso SIP**. In **Web Conferencing** digitare l'indirizzo IPv6 scelto per il lato pubblico di questo server del pool di server perimetrali. In **A/V Conferencing** digitare l'indirizzo IPv6 scelto per il lato pubblico di questo server del pool di server perimetrali.
    
    <div>
    

    > [!NOTE]  
    > Se non è stato scelto di abilitare e assegnare gli indirizzi IPv6, questa finestra di dialogo non viene visualizzata.

    
    </div>

15. Fare clic su **Fine**.
    
    <div>
    

    > [!NOTE]  
    > Il primo server perimetrale creato nel pool verrà ora visualizzato nella finestra di dialogo <STRONG>Definire i computer nel pool corrente</STRONG>.

    
    </div>

16. In **Definire i computer nel pool corrente** fare clic su **Aggiungi** e quindi ripetere i passaggi da 11 a 14 per il secondo server perimetrale che si desidera aggiungere al pool di server perimetrali.

17. Dopo aver ripetuto i passaggi da 11 a 14, fare clic su **Avanti** in **Definire i computer nel pool corrente**.
    
    <div>
    

    > [!NOTE]  
    > A questo punto, è possibile visualizzare entrambi i server perimetrali nel pool.

    
    </div>

18. Nell'elenco **Pool hop successivo** in **Definire l'hop successivo** selezionare il nome del pool interno, che può essere un pool Front End o un pool Standard Edition. In alternativa, se la distribuzione include un server Director, selezionare il nome di questo server e quindi fare clic su **Avanti**.

19. In **Associare pool Front End** specificare uno o più pool interni, che possono includere pool Front End e server Standard Edition, da associare a questo server perimetrale, selezionando i nomi dei pool interni che utilizzeranno il server perimetrale per la comunicazione con gli utenti esterni supportati.
    
    <div>
    

    > [!NOTE]  
    > È possibile associare solo un pool di server perimetrali o un singolo server perimetrale con carico bilanciato a ogni pool interno per il traffico audio/video. Se è già stato associato un pool interno a un pool di server perimetrali o a un server perimetrale, viene visualizzato un avviso che indica che al pool interno è già associato un pool di server perimetrali o un server perimetrale. Se si seleziona un pool già associato a un altro server perimetrale, l'associazione verrà modificata.

    
    </div>

20. Fare clic su **Fine**.

21. Pubblicare la topologia.

</div>

</div>

<span> </span>

</div>

</div>

</div>

