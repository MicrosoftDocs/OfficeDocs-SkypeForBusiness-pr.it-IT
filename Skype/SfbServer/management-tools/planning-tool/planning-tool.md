---
title: Strumento di pianificazione di Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
description: Informazioni sull'utilizzo dello strumento di pianificazione di Skype for Business Server 2015.
ms.openlocfilehash: 8eec7865b74640cf6dfe4f5a5122f4c7091cc5ae
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050098"
---
# <a name="skype-for-business-server-2015-planning-tool"></a><span data-ttu-id="713db-103">Strumento di pianificazione di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="713db-103">Skype for Business Server 2015 Planning Tool</span></span>
 
<span data-ttu-id="713db-104">Informazioni sull'utilizzo dello strumento di pianificazione di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="713db-104">Guidance on using the Skype for Business Server 2015 Planning Tool.</span></span>
  
<span data-ttu-id="713db-105">Lo strumento di pianificazione di Skype for Business Server 2015 è uno strumento basato su una procedura guidata, che richiede domande sulla topologia di Skype for Business Server 2015 che si sta progettando.</span><span class="sxs-lookup"><span data-stu-id="713db-105">The Skype for Business Server 2015 Planning Tool is a wizard driven, interview-like tool that asks questions about the Skype for Business Server 2015 topology that you are designing.</span></span> <span data-ttu-id="713db-106">Lo strumento di pianificazione utilizza le informazioni fornite, unitamente alle procedure consigliate per la progettazione e la capacità della topologia, per presentare una topologia consigliata in base alle risposte fornite.</span><span class="sxs-lookup"><span data-stu-id="713db-106">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="713db-107">È possibile scaricare lo strumento di pianificazione dallo [strumento di pianificazione di Skype for Business Server 2015](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span><span class="sxs-lookup"><span data-stu-id="713db-107">You can download the Planning Tool from the [Skype for Business Server 2015 Planning Tool](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span></span>
  
<span data-ttu-id="713db-108">Infine, l'obiettivo dello strumento di pianificazione è quello di facilitare la complessità potenziale della progettazione di una topologia completa di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="713db-108">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="713db-109">Lo strumento fornisce anche riferimenti contestuali alla documentazione relativa alla pianificazione e alla distribuzione all'interno dello strumento, a condizione che sia disponibile una connessione Internet per la connessione al sito Web Microsoft.</span><span class="sxs-lookup"><span data-stu-id="713db-109">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft  website.</span></span>
  
<span data-ttu-id="713db-110">Dopo aver personalizzato la topologia con gli indirizzi TCP/IP e i nomi di dominio completi (FQDN) dell'infrastruttura, lo strumento di pianificazione rende disponibili una serie di report che comprendono la denominazione DNS (Domain Name System), le regole del firewall, i certificati e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="713db-110">After customizing the topology with the infrastructure's TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span> 
  
<span data-ttu-id="713db-111">L'utilizzo di questo strumento è il primo passaggio per la pianificazione dell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="713db-111">Using this tool is the first step in planning your implementation.</span></span> <span data-ttu-id="713db-112">Il passaggio successivo consiste nel inserire le informazioni specifiche del sito nel calcolatore di [capacità di Skype for Business server 2015](https://www.microsoft.com/download/details.aspx?id=51196), modificarle in base alle esigenze e quindi utilizzare lo [strumento di gestione di stress e prestazioni di Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=50367) per simulare e verificare che l'implementazione sia in grado di soddisfare le proprie necessità.</span><span class="sxs-lookup"><span data-stu-id="713db-112">The next step would be to input your site information specifics into the [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=51196), adjust as needed, then use the [Skype for Business Server 2015 Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367) to simulate and verify the implementation will serve your needs.</span></span>
  
<span data-ttu-id="713db-113">Lo strumento di pianificazione consente inoltre di esportare le informazioni in due formati:</span><span class="sxs-lookup"><span data-stu-id="713db-113">The Planning Tool also provides the ability to export information in two formats:</span></span>
  
- <span data-ttu-id="713db-114">Microsoft Excel (foglio di calcolo con estensione XML)</span><span class="sxs-lookup"><span data-stu-id="713db-114">Microsoft Excel (.xml spreadsheet)</span></span>
    
- <span data-ttu-id="713db-115">Microsoft Visio (. vdx)</span><span class="sxs-lookup"><span data-stu-id="713db-115">Microsoft Visio (.vdx)</span></span>
    
<span data-ttu-id="713db-116">Negli argomenti seguenti vengono introdotti e dettagliati lo strumento di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="713db-116">The following topics introduce and detail the Planning Tool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="713db-117">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="713db-117">In this section</span></span>

- [<span data-ttu-id="713db-118">Installare lo strumento di pianificazione in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="713db-118">Install the Planning Tool in Skype for Business Server 2015</span></span>](install.md)
    
- [<span data-ttu-id="713db-119">Software facoltativo</span><span class="sxs-lookup"><span data-stu-id="713db-119">Optional Software</span></span>](install.md#Optional_Software)
    
- [<span data-ttu-id="713db-120">Accedere allo strumento di pianificazione in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="713db-120">Navigate the Planning Tool in Skype for Business Server 2015</span></span>](navigate.md)
    
- [<span data-ttu-id="713db-121">Creare la progettazione della topologia iniziale per Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="713db-121">Create the initial topology design for Skype for Business Server 2015</span></span>](create-the-initial-design.md)
    
- [<span data-ttu-id="713db-122">Modificare la topologia in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="713db-122">Edit the topology in Skype for Business Server 2015</span></span>](edit-the-topology.md)
    
- [<span data-ttu-id="713db-123">Modificare il diagramma di configurazione di rete</span><span class="sxs-lookup"><span data-stu-id="713db-123">Edit the network configuration diagram</span></span>](edit-the-topology.md#Edit_Network_diagram)
    
- [<span data-ttu-id="713db-124">Esaminare i rapporti dell'amministratore in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="713db-124">Review the Administrator Reports in Skype for Business Server 2015</span></span>](review-the-administrator-reports.md)
    
## <a name="see-also"></a><span data-ttu-id="713db-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="713db-125">See also</span></span>

[<span data-ttu-id="713db-126">Installare Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="713db-126">Install Skype for Business Server 2015</span></span>](../../deploy/install/install.md)
  
[<span data-ttu-id="713db-127">Pianificare la messaggistica istantanea e la presenza in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="713db-127">Plan for instant messaging and presence in Skype for Business Server 2015</span></span>](../../plan-your-deployment/instant-messaging-and-presence.md)
