---
title: Gestione di ripristino di emergenza, disponibilità elevata e servizio di backup di Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server disaster recovery, high availability, and Backup Service
ms:assetid: f4cd36fb-ffd6-48fa-b761-e11b3bcff91a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721939(v=OCS.15)
ms:contentKeyID: 49733876
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c935a27f737d8ec7fdb012f4e0c13930d20a1319
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498153"
---
# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a>Gestione di ripristino di emergenza, disponibilità elevata e servizio di backup di Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-12_

In questa sezione sono incluse le procedure per le operazioni di ripristino di emergenza e per la gestione del servizio di backup che esegue la sincronizzazione dei dati nei pool Front End abbinati.

Le procedure di ripristino di emergenza, sia di failover che di failback, sono manuali. In caso di emergenza, è necessario che l'amministratore richiami manualmente le procedure di failover. La stessa procedura si applica al failback dopo che il pool è stato ripristinato.

Per le procedure di ripristino di emergenza presenti nel resto della sezione vengono presupposti gli elementi seguenti:

  - Si dispone di una distribuzione con pool Front End associati, che si trovano in siti diversi, come descritto in [pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). Il servizio di backup è stato eseguito nei pool abbinati per mantenerli sincronizzati.

  - Se l'archivio di gestione centrale è ospitato in un pool, è installato e in esecuzione su entrambi i pool associati, con uno dei pool che ospitano il master attivo e l'altro pool che ospita la modalità standby.

<div>


> [!IMPORTANT]
> Nelle procedure seguenti il parametro <EM>PoolFQDN</EM> si riferisce al nome di dominio completo (FQDN) del pool interessato dall'emergenza, non al pool da cui gli utenti interessati dal problema vengono reindirizzati. Per lo stesso gruppo di utenti interessati dal problema, si riferisce allo stesso pool nei cmdlet di failover e failback (il pool che ospitava gli utenti prima del failover).<BR>Si supponga ad esempio un caso in cui per tutti gli utenti ospitati in un pool P1 sia stato eseguito il failover nel pool di backup, P2. Se l'amministratore desidera spostare tutti gli utenti serviti da P2 in modo che siano serviti da P1, è necessario che esegua le procedure seguenti: 
> <OL>
> <LI>
> <P>Eseguire il failback di tutti gli utenti originariamente ospitati in P1 da P2 a P1 utilizzando il cmdlet di failback. In tal caso, <EM>PoolFQDN</EM> è il nome di dominio completo (FQDN) di P1.</P>
> <LI>
> <P>Eseguire il failover di tutti gli utenti originariamente ospitati in P2 a P1 utilizzando il cmdlet di failover. In tal caso, <EM>PoolFQDN</EM> è il nome di dominio completo (FQDN) di P2.</P>
> <LI>
> <P>Se successivamente l'amministratore desidera eseguire il failback degli utenti P2 a P2, <EM>PoolFQDN</EM> è il nome di dominio completo (FQDN) di P2.</P></LI></OL>Per preservare l'integrità del pool, è necessario eseguire la procedura 1 prima della procedura 2. Se si esegue la procedura 2 prima della procedura 1, il cmdlet della procedura 2 avrà esito negativo.



</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Configurazione e monitoraggio del servizio di backup in Lync Server 2013](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [Failover di un pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md)

  - [Failover di un pool in Lync Server 2013](lync-server-2013-failing-back-a-pool.md)

  - [Failover di un database con mirroring in Lync Server 2013](lync-server-2013-failing-over-a-mirrored-database.md)

  - [Failover del pool di server perimetrali utilizzato per la Federazione di Lync ServerAnalysis in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [Failover del pool di server perimetrali utilizzato per la Federazione XMPP in Lync 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [Failover del pool di server perimetrali utilizzato per la Federazione di Lync o la Federazione XMPP in Lync Server 2013](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [Modifica del pool di server perimetrali associato a un pool Front end in Lync 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

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

