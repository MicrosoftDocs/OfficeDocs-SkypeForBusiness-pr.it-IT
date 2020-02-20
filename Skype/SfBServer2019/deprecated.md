---
title: Cosa è obsoleto da Skype for Business Server 2019
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Riepilogo: queste funzionalità sono state rimosse da Skype for Business Server 2019.'
ms.openlocfilehash: 40a202f802ec8ac1a0f880f92ad9cf59ce68a627
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42125219"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a><span data-ttu-id="4450c-103">Cosa è obsoleto da Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="4450c-103">What's deprecated from Skype for Business Server 2019</span></span>

<span data-ttu-id="4450c-104">Informazioni sulle caratteristiche e le funzionalità deprecate in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4450c-104">Learn about the features and functionality that are deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="4450c-105">Per informazioni sulle nuove funzionalità in Skype for Business Server 2019, vedere [What ' s in Skype for Business server 2019](whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="4450c-105">For information about new features in Skype for Business Server 2019, see [What's in Skype for Business Server 2019](whats-new.md).</span></span>

<span data-ttu-id="4450c-106">Alcune caratteristiche de-enfatizzate sono incluse in Skype for Business Server 2019 per la compatibilità con le versioni precedenti del prodotto.</span><span class="sxs-lookup"><span data-stu-id="4450c-106">Some de-emphasized features are included in Skype for Business Server 2019 for compatibility with previous product versions.</span></span>

## <a name="features-deprecated-in-skype-for-business-server-2019"></a><span data-ttu-id="4450c-107">Caratteristiche deprecate in Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="4450c-107">Features deprecated in Skype for Business Server 2019</span></span> 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a><span data-ttu-id="4450c-108">Gateway XMPP per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4450c-108">XMPP Gateways for Skype for Business Server</span></span>

<span data-ttu-id="4450c-109">Skype for Business Server 2015 e i suoi predecessori hanno consentito di configurare un proxy XMPP (Extensible Messaging and Presence Protocol) nel server perimetrale e un gateway XMPP nel front end server o nel pool Front end.</span><span class="sxs-lookup"><span data-stu-id="4450c-109">Skype for Business Server 2015 and its predecessors allowed you to configure an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="4450c-110">Questa funzionalità non è più disponibile in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4450c-110">This functionality is no longer available in Skype for Business Server 2019.</span></span>

### <a name="persistent-chat-for-skype-for-business-server"></a><span data-ttu-id="4450c-111">Chat persistente per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4450c-111">Persistent Chat for Skype for Business Server</span></span>

<span data-ttu-id="4450c-112">Il server Chat persistente è un ruolo facoltativo che consente a più utenti dell'organizzazione di partecipare a conversazioni chat room che persistono nel tempo.</span><span class="sxs-lookup"><span data-stu-id="4450c-112">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="4450c-113">La chat persistente non può essere distribuita con Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4450c-113">Persistent chat can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="4450c-114">Questo ruolo del server viene rimosso dal generatore di topologie e dal codice.</span><span class="sxs-lookup"><span data-stu-id="4450c-114">This server role is removed from Topology Builder, as well as from the code.</span></span> 

<span data-ttu-id="4450c-115">La stessa funzionalità è disponibile in teams.</span><span class="sxs-lookup"><span data-stu-id="4450c-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="4450c-116">Per ulteriori informazioni, vedere [Guida introduttiva all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="4450c-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span>

### <a name="sql-mirroring-for-skype-for-business-server"></a><span data-ttu-id="4450c-117">Mirroring SQL per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4450c-117">SQL Mirroring for Skype for Business Server</span></span>

<span data-ttu-id="4450c-118">Il mirroring SQL non può essere distribuito con Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4450c-118">SQL Mirroring can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="4450c-119">Altre opzioni per la disponibilità elevata e il ripristino di emergenza sono ancora supportate e è consigliabile scegliere tra di esse.</span><span class="sxs-lookup"><span data-stu-id="4450c-119">Other options for providing High Availability and Disaster Recovery are still supported and you should choose from among them.</span></span> <span data-ttu-id="4450c-120">Per esaminare le opzioni, vedere [pianificare la disponibilità elevata e il ripristino di emergenza in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) .</span><span class="sxs-lookup"><span data-stu-id="4450c-120">See [Plan for high availability and disaster recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) to review the options.</span></span>

### <a name="in-place-upgrades"></a><span data-ttu-id="4450c-121">Aggiornamenti sul posto</span><span class="sxs-lookup"><span data-stu-id="4450c-121">In-place upgrades</span></span> 

<span data-ttu-id="4450c-122">Gli aggiornamenti sul posto sono disponibili in Skype for Business Server 2015 ma non sono più supportati in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4450c-122">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="4450c-123">L'aggiornamento affiancato e la coesistenza sono supportati, vedere [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="4450c-123">Side by side upgrade and coexistance is supported, see [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>

### <a name="mobility-service-mcx"></a><span data-ttu-id="4450c-124">Servizio per dispositivi mobili (MCX)</span><span class="sxs-lookup"><span data-stu-id="4450c-124">Mobility Service (Mcx)</span></span>

<span data-ttu-id="4450c-125">Il supporto per i servizi mobili utilizzato dai client mobili legacy non è più disponibile in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4450c-125">Mobility Service support used by legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="4450c-126">Questo è stato annunciato in precedenza in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="4450c-126">This was previously announced in Skype for Business Server 2015.</span></span>

<span data-ttu-id="4450c-127">Tutti i client per dispositivi mobili Skype for business corrente utilizzano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti.</span><span class="sxs-lookup"><span data-stu-id="4450c-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="4450c-128">Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.</span><span class="sxs-lookup"><span data-stu-id="4450c-128">Users with legacy clients using Mcx will need to upgrade to a current client.</span></span>

<span data-ttu-id="4450c-129">Per ulteriori informazioni, vedere [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [mobile client Feature Comparison for Skype for business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span><span class="sxs-lookup"><span data-stu-id="4450c-129">For more details, see [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [Mobile client feature comparison for Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span></span>

## <a name="tools"></a><span data-ttu-id="4450c-130">Strumenti</span><span class="sxs-lookup"><span data-stu-id="4450c-130">Tools</span></span>

<span data-ttu-id="4450c-131">Gli strumenti seguenti non saranno disponibili per l'uso nella versione iniziale di Skype for Business Server 2019:</span><span class="sxs-lookup"><span data-stu-id="4450c-131">The following tools will not be available for use at the initial release of Skype for Business Server 2019:</span></span>

- <span data-ttu-id="4450c-132">Calcolatore di pianificazione della capacità di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4450c-132">Skype for Business Server Capacity Planning Calculator</span></span>
- <span data-ttu-id="4450c-133">Strumenti di debug di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4450c-133">Skype for Business Server Debugging Tools</span></span>
- <span data-ttu-id="4450c-134">Strumenti del Resource Kit di Skype for Business Server (alcuni strumenti verranno rimossi)</span><span class="sxs-lookup"><span data-stu-id="4450c-134">Skype for Business Server Resource Kit Tools (some tools will be removed)</span></span>
    - <span data-ttu-id="4450c-135">Chiamata Parkometer</span><span class="sxs-lookup"><span data-stu-id="4450c-135">Call Parkometer</span></span>
    - <span data-ttu-id="4450c-136">Console utente di ricerca</span><span class="sxs-lookup"><span data-stu-id="4450c-136">Lookup user console</span></span>
    - <span data-ttu-id="4450c-137">Migrazione degli annunci di numeri non assegnati</span><span class="sxs-lookup"><span data-stu-id="4450c-137">Unassigned number Announcement Migration</span></span>

<span data-ttu-id="4450c-138">Gli strumenti seguenti non sono supportati con Skype for Business Server 2019:</span><span class="sxs-lookup"><span data-stu-id="4450c-138">The following tools are not supported with Skype for Business Server 2019:</span></span>

- <span data-ttu-id="4450c-139">Metodologia della qualità delle chiamate (ma non Call Quality Dashboard)</span><span class="sxs-lookup"><span data-stu-id="4450c-139">Call Quality Methodology (but not Call Quality Dashboard)</span></span>
- <span data-ttu-id="4450c-140">Scorecard della metodologia della qualità delle chiamate Microsoft, v 1.5</span><span class="sxs-lookup"><span data-stu-id="4450c-140">Microsoft Call Quality Methodology Scorecard, v1.5</span></span>
- <span data-ttu-id="4450c-141">Strumento di pianificazione di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4450c-141">Skype for Business Server 2015 Planning Tool</span></span>
- <span data-ttu-id="4450c-142">Strumento per lo stress e le prestazioni di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4450c-142">Skype for Business Server 2015 Stress and Performance Tool</span></span>

### <a name="see-also"></a><span data-ttu-id="4450c-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4450c-143">See also</span></span>

[<span data-ttu-id="4450c-144">Novità di Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="4450c-144">What's new in Skype for Business Server 2019</span></span>](whats-new.md)

[<span data-ttu-id="4450c-145">Migrazione della Federazione XMPP</span><span class="sxs-lookup"><span data-stu-id="4450c-145">Migrating XMPP federation</span></span>](migration/migrating-xmpp-federation.md)
