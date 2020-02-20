---
title: 'Lync Server 2013: definire ulteriori trunk in Generatore di topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define additional trunks in Topology Builder
ms:assetid: e68b8377-50a2-452a-bf5c-910929e34236
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721915(v=OCS.15)
ms:contentKeyID: 49733849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f4c31dc9b3e23f591e1084ba649bf00a4c8a0f3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a>Definire ulteriori trunk in Generatore di topologie in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-04_

Eseguire la procedura seguente per utilizzare il generatore di topologie per definire un trunk aggiuntivo a cui è possibile associare un *peer* a un Mediation Server. Un peer fornisce gli utenti abilitati per VoIP aziendale con connettività alla rete PSTN (Public Switched Telephone Network). Un peer può essere un gateway PSTN, un IP-PBX, o un SBC (Session Border Controller) per un provider di servizi di telefonia Internet (ITSP). Il trunk definisce la connessione tra il Mediation Server e il peer. È possibile definire più trunk per Mediation Server. Un Mediation Server può essere associato a più peer.

Un trunk è una connessione logica tra un Mediation Server e un gateway identificato in modo univoco dalla tupla:

{FQDN Mediation Server, porta di attesa Mediation Server (TLS o TCP): IP e FQDN del gateway, porta di attesa del gateway}

<div>


> [!NOTE]  
> In questo argomento si presuppone che sia installato un gateway PSTN e un trunk radice con almeno un Mediation Server collocato o autonomo, come descritto in <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">define a gateway in Generatore di topologie in Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

<div>


> [!NOTE]  
> In questo argomento si presuppone che sia stato configurato almeno un pool Front end o un server Standard Edition in almeno un sito centrale, come descritto in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definire e configurare un pool Front end o un server Standard Edition in Lync server 2013</A> e <A href="lync-server-2013-publish-the-topology.md">pubblicare la topologia in Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>Per definire un ulteriore Trunk tra un Mediation Server e un peer gateway

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.

2.  In Lync Server 2013, nome del sito, **componenti condivisi**, fare clic con il pulsante destro del mouse sul nodo **Trunks** e quindi scegliere **nuovo trunk**.
    
    ![Schermata struttura file del generatore di topologie di Lync Server](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Schermata struttura file del generatore di topologie di Lync Server")

3.  In **Definisci nuovo trunk**, specificare un nome descrittivo per identificare in modo univoco il trunk. Non è possibile definire due trunk con lo stesso nome.
    
    <div>
    

    > [!NOTE]  
    > Se si specifica TLS (Transport Layer Security) come tipo di trasporto, è necessario specificare il nome di dominio completo anziché l'indirizzo IP del peer del Mediation Server.

    
    </div>

4.  In **Gateway PSTN associato** selezionare il peer gateway PSTN da associare al trunk.
    
    ![Impostazioni delle proprietà per il peer gateway PSTN per trunk](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Impostazioni delle proprietà per il peer gateway PSTN per trunk")

5.  In **porta di attesa per gateway PSTN**Digitare la porta di attesa che il peer (gateway PSTN, IP-PBX o SBC) riceverà i messaggi SIP dal Mediation Server che deve essere associato a questo trunk. Le porte predefinite per il peer sono 5066 per TCP (Transmission Control Protocol) e 5067 per TLS (Transport Layer Security). Le porte di Survivable Branch Appliance predefinite sono 5081 per TCP e 5082 per TLS.

6.  In **Protocollo trasporto SIP** fare clic sul tipo di di trasporto utilizzato dal peer.
    
    <div>
    

    > [!NOTE]  
    > Per motivi di sicurezza, è consigliabile distribuire un peer al Mediation Server in grado di utilizzare TLS.

    
    </div>

7.  In **Mediation Server associato**selezionare il pool di Mediation Server da associare al trunk radice di questo peer

8.  In **porta Mediation Server associato**Digitare la porta di attesa che il Mediation Server riceverà messaggi SIP dal peer.
    
    <div>
    

    > [!NOTE]  
    > Con il supporto per più trunk in Lync Server 2013, è possibile configurare due trunk con nomi trunk diversi con la stessa <STRONG>porta di Mediation Server associata</STRONG> e la <STRONG>porta di attesa per gateway IP/PSTN</STRONG>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Con il supporto di più trunk in Lync Server 2013, è possibile definire più porte di segnalazione SIP sul Mediation Server per la comunicazione con più peer. Quando si definisce un trunk, il numero di <STRONG>porta del Mediation Server associato</STRONG> deve trovarsi all'interno dell'intervallo delle porte di attesa per il rispettivo protocollo consentito dal Mediation Server. Questo intervallo di porte è definito in Lync Server 2013 e nei pool di Mediation Server. Fare clic con il pulsante destro del mouse sul pool di Mediation Server pertinente e scegliere <STRONG>modifica proprietà</STRONG>. Specificare l'intervallo di porte nel campo <STRONG>Porte di attesa</STRONG>.

    
    </div>

9.  Fare clic su **OK**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Modificare un trunk in Generatore di topologie in Lync Server 2013](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

