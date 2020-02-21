---
title: 'Lync Server 2013: componenti e topologie per la messaggistica unificata locale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for on-premises Unified Messaging
ms:assetid: 22fc87cf-a7e5-4c8c-bb9b-101e5380cdcf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425711(v=OCS.15)
ms:contentKeyID: 48183619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a21f24e87f889213a92123886a871dd1f5209ed1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208102"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-on-premises-unified-messaging-in-lync-server-2013"></a><span data-ttu-id="bd328-102">Componenti e topologie per la messaggistica unificata locale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd328-102">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd328-103">_**Ultimo argomento modificato:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="bd328-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="bd328-104">In questo argomento vengono descritti i componenti di Microsoft Exchange Server 2013 necessari per fornire le funzionalità di messaggistica unificata di Exchange alla distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd328-104">This topic describes the Microsoft Exchange Server 2013 components required to provide Exchange Unified Messaging (UM) features to Lync Server 2013 deployment.</span></span> <span data-ttu-id="bd328-105">Vengono inoltre descritte le topologie supportate per l'integrazione della messaggistica unificata di Exchange locale.</span><span class="sxs-lookup"><span data-stu-id="bd328-105">It also describes the supported topologies for on-premises Exchange UM integration.</span></span>

<div>

## <a name="exchange-server-components"></a><span data-ttu-id="bd328-106">Componenti di Exchange Server</span><span class="sxs-lookup"><span data-stu-id="bd328-106">Exchange Server Components</span></span>

<span data-ttu-id="bd328-107">Per fornire le funzionalità e i servizi di messaggistica unificata di Exchange descritti in [funzionalità di messaggistica unificata integrata e Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md) per gli utenti di VoIP aziendale nell'organizzazione, è necessario distribuire un server cassette postali di Microsoft Exchange e un server Accesso client che ospita le cassette postali degli utenti e fornisce un singolo percorso di archiviazione per la posta elettronica e la segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="bd328-107">To provide the Exchange UM features and services described in [Features of integrated Unified Messaging and Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md) to Enterprise Voice users in your organization, you must deploy an Microsoft Exchange Mailbox server and Client Access server, which hosts user mailboxes and provides a single storage location for email and voice mail.</span></span> <span data-ttu-id="bd328-108">La messaggistica unificata di Exchange viene eseguita come servizio nei server cassette postali e accesso client di Exchange.</span><span class="sxs-lookup"><span data-stu-id="bd328-108">Exchange UM runs as a service on Exchange Mailbox and Client Access servers.</span></span>

<span data-ttu-id="bd328-109">Per informazioni dettagliate sui componenti di messaggistica unificata di Exchange in Microsoft Exchange Server 2007 e Microsoft Exchange Server 2010, vedere [Deploying on-premises Exchange Messaggistica unificata per fornire Lync Server 2013](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) segreteria telefonica nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="bd328-109">For details about Exchange UM components in Microsoft Exchange Server 2007 and Microsoft Exchange Server 2010, see [Deploying on-premises Exchange UM to provide Lync Server 2013 voice mail](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="bd328-110">Topologie supportate</span><span class="sxs-lookup"><span data-stu-id="bd328-110">Supported Topologies</span></span>

<span data-ttu-id="bd328-111">È possibile distribuire Lync Server 2013 e la messaggistica unificata di Exchange nella stessa foresta o più foreste.</span><span class="sxs-lookup"><span data-stu-id="bd328-111">You can deploy Lync Server 2013 and Exchange Unified Messaging (UM) in the same forest or multiple forests.</span></span> <span data-ttu-id="bd328-112">Se la distribuzione si estende su più insiemi di strutture, è necessario eseguire i passaggi di integrazione di Exchange per ogni foresta di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="bd328-112">If the deployment spans multiple forests, you must perform the Exchange integration steps for each Exchange UM forest.</span></span> <span data-ttu-id="bd328-113">Inoltre, è necessario configurare ogni foresta di Microsoft Exchange affinché consideri attendibile la foresta Lync Server 2013 e la foresta Lync Server 2013 per considerare attendibile ogni foresta di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="bd328-113">Furthermore, you must configure each Microsoft Exchange forest to trust the Lync Server 2013 forest and the Lync Server 2013 forest to trust each Exchange UM forest.</span></span> <span data-ttu-id="bd328-114">Oltre a questo trust tra foreste, è necessario che le impostazioni di messaggistica unificata di Exchange per tutti gli utenti siano impostate sugli oggetti utente nella foresta di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd328-114">In addition to this forest trust, the Exchange UM settings for all users must be set on the user objects in the Lync Server 2013 forest.</span></span>

<span data-ttu-id="bd328-115">Lync Server 2013 supporta le topologie seguenti per l'integrazione della messaggistica unificata di Exchange:</span><span class="sxs-lookup"><span data-stu-id="bd328-115">Lync Server 2013 supports the following topologies for Exchange UM integration:</span></span>

  - <span data-ttu-id="bd328-116">Foresta singola</span><span class="sxs-lookup"><span data-stu-id="bd328-116">Single forest</span></span>

  - <span data-ttu-id="bd328-117">Singolo dominio, ovvero foresta singola con un solo dominio.</span><span class="sxs-lookup"><span data-stu-id="bd328-117">Single domain (that is, a single forest with a single domain).</span></span> <span data-ttu-id="bd328-118">Lync Server 2013, Microsoft Exchange e tutti gli utenti risiedono nello stesso dominio.</span><span class="sxs-lookup"><span data-stu-id="bd328-118">Lync Server 2013, Microsoft Exchange, and users all reside in the same domain.</span></span>

  - <span data-ttu-id="bd328-119">Dominio multiplo, ovvero un dominio radice con uno o più domini figlio.</span><span class="sxs-lookup"><span data-stu-id="bd328-119">Multiple domain (that is, a root domain with one or more child domains).</span></span> <span data-ttu-id="bd328-120">Lync Server 2013 e i server di Microsoft Exchange vengono distribuiti in domini diversi dal dominio in cui vengono creati gli utenti.</span><span class="sxs-lookup"><span data-stu-id="bd328-120">Lync Server 2013, and Microsoft Exchange servers are deployed in different domains from the domain where you create users.</span></span> <span data-ttu-id="bd328-121">I server di messaggistica unificata di Exchange possono essere distribuiti in domini diversi dal pool Lync Server 2013 che supportano.</span><span class="sxs-lookup"><span data-stu-id="bd328-121">Exchange UM servers can be deployed in different domains from the Lync Server 2013 pool they support.</span></span>

  - <span data-ttu-id="bd328-122">Foresta multipla, ovvero foresta di risorse.</span><span class="sxs-lookup"><span data-stu-id="bd328-122">Multiple forest (that is, resource forest).</span></span> <span data-ttu-id="bd328-123">Lync Server 2013 è distribuito in una singola foresta e quindi gli utenti vengono distribuiti tra più foreste.</span><span class="sxs-lookup"><span data-stu-id="bd328-123">Lync Server 2013 is deployed in a single forest, and then users are distributed across multiple forests.</span></span> <span data-ttu-id="bd328-124">Gli attributi di messaggistica unificata di Exchange per gli utenti devono essere replicati nella foresta di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd328-124">The users’ Exchange UM attributes must be replicated over to the Lync Server 2013 forest.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bd328-125">Exchange può essere distribuito in più foreste.</span><span class="sxs-lookup"><span data-stu-id="bd328-125">Exchange can be deployed in multiple forests.</span></span> <span data-ttu-id="bd328-126">Ogni organizzazione di Exchange può fornire la messaggistica unificata di Exchange ai propri utenti oppure è possibile distribuire la messaggistica unificata di Exchange nella stessa foresta di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd328-126">Each Exchange organization can provide Exchange UM to its users, or Exchange UM can be deployed in the same forest as Lync Server 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

