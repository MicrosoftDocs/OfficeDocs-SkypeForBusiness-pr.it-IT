---
title: 'Lync Server 2013: distribuire i tipi di indirizzi IP in un front end server'
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
ms.openlocfilehash: f3be24a05cf75adfc999205bb306010ba43fa1d6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150915"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-front-end-server-for-lync-server-2013"></a><span data-ttu-id="1feac-102">Distribuire i tipi di indirizzi IP in un front end server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1feac-102">Deploy IP address types on a Front End Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1feac-103">_**Ultimo argomento modificato:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="1feac-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="1feac-104">Utilizzando Generatore di topologie, eseguire i passaggi descritti nella procedura seguente per distribuire i tipi di indirizzi IP in un front end server.</span><span class="sxs-lookup"><span data-stu-id="1feac-104">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="1feac-105">Per distribuire i tipi di indirizzi IP in un Front End Server</span><span class="sxs-lookup"><span data-stu-id="1feac-105">To deploy IP address types on a Front End Server</span></span>

1.  <span data-ttu-id="1feac-p101">In **Pool Enterprise Edition Front End** fare clic con il pulsante destro del mouse sul server all'interno di un pool e quindi scegliere **Modifica proprietà**. In alternativa, selezionare il server e quindi scegliere **Modifica proprietà** dal menu **Azione**.</span><span class="sxs-lookup"><span data-stu-id="1feac-p101">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**. (Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2.  <span data-ttu-id="1feac-p102">Nella finestra di dialogo **Modifica proprietà** selezionare il tipo di indirizzo IP che si desidera configurare. Per una configurazione con dual stack, selezionare **Abilita IPv4** e **Abilita IPv6**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="1feac-p102">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="1feac-110">**Finestra di dialogo Modifica proprietà per il pool Front End Server**</span><span class="sxs-lookup"><span data-stu-id="1feac-110">**Edit Properties dialog box for the Front End Server pool**</span></span>
    
    <span data-ttu-id="1feac-111">![Finestra di dialogo Modifica proprietà di front end server](images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "Finestra di dialogo Modifica proprietà di front end server")</span><span class="sxs-lookup"><span data-stu-id="1feac-111">![Front End Server Edit Properties dialog box](images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "Front End Server Edit Properties dialog box")</span></span>
    
      - <span data-ttu-id="1feac-p103">**Usa tutti gli indirizzi IP configurati**. Selezionare questa opzione se si desidera consentire l'utilizzo di qualsiasi indirizzo IP definito nel computer.</span><span class="sxs-lookup"><span data-stu-id="1feac-p103">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="1feac-114">Questa è l'opzione consigliata per le configurazioni IP versione 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="1feac-114">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

        
        </div>
    
      - <span data-ttu-id="1feac-p104">**Limita utilizzo servizio a indirizzi IP selezionati**. Selezionare questa opzione per specificare un determinato indirizzo da utilizzare nel nuovo server. Se si seleziona questa opzione, sarà necessario immettere un valore per **Indirizzo IP primario**.</span><span class="sxs-lookup"><span data-stu-id="1feac-p104">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for **Primary IP address**.</span></span>
    
      - <span data-ttu-id="1feac-p105">**Indirizzo IP primario**. Immettere un indirizzo IP che verrà utilizzato dal server per tutte le comunicazioni, tranne quelle su rete PSTN (Public Switched Telephone Network). L'indirizzo IP immesso deve corrispondere al formato del tipo di indirizzo selezionato.</span><span class="sxs-lookup"><span data-stu-id="1feac-p105">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>
    
      - <span data-ttu-id="1feac-121">**Indirizzo IP PSTN**.</span><span class="sxs-lookup"><span data-stu-id="1feac-121">**PSTN IP address**.</span></span> <span data-ttu-id="1feac-122">L'installazione di altre schede di interfaccia di rete (NIC) per supportare la configurazione degli indirizzi IP PSTN per Lync Server 2013 non è supportata nei ruoli Mediation Server collocati.</span><span class="sxs-lookup"><span data-stu-id="1feac-122">The installation of additional network interface cards (NIC)s to support the PSTN IP address configuration for Lync Server 2013 is not supported on collocated Mediation Server roles.</span></span> <span data-ttu-id="1feac-123">Per ulteriori informazioni sulle configurazioni NIC supportate per Lync Server 2013, vedere [server hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md).</span><span class="sxs-lookup"><span data-stu-id="1feac-123">For more information about supported NIC configurations for Lync Server 2013, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

