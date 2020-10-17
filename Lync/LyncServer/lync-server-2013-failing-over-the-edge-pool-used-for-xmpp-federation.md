---
title: 'Lync Server 2013: failover del pool di Edge utilizzato per la Federazione XMPP'
description: 'Lync Server 2013: failover del pool di Edge utilizzato per la Federazione XMPP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for XMPP federation
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49733659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccdfe119258b4d09ddedefb22d0272d72003bf04
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554902"
---
# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a>Failover del pool di server perimetrali utilizzato per la Federazione XMPP in Lync 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-19_

All'interno dell'organizzazione un solo pool di server perimetrali è designato come pool da usare per la federazione XMPP. Se questo pool non è disponibile, per consentire il funzionamento della federazione XMPP è necessario eseguire il failover di questa a un altro pool di server perimetrali.

Quando si installano i pool di server perimetrali e si abilita la federazione XMPP per la prima volta, per semplificare il processo di ripristino di emergenza della federazione XMPP è possibile impostare record DNS SRV esterni per tutti i pool di server perimetrali, invece che per uno solo. Per ciascuno di questi record SRV deve essere impostata una priorità diversa. Tutto il traffico di federazione XMPP passa per il pool con il record SRV con la priorità più alta. Per ulteriori informazioni sull'abilitazione e sulla configurazione della Federazione XMPP, vedere [Setting up XMPP Federation in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).

Nella procedura seguente EdgePool1 è il pool di server perimetrali che ospita la federazione XMPP originariamente ed EdgePool2 è il pool che la ospiterà.

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a>Failover del pool di server perimetrali usato per la federazione XMPP

1.  Se oltre al pool di server perimetrali non disponibile non ne sono stati distribuiti altri, distribuirne uno. Per informazioni dettagliate, vedere [Deploying External User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).

2.  In ogni server perimetrale del nuovo pool di server perimetrali che ora ospita la federazione XMPP (EdgePool2) eseguire il cmdlet seguente:
    
        Stop-CsWindowsService

3.  Eseguire il cmdlet seguente per puntare la route della federazione XMPP a EdgePool2:
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    In questo esempio, Site2 è il sito che contiene il pool di server perimetrali che ospiterà la route della federazione XMPP ed EdgeServer2.contoso.com è l'FQDN di un server perimetrale del pool.

4.  Nel server DNS esterno modificare il record DNS A in modo che la federazione XMPP punti a EdgeServer2.contoso.com.

5.  Se per la federazione XMPP non è disponibile un record DNS SRV corrispondente al pool di server perimetrali che ospiterà la federazione XMPP, è necessario aggiungerlo così com'è illustrato nell'esempio seguente. Il valore della porta del record SRV deve essere 5269.
    
        _xmpp-server._tcp.contoso.com

6.  Verificare che il pool di server perimetrali che ospiterà la federazione XMPP abbia la porta 5269 aperta verso l'esterno.

7.  Avviare i servizi in tutti i server perimetrali del pool che ospiterà la federazione XMPP:
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

