---
title: 'Lync Server 2013: topologie per telefoni IP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies for IP phones
ms:assetid: 26ebffcf-43ff-4e70-847d-0fbc90e94e57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425740(v=OCS.15)
ms:contentKeyID: 48183662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e05a56d30167f2e20a383cde9fcfaaa70418e650
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-for-ip-phones-in-lync-server-2013"></a><span data-ttu-id="c89da-102">Topologie per telefoni IP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c89da-102">Topologies for IP phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c89da-103">_**Argomento Ultima modifica:** 2012-06-21_</span><span class="sxs-lookup"><span data-stu-id="c89da-103">_**Topic Last Modified:** 2012-06-21_</span></span>

<span data-ttu-id="c89da-104">Questa sezione offre una panoramica del processo di connettività e spiega le differenze tra il modo in cui un telefono IP si connette in una rete interna ed esterna.</span><span class="sxs-lookup"><span data-stu-id="c89da-104">This section provides an overview of the connectivity process and explains the differences between how an IP phone connects in an internal and external network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c89da-105">Lync Server offre il supporto per i telefoni IP seguenti: il telefono per l'area comune Aastra 6721ip, il telefono da tavolo Aastra 6725ip, il telefono IP HP 4110 (telefono per l'area comune), il telefono IP HP 4120 (telefono da tavolo), il telefono da tavolo IP di Polycom CX600, il telefono da tavolo IP di Polycom CX700 Polycom IP telefono per area comune e telefono per conferenze IP di Polycom CX3000.</span><span class="sxs-lookup"><span data-stu-id="c89da-105">Lync Server provides support for the following IP phones: the Aastra 6721ip common area phone, Aastra 6725ip desk phone, HP 4110 IP Phone (common area phone), HP 4120 IP Phone (desk phone), Polycom CX600 IP desk phone, Polycom CX700 IP desk phone, Polycom CX500 IP common area phone, and Polycom CX3000 IP conference phone.</span></span> <span data-ttu-id="c89da-106">Di questi telefoni, tutti tranne il Polycom CX700 può eseguire Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="c89da-106">Of those phones, all but the Polycom CX700 can run Lync Phone Edition.</span></span>



</div>

<span data-ttu-id="c89da-107">Il diagramma seguente descrive tutti i componenti coinvolti nella connettività dei dispositivi nell'ambiente aziendale.</span><span class="sxs-lookup"><span data-stu-id="c89da-107">The following diagram describes all the components involved in device connectivity within the corporate environment.</span></span>

<span data-ttu-id="c89da-108">**Topologia interna**</span><span class="sxs-lookup"><span data-stu-id="c89da-108">**Internal Topology**</span></span>

<span data-ttu-id="c89da-109">![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")</span><span class="sxs-lookup"><span data-stu-id="c89da-109">![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c89da-110">La figura precedente è una rappresentazione logica, non una panoramica fisica.</span><span class="sxs-lookup"><span data-stu-id="c89da-110">The previous figure is a logical representation, not a physical overview.</span></span> <span data-ttu-id="c89da-111">Ad esempio, Active Directory Domain Services (AD DS) si trova raramente nello stesso computer dei componenti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c89da-111">For example, Active Directory Domain Services (AD DS) is rarely located on the same machine as any Lync Server components.</span></span> <span data-ttu-id="c89da-112">L'archivio utenti può essere posizionato sul server back-end o sui server di archiviazione e monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="c89da-112">The user store can be located on the Back End Server or on the Archiving and Monitoring Servers.</span></span> <span data-ttu-id="c89da-113">Lync Server Management Shell, Web Server e Update Services fanno parte del ruolo del server front-end.</span><span class="sxs-lookup"><span data-stu-id="c89da-113">The Lync Server Management Shell, web server, and update services are all part of the Front End Server role.</span></span>



</div>

<span data-ttu-id="c89da-114">Il diagramma seguente offre una panoramica dei componenti coinvolti quando il dispositivo si trova all'esterno della rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="c89da-114">The following diagram provides an overview of the components involved when the device is located outside the corporate network.</span></span>

<span data-ttu-id="c89da-115">**Topologia esterna**</span><span class="sxs-lookup"><span data-stu-id="c89da-115">**External Topology**</span></span>

<span data-ttu-id="c89da-116">![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")</span><span class="sxs-lookup"><span data-stu-id="c89da-116">![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c89da-117">Il servizio Web Update del dispositivo fornisce un sito Web esterno e interno, ma solo quello esterno è illustrato qui.</span><span class="sxs-lookup"><span data-stu-id="c89da-117">The Device Update Web service provides an external and internal website, but only the external one is shown here.</span></span><BR><span data-ttu-id="c89da-118">La posizione del registrar e l'URL del servizio Web di aggiornamento dei dispositivi per l'organizzazione devono essere pubblicati in DNS se è necessario abilitare l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="c89da-118">The location of the Registrar and the URL of the Device Update Web service for the organization must be published in DNS if external access is to be enabled.</span></span> <span data-ttu-id="c89da-119">Inoltre, il server perimetrale deve essere distribuito e configurato correttamente per consentire le comunicazioni esterne dal dispositivo all'ambiente aziendale e viceversa.</span><span class="sxs-lookup"><span data-stu-id="c89da-119">Additionally, the Edge Server must be deployed and correctly configured to allow external communications from the device to the corporate environment and back.</span></span> <span data-ttu-id="c89da-120">Questa operazione viene omessa dal diagramma precedente perché la distribuzione di Edge non è specifica della connettività dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="c89da-120">This is omitted from the previous diagram because Edge deployment is not specific to device connectivity.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

