---
title: 'Lync Server 2013: ripristino di emergenza del server perimetrale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edge Server disaster recovery
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49733545
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 519243475f5452cebc6fff82cc54f267bb8b36fd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136353"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a>Ripristino di emergenza del server perimetrale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-03-12_

Come per gli altri ruoli del server, il modo migliore per garantire la disponibilità elevata dei server perimetrali consiste nel distribuire più server perimetrali in pool in ogni sito. In caso di blocco di un server perimetrale, i servizi Edge verranno forniti dagli altri server del pool.

Per abilitare le procedure di ripristino di emergenza è necessario distribuire pool di server perimetrali distinti in siti separati. Non è necessario accoppiare esplicitamente i pool di server perimetrali come nel caso dei pool Front End, poiché la semplice presenza di più pool di server perimetrali consente di proseguire il lavoro anche in caso di blocco di un intero pool di server perimetrali. Nelle sezioni seguenti sono disponibili informazioni dettagliate sul ripristino di emergenza per le varie funzioni dei server perimetrali.

<div>

## <a name="remote-access"></a>Accesso remoto

Se si dispone di più siti, ognuno con un pool di server perimetrali e un intero pool di perimetri ha esito negativo, i servizi di accesso remoto continueranno a funzionare senza l'intervento dell'amministratore. Quando si creano pool di server perimetrali in siti diversi, non è possibile utilizzare lo stesso nome di dominio completo. Ogni pool di server perimetrali deve disporre di FQDN univoci (interno ed esterno). I pool di server perimetrali non utilizzano le regole di pubblicazione del proxy inverso per comunicare con i front-end. Il failover automatico si verifica quando il client riesegue la query sui record del servizio DNS di accesso remoto e gli utenti remoti vengono instradati ai server perimetrali in un altro sito. Il client tenta ogni FQDN del perimetro esterno in base alla priorità dei record SRV DNS.

<div>


> [!NOTE]  
> Affinché il failover funzioni correttamente, verificare che il firewall consenta ai front end server di ogni pool di comunicare con tutti i server perimetrali.



</div>

</div>

<div>

## <a name="federation"></a>Federazione

Per le relazioni di federazione con altre organizzazioni che eseguono Lync Server, le richieste di federazione in ingresso continueranno a funzionare fino a quando si dispone di soluzioni come Geo-DNS GTM. È importante comprendere che il failover federativo non fornisce il failover con priorità nei record SRV. Una soluzione fornita in precedenza può aiutare a fornire le funzionalità di ripristino di emergenza per la Federazione in ingresso.

La federazione in uscita viene sempre configurata attraverso un server perimetrale o un pool di server perimetrali pubblicato nell'organizzazione. Se tale pool è inattivo, è necessario utilizzare il Generatore di topologie per modificare la route di federazione in ingresso in modo che venga utilizzato un pool di server perimetrali ancora in esecuzione. Per informazioni dettagliate, vedere [failover del pool di server perimetrali utilizzato per la Federazione di Lync in Lync server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

</div>

<div>

## <a name="xmpp-federation"></a>Federazione XMPP

Per la federazione XMPP, in caso di blocco del pool di server perimetrali designato come gateway XMPP si verificherà un errore sia nel traffico in ingresso che in quello in uscita. Per ripristinare il funzionamento della federazione XMPP è necessario modificarla in modo che venga utilizzato un pool di server perimetrali diverso. Per informazioni dettagliate, vedere [failover del pool di server perimetrali utilizzato per la Federazione XMPP in Lync 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a>Il pool di server perimetrali è in errore, ma il pool Front End è ancora in esecuzione

Se un pool di server perimetrali di un sito è in errore, ma il pool Front End dello stesso sito è ancora in esecuzione, sarà necessario modificare il pool Front End in modo che durante il periodo di non disponibilità del primo pool venga utilizzato un pool di server perimetrali diverso presso un altro sito. Per ulteriori informazioni, vedere [Changing the Edge pool associato a un pool Front end in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

