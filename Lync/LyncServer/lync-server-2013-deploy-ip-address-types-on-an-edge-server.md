---
title: 'Lync Server 2013: distribuire i tipi di indirizzi IP in un server perimetrale'
description: 'Lync Server 2013: distribuire i tipi di indirizzi IP in un server perimetrale.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on an Edge Server
ms:assetid: 6e2fe7e8-6e90-4d1a-8fc5-e3be92c46571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204984(v=OCS.15)
ms:contentKeyID: 48184435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7798ca2f7b38865a2b4ea373546dd4e7203f5b8e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558662"
---
# <a name="deploy-ip-address-types-on-an-edge-server-for-lync-server-2013"></a><span data-ttu-id="58be3-103">Distribuire i tipi di indirizzi IP in un server perimetrale per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58be3-103">Deploy IP address types on an Edge Server for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58be3-104">_**Ultimo argomento modificato:** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="58be3-104">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="58be3-105">Utilizzando Generatore di topologie, eseguire i passaggi descritti nella procedura seguente per distribuire i tipi di indirizzi IP in un server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="58be3-105">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on an Edge Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="58be3-106">Per distribuire tipi di indirizzo IP su un server perimetrale</span><span class="sxs-lookup"><span data-stu-id="58be3-106">To deploy IP address types on an Edge Server</span></span>

1.  <span data-ttu-id="58be3-107">In Generatore di topologie, in pool di server **perimetrali**, fare clic con il pulsante destro del mouse su di esso in un pool e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="58be3-107">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="58be3-108">(Alternativamente, selezionare il server e fare clic su **Modifica proprietà** dal menu **Azione**.)</span><span class="sxs-lookup"><span data-stu-id="58be3-108">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2.  <span data-ttu-id="58be3-p102">Nella finestra **Modifica proprietà**, selezionare la configurazione dell'indirizzo IP che si desidera supportare. Nelle figure seguenti è mostrata una configurazione dual stack per l'interfaccia interna e l'interfaccia esterna.</span><span class="sxs-lookup"><span data-stu-id="58be3-p102">In the **Edit Properties** window, select the IP address configuration that you want to support. The following figures show a dual stack configuration for the internal interface and the external interface.</span></span>
    
    <span data-ttu-id="58be3-111">**Interfaccia interna del server perimetrale dual stack**</span><span class="sxs-lookup"><span data-stu-id="58be3-111">**Dual stacked Edge Server internal interface**</span></span>
    
    <span data-ttu-id="58be3-112">![Pagina delle proprietà generali di Lync Server](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Pagina delle proprietà generali di Lync Server")</span><span class="sxs-lookup"><span data-stu-id="58be3-112">![Lync Server general properties page](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Lync Server general properties page")</span></span>
    
    <span data-ttu-id="58be3-113">**Interfaccia esterna del server perimetrale dual stack**</span><span class="sxs-lookup"><span data-stu-id="58be3-113">**Dual stacked Edge Server external interface**</span></span>
    
    <span data-ttu-id="58be3-114">![Lync Server Next Hop/pagina di configurazione esterna](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Lync Server Next Hop/pagina di configurazione esterna")</span><span class="sxs-lookup"><span data-stu-id="58be3-114">![Lync Server next hop/external configuration page](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Lync Server next hop/external configuration page")</span></span>

3.  <span data-ttu-id="58be3-115">Per ciascun tipo di indirizzo selezionato, è necessario fornire gli indirizzi interni e esterni appropriati.</span><span class="sxs-lookup"><span data-stu-id="58be3-115">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

