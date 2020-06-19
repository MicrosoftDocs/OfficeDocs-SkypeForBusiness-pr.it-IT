---
title: Case Study di teams Voice contoso
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
description: Case Study di teams Voice per società multinazionali
appliesto:
- Microsoft Teams
ms.openlocfilehash: d5429b4c45ccea82d1451210438bedd328618604
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786018"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a><span data-ttu-id="93fbf-103">Case Study di Contoso: piano di aggiornamento Teams</span><span class="sxs-lookup"><span data-stu-id="93fbf-103">Contoso case study: Teams upgrade plan</span></span>

<span data-ttu-id="93fbf-104">Nella decisione di eseguire la migrazione da Skype for business a teams, Contoso ha voluto creare un'esperienza di transizione semplice per gli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="93fbf-104">In the decision to migrate from Skype for Business to Teams, Contoso wanted to provide an easy transition experience for end users.</span></span> <span data-ttu-id="93fbf-105">Invece di cambiare tutti i team contemporaneamente, hanno deciso di configurare la connettività ibrida e di usare il metodo di funzionalità sovrapposte per trasferire gli utenti in teams.</span><span class="sxs-lookup"><span data-stu-id="93fbf-105">Instead of switching everyone to Teams at the same time, they decided to set up hybrid connectivity, and use the overlapping capabilities method to move users to Teams.</span></span> <span data-ttu-id="93fbf-106">In questo articolo sono stati consentiti utenti in teams e Skype for business locali per condividere la presenza e comunicare.</span><span class="sxs-lookup"><span data-stu-id="93fbf-106">This allowed users in Teams and Skype for Business on-premises to share presence and communicate.</span></span> <span data-ttu-id="93fbf-107">Quando gli utenti hanno inserito il sistema pilota per telefono, sono stati spostati in modalità solo teams.</span><span class="sxs-lookup"><span data-stu-id="93fbf-107">As users entered the pilot for Phone System, they were moved to Teams Only mode.</span></span>

<span data-ttu-id="93fbf-108">Per comprendere i concetti fondamentali sull'aggiornamento, i metodi e le modalità, Contoso ha letto gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="93fbf-108">To understand fundamental concepts about upgrade, methods, and modes, Contoso read the following articles:</span></span>

- [<span data-ttu-id="93fbf-109">Guida introduttiva all'aggiornamento di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="93fbf-109">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="93fbf-110">Aggiornamento da Skype for Business a Teams</span><span class="sxs-lookup"><span data-stu-id="93fbf-110">Upgrade from Skype for Business to Teams</span></span>](upgrade-to-teams-on-prem-overview.md) 
- [<span data-ttu-id="93fbf-111">Linee guida per la migrazione e l'interoperabilità</span><span class="sxs-lookup"><span data-stu-id="93fbf-111">Migration and interoperability guidance</span></span>](migration-interop-guidance-for-teams-with-skype.md)
 
<span data-ttu-id="93fbf-112">Contoso ha partecipato anche alla sessione Ignite 2019 [che ha progettato il percorso da Skype for business a teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions).</span><span class="sxs-lookup"><span data-stu-id="93fbf-112">Contoso also attended the Ignite 2019 session [Designing your path from Skype for Business to Teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions).</span></span> <span data-ttu-id="93fbf-113">Contoso ha imparato a conoscere:</span><span class="sxs-lookup"><span data-stu-id="93fbf-113">Contoso learned about:</span></span>

- <span data-ttu-id="93fbf-114">Concetti fondamentali come l'interoperabilità, la Federazione e il comportamento di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="93fbf-114">Fundamental concepts such as interoperability, federation, and upgrade behavior</span></span> 

- <span data-ttu-id="93fbf-115">Modalità di coesistenza e gestione basate su TeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="93fbf-115">Coexistence modes and management based on TeamsUpgradePolicy</span></span> 

- <span data-ttu-id="93fbf-116">Esperienza utente finale per:</span><span class="sxs-lookup"><span data-stu-id="93fbf-116">End user experience for:</span></span> 

  - <span data-ttu-id="93fbf-117">Chat e chiamate</span><span class="sxs-lookup"><span data-stu-id="93fbf-117">Chat and Calling</span></span> 

  - <span data-ttu-id="93fbf-118">Pianificazione delle riunioni</span><span class="sxs-lookup"><span data-stu-id="93fbf-118">Meeting scheduling</span></span> 

  - <span data-ttu-id="93fbf-119">Disponibilità della funzionalità di collaborazione nei client di Teams</span><span class="sxs-lookup"><span data-stu-id="93fbf-119">Availability of collaboration functionality in Teams clients</span></span> 

<span data-ttu-id="93fbf-120">Per pianificare e configurare la connettività ibrida, il primo passaggio per spostare l'ambiente locale nel cloud, contoso leggere il [piano di connettività ibrida](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) e [configurare la connettività ibrida](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) per comprendere come:</span><span class="sxs-lookup"><span data-stu-id="93fbf-120">To plan and configure hybrid connectivity, the first step in moving their on-premises environment to the cloud, Contoso read [Plan hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) and [Configure hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) to understand how to:</span></span> 

  - <span data-ttu-id="93fbf-121">Configurare il servizio di ambiente locale per la Federazione con Office 365.</span><span class="sxs-lookup"><span data-stu-id="93fbf-121">Configure their on-premises environment service to federate with Office 365.</span></span> 

  - <span data-ttu-id="93fbf-122">Configurare l'ambiente locale per considerare attendibile Office 365 e abilitare lo spazio di indirizzi SIP condiviso con Office 365</span><span class="sxs-lookup"><span data-stu-id="93fbf-122">Configure their on-premises environment to trust Office 365 and enable shared SIP address space with Office 365</span></span> 

  - <span data-ttu-id="93fbf-123">Abilitare lo spazio di indirizzi SIP condiviso nel tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="93fbf-123">Enable shared SIP address space in their Office 365 tenant.</span></span>

  - <span data-ttu-id="93fbf-124">Usare la modalità isole durante il Pilot tecnico.</span><span class="sxs-lookup"><span data-stu-id="93fbf-124">Use Islands mode during the technical pilot.</span></span>

  - <span data-ttu-id="93fbf-125">Passare gli utenti alla modalità TeamsOnly una volta che l'utente è abilitato per il sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="93fbf-125">Switch users to TeamsOnly mode once the user is enabled for Phone System.</span></span> <span data-ttu-id="93fbf-126">La modalità TeamsOnly è necessaria per chiamare il piano e il routing diretto.</span><span class="sxs-lookup"><span data-stu-id="93fbf-126">TeamsOnly mode is required for  Calling Plan and Direct Routing.</span></span> 
