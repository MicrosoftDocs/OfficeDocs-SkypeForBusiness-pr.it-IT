---
title: 'Lync Server 2013: aggiornare o aggiornare i server front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Upgrade or update Front End Servers
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204736(v=OCS.15)
ms:contentKeyID: 48183597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e4edb5ea009960fe0456f266a428431049f542b
ms.sourcegitcommit: de7e0afbd40bbe52994ab99d85cf9e95ecbc4a6c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2019
ms.locfileid: "40980009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a>Aggiornare o aggiornare i server front-end in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-06-28_

I server front-end in un pool di Enterprise Edition sono organizzati in *domini di aggiornamento*. Si tratta di sottoinsiemi di server front-end nel pool. I domini di aggiornamento vengono creati automaticamente da generatore di topologia.

Quando si aggiornano i server, è necessario farlo un dominio di aggiornamento alla volta. Trasferire ogni server in un dominio di aggiornamento, aggiornarlo e quindi riavviarlo prima di passare a un altro dominio di aggiornamento. Assicurati di tenere traccia dei domini e server di aggiornamento aggiornati fino a questo momento. Usare il diagramma di flusso seguente durante l'aggiornamento di ogni server.

:::image type="content" source="images/UpgradeUpdateFrontEndServerslync2013.png" alt-text="Aggiornare o aggiornare i server front-end":::

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>Per applicare un aggiornamento ai server front-end in un pool

1.  In un server front-end nel pool eseguire il cmdlet seguente:
    
    **Get-CsPoolUpgradeReadinessState**
    
    Se il valore di *PoolUpgradeState* è **occupato**, attendere 10 minuti e quindi provare di nuovo **Get-CsPoolUpgradeReadinessState** . Se si vede **occupato** per almeno tre volte consecutive, dopo aver aspettato 10 minuti tra ogni tentativo o se viene visualizzato qualsiasi risultato di **InsufficientActiveFrontEnds** per **PoolUpgradeState,** si verifica un problema con il pool. Se questo pool è associato a un altro pool Front-end in una topologia di ripristino di emergenza, il pool deve essere superato nel pool di backup e quindi aggiornare i server in questo pool. Per informazioni dettagliate, vedere [mancanza di un pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).
    
    Se il valore di *PoolUpgradeState* è **pronto**, passare al passaggio 2.

2.  Il cmdlet **Get-CsPoolUpgradeReadinessState** restituisce anche informazioni su ogni dominio di aggiornamento nel pool e su quali server front-end si trovano in ogni dominio di aggiornamento. Se il valore **ReadyforUpgrade** è **true** per il dominio di aggiornamento che contiene il server o i server che si desidera aggiornare, è possibile aggiornare i server in modo sicuro. Per eseguire questa operazione, eseguire le operazioni seguenti:
    
    1.  Arrestare le nuove connessioni ai server front-end che si vuole aggiornare usando il `Stop-CsWindowsService -Graceful -Verbose` cmdlet.
        
        <div>
        

        > [!NOTE]  
        > Se si eseguono questi aggiornamenti del server durante un periodo di inattività pianificato del server, è possibile eseguire questo cmdlet senza il parametro "-<STRONG>grazioso</STRONG>", come indicato di seguito: <STRONG>Stop-CsWindowsService</STRONG>. In questo modo si chiuderanno immediatamente i servizi, senza attendere la compilazione di tutte le richieste di servizio esistenti.

        
        </div>
    
    2.  Aggiornare i server associati al dominio di aggiornamento.
    
    3.  Riavviare i server e verificare che accettino nuove connessioni.

3.  Ripetere i passaggi 1 e 2 per ogni altro dominio di aggiornamento nel pool, finché non sono stati aggiornati tutti i server front-end.

</div>

</div>

<span> </span>

</div>

</div>

</div>

