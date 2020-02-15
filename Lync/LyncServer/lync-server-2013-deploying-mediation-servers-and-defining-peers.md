---
title: 'Lync Server 2013: distribuzione di Mediation Server e definizione di peer'
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
ms.openlocfilehash: 7e9ca9fa29d2646a38a9cbf94d79ba9766b21d62
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050648"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a><span data-ttu-id="7857f-102">Distribuzione di Mediation Server e definizione di peer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7857f-102">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7857f-103">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="7857f-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="7857f-104">Il carico di lavoro VoIP aziendale, le conferenze telefoniche con accesso esterno e le applicazioni vocali avanzate (applicazione Response Group, applicazione Parcheggio di chiamata, controllo di ammissione di chiamata e così via) sono disponibili nei pool Front end.</span><span class="sxs-lookup"><span data-stu-id="7857f-104">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="7857f-105">Con Lync Server 2013, la funzionalità del Mediation Server è incorporata nel front end server.</span><span class="sxs-lookup"><span data-stu-id="7857f-105">With Lync Server 2013, the functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="7857f-106">Non è più necessario un Mediation Server autonomo distinto.</span><span class="sxs-lookup"><span data-stu-id="7857f-106">A separate stand-alone Mediation Server is no longer necessary.</span></span> <span data-ttu-id="7857f-107">I pool Front end possono comunicare direttamente con i gateway supportati (un gateway PSTN (Public Switched Telephone Network) o un IP-PBX), eliminando la necessità che un Mediation Server funga da intermediario.</span><span class="sxs-lookup"><span data-stu-id="7857f-107">Front End pools can communicate directly with supported gateways (a public switched telephone network (PSTN) gateway or an IP-PBX), removing the need for a Mediation Server to serve as an intermediary.</span></span>

<span data-ttu-id="7857f-108">L'unica eccezione è rappresentata dalla configurazione di un trunk SIP per la connessione a un Session Border Controller per un provider di servizi di telefonia Internet (ITSP).</span><span class="sxs-lookup"><span data-stu-id="7857f-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="7857f-109">Per connettere l'infrastruttura VoIP aziendale al provider trunk SIP, è necessario distribuire un Mediation Server separato.</span><span class="sxs-lookup"><span data-stu-id="7857f-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>

<span data-ttu-id="7857f-110">La connessione tra Lync Server (il componente Mediation Server in un pool Front end o Mediation Server autonomo) e un gateway è definito come un'associazione logica denominata *trunk*.</span><span class="sxs-lookup"><span data-stu-id="7857f-110">The connection between Lync Server (the Mediation Server component on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a *trunk*.</span></span> <span data-ttu-id="7857f-111">Negli argomenti di questa sezione viene illustrato come definire un trunk e come distribuire un Mediation Server autonomo se si effettua la connessione a un trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="7857f-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7857f-112">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="7857f-112">In This Section</span></span>

  - [<span data-ttu-id="7857f-113">Definire un Mediation Server in Generatore di topologie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7857f-113">Define a Mediation Server in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [<span data-ttu-id="7857f-114">Definire un gateway in Generatore di topologie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7857f-114">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [<span data-ttu-id="7857f-115">Installare i file per Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7857f-115">Install the files for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-install-the-files-for-mediation-server.md)

  - [<span data-ttu-id="7857f-116">Definire ulteriori trunk in Generatore di topologie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7857f-116">Define additional trunks in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="7857f-117">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="7857f-117">Related Sections</span></span>

[<span data-ttu-id="7857f-118">Configurazione delle conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7857f-118">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

