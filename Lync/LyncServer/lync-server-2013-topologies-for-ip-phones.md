---
title: 'Lync Server 2013: topologie per i telefoni IP'
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
ms.openlocfilehash: 69761715846cd65a44fe34c9c8465101e9ceb681
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045448"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-for-ip-phones-in-lync-server-2013"></a><span data-ttu-id="e516c-102">Topologie per i telefoni IP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e516c-102">Topologies for IP phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e516c-103">_**Ultimo argomento modificato:** 2012-06-21_</span><span class="sxs-lookup"><span data-stu-id="e516c-103">_**Topic Last Modified:** 2012-06-21_</span></span>

<span data-ttu-id="e516c-104">In questa sezione viene fornita una panoramica del processo di connettività e vengono illustrate le differenze tra la modalità di connessione di un telefono IP in una rete interna e in una rete esterna.</span><span class="sxs-lookup"><span data-stu-id="e516c-104">This section provides an overview of the connectivity process and explains the differences between how an IP phone connects in an internal and external network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e516c-105">Lync Server fornisce il supporto per i seguenti telefoni IP: Aastra 6721ip common area Phone, Aastra 6725ip Desk Phone, HP 4110 IP Phone (Common area Phone), HP 4120 IP Phone (Desk Phone), Polycom CX600 IP Desk Phone, Polycom CX700 IP Desk Phone, Polycom CX500 IP telefono di area comune e telefono di conferenza IP di Polycom CX3000.</span><span class="sxs-lookup"><span data-stu-id="e516c-105">Lync Server provides support for the following IP phones: the Aastra 6721ip common area phone, Aastra 6725ip desk phone, HP 4110 IP Phone (common area phone), HP 4120 IP Phone (desk phone), Polycom CX600 IP desk phone, Polycom CX700 IP desk phone, Polycom CX500 IP common area phone, and Polycom CX3000 IP conference phone.</span></span> <span data-ttu-id="e516c-106">Di tali telefoni, tutti gli utenti di Polycom CX700 possono eseguire Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="e516c-106">Of those phones, all but the Polycom CX700 can run Lync Phone Edition.</span></span>



</div>

<span data-ttu-id="e516c-107">Nel diagramma seguente vengono descritti tutti i componenti coinvolti nella connettività di un dispositivo nell'ambiente aziendale.</span><span class="sxs-lookup"><span data-stu-id="e516c-107">The following diagram describes all the components involved in device connectivity within the corporate environment.</span></span>

<span data-ttu-id="e516c-108">**Topologia interna**</span><span class="sxs-lookup"><span data-stu-id="e516c-108">**Internal Topology**</span></span>

<span data-ttu-id="e516c-109">![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")</span><span class="sxs-lookup"><span data-stu-id="e516c-109">![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e516c-110">La figura precedente è una rappresentazione logica e non una panoramica fisica.</span><span class="sxs-lookup"><span data-stu-id="e516c-110">The previous figure is a logical representation, not a physical overview.</span></span> <span data-ttu-id="e516c-111">Ad esempio, Active Directory Domain Services (AD DS) si trova raramente nello stesso computer di qualsiasi componente di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e516c-111">For example, Active Directory Domain Services (AD DS) is rarely located on the same machine as any Lync Server components.</span></span> <span data-ttu-id="e516c-112">L'archivio utente può essere contenuto nel server back-end, nel server di archiviazione o nel Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="e516c-112">The user store can be located on the Back End Server or on the Archiving and Monitoring Servers.</span></span> <span data-ttu-id="e516c-113">Lync Server Management Shell, il server Web e i servizi di aggiornamento fanno parte del ruolo del server front-end.</span><span class="sxs-lookup"><span data-stu-id="e516c-113">The Lync Server Management Shell, web server, and update services are all part of the Front End Server role.</span></span>



</div>

<span data-ttu-id="e516c-114">Nel diagramma seguente viene fornita una panoramica dei componenti coinvolti quando il dispositivo si trova all'esterno della rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="e516c-114">The following diagram provides an overview of the components involved when the device is located outside the corporate network.</span></span>

<span data-ttu-id="e516c-115">**Topologia esterna**</span><span class="sxs-lookup"><span data-stu-id="e516c-115">**External Topology**</span></span>

<span data-ttu-id="e516c-116">![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")</span><span class="sxs-lookup"><span data-stu-id="e516c-116">![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e516c-117">Il Servizio Web aggiornamento dispositivi offre un sito Web esterno e uno interno, ma in questo diagramma viene illustrato solo quello esterno.</span><span class="sxs-lookup"><span data-stu-id="e516c-117">The Device Update Web service provides an external and internal website, but only the external one is shown here.</span></span><BR><span data-ttu-id="e516c-p103">La posizione della funzione di registrazione e l'URL del Servizio Web aggiornamento dispositivi dell'organizzazione devono essere pubblicati in DNS se deve essere abilitato l'accesso esterno. Il server perimetrale inoltre deve essere distribuito e configurato correttamente per consentire le comunicazioni esterne dal dispositivo all'ambiente aziendale e viceversa. Questo viene omesso nel diagramma precedente perché la distribuzione di server perimetrali non è specifica della connettività di un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e516c-p103">The location of the Registrar and the URL of the Device Update Web service for the organization must be published in DNS if external access is to be enabled. Additionally, the Edge Server must be deployed and correctly configured to allow external communications from the device to the corporate environment and back. This is omitted from the previous diagram because Edge deployment is not specific to device connectivity.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

