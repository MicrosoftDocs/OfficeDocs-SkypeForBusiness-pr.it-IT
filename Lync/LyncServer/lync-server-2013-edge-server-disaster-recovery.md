---
title: 'Lync Server 2013: Ripristino di emergenza dei server perimetrali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Edge Server disaster recovery
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49733545
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d19e5a606c3217ad7653fd4c3c885a97aafdb5ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980640"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a>Ripristino di emergenza dei server perimetrali in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-03-12_

Come per gli altri ruoli del server, il modo migliore per garantire elevata disponibilità agli Edge Server consiste nel distribuire più Edge Server nei pool di ogni sito. Se si abbassa un server perimetrale, gli altri server del pool continueranno a includere servizi Edge.

Per abilitare le procedure di ripristino di emergenza, è necessario disporre di pool di Edge Server distinti distribuiti in siti distinti. Non è necessario associare in modo esplicito i pool di bordi come si fa con i pool di front-end, ma avere più pool di bordi offre ancora la disponibilità a continuare se un intero pool di bordi scende. Nelle sezioni seguenti sono disponibili informazioni dettagliate sul ripristino di emergenza per le varie funzioni di Edge Server.

<div>

## <a name="remote-access"></a>Accesso remoto

Se si hanno più siti, ognuno con un pool di Edge Server e un intero pool di bordi non riesce, i servizi di accesso remoto continueranno a funzionare senza bisogno di un'azione di amministratore. Quando si creano pool di bordi in siti diversi, non è possibile usare lo stesso nome di dominio completo. Ogni pool di bordi deve avere nomi di dominio completi univoci (interni ed esterni). I pool di bordi non usano regole di pubblicazione del proxy inverso per comunicare con i server front-end. Il failover automatico si verifica quando il client esegue di nuovo una query sui record del servizio DNS di accesso remoto e gli utenti remoti vengono instradati agli Edge Server in un altro sito. Il client tenta ogni FQDN del bordo esterno in base alla priorità dei record SRV DNS.

<div>


> [!NOTE]  
> Affinché il failover funzioni correttamente, verificare che il firewall consenta ai server front-end di ogni pool di comunicare con tutti i server perimetrali.



</div>

</div>

<div>

## <a name="federation"></a>Federazione

Per le relazioni federative con altre organizzazioni che gestiscono Lync Server, le richieste di federazione in ingresso continueranno a funzionare purché si disponga di soluzioni come Geo-DNS GTM. È importante comprendere che il failover federativo non offre il failover con priorità nei record SRV. Una soluzione fornita in precedenza può aiutare a fornire funzionalità di ripristino di emergenza per la Federazione in ingresso.

La Federazione in uscita viene sempre configurata tramite un pool Edge o un server perimetrale pubblicato nell'organizzazione. Se il pool di Edge è sceso, è necessario usare generatore di topologie per modificare la route della Federazione in uscita per usare un pool di bordi ancora in corso. Per informazioni dettagliate, vedere [errori nel pool di Edge usato per la federazione Lync Server in Lync server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

</div>

<div>

## <a name="xmpp-federation"></a>Federazione XMPP

Per la Federazione XMPP, il traffico in uscita e in uscita non riuscirà se il pool di bordi designato come gateway federativo XMPP scende. Per rendere di nuovo possibile il lavoro della Federazione XMPP, devi modificare la Federazione XMPP per usare un pool di bordi diverso. Per informazioni dettagliate, vedere [errori nel pool di Edge usato per la Federazione XMPP in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a>Il pool di Edge non riesce ma il pool Front-End è ancora in corso

Se un pool di Edge non riesce in un sito, ma il pool Front-end in tale sito è ancora in esecuzione, sarà necessario cambiare il pool Front-end per usare un pool di bordi diverso in un sito diverso mentre il primo pool Edge è in calo. Per altre informazioni, vedere [modifica del pool di bordi associato a un pool Front-end in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

