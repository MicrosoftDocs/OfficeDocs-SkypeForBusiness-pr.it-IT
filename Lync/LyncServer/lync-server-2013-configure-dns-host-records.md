---
title: 'Lync Server 2013: configurare i record host DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS Host records
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398593(v=OCS.15)
ms:contentKeyID: 48184577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e96c23741430f17b6d343606526df230f74c032
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537133"
---
# <a name="configure-dns-host-records-for-lync-server-2013"></a>Configurare i record host DNS per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-01_

Per eseguire correttamente questa procedura, è necessario connettersi al server o al dominio almeno come membro del gruppo Domain Admins o DnsAdmins.

<div>

## <a name="to-configure-dns-host-a-records"></a>Per configurare i record A host DNS

1.  Nel server DNS (Domain Name System) fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi **DNS**.

2.  Nell'albero della console per il dominio espandere **zone di ricerca diretta**e quindi fare clic con il pulsante destro del mouse sul dominio in cui verrà installato Lync Server 2013.

3.  Scegliere **Nuovo host (A o AAAA)**.

4.  Fare clic su **Nome** e digitare il nome host per il pool. Il nome di dominio viene presupposto dalla zona in cui è definito il record e non deve essere immesso come parte del record A.

5.  Fare clic su **indirizzo IP**, digitare l'IP virtuale (VIP) del bilanciamento del carico per il pool Front end.
    
    <div>
    

    > [!IMPORTANT]  
    > Nelle distribuzioni in cui viene utilizzato un pool di server Director, i record host (A) per gli URL semplici devono puntare al VIP del servizio di bilanciamento del carico dei server Director.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Se si distribuisce solo un Server Enterprise o un server Director connesso alla topologia senza un servizio di bilanciamento del carico o si distribuisce un server Standard Edition, digitare l'indirizzo IP del Server Enterprise, del server Standard Edition o del server Director. Un servizio di bilanciamento del carico è necessario se si distribuiscono più Server Enterprise o server Director in un pool. I servizi di bilanciamento del carico non vengono utilizzati con server Standard Edition.

    
    </div>

6.  Fare clic su **Aggiungi host** e quindi su **OK**.

7.  Per creare un record A aggiuntivo, ripetere i passaggi 4 e 5.

8.  Al termine della creazione di tutti i record A necessari, fare clic su **Fine**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

