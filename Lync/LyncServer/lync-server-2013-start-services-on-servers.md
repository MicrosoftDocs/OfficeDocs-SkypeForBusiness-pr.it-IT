---
title: 'Lync Server 2013: Avviare servizi nei server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start services on servers
ms:assetid: fa26eaed-0529-4f32-9f3f-f32c4bd4b1c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413059(v=OCS.15)
ms:contentKeyID: 48185912
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e6474071e7f95228f3c04c4931b4f899df68b40
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="start-services-on-servers-for-lync-server-2013"></a>Avviare servizi nei server per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-09-03_

Per completare correttamente questa procedura, è necessario avere effettuato l'accesso come utente membro del gruppo RTCUniversalServerAdmins o avere le autorizzazioni corrette Delegate. Per informazioni dettagliate sulla delega delle autorizzazioni, vedere l'argomento [autorizzazioni di configurazione per i delegati in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

Dopo l'installazione dell'archivio di configurazione locale nei server, installare i componenti di Lync Server 2013 e configurare i certificati in un front end server o front end server, è necessario avviare i servizi di Lync Server 2013 nel server. Usare la procedura seguente per avviare i servizi in ogni server front-end della distribuzione.

<div>

## <a name="to-start-services-on-a-standard-edition-or-front-end-server"></a>Per avviare i servizi in una versione standard o front end server

1.  Nella pagina **Lync server 2013** della distribuzione guidata di Lync Server fare clic su **Esegui** accanto al **passaggio 4: avviare i servizi**.

2.  Nella pagina **Start Services** fare clic su **Avanti** per avviare i servizi di Lync Server nel server.

3.  Nella pagina **esecuzione dei comandi** , dopo aver avviato tutti i servizi, fare clic su **fine**.
    
    <div>
    

    > [!IMPORTANT]  
    > Il comando per avviare i servizi sul server è un metodo di sforzo ottimale per segnalare che i servizi sono effettivamente stati avviati. Potrebbe non corrispondere allo stato effettivo del servizio. È consigliabile usare lo stato del servizio di passaggio <STRONG>(facoltativo)</STRONG> subito dopo i <STRONG>Servizi Start</STRONG> per aprire Microsoft Management Console (MMC) e verificare che i servizi siano stati avviati correttamente. Se un servizio di Lync Server non è stato avviato, è possibile fare clic con il pulsante destro del mouse su tale servizio in MMC e quindi scegliere <STRONG>Avvia</STRONG>.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

