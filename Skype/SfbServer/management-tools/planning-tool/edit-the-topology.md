---
title: Modificare la topologia in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Dopo aver completato le domande di colloquio iniziale, è possibile modificare il nome di dominio completo (FQDN) e gli indirizzi IP per il sito. A questo scopo, nella pagina topologia globale fare doppio clic sul sito che si vuole modificare.
ms.openlocfilehash: dae99620f34b832dd4abe0baf83d6df11b388750
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816445"
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a><span data-ttu-id="85dd5-104">Modificare la topologia in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="85dd5-104">Edit the topology in Skype for Business Server 2015</span></span>

<span data-ttu-id="85dd5-105">Dopo aver completato le domande di colloquio iniziale, è possibile modificare il nome di dominio completo (FQDN) e gli indirizzi IP per il sito.</span><span class="sxs-lookup"><span data-stu-id="85dd5-105">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site.</span></span> <span data-ttu-id="85dd5-106">A questo scopo, nella pagina **topologia globale** fare doppio clic sul sito che si vuole modificare.</span><span class="sxs-lookup"><span data-stu-id="85dd5-106">To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="85dd5-107">Lo strumento di pianificazione Visualizza la topologia di sito per il sito selezionato.</span><span class="sxs-lookup"><span data-stu-id="85dd5-107">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="85dd5-108">Nella parte inferiore della pagina del sito sono presenti quattro schede:</span><span class="sxs-lookup"><span data-stu-id="85dd5-108">At the bottom of the site page are four tabs:</span></span>

![Topologia del sito dello strumento di pianificazione](../../media/Planning_Tool_Site_Topology.png)

- <span data-ttu-id="85dd5-110">Topologia del sito-la pagina attualmente visualizzata con una panoramica visiva della topologia come consigliato.</span><span class="sxs-lookup"><span data-stu-id="85dd5-110">Site Topology - The currently displayed page with a visual overview of the topology as recommended.</span></span>

- <span data-ttu-id="85dd5-111">Diagramma reticolare Edge: la pagina del diagramma reticolare perimetrale è il punto in cui la finestra di progettazione esegue la maggior parte del lavoro nello strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="85dd5-111">Edge Network Diagram - The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="85dd5-112">Il diagramma Visualizza la configurazione di rete per una topologia di Skype for Business Server 2015 consigliata, con le voci modificabili per gli indirizzi IP e gli FQDN per server, pool e per i dispositivi di bilanciamento del carico DNS (hardware e Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="85dd5-112">The diagram displays the network configuration for a recommended Skype for Business Server 2015 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

- <span data-ttu-id="85dd5-113">Report amministratore Edge-il report amministratore Edge contiene un totale di quattro report:</span><span class="sxs-lookup"><span data-stu-id="85dd5-113">Edge Admin Report - The Edge Admin Report contains a total of four reports:</span></span>

     ![Pagina del rapporto di amministrazione della rete perimetrale](../../media/Planning_Tool_Summary_Report.png)

  - <span data-ttu-id="85dd5-115">Riepilogo-report generale delle impostazioni per la configurazione di rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="85dd5-115">Summary Report - A general report of settings for the Edge network configuration.</span></span> <span data-ttu-id="85dd5-116">Se si modificano i valori nella pagina del **diagramma reticolare** alla topologia TCP/IP e i valori FQDN di che verranno usati nella distribuzione effettiva, questi indirizzi e nomi verranno rappresentati qui.</span><span class="sxs-lookup"><span data-stu-id="85dd5-116">If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here.</span></span> <span data-ttu-id="85dd5-117">In caso contrario, verrà visualizzato il testo predefinito.</span><span class="sxs-lookup"><span data-stu-id="85dd5-117">Otherwise, the default text will appear.</span></span>

  - <span data-ttu-id="85dd5-118">Report certificato: il report certificato elenca il nome dell'oggetto e i nomi alternativi oggetto per i certificati necessari per la topologia.</span><span class="sxs-lookup"><span data-stu-id="85dd5-118">Certificate Report - The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>

  - <span data-ttu-id="85dd5-119">Report firewall: il report firewall elenca le informazioni necessarie per configurare i firewall perimetrali nell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="85dd5-119">Firewall Report - The firewall report lists information necessary to configure perimeter firewalls in the infrastructure.</span></span> <span data-ttu-id="85dd5-120">Sono inclusi gli indirizzi IP (valori predefiniti o modificati), il ruolo del server, l'IP di origine e la porta, la destinazione IP e la porta, il protocollo di trasporto, il protocollo dell'applicazione e le note rilevanti.</span><span class="sxs-lookup"><span data-stu-id="85dd5-120">This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>

  - <span data-ttu-id="85dd5-121">Report DNS: il report DNS elenca le informazioni rilevanti per le voci DNS che è necessario creare.</span><span class="sxs-lookup"><span data-stu-id="85dd5-121">DNS Report - The DNS Report lists relevant information for the DNS entries that you must create.</span></span> <span data-ttu-id="85dd5-122">Sono inclusi il tipo di record, il nome di dominio completo, l'indirizzo IP e i commenti necessari per l'operazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="85dd5-122">The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

- <span data-ttu-id="85dd5-123">Riepilogo sito-il riepilogo del sito presenta una panoramica delle selezioni effettuate rispondendo alle domande di colloquio iniziale o inserendo i valori nei **siti di progettazione**.</span><span class="sxs-lookup"><span data-stu-id="85dd5-123">Site Summary - The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**.</span></span> <span data-ttu-id="85dd5-124">Vengono presentate anche informazioni sulla capacità.</span><span class="sxs-lookup"><span data-stu-id="85dd5-124">Capacity information is also presented.</span></span>

    > [!NOTE]
    > <span data-ttu-id="85dd5-125">Le informazioni nella pagina di riepilogo del sito sono personalizzate per ogni progettazione e potrebbero non contenere tutte le sezioni o le informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="85dd5-125">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

## <a name="edit-the-network-configuration-diagram"></a><span data-ttu-id="85dd5-126">Modificare il diagramma di configurazione della rete</span><span class="sxs-lookup"><span data-stu-id="85dd5-126">Edit the network configuration diagram</span></span>
<span data-ttu-id="85dd5-127"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="85dd5-127"><a name="Edit_Network_diagram"> </a></span></span>

<span data-ttu-id="85dd5-128">La maggior parte del lavoro svolto da un progettista nello strumento di pianificazione di Skype for Business Server 2015 è costituito dalla definizione delle voci relative agli indirizzi IP e ai nomi di dominio completi per le voci del diagramma reticolare.</span><span class="sxs-lookup"><span data-stu-id="85dd5-128">Most of the work that a designer does in the Skype for Business Server 2015 Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="85dd5-129">Le informazioni immesse in questa pagina vengono riportate nei report e in altre informazioni contenute nello strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="85dd5-129">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span>

![Diagramma di rete dello strumento di pianificazione](../../media/Planning_Tool_Network_Diagram.png)

<span data-ttu-id="85dd5-131">Lo strumento di pianificazione crea un diagramma reticolare con testo predefinito per gli indirizzi IP e i nomi di dominio completi.</span><span class="sxs-lookup"><span data-stu-id="85dd5-131">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span>

<span data-ttu-id="85dd5-132">Per modificare il diagramma reticolare e i valori di input:</span><span class="sxs-lookup"><span data-stu-id="85dd5-132">To edit the network diagram and input values:</span></span>

1. <span data-ttu-id="85dd5-133">Scegliere una sezione della rete per iniziare a lavorare.</span><span class="sxs-lookup"><span data-stu-id="85dd5-133">Choose a section of the network to begin working on.</span></span> <span data-ttu-id="85dd5-134">Ad esempio, fare doppio clic sul testo, **Access1.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="85dd5-134">For example, double-click the text, **access1.contoso.com**.</span></span> <span data-ttu-id="85dd5-135">Nella finestra di dialogo visualizzata digitare il nome di dominio completo effettivo del server access1.contoso.com e l'indirizzo IP effettivo, sostituendo 131.107.155.3.</span><span class="sxs-lookup"><span data-stu-id="85dd5-135">In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>

2. <span data-ttu-id="85dd5-136">Fare clic su **OK** per salvare le voci.</span><span class="sxs-lookup"><span data-stu-id="85dd5-136">Click **OK** to save the entries.</span></span>

3. <span data-ttu-id="85dd5-137">Continuare a modificare gli indirizzi IP e gli FQDN, fornendo indirizzi IP virtuali per i servizi di bilanciamento del carico hardware o le voci del server per il bilanciamento del carico DNS (Domain Name System) per i server nei pool.</span><span class="sxs-lookup"><span data-stu-id="85dd5-137">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>

<span data-ttu-id="85dd5-138">Una caratteristica utile dello strumento di pianificazione è la possibilità di assegnare in modo incrementale un intervallo di indirizzi IP e nomi host del server, anziché richiedere alla finestra di progettazione di modificare ogni server separato in un pool.</span><span class="sxs-lookup"><span data-stu-id="85dd5-138">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool.</span></span> <span data-ttu-id="85dd5-139">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="85dd5-139">For example:</span></span>

1. <span data-ttu-id="85dd5-140">Fare doppio clic sui server front-end in pool.</span><span class="sxs-lookup"><span data-stu-id="85dd5-140">Double-click the pooled Front End Servers.</span></span> <span data-ttu-id="85dd5-141">Quando si apre la finestra di dialogo, selezionare **si vuole usare l'IPS e il nome di dominio completo come punti di partenza per tutti i server equivalenti di questo cluster?**.</span><span class="sxs-lookup"><span data-stu-id="85dd5-141">When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span>

2. <span data-ttu-id="85dd5-142">Ad esempio, il valore iniziale per il primo server è fe0101.contoso.com e un indirizzo IP di 192.168.21.122.</span><span class="sxs-lookup"><span data-stu-id="85dd5-142">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>

3. <span data-ttu-id="85dd5-143">Digitare fe0.contoso.com in **FQDN del server front-end**, digitare 192.168.21.131 nell' **indirizzo IP del server front-end**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="85dd5-143">Type fe0.contoso.com in **Front End Server FQDN**, type 192.168.21.131 in **Front End Server IP address**, and then click **OK**.</span></span>

4. <span data-ttu-id="85dd5-144">La caratteristica di incremento automatico aggiorna tutti i server del pool in FE01 tramite fe06 e tutti gli indirizzi IP da 192.168.21.131 a 136.</span><span class="sxs-lookup"><span data-stu-id="85dd5-144">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>

<span data-ttu-id="85dd5-145">Dopo aver completato tutte le modifiche, salvare la topologia completando la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="85dd5-145">After you have completed all edits, save the topology by completing the following steps:</span></span>

<span data-ttu-id="85dd5-146">Per salvare la struttura dello strumento di pianificazione, fare clic su **file**e quindi su **Salva topologia** o **Salva topologia con nome**.</span><span class="sxs-lookup"><span data-stu-id="85dd5-146">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="85dd5-147">Se viene visualizzata una finestra di dialogo **Salva strumento di pianificazione come** , digitare un nome per il file in **nome file**e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="85dd5-147">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="85dd5-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85dd5-148">See also</span></span>
<span data-ttu-id="85dd5-149"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="85dd5-149"><a name="Edit_Network_diagram"> </a></span></span>

[<span data-ttu-id="85dd5-150">Modifica della struttura</span><span class="sxs-lookup"><span data-stu-id="85dd5-150">Editing the Design</span></span>](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
