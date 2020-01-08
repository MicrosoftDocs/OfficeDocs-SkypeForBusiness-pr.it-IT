---
title: "Lync Server 2013: stato della replica dell'archivio di gestione centrale"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Central management store replication status
ms:assetid: f514f88d-986b-4e45-b79b-e04a7616c1fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720926(v=OCS.15)
ms:contentKeyID: 63969663
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ce46b403e27d0a2b69f705b5bada026882eec7d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="central-management-store-replication-status-in-lync-server-2013"></a>Stato della replica dell'archivio di gestione centrale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2015-01-26_

Quando un amministratore apporta una modifica di qualche tipo a Lync Server, ad esempio quando un amministratore crea un nuovo criterio vocale o modifica le impostazioni di configurazione del server della Rubrica, la modifica viene registrata nell'Central Management store. A sua volta, la modifica deve essere replicata in tutti i computer in cui sono in uso servizi o ruoli del server Lync.

Per replicare i dati, il replicatore Master (in uso nel server di gestione centralizzato) crea uno snapshot dei dati di configurazione modificati. Una copia di questo snapshot viene quindi inviata a ogni computer in cui è in uso servizi o ruoli del server Lync. In tali computer, un agente di replica riceve lo snapshot e carica i dati modificati. L'agente invia quindi a Master Replicator un messaggio che riporta lo stato di replica più recente.

Il cmdlet Get-CsManagementStoreReplicationStatus consente di verificare lo stato di replica per qualsiasi o tutti i computer Lync Server dell'organizzazione.

Chi può eseguire questo cmdlet? Per impostazione predefinita, i membri dei seguenti gruppi sono autorizzati a eseguire in locale il cmdlet Get-CsManagementStoreReplicationStatus: RTCUniversalUserAdmins, RTCUniversalServerAdmins.

Per restituire un elenco di tutti i ruoli RBAC a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati manualmente), eseguire il comando seguente dal prompt di Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

<div>

## <a name="see-also"></a>Vedere anche


[Get-CsManagementStoreReplicationStatus](https://docs.microsoft.com/powershell/module/skype/Get-CsManagementStoreReplicationStatus)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

