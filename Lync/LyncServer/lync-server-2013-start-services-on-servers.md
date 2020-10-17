---
title: 'Lync Server 2013: avviare i servizi nei server'
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
ms.openlocfilehash: 7d276dfdedacdcb00b4cc19a486fea1103c0bc8d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532963"
---
# <a name="start-services-on-servers-for-lync-server-2013"></a>Avviare servizi nei server per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-09-03_

Per eseguire questa procedura, è necessario accedere come utente membro del gruppo RTCUniversalServerAdmins o disporre della delega delle autorizzazioni appropriate. Per informazioni dettagliate su come delegare le autorizzazioni, vedere l'argomento [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

Dopo l'installazione dell'archivio di configurazione locale nei server, l'installazione dei componenti di Lync Server 2013 e la configurazione dei certificati in un front end server o front end server, è necessario avviare i servizi Lync Server 2013 sul server. Utilizzare la procedura seguente per avviare i servizi in ogni front end server della distribuzione.

<div>

## <a name="to-start-services-on-a-standard-edition-or-front-end-server"></a>Per avviare i servizi in un server Standard Edition o front end

1.  Nella distribuzione guidata di Lync Server, nella pagina **Lync server 2013** , fare clic su **Esegui** accanto a **passaggio 4: Avvia servizi**.

2.  Nella pagina **Avvia servizi** fare clic su **Avanti** per avviare i servizi Lync Server nel server.

3.  Nella pagina **Esecuzione comandi in corso**, dopo l'avvio di tutti i servizi, fare clic su **Fine**.
    
    <div>
    

    > [!IMPORTANT]  
    > Il comando per avviare i servizi nel server è un metodo di sforzo ottimale per segnalare che i servizi sono stati effettivamente avviati. Potrebbe non rispecchiare lo stato effettivo del servizio. È consigliabile utilizzare lo stato del servizio di passaggio <STRONG>(facoltativo)</STRONG> subito dopo l' <STRONG>avvio dei servizi</STRONG> per aprire Microsoft Management Console (MMC) e verificare che i servizi siano stati avviati correttamente. Se un servizio di Lync Server non è stato avviato, è possibile fare clic con il pulsante destro del mouse su tale servizio in MMC e quindi scegliere <STRONG>Avvia</STRONG>.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

