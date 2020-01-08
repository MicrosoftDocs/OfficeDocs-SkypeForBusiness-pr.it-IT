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

# <a name="central-management-store-replication-status-in-lync-server-2013"></a><span data-ttu-id="cf544-102">Stato della replica dell'archivio di gestione centrale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf544-102">Central management store replication status in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf544-103">_**Argomento Ultima modifica:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="cf544-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="cf544-104">Quando un amministratore apporta una modifica di qualche tipo a Lync Server, ad esempio quando un amministratore crea un nuovo criterio vocale o modifica le impostazioni di configurazione del server della Rubrica, la modifica viene registrata nell'Central Management store.</span><span class="sxs-lookup"><span data-stu-id="cf544-104">When an administrator makes a change of some kind to Lync Server (for example, when an administrator creates a new voice policy or changes the Address Book Server configuration settings) that change is recorded in the Central Management store.</span></span> <span data-ttu-id="cf544-105">A sua volta, la modifica deve essere replicata in tutti i computer in cui sono in uso servizi o ruoli del server Lync.</span><span class="sxs-lookup"><span data-stu-id="cf544-105">In turn, the change must then be replicated to all the computers that are running Lync Server services or server roles.</span></span>

<span data-ttu-id="cf544-106">Per replicare i dati, il replicatore Master (in uso nel server di gestione centralizzato) crea uno snapshot dei dati di configurazione modificati.</span><span class="sxs-lookup"><span data-stu-id="cf544-106">To replicate data, the Master Replicator (running on the Central Management Server) creates a snapshot of the changed configuration data.</span></span> <span data-ttu-id="cf544-107">Una copia di questo snapshot viene quindi inviata a ogni computer in cui è in uso servizi o ruoli del server Lync.</span><span class="sxs-lookup"><span data-stu-id="cf544-107">A copy of this snapshot is then sent to each computer that is running Lync Server services or server roles.</span></span> <span data-ttu-id="cf544-108">In tali computer, un agente di replica riceve lo snapshot e carica i dati modificati.</span><span class="sxs-lookup"><span data-stu-id="cf544-108">On those computers, a replication agent receives the snapshot and uploads the changed data.</span></span> <span data-ttu-id="cf544-109">L'agente invia quindi a Master Replicator un messaggio che riporta lo stato di replica più recente.</span><span class="sxs-lookup"><span data-stu-id="cf544-109">The agent then sends the Master Replicator a message reporting the latest replication status.</span></span>

<span data-ttu-id="cf544-110">Il cmdlet Get-CsManagementStoreReplicationStatus consente di verificare lo stato di replica per qualsiasi o tutti i computer Lync Server dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cf544-110">The Get-CsManagementStoreReplicationStatus cmdlet enables you to verify the replication status for any (or all) of the Lync Server computers in your organization.</span></span>

<span data-ttu-id="cf544-111">Chi può eseguire questo cmdlet?</span><span class="sxs-lookup"><span data-stu-id="cf544-111">Who can run this cmdlet?</span></span> <span data-ttu-id="cf544-112">Per impostazione predefinita, i membri dei seguenti gruppi sono autorizzati a eseguire in locale il cmdlet Get-CsManagementStoreReplicationStatus: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="cf544-112">By default, members of the following groups are authorized to run the Get-CsManagementStoreReplicationStatus cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span>

<span data-ttu-id="cf544-113">Per restituire un elenco di tutti i ruoli RBAC a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati manualmente), eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="cf544-113">To return a list of all RBAC roles this cmdlet was assigned to (including any custom RBAC roles that you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

<div>

## <a name="see-also"></a><span data-ttu-id="cf544-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf544-114">See Also</span></span>


[<span data-ttu-id="cf544-115">Get-CsManagementStoreReplicationStatus</span><span class="sxs-lookup"><span data-stu-id="cf544-115">Get-CsManagementStoreReplicationStatus</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsManagementStoreReplicationStatus)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

