---
title: 'Lync Server 2013: configurare il server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Persistent Chat Server
ms:assetid: 85028aff-a38e-4748-958e-59e707a47532
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205054(v=OCS.15)
ms:contentKeyID: 48184709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a9661c3e9695bde240225b7d0bcd8ca1e54df09
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520443"
---
# <a name="configure-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="ffe13-102">Configurare il server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffe13-102">Configure Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffe13-103">_**Ultimo argomento modificato:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="ffe13-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="ffe13-104">Per creare una nuova configurazione di chat persistente</span><span class="sxs-lookup"><span data-stu-id="ffe13-104">To create a new Persistent Chat configuration</span></span>

    New-CsPersistentChatConfiguration -Identity <XdsIdentity> [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="ffe13-105">Per ottenere la configurazione della chat persistente</span><span class="sxs-lookup"><span data-stu-id="ffe13-105">To get Persistent Chat configuration</span></span>

    Get-CsPersistentChatConfiguration [-LocalStore <Switch Parameter>] [-Identity <XdsIdentity>]

<span data-ttu-id="ffe13-106">Per rimuovere la configurazione della chat persistente</span><span class="sxs-lookup"><span data-stu-id="ffe13-106">To remove Persistent Chat configuration</span></span>

    Remove-CsPersistentChatConfiguration -Identity <XdsIdentity>

<span data-ttu-id="ffe13-107">Per impostare la configurazione di chat persistente</span><span class="sxs-lookup"><span data-stu-id="ffe13-107">To set Persistent Chat configuration</span></span>

    Set-CsPersistentChatConfiguration [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject >] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="ffe13-108">Per Lync Server 2013, tutto il traffico dei servizi Web è supportato in Lync Server 2013, Front End Server.</span><span class="sxs-lookup"><span data-stu-id="ffe13-108">For Lync Server 2013, all web service traffic is supported on the Lync Server 2013, Front End Servers.</span></span> <span data-ttu-id="ffe13-109">Pertanto, l'indirizzo gcweb01 sul server Chat persistente non è necessario.</span><span class="sxs-lookup"><span data-stu-id="ffe13-109">Therefore, the gcweb01 address on Persistent Chat Server is not necessary.</span></span> <span data-ttu-id="ffe13-110">L'accesso al servizio Web interno è ancora supportato poiché è offerto il servizio Web di Download e Upload file al sito Web *interno* (ma non al sito Web *esterno* per gli utenti remoti).</span><span class="sxs-lookup"><span data-stu-id="ffe13-110">We still support internal web service access because we provide the File Upload/Download Web service to the *internal* website only (not to the *external* website for remote users).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

