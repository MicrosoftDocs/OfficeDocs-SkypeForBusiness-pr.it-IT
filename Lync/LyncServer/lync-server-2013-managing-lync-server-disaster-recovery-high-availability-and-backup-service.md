---
title: Gestione del ripristino di emergenza di Lync Server, disponibilità elevata e servizio di backup
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Lync Server disaster recovery, high availability, and Backup Service
ms:assetid: f4cd36fb-ffd6-48fa-b761-e11b3bcff91a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721939(v=OCS.15)
ms:contentKeyID: 49733876
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cada393fca28895ee5f23a12fdd55eabd211128e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977328"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a>Gestione di ripristino di emergenza, disponibilità elevata e servizio di backup di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-12_

Questa sezione contiene le procedure per le operazioni di ripristino di emergenza e per il mantenimento del servizio di backup che sincronizza i dati in pool Front-End associati.

Le procedure di ripristino di emergenza, sia failover che failback, sono manuali. In caso di emergenza, l'amministratore deve richiamare manualmente le procedure di failover. Lo stesso vale per il failback dopo la riparazione del pool.

Le procedure di ripristino di emergenza nella parte restante di questa sezione presuppongono quanto segue:

  - Si dispone di una distribuzione con pool Front-End associati, che si trova in siti diversi, come descritto in [pianificazione per l'elevata disponibilità e il ripristino di emergenza in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). Il servizio di backup è stato eseguito in questi pool associati per mantenerli sincronizzati.

  - Se l'archivio di gestione centrale è ospitato in un pool, viene installato ed eseguito in entrambi i pool associati, con uno di questi pool che ospitano l'Active master e l'altro pool che ospita la modalità standby.

<div>


> [!IMPORTANT]
> Nelle procedure seguenti il parametro <EM>PoolFqdn</EM> si riferisce al nome di dominio completo del pool interessato da Disaster, non al pool in cui vengono reindirizzati gli utenti interessati. Per lo stesso set di utenti interessati, si riferisce allo stesso pool sia in cmdlet di failover che di failback, ovvero il pool che ha prima ospitato gli utenti prima del failover.<BR>Ad esempio, supponiamo che un caso in cui tutti gli utenti ospitati in un pool P1 non siano stati rilevati nel pool di backup, P2. Se l'amministratore vuole trasferire tutti gli utenti attualmente serviti da P2 per essere serviti da P1, l'amministratore deve eseguire i passaggi seguenti: 
> <OL>
> <LI>
> <P>Non eseguire il backup di tutti gli utenti originariamente assegnati a P1 da P2 a P1 usando il cmdlet failback. In questo caso, <EM>PoolFqdn</EM> è il nome di dominio completo di P1.</P>
> <LI>
> <P>Non eseguire il failover di tutti gli utenti originariamente ospitati in P2 in P1 usando il cmdlet per l'uso del protocollo. In questo caso, <EM>PoolFqdn</EM> è il nome di dominio completo di P2's.</P>
> <LI>
> <P>Se l'amministratore vuole in seguito riuscire a restituire gli utenti P2 a P2, <EM>PoolFqdn</EM> è il nome di dominio completo di P2's.</P></LI></OL>Tieni presente che il passaggio 1 deve essere eseguito prima del passaggio 2 per mantenere l'integrità del pool. Se si prova il passaggio 2 prima del passaggio 1, il cmdlet Step 2 non riuscirà.



</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Configurazione e monitoraggio del servizio di backup in Lync Server 2013](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [Failover di un pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md)

  - [Failback di un pool in Lync Server 2013](lync-server-2013-failing-back-a-pool.md)

  - [Failover di un database con mirroring in Lync Server 2013](lync-server-2013-failing-over-a-mirrored-database.md)

  - [Failover del pool di server perimetrali utilizzato per la federazione di Lync Server in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [Failover del pool di server perimetrali utilizzato per la federazione di XMPP in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [Failback del pool di server perimetrali utilizzato per la federazione di Lync Server o di XMPP in Lync Server 2013](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [Modifica del pool di server perimetrali associato a un pool Front End in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [Ripristino del contenuto delle conferenze tramite il servizio di backup in Lync Server 2013](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

