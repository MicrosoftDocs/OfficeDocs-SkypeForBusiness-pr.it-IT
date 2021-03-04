---
title: Case study su Teams per Contoso
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
description: Case study vocale di Teams per multi-national corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: 93f6d0877537a740dc867b44c3c4deb9bebb8441
ms.sourcegitcommit: 6f7b91f573e2a034f8c5474be2c5cb2971f4b5ab
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421291"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a><span data-ttu-id="f0132-103">Case study contoso: Piano di aggiornamento di Teams</span><span class="sxs-lookup"><span data-stu-id="f0132-103">Contoso case study: Teams upgrade plan</span></span>

<span data-ttu-id="f0132-104">Nella decisione di eseguire la migrazione da Skype for Business a Teams, Contoso ha voluto offrire un'esperienza di transizione facile per gli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="f0132-104">In the decision to migrate from Skype for Business to Teams, Contoso wanted to provide an easy transition experience for end users.</span></span> <span data-ttu-id="f0132-105">Invece di spostare tutti gli utenti in Teams contemporaneamente, hanno deciso di configurare la connettività ibrida e usare il metodo delle funzionalità sovrapposte per spostare gli utenti in Teams.</span><span class="sxs-lookup"><span data-stu-id="f0132-105">Instead of switching everyone to Teams at the same time, they decided to set up hybrid connectivity, and use the overlapping capabilities method to move users to Teams.</span></span> <span data-ttu-id="f0132-106">Ciò consentiva agli utenti di Teams e Skype for Business locale di condividere la presenza e comunicare.</span><span class="sxs-lookup"><span data-stu-id="f0132-106">This allowed users in Teams and Skype for Business on-premises to share presence and communicate.</span></span> <span data-ttu-id="f0132-107">Quando gli utenti entravano nel progetto pilota per Sistema telefonico, venivano spostati in modalità Solo Teams.</span><span class="sxs-lookup"><span data-stu-id="f0132-107">As users entered the pilot for Phone System, they were moved to Teams Only mode.</span></span>

<span data-ttu-id="f0132-108">Per comprendere i concetti fondamentali sull'aggiornamento, i metodi e le modalità, Contoso leggere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="f0132-108">To understand fundamental concepts about upgrade, methods, and modes, Contoso read the following articles:</span></span>

- [<span data-ttu-id="f0132-109">Guida introduttiva all'aggiornamento di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f0132-109">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="f0132-110">Strategie di aggiornamento per gli amministratori IT</span><span class="sxs-lookup"><span data-stu-id="f0132-110">Upgrade strategies for IT administrators</span></span>](upgrade-to-teams-on-prem-implement.md) 
- [<span data-ttu-id="f0132-111">Indicazioni per la migrazione e l'interoperabilità</span><span class="sxs-lookup"><span data-stu-id="f0132-111">Migration and interoperability guidance</span></span>](migration-interop-guidance-for-teams-with-skype.md)
 
<span data-ttu-id="f0132-112">Contoso ha partecipato anche alla sessione Ignite 2019 [Designing your path from Skype for Business to Teams.](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions)</span><span class="sxs-lookup"><span data-stu-id="f0132-112">Contoso also attended the Ignite 2019 session [Designing your path from Skype for Business to Teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions).</span></span> <span data-ttu-id="f0132-113">Contoso ha imparato a:</span><span class="sxs-lookup"><span data-stu-id="f0132-113">Contoso learned about:</span></span>

- <span data-ttu-id="f0132-114">Concetti fondamentali come l'interoperabilità, la federazione e il comportamento di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="f0132-114">Fundamental concepts such as interoperability, federation, and upgrade behavior</span></span> 

- <span data-ttu-id="f0132-115">Modalità di coesistenza e gestione basate su TeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="f0132-115">Coexistence modes and management based on TeamsUpgradePolicy</span></span> 

- <span data-ttu-id="f0132-116">Esperienza utente finale per:</span><span class="sxs-lookup"><span data-stu-id="f0132-116">End user experience for:</span></span> 

  - <span data-ttu-id="f0132-117">Chat e chiamate</span><span class="sxs-lookup"><span data-stu-id="f0132-117">Chat and Calling</span></span> 

  - <span data-ttu-id="f0132-118">Pianificazione delle riunioni</span><span class="sxs-lookup"><span data-stu-id="f0132-118">Meeting scheduling</span></span> 

  - <span data-ttu-id="f0132-119">Disponibilità delle funzionalità di collaborazione nei client di Teams</span><span class="sxs-lookup"><span data-stu-id="f0132-119">Availability of collaboration functionality in Teams clients</span></span> 

<span data-ttu-id="f0132-120">Per pianificare e configurare la connettività ibrida, il primo passaggio per [](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) lo spostamento [](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) dell'ambiente locale nel cloud, Contoso leggere Pianificare la connettività ibrida e Configurare la connettività ibrida per comprendere come:</span><span class="sxs-lookup"><span data-stu-id="f0132-120">To plan and configure hybrid connectivity, the first step in moving their on-premises environment to the cloud, Contoso read [Plan hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) and [Configure hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) to understand how to:</span></span> 

  - <span data-ttu-id="f0132-121">Configurare il servizio di ambiente locale per la federazione con Office 365.</span><span class="sxs-lookup"><span data-stu-id="f0132-121">Configure their on-premises environment service to federate with Office 365.</span></span> 

  - <span data-ttu-id="f0132-122">Configurare l'ambiente locale in modo che considera attendibile Office 365 e abilitare lo spazio di indirizzi SIP condiviso con Office 365</span><span class="sxs-lookup"><span data-stu-id="f0132-122">Configure their on-premises environment to trust Office 365 and enable shared SIP address space with Office 365</span></span> 

  - <span data-ttu-id="f0132-123">Abilitare lo spazio di indirizzi SIP condiviso nel proprio tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="f0132-123">Enable shared SIP address space in their Office 365 tenant.</span></span>

  - <span data-ttu-id="f0132-124">Usa la modalità Isole durante il progetto pilota tecnico.</span><span class="sxs-lookup"><span data-stu-id="f0132-124">Use Islands mode during the technical pilot.</span></span>

  - <span data-ttu-id="f0132-125">Passare alla modalità TeamsOnly dopo aver abilitato l'utente per Sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="f0132-125">Switch users to TeamsOnly mode once the user is enabled for Phone System.</span></span> <span data-ttu-id="f0132-126">La modalità TeamsOnly è necessaria per il piano per chiamate e l'instradamento diretto.</span><span class="sxs-lookup"><span data-stu-id="f0132-126">TeamsOnly mode is required for  Calling Plan and Direct Routing.</span></span> 
