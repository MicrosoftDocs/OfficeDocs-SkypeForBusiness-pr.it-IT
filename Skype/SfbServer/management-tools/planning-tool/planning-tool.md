---
title: Progettazione della topologia per Lync Server 2013 mediante lo strumento di pianificazione
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
description: Istruzioni sull'uso dello strumento di pianificazione di Skype for Business Server 2015.
ms.openlocfilehash: b130ca05200ea30bed8008399050affa96438644
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191234"
---
# <a name="skype-for-business-server-2015-planning-tool"></a><span data-ttu-id="d061c-103">Progettazione della topologia per Lync Server 2013 mediante lo strumento di pianificazione</span><span class="sxs-lookup"><span data-stu-id="d061c-103">Skype for Business Server 2015 Planning Tool</span></span>
 
<span data-ttu-id="d061c-104">Istruzioni sull'uso dello strumento di pianificazione di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d061c-104">Guidance on using the Skype for Business Server 2015 Planning Tool.</span></span>
  
<span data-ttu-id="d061c-105">Lo strumento di pianificazione di Skype for Business Server 2015 è uno strumento basato su una procedura guidata, con un'intervista che pone domande sulla topologia di Skype for Business Server 2015 che si sta progettando.</span><span class="sxs-lookup"><span data-stu-id="d061c-105">The Skype for Business Server 2015 Planning Tool is a wizard driven, interview-like tool that asks questions about the Skype for Business Server 2015 topology that you are designing.</span></span> <span data-ttu-id="d061c-106">Lo strumento di pianificazione usa le informazioni fornite, insieme alle procedure consigliate per la progettazione e la capacità della topologia, per presentare una topologia consigliata in base alle risposte fornite.</span><span class="sxs-lookup"><span data-stu-id="d061c-106">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="d061c-107">È possibile scaricare lo strumento di pianificazione dallo [strumento di pianificazione di Skype for Business Server 2015](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span><span class="sxs-lookup"><span data-stu-id="d061c-107">You can download the Planning Tool from the [Skype for Business Server 2015 Planning Tool](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span></span>
  
<span data-ttu-id="d061c-108">In definitiva, l'obiettivo dello strumento di pianificazione è quello di semplificare la complessità potenziale della progettazione di una topologia completa di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d061c-108">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="d061c-109">Lo strumento fornisce anche riferimenti contestuali alla documentazione relativa alla pianificazione e alla distribuzione all'interno dello strumento, a condizione che sia disponibile una connessione Internet per la connessione al sito Web Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d061c-109">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft  website.</span></span>
  
<span data-ttu-id="d061c-110">Dopo la personalizzazione della topologia con gli indirizzi TCP/IP dell'infrastruttura e i nomi di dominio completi (FQDN), lo strumento di pianificazione rende disponibile una serie di report che includono la denominazione DNS (Domain Name System), le regole del firewall, i certificati e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="d061c-110">After customizing the topology with the infrastructure's TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span> 
  
<span data-ttu-id="d061c-111">L'uso di questo strumento è il primo passo per pianificare l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="d061c-111">Using this tool is the first step in planning your implementation.</span></span> <span data-ttu-id="d061c-112">Il passaggio successivo consiste nell'inserire le informazioni specifiche del sito nella calcolatrice della [capacità di Skype for Business server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=51196), modificarla in base alle esigenze e quindi usare lo [strumento di stress e prestazioni di Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=50367) per simulare e verificare la l'implementazione sarà utile alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="d061c-112">The next step would be to input your site information specifics into the [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/en-us/download/details.aspx?id=51196), adjust as needed, then use the [Skype for Business Server 2015 Stress and Performance Tool](https://www.microsoft.com/en-us/download/details.aspx?id=50367) to simulate and verify the implementation will serve your needs.</span></span>
  
<span data-ttu-id="d061c-113">Lo strumento di pianificazione offre anche la possibilità di esportare informazioni in due formati:</span><span class="sxs-lookup"><span data-stu-id="d061c-113">The Planning Tool also provides the ability to export information in two formats:</span></span>
  
- <span data-ttu-id="d061c-114">Microsoft Excel (foglio di calcolo XML)</span><span class="sxs-lookup"><span data-stu-id="d061c-114">Microsoft Excel (.xml spreadsheet)</span></span>
    
- <span data-ttu-id="d061c-115">Microsoft Visio (. vdx)</span><span class="sxs-lookup"><span data-stu-id="d061c-115">Microsoft Visio (.vdx)</span></span>
    
<span data-ttu-id="d061c-116">Gli argomenti seguenti introducono e dettagliano lo strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="d061c-116">The following topics introduce and detail the Planning Tool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="d061c-117">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="d061c-117">In this section</span></span>

- [<span data-ttu-id="d061c-118">Installazione di software facoltativo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d061c-118">Install the Planning Tool in Skype for Business Server 2015</span></span>](install.md)
    
- [<span data-ttu-id="d061c-119">Software facoltativo</span><span class="sxs-lookup"><span data-stu-id="d061c-119">Optional Software</span></span>](install.md#Optional_Software)
    
- [<span data-ttu-id="d061c-120">Spostamento all'interno dello strumento di pianificazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d061c-120">Navigate the Planning Tool in Skype for Business Server 2015</span></span>](navigate.md)
    
- [<span data-ttu-id="d061c-121">Creare la progettazione della topologia iniziale per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d061c-121">Create the initial topology design for Skype for Business Server 2015</span></span>](create-the-initial-design.md)
    
- [<span data-ttu-id="d061c-122">Modificare la topologia in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d061c-122">Edit the topology in Skype for Business Server 2015</span></span>](edit-the-topology.md)
    
- [<span data-ttu-id="d061c-123">Modificare il diagramma di configurazione della rete</span><span class="sxs-lookup"><span data-stu-id="d061c-123">Edit the network configuration diagram</span></span>](edit-the-topology.md#Edit_Network_diagram)
    
- [<span data-ttu-id="d061c-124">Esaminare i report dell'amministratore in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d061c-124">Review the Administrator Reports in Skype for Business Server 2015</span></span>](review-the-administrator-reports.md)
    
## <a name="see-also"></a><span data-ttu-id="d061c-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d061c-125">See also</span></span>

[<span data-ttu-id="d061c-126">Installare Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d061c-126">Install Skype for Business Server 2015</span></span>](../../deploy/install/install.md)
  
[<span data-ttu-id="d061c-127">Pianificare la messaggistica istantanea e la presenza in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d061c-127">Plan for instant messaging and presence in Skype for Business Server 2015</span></span>](../../plan-your-deployment/instant-messaging-and-presence.md)
