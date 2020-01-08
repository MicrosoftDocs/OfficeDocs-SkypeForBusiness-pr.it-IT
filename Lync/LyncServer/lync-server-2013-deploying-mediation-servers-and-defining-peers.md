---
title: 'Lync Server 2013: Distribuzione di Mediation Server e definizione di peer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Mediation Servers and defining peers
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412780(v=OCS.15)
ms:contentKeyID: 48185077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b01ccf2e3822933842249df012877b13d10baef3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a><span data-ttu-id="24b0c-102">Distribuzione di Mediation Server e definizione di peer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24b0c-102">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24b0c-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="24b0c-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="24b0c-104">Il carico di lavoro VoIP aziendale, i servizi di conferenza telefonica con accesso esterno e le applicazioni vocali avanzate di Enterprise (Response Group Application, Call Park application, Call ammissioni Control (CAC) e così via) sono disponibili nei pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="24b0c-104">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="24b0c-105">Con Lync Server 2013, la funzionalità di Mediation Server è integrata nel server front-end.</span><span class="sxs-lookup"><span data-stu-id="24b0c-105">With Lync Server 2013, the functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="24b0c-106">Un Mediation Server autonomo separato non è più necessario.</span><span class="sxs-lookup"><span data-stu-id="24b0c-106">A separate stand-alone Mediation Server is no longer necessary.</span></span> <span data-ttu-id="24b0c-107">I pool Front-end possono comunicare direttamente con i gateway supportati (un gateway PSTN (Public Switched Telephone Network) o un IP-PBX), eliminando la necessità di un Mediation Server di fungere da intermediario.</span><span class="sxs-lookup"><span data-stu-id="24b0c-107">Front End pools can communicate directly with supported gateways (a public switched telephone network (PSTN) gateway or an IP-PBX), removing the need for a Mediation Server to serve as an intermediary.</span></span>

<span data-ttu-id="24b0c-108">L'unica eccezione è la configurazione di un trunk SIP per la connessione a un controller di bordo della sessione per un provider di servizi di telefonia Internet.</span><span class="sxs-lookup"><span data-stu-id="24b0c-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="24b0c-109">Per connettere l'infrastruttura VoIP aziendale al provider trunk SIP, è necessario distribuire un server di mediazione separato.</span><span class="sxs-lookup"><span data-stu-id="24b0c-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>

<span data-ttu-id="24b0c-110">La connessione tra Lync Server (il componente Mediation Server in un pool Front-end o un Mediation Server autonomo) e un gateway viene definita come associazione logica denominata *trunk*.</span><span class="sxs-lookup"><span data-stu-id="24b0c-110">The connection between Lync Server (the Mediation Server component on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a *trunk*.</span></span> <span data-ttu-id="24b0c-111">Gli argomenti di questa sezione descrivono come definire un trunk e come distribuire un Mediation Server autonomo, se ci si connette a un trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="24b0c-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="24b0c-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="24b0c-112">In This Section</span></span>

  - [<span data-ttu-id="24b0c-113">Definire un Mediation Server in Generatore di topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24b0c-113">Define a Mediation Server in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [<span data-ttu-id="24b0c-114">Definire un gateway in Generatore di topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24b0c-114">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [<span data-ttu-id="24b0c-115">Installare i file per Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24b0c-115">Install the files for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-install-the-files-for-mediation-server.md)

  - [<span data-ttu-id="24b0c-116">Definire trunk aggiuntivi in Generatore di topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24b0c-116">Define additional trunks in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="24b0c-117">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="24b0c-117">Related Sections</span></span>

[<span data-ttu-id="24b0c-118">Configurazione di conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24b0c-118">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

