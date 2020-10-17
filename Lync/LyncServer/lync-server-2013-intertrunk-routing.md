---
title: 'Lync Server 2013: routing tra trunk'
description: 'Lync Server 2013: routing tra trunk.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Intertrunk routing
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205272(v=OCS.15)
ms:contentKeyID: 48185442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30c838ee94a2df0807195c172d7e2a3a393523af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553142"
---
# <a name="intertrunk-routing-in-lync-server-2013"></a>Routing tra trunk in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-20_

Lync Server 2013 può interconnettere un IP-PBX a un gateway PSTN (Public Switched Telephone Network) in modo che le chiamate provenienti da un telefono PBX possano essere instradate alla rete PSTN e che le chiamate PSTN in arrivo possano essere instradate a un telefono PBX (Private Branch Exchange). Analogamente, Lync Server 2013 può interconnettere due o più sistemi IP-PBX in modo che le chiamate possano essere inserite e ricevute tra i telefoni PBX dei diversi sistemi IP-PBX.

Questa funzionalità di routing intertrunk può essere configurata utilizzando il cmdlet di Lync Server Management Shell, **Set-CsTrunkConfiguration**, con il nuovo parametro PstnUsages. Questo parametro specifica l'insieme di record di utilizzo PSTN da applicare. Un trunk si basa su questo utilizzo PSTN per determinare una route e per instradare tutte le chiamate in arrivo di conseguenza.

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

Nel diagramma seguente viene illustrato Lync Server 2013 che fornisce l'interconnettività tra un gateway PSTN e un IP-PBX.

**Routing tra trunk tra gateway e IP-PBX**

![Lync Server che connette il diagramma gateway PSTN/IP-PBX](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server che connette il diagramma gateway PSTN/IP-PBX")

Nel diagramma seguente viene illustrato Lync Server 2013 che interconnette due sistemi IP-PBX.

**Routing tra trunk tra due sistemi IP-PBX**

![Diagramma dei sistemi IP-PAX per la connessione di Lync Server](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Diagramma dei sistemi IP-PAX per la connessione di Lync Server")

</div>

<span> </span>

</div>

</div>

</div>

