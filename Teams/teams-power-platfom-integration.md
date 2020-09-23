---
title: Integrazione di teams con Microsoft Power Platform
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: kvivek
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Informazioni sull'integrazione di team con gli strumenti di Microsoft Power Platform, tra cui Power BI, Power Apps, Power Automate e Power Virtual Agent.
ms.openlocfilehash: 2dfcf0dffec420e70d8f90c669bb64d2e9236c3e
ms.sourcegitcommit: 3db7c450d3afbc1049e1016d51016442e5764634
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203994"
---
# <a name="teams-integration-with-microsoft-power-platform"></a><span data-ttu-id="fa1c9-103">Integrazione di teams con Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="fa1c9-103">Teams integration with Microsoft Power Platform</span></span>

<span data-ttu-id="fa1c9-104">Microsoft Power Platform consente agli utenti di velocizzare lo sviluppo con strumenti di basso codice per analizzare i dati con **Power bi**, creare app personalizzate con **Power Apps**, automatizzare i processi con **Power Automate**e creare bot intelligenti usando **agenti virtuali di Power** più rapidamente che mai.</span><span class="sxs-lookup"><span data-stu-id="fa1c9-104">Microsoft Power Platform helps users accelerate their development with low-code tools to analyze data using **Power BI**, build custom apps using **Power Apps**, automate processes using **Power Automate**, and create intelligent bots using **Power Virtual Agents** more quickly than ever.</span></span> <span data-ttu-id="fa1c9-105">Con il cambio di lavoro remoto e ibrido, Microsoft Teams ha consentito agli utenti di tutto il mondo di continuare a creare, collaborare e comunicare.</span><span class="sxs-lookup"><span data-stu-id="fa1c9-105">With the shift to remote and hybrid work, Microsoft Teams has enabled people around the world to continue to create, collaborate, and communicate.</span></span> <span data-ttu-id="fa1c9-106">Con più di 75 milioni utenti attivi giornalieri, teams è il modo in cui le persone stanno ottenendo il lavoro svolto.</span><span class="sxs-lookup"><span data-stu-id="fa1c9-106">With more than 75 million daily active users, Teams is how people are getting work done.</span></span>

:::image type="content" source="media/teams-power-platform-integration.png" alt-text="Team di riepilogo immagini e Microsoft Power Platform":::

<span data-ttu-id="fa1c9-108">Microsoft Power Platform offre numerose funzionalità di integrazione con i team in cui è possibile incorporare i report di **Power bi** nell'area di lavoro teams, incorporare le app create usando **Power Apps** come scheda o un'app personale, attivare un flusso di **automatizzazione di Power** da qualsiasi messaggio o usare schede adattive e aggiungere il bot creato con **Power Virtual Agents** ai team per gli altri membri dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fa1c9-108">Microsoft Power Platform provides many integration capabilities with Teams where you can embed **Power BI** reports in the Teams workspace, embed apps created using **Power Apps** as a tab or personal app, trigger a **Power Automate** flow from any message or use adaptive cards, and add your bot created using **Power Virtual Agents** to Teams for other members of your organization to interact with.</span></span>

<span data-ttu-id="fa1c9-109">A partire da settembre 2020, l'integrazione con Microsoft Power Platform è migliorata per consentire agli utenti di eseguire le operazioni seguenti *senza mai uscire dall'interfaccia teams*:</span><span class="sxs-lookup"><span data-stu-id="fa1c9-109">Starting September 2020, integration with Microsoft Power Platform has improved to let users do the following *without ever leaving the Teams interface*:</span></span>

- <span data-ttu-id="fa1c9-110">Creare e condividere dashboard, report e app usando **Power bi** per prendere decisioni basate sui dati.</span><span class="sxs-lookup"><span data-stu-id="fa1c9-110">Create and share dashboards, reports, and apps using **Power BI** to make data-driven decisions.</span></span>
- <span data-ttu-id="fa1c9-111">Creare e condividere app di basso codice e di uso personale con un **Power Apps** studio integrato connettendosi ai dati aziendali archiviati nella nuova piattaforma dati sottostante (Project Oakdale), Microsoft 365 o in altre origini dati tramite connettori.</span><span class="sxs-lookup"><span data-stu-id="fa1c9-111">Create and share low-code, purpose-built apps using an integrated **Power Apps** studio by connecting to your business data stored either in the new underlying data platform (Project Oakdale), Microsoft 365, or in other data sources through connectors.</span></span>
- <span data-ttu-id="fa1c9-112">Creare flussi di lavoro automatizzati tra le app e i servizi per sincronizzare i file, ricevere notifiche, raccogliere dati e altro tramite **Power automatizzate**.</span><span class="sxs-lookup"><span data-stu-id="fa1c9-112">Create automated workflows between your apps and services to synchronize files, get notifications, collect data, and more using **Power Automate**.</span></span>
- <span data-ttu-id="fa1c9-113">Costruisci bot usando un'interfaccia grafica guidata senza codice con **Power Virtual Agents** per creare facilmente gli assistenti digitali in teams e renderli disponibili ai tuoi colleghi per chattare.</span><span class="sxs-lookup"><span data-stu-id="fa1c9-113">Build bots using a guided, no-code graphical interface using **Power Virtual Agents** to easily create digital assistants within Teams and make them available to your colleagues to chat with.</span></span>

<span data-ttu-id="fa1c9-114">Le nuove funzionalità per la creazione di app, bot e flussi di lavoro sono supportate dalla nuova piattaforma dati predefinita per Teams, [Project Oakdale](https://go.microsoft.com/fwlink/?linkid=2143541), che fornisce l'archiviazione dei dati relazionali, i tipi di dati RTF, la governance del grado aziendale e la distribuzione di soluzioni con un solo clic.</span><span class="sxs-lookup"><span data-stu-id="fa1c9-114">The new capabilities to create apps, bots, and workflows are backed by the new built-in, low-code data platform for Teams, [Project Oakdale](https://go.microsoft.com/fwlink/?linkid=2143541), which provides relational data storage, rich data types, enterprise grade governance, and one-click solution deployment.</span></span> <span data-ttu-id="fa1c9-115">Project Oakdale è basato sul [servizio dati comune](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span><span class="sxs-lookup"><span data-stu-id="fa1c9-115">Project Oakdale is built on top of [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span></span> <span data-ttu-id="fa1c9-116">Con Project Oakdale, gli utenti di teams possono trovare e installare soluzioni personalizzate e pronte per l'uso dall'app store teams che mettono in evidenza scenari comuni tra i vari settori.</span><span class="sxs-lookup"><span data-stu-id="fa1c9-116">With Project Oakdale, Teams users can find and install custom, ready-to-use solutions from the Teams app store that showcase common scenarios across industries.</span></span> <span data-ttu-id="fa1c9-117">È possibile personalizzare ed estendere queste soluzioni personalizzate per adattarsi ai requisiti e alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fa1c9-117">You can customize and extend these custom solutions to adapt to your organization's branding and requirements.</span></span>

## <a name="licensing"></a><span data-ttu-id="fa1c9-118">Licenze</span><span class="sxs-lookup"><span data-stu-id="fa1c9-118">Licensing</span></span>

<span data-ttu-id="fa1c9-119">Le nuove funzionalità sono disponibili per gli abbonamenti seleziona Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fa1c9-119">The new capabilities are available to the select Microsoft 365 subscriptions.</span></span>

- <span data-ttu-id="fa1c9-120">Per altre informazioni sui requisiti di licenza per Power Apps, Power automatizzate, Power Virtual Agent e Project Oakdale, vedere [licenze](https://go.microsoft.com/fwlink/?linkid=2143647).</span><span class="sxs-lookup"><span data-stu-id="fa1c9-120">For more information about licensing requirements for Power Apps, Power Automate, Power Virtual Agents, and Project Oakdale, see [Licensing](https://go.microsoft.com/fwlink/?linkid=2143647).</span></span>
- <span data-ttu-id="fa1c9-121">Per altre informazioni sui requisiti di licenza per Power BI, vedere [requisiti](https://go.microsoft.com/fwlink/?linkid=2143490).</span><span class="sxs-lookup"><span data-stu-id="fa1c9-121">For more information about licensing requirements for Power BI, see [Requirements](https://go.microsoft.com/fwlink/?linkid=2143490).</span></span>
 
## <a name="how-do-i-get-started"></a><span data-ttu-id="fa1c9-122">Come iniziare?</span><span class="sxs-lookup"><span data-stu-id="fa1c9-122">How do I get started?</span></span>

- [<span data-ttu-id="fa1c9-123">Power BI e teams</span><span class="sxs-lookup"><span data-stu-id="fa1c9-123">Power BI and Teams</span></span>](https://aka.ms/pbi-teams-docs)
- [<span data-ttu-id="fa1c9-124">Power Apps and Teams</span><span class="sxs-lookup"><span data-stu-id="fa1c9-124">Power Apps and Teams</span></span>](https://aka.ms/pa-teams-docs)
- [<span data-ttu-id="fa1c9-125">Automatizzazione e team di Power</span><span class="sxs-lookup"><span data-stu-id="fa1c9-125">Power Automate and Teams</span></span>](https://aka.ms/pauto-teams-docs)
- [<span data-ttu-id="fa1c9-126">Agenti e team virtuali di Power</span><span class="sxs-lookup"><span data-stu-id="fa1c9-126">Power Virtual Agents and Teams</span></span>](https://aka.ms/pva-teams-docs)
