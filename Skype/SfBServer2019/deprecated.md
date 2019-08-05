---
title: Cosa è deprecato da Skype for Business Server 2019
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Riepilogo: queste funzionalità sono state rimosse da Skype for Business Server 2019.'
ms.openlocfilehash: 9fd6ddc28a3b75b8d4c411aa7909516d4b5c0ab8
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "36195994"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a><span data-ttu-id="0f625-103">Cosa è deprecato da Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="0f625-103">What's deprecated from Skype for Business Server 2019</span></span>

<span data-ttu-id="0f625-104">Informazioni sulle caratteristiche e le funzionalità deprecate in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0f625-104">Learn about the features and functionality that are deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="0f625-105">Per informazioni sulle nuove funzionalità di Skype for Business Server 2019, vedere [novità di Skype for Business server 2019](whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="0f625-105">For information about new features in Skype for Business Server 2019, see [What's in Skype for Business Server 2019](whats-new.md).</span></span>

<span data-ttu-id="0f625-106">Alcune caratteristiche de-enfatizzate sono incluse in Skype for Business Server 2019 per la compatibilità con le versioni precedenti del prodotto.</span><span class="sxs-lookup"><span data-stu-id="0f625-106">Some de-emphasized features are included in Skype for Business Server 2019 for compatibility with previous product versions.</span></span>

## <a name="features-deprecated-in-skype-for-business-server-2019"></a><span data-ttu-id="0f625-107">Caratteristiche deprecate in Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="0f625-107">Features deprecated in Skype for Business Server 2019</span></span> 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a><span data-ttu-id="0f625-108">Gateway XMPP per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0f625-108">XMPP Gateways for Skype for Business Server</span></span>

<span data-ttu-id="0f625-109">Skype for Business Server 2015 e i suoi predecessori hanno consentito di configurare un proxy XMPP (Extensible Messaging and Presence Protocol) nell'Edge Server e un gateway XMPP nel server front-end o nel pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="0f625-109">Skype for Business Server 2015 and its predecessors allowed you to configure an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="0f625-110">Questa funzionalità non è più disponibile in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0f625-110">This functionality is no longer available in Skype for Business Server 2019.</span></span>

### <a name="persistent-chat-for-skype-for-business-server"></a><span data-ttu-id="0f625-111">Chat persistente per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0f625-111">Persistent Chat for Skype for Business Server</span></span>

<span data-ttu-id="0f625-112">Il server di chat persistente è un ruolo facoltativo che consente a più utenti dell'organizzazione di partecipare alle conversazioni delle chat room che persistono nel tempo.</span><span class="sxs-lookup"><span data-stu-id="0f625-112">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="0f625-113">La chat persistente non può essere distribuita con Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0f625-113">Persistent chat can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="0f625-114">Questo ruolo del server viene rimosso dal generatore di topologia e dal codice.</span><span class="sxs-lookup"><span data-stu-id="0f625-114">This server role is removed from Topology Builder, as well as from the code.</span></span> 

<span data-ttu-id="0f625-115">La stessa funzionalità è disponibile in teams.</span><span class="sxs-lookup"><span data-stu-id="0f625-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="0f625-116">Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="0f625-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span>

### <a name="sql-mirroring-for-skype-for-business-server"></a><span data-ttu-id="0f625-117">Mirroring SQL per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0f625-117">SQL Mirroring for Skype for Business Server</span></span>

<span data-ttu-id="0f625-118">Il mirroring SQL non può essere distribuito con Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0f625-118">SQL Mirroring can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="0f625-119">Altre opzioni per fornire elevata disponibilità e ripristino di emergenza sono ancora supportate e scegliere tra di esse.</span><span class="sxs-lookup"><span data-stu-id="0f625-119">Other options for providing High Availability and Disaster Recovery are still supported and you should choose from among them.</span></span> <span data-ttu-id="0f625-120">Vedere [pianificare l'elevata disponibilità e il ripristino di emergenza in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) per esaminare le opzioni.</span><span class="sxs-lookup"><span data-stu-id="0f625-120">See [Plan for high availability and disaster recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) to review the options.</span></span>

### <a name="in-place-upgrades"></a><span data-ttu-id="0f625-121">Aggiornamenti sul posto</span><span class="sxs-lookup"><span data-stu-id="0f625-121">In-place upgrades</span></span> 

<span data-ttu-id="0f625-122">Gli aggiornamenti sul posto sono disponibili in Skype for Business Server 2015, ma non sono più supportati in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0f625-122">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="0f625-123">L'aggiornamento affiancato e la coesistenza sono supportati, vedere [migrazione a Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="0f625-123">Side by side upgrade and coexistance is supported, see [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>

### <a name="mobility-service-mcx"></a><span data-ttu-id="0f625-124">Servizio di mobilità (MCX)</span><span class="sxs-lookup"><span data-stu-id="0f625-124">Mobility Service (Mcx)</span></span>

<span data-ttu-id="0f625-125">Il supporto del servizio di mobilità usato dai client mobili legacy non è più disponibile in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0f625-125">Mobility Service support used by legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="0f625-126">Questa operazione è stata annunciata in precedenza in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0f625-126">This was previously announced in Skype for Business Server 2015.</span></span>

<span data-ttu-id="0f625-127">Tutti i client di Skype for business mobile correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti.</span><span class="sxs-lookup"><span data-stu-id="0f625-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="0f625-128">Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.</span><span class="sxs-lookup"><span data-stu-id="0f625-128">Users with legacy clients using Mcx will need to upgrade to a current client.</span></span>

<span data-ttu-id="0f625-129">Per altre informazioni, Vedi [pianificare la mobilità per Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) e il [confronto delle caratteristiche dei client per dispositivi mobili per Skype for business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span><span class="sxs-lookup"><span data-stu-id="0f625-129">For more details, see [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [Mobile client feature comparison for Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span></span>

## <a name="tools"></a><span data-ttu-id="0f625-130">Strumenti</span><span class="sxs-lookup"><span data-stu-id="0f625-130">Tools</span></span>

<span data-ttu-id="0f625-131">Gli strumenti seguenti non saranno disponibili per l'uso in occasione della versione iniziale di Skype for Business Server 2019:</span><span class="sxs-lookup"><span data-stu-id="0f625-131">The following tools will not be available for use at the initial release of Skype for Business Server 2019:</span></span>

- <span data-ttu-id="0f625-132">Calcolatore di pianificazione della capacità di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0f625-132">Skype for Business Server Capacity Planning Calculator</span></span>
- <span data-ttu-id="0f625-133">Strumenti di debug di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0f625-133">Skype for Business Server Debugging Tools</span></span>
- <span data-ttu-id="0f625-134">Strumenti del Resource Kit di Skype for Business Server (alcuni strumenti verranno rimossi)</span><span class="sxs-lookup"><span data-stu-id="0f625-134">Skype for Business Server Resource Kit Tools (some tools will be removed)</span></span>
    - <span data-ttu-id="0f625-135">Chiama Parkometer</span><span class="sxs-lookup"><span data-stu-id="0f625-135">Call Parkometer</span></span>
    - <span data-ttu-id="0f625-136">Console utente di ricerca</span><span class="sxs-lookup"><span data-stu-id="0f625-136">Lookup user console</span></span>
    - <span data-ttu-id="0f625-137">Migrazione degli annunci di numeri non assegnati</span><span class="sxs-lookup"><span data-stu-id="0f625-137">Unassigned number Announcement Migration</span></span>

<span data-ttu-id="0f625-138">Gli strumenti seguenti non sono supportati con Skype for Business Server 2019:</span><span class="sxs-lookup"><span data-stu-id="0f625-138">The following tools are not supported with Skype for Business Server 2019:</span></span>

- <span data-ttu-id="0f625-139">Metodologia di qualità delle chiamate (ma non chiamata Quality Dashboard)</span><span class="sxs-lookup"><span data-stu-id="0f625-139">Call Quality Methodology (but not Call Quality Dashboard)</span></span>
- <span data-ttu-id="0f625-140">Scorecard della metodologia della qualità della chiamata Microsoft, v 1.5</span><span class="sxs-lookup"><span data-stu-id="0f625-140">Microsoft Call Quality Methodology Scorecard, v1.5</span></span>
- <span data-ttu-id="0f625-141">Progettazione della topologia per Lync Server 2013 mediante lo strumento di pianificazione</span><span class="sxs-lookup"><span data-stu-id="0f625-141">Skype for Business Server 2015 Planning Tool</span></span>
- <span data-ttu-id="0f625-142">Strumento di stress e prestazioni di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0f625-142">Skype for Business Server 2015 Stress and Performance Tool</span></span>

### <a name="see-also"></a><span data-ttu-id="0f625-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f625-143">See also</span></span>

[<span data-ttu-id="0f625-144">Novità di Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="0f625-144">What's new in Skype for Business Server 2019</span></span>](whats-new.md)

[<span data-ttu-id="0f625-145">Migrazione della Federazione XMPP</span><span class="sxs-lookup"><span data-stu-id="0f625-145">Migrating XMPP federation</span></span>](migration/migrating-xmpp-federation.md)
