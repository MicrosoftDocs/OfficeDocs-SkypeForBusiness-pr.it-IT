---
title: Chiamata Analitica e Dashboard qualità chiamata
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Learn about Call Analytics and Call Quality Dashboard and when to use them to monitor and troubleshoot call-quality problems in Skype for Business.
ms.openlocfilehash: 3871db21fef268f9589246b31ee285aa117d0412
ms.sourcegitcommit: 26d93a15c9d4704c08f3fabc5635839ce2456b2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2018
ms.locfileid: "20205087"
---
# <a name="call-analytics-and-call-quality-dashboard"></a><span data-ttu-id="b378f-103">Chiamata Analitica e Dashboard qualità chiamata</span><span class="sxs-lookup"><span data-stu-id="b378f-103">Call Analytics and Call Quality Dashboard</span></span>

<span data-ttu-id="b378f-104">Microsoft Teams e Skype per le aziende consentono di due modi per monitorare e risolvere i problemi di qualità delle chiamate: Analitica delle chiamate e il Dashboard di qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="b378f-104">Microsoft Teams and Skype for Business give you two ways to monitor and troubleshoot call-quality problems: Call Analytics and Call Quality Dashboard.</span></span> <span data-ttu-id="b378f-105">Questo articolo li descrive entrambi e indica quando usare l'uno o l'altro.</span><span class="sxs-lookup"><span data-stu-id="b378f-105">This article describes both and tells you when to use each one.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b378f-106">Chiamata Analitica è ora disponibile in Microsoft Teams e Skype per interfaccia di amministrazione di Business in https://admin.teams.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="b378f-106">Call Analytics is now available in the Microsoft Teams and Skype for Business admin center at https://admin.teams.microsoft.com.</span></span> <span data-ttu-id="b378f-107">Solo ultimi 30 giorni di dati è disponibile nelle chiamate Analitica.</span><span class="sxs-lookup"><span data-stu-id="b378f-107">Only last 30 days of data is available in Call Analytics.</span></span>
  
## <a name="whats-call-analytics-and-when-should-i-use-it"></a><span data-ttu-id="b378f-108">Che cos'è Call Analytics e quando è consigliabile usarlo?</span><span class="sxs-lookup"><span data-stu-id="b378f-108">What's Call Analytics, and when should I use it?</span></span>

<span data-ttu-id="b378f-109">Chiamata Analitica Visualizza informazioni dettagliate sui dispositivi, reti e connettività relative alle chiamate specifiche e riunioni per ogni utente in un Teams Microsoft Skype per conto di Business.</span><span class="sxs-lookup"><span data-stu-id="b378f-109">Call Analytics shows detailed information about the devices, networks, and connectivity related to the specific calls and meetings for each user in a Microsoft Teams or Skype for Business account.</span></span> <span data-ttu-id="b378f-110">Se si è un amministratore di Office 365, è possibile utilizzare chiamate Analitica risoluzione dei problemi di qualità e la connessione telefonica in Microsoft Teams e Skype per le aziende.</span><span class="sxs-lookup"><span data-stu-id="b378f-110">If you're an Office 365 admin, you can use Call Analytics to troubleshoot call quality and connection problems in Microsoft Teams and Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="b378f-111">Autorizzazioni di agenti help desk e il caricamento di topologia di rete sarà disponibile nel portale di amministrazione di nuovo nei prossimi mesi.</span><span class="sxs-lookup"><span data-stu-id="b378f-111">Helpdesk agent permissions and network topology upload will be available in the new admin portal in the coming months.</span></span>

<span data-ttu-id="b378f-112">Se desideri che gli utenti non amministratori, come gli agenti di helpdesk di fornitori esterni, possano usare Call Analytics, puoi assegnare loro autorizzazioni in modo che possano usare Call Analytics ma non possano accedere al resto dell'interfaccia di amministrazione di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="b378f-112">If you want non-admins, such as helpdesk agents from an external vendor, to use Call Analytics, you can assign permissions so that they can use Call Analytics but they can't access the rest of the Skype for Business Admin center:</span></span> 
  
- <span data-ttu-id="b378f-p104">**Agenti helpdesk con autorizzazioni di Livello 1**: gli agenti vendono un sottoinsieme limitato di dati e di informazioni personali identificabili (personally identifiable information, PII) in Call Analytics. Possono risolvere i problemi delle chiamate, ma inoltreranno i problemi di riunione a un agente di Livello 2.</span><span class="sxs-lookup"><span data-stu-id="b378f-p104">**Helpdesk agents with Tier 1 permissions**: Agents see a limited set of data and personally identifiable information (PII) in Call Analytics. They can troubleshoot calls, but they will hand off problems with meetings to a Tier 2 agent.</span></span>
    
- <span data-ttu-id="b378f-p105">**Agenti helpdesk con autorizzazioni di Livello 2**: gli agenti vedono tutti i dati disponibili in Call Analytics e risolvono i problemi di chiamate e riunioni. hanno accesso completo ai registri chiamate e alle informazioni del cliente.</span><span class="sxs-lookup"><span data-stu-id="b378f-p105">**Helpdesk agents with Tier 2 permissions**: Agents see all available data in Call Analytics and troubleshoot both calls and meetings. They have full access to call logs and customer information.</span></span>
    
<span data-ttu-id="b378f-117">Per i dettagli sull'installazione di Call Analytics, vedi [Configurazione di Skype for Business Call Analytics](set-up-call-analytics.md).</span><span class="sxs-lookup"><span data-stu-id="b378f-117">For details about setting up Call Analytics, see [Set up Skype for Business Call Analytics](set-up-call-analytics.md).</span></span> <span data-ttu-id="b378f-118">Per ulteriori informazioni sul funzionamento di agenti help desk con chiamata Analitica, vedere [Utilizzo delle chiamate Analitica per risolvere i problemi di qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span><span class="sxs-lookup"><span data-stu-id="b378f-118">For more information about how Helpdesk agents can work with Call Analytics, see [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a><span data-ttu-id="b378f-119">Che cos'è Call Quality Dashboard e quando è consigliabile usarlo?</span><span class="sxs-lookup"><span data-stu-id="b378f-119">What's the Call Quality Dashboard, and when should I use it?</span></span>

<span data-ttu-id="b378f-120">Call Analytics offre informazioni dettagliate e specifiche sulla qualità della chiamata dal punto di vista dell'utente.</span><span class="sxs-lookup"><span data-stu-id="b378f-120">Call Analytics gives you detailed, specific information about the call quality experienced by users.</span></span> <span data-ttu-id="b378f-121">Perché la chiamata dell'utente Antonio Rossi aveva un audio di bassa qualità oggi pomeriggio?</span><span class="sxs-lookup"><span data-stu-id="b378f-121">Why did user Tony Smith have a poor call this afternoon?</span></span> <span data-ttu-id="b378f-122">Mediante chiamata Analitica, un Microsoft Teams o Skype per agente help desk adeguatamente formati o amministratore aziendale può esaminare il dispositivo, rete, connettività e altri fattori legati alle chiamate di Tony.</span><span class="sxs-lookup"><span data-stu-id="b378f-122">Using Call Analytics, a Microsoft Teams or Skype for Business admin or trained helpdesk agent can investigate the device, network, connectivity, and other factors related to Tony's call.</span></span>
  
<span data-ttu-id="b378f-p108">Se da una parte CA è progettato per aiutare amministratori e agenti helpdesk a risolvere i problemi di qualità per specifiche chiamate, Call Quality Dashboard (CQD) è progettato per aiutare gli amministratori di Skype for Business e i tecnici di rete a ottimizzare una rete. CQD non è focalizzato sui singoli utenti, bensì sulle informazioni in aggregato di un'intera organizzazione di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="b378f-p108">Where CA is designed to help admins and helpdesk agents troubleshoot call quality problems with specific calls, the Call Quality Dashboard (CQD) is designed to help Skype for Business admins and network engineers optimize a network. CQD shifts focus from specific users and instead looks at aggregate information for an entire Skype for Business organization.</span></span> 
  
<span data-ttu-id="b378f-p109">Forse la bassa qualità della chiamata di Antonio è dovuta a un problema di rete che colpisce anche molti altri utenti. La singola esperienza di chiamata di Antonio non è visibile in CQD, ma viene dato un quadro generale della qualità complessiva delle chiamate effettuate tramite Skype for Business. Con CQD possono emergere degli schemi generali, che permettono ai tecnici di rete di fare una valutazione informata sulla qualità delle chiamate. CQD mette a disposizione report basati sulle metriche di chiamata che danno un'idea più dettagliata della qualità generale della chiamata, dei flussi di dati server-client e client-client e della qualità vocale a livello di [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span><span class="sxs-lookup"><span data-stu-id="b378f-p109">Maybe Tony's poor call quality is due to a network issue that's also affecting many other users. Tony's individual call experience isn't visible in CQD, but the overall quality of calls made using Skype for Business is captured. With the CQD, overall patterns may become apparent, allowing network engineers to make informed assessments of call quality. CQD provides reports of call quality metrics that give you insights into overall call quality, server-client and client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span> 
  
![Screenshot of Call Quality Dashboard in the Skype for Business Admin Center. Tabs shown are Overall Call Quality, Server - Client, Client - Client, and View Quality SLA.](../images/6eaccf99-8ee8-4f99-bdf2-ba1c72471cb9.png)
  
<span data-ttu-id="b378f-131">Per maggiori dettagli, consulta [Funzionalità di Call Quality Dashboard per Skype for Business online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).</span><span class="sxs-lookup"><span data-stu-id="b378f-131">For more details, see [Features of the Call Quality Dashboard for Skype for Business Online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).</span></span>
  
<span data-ttu-id="b378f-p111">Call Analytics e CQD funzionano parallelamente l'uno all'altro e possono essere usati come programmi indipendenti oppure insieme. Per esempio, ipotizziamo che un agente di Livello 1 decida che ha bisogno d'aiuto per risolvere un problema di chiamata. L'agente di Livello 1 trasferisce la chiamata a un agente di Livello 2, che ha accesso a più informazioni in Call Analytics rispetto all'agente di Livello 1. A sua volta, l'agente di Livello 2 può segnalare un problema a un tecnico di rete. Il tecnico di rete potrà consultare CQD per verificare se un problema generale relativo al sito sta contribuendo ai problemi di chiamata.</span><span class="sxs-lookup"><span data-stu-id="b378f-p111">Call Analytics and CQD run in parallel and can be used independently or together. For example, say a Tier 1 agent determines that they need more help troubleshooting a call problem. The Tier 1 agent passes the call to a Tier 2 agent, who has access to more information in Call Analytics than the Tier 1 agent. In turn, the Tier 2 agent can alert a network engineer to an issue. The network engineer may check CQD to see if an overall site-related issue could be a contributing cause of call problems.</span></span>
  
<span data-ttu-id="b378f-137">Per ulteriori informazioni su CQD, vedere [attivazione e l'utilizzo del Dashboard di qualità delle chiamate per team di Microsoft e Skype Business online](turning-on-and-using-call-quality-dashboard.md) e [dimensioni e misure disponibile nel Dashboard di qualità delle chiamate per team di Microsoft e Skype Business online](dimensions-and-measures-available-in-call-quality-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="b378f-137">For more information about CQD, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](turning-on-and-using-call-quality-dashboard.md) and [Dimensions and measures available in Call Quality Dashboard for Microsoft Teams and Skype for Business Online](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b378f-138">See also</span><span class="sxs-lookup"><span data-stu-id="b378f-138">Related topics</span></span>
[<span data-ttu-id="b378f-139">Configurazione di Skype for Business Call Analytics</span><span class="sxs-lookup"><span data-stu-id="b378f-139">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="b378f-140">Utilizzo delle chiamate Analitica per la risoluzione dei Skype insufficiente per le aziende qualità delle chiamate</span><span class="sxs-lookup"><span data-stu-id="b378f-140">Use Call Analytics to troubleshoot poor Skype for Business call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

  
 
