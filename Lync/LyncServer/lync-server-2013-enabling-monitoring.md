---
title: 'Lync Server 2013: abilitazione del monitoraggio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling monitoring
ms:assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687994(v=OCS.15)
ms:contentKeyID: 49733584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2b13028390328e93a9e90636962dedea8ea8ec9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-monitoring-in-lync-server-2013"></a>Abilitazione del monitoraggio in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-17_

Anche se gli agenti di raccolta dati unificati vengono installati e attivati automaticamente in ogni server front-end, ciò non significa che si inizierà automaticamente a raccogliere i dati di monitoraggio nel momento in cui si completa l'installazione di Microsoft Lync Server 2013. È invece necessario eseguire due operazioni: è necessario associare i server front-end/pool Front-end a un database di monitoraggio ed è necessario abilitare il monitoraggio della registrazione dei dettagli delle chiamate (CDR) e/o la qualità dell'esperienza (QoE) nell'ambito globale e/o nell'ambito del sito.

Per istruzioni dettagliate sull'associazione di server front-end o pool Front-end a un database di monitoraggio, vedere l'argomento [associazione di un archivio di monitoraggio con un pool Front-end in Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) nella Guida alla distribuzione. Dopo aver effettuato queste associazioni e dopo la pubblicazione della nuova topologia di Lync Server, non sarà ancora possibile raccogliere i dati di monitoraggio. Questo perché, per impostazione predefinita, sia la raccolta di dati CDR che QoE è disabilitata durante l'installazione di Lync Server 2013.

Per avviare la raccolta dei dati, è necessario abilitare il monitoraggio CDR e/o QoE. (Si noti che non è necessario abilitare il monitoraggio CDR e QoE, se si preferisce, è possibile abilitare un tipo di monitoraggio lasciando l'altro tipo disabilitato). Per abilitare il monitoraggio CDR nell'ambito globale, eseguire il comando seguente dall'interno di Lync Server Management Shell:

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

In alternativa, è possibile abilitare il monitoraggio CDR dall'interno del pannello di controllo di Lync Server 2013. Nel pannello di controllo di Lync Server completare la procedura seguente:

1.  Fare clic su **monitoraggio**.

2.  Nella scheda **registrazione dettagli chiamata** fare doppio clic sull'impostazione **globale** .

3.  Nel riquadro **Impostazioni registrazione dettagli chiamata (CDR)** selezionare **Abilita monitoraggio di CDRS** e quindi fare clic su **commit**.

Per abilitare il monitoraggio QoE nell'ambito globale, eseguire questo comando dall'interno di Lync Server Management Shell:

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

Se si preferisce, è anche possibile abilitare il monitoraggio QoE dall'interno del pannello di controllo di Lync Server. Nel pannello di controllo completare la procedura seguente:

1.  Fare clic su **monitoraggio**.

2.  Nella scheda **qualità di dati esperienza** fare doppio clic sull'impostazione **globale** .

3.  Nel riquadro **Impostazioni modifica qualità dell'esperienza (QoE)** selezionare Abilita il **monitoraggio dei dati QoE** e quindi fare clic su **commit**.

Come indicato, gli esempi precedenti consentono il monitoraggio nell'ambito globale; in altre altre, abilitano il monitoraggio CDR e QoE in tutta l'organizzazione. In alternativa, è possibile creare impostazioni di configurazione CDR e QoE separate nell'ambito del sito e quindi abilitare o disabilitare il monitoraggio in modo selettivo per ogni sito. Ad esempio, è possibile abilitare il monitoraggio CDR per il sito Redmond, ma disabilitare il monitoraggio CDR per il sito di Dublino. Per altre informazioni sulla gestione delle impostazioni di configurazione del monitoraggio, vedere l'argomento Guida alla distribuzione [configurazione della registrazione dei dettagli delle chiamate e della qualità delle impostazioni dell'esperienza in Lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).

</div>

<span> </span>

</div>

</div>

</div>

