---
title: Eliminare una raccolta esistente di impostazioni di configurazione di un/V Edge Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of A/V Edge Server configuration settings
ms:assetid: 668d3613-e464-4b68-967a-cfff90b9ce4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688077(v=OCS.15)
ms:contentKeyID: 49733673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7cc085cd6ac39c4712647795c5baf06eaa68f77a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>Eliminare una raccolta esistente di impostazioni di configurazione di un/V Edge Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Il servizio A/V Edge consente agli utenti interni (utenti che hanno effettuato l'accesso alla rete organizzativa) di condividere audio e video con utenti esterni (utenti che non hanno eseguito l'accesso alla rete organizzativa). Il servizio A/V Edge viene gestito principalmente con le impostazioni di configurazione di Edge A/V, che possono essere configurate nell'ambito del sito o nell'ambito del servizio, ovvero possono essere configurate per un singolo server A/V Edge.

Quando si installa Lync Server, viene creata una raccolta globale di impostazioni di configurazione di Edge A/V. Questa raccolta globale non può essere eliminata. Puoi tuttavia usare Windows PowerShell e il cmdlet Remove-CsAVEdgeConfiguration per "reimpostare" la raccolta globale; Questo significa semplicemente che tutti i valori di proprietà nella raccolta globale verranno reimpostati sul valore predefinito. Se ad esempio è stata impostata la proprietà MaxTokenLifetime per 16 ore, tale proprietà verrà reimpostata sul valore predefinito di 8 ore.

Tuttavia, le raccolte di impostazioni personalizzate create nell'ambito del sito o nell'ambito del servizio possono essere eliminate usando il cmdlet Remove-CsAVEdgeConfiguration. Se si eliminano le impostazioni dei siti, i server a/V Edge in tale sito verranno gestiti dalle impostazioni globali. Se si eliminano le impostazioni per l'ambito del servizio, tale server verrà gestito dalle impostazioni del sito, se esistenti o dalle impostazioni globali, se non sono disponibili impostazioni del sito.

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15)) .

<div>

## <a name="to-reset-the-global-collection"></a>Per reimpostare la raccolta globale

  - Il comando seguente reimposta la raccolta globale delle impostazioni di configurazione di un/V Edge:
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a>Per rimuovere una raccolta dall'ambito del sito

  - Questo comando rimuove le impostazioni di configurazione del bordo A/V applicate al sito Redmond:
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a>Per rimuovere una raccolta dall'ambito del servizio

  - Questo comando rimuove le impostazioni applicate all'atl-edge-001.litwareinc.com A/V Edge Server:
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Restituire le informazioni di configurazione A/V Edge Server in Lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Creare o modificare una raccolta di impostazioni di configurazione di un/V Edge Server in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[Audio/video (A/V) Edge Server in Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

