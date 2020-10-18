---
title: 'Lync Server 2013: restituire le informazioni di configurazione di A/V Edge Server'
description: 'Lync Server 2013: restituire le informazioni di configurazione di A/V Edge Server.'
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
ms.openlocfilehash: f4f72fccfe51b946dc0dc285aee12a07e59c844b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575442"
---
# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a>Restituire le informazioni di configurazione di A/V Edge Server in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Il servizio A/V Edge consente agli utenti interni, ovvero gli utenti connessi alla rete dell'organizzazione, di condividere audio e video con gli utenti esterni, ovvero gli utenti non connessi alla rete dell'organizzazione. Il servizio A/V Edge viene gestito principalmente tramite le impostazioni di configurazione di A/V Edge, configurabili nell'ambito del sito o nell'ambito del servizio, ovvero per un singolo server A/V Edge.

Per ottenere informazioni sulle impostazioni di configurazione a/V Edge in uso nell'organizzazione, è necessario utilizzare Windows PowerShell e il cmdlet Get-CsAVEdgeConfiguration. Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) .

Le informazioni restituite dal cmdlet Get-CsAVEdgeConfiguration saranno simili alle seguenti:

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a>Per restituire informazioni su tutte le impostazioni di configurazione A/V Edge

  - Il comando seguente restituisce informazioni su tutte le impostazioni di configurazione A/V Edge attualmente in uso nell'organizzazione:
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a>Per restituire le informazioni relative alle impostazioni di configurazione A/V Edge con ambito sito

  - Per restituire informazioni su una raccolta specifica di impostazioni di configurazione A/V Edge, specificare l'identità (Identity) di tale raccolta quando si esegue il cmdlet Get-CsAVEdgeConfiguration. Questo comando ad esempio restituisce informazioni solo sulle impostazioni applicate al sito Redmond:
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a>Per restituire le informazioni relative alle impostazioni di configurazione A/V Edge con ambito servizio

  - Questo comando restituisce informazioni solo sulle impostazioni applicate a un A/V Edge Server specifico:
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creare o modificare una raccolta di impostazioni di configurazione di A/V Edge Server in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[Eliminare una raccolta esistente di impostazioni di configurazione di A/V Edge Server in Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Audio/video (A/V) server perimetrali in Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

