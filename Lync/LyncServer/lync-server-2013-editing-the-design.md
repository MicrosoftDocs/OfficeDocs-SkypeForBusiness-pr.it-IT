---
title: 'Lync Server 2013: modifica della progettazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the design
ms:assetid: 08f639ba-0e5f-4ae7-9191-c3d96c25b169
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558608(v=OCS.15)
ms:contentKeyID: 51541445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7607fb2f31107e3368fa52167dc5015eb1b71f15
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-design-in-lync-server-2013"></a><span data-ttu-id="55503-102">Modifica della progettazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55503-102">Editing the design in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55503-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="55503-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="55503-104">Dopo aver completato le domande relative all'intervista iniziale, è possibile modificare il nome di dominio completo (FQDN) e gli indirizzi IP per il sito.</span><span class="sxs-lookup"><span data-stu-id="55503-104">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site.</span></span> <span data-ttu-id="55503-105">A tale scopo, nella pagina **topologia globale** fare doppio clic sul sito che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="55503-105">To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="55503-106">Lo strumento di pianificazione Visualizza la topologia di sito per il sito selezionato.</span><span class="sxs-lookup"><span data-stu-id="55503-106">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="55503-107">Nella parte inferiore della pagina del sito sono disponibili quattro schede:</span><span class="sxs-lookup"><span data-stu-id="55503-107">At the bottom of the site page are four tabs:</span></span>

<span data-ttu-id="55503-108">![Topologia del sito dello strumento di pianificazione](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Topologia del sito dello strumento di pianificazione")</span><span class="sxs-lookup"><span data-stu-id="55503-108">![Planning Tool Site Topology](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Planning Tool Site Topology")</span></span>

  - <span data-ttu-id="55503-109">Topologia del sito – la pagina attualmente visualizzata con una panoramica visiva della topologia come consigliato.</span><span class="sxs-lookup"><span data-stu-id="55503-109">Site Topology – The currently displayed page with a visual overview of the topology as recommended.</span></span>

  - <span data-ttu-id="55503-110">Diagramma di rete perimetrale: la pagina del diagramma reticolare è la posizione in cui la finestra di progettazione esegue la maggior parte del lavoro nello strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="55503-110">Edge Network Diagram – The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="55503-111">Nel diagramma viene visualizzata la configurazione di rete per una topologia di Lync Server 2013 consigliata, con voci modificabili per gli indirizzi IP e FQDN per i server, il pool e i dispositivi di bilanciamento del carico DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="55503-111">The diagram displays the network configuration for a recommended Lync Server 2013 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

  - <span data-ttu-id="55503-112">Report amministratore Edge – il report amministratore Edge contiene un totale di quattro rapporti:</span><span class="sxs-lookup"><span data-stu-id="55503-112">Edge Admin Report – The Edge Admin Report contains a total of four reports:</span></span>
    
    <span data-ttu-id="55503-113">![Pagina del rapporto di amministrazione Edge](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Pagina del rapporto di amministrazione Edge")</span><span class="sxs-lookup"><span data-stu-id="55503-113">![Edge Admin Report page](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Edge Admin Report page")</span></span>  
    
      - <span data-ttu-id="55503-114">Report riepilogativo – un rapporto generale delle impostazioni per la configurazione della rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="55503-114">Summary Report – A general report of settings for the Edge network configuration.</span></span> <span data-ttu-id="55503-115">Se si modificano i valori della pagina del **diagramma di rete perimetrale** nella topologia TCP/IP e i valori FQDN di che verranno utilizzati nella distribuzione effettiva, tali indirizzi e nomi verranno rappresentati in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="55503-115">If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here.</span></span> <span data-ttu-id="55503-116">In caso contrario, verrà visualizzato il testo predefinito.</span><span class="sxs-lookup"><span data-stu-id="55503-116">Otherwise, the default text will appear.</span></span>
    
      - <span data-ttu-id="55503-117">Rapporto certificati: il report del certificato elenca i nomi soggetto e gli oggetti alternativi per i certificati necessari per la topologia.</span><span class="sxs-lookup"><span data-stu-id="55503-117">Certificate Report – The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>
    
      - <span data-ttu-id="55503-118">Report firewall: il report del firewall elenca le informazioni necessarie per configurare i firewall perimetrali nell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="55503-118">Firewall Report – The firewall report lists information necessary to configure perimeter firewalls in the infrastructure.</span></span> <span data-ttu-id="55503-119">Sono inclusi gli indirizzi IP (valori predefiniti o modificati), il ruolo del server, l'IP di origine e la porta, l'IP di destinazione e la porta, il protocollo di trasporto, il protocollo dell'applicazione e le note rilevanti.</span><span class="sxs-lookup"><span data-stu-id="55503-119">This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>
    
      - <span data-ttu-id="55503-120">Report DNS: il report DNS elenca le informazioni rilevanti per le voci DNS che è necessario creare.</span><span class="sxs-lookup"><span data-stu-id="55503-120">DNS Report – The DNS Report lists relevant information for the DNS entries that you must create.</span></span> <span data-ttu-id="55503-121">Sono inclusi il tipo di record, il nome di dominio completo, l'indirizzo IP e i commenti necessari per il corretto funzionamento.</span><span class="sxs-lookup"><span data-stu-id="55503-121">The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

  - <span data-ttu-id="55503-122">Riepilogo del sito: il riepilogo del sito presenta una panoramica delle selezioni effettuate rispondendo alle domande relative all'intervista iniziale o compilando i valori nei **siti di progettazione**.</span><span class="sxs-lookup"><span data-stu-id="55503-122">Site Summary – The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**.</span></span> <span data-ttu-id="55503-123">Vengono inoltre presentate informazioni sulla capacità.</span><span class="sxs-lookup"><span data-stu-id="55503-123">Capacity information is also presented.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="55503-124">Le informazioni nella pagina di riepilogo del sito sono personalizzate per ogni progettazione e potrebbero non contenere tutte le sezioni o informazioni dettagliate in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="55503-124">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="55503-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55503-125">See Also</span></span>


[<span data-ttu-id="55503-126">Modifica del diagramma di configurazione di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55503-126">Editing the network configuration diagram in Lync Server 2013</span></span>](lync-server-2013-editing-the-network-configuration-diagram.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

