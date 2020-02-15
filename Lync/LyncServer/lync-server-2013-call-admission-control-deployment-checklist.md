---
title: 'Lync Server 2013: elenco di controllo per la distribuzione di controlli di ammissione di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control deployment checklist
ms:assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398928(v=OCS.15)
ms:contentKeyID: 48185525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a8dc32eb017baf832128301b9639aefe23ae4ce
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045358"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="05086-102">Elenco di controllo per la distribuzione dei controlli di ammissione di chiamata per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05086-102">Call admission control deployment checklist for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05086-103">_**Ultimo argomento modificato:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="05086-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="05086-104">Utilizzare l'elenco di controllo seguente per verificare che siano state completate tutte le attività di configurazione necessarie per la distribuzione dei controlli di ammissione di chiamata (CAC).</span><span class="sxs-lookup"><span data-stu-id="05086-104">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy call admission control (CAC).</span></span>

  - <span data-ttu-id="05086-105">Se uno o più server perimetrali sono distribuiti, ogni indirizzo IP dell'interfaccia esterna deve essere aggiunto all'elenco di subnet nelle impostazioni di configurazione di rete, con una maschera di bit pari a 32.</span><span class="sxs-lookup"><span data-stu-id="05086-105">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32.</span></span> <span data-ttu-id="05086-106">È inoltre consigliabile associare questa subnet (indirizzo IP) all'ID sito di rete per la posizione geografica in cui è distribuito il servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="05086-106">You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="05086-107">I server perimetrali non sono necessari per implementare il servizio di controllo di ammissione.</span><span class="sxs-lookup"><span data-stu-id="05086-107">Edge servers are not required to implement CAC.</span></span>

    
    </div>

  - <span data-ttu-id="05086-108">Verificare che il servizio di controllo di ammissione di chiamata sia abilitato, tramite il pannello di gestione di Lync Server o eseguendo il cmdlet come specificato in [Enable Call Admission Control in Lync Server 2013](lync-server-2013-enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="05086-108">Make sure that CAC is enabled, either through Lync Server Control Panel or by running the cmdlet as specified in [Enable call admission control in Lync Server 2013](lync-server-2013-enable-call-admission-control.md).</span></span>

  - <span data-ttu-id="05086-109">Verificare che il servizio di controllo di ammissione sia abilitato in tutti i siti centrali.</span><span class="sxs-lookup"><span data-stu-id="05086-109">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="05086-110">È possibile eseguire questa operazione tramite il generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="05086-110">This can be done through the Topology Builder.</span></span> <span data-ttu-id="05086-111">Se viene generato un avviso quando si *pubblica, non* ignorarlo.</span><span class="sxs-lookup"><span data-stu-id="05086-111">If a warning is generated when you publish, *do not* ignore it.</span></span>

  - <span data-ttu-id="05086-112">Verificare che tutte le subnet gestite nella rete aziendale siano configurate nelle impostazioni di configurazione di rete.</span><span class="sxs-lookup"><span data-stu-id="05086-112">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="05086-113">È inoltre essenziale che ogni subnet sia associata a un sito di rete, come illustrato in [associare una subnet a un sito di rete in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="05086-113">It is also essential that every subnet be associated to a network site, as explained in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

  - <span data-ttu-id="05086-114">Verificare che la subnet o gli indirizzi IP di tutti i Front End Server, Survivable Branch Appliance (SBA), audio/video Conferencing Server (se in un pool separato) e Mediation Server siano configurati nelle impostazioni di configurazione di rete.</span><span class="sxs-lookup"><span data-stu-id="05086-114">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

