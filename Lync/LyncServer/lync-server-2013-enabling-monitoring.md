---
title: 'Lync Server 2013: attivazione del monitoraggio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling monitoring
ms:assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687994(v=OCS.15)
ms:contentKeyID: 49733584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f07ea86bfeb9bd13f8fb3c4f34d114af075e6150
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-monitoring-in-lync-server-2013"></a>Abilitazione del monitoraggio in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-17_

Anche se gli agenti di raccolta dati unificati vengono installati e attivati automaticamente su ogni Front End Server, ciò non significa che si inizierà automaticamente a raccogliere i dati di monitoraggio nel momento in cui si termina l'installazione di Microsoft Lync Server 2013. Al contrario, è necessario eseguire due operazioni: associare Front End Server e pool Front End a un database di monitoraggio e abilitare il monitoraggio di registrazione dettagli chiamata e/o QoE nell'ambito globale e/o del sito.

Per istruzioni dettagliate sull'associazione di front end server o pool Front end a un database di monitoraggio, vedere l'argomento [associazione di un archivio di monitoraggio con un pool Front end in Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) nella Guida alla distribuzione. Dopo aver completato queste associazioni e dopo aver pubblicato la nuova topologia di Lync Server, non è ancora possibile raccogliere dati di monitoraggio. Ciò è dovuto al fatto che, per impostazione predefinita, sia la raccolta di dati CDR che QoE è disabilitata quando si installa Lync Server 2013.

Per iniziare la raccolta dei dati, è necessario abilitare il monitoraggio di registrazione dettagli chiamata e/o QoE. Tenere presente che non è necessario abilitare il monitoraggio di CDR e QoE, se si preferisce, è possibile abilitare un tipo di monitoraggio lasciando l'altro tipo disabilitato. Per abilitare il monitoraggio CDR nell'ambito globale, eseguire il comando riportato di seguito dall'interno di Lync Server Management Shell:

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

In alternativa, è possibile abilitare il monitoraggio di registrazione dettagli chiamata dall'interno del pannello di controllo di Lync Server 2013. Nel pannello di controllo di Lync Server, eseguire la procedura seguente:

1.  Fare clic su **Monitoraggio**.

2.  Nella scheda **Registrazione dettagli chiamata** fare doppio clic sull'impostazione **Globale**.

3.  Nel riquadro **Modifica impostazione di registrazione dettagli chiamata** selezionare **Abilita monitoraggio registrazioni dettagli chiamata** e fare clic su **Commit**.

Per abilitare il monitoraggio QoE nell'ambito globale, eseguire questo comando dall'interno di Lync Server Management Shell:

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

Se si preferisce, è anche possibile abilitare il monitoraggio QoE dall'interno del pannello di controllo di Lync Server. Dal Pannello di controllo, completare la procedura seguente:

1.  Fare clic su **Monitoraggio**.

2.  Nella scheda **Dati QoE** fare doppio clic sull'impostazione **Globale**.

3.  Nel riquadro **Modifica impostazione QoE** selezionare **Abilita monitoraggio dei dati QoE** e fare clic su **Commit**.

Come si può notare, negli esempi precedenti il monitoraggio viene abilitato nell'ambito globale, ciò significa che il monitoraggio di registrazione dettagli chiamata e QoE viene abilitato per l'intera organizzazione. In alternativa, è possibile creare impostazioni di configurazione di registrazione dettagli chiamata e QoE nell'ambito del sito, quindi abilitare o disabilitare in modo selettivo per ogni sito. Ad esempio, è possibile abilitare il monitoraggio di registrazione dettagli chiamata per il sito di Parigi, ma disabilitarlo per il sito di Milano. Per ulteriori informazioni sulla gestione delle impostazioni di configurazione del monitoraggio, vedere l'argomento relativo alla distribuzione delle [impostazioni di registrazione dettagli chiamata e qualità delle esperienze in Lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).

</div>

<span> </span>

</div>

</div>

</div>

