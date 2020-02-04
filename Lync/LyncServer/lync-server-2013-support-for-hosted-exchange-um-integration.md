---
title: "Lync Server 2013: Supporto per l'integrazione di messaggistica unificata di Exchange ospitata"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for hosted Exchange UM integration
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48185376
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24139ad5294bf908a85b797300397fa8b2ac9140
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a><span data-ttu-id="8cc54-102">Supporto per l'integrazione di messaggistica unificata di Exchange ospitata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cc54-102">Support for hosted Exchange UM integration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cc54-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="8cc54-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="8cc54-104">L'applicazione di routing ExUM di Lync Server 2013 supporta l'integrazione con la messaggistica unificata di Exchange in un ambiente locale, in cui Lync Server 2013 e la messaggistica unificata di Exchange sono installati localmente all'interno dell'organizzazione o con la messaggistica unificata di Exchange ospitata da un provider di servizi, come illustrato nel diagramma seguente.</span><span class="sxs-lookup"><span data-stu-id="8cc54-104">The Lync Server 2013 ExUM Routing application supports integration with Exchange Unified Messaging (UM) in an on-premises environment, where Lync Server 2013 and Exchange UM are both installed locally within your enterprise, or in with Exchange UM hosted by a service provider, as shown in the following diagram.</span></span>

<span data-ttu-id="8cc54-105">![Distribuzione della messaggistica unificata di Exchange con Lync Server in locale](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Distribuzione della messaggistica unificata di Exchange con Lync Server in locale")</span><span class="sxs-lookup"><span data-stu-id="8cc54-105">![On-premises Lync Server Exchange UM Deployment](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "On-premises Lync Server Exchange UM Deployment")</span></span>

<span data-ttu-id="8cc54-106">Sono supportate le modalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="8cc54-106">The following modes are supported:</span></span>

  - <span data-ttu-id="8cc54-107">**Modalità**   locale Lync Server 2013 e messaggistica unificata di Exchange sono entrambi distribuiti su server locali all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8cc54-107">**On-premises Mode**   Lync Server 2013 and Exchange UM are both deployed on local servers within your enterprise.</span></span>

  - <span data-ttu-id="8cc54-108">**Modalità cross-locale**   Lync Server 2013 è distribuito nei server locali all'interno dell'organizzazione e la messaggistica unificata di Exchange è ospitata in una struttura del provider di servizi online, ad esempio un Data Center di Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8cc54-108">**Cross-premises Mode**   Lync Server 2013 is deployed on local servers within your enterprise and Exchange UM is hosted in an online service provider’s facility, such as a Microsoft Exchange Online data center.</span></span>

  - <span data-ttu-id="8cc54-109">**Modalità mista**   la distribuzione di Lync Server 2013 include alcune cassette postali utente in server locali che utilizzano Microsoft Exchange Server all'interno dell'organizzazione e alcune cassette postali ospitate in un centro dati del servizio Exchange ospitato.</span><span class="sxs-lookup"><span data-stu-id="8cc54-109">**Mixed Mode**   Your Lync Server 2013 deployment has some user mailboxes homed on local servers running Microsoft Exchange Server within your enterprise and some mailboxes homed in a hosted Exchange service data center.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8cc54-110">La modalità mista può essere usata come soluzione transitoria durante la valutazione e la migrazione graduale degli utenti alla messaggistica unificata di Exchange ospitata o come soluzione permanente se si sceglie di conservare i servizi di messaggistica unificata di Exchange in locale dopo la migrazione di altri utenti.</span><span class="sxs-lookup"><span data-stu-id="8cc54-110">Mixed mode can be used as a transitional solution during evaluation and stepwise migration of users to hosted Exchange UM, or as a permanent solution if you opt to keep some users’ Exchange UM services on-premises after migrating others.</span></span>

    
    </div>

<span data-ttu-id="8cc54-111">Per integrare Lync Server 2013 con UM ospitata di Exchange, è necessario configurare uno *spazio di indirizzi SIP condiviso* (detto anche *dominio diviso*).</span><span class="sxs-lookup"><span data-stu-id="8cc54-111">To integrate Lync Server 2013 with hosted Exchange UM, you must configure a *shared SIP address space* (also called a *split domain*).</span></span> <span data-ttu-id="8cc54-112">In questa configurazione, sia Lync Server 2013 che il provider di servizi di messaggistica unificata di Exchange ospitati di terze parti possono accedere allo stesso spazio di indirizzi del dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="8cc54-112">In this configuration, both Lync Server 2013 and the third-party hosted Exchange UM service provider can access the same SIP domain address space.</span></span> <span data-ttu-id="8cc54-113">Per informazioni dettagliate, vedere [architettura di integrazione della messaggistica unificata di Exchange ospitata in Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="8cc54-113">For details, see [Hosted Exchange UM integration architecture in Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

