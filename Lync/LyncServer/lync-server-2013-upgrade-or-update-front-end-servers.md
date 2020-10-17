---
title: 'Lync Server 2013: aggiornare o aggiornare Front End Server'
description: 'Lync Server 2013: aggiornare o aggiornare Front End Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update Front End Servers
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/library/JJ204736(v=OCS.15)
ms:contentKeyID: 48183597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5340ca5549aeff51b275798572573b2c9f017644
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569922"
---
# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a>Aggiornare o aggiornare Front End Server in Lync Server 2013

<div data-xmlns="https://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-06-28_

I Front End Server di un pool Enterprise Edition sono organizzati in *domini di aggiornamento*. Si tratta di subset di Front End Server nel pool. I domini di aggiornamento vengono creati automaticamente dal generatore di topologie.

Quando si aggiornano i server, è necessario eseguire un dominio di aggiornamento alla volta. Portare ogni server in un dominio di aggiornamento verso il basso, aggiornarlo e quindi riavviarlo prima di passare a un altro dominio di aggiornamento. Tenere presente che i domini e i server dell'aggiornamento sono stati aggiornati fino a quel momento. Quando si aggiorna ogni server, utilizzare il diagramma diagramma di flusso seguente.

![Eseguire l'aggiornamento dei Front End Server](images/upgradeupdatefrontendserverslync2013.png)

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>Per applicare un aggiornamento ai Front End Server in un pool

1.  In un Front End Server del pool eseguire il cmdlet seguente:
    
    **Get-CsPoolUpgradeReadinessState**
    
    Se il valore di *PoolUpgradeState* è **occupato**, attendere 10 minuti, quindi tentare di nuovo **Get-CsPoolUpgradeReadinessState** . Se si vede **occupato** per almeno tre volte consecutive, dopo aver atteso 10 minuti tra ogni tentativo o se viene visualizzato un risultato di **InsufficientActiveFrontEnds** per **PoolUpgradeState,** si verifica un problema con il pool. Se questo pool è associato a un altro pool Front End in una topologia per il ripristino di emergenza, eseguire il failover del pool nel pool di backup e aggiornare i server di questo pool. Per ulteriori informazioni, vedere [failover di un pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).
    
    Se il valore di *PoolUpgradeState* è **Pronto**, andare al passaggio 2.

2.  Il cmdlet **Get-CsPoolUpgradeReadinessState** restituisce inoltre informazioni su ogni dominio di aggiornamento nel pool e sui front end server in ogni dominio di aggiornamento. Se il valore **ReadyforUpgrade** è impostato su **true** per il dominio di aggiornamento che contiene il server o i server che si desidera aggiornare, è possibile aggiornare i server in modo sicuro. A tale scopo, effettuare quando segue:
    
    1.  Interrompere le nuove connessioni ai front end server che si desidera aggiornare utilizzando il `Stop-CsWindowsService -Graceful -Verbose` cmdlet.
        
        <div>
        

        > [!NOTE]  
        > Se si eseguono questi aggiornamenti del server durante i tempi di inattività dei server pianificati, è possibile eseguire questo cmdlet senza il parametro '-<STRONG>grazioso</STRONG>', come indicato di seguito: <STRONG>Stop-CsWindowsService</STRONG>. Questo consente di arrestare immediatamente i servizi, senza attendere che vengano soddisfatte tutte le richieste di servizio esistenti.

        
        </div>
    
    2.  Aggiornare i server associati a questo dominio di aggiornamento.
    
    3.  Riavviare i server e verificare che accettino nuove connessioni.

3.  Ripetere i passaggi 1 e 2 per ogni altro dominio di aggiornamento nel pool fino a quando non sono stati aggiornati tutti i Front End Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

