---
title: 'Lync Server 2013: restituire le informazioni di configurazione A/V Edge Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Return A/V Edge Server configuration information
ms:assetid: b041f5a4-2387-4075-846c-ec4f99640903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721850(v=OCS.15)
ms:contentKeyID: 49733783
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ea7d7ed1ef74c092dac60ecfb2f009219564455
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a>Restituire le informazioni di configurazione A/V Edge Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Il servizio A/V Edge consente agli utenti interni (utenti che hanno effettuato l'accesso alla rete organizzativa) di condividere audio e video con utenti esterni (utenti che non hanno eseguito l'accesso alla rete organizzativa). Il servizio A/V Edge viene gestito principalmente con le impostazioni di configurazione di Edge A/V, che possono essere configurate nell'ambito del sito o nell'ambito del servizio, ovvero possono essere configurate per un singolo server A/V Edge.

Per restituire informazioni sulle impostazioni di configurazione a/V Edge in uso nell'organizzazione, è necessario usare Windows PowerShell e il cmdlet Get-CsAVEdgeConfiguration. Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) .

Le informazioni restituite dal cmdlet Get-CsAVEdgeConfiguration avranno un aspetto simile al seguente:

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a>Per restituire informazioni per tutte le impostazioni di configurazione di Edge A/V

  - Il comando seguente restituisce informazioni su tutte le impostazioni di configurazione A/V Edge attualmente in uso nell'organizzazione:
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a>Per restituire informazioni per le impostazioni di configurazione A/V Edge con ambito sito

  - Per restituire informazioni su una raccolta specifica di impostazioni di configurazione di un/V Edge, specificare l'identità della raccolta durante l'uso del cmdlet Get-CsAVEdgeConfiguration. Ad esempio, questo comando restituisce le informazioni solo per le impostazioni applicate al sito Redmond:
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a>Per restituire informazioni per le impostazioni di configurazione A/V Edge con ambito servizio

  - Questo comando restituisce solo le informazioni per le impostazioni applicate a un/V Edge Server specifico:
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creare o modificare una raccolta di impostazioni di configurazione di un/V Edge Server in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[Eliminare una raccolta esistente di impostazioni di configurazione di un/V Edge Server in Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Audio/video (A/V) Edge Server in Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

