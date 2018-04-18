---
title: Qual è la differenza tra Call Analytics e Call Quality Dashboard?
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
ms.openlocfilehash: 869b4373d6e1bea65700532b52959aa2126d94d9
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="whats-the-difference-between-call-analytics-and-call-quality-dashboard"></a><span data-ttu-id="97a20-103">Qual è la differenza tra Call Analytics e Call Quality Dashboard?</span><span class="sxs-lookup"><span data-stu-id="97a20-103">What's the difference between Call Analytics and Call Quality Dashboard?</span></span>

<span data-ttu-id="97a20-p101">[] Skype for Business offre due modi per monitorare e risolvere i problemi di qualità delle chiamate: Call Analytics e Call Quality Dashboard. Questo articolo li descrive entrambi e indica quando usare l'uno o l'altro.</span><span class="sxs-lookup"><span data-stu-id="97a20-p101">Skype for Business gives you two ways to monitor and troubleshoot call-quality problems: Call Analytics and Call Quality Dashboard. This article describes both and tells you when to use each one.</span></span>
  
> [!NOTE]
> <span data-ttu-id="97a20-p102">Call Analytics è attualmente in fase di anteprima. Il testo e le immagini qui riportati possono non corrispondere alla tua esperienza di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="97a20-p102">Call Analytics is currently in preview. Text and images described here may not match your experience.</span></span> 
  
## <a name="whats-call-analytics-and-when-should-i-use-it"></a><span data-ttu-id="97a20-108">Che cos'è Call Analytics e quando è consigliabile usarlo?</span><span class="sxs-lookup"><span data-stu-id="97a20-108">What's Call Analytics, and when should I use it?</span></span>

<span data-ttu-id="97a20-p103">Call Analytics mostra informazioni dettagliate sui dispositivi, le reti e la connettività relativamente alle specifiche chiamate e riunioni di ciascun utente in un account Skype for Business. Se sei un amministratore di Skype for Business, puoi usare Call Analytics per risolvere i problemi di qualità delle chiamate e di connessione di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="97a20-p103">Call Analytics shows detailed information about the devices, networks, and connectivity related to the specific calls and meetings for each user in a Skype for Business account. If you're a Skype for Business admin, you can use Call Analytics to troubleshoot Skype for Business call quality and connection problems.</span></span>
  
<span data-ttu-id="97a20-111">Se desideri che gli utenti non amministratori, come gli agenti di helpdesk di fornitori esterni, possano usare Call Analytics, puoi assegnare loro autorizzazioni in modo che possano usare Call Analytics ma non possano accedere al resto dell'interfaccia di amministrazione di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="97a20-111">If you want non-admins, such as helpdesk agents from an external vendor, to use Call Analytics, you can assign permissions so that they can use Call Analytics but they can't access the rest of the Skype for Business Admin center:</span></span> 
  
- <span data-ttu-id="97a20-p104">**Agenti helpdesk con autorizzazioni di Livello 1**: gli agenti vendono un sottoinsieme limitato di dati e di informazioni personali identificabili (personally identifiable information, PII) in Call Analytics. Possono risolvere i problemi delle chiamate, ma inoltreranno i problemi di riunione a un agente di Livello 2.</span><span class="sxs-lookup"><span data-stu-id="97a20-p104">**Helpdesk agents with Tier 1 permissions**: Agents see a limited set of data and personally identifiable information (PII) in Call Analytics. They can troubleshoot calls, but they will hand off problems with meetings to a Tier 2 agent.</span></span>
    
- <span data-ttu-id="97a20-p105">**Agenti helpdesk con autorizzazioni di Livello 2**: gli agenti vedono tutti i dati disponibili in Call Analytics e risolvono i problemi di chiamate e riunioni. hanno accesso completo ai registri chiamate e alle informazioni del cliente.</span><span class="sxs-lookup"><span data-stu-id="97a20-p105">**Helpdesk agents with Tier 2 permissions**: Agents see all available data in Call Analytics and troubleshoot both calls and meetings. They have full access to call logs and customer information.</span></span>
    
<span data-ttu-id="97a20-116">Per i dettagli sull'installazione di Call Analytics, vedi [Configurazione di Skype for Business Call Analytics](set-up-call-analytics.md).</span><span class="sxs-lookup"><span data-stu-id="97a20-116">For details about setting up Call Analytics, see [Set up Skype for Business Call Analytics](set-up-call-analytics.md).</span></span> <span data-ttu-id="97a20-117">Per ulteriori informazioni sul funzionamento di agenti help desk con chiamata Analitica, vedere [Utilizzo delle chiamate Analitica per risolvere i problemi di qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span><span class="sxs-lookup"><span data-stu-id="97a20-117">For more information about how Helpdesk agents can work with Call Analytics, see [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a><span data-ttu-id="97a20-118">Che cos'è Call Quality Dashboard e quando è consigliabile usarlo?</span><span class="sxs-lookup"><span data-stu-id="97a20-118">What's the Call Quality Dashboard, and when should I use it?</span></span>

<span data-ttu-id="97a20-p107">Call Analytics offre informazioni dettagliate e specifiche sulla qualità della chiamata dal punto di vista dell'utente. Perché la chiamata dell'utente Antonio Rossi aveva un audio di bassa qualità oggi pomeriggio? Usando Call Analytics, un amministratore di Skype for Business o un agente helpdesk con adeguata formazione può indagare su dispositivo, rete, connettività e altri fattori relativi alla chiamata di Antonio.</span><span class="sxs-lookup"><span data-stu-id="97a20-p107">Call Analytics gives you detailed, specific information about the call quality experienced by users. Why did user Tony Smith have a poor call this afternoon? Using Call Analytics, a Skype for Business admin or trained helpdesk agent can investigate the device, network, connectivity, and other factors related to Tony's call.</span></span>
  
<span data-ttu-id="97a20-p108">Se da una parte CA è progettato per aiutare amministratori e agenti helpdesk a risolvere i problemi di qualità per specifiche chiamate, Call Quality Dashboard (CQD) è progettato per aiutare gli amministratori di Skype for Business e i tecnici di rete a ottimizzare una rete. CQD non è focalizzato sui singoli utenti, bensì sulle informazioni in aggregato di un'intera organizzazione di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="97a20-p108">Where CA is designed to help admins and helpdesk agents troubleshoot call quality problems with specific calls, the Call Quality Dashboard (CQD) is designed to help Skype for Business admins and network engineers optimize a network. CQD shifts focus from specific users and instead looks at aggregate information for an entire Skype for Business organization.</span></span> 
  
<span data-ttu-id="97a20-p109">Forse la bassa qualità della chiamata di Antonio è dovuta a un problema di rete che colpisce anche molti altri utenti. La singola esperienza di chiamata di Antonio non è visibile in CQD, ma viene dato un quadro generale della qualità complessiva delle chiamate effettuate tramite Skype for Business. Con CQD possono emergere degli schemi generali, che permettono ai tecnici di rete di fare una valutazione informata sulla qualità delle chiamate. CQD mette a disposizione report basati sulle metriche di chiamata che danno un'idea più dettagliata della qualità generale della chiamata, dei flussi di dati server-client e client-client e della qualità vocale a livello di [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span><span class="sxs-lookup"><span data-stu-id="97a20-p109">Maybe Tony's poor call quality is due to a network issue that's also affecting many other users. Tony's individual call experience isn't visible in CQD, but the overall quality of calls made using Skype for Business is captured. With the CQD, overall patterns may become apparent, allowing network engineers to make informed assessments of call quality. CQD provides reports of call quality metrics that give you insights into overall call quality, server-client and client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span> 
  
![Screenshot of Call Quality Dashboard in the Skype for Business Admin Center. Tabs shown are Overall Call Quality, Server - Client, Client - Client, and View Quality SLA.](../images/6eaccf99-8ee8-4f99-bdf2-ba1c72471cb9.png)
  
<span data-ttu-id="97a20-130">Per maggiori dettagli, consulta [Funzionalità di Call Quality Dashboard per Skype for Business online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).</span><span class="sxs-lookup"><span data-stu-id="97a20-130">For more details, see [Features of the Call Quality Dashboard for Skype for Business Online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).</span></span>
  
<span data-ttu-id="97a20-p111">Call Analytics e CQD funzionano parallelamente l'uno all'altro e possono essere usati come programmi indipendenti oppure insieme. Per esempio, ipotizziamo che un agente di Livello 1 decida che ha bisogno d'aiuto per risolvere un problema di chiamata. L'agente di Livello 1 trasferisce la chiamata a un agente di Livello 2, che ha accesso a più informazioni in Call Analytics rispetto all'agente di Livello 1. A sua volta, l'agente di Livello 2 può segnalare un problema a un tecnico di rete. Il tecnico di rete potrà consultare CQD per verificare se un problema generale relativo al sito sta contribuendo ai problemi di chiamata.</span><span class="sxs-lookup"><span data-stu-id="97a20-p111">Call Analytics and CQD run in parallel and can be used independently or together. For example, say a Tier 1 agent determines that they need more help troubleshooting a call problem. The Tier 1 agent passes the call to a Tier 2 agent, who has access to more information in Call Analytics than the Tier 1 agent. In turn, the Tier 2 agent can alert a network engineer to an issue. The network engineer may check CQD to see if an overall site-related issue could be a contributing cause of call problems.</span></span>
  
<span data-ttu-id="97a20-136">Per ulteriori informazioni su CQD, vedere [attivazione e l'utilizzo del Dashboard di qualità delle chiamate per team di Microsoft e Skype Business online](turning-on-and-using-call-quality-dashboard.md) e [dimensioni e misure disponibile nel Dashboard di qualità delle chiamate per team di Microsoft e Skype Business online](dimensions-and-measures-available-in-call-quality-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="97a20-136">For more information about CQD, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](turning-on-and-using-call-quality-dashboard.md) and [Dimensions and measures available in Call Quality Dashboard for Microsoft Teams and Skype for Business Online](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="97a20-137">See also</span><span class="sxs-lookup"><span data-stu-id="97a20-137">Related topics</span></span>
[<span data-ttu-id="97a20-138">Configurazione di Skype for Business Call Analytics</span><span class="sxs-lookup"><span data-stu-id="97a20-138">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="97a20-139">Utilizzo delle chiamate Analitica per la risoluzione dei Skype insufficiente per le aziende qualità delle chiamate</span><span class="sxs-lookup"><span data-stu-id="97a20-139">Use Call Analytics to troubleshoot poor Skype for Business call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

  
 