---
title: Teams caso di studio contoso vocale
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams caso di studio vocale per multinazionali
appliesto:
- Microsoft Teams
ms.openlocfilehash: b0da56bc0da083654a0cd694bd5983f2fe4fe515
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093726"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a><span data-ttu-id="15ed9-103">Case study contoso: Teams di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="15ed9-103">Contoso case study: Teams upgrade plan</span></span>

<span data-ttu-id="15ed9-104">Nella decisione di eseguire la migrazione da Skype for Business a Teams, Contoso ha voluto offrire un'esperienza di transizione semplice per gli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="15ed9-104">In the decision to migrate from Skype for Business to Teams, Contoso wanted to provide an easy transition experience for end users.</span></span> <span data-ttu-id="15ed9-105">Invece di passare tutti alla Teams contemporaneamente, hanno deciso di configurare la connettività ibrida e di usare il metodo delle funzionalità sovrapposte per spostare gli utenti in Teams.</span><span class="sxs-lookup"><span data-stu-id="15ed9-105">Instead of switching everyone to Teams at the same time, they decided to set up hybrid connectivity, and use the overlapping capabilities method to move users to Teams.</span></span> <span data-ttu-id="15ed9-106">In questo modo gli utenti Teams e Skype for Business locali di condividere la presenza e comunicare.</span><span class="sxs-lookup"><span data-stu-id="15ed9-106">This allowed users in Teams and Skype for Business on-premises to share presence and communicate.</span></span> <span data-ttu-id="15ed9-107">Quando gli utenti entravano nel progetto pilota per Sistema telefonico, venivano spostati in Teams modalità Solo utenti.</span><span class="sxs-lookup"><span data-stu-id="15ed9-107">As users entered the pilot for Phone System, they were moved to Teams Only mode.</span></span>

<span data-ttu-id="15ed9-108">Per comprendere i concetti fondamentali sull'aggiornamento, i metodi e le modalità, Contoso leggere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="15ed9-108">To understand fundamental concepts about upgrade, methods, and modes, Contoso read the following articles:</span></span>

- [<span data-ttu-id="15ed9-109">Guida introduttiva all'aggiornamento di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="15ed9-109">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="15ed9-110">Strategie di aggiornamento per gli amministratori IT</span><span class="sxs-lookup"><span data-stu-id="15ed9-110">Upgrade strategies for IT administrators</span></span>](upgrade-to-teams-on-prem-implement.md) 
- [<span data-ttu-id="15ed9-111">Guida alla migrazione e all'interoperabilità</span><span class="sxs-lookup"><span data-stu-id="15ed9-111">Migration and interoperability guidance</span></span>](migration-interop-guidance-for-teams-with-skype.md)
 
<span data-ttu-id="15ed9-112">Contoso ha partecipato anche alla sessione Ignite 2019 Progettazione del percorso da [Skype for Business a Teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions).</span><span class="sxs-lookup"><span data-stu-id="15ed9-112">Contoso also attended the Ignite 2019 session [Designing your path from Skype for Business to Teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions).</span></span> <span data-ttu-id="15ed9-113">Contoso ha appreso di:</span><span class="sxs-lookup"><span data-stu-id="15ed9-113">Contoso learned about:</span></span>

- <span data-ttu-id="15ed9-114">Concetti fondamentali come l'interoperabilità, la federazione e il comportamento di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="15ed9-114">Fundamental concepts such as interoperability, federation, and upgrade behavior</span></span> 

- <span data-ttu-id="15ed9-115">Modalità di coesistenza e gestione basate su TeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="15ed9-115">Coexistence modes and management based on TeamsUpgradePolicy</span></span> 

- <span data-ttu-id="15ed9-116">Esperienza utente finale per:</span><span class="sxs-lookup"><span data-stu-id="15ed9-116">End user experience for:</span></span> 

  - <span data-ttu-id="15ed9-117">Chat e chiamate</span><span class="sxs-lookup"><span data-stu-id="15ed9-117">Chat and Calling</span></span> 

  - <span data-ttu-id="15ed9-118">Pianificazione delle riunioni</span><span class="sxs-lookup"><span data-stu-id="15ed9-118">Meeting scheduling</span></span> 

  - <span data-ttu-id="15ed9-119">Disponibilità delle funzionalità di collaborazione nei Teams client</span><span class="sxs-lookup"><span data-stu-id="15ed9-119">Availability of collaboration functionality in Teams clients</span></span> 

<span data-ttu-id="15ed9-120">Per pianificare e configurare la connettività ibrida, il primo passaggio per [](/SkypeForBusiness/hybrid/plan-hybrid-connectivity) spostare l'ambiente locale nel cloud, Contoso ha letto Pianificare la connettività ibrida e Configurare la connettività ibrida per comprendere come: [](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="15ed9-120">To plan and configure hybrid connectivity, the first step in moving their on-premises environment to the cloud, Contoso read [Plan hybrid connectivity](/SkypeForBusiness/hybrid/plan-hybrid-connectivity) and [Configure hybrid connectivity](/SkypeForBusiness/hybrid/configure-hybrid-connectivity) to understand how to:</span></span> 

  - <span data-ttu-id="15ed9-121">Configurare il servizio dell'ambiente locale per la federazione con Office 365.</span><span class="sxs-lookup"><span data-stu-id="15ed9-121">Configure their on-premises environment service to federate with Office 365.</span></span> 

  - <span data-ttu-id="15ed9-122">Configurare l'ambiente locale in modo da considerare attendibile Office 365 e abilitare lo spazio degli indirizzi SIP condiviso con Office 365</span><span class="sxs-lookup"><span data-stu-id="15ed9-122">Configure their on-premises environment to trust Office 365 and enable shared SIP address space with Office 365</span></span> 

  - <span data-ttu-id="15ed9-123">Abilitare lo spazio degli indirizzi SIP condiviso nel tenant Office 365.</span><span class="sxs-lookup"><span data-stu-id="15ed9-123">Enable shared SIP address space in their Office 365 tenant.</span></span>

  - <span data-ttu-id="15ed9-124">Usare la modalità Isole durante il progetto pilota tecnico.</span><span class="sxs-lookup"><span data-stu-id="15ed9-124">Use Islands mode during the technical pilot.</span></span>

  - <span data-ttu-id="15ed9-125">Passare alla modalità TeamsOnly dopo che l'utente è abilitato per Sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="15ed9-125">Switch users to TeamsOnly mode once the user is enabled for Phone System.</span></span> <span data-ttu-id="15ed9-126">La modalità TeamsOnly è obbligatoria per Piano chiamate e Instradamento diretto.</span><span class="sxs-lookup"><span data-stu-id="15ed9-126">TeamsOnly mode is required for  Calling Plan and Direct Routing.</span></span>