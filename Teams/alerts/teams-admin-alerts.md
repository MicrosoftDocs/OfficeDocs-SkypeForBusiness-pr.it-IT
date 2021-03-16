---
title: Monitoraggio e avvisi di Microsoft Teams
author: vaibhav
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: vapati
f1.keywords: ''
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-collaboration
description: Informazioni sulle funzionalità di avvisi e notifiche di Teams disponibili nell'interfaccia di amministrazione di Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 1be3ca52d4b03cfbf82d82310148ef4c2bb7f06d
ms.sourcegitcommit: c6b630f9193d7f82f0416bd567a1de390d4b260f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819456"
---
# <a name="microsoft-teams-monitoring-and-alerting"></a><span data-ttu-id="55159-103">Monitoraggio e avvisi di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="55159-103">Microsoft Teams monitoring and alerting</span></span>

<span data-ttu-id="55159-104">Nell'interfaccia di amministrazione di Teams sono disponibili nuove funzionalità di monitoraggio e avviso per Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="55159-104">New monitoring and alerting capabilities for Microsoft Teams are available in the Teams admin center.</span></span> <span data-ttu-id="55159-105">Usare diversi set di  regole disponibili nella sezione Avvisi & notifiche nell'interfaccia di amministrazione di Teams per monitorare le funzionalità di Teams e ricevere avvisi.</span><span class="sxs-lookup"><span data-stu-id="55159-105">Use different sets of rules available under the **Notifications & alerts** section in the Teams admin center to monitor Teams capabilities and receive alerts.</span></span> <span data-ttu-id="55159-106">Ad esempio, è possibile monitorare attivamente l'integrità dei dispositivi di Teams, ad esempio telefoni IP, barre di collaborazione e altri utenti, se vengono inaspettatamente offline.</span><span class="sxs-lookup"><span data-stu-id="55159-106">For example, you can actively monitor the health of Teams devices such as IP Phones, collaboration bars, and others if they unexpectedly go offline.</span></span>  

<span data-ttu-id="55159-107">L'organizzazione può usare il monitoraggio e gli avvisi di Teams per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="55159-107">Your organization can use Teams monitoring and alerting to do the following items:</span></span>

- <span data-ttu-id="55159-108">Gestire automaticamente le funzionalità di Teams</span><span class="sxs-lookup"><span data-stu-id="55159-108">Automatically manage Teams capabilities</span></span>
- <span data-ttu-id="55159-109">Essere avvisati se mostrano qualcosa di imprevisto.</span><span class="sxs-lookup"><span data-stu-id="55159-109">Be alerted if they show something unexpected.</span></span>
- <span data-ttu-id="55159-110">Eseguire azioni correttive per ri tenere traccia degli elementi.</span><span class="sxs-lookup"><span data-stu-id="55159-110">Take corrective actions to get things back on-track.</span></span>

## <a name="how-to-manage-monitoring-and-alerting"></a><span data-ttu-id="55159-111">Come gestire il monitoraggio e gli avvisi</span><span class="sxs-lookup"><span data-stu-id="55159-111">How to manage monitoring and alerting</span></span>

 <span data-ttu-id="55159-112">Per configurare le regole di avviso, è necessario essere un amministratore globale di Microsoft 365 o un amministratore del servizio Teams.</span><span class="sxs-lookup"><span data-stu-id="55159-112">You must be a global admin in Microsoft 365 or a Teams service admin to configure alerting rules.</span></span> <span data-ttu-id="55159-113">Vedere [Usare i ruoli di amministratore di Teams per gestire Teams](../using-admin-roles.md) per altre informazioni sui ruoli di amministratore di Teams e sui report a cui ogni ruolo di amministratore può accedere.</span><span class="sxs-lookup"><span data-stu-id="55159-113">See [Use Teams administrator roles to manage Teams](../using-admin-roles.md) to learn more about Teams admin roles and which reports each admin role can access.</span></span>

1. <span data-ttu-id="55159-114">Passare all'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="55159-114">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="55159-115">Nel riquadro di spostamento sinistro selezionare **Notifiche & avvisi**.</span><span class="sxs-lookup"><span data-stu-id="55159-115">From the left navigation, select **Notifications & alerts**.</span></span>
3. <span data-ttu-id="55159-116">Scegliere la regola da configurare in **Regole**.</span><span class="sxs-lookup"><span data-stu-id="55159-116">Choose the rule you want to configure from **Rules**.</span></span>

## <a name="teams-monitoring-rules-reference"></a><span data-ttu-id="55159-117">Riferimento alle regole di monitoraggio di Teams</span><span class="sxs-lookup"><span data-stu-id="55159-117">Teams monitoring rules reference</span></span>

<span data-ttu-id="55159-118">Continuiamo ad aggiungere e migliorare l'esperienza di monitoraggio di Teams aggiungendo varie funzionalità di monitoraggio e funzionalità di configurazione.</span><span class="sxs-lookup"><span data-stu-id="55159-118">We continue adding to and improving the Teams monitoring experience by adding various monitoring capabilities and configuration functionalities.</span></span> <span data-ttu-id="55159-119">Ecco un elenco delle regole di monitoraggio di Teams attualmente disponibili nell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="55159-119">Here's a list of the Teams monitoring rules currently available in the Teams admin center.</span></span>


|<span data-ttu-id="55159-120">Regola</span><span class="sxs-lookup"><span data-stu-id="55159-120">Rule</span></span>  |<span data-ttu-id="55159-121">Funzionalità di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="55159-121">Monitoring capability</span></span>|<span data-ttu-id="55159-122">Cosa viene monitorato?</span><span class="sxs-lookup"><span data-stu-id="55159-122">What's monitored?</span></span> |
|---------|---------|---------|
|[<span data-ttu-id="55159-123">Stato di integrità del dispositivo</span><span class="sxs-lookup"><span data-stu-id="55159-123">Device health status</span></span>](device-health-status.md)  |<span data-ttu-id="55159-124">Dispositivi di Teams</span><span class="sxs-lookup"><span data-stu-id="55159-124">Teams Devices</span></span> | <span data-ttu-id="55159-125">Monitora attivamente i dispositivi di Teams se passano offline.</span><span class="sxs-lookup"><span data-stu-id="55159-125">Pro-actively monitor Teams devices if they go offline.</span></span>|
