---
title: 'Lync Server 2013: server perimetrali audio/video (A/V)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Audio/Video (A/V) Edge Servers
ms:assetid: b0cc538b-77eb-47fb-be82-5ab0631c6219
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721852(v=OCS.15)
ms:contentKeyID: 49733785
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a83aa6c21be0a1055be091ab7195f3c03c4c6e2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508273"
---
# <a name="audiovideo-av-edge-servers-in-lync-server-2013"></a><span data-ttu-id="cf312-102">Audio/video (A/V) server perimetrali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf312-102">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf312-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="cf312-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="cf312-p101">Il servizio A/V Edge consente agli utenti interni, ovvero agli utenti connessi alla rete dell'organizzazione, di condividere audio e video con utenti esterni, che non sono connessi alla rete dell'organizzazione. Oltre ad audio e video, il servizio A/V Edge inoltre offre il supporto per attività come la condivisione del desktop e il trasferimento di file.</span><span class="sxs-lookup"><span data-stu-id="cf312-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). In addition to audio and video, the A/V Edge service also provides support for such things desktop sharing and file transfer.</span></span>

<span data-ttu-id="cf312-p102">Il servizio A/V Edge viene principalmente gestito mediante la configurazione A/V Edge. Queste impostazioni consentono di gestire la quantità massima di larghezza di banda da allocare per porta e per utente e di specificare per quanto tempo può essere utilizzato un token di autenticazione prima che debba essere rinnovato. Le impostazioni di configurazione A/V Edge possono essere applicate ai siti o ai singoli A/V Edge Server. Quando si determina la raccolta di impostazioni che avrà la priorità, utilizzare come riferimento le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cf312-p102">The A/V Edge service is primarily managed by using A/V Edge configuration; these settings enable you to manage the maximum amount of bandwidth to be allocated per port and per user, and to specify the length of time that an authentication token can be used before that token must be renewed. A/V Edge configuration settings can be applied to sites or to individual A/V Edge servers. When determining which collection of settings will take priority, use the following guide:</span></span>

  - <span data-ttu-id="cf312-109">Le impostazioni configurate nell'ambito del servizio, ovvero in un singolo server, hanno la priorità su tutto.</span><span class="sxs-lookup"><span data-stu-id="cf312-109">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="cf312-p103">Le impostazioni configurate nell'ambito del sito hanno la priorità su quelle configurate nell'ambito globale. Le impostazioni nell'ambito del servizio avranno tuttavia la precedenza sulle impostazioni nell'ambito del sito.</span><span class="sxs-lookup"><span data-stu-id="cf312-p103">Settings configured at the site scope take priority over settings configured at the global scope. However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="cf312-112">Le impostazioni nell'ambito globale verranno utilizzate solo se non vi sono impostazioni di servizio configurate nel singolo server e se non vi sono impostazioni per il sito in cui si trova tale server.</span><span class="sxs-lookup"><span data-stu-id="cf312-112">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="cf312-113">Il servizio A/V Edge può essere gestito solo utilizzando Lync Server PowerShell e i cmdlet di CsAVEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="cf312-113">The A/V Edge service can only be managed by using Lync Server PowerShell and the CsAVEdgeConfiguration cmdlets.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cf312-114">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="cf312-114">In This Section</span></span>

  - [<span data-ttu-id="cf312-115">Restituire le informazioni di configurazione di A/V Edge Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf312-115">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)

  - [<span data-ttu-id="cf312-116">Creare o modificare una raccolta di impostazioni di configurazione di A/V Edge Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf312-116">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)

  - [<span data-ttu-id="cf312-117">Eliminare una raccolta esistente di impostazioni di configurazione di A/V Edge Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf312-117">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

