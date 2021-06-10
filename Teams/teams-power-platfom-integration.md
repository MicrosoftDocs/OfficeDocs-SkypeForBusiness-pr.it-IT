---
title: Teams'integrazione con Microsoft Power Platform
author: cichur
ms.author: v-cichur
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
description: Informazioni sull'Teams con gli strumenti della piattaforma Microsoft Power, tra cui Power BI, app Power, Automazione di Power e Power Virtual Agents.
ms.openlocfilehash: c6442cd654dd8da6e26de048d50b7c80ef95cf26
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111042"
---
# <a name="teams-integration-with-microsoft-power-platform"></a><span data-ttu-id="0b95e-103">Teams'integrazione con Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="0b95e-103">Teams integration with Microsoft Power Platform</span></span>

<span data-ttu-id="0b95e-104">Microsoft Power Platform consente agli utenti di accelerare lo sviluppo con strumenti a basso codice per analizzare i dati usando **Power BI,** creare app personalizzate con **Power Apps,** automatizzare i processi con **Power Automate e** creare bot intelligenti **usando Power Virtual Agents più** rapidamente che mai.</span><span class="sxs-lookup"><span data-stu-id="0b95e-104">Microsoft Power Platform helps users accelerate their development with low-code tools to analyze data using **Power BI**, build custom apps using **Power Apps**, automate processes using **Power Automate**, and create intelligent bots using **Power Virtual Agents** more quickly than ever.</span></span> <span data-ttu-id="0b95e-105">Con il passaggio al lavoro remoto e ibrido, Microsoft Teams ha consentito alle persone di tutto il mondo di continuare a creare, collaborare e comunicare.</span><span class="sxs-lookup"><span data-stu-id="0b95e-105">With the shift to remote and hybrid work, Microsoft Teams has enabled people around the world to continue to create, collaborate, and communicate.</span></span> <span data-ttu-id="0b95e-106">Con più di 75 milioni di utenti attivi al giorno, Teams è il modo in cui le persone lavorano.</span><span class="sxs-lookup"><span data-stu-id="0b95e-106">With more than 75 million daily active users, Teams is how people are getting work done.</span></span>

:::image type="content" source="media/teams-power-platform-integration.png" alt-text="Immagine che riepiloga Teams e Microsoft Power Platform":::

<span data-ttu-id="0b95e-108">Microsoft Power Platform offre molte funzionalità di integrazione  con Teams in cui è possibile incorporare report Power BI nell'area di lavoro di Teams, incorporare app create usando **Power Apps come** scheda o app personale, attivare un flusso **di Power Automate** da qualsiasi messaggio o usare schede adattive e aggiungere il bot creato con **Power Virtual Agents** a Teams con cui gli altri membri dell'organizzazione possono interagire.</span><span class="sxs-lookup"><span data-stu-id="0b95e-108">Microsoft Power Platform provides many integration capabilities with Teams where you can embed **Power BI** reports in the Teams workspace, embed apps created using **Power Apps** as a tab or personal app, trigger a **Power Automate** flow from any message or use adaptive cards, and add your bot created using **Power Virtual Agents** to Teams for other members of your organization to interact with.</span></span>

<span data-ttu-id="0b95e-109">A partire da settembre 2020, l'integrazione con Microsoft Power Platform è stata migliorata per consentire agli utenti di eseguire le operazioni seguenti senza uscire *dall'interfaccia Teams:*</span><span class="sxs-lookup"><span data-stu-id="0b95e-109">Starting September 2020, integration with Microsoft Power Platform has improved to let users do the following *without ever leaving the Teams interface*:</span></span>

- <span data-ttu-id="0b95e-110">Creare e condividere dashboard, report e app usando **Power BI** per prendere decisioni in base ai dati.</span><span class="sxs-lookup"><span data-stu-id="0b95e-110">Create and share dashboards, reports, and apps using **Power BI** to make data-driven decisions.</span></span>
- <span data-ttu-id="0b95e-111">Creare e condividere app a basso codice e appositamente create usando uno studio Power Apps integrato connettendosi **ai** dati aziendali archiviati nella nuova piattaforma dati sottostante (Microsoft Dataverse per Teams), Microsoft 365 o in altre origini dati tramite connettori.</span><span class="sxs-lookup"><span data-stu-id="0b95e-111">Create and share low-code, purpose-built apps using an integrated **Power Apps** studio by connecting to your business data stored either in the new underlying data platform (Microsoft Dataverse for Teams), Microsoft 365, or in other data sources through connectors.</span></span>
- <span data-ttu-id="0b95e-112">Creare flussi di lavoro automatizzati tra le app e i servizi per sincronizzare i file, ricevere notifiche, raccogliere dati e altro ancora **usando Power Automate**.</span><span class="sxs-lookup"><span data-stu-id="0b95e-112">Create automated workflows between your apps and services to synchronize files, get notifications, collect data, and more using **Power Automate**.</span></span>
- <span data-ttu-id="0b95e-113">Crea bot usando un'interfaccia grafica guidata senza codice usando **Power Virtual Agents** per creare facilmente assistenti digitali all'interno di Teams e renderli disponibili ai colleghi con cui chattare.</span><span class="sxs-lookup"><span data-stu-id="0b95e-113">Build bots using a guided, no-code graphical interface using **Power Virtual Agents** to easily create digital assistants within Teams and make them available to your colleagues to chat with.</span></span>

<span data-ttu-id="0b95e-114">Le nuove funzionalità per creare app, bot e flussi di lavoro sono supportate dalla nuova piattaforma di dati predefinita e a basso codice per Teams, [Dataverse per Teams](/powerapps/teams/overview-data-platform), che fornisce l'archiviazione relazionale dei dati, i tipi di dati complessi, la governance aziendale e la distribuzione di soluzioni con un solo clic.</span><span class="sxs-lookup"><span data-stu-id="0b95e-114">The new capabilities to create apps, bots, and workflows are backed by the new built-in, low-code data platform for Teams, [Dataverse for Teams](/powerapps/teams/overview-data-platform), which provides relational data storage, rich data types, enterprise grade governance, and one-click solution deployment.</span></span> <span data-ttu-id="0b95e-115">Dataverse per Teams è basato su [Microsoft Dataverse](/powerapps/maker/common-data-service/data-platform-intro).</span><span class="sxs-lookup"><span data-stu-id="0b95e-115">Dataverse for Teams is built on top of [Microsoft Dataverse](/powerapps/maker/common-data-service/data-platform-intro).</span></span> <span data-ttu-id="0b95e-116">Con Dataverse per Teams, Teams utenti possono trovare e installare soluzioni personalizzate e pronte per l'uso dall'app store di Teams che illustrano scenari comuni in tutti i settori.</span><span class="sxs-lookup"><span data-stu-id="0b95e-116">With Dataverse for Teams, Teams users can find and install custom, ready-to-use solutions from the Teams app store that showcase common scenarios across industries.</span></span> <span data-ttu-id="0b95e-117">È possibile personalizzare ed estendere queste soluzioni personalizzate per adattarsi ai requisiti e al marchio dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0b95e-117">You can customize and extend these custom solutions to adapt to your organization's branding and requirements.</span></span>

## <a name="licensing"></a><span data-ttu-id="0b95e-118">Licenze</span><span class="sxs-lookup"><span data-stu-id="0b95e-118">Licensing</span></span>

<span data-ttu-id="0b95e-119">Le nuove funzionalità sono disponibili per gli abbonamenti Microsoft 365 selezionati.</span><span class="sxs-lookup"><span data-stu-id="0b95e-119">The new capabilities are available to the select Microsoft 365 subscriptions.</span></span>

- <span data-ttu-id="0b95e-120">Per altre informazioni sui requisiti di licenza per Power Apps, Power Automate, Power Virtual Agents e Dataverse per Teams, vedere [Licenze](/power-platform/admin/about-teams-environment).</span><span class="sxs-lookup"><span data-stu-id="0b95e-120">For more information about licensing requirements for Power Apps, Power Automate, Power Virtual Agents, and Dataverse for Teams, see [Licensing](/power-platform/admin/about-teams-environment).</span></span>
- <span data-ttu-id="0b95e-121">Per altre informazioni sui requisiti di licenza per Power BI, vedere [Requisiti](/power-bi/collaborate-share/service-collaborate-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="0b95e-121">For more information about licensing requirements for Power BI, see [Requirements](/power-bi/collaborate-share/service-collaborate-microsoft-teams).</span></span>
 
## <a name="how-do-i-get-started"></a><span data-ttu-id="0b95e-122">Come si inizia?</span><span class="sxs-lookup"><span data-stu-id="0b95e-122">How do I get started?</span></span>

- [<span data-ttu-id="0b95e-123">Power BI e Teams</span><span class="sxs-lookup"><span data-stu-id="0b95e-123">Power BI and Teams</span></span>](/power-bi/collaborate-share/service-collaborate-microsoft-teams)
- [<span data-ttu-id="0b95e-124">Power Apps e Teams</span><span class="sxs-lookup"><span data-stu-id="0b95e-124">Power Apps and Teams</span></span>](/powerapps/teams/overview)
- [<span data-ttu-id="0b95e-125">Power Automate e Teams</span><span class="sxs-lookup"><span data-stu-id="0b95e-125">Power Automate and Teams</span></span>](/power-automate/teams/overview)
- [<span data-ttu-id="0b95e-126">Power Virtual Agents e Teams</span><span class="sxs-lookup"><span data-stu-id="0b95e-126">Power Virtual Agents and Teams</span></span>](/power-virtual-agents/teams/fundamentals-what-is-power-virtual-agents-teams)