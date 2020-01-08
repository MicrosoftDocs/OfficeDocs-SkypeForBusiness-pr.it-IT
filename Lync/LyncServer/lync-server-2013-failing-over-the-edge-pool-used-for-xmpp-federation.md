---
title: 'Lync Server 2013: Failover del pool di server perimetrali utilizzato per la federazione di XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over the Edge pool used for XMPP federation
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49733659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 551774c070ebafd25376d220b20acccc8c573af2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a>Failover del pool di server perimetrali utilizzato per la federazione di XMPP in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-19_

Nell'organizzazione esiste un pool di bordi designato come pool da usare per la Federazione XMPP. Se il pool scende, è necessario eseguire il failover della Federazione XMPP per usare un pool di bordi diverso prima che la Federazione XMPP possa funzionare di nuovo.

La prima volta che si installano pool di bordi e si Abilita la Federazione XMPP, è possibile semplificare il processo di ripristino di emergenza impostando i record SRV DNS esterni per tutti i pool di Edge per la Federazione XMPP, anziché solo uno. Ognuno di questi record SRV deve avere un set di priorità diverso. Tutto il traffico federativo XMPP passa attraverso il pool con il record SRV con la massima priorità. Per altre informazioni sull'abilitazione e la configurazione della Federazione XMPP, vedere [configurazione della Federazione XMPP in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).

Nella procedura seguente, EdgePool1 è il pool che ospitava originariamente la Federazione XMPP e EdgePool2 è il pool che ora ospiterà la Federazione XMPP.

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a>Errori nel pool di bordi usato per la Federazione XMPP

1.  Se non si dispone già di un altro pool di Edge distribuito, oltre a quello attualmente in calo, distribuire il pool. Per informazioni dettagliate, vedere [distribuzione dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).

2.  In ogni Edge Server nel nuovo pool di Edge che ora ospiterà la Federazione XMPP (EdgePool2), eseguire il cmdlet seguente:
    
        Stop-CsWindowsService

3.  Eseguire il cmdlet seguente per reindirizzare la route federativo XMPP a EdgePool2:
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    In questo esempio, sito2 è il sito che contiene il pool di bordi che ora ospiterà la route federativa XMPP e EdgeServer2.contoso.com è il nome di dominio completo di un server perimetrale in tale pool.

4.  Nel server DNS esterno modificare il record DNS per la Federazione XMPP in punti a EdgeServer2.contoso.com.

5.  Se non si ha già un record SRV DNS per la Federazione XMPP che si risolve nel pool di Edge che ora ospiterà la Federazione XMPP, è necessario aggiungerlo, come nell'esempio seguente. Questo record SRV deve avere un valore di porta 5269.
    
        _xmpp-server._tcp.contoso.com

6.  Verificare che il pool di Edge che ora ospita la Federazione XMPP contenga la porta 5269 aperta esternamente.

7.  Avviare i servizi in tutti i server perimetrali nel pool di Edge, che ora ospiterà la Federazione XMPP:
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

