---
title: 'Lync Server 2013: Definire la topologia perimetrale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define your edge topology
ms:assetid: 787b23f1-8fa0-4c37-abf2-c516c5dd66f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398591(v=OCS.15)
ms:contentKeyID: 48184562
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8364d2167b719e020ecebc3808c2ca850d14bc0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-your-edge-topology-in-lync-server-2013"></a>Definire la topologia perimetrale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-28_

Per creare la topologia, è necessario usare generatore di topologia e configurare almeno un pool di front-end interno o un server Standard Edition prima di poter distribuire il server perimetrale. Usare la procedura seguente per definire la topologia di Edge per un singolo Edge Server e quindi usare le procedure descritte in [pubblicare la topologia in Lync server 2013](lync-server-2013-publish-your-topology.md) ed [esportare la topologia di Lync Server 2013 e copiarla in elementi multimediali esterni per l'installazione di Edge](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) per pubblicare la topologia e renderla disponibile per il server perimetrale.

<div>


> [!NOTE]  
> L'interfaccia perimetrale interna e l'interfaccia perimetrale esterna devono usare lo stesso tipo di bilanciamento del carico. Non è possibile usare il bilanciamento del carico DNS in un'interfaccia perimetrale e il bilanciamento del carico hardware nell'altra.



</div>

Per pubblicare, abilitare o disabilitare correttamente una topologia durante l'aggiunta o la rimozione di un ruolo del server, è necessario avere effettuato l'accesso come utente membro dei gruppi RTCUniversalServerAdmins e Domain Admins. È anche possibile concedere i diritti di amministratore e le autorizzazioni necessarie per l'aggiunta di ruoli del server a un account utente. Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync server 2013](lync-server-2013-delegate-setup-permissions.md) nella documentazione sulla distribuzione di server Standard Edition o Server Enterprise Edition. Per altre modifiche alla configurazione, è necessaria solo l'appartenenza al gruppo RTCUniversalServerAdmins.

Se è stata definita la topologia di Edge quando è stata definita e pubblicata la topologia interna e non sono necessarie modifiche alla topologia perimetrale definita in precedenza, non è necessario definirla e pubblicarla di nuovo. Usare la procedura seguente solo se è necessario apportare modifiche alla topologia di Edge. Per usare la topologia definita e pubblicata in precedenza per gli Edge Server, è necessario eseguire la procedura descritta in [esportare la topologia di Lync Server 2013 e copiarla in elementi multimediali esterni per l'installazione di Edge](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).

<div>


> [!IMPORTANT]  
> Non è possibile eseguire Generatore di topologia da un server perimetrale. È necessario eseguirlo dal server front-end o da server Standard Edition.



</div>

Il processo per definire la topologia di Edge Server viene eseguito in Generatore di topologie. Di seguito sono elencati i tre tipi principali di topologie di Edge Server che si prevede di pianificare e configurare:

  - Per definire la topologia di un singolo Edge Server

  - Per definire la topologia di un pool di Edge Server con bilanciamento del carico

  - Per definire la topologia di un pool di Edge con bilanciamento del carico hardware

<div>

## <a name="to-define-the-topology-for-a-single-edge-server"></a>Per definire la topologia di un singolo Edge Server

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.

2.  Nell'albero della console espandere il sito in cui si vuole distribuire un server perimetrale.

3.  Fare clic con il pulsante destro del mouse su pool **Edge**e quindi scegliere **nuovo pool di bordi**.

4.  In **definire il nuovo pool di bordi**fare clic su **Avanti**.

5.  In **definire il nome di dominio completo del pool Edge**eseguire le operazioni seguenti:
    
      - In **FQDN del pool**Digitare il nome di dominio completo (FQDN) dell'interfaccia interna per il server perimetrale.
        
        <div>
        

        > [!IMPORTANT]  
        > Il nome specificato deve essere uguale al nome del computer configurato nel server. Per impostazione predefinita, il nome del computer di un computer che non è associato a un dominio è un nome breve, non un FQDN. Generatore di topologie usa gli FQDN e non i nomi brevi. Devi quindi configurare un suffisso DNS sul nome del computer da distribuire come server perimetrale che non è associato a un dominio. Usare solo caratteri standard (tra cui A-Z, a-z, 0-9 e segni meno) durante l'assegnazione di nomi di dominio completi di Lync Server, Edge Server e pool. Non usare caratteri Unicode o carattere di sottolineatura. I caratteri non standard di un nome di dominio completo spesso non sono supportati dal DNS esterno e dalle CA pubbliche (quando il nome di dominio completo deve essere assegnato a SN nel certificato). Per informazioni dettagliate sull'aggiunta di un suffisso DNS a un nome di computer, vedere <A href="lync-server-2013-configure-dns-for-edge-support.md">configurare il supporto DNS per Edge in Lync Server 2013</A>.

        
        </div>
    
      - Fare clic su **pool di computer singolo**e quindi su **Avanti**.

6.  In **Seleziona funzionalità**eseguire le operazioni seguenti:
    
      - Se si prevede di usare un solo FQDN e un indirizzo IP per il servizio di accesso SIP, il servizio di conferenza Web di Lync Server 2013 e i servizi A/V Edge, selezionare la casella di controllo **Usa un solo nome di dominio completo e indirizzo IP** .
    
      - Se si prevede di abilitare la Federazione, selezionare la casella **di controllo Abilita federazione per questo pool di bordi (porta 5061)** .
        
        <div>
        

        > [!NOTE]  
        > È possibile selezionare questa opzione, ma è possibile pubblicare esternamente per la Federazione solo un pool di Edge o un server perimetrale dell'organizzazione. Tutti gli accessi da parte di utenti federati, inclusi gli utenti di messaggistica istantanea pubblica, passano attraverso lo stesso pool di Edge o un singolo Edge Server. Ad esempio, se la distribuzione include un pool di Edge o un server perimetrale distribuito in New York e uno distribuito a Londra e si Abilita il supporto federativo per il pool Edge di New York o un singolo Edge Server, il traffico di segnale per gli utenti federati passerà attraverso New York Edge pool o Single Edge Server. Ciò avviene persino per le comunicazioni con gli utenti di Londra, anche se un utente interno di Londra che chiama un utente federato di Londra utilizza il pool o il server perimetrale di Londra per il traffico A/V.

        
        </div>
    
      - Se si prevede di supportare il protocollo XMPP (Extensible Messaging and Presence Protocol) per la distribuzione, selezionare la casella di controllo **Abilita federazione XMPP (porta 5269)**

7.  In **Seleziona opzioni IP**eseguire le operazioni seguenti:
    
      - **Abilitare IPv4 sull'interfaccia interna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv4 all'interfaccia interna del server perimetrale o del pool Edge
    
      - **Abilitare IPv6 sull'interfaccia interna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv6 all'interfaccia interna del server perimetrale o del pool Edge
    
      - **Abilitare IPv4 sull'interfaccia esterna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv4 all'interfaccia esterna del server perimetrale o del pool Edge
    
      - **Abilitare IPv6 sull'interfaccia esterna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv6 all'interfaccia esterna del server perimetrale o del pool Edge
    
    È anche possibile configurare l'Edge Server o il pool di Edge in uso di un indirizzo di rete per gli indirizzi IP esterni. A tale scopo, seleziona la casella di controllo **l'indirizzo IP esterno di questo pool di bordi viene tradotto da NAT**.

8.  In **FQDN esterni**eseguire le operazioni seguenti:
    
      - Se in **Seleziona funzionalità** si è scelto di usare un singolo FQDN e un indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio a/V Edge, digitare il nome di dominio completo esterno in **Access SIP**.
        
        <div>
        

        > [!NOTE]  
        > Se si sceglie questa opzione, è necessario specificare un numero di porta diverso per ogni servizio Edge (impostazioni di porta consigliate: 5061 per Access Edge service, 444 per Web Conferencing Edge service e 443 per un/V Edge service). Se si seleziona questa opzione, è possibile evitare potenziali problemi di connettività e semplificare la configurazione perché è quindi possibile usare lo stesso numero di porta, ad esempio 443, per tutti e tre i servizi.

        
        </div>
    
      - Se in **Seleziona funzionalità** non si è scelto di usare un singolo nome di dominio completo e un indirizzo IP, digitare gli FQDN esterni per l' **accesso SIP**, le **conferenze Web** e il **video audio**, mantenendo le porte predefinite.

9.  Fare clic su **Avanti**.

10. In **definire l'indirizzo IP interno**Digitare l'indirizzo IP del server perimetrale nell'indirizzo **IPv4 interno** e l' **indirizzo IPv6 interno** , come appropriato per i requisiti. Fare clic su **Avanti**.

11. In **definire l'indirizzo IP esterno**eseguire le operazioni seguenti:
    
      - Se si è scelto di usare un singolo FQDN e un indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare l'indirizzo IPv4 esterno del server perimetrale in **Access SIP**e quindi fare clic su **Avanti**.
    
      - Se si è scelto di usare gli indirizzi IPv6, digitare l'indirizzo IPv6 esterno dell'Edge Server in **Access SIP**e quindi fare clic su **Avanti**.
    
      - Se non si è scelto di usare un singolo FQDN e un indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare gli indirizzi IPv4 esterni dell'Edge Server in **Access SIP**, servizi di **conferenza Web**e **conferenze a/v**e quindi fare clic su **Avanti**.
    
      - Se si è scelto di usare gli indirizzi IPv6 e non si è scelto di usare un singolo FQDN e un indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare gli indirizzi IPv6 esterni dell'Edge Server in **Access SIP**, servizi di **conferenza Web**e **conferenze a/v**e quindi fare clic su **Avanti**.
        
        <div>
        

        > [!NOTE]  
        > Se non si è scelto di abilitare e assegnare l'indirizzo IPv6, la finestra di dialogo non verrà visualizzata.

        
        </div>

12. Se si è scelto di usare NAT, viene visualizzata una finestra di dialogo. Nell' **indirizzo IPv4 pubblico per il servizio a/V Edge**Digitare l'indirizzo IPv4 pubblico da tradurre tramite NAT e quindi fare clic su **Avanti**.
    
    <div>
    

    > [!NOTE]  
    > Dovrebbe essere l'indirizzo IP esterno del servizio A/V Edge.

    
    </div>

13. Se si è scelto di usare gli indirizzi NAT e IPv6, viene visualizzata una finestra di dialogo. Nell' **indirizzo IPv6 pubblico per il servizio a/V Edge**Digitare l'indirizzo IPv6 pubblico da tradurre tramite NAT e quindi fare clic su **Avanti**.
    
    <div>
    

    > [!NOTE]  
    > Dovrebbe essere l'indirizzo IP esterno del servizio A/V Edge.

    
    </div>

14. In **Definisci l'hop successivo**, nel **pool hop successivo**, selezionare il nome del pool interno, che può essere un pool Front-end o un pool Standard Edition. In alternativa, se la distribuzione include un amministratore, selezionare il Director. Quindi fare clic su **Avanti**.

15. In **Associa pool Front End**specificare uno o più pool interni, che possono includere i pool Front-end e i server Standard Edition, da associare a questo Edge Server, selezionando i nomi dei pool interni che devono usare questo Edge Server per la comunicazione con utenti esterni supportati.
    
    <div>
    

    > [!NOTE]  
    > Solo un pool di Edge con bilanciamento del carico o un singolo Edge Server può essere associato a ogni pool interno per il traffico A/V. Se si dispone già di un pool interno associato a un pool di Edge o un server perimetrale, viene visualizzato un avviso che indica che il pool interno è già associato a un pool di Edge o a un server perimetrale. Se si seleziona un pool già associato a un altro Edge Server, l'associazione verrà modificata.

    
    </div>

16. Fare clic su **fine**.

17. Pubblicare la topologia.

</div>

<div>

## <a name="to-define-the-topology-for-a-dns-load-balanced-edge-server-pool"></a>Per definire la topologia di un pool di server Edge con bilanciamento del carico DNS

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.

2.  Nell'albero della console espandere il sito in cui si vogliono distribuire i server perimetrali.

3.  Fare clic con il pulsante destro del mouse su pool **Edge**e quindi scegliere **nuovo pool di bordi**.

4.  In **definire il nuovo pool di bordi**fare clic su **Avanti**.

5.  In **definire il nome di dominio completo del pool Edge**eseguire le operazioni seguenti:
    
      - In **FQDN del pool**Digitare il nome di dominio completo (FQDN) per la connessione interna del pool di bordi.
        
        <div>
        

        > [!IMPORTANT]  
        > Il nome specificato per il pool deve essere il nome del pool di Edge interno. Questa operazione deve essere definita come FQDN. Generatore di topologie usa gli FQDN e non i nomi brevi. Usare solo caratteri standard (tra cui A-Z, a-z, 0-9 e segni meno) durante l'assegnazione di nomi di dominio completi di Lync Server, Edge Server e pool. Non usare caratteri Unicode o carattere di sottolineatura. I caratteri non standard di un nome di dominio completo spesso non sono supportati dal DNS esterno e dalle CA pubbliche (quando il nome di dominio completo deve essere assegnato a SN nel certificato).

        
        </div>
    
      - Fare clic su **pool di computer multipli**e quindi su **Avanti**.

6.  In **Seleziona funzionalità**eseguire le operazioni seguenti:
    
      - Se si prevede di usare un solo FQDN e un indirizzo IP per l'accesso SIP, il servizio Web Conferencing di Lync Server 2013 e un/V Edge Services, selezionare la casella di controllo **Usa un solo nome di dominio completo e indirizzo IP** .
    
      - Se si prevede di abilitare la Federazione, selezionare la casella **di controllo Abilita federazione per questo pool di bordi (porta 5061)** . Fare clic su **Avanti**
        
        <div>
        

        > [!NOTE]  
        > È possibile selezionare questa opzione, ma è possibile pubblicare esternamente per la Federazione solo un pool di Edge o un server perimetrale dell'organizzazione. Tutti gli accessi da parte di utenti federati, inclusi gli utenti di messaggistica istantanea pubblica, passano attraverso lo stesso pool di Edge o un singolo Edge Server. Se ad esempio nella distribuzione è incluso un pool di server perimetrali o un singolo server perimetrale distribuito a New York e uno distribuito a Londra e si abilita il supporto della federazione per il pool di server perimetrali o il singolo server perimetrale di New York, il traffico di segnalazione per gli utenti federati passerà attraverso tale pool o server. Ciò avviene persino per le comunicazioni con gli utenti di Londra, anche se un utente interno di Londra che chiama un utente federato di Londra utilizza il pool o il server perimetrale di Londra per il traffico A/V.

        
        </div>
    
      - Se si prevede di supportare il protocollo XMPP (Extensible Messaging and Presence Protocol) per la distribuzione, selezionare la casella di controllo **Abilita federazione XMPP (porta 5269)**

7.  Fare clic su **Avanti**.

8.  In **Seleziona opzioni IP**eseguire le operazioni seguenti:
    
      - **Abilitare IPv4 sull'interfaccia interna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv4 all'interfaccia interna del server perimetrale o del pool Edge
    
      - **Abilitare IPv6 sull'interfaccia interna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv6 all'interfaccia interna del server perimetrale o del pool Edge
    
      - **Abilitare IPv4 sull'interfaccia esterna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv4 all'interfaccia esterna del server perimetrale o del pool Edge
    
      - **Abilitare IPv6 sull'interfaccia esterna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv6 all'interfaccia esterna del server perimetrale o del pool Edge
    
    È anche possibile configurare l'Edge Server o il pool di Edge in uso di un indirizzo di rete per gli indirizzi IP esterni. A tale scopo, seleziona la casella di controllo **l'indirizzo IP esterno di questo pool di bordi viene tradotto da NAT**.

9.  In **FQDN esterni**eseguire le operazioni seguenti:
    
      - Se in **Seleziona funzionalità** si è scelto di usare un singolo FQDN e un indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio a/V Edge, digitare il nome di dominio completo esterno in **Access SIP**.
        
        <div>
        

        > [!NOTE]  
        > Se si sceglie questa opzione, è necessario specificare un numero di porta diverso per ogni servizio Edge (impostazioni di porta consigliate: 5061 per Access Edge service, 444 per Web Conferencing Edge service e 443 per un/V Edge service). Selezionando questa opzione, è possibile evitare potenziali problemi di connettività e semplificare la configurazione perché è quindi possibile usare lo stesso numero di porta, ad esempio 443, per tutti e tre i servizi.

        
        </div>
    
      - Se in **Seleziona funzionalità** non si è scelto di usare un singolo nome di dominio completo e indirizzo IP, digitare il nome di dominio completo scelto per il lato pubblico del pool di Edge per l' **accesso SIP**. In **Web Conferencing**Digitare il nome di dominio completo scelto per il lato pubblico del pool di Edge. In **audio/video**Digitare il nome di dominio completo scelto per il lato pubblico del pool di bordi. Usare le porte predefinite.

10. Fare clic su **Avanti**.

11. In **definire i computer in questo pool**fare clic su **Aggiungi**.

12. In **FQDN interno e indirizzo IP**eseguire le operazioni seguenti:
    
      - Nell' **indirizzo IPv4 interno**Digitare l'indirizzo IPv4 e l' **indirizzo IPv6 interno** come appropriato per i requisiti per il primo Edge Server che si vuole creare nel pool.
    
      - In **FQDN interno**Digitare il nome di dominio completo del primo Edge Server che si vuole creare nel pool.
        
        <div>
        

        > [!NOTE]  
        > Il nome specificato deve essere uguale al nome del computer configurato nel server. Per impostazione predefinita, il nome di un computer non aggiunto a un dominio è un nome breve e non un FQDN. Generatore di topologie usa gli FQDN e non i nomi brevi. Devi quindi configurare un suffisso DNS sul nome del computer da distribuire come server perimetrale che non è associato a un dominio. Usare solo caratteri standard (tra cui A-Z, a-z, 0-9 e segni meno) durante l'assegnazione di nomi di dominio completi di Lync Server, Edge Server, pool e matrici. Non usare caratteri Unicode o carattere di sottolineatura. I caratteri non standard di un nome di dominio completo spesso non sono supportati dal DNS esterno e dalle CA pubbliche (quando il nome di dominio completo deve essere assegnato a SN nel certificato). Per informazioni dettagliate sull'aggiunta di un suffisso DNS a un nome di computer, vedere <A href="lync-server-2013-configure-dns-for-edge-support.md">configurare il supporto DNS per Edge in Lync Server 2013</A>.

        
        </div>

13. Fare clic su **Avanti**.

14. In **definire gli indirizzi IP esterni**eseguire le operazioni seguenti:
    
      - Se si è scelto di usare un singolo FQDN e un indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare l'indirizzo IP esterno dell'Edge Server in **Access SIP**.
    
      - Se non si è scelto di usare un singolo FQDN e un indirizzo IP per l'accesso SIP, il servizio di conferenza Web e il servizio di conferenza telefonica A/V, digitare l'indirizzo IP scelto per il lato pubblico di questo server Edge pool per l' **accesso SIP**. In **Web Conferencing**Digitare l'indirizzo IP scelto per il lato pubblico di questo server Edge pool. In **conferenze telefoniche a/V**Digitare l'indirizzo IP scelto per il lato pubblico di questo server Edge pool.

15. Fare clic su **Avanti**.

16. Se si è scelto di abilitare gli indirizzi IPv6, in **definire gli indirizzi IP esterni**eseguire le operazioni seguenti:
    
      - Se si è scelto di usare un singolo FQDN e un indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare l'indirizzo IPv6 esterno dell'Edge Server in **Access SIP**.
    
      - Se non si è scelto di usare un singolo FQDN e un indirizzo IP per l'accesso SIP, il servizio di conferenza Web e il servizio di conferenza telefonica A/V, digitare l'indirizzo IPv6 scelto per il lato pubblico di questo server Edge pool per l' **accesso SIP**. In servizi di **conferenza Web**Digitare l'indirizzo IPv6 scelto per il lato pubblico di questo server Edge pool. In **conferenze telefoniche a/V**Digitare l'indirizzo IPv6 scelto per il lato pubblico di questo server Edge pool.
    
    <div>
    

    > [!NOTE]  
    > Se non si è scelto di abilitare e assegnare l'indirizzo IPv6, la finestra di dialogo non verrà visualizzata.

    
    </div>

17. Fare clic su **fine**.
    
    <div>
    

    > [!NOTE]  
    > Si vedrà ora il primo server perimetrale creato nel pool nella finestra di dialogo <STRONG>Definisci computer in questo pool</STRONG> .

    
    </div>

18. In **definire i computer in questo pool**fare clic su **Aggiungi**e quindi ripetere i passaggi da 11 a 14 per il secondo Edge Server che si vuole aggiungere al pool di Edge.

19. Dopo aver ripetuto i passaggi da 11 a 14, fare clic su **Avanti** in **Definisci i computer in questo pool**.
    
    <div>
    

    > [!NOTE]  
    > A questo punto, è possibile visualizzare entrambi i server perimetrali nel pool.

    
    </div>

20. Se si è scelto di usare NAT, viene visualizzata una finestra di dialogo. In **indirizzo IP pubblico**Digitare gli indirizzi IPv4 e IPv6 (in base alle esigenze) pubblici da tradurre tramite NAT e quindi fare clic su **Avanti**.
    
    <div>
    

    > [!NOTE]  
    > Dovrebbe essere l'indirizzo IP esterno del bordo A/V.

    
    </div>

21. In **Definisci l'hop successivo**, nell'elenco del **pool hop successivo** , selezionare il nome del pool interno, che può essere un pool di front-end o un pool di Standard Edition. In alternativa, se la distribuzione include un amministratore, selezionare il nome del direttore. Quindi fare clic su **Avanti**.

22. In **Associa pool Front End**specificare uno o più pool interni, che possono includere i pool Front-end e i server Standard Edition, da associare a questo Edge Server, selezionando i nomi dei pool interni che devono usare questo Edge Server per la comunicazione con utenti esterni supportati.
    
    <div>
    

    > [!NOTE]  
    > Solo un pool di Edge con bilanciamento del carico o un singolo Edge Server può essere associato a ogni pool interno per il traffico A/V. Se si dispone già di un pool interno associato a un pool di Edge o un server perimetrale, viene visualizzato un avviso che indica che il pool interno è già associato a un pool di Edge o a un server perimetrale. Se si seleziona un pool già associato a un altro Edge Server, l'associazione verrà modificata.

    
    </div>

23. Fare clic su **fine**.

24. Pubblicare la topologia.

</div>

<div>

## <a name="to-define-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a>Per definire la topologia di un pool di server Edge con bilanciamento del carico hardware

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.

2.  Nell'albero della console espandere il sito in cui si vogliono distribuire i server perimetrali.

3.  Fare clic con il pulsante destro del mouse su **pool di bordi**e quindi scegliere **nuovo pool di bordi**.

4.  In **definire il nuovo pool di bordi**fare clic su **Avanti**.

5.  In **definire il nome di dominio completo del pool Edge**eseguire le operazioni seguenti:
    
      - In **FQDN**Digitare il nome di dominio completo (FQDN) scelto per il lato interno del pool di bordi.
        
        <div>
        

        > [!IMPORTANT]  
        > Il nome specificato per il pool deve essere il nome del pool di Edge interno. Questa operazione deve essere definita come FQDN. Generatore di topologie usa gli FQDN e non i nomi brevi. Usare solo caratteri standard (tra cui A-Z, a-z, 0-9 e segni meno) durante l'assegnazione di nomi di dominio completi di Lync Server, Edge Server e pool. Non usare caratteri Unicode o carattere di sottolineatura. I caratteri non standard di un nome di dominio completo spesso non sono supportati dal DNS esterno e dalle CA pubbliche (quando il nome di dominio completo deve essere assegnato a SN nel certificato).

        
        </div>
    
    <!-- end list -->
    
      - Fare clic su **pool di computer multipli**e quindi su **Avanti**.

6.  In **Seleziona funzionalità** eseguire le operazioni seguenti:
    
      - Se si prevede di usare un solo nome di dominio completo e un indirizzo IP per il servizio di accesso SIP, Lync Server Web Conferencing Service e A/V Edge Services, selezionare la casella **di controllo Usa un solo nome fqdn & indirizzo IP** .
    
      - Se si prevede di abilitare la Federazione, selezionare la casella **di controllo Abilita federazione per questo pool di bordi (porta 5061)** .
        
        <div>
        

        > [!NOTE]  
        > Puoi selezionare questa opzione, ma solo un bordo o un server perimetrale nell'organizzazione può essere pubblicato esternamente per la Federazione. Tutti gli accessi da parte di utenti federati, inclusi gli utenti di messaggistica istantanea pubblica, passano attraverso lo stesso pool di Edge o un singolo Edge Server. Se ad esempio nella distribuzione è incluso un pool di server perimetrali o un singolo server perimetrale distribuito a New York e uno distribuito a Londra e si abilita il supporto della federazione per il pool di server perimetrali o il singolo server perimetrale di New York, il traffico di segnalazione per gli utenti federati passerà attraverso tale pool o server. Ciò avviene persino per le comunicazioni con gli utenti di Londra, anche se un utente interno di Londra che chiama un utente federato di Londra utilizza il pool o il server perimetrale di Londra per il traffico A/V.

        
        </div>
    
      - Se si prevede di supportare il protocollo XMPP (Extensible Messaging and Presence Protocol) per la distribuzione, selezionare la casella di controllo **Abilita federazione XMPP (porta 5269)**

7.  Fare clic su **Avanti**.

8.  In **Seleziona opzioni IP**eseguire le operazioni seguenti:
    
      - **Abilitare IPv4 sull'interfaccia interna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv4 all'interfaccia interna del server perimetrale o del pool Edge
    
      - **Abilitare IPv6 sull'interfaccia interna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv6 all'interfaccia interna del server perimetrale o del pool Edge
    
      - **Abilitare IPv4 sull'interfaccia esterna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv4 all'interfaccia esterna del server perimetrale o del pool Edge
    
      - **Abilitare IPv6 sull'interfaccia esterna**: selezionare la casella di controllo se si vuole applicare un indirizzo IPv6 all'interfaccia esterna del server perimetrale o del pool Edge
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>Non selezionare la</STRONG> casella di controllo <STRONG>l'indirizzo IP esterno del pool di Edge viene tradotto da NAT</STRONG> . NAT (Network Address Translation) non è supportato quando si usa il bilanciamento del carico hardware.

    
    </div>

9.  In **FQDN esterni**eseguire le operazioni seguenti:
    
      - Se in **Seleziona funzionalità** si è scelto di usare un singolo FQDN e un indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio a/V Edge, digitare il nome di dominio completo esterno in **Access SIP**.
        
        <div>
        

        > [!NOTE]  
        > Se si sceglie di selezionare questa opzione, è necessario specificare un numero di porta diverso per ogni servizio Edge (impostazioni di porta consigliate: 5061 per Access Edge service, 444 per Web Conferencing Edge service e 443 per un/V Edge Server). Selezionando questa opzione, è possibile evitare potenziali problemi di connettività e semplificare la configurazione perché è quindi possibile usare lo stesso numero di porta, ad esempio 443, per tutti e tre i servizi.

        
        </div>
    
      - Se in **Seleziona funzionalità** non si è scelto di usare un singolo nome di dominio completo e indirizzo IP, digitare il nome di dominio completo scelto per il lato pubblico del pool di Edge per l' **accesso SIP**. In **Web Conferencing**Digitare il nome di dominio completo scelto per il lato pubblico del pool di Edge. In **audio/video**Digitare il nome di dominio completo scelto per il lato pubblico del pool di bordi. Usare le porte predefinite.
        
        <div>
        

        > [!NOTE]  
        > Questi saranno gli FQDN di Virtual IP (VIP) pubblicamente di fronte per il pool.

        
        </div>

10. Fare clic su **Avanti**.

11. In **definire i computer in questo pool**fare clic su **Aggiungi**.

12. In **definire gli indirizzi IP esterni**eseguire le operazioni seguenti:
    
      - Se si è scelto di usare un singolo FQDN e un indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare l'indirizzo IPv4 esterno dell'Edge Server in **Access**SIP. indirizzo IP esterno dell'Edge Server in **Access SIP**.
    
      - Se non si è scelto di usare un singolo FQDN e un indirizzo IP per l'accesso SIP, il servizio di conferenza Web e il servizio di conferenza telefonica A/V, digitare l'indirizzo IP scelto per il lato pubblico di questo server Edge pool per l' **accesso SIP**. In **Web Conferencing**Digitare l'indirizzo IP scelto per il lato pubblico di questo server Edge pool. In **conferenze telefoniche a/V**Digitare l'indirizzo IP scelto per il lato pubblico di questo server Edge pool.

13. Fare clic su **Avanti**.

14. Se si è scelto di abilitare gli indirizzi IPv6, in **definire gli indirizzi IP esterni**eseguire le operazioni seguenti:
    
      - Se si è scelto di usare un singolo FQDN e un indirizzo IP per l'accesso SIP, il servizio Web Conferencing e il servizio A/V Edge, digitare l'indirizzo IPv6 esterno dell'Edge Server in **Access SIP**.
    
      - Se non si è scelto di usare un singolo FQDN e un indirizzo IP per l'accesso SIP, il servizio di conferenza Web e il servizio di conferenza telefonica A/V, digitare l'indirizzo IPv6 scelto per il lato pubblico di questo server Edge pool per l' **accesso SIP**. In servizi di **conferenza Web**Digitare l'indirizzo IPv6 scelto per il lato pubblico di questo server Edge pool. In **conferenze telefoniche a/V**Digitare l'indirizzo IPv6 scelto per il lato pubblico di questo server Edge pool.
    
    <div>
    

    > [!NOTE]  
    > Se non si è scelto di abilitare e assegnare l'indirizzo IPv6, la finestra di dialogo non verrà visualizzata.

    
    </div>

15. Fare clic su **fine**.
    
    <div>
    

    > [!NOTE]  
    > Si vedrà ora il primo server perimetrale creato nel pool nella finestra di dialogo <STRONG>Definisci computer in questo pool</STRONG> .

    
    </div>

16. In **definire i computer in questo pool**fare clic su **Aggiungi**e quindi ripetere i passaggi da 11 a 14 per il secondo Edge Server che si vuole aggiungere al pool di Edge.

17. Dopo aver ripetuto i passaggi da 11 a 14, fare clic su **Avanti** in **Definisci i computer in questo pool**.
    
    <div>
    

    > [!NOTE]  
    > A questo punto, è possibile visualizzare entrambi i server perimetrali nel pool.

    
    </div>

18. In **Definisci l'hop successivo**, nell'elenco del **pool hop successivo** , selezionare il nome del pool interno, che può essere un pool di front-end o un pool di Standard Edition. In alternativa, se la distribuzione include un amministratore, selezionare il nome del direttore. Quindi fare clic su **Avanti**.

19. In **Associa pool Front End**specificare uno o più pool interni, che possono includere i pool Front-end e i server Standard Edition, da associare a questo Edge Server, selezionando i nomi dei pool interni che devono usare questo Edge Server per la comunicazione con utenti esterni supportati.
    
    <div>
    

    > [!NOTE]  
    > Solo un pool di Edge con bilanciamento del carico o un singolo Edge Server può essere associato a ogni pool interno per il traffico A/V. Se si dispone già di un pool interno associato a un pool di Edge o un server perimetrale, viene visualizzato un avviso che indica che il pool interno è già associato a un pool di Edge o a un server perimetrale. Se si seleziona un pool già associato a un altro Edge Server, l'associazione verrà modificata.

    
    </div>

20. Fare clic su **fine**.

21. Pubblicare la topologia.

</div>

</div>

<span> </span>

</div>

</div>

</div>

