---
title: Eliminare una raccolta esistente di impostazioni di configurazione di A/V Edge Server
description: Eliminare una raccolta esistente di impostazioni di configurazione di A/V Edge Server.
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
ms.openlocfilehash: d7fe444e8bcb7e7e8e2633e59c23aeb2e80e9b98
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553622"
---
# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>Eliminare una raccolta esistente di impostazioni di configurazione di A/V Edge Server in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Il servizio A/V Edge consente agli utenti interni, ovvero gli utenti connessi alla rete dell'organizzazione, di condividere audio e video con gli utenti esterni, ovvero gli utenti non connessi alla rete dell'organizzazione. Il servizio A/V Edge viene gestito principalmente tramite le impostazioni di configurazione di A/V Edge, configurabili nell'ambito del sito o nell'ambito del servizio, ovvero per un singolo server A/V Edge.

Quando si installa Lync Server, viene creata una raccolta globale delle impostazioni di configurazione di A/V Edge. Questa raccolta globale non può essere eliminata. Tuttavia, è possibile utilizzare Windows PowerShell e il cmdlet Remove-CsAVEdgeConfiguration per "reimpostare" la raccolta globale. Ciò significa semplicemente che tutti i valori della proprietà nella raccolta globale verranno reimpostati sul valore predefinito. Se la proprietà MaxTokenLifetime è impostata su 16 ore, ad esempio, con l'esecuzione del cmdlet verrebbe ripristinato il valore predefinito di 8 ore.

È comunque possibile utilizzare il cmdlet Remove-CsAVEdgeConfiguration per eliminare le raccolte di impostazioni personalizzate create con ambito sito o con ambito servizio. Se si eliminano le impostazioni a livello di sito, i server A/V Edge in tale sito verranno gestiti dalle impostazioni globali. Se si eliminano le impostazioni con ambito servizio, il server verrà gestito dalle impostazioni a livello sito, se esistenti, o dalle impostazioni globali se non sono disponibili impostazioni a livello di sito.

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15)) .

<div>

## <a name="to-reset-the-global-collection"></a>Per reimpostare la raccolta globale

  - Il comando seguente consente di reimpostare la raccolta globale delle impostazioni di configurazione di A/V Edge:
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a>Per rimuovere una raccolta dall'ambito del sito

  - Questo comando consente di rimuovere le impostazioni di configurazione di A/V Edge applicate al sito Redmond:
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a>Per rimuovere una raccolta dall'ambito del servizio

  - Questo comando consente di rimuovere le impostazioni applicate al server A/V Edge atl-edge-001.litwareinc.com:
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Restituire le informazioni di configurazione di A/V Edge Server in Lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Creare o modificare una raccolta di impostazioni di configurazione di A/V Edge Server in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[Audio/video (A/V) server perimetrali in Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

