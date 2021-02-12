---
title: Integrazione di Teams con Microsoft Power Platform
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
description: Informazioni sull'integrazione di Teams con gli strumenti di Microsoft Power Platform, tra cui Power BI, le app Power, Power Automate e gli agenti virtuali di Power.
ms.openlocfilehash: 0fb05596fb5fa87ab4e209325cc35b7a3eae56d9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804566"
---
# <a name="teams-integration-with-microsoft-power-platform"></a><span data-ttu-id="24327-103">Integrazione di Teams con Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="24327-103">Teams integration with Microsoft Power Platform</span></span>

<span data-ttu-id="24327-104">Microsoft Power Platform consente agli utenti di accelerare il loro sviluppo con strumenti a basso codice per analizzare i dati usando **Power BI,** creare app personalizzate con **Power Apps,** automatizzare i processi con **Power Automate** e creare bot intelligenti con gli agenti virtuali di **Power** più rapidamente che mai.</span><span class="sxs-lookup"><span data-stu-id="24327-104">Microsoft Power Platform helps users accelerate their development with low-code tools to analyze data using **Power BI**, build custom apps using **Power Apps**, automate processes using **Power Automate**, and create intelligent bots using **Power Virtual Agents** more quickly than ever.</span></span> <span data-ttu-id="24327-105">Con il passaggio al lavoro remoto e ibrido, Microsoft Teams ha permesso a tutto il mondo di continuare a creare, collaborare e comunicare.</span><span class="sxs-lookup"><span data-stu-id="24327-105">With the shift to remote and hybrid work, Microsoft Teams has enabled people around the world to continue to create, collaborate, and communicate.</span></span> <span data-ttu-id="24327-106">Con più di 75 milioni di utenti attivi giornalieri, Teams è il modo in cui le persone lavorano.</span><span class="sxs-lookup"><span data-stu-id="24327-106">With more than 75 million daily active users, Teams is how people are getting work done.</span></span>

:::image type="content" source="media/teams-power-platform-integration.png" alt-text="Immagine di riepilogo di Teams e Microsoft Power Platform":::

<span data-ttu-id="24327-108">Microsoft Power Platform offre molte funzionalità di integrazione con Teams, in cui è possibile incorporare i report di **Power BI** nell'area di lavoro di Teams, incorporare app create utilizzando **Power Apps** come scheda o app personale, avviare un flusso **Power Automate** da qualsiasi messaggio o usare schede adattive e aggiungere il bot creato con gli agenti virtuali di **Power** a Teams con cui altri membri dell'organizzazione possono interagire.</span><span class="sxs-lookup"><span data-stu-id="24327-108">Microsoft Power Platform provides many integration capabilities with Teams where you can embed **Power BI** reports in the Teams workspace, embed apps created using **Power Apps** as a tab or personal app, trigger a **Power Automate** flow from any message or use adaptive cards, and add your bot created using **Power Virtual Agents** to Teams for other members of your organization to interact with.</span></span>

<span data-ttu-id="24327-109">A partire da settembre 2020, l'integrazione con la piattaforma Microsoft Power è stata migliorata per consentire agli utenti di fare quanto segue senza *uscire dall'interfaccia di Teams:*</span><span class="sxs-lookup"><span data-stu-id="24327-109">Starting September 2020, integration with Microsoft Power Platform has improved to let users do the following *without ever leaving the Teams interface*:</span></span>

- <span data-ttu-id="24327-110">Creare e condividere dashboard, report e app usando **Power BI** per prendere decisioni basata sui dati.</span><span class="sxs-lookup"><span data-stu-id="24327-110">Create and share dashboards, reports, and apps using **Power BI** to make data-driven decisions.</span></span>
- <span data-ttu-id="24327-111">Crea e condividi app a basso codice e appositamente create utilizzando uno studio **Power Apps** integrato connettendoti ai dati aziendali archiviati nella nuova piattaforma dati sottostante (Microsoft Dataverse per Teams), Microsoft 365 o in altre origini dati tramite connettori.</span><span class="sxs-lookup"><span data-stu-id="24327-111">Create and share low-code, purpose-built apps using an integrated **Power Apps** studio by connecting to your business data stored either in the new underlying data platform (Microsoft Dataverse for Teams), Microsoft 365, or in other data sources through connectors.</span></span>
- <span data-ttu-id="24327-112">Creare flussi di lavoro automatizzati tra app e servizi per sincronizzare i file, ricevere notifiche, raccogliere dati e altro ancora **con Power Automate.**</span><span class="sxs-lookup"><span data-stu-id="24327-112">Create automated workflows between your apps and services to synchronize files, get notifications, collect data, and more using **Power Automate**.</span></span>
- <span data-ttu-id="24327-113">Crea bot utilizzando un'interfaccia grafica guidata e senza codice utilizzando gli agenti virtuali di **Power** per creare facilmente assistenti digitali all'interno di Teams e renderli disponibili ai tuoi colleghi con cui chattare.</span><span class="sxs-lookup"><span data-stu-id="24327-113">Build bots using a guided, no-code graphical interface using **Power Virtual Agents** to easily create digital assistants within Teams and make them available to your colleagues to chat with.</span></span>

<span data-ttu-id="24327-114">Le nuove funzionalità per creare app, bot e flussi di lavoro sono supportate dalla nuova piattaforma di dati a basso codice integrata per Teams, [Dataverse per Teams,](https://go.microsoft.com/fwlink/?linkid=2143541)che offre archiviazione dei dati relazionali, tipi di dati complessi, governance di livello enterprise e distribuzione delle soluzioni con un solo clic.</span><span class="sxs-lookup"><span data-stu-id="24327-114">The new capabilities to create apps, bots, and workflows are backed by the new built-in, low-code data platform for Teams, [Dataverse for Teams](https://go.microsoft.com/fwlink/?linkid=2143541), which provides relational data storage, rich data types, enterprise grade governance, and one-click solution deployment.</span></span> <span data-ttu-id="24327-115">Dataverse per Teams si basa su [Microsoft Dataverse.](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="24327-115">Dataverse for Teams is built on top of [Microsoft Dataverse](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span></span> <span data-ttu-id="24327-116">Con Dataverse per Teams, gli utenti di Teams possono trovare e installare soluzioni personalizzate e pronte per l'uso dall'app store di Teams che mostrano scenari comuni nei vari settori.</span><span class="sxs-lookup"><span data-stu-id="24327-116">With Dataverse for Teams, Teams users can find and install custom, ready-to-use solutions from the Teams app store that showcase common scenarios across industries.</span></span> <span data-ttu-id="24327-117">È possibile personalizzare ed estendere queste soluzioni personalizzate in base al marchio e ai requisiti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="24327-117">You can customize and extend these custom solutions to adapt to your organization's branding and requirements.</span></span>

## <a name="licensing"></a><span data-ttu-id="24327-118">Licenze</span><span class="sxs-lookup"><span data-stu-id="24327-118">Licensing</span></span>

<span data-ttu-id="24327-119">Le nuove funzionalità sono disponibili per gli abbonamenti selezionati a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="24327-119">The new capabilities are available to the select Microsoft 365 subscriptions.</span></span>

- <span data-ttu-id="24327-120">Per altre informazioni sui requisiti di licenza per Power Apps, Power Automate, Power Virtual Agents e Dataverse per Teams, vedere [Licenze.](https://go.microsoft.com/fwlink/?linkid=2143647)</span><span class="sxs-lookup"><span data-stu-id="24327-120">For more information about licensing requirements for Power Apps, Power Automate, Power Virtual Agents, and Dataverse for Teams, see [Licensing](https://go.microsoft.com/fwlink/?linkid=2143647).</span></span>
- <span data-ttu-id="24327-121">Per altre informazioni sui requisiti di licenza per Power BI, vedere [Requisiti.](https://go.microsoft.com/fwlink/?linkid=2143490)</span><span class="sxs-lookup"><span data-stu-id="24327-121">For more information about licensing requirements for Power BI, see [Requirements](https://go.microsoft.com/fwlink/?linkid=2143490).</span></span>
 
## <a name="how-do-i-get-started"></a><span data-ttu-id="24327-122">Come si inizia?</span><span class="sxs-lookup"><span data-stu-id="24327-122">How do I get started?</span></span>

- [<span data-ttu-id="24327-123">Power BI e Teams</span><span class="sxs-lookup"><span data-stu-id="24327-123">Power BI and Teams</span></span>](https://aka.ms/pbi-teams-docs)
- [<span data-ttu-id="24327-124">Power Apps e Teams</span><span class="sxs-lookup"><span data-stu-id="24327-124">Power Apps and Teams</span></span>](https://aka.ms/pa-teams-docs)
- [<span data-ttu-id="24327-125">Power Automate e Teams</span><span class="sxs-lookup"><span data-stu-id="24327-125">Power Automate and Teams</span></span>](https://aka.ms/pauto-teams-docs)
- [<span data-ttu-id="24327-126">Power Virtual Agents and Teams</span><span class="sxs-lookup"><span data-stu-id="24327-126">Power Virtual Agents and Teams</span></span>](https://aka.ms/pva-teams-docs)
