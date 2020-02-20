---
title: Creare o modificare una raccolta di impostazioni di configurazione di A/V Edge Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of A/V Edge Server configuration settings
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49733630
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faff058e2d4e2ef3a874ad5fcece3ad1422605c1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151918"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>Creare o modificare una raccolta di impostazioni di configurazione di A/V Edge Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Il servizio A/V Edge consente agli utenti interni, ovvero gli utenti connessi alla rete dell'organizzazione, di condividere audio e video con gli utenti esterni, ovvero gli utenti non connessi alla rete dell'organizzazione. Il servizio A/V Edge viene gestito principalmente tramite le impostazioni di configurazione di A/V Edge, configurabili nell'ambito del sito o nell'ambito del servizio, ovvero per un singolo server A/V Edge.

Quando si installa Lync Server, viene creata una raccolta globale delle impostazioni di configurazione di A/V Edge. Oltre a ciò, è possibile utilizzare Windows PowerShell e il cmdlet New-CsAVEdgeConfiguration per creare nuove impostazioni nell'ambito del sito o nell'ambito del servizio, ovvero per un singolo server A/V Edge. Quando si creano nuove impostazioni, tenere presente quanto segue.

  - Le impostazioni configurate nell'ambito del servizio, ovvero in un singolo server, avranno la precedenza su tutte le altre.

  - Le impostazioni configurate nell'ambito del sito hanno la priorità su quelle configurate nell'ambito globale. Le impostazioni nell'ambito del servizio avranno tuttavia la precedenza sulle impostazioni nell'ambito del sito.

  - Le impostazioni dell'ambito globale vengono utilizzate solo se non sono state configurate impostazioni del servizio nel singolo server e se non sono presenti impostazioni del sito per il sito in cui si trova il server in oggetto.

Tutte le impostazioni possono essere quindi modificate utilizzando il cmdlet Set-CsAVEdgeConfiguration. Per ulteriori informazioni, vedere gli argomenti della Guida per i cmdlet [New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15)) e [Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15)) .

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a>Per creare nuove impostazioni di configurazione a/V Edge nell'ambito del sito

  - Il comando seguente crea una nuova raccolta di impostazioni di configurazione di A/V Edge per il sito Redmond.
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a>Per creare impostazioni di configurazione a/V Edge personalizzate nell'ambito del sito

  - Poiché non sono stati inclusi parametri aggiuntivi, queste nuove impostazioni utilizzeranno i valori predefiniti per il servizio A/V Edge. In alternativa, è possibile inserire altri parametri e valori di parametro per creare una raccolta personalizzata. Questo comando imposta ad esempio la proprietà MaxTokenLifetime su 4 ore (04 ore : 00 minuti : 00 secondi):
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a>Per creare impostazioni di configurazione a/V Edge personalizzate nell'ambito del servizio

  - Questo comando crea una raccolta simile applicata al server A/V Edge atl-edge-001.litwareinc.com:
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a>Per modificare le impostazioni di configurazione di A/V Edge esistenti

  - In questo esempio il cmdlet Set-CsAVEdgeConfiguration viene utilizzato per modificare in 12 ore la durata massima dei token per il sito Redmond:
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Restituire le informazioni di configurazione di A/V Edge Server in Lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Eliminare una raccolta esistente di impostazioni di configurazione di A/V Edge Server in Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Audio/video (A/V) server perimetrali in Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))  
[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

