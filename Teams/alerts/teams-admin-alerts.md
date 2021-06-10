---
title: Microsoft Teams Monitoraggio e avvisi
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
description: Informazioni sulle funzionalità Teams avvisi e notifiche disponibili nell'Microsoft Teams di amministrazione.
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: c99cc9af08fb1353e0c94e6f8bf156df04327d49
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684606"
---
# <a name="microsoft-teams-monitoring-and-alerting"></a><span data-ttu-id="64494-103">Microsoft Teams e avvisi</span><span class="sxs-lookup"><span data-stu-id="64494-103">Microsoft Teams monitoring and alerting</span></span>

<span data-ttu-id="64494-104">Nell'interfaccia di amministrazione Teams sono disponibili nuove funzionalità di monitoraggio e avviso per i Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="64494-104">New monitoring and alerting capabilities for Microsoft Teams are available in the Teams admin center.</span></span> <span data-ttu-id="64494-105">Usare diversi set di  regole disponibili nella sezione Avvisi & notifiche nell'interfaccia di amministrazione di Teams per monitorare le funzionalità Teams e ricevere avvisi.</span><span class="sxs-lookup"><span data-stu-id="64494-105">Use different sets of rules available under the **Notifications & alerts** section in the Teams admin center to monitor Teams capabilities and receive alerts.</span></span> <span data-ttu-id="64494-106">Ad esempio, è possibile monitorare attivamente l'integrità dei dispositivi Teams, ad esempio telefoni IP, barre di collaborazione e altri dispositivi, se in modo imprevisto passano offline.</span><span class="sxs-lookup"><span data-stu-id="64494-106">For example, you can actively monitor the health of Teams devices such as IP Phones, collaboration bars, and others if they unexpectedly go offline.</span></span>  

<span data-ttu-id="64494-107">L'organizzazione può usare il Teams e gli avvisi per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="64494-107">Your organization can use Teams monitoring and alerting to do the following items:</span></span>

- <span data-ttu-id="64494-108">Gestire automaticamente Teams funzionalità</span><span class="sxs-lookup"><span data-stu-id="64494-108">Automatically manage Teams capabilities</span></span>
- <span data-ttu-id="64494-109">Essere avvisati se mostrano qualcosa di imprevisto.</span><span class="sxs-lookup"><span data-stu-id="64494-109">Be alerted if they show something unexpected.</span></span>
- <span data-ttu-id="64494-110">Eseguire azioni correttive per ri tenere traccia degli elementi.</span><span class="sxs-lookup"><span data-stu-id="64494-110">Take corrective actions to get things back on-track.</span></span>

## <a name="how-to-manage-monitoring-and-alerting"></a><span data-ttu-id="64494-111">Come gestire il monitoraggio e gli avvisi</span><span class="sxs-lookup"><span data-stu-id="64494-111">How to manage monitoring and alerting</span></span>

 <span data-ttu-id="64494-112">Per configurare le regole di avviso, è necessario essere un amministratore globale di Microsoft 365 o un amministratore Teams servizio.</span><span class="sxs-lookup"><span data-stu-id="64494-112">You must be a global admin in Microsoft 365 or a Teams service admin to configure alerting rules.</span></span> <span data-ttu-id="64494-113">Vedere [Usare i Teams di](../using-admin-roles.md) amministratore per gestire Teams per altre informazioni sui ruoli di Teams e sui report a cui ogni ruolo di amministratore può accedere.</span><span class="sxs-lookup"><span data-stu-id="64494-113">See [Use Teams administrator roles to manage Teams](../using-admin-roles.md) to learn more about Teams admin roles and which reports each admin role can access.</span></span>

1. <span data-ttu-id="64494-114">Passare all'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="64494-114">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="64494-115">Nel riquadro di spostamento sinistro selezionare **Notifiche & avvisi**.</span><span class="sxs-lookup"><span data-stu-id="64494-115">From the left navigation, select **Notifications & alerts**.</span></span>
3. <span data-ttu-id="64494-116">Scegliere la regola da configurare in **Regole**.</span><span class="sxs-lookup"><span data-stu-id="64494-116">Choose the rule you want to configure from **Rules**.</span></span>

## <a name="teams-monitoring-rules-reference"></a><span data-ttu-id="64494-117">Teams regole di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="64494-117">Teams monitoring rules reference</span></span>

<span data-ttu-id="64494-118">Continuiamo ad aggiungere e migliorare l'esperienza Teams di monitoraggio aggiungendo varie funzionalità di monitoraggio e funzionalità di configurazione.</span><span class="sxs-lookup"><span data-stu-id="64494-118">We continue adding to and improving the Teams monitoring experience by adding various monitoring capabilities and configuration functionalities.</span></span> <span data-ttu-id="64494-119">Ecco un elenco delle regole di Teams di monitoraggio dei messaggi attualmente disponibili nell'interfaccia Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="64494-119">Here's a list of the Teams monitoring rules currently available in the Teams admin center.</span></span>


|<span data-ttu-id="64494-120">Regola</span><span class="sxs-lookup"><span data-stu-id="64494-120">Rule</span></span>  |<span data-ttu-id="64494-121">Funzionalità di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="64494-121">Monitoring capability</span></span>|<span data-ttu-id="64494-122">Cosa viene monitorato?</span><span class="sxs-lookup"><span data-stu-id="64494-122">What's monitored?</span></span> |
|---------|---------|---------|
|[<span data-ttu-id="64494-123">Stato di integrità del dispositivo</span><span class="sxs-lookup"><span data-stu-id="64494-123">Device health status</span></span>](device-health-status.md)  |<span data-ttu-id="64494-124">Teams Dispositivi</span><span class="sxs-lookup"><span data-stu-id="64494-124">Teams Devices</span></span> | <span data-ttu-id="64494-125">Pro monitorare attivamente i Teams dispositivi se passano offline.</span><span class="sxs-lookup"><span data-stu-id="64494-125">Pro-actively monitor Teams devices if they go offline.</span></span>|