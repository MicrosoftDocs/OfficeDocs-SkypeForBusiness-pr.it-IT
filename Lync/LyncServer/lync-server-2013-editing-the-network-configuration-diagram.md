---
title: 'Lync Server 2013: modifica del diagramma di configurazione di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the network configuration diagram
ms:assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558643(v=OCS.15)
ms:contentKeyID: 51541469
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f23e1ca036690f7f48071c46db6769b75424fe1e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="editing-the-network-configuration-diagram-in-lync-server-2013"></a><span data-ttu-id="90fb0-102">Modifica del diagramma di configurazione di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90fb0-102">Editing the network configuration diagram in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90fb0-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="90fb0-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="90fb0-104">La maggior parte del lavoro svolto da un progettista in Lync Server 2013 è costituito dalla definizione delle voci relative agli indirizzi IP e ai nomi di dominio completi (FQDN) per le voci del diagramma reticolare.</span><span class="sxs-lookup"><span data-stu-id="90fb0-104">Most of the work that a designer does in the Lync Server 2013, Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="90fb0-105">Le informazioni immesse in questa pagina vengono riportate nei report e nelle altre informazioni contenute nello strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="90fb0-105">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span>

<span data-ttu-id="90fb0-106">![Diagramma di rete dello strumento di pianificazione](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "Diagramma di rete dello strumento di pianificazione")</span><span class="sxs-lookup"><span data-stu-id="90fb0-106">![Planning Tool Network diagram](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "Planning Tool Network diagram")</span></span>

<span data-ttu-id="90fb0-107">Lo strumento di pianificazione crea un diagramma reticolare con testo predefinito per gli indirizzi IP e gli FQDN.</span><span class="sxs-lookup"><span data-stu-id="90fb0-107">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span>

<span data-ttu-id="90fb0-108">Per modificare il diagramma di rete e i valori di input:</span><span class="sxs-lookup"><span data-stu-id="90fb0-108">To edit the network diagram and input values:</span></span>

1.  <span data-ttu-id="90fb0-109">Scegliere una sezione della rete da cui iniziare.</span><span class="sxs-lookup"><span data-stu-id="90fb0-109">Choose a section of the network to begin working on.</span></span> <span data-ttu-id="90fb0-110">Ad esempio, fare doppio clic sul testo **Access1.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="90fb0-110">For example, double-click the text, **access1.contoso.com**.</span></span> <span data-ttu-id="90fb0-111">Nella finestra di dialogo che si apre, digitare il nome di dominio completo effettivo del server access1.contoso.com e l'indirizzo IP effettivo, sostituendo 131.107.155.3.</span><span class="sxs-lookup"><span data-stu-id="90fb0-111">In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>

2.  <span data-ttu-id="90fb0-112">Fare clic su **OK** per salvare le immissioni.</span><span class="sxs-lookup"><span data-stu-id="90fb0-112">Click **OK** to save the entries.</span></span>

3.  <span data-ttu-id="90fb0-113">Continuare a modificare gli indirizzi IP e gli FQDN, fornendo indirizzi IP virtuali per i dispositivi di bilanciamento del carico hardware o le voci relative ai server per il bilanciamento del carico DNS (Domain Name System) per i server dei pool.</span><span class="sxs-lookup"><span data-stu-id="90fb0-113">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>

<span data-ttu-id="90fb0-p103">Nello Strumento di pianificazione è disponibile una funzionalità utile che consente di assegnare in modo incrementale un intervallo di indirizzi IP e nomi host di server anziché richiedere al progettista di modificare ogni server separato di un pool. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="90fb0-p103">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool. For example:</span></span>

1.  <span data-ttu-id="90fb0-116">Fare doppio clic sui Front End Server in pool.</span><span class="sxs-lookup"><span data-stu-id="90fb0-116">Double-click the pooled Front End Servers.</span></span> <span data-ttu-id="90fb0-117">Quando viene visualizzata la finestra di dialogo, selezionare **Utilizzare questi IP e l'FQDN come punti di partenza per tutti i server equivalenti nel cluster?**.</span><span class="sxs-lookup"><span data-stu-id="90fb0-117">When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span>

2.  <span data-ttu-id="90fb0-118">Ad esempio, il valore iniziale del primo server è fe0101.contoso.com e un indirizzo IP di 192.168.21.122.</span><span class="sxs-lookup"><span data-stu-id="90fb0-118">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>

3.  <span data-ttu-id="90fb0-119">Digitare **fe0.contoso.com** nell' **FQDN front end server**, digitare **192.168.21.131** nell' **indirizzo IP front end server**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="90fb0-119">Type **fe0.contoso.com** in **Front End Server FQDN**, type **192.168.21.131** in **Front End Server IP address**, and then click **OK**.</span></span>

4.  <span data-ttu-id="90fb0-120">La funzionalità di incremento automatico consente di aggiornare tutti i server del pool a FE01 tramite fe06 e tutti gli indirizzi IP da 192.168.21.131 a 136.</span><span class="sxs-lookup"><span data-stu-id="90fb0-120">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>

<span data-ttu-id="90fb0-121">Dopo aver completato tutte le modifiche, salvare la topologia completando i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="90fb0-121">After you have completed all edits, save the topology by completing the following steps:</span></span>

<span data-ttu-id="90fb0-122">Per salvare la progettazione dello strumento di pianificazione, fare clic su **file**e quindi su **Salva topologia** o **Salva topologia con nome**.</span><span class="sxs-lookup"><span data-stu-id="90fb0-122">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="90fb0-123">Se viene visualizzata una finestra di dialogo **Salva file dello Strumento di pianificazione con nome**, digitare un nome per il file in **Nome file** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="90fb0-123">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="90fb0-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90fb0-124">See Also</span></span>


[<span data-ttu-id="90fb0-125">Modifica della progettazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90fb0-125">Editing the design in Lync Server 2013</span></span>](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

