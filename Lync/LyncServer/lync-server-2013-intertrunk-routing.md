---
title: 'Lync Server 2013: Routing tra trunk'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Intertrunk routing
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205272(v=OCS.15)
ms:contentKeyID: 48185442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c1b66ea04ed72bab6d33114f52fa9fe96364b48
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975195"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="intertrunk-routing-in-lync-server-2013"></a>Routing tra trunk in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-20_

Lync Server 2013 può connettere un IP-PBX a un gateway PSTN (Public Switched Telephone Network) in modo che le chiamate da un telefono PBX possano essere indirizzate alla rete PSTN e le chiamate PSTN in arrivo possano essere indirizzate a un telefono PBX (Private Branch Exchange). Analogamente, Lync Server 2013 può interconnettere due o più sistemi IP-PBX in modo che le chiamate possano essere inserite e ricevute tra i telefoni PBX dei diversi sistemi IP-PBX.

Questa caratteristica di routing intertrunk può essere configurata usando il cmdlet Lync Server Management Shell, **Set-CsTrunkConfiguration**, con il nuovo parametro PstnUsages. Questo parametro specifica il set di record di utilizzo PSTN da usare. Un trunk usa questo uso PSTN per determinare una route e per instradare tutte le chiamate in arrivo di conseguenza.

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

Il diagramma seguente illustra Lync Server 2013 che fornisce l'interconnettività tra un gateway PSTN e un IP-PBX.

**Routing intertrunk tra gateway e IP PBX**

![Lync Server che connette il gateway PSTN/IP-PBX schema](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server che connette il portale PSTN/IP-PBX")

Il diagramma seguente illustra Lync Server 2013 che interconnette due sistemi IP-PBX.

**Routing intertrunk tra due IP PBX**

![Lync Server Interconnecting IP-Pax System Diagram](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server Interconnecting IP-Pax System Diagram")

</div>

<span> </span>

</div>

</div>

</div>

