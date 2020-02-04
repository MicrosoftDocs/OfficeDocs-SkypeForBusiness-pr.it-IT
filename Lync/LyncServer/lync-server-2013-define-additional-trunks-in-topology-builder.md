---
title: 'Lync Server 2013: definire trunk aggiuntivi in Generatore di topologie'
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
ms.openlocfilehash: c55e8073bd1ad1bb2db69096e4e58aa2b148e775
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a>Definire trunk aggiuntivi in Generatore di topologia in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-04_

Seguire questa procedura per usare generatore di topologie per definire un trunk aggiuntivo a cui è possibile associare un *peer* a un Mediation Server. Un peer fornisce agli utenti abilitati per VoIP aziendale la connettività alla rete PSTN (Public Switched Telephone Network). Un peer può essere un gateway PSTN, un IP-PBX o un SBC (Session Border Controller) per un provider di servizi di telefonia Internet (ITSP). Il trunk definisce questa connessione tra il Mediation Server e il peer. È possibile definire più trunk per Mediation Server. Un Mediation Server può essere associato a più peer.

Un trunk è una connessione logica tra un Mediation Server e un gateway identificato in modo univoco dalla tupla:

{Nome completo di Mediation Server, porta di attesa di Mediation Server (TLS o TCP): IP gateway e FQDN, porta di ascolto del gateway}

<div>


> [!NOTE]  
> Questo argomento presuppone che sia stato configurato un gateway PSTN e un trunk radice con almeno un server o un pool di mediazione autonomo o indipendente, come descritto in <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">definire un gateway in Generatore di topologie in Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

<div>


> [!NOTE]  
> Questo argomento presuppone che sia stato configurato almeno un pool Front end o un server Standard Edition in almeno un sito centrale, come descritto in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definire e configurare un pool Front end o un server Standard Edition in Lync server 2013</A> e <A href="lync-server-2013-publish-the-topology.md">pubblicare la topologia in Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>Per definire un trunk aggiuntivo tra un Mediation Server e un peer gateway

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.

2.  In Lync Server 2013, il nome del sito, i **componenti condivisi**, fare clic con il pulsante destro del mouse sul nodo **Trunks** e quindi scegliere **nuovo trunk**.
    
    ![Schermata della struttura di file di Generatore di topologie di Lync Server](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Schermata della struttura di file di Generatore di topologie di Lync Server")

3.  In **Definisci nuovo trunk**specificare un nome descrittivo per identificare in modo univoco il trunk. Non è possibile avere due trunk con lo stesso nome.
    
    <div>
    

    > [!NOTE]  
    > Se si specifica TLS (Transport Layer Security) come tipo di trasporto, è necessario specificare il nome di dominio completo anziché l'indirizzo IP del peer del Mediation Server.

    
    </div>

4.  In **gateway PSTN associato**selezionare il peer del gateway PSTN da associare al trunk.
    
    ![Impostazioni delle proprietà del peer gateway PSTN per trunk](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Impostazioni delle proprietà del peer gateway PSTN per trunk")

5.  In **porta di attesa per gateway PSTN**Digitare la porta di attesa che il peer (gateway PSTN, IP-PBX o SBC) riceva i messaggi SIP dal Mediation Server che deve essere associato a questo trunk. Le porte peer predefinite sono 5066 per TCP (Transmission Control Protocol) e 5067 per Transport Layer Security (TLS). Le porte predefinite Survivable Branch Appliance sono 5081 per TCP e 5082 per TLS.

6.  In **protocollo di trasporto SIP**fare clic sul tipo di trasporto usato dal peer.
    
    <div>
    

    > [!NOTE]  
    > Per motivi di sicurezza, ti consigliamo vivamente di distribuire un peer al Mediation Server che può usare TLS.

    
    </div>

7.  In **Mediation Server associato**selezionare il pool di Mediation Server da associare al trunk radice di questo peer

8.  In **porta Mediation Server associata**Digitare la porta di attesa in cui il Mediation Server riceverà i messaggi SIP dal peer.
    
    <div>
    

    > [!NOTE]  
    > Con il supporto di più trunk in Lync Server 2013, non è possibile configurare due trunk con nomi trunk diversi con la stessa <STRONG>porta del server di mediazione associata</STRONG> e la <STRONG>porta di ascolto per gateway IP/PSTN</STRONG>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Con il supporto di più trunk in Lync Server 2013, è possibile definire più porte di segnalazione SIP nel server Mediation per la comunicazione con più peer. Quando si definisce un trunk, il numero di <STRONG>porta del server di mediazione associato</STRONG> deve essere compreso nell'intervallo delle porte in attesa per il rispettivo protocollo consentito dal server Mediation. Questo intervallo di porte è definito in Lync Server 2013 e nei pool di Mediation Server. Fare clic con il pulsante destro del mouse sul pool di Mediation Server e scegliere <STRONG>modifica proprietà</STRONG>. Specificare l'intervallo di porte nel campo <STRONG>porte in attesa</STRONG> .

    
    </div>

9.  Fare clic su **OK**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Modificare un trunk in Generatore di topologia in Lync Server 2013](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

