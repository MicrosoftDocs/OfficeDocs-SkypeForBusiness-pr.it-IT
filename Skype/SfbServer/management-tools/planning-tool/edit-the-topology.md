---
title: Modificare la topologia in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
description: Dopo aver completato le domande iniziali, è possibile modificare il nome di dominio completo (FQDN) e gli indirizzi IP per il sito. A tale scopo, nella pagina Topologia globale fare doppio clic sul sito che si desidera modificare.
ms.openlocfilehash: 9a345c753195c32907d078d5ee4a267b8b96d6b0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093184"
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a><span data-ttu-id="45ad7-104">Modificare la topologia in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="45ad7-104">Edit the topology in Skype for Business Server 2015</span></span>

<span data-ttu-id="45ad7-105">Dopo aver completato le domande iniziali, è possibile modificare il nome di dominio completo (FQDN) e gli indirizzi IP per il sito.</span><span class="sxs-lookup"><span data-stu-id="45ad7-105">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site.</span></span> <span data-ttu-id="45ad7-106">A tale scopo, nella **pagina Topologia globale** fare doppio clic sul sito che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="45ad7-106">To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="45ad7-107">Lo Strumento di pianificazione visualizza la topologia del sito per il sito selezionato.</span><span class="sxs-lookup"><span data-stu-id="45ad7-107">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="45ad7-108">Nella parte inferiore della pagina del sito sono presenti quattro schede:</span><span class="sxs-lookup"><span data-stu-id="45ad7-108">At the bottom of the site page are four tabs:</span></span>

![Topologia del sito dello strumento di pianificazione](../../media/Planning_Tool_Site_Topology.png)

- <span data-ttu-id="45ad7-110">Topologia sito - La pagina attualmente visualizzata con una panoramica visiva della topologia come consigliato.</span><span class="sxs-lookup"><span data-stu-id="45ad7-110">Site Topology - The currently displayed page with a visual overview of the topology as recommended.</span></span>

- <span data-ttu-id="45ad7-111">Diagramma reticolare perimetrale - La pagina Diagramma reticolare perimetrale è la posizione in cui il progettista esegue la maggior parte delle operazioni nello strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="45ad7-111">Edge Network Diagram - The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="45ad7-112">Nel diagramma viene visualizzata la configurazione di rete per una topologia consigliata di Skype for Business Server 2015, con voci modificabili per gli indirizzi IP e gli FQDN per server, pool ed hardware e servizi di bilanciamento del carico DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="45ad7-112">The diagram displays the network configuration for a recommended Skype for Business Server 2015 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

- <span data-ttu-id="45ad7-113">Edge Admin Report - Il report dell'amministratore di Edge contiene un totale di quattro report:</span><span class="sxs-lookup"><span data-stu-id="45ad7-113">Edge Admin Report - The Edge Admin Report contains a total of four reports:</span></span>

     ![Pagina Report amministratore Edge](../../media/Planning_Tool_Summary_Report.png)

  - <span data-ttu-id="45ad7-115">Rapporto riepilogativo - Report generale delle impostazioni per la configurazione della rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="45ad7-115">Summary Report - A general report of settings for the Edge network configuration.</span></span> <span data-ttu-id="45ad7-116">Se si modificano i valori nella pagina **Diagramma** reti perimetrale con i valori TCP/IP e FQDN della topologia che verranno utilizzati nella distribuzione effettiva, tali indirizzi e nomi verranno rappresentati qui.</span><span class="sxs-lookup"><span data-stu-id="45ad7-116">If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here.</span></span> <span data-ttu-id="45ad7-117">In caso contrario, verrà visualizzato il testo predefinito.</span><span class="sxs-lookup"><span data-stu-id="45ad7-117">Otherwise, the default text will appear.</span></span>

  - <span data-ttu-id="45ad7-118">Rapporto certificati - Nel report del certificato verranno elencati il nome soggetto e i nomi alternativi del soggetto per i certificati necessari per la topologia.</span><span class="sxs-lookup"><span data-stu-id="45ad7-118">Certificate Report - The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>

  - <span data-ttu-id="45ad7-119">Report firewall - Nel report del firewall sono elencate le informazioni necessarie per configurare i firewall perimetrali nell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="45ad7-119">Firewall Report - The firewall report lists information necessary to configure perimeter firewalls in the infrastructure.</span></span> <span data-ttu-id="45ad7-120">Sono inclusi gli indirizzi IP (valori predefiniti o modificati), il ruolo del server, l'IP e la porta di origine, l'IP e la porta di destinazione, il protocollo di trasporto, il protocollo dell'applicazione e le note rilevanti.</span><span class="sxs-lookup"><span data-stu-id="45ad7-120">This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>

  - <span data-ttu-id="45ad7-121">Rapporto DNS - Nel rapporto DNS sono elencate le informazioni rilevanti per le voci DNS che è necessario creare.</span><span class="sxs-lookup"><span data-stu-id="45ad7-121">DNS Report - The DNS Report lists relevant information for the DNS entries that you must create.</span></span> <span data-ttu-id="45ad7-122">Sono inclusi il tipo di record, l'FQDN, l'indirizzo IP e i commenti necessari per l'operazione corretta.</span><span class="sxs-lookup"><span data-stu-id="45ad7-122">The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

- <span data-ttu-id="45ad7-123">Riepilogo sito- Il riepilogo del sito presenta una panoramica delle selezioni effettuate rispondendo alle domande iniziali del colloquio o compilando i valori in **Siti di progettazione.**</span><span class="sxs-lookup"><span data-stu-id="45ad7-123">Site Summary - The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**.</span></span> <span data-ttu-id="45ad7-124">Vengono presentate anche le informazioni sulla capacità.</span><span class="sxs-lookup"><span data-stu-id="45ad7-124">Capacity information is also presented.</span></span>

    > [!NOTE]
    > <span data-ttu-id="45ad7-125">Le informazioni nella pagina Riepilogo sito sono personalizzate per ogni progettazione e potrebbero non contenere tutte le sezioni o le informazioni qui descritte.</span><span class="sxs-lookup"><span data-stu-id="45ad7-125">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

## <a name="edit-the-network-configuration-diagram"></a><span data-ttu-id="45ad7-126">Modificare il diagramma di configurazione di rete</span><span class="sxs-lookup"><span data-stu-id="45ad7-126">Edit the network configuration diagram</span></span>
<span data-ttu-id="45ad7-127"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="45ad7-127"><a name="Edit_Network_diagram"> </a></span></span>

<span data-ttu-id="45ad7-128">La maggior parte delle attività che un progettista esegue nello strumento di pianificazione di Skype for Business Server 2015 consiste nella definizione delle voci per gli indirizzi IP e i nomi di dominio completi (FQDN) per le voci nel diagramma di rete.</span><span class="sxs-lookup"><span data-stu-id="45ad7-128">Most of the work that a designer does in the Skype for Business Server 2015 Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="45ad7-129">Le informazioni immesse in questa pagina vengono riportate nei report e nelle altre informazioni contenute nello Strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="45ad7-129">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span>

![Diagramma di rete dello strumento di pianificazione](../../media/Planning_Tool_Network_Diagram.png)

<span data-ttu-id="45ad7-131">Lo strumento di pianificazione crea un diagramma di rete con testo predefinito per gli indirizzi IP e gli FQDN.</span><span class="sxs-lookup"><span data-stu-id="45ad7-131">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span>

<span data-ttu-id="45ad7-132">Per modificare il diagramma di rete e i valori di input:</span><span class="sxs-lookup"><span data-stu-id="45ad7-132">To edit the network diagram and input values:</span></span>

1. <span data-ttu-id="45ad7-133">Scegliere una sezione della rete da cui iniziare.</span><span class="sxs-lookup"><span data-stu-id="45ad7-133">Choose a section of the network to begin working on.</span></span> <span data-ttu-id="45ad7-134">Ad esempio, fare doppio clic sul testo, **access1.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="45ad7-134">For example, double-click the text, **access1.contoso.com**.</span></span> <span data-ttu-id="45ad7-135">Nella finestra di dialogo visualizzata digitare l'FQDN effettivo del server access1.contoso.com e l'indirizzo IP effettivo, sostituendo 131.107.155.3.</span><span class="sxs-lookup"><span data-stu-id="45ad7-135">In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>

2. <span data-ttu-id="45ad7-136">Fare clic su **OK** per salvare le immissioni.</span><span class="sxs-lookup"><span data-stu-id="45ad7-136">Click **OK** to save the entries.</span></span>

3. <span data-ttu-id="45ad7-137">Continuare a modificare gli indirizzi IP e gli FQDN, fornendo indirizzi IP virtuali per i dispositivi di bilanciamento del carico hardware o le voci relative ai server per il bilanciamento del carico DNS (Domain Name System) per i server dei pool.</span><span class="sxs-lookup"><span data-stu-id="45ad7-137">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>

<span data-ttu-id="45ad7-p111">Nello Strumento di pianificazione è disponibile una funzionalità utile che consente di assegnare in modo incrementale un intervallo di indirizzi IP e nomi host di server anziché richiedere al progettista di modificare ogni server separato di un pool. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="45ad7-p111">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool. For example:</span></span>

1. <span data-ttu-id="45ad7-140">Fare doppio clic sui Front End Server in pool.</span><span class="sxs-lookup"><span data-stu-id="45ad7-140">Double-click the pooled Front End Servers.</span></span> <span data-ttu-id="45ad7-141">Quando viene visualizzata la finestra di dialogo, selezionare **Utilizzare questi IP e l'FQDN come punti di partenza per tutti i server equivalenti nel cluster?**.</span><span class="sxs-lookup"><span data-stu-id="45ad7-141">When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span>

2. <span data-ttu-id="45ad7-142">Ad esempio, il valore iniziale per il primo server è fe0101.contoso.com e un indirizzo IP di 192.168.21.122.</span><span class="sxs-lookup"><span data-stu-id="45ad7-142">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>

3. <span data-ttu-id="45ad7-143">Digitare fe0.contoso.com in **FQDN Front End Server,** digitare 192.168.21.131 in Indirizzo IP **front-end server** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="45ad7-143">Type fe0.contoso.com in **Front End Server FQDN**, type 192.168.21.131 in **Front End Server IP address**, and then click **OK**.</span></span>

4. <span data-ttu-id="45ad7-144">La funzionalità di incremento automatico aggiorna tutti i server del pool da fe01 a fe06 e tutti gli indirizzi IP da 192.168.21.131 a 136.</span><span class="sxs-lookup"><span data-stu-id="45ad7-144">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>

<span data-ttu-id="45ad7-145">Dopo aver completato tutte le modifiche, salvare la topologia completando la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="45ad7-145">After you have completed all edits, save the topology by completing the following steps:</span></span>

<span data-ttu-id="45ad7-146">Per salvare la struttura dello strumento di pianificazione, fare clic **su File** e quindi su **Salva** topologia o Salva topologia **con nome.**</span><span class="sxs-lookup"><span data-stu-id="45ad7-146">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="45ad7-147">Se viene visualizzata una finestra di dialogo **Salva file dello Strumento di pianificazione con nome**, digitare un nome per il file in **Nome file** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="45ad7-147">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="45ad7-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45ad7-148">See also</span></span>
<span data-ttu-id="45ad7-149"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="45ad7-149"><a name="Edit_Network_diagram"> </a></span></span>

[<span data-ttu-id="45ad7-150">Modifica della struttura</span><span class="sxs-lookup"><span data-stu-id="45ad7-150">Editing the Design</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-editing-the-design)