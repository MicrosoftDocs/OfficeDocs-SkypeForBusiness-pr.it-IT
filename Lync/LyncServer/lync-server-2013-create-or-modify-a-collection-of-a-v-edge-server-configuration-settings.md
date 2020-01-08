---
title: Creare o modificare una raccolta di impostazioni di configurazione di un/V Edge Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of A/V Edge Server configuration settings
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49733630
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a4010c209e1231c47c328d616f686f55fc89008
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984930"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>Creare o modificare una raccolta di impostazioni di configurazione di un/V Edge Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Il servizio A/V Edge consente agli utenti interni (utenti che hanno effettuato l'accesso alla rete organizzativa) di condividere audio e video con utenti esterni (utenti che non hanno eseguito l'accesso alla rete organizzativa). Il servizio A/V Edge viene gestito principalmente con le impostazioni di configurazione di Edge A/V, che possono essere configurate nell'ambito del sito o nell'ambito del servizio, ovvero possono essere configurate per un singolo server A/V Edge.

Quando si installa Lync Server, viene creata una raccolta globale di impostazioni di configurazione di Edge A/V. Oltre a questo, puoi usare Windows PowerShell e il cmdlet New-CsAVEdgeConfiguration per creare nuove impostazioni nell'ambito del sito o nell'ambito del servizio (ovvero, per un singolo A/V Edge Server). Se crei nuove impostazioni, tieni presente che:

  - Le impostazioni configurate nell'ambito del servizio, ovvero su un singolo server, hanno la priorità su tutto.

  - Le impostazioni configurate nell'ambito del sito hanno la priorità sulle impostazioni configurate nell'ambito globale. Tuttavia, le impostazioni dell'ambito del servizio sostituiranno anche le impostazioni dell'ambito del sito.

  - Le impostazioni dell'ambito globale verranno usate solo se non sono state configurate impostazioni di servizio nel singolo server e se non sono presenti impostazioni del sito per il sito in cui si trova il server.

È quindi possibile modificare le impostazioni usando il cmdlet Set-CsAVEdgeConfiguration. Per altre informazioni, vedere gli argomenti della Guida per i cmdlet [New-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15)) e [Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15)) .

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a>Per creare nuove impostazioni di configurazione a/V Edge nell'ambito del sito

  - Il comando seguente crea una nuova raccolta di impostazioni di configurazione A/V Edge per il sito Redmond:
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a>Per creare impostazioni di configurazione personalizzate a/V Edge nell'ambito del sito

  - Dato che non sono stati inclusi parametri aggiuntivi, queste nuove impostazioni utilizzeranno i valori predefiniti per il servizio A/V Edge. In alternativa, è possibile aggiungere altri parametri e valori di parametro per creare una raccolta personalizzata. Questo comando, ad esempio, imposta la proprietà MaxTokenLifetime su 4 ore (04 ore: 00 minuti: 00 secondi):
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a>Per creare impostazioni di configurazione personalizzate a/V Edge nell'ambito del servizio

  - Questo comando crea una raccolta simile applicata all'atl-edge-001.litwareinc.com A/V Edge Server:
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a>Per modificare le impostazioni di configurazione di un/V Edge esistenti

  - In questo esempio, il cmdlet Set-CsAVEdgeConfiguration viene usato per modificare la durata del token massimo per il sito Redmond in 12 ore:
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Restituire le informazioni di configurazione A/V Edge Server in Lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Eliminare una raccolta esistente di impostazioni di configurazione di un/V Edge Server in Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Audio/video (A/V) Edge Server in Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
[New-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))  
[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

