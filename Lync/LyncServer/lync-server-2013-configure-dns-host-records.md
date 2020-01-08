---
title: 'Lync Server 2013: Configurare i record host DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DNS Host records
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398593(v=OCS.15)
ms:contentKeyID: 48184577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac3bb3c771d99e56e0c584675d77a92d95fdd757
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980648"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-host-records-for-lync-server-2013"></a>Configurare i record host DNS per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-01_

Per completare correttamente questa procedura, è necessario avere effettuato l'accesso al server o al dominio al minimo come membro del gruppo Domain Admins o di un membro del gruppo DnsAdmins.

<div>

## <a name="to-configure-dns-host-a-records"></a>Per configurare i record dell'host DNS

1.  Nel server DNS (Domain Name System) fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **DNS**.

2.  Nell'albero della console per il dominio espandere **aree di ricerca in avanti**e quindi fare clic con il pulsante destro del mouse sul dominio in cui verrà installato Lync Server 2013.

3.  Fare clic su **nuovo host (A o AAAA)**.

4.  Fare clic su **nome**, digitare il nome host per il pool (il nome di dominio viene considerato dalla zona in cui è definito il record e non deve essere immesso come parte del record a).

5.  Fare clic su **indirizzo IP**, digitare l'IP virtuale (VIP) del bilanciamento del carico per il pool Front-end.
    
    <div>
    

    > [!IMPORTANT]  
    > Nelle distribuzioni che usano un pool di Director i record host (A) per gli URL semplici devono puntare al VIP del responsabile del bilanciamento del carico.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Se si distribuisce solo un server Enterprise o un Director connesso alla topologia senza un bilanciamento del carico oppure se si distribuisce un server standard, digitare l'indirizzo IP del server Enterprise Edition, il server standard o il Director. Se si distribuiscono più server o Director Enterprise Edition in un pool, è necessario un bilanciamento del carico. I bilanciamento del carico non vengono usati con i server Standard Edition.

    
    </div>

6.  Fare clic su **Aggiungi host**e quindi su **OK**.

7.  Per creare un record aggiuntivo, ripetere i passaggi 4 e 5.

8.  Al termine della creazione di tutti i record necessari, fare clic su **fine**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

