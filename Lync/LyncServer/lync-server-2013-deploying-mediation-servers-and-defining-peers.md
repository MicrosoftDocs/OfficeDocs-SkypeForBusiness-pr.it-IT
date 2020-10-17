---
title: 'Lync Server 2013: distribuzione di Mediation Server e definizione di peer'
description: 'Lync Server 2013: distribuzione di Mediation Server e definizione di peer.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Mediation Servers and defining peers
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412780(v=OCS.15)
ms:contentKeyID: 48185077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc3afce038371920beea1cc52549d8d027429e08
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545232"
---
# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a><span data-ttu-id="78d7f-103">Distribuzione di Mediation Server e definizione di peer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78d7f-103">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78d7f-104">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="78d7f-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="78d7f-105">Il carico di lavoro VoIP aziendale, le conferenze telefoniche con accesso esterno e le applicazioni vocali avanzate (applicazione Response Group, applicazione Parcheggio di chiamata, controllo di ammissione di chiamata e così via) sono disponibili nei pool Front end.</span><span class="sxs-lookup"><span data-stu-id="78d7f-105">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="78d7f-106">Con Lync Server 2013, la funzionalità del Mediation Server è incorporata nel front end server.</span><span class="sxs-lookup"><span data-stu-id="78d7f-106">With Lync Server 2013, the functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="78d7f-107">Non è più necessario un Mediation Server autonomo distinto.</span><span class="sxs-lookup"><span data-stu-id="78d7f-107">A separate stand-alone Mediation Server is no longer necessary.</span></span> <span data-ttu-id="78d7f-108">I pool Front end possono comunicare direttamente con i gateway supportati (un gateway PSTN (Public Switched Telephone Network) o un IP-PBX), eliminando la necessità che un Mediation Server funga da intermediario.</span><span class="sxs-lookup"><span data-stu-id="78d7f-108">Front End pools can communicate directly with supported gateways (a public switched telephone network (PSTN) gateway or an IP-PBX), removing the need for a Mediation Server to serve as an intermediary.</span></span>

<span data-ttu-id="78d7f-109">L'unica eccezione è rappresentata dalla configurazione di un trunk SIP per la connessione a un Session Border Controller per un provider di servizi di telefonia Internet (ITSP).</span><span class="sxs-lookup"><span data-stu-id="78d7f-109">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="78d7f-110">Per connettere l'infrastruttura VoIP aziendale al provider trunk SIP, è necessario distribuire un Mediation Server separato.</span><span class="sxs-lookup"><span data-stu-id="78d7f-110">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>

<span data-ttu-id="78d7f-111">La connessione tra Lync Server (il componente Mediation Server in un pool Front end o Mediation Server autonomo) e un gateway è definito come un'associazione logica denominata *trunk*.</span><span class="sxs-lookup"><span data-stu-id="78d7f-111">The connection between Lync Server (the Mediation Server component on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a *trunk*.</span></span> <span data-ttu-id="78d7f-112">Negli argomenti di questa sezione viene illustrato come definire un trunk e come distribuire un Mediation Server autonomo se si effettua la connessione a un trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="78d7f-112">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="78d7f-113">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="78d7f-113">In This Section</span></span>

  - [<span data-ttu-id="78d7f-114">Definire un Mediation Server in Generatore di topologie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78d7f-114">Define a Mediation Server in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [<span data-ttu-id="78d7f-115">Definire un gateway in Generatore di topologie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78d7f-115">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [<span data-ttu-id="78d7f-116">Installare i file per Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78d7f-116">Install the files for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-install-the-files-for-mediation-server.md)

  - [<span data-ttu-id="78d7f-117">Definire ulteriori trunk in Generatore di topologie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78d7f-117">Define additional trunks in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="78d7f-118">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="78d7f-118">Related Sections</span></span>

[<span data-ttu-id="78d7f-119">Configurazione delle conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78d7f-119">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

