---
title: 'Lync Server 2013: Distribuire i tipi di indirizzi IP in un Front End Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Front End Server
ms:assetid: b6c8e0f9-ec8e-4a4e-a525-756f9cd6b9d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205191(v=OCS.15)
ms:contentKeyID: 48185193
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f70ff3098f11cbb3d3b04602dca9c12a4998a367
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763328"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-front-end-server-for-lync-server-2013"></a><span data-ttu-id="d135e-102">Distribuire i tipi di indirizzi IP in un Front End Server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d135e-102">Deploy IP address types on a Front End Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d135e-103">_**Argomento Ultima modifica:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="d135e-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="d135e-104">Usando generatore di topologie, eseguire i passaggi descritti nella procedura seguente per distribuire i tipi di indirizzo IP in un server front-end.</span><span class="sxs-lookup"><span data-stu-id="d135e-104">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="d135e-105">Per distribuire i tipi di indirizzo IP in un server front-end</span><span class="sxs-lookup"><span data-stu-id="d135e-105">To deploy IP address types on a Front End Server</span></span>

1.  <span data-ttu-id="d135e-106">In **pool Enterprise Edition front-end**fare clic con il pulsante destro del mouse sul server all'interno di un pool e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="d135e-106">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="d135e-107">In alternativa, selezionare il server e quindi fare clic su **modifica proprietà** dal menu **azione** .</span><span class="sxs-lookup"><span data-stu-id="d135e-107">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2.  <span data-ttu-id="d135e-108">Nella finestra di dialogo **modifica proprietà** selezionare il tipo di indirizzo IP che si vuole configurare.</span><span class="sxs-lookup"><span data-stu-id="d135e-108">In the **Edit Properties** dialog box, select the IP address type that you want to configure.</span></span> <span data-ttu-id="d135e-109">Per una configurazione a doppio stack, selezionare **Abilita IPv4** e **Abilita IPv6**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="d135e-109">For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="d135e-110">**Finestra di dialogo Modifica proprietà per il pool del server front-end**</span><span class="sxs-lookup"><span data-stu-id="d135e-110">**Edit Properties dialog box for the Front End Server pool**</span></span>
    
    <span data-ttu-id="d135e-111">![Finestra di dialogo Modifica proprietà del server Front End](images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "Finestra di dialogo Modifica proprietà del server Front End")</span><span class="sxs-lookup"><span data-stu-id="d135e-111">![Front End Server Edit Properties dialog box](images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "Front End Server Edit Properties dialog box")</span></span>
    
      - <span data-ttu-id="d135e-112">**Usare tutti gli indirizzi IP configurati**.</span><span class="sxs-lookup"><span data-stu-id="d135e-112">**Use all configured IP addresses**.</span></span> <span data-ttu-id="d135e-113">Selezionare questa opzione se si vuole consentire l'uso di qualsiasi indirizzo IP definito nel computer.</span><span class="sxs-lookup"><span data-stu-id="d135e-113">Select this option if you want to allow any IP address defined on the computer to be used.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="d135e-114">Questa è l'opzione consigliata per le configurazioni IP versione 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="d135e-114">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

        
        </div>
    
      - <span data-ttu-id="d135e-115">**Limitare l'utilizzo del servizio agli indirizzi IP selezionati**.</span><span class="sxs-lookup"><span data-stu-id="d135e-115">**Limit service usage to selected IP addresses**.</span></span> <span data-ttu-id="d135e-116">Selezionare questa opzione per specificare un indirizzo specifico da usare nel nuovo server.</span><span class="sxs-lookup"><span data-stu-id="d135e-116">Select this option to specify a specific address to use on the new server.</span></span> <span data-ttu-id="d135e-117">Se si seleziona questa opzione, è necessario immettere un valore per l' **indirizzo IP principale**.</span><span class="sxs-lookup"><span data-stu-id="d135e-117">If you select this option, you must enter a value for **Primary IP address**.</span></span>
    
      - <span data-ttu-id="d135e-118">**Indirizzo IP principale**.</span><span class="sxs-lookup"><span data-stu-id="d135e-118">**Primary IP address**.</span></span> <span data-ttu-id="d135e-119">Immettere un indirizzo IP che il server userà per tutte le comunicazioni eccetto PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="d135e-119">Enter an IP address that the server will use for all communications except public switched telephone network (PSTN).</span></span> <span data-ttu-id="d135e-120">L'indirizzo IP immesso deve corrispondere al formato del tipo di indirizzo di selezione.</span><span class="sxs-lookup"><span data-stu-id="d135e-120">The IP address entered must match the format of the select address type.</span></span>
    
      - <span data-ttu-id="d135e-121">**Indirizzo IP PSTN**.</span><span class="sxs-lookup"><span data-stu-id="d135e-121">**PSTN IP address**.</span></span> <span data-ttu-id="d135e-122">L'installazione di altre schede di interfaccia di rete (NIC) per supportare la configurazione degli indirizzi IP PSTN per Lync Server 2013 non è supportata nei ruoli di Mediation Server collocati.</span><span class="sxs-lookup"><span data-stu-id="d135e-122">The installation of additional network interface cards (NIC)s to support the PSTN IP address configuration for Lync Server 2013 is not supported on collocated Mediation Server roles.</span></span> <span data-ttu-id="d135e-123">Per altre informazioni sulle configurazioni di NIC supportate per Lync Server 2013, vedere [piattaforme hardware del server per Lync server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="d135e-123">For more information about supported NIC configurations for Lync Server 2013, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

