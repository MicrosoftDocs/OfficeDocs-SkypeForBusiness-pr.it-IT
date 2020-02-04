---
title: 'Lync Server 2013: Componenti VoIP del server front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End Server VoIP components
ms:assetid: 310e81a7-da45-47d4-95d0-92837e386502
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425812(v=OCS.15)
ms:contentKeyID: 48183765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bab5751fc0291047f3795731f379d1e14f5f12b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-server-voip-components-for-lync-server-2013"></a><span data-ttu-id="e6610-102">Componenti VoIP del server front-end per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6610-102">Front End Server VoIP components for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6610-103">_**Argomento Ultima modifica:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e6610-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e6610-104">I componenti VoIP situati nei server front-end sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="e6610-104">The VoIP components located on Front End Servers are as follows:</span></span>

  - <span data-ttu-id="e6610-105">Servizio di traduzione</span><span class="sxs-lookup"><span data-stu-id="e6610-105">Translation Service</span></span>

  - <span data-ttu-id="e6610-106">Componente di routing in ingresso</span><span class="sxs-lookup"><span data-stu-id="e6610-106">Inbound Routing component</span></span>

  - <span data-ttu-id="e6610-107">Componente di routing in uscita</span><span class="sxs-lookup"><span data-stu-id="e6610-107">Outbound Routing component</span></span>

  - <span data-ttu-id="e6610-108">Componente di routing della messaggistica unificata di Exchange</span><span class="sxs-lookup"><span data-stu-id="e6610-108">Exchange UM Routing component</span></span>

  - <span data-ttu-id="e6610-109">Componente di routing Intercluster</span><span class="sxs-lookup"><span data-stu-id="e6610-109">Intercluster Routing component</span></span>

  - [<span data-ttu-id="e6610-110">Componente Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6610-110">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)

<div>

## <a name="translation-service"></a><span data-ttu-id="e6610-111">Servizio di traduzione</span><span class="sxs-lookup"><span data-stu-id="e6610-111">Translation Service</span></span>

<span data-ttu-id="e6610-112">Il servizio di traduzione è il componente server responsabile della traduzione di un numero composto nel formato E. 164 o in un altro formato, in base alle regole di normalizzazione definite dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="e6610-112">The Translation Service is the server component that is responsible for translating a dialed number into the E.164 format or another format, according to the normalization rules that are defined by the administrator.</span></span> <span data-ttu-id="e6610-113">Il servizio di traduzione può tradursi in formati diversi da E. 164 se l'organizzazione usa un sistema di numerazione privato o usa un gateway o un PBX che non supporta E. 164.</span><span class="sxs-lookup"><span data-stu-id="e6610-113">The Translation Service can translate to formats other than E.164 if your organization uses a private numbering system or uses a gateway or PBX that does not support E.164.</span></span>

</div>

<div>

## <a name="inbound-routing-component"></a><span data-ttu-id="e6610-114">Componente di routing in ingresso</span><span class="sxs-lookup"><span data-stu-id="e6610-114">Inbound Routing Component</span></span>

<span data-ttu-id="e6610-115">Il componente di routing in ingresso gestisce le chiamate in arrivo in gran parte in base alle preferenze specificate dagli utenti nei client Voice aziendali.</span><span class="sxs-lookup"><span data-stu-id="e6610-115">The Inbound Routing component handles incoming calls largely according to preferences that are specified by users on their Enterprise Voice clients.</span></span> <span data-ttu-id="e6610-116">Facilita inoltre la chiamata del delegato e lo squillo simultaneo, se configurato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="e6610-116">It also facilitates delegate ringing and simultaneous ringing, if configured by the user.</span></span> <span data-ttu-id="e6610-117">Ad esempio, gli utenti specificano se le chiamate senza risposta vengono inoltrate o semplicemente registrate per la notifica.</span><span class="sxs-lookup"><span data-stu-id="e6610-117">For example, users specify whether unanswered calls are forwarded or simply logged for notification.</span></span> <span data-ttu-id="e6610-118">Se l'inoltro di chiamata è abilitato, gli utenti possono specificare se le chiamate senza risposta devono essere inoltrate a un altro numero o a un server di messaggistica unificata di Exchange configurato per fornire le risposte alle chiamate.</span><span class="sxs-lookup"><span data-stu-id="e6610-118">If call forwarding is enabled, users can specify whether unanswered calls should be forwarded to another number or to a Exchange UM server that has been configured to provide call answering.</span></span> <span data-ttu-id="e6610-119">Il componente di routing in ingresso viene installato per impostazione predefinita in tutti i server Standard Edition e front end.</span><span class="sxs-lookup"><span data-stu-id="e6610-119">The Inbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

</div>

<div>

## <a name="outbound-routing-component"></a><span data-ttu-id="e6610-120">Componente di routing in uscita</span><span class="sxs-lookup"><span data-stu-id="e6610-120">Outbound Routing Component</span></span>

<span data-ttu-id="e6610-121">Il componente di routing in uscita instrada le chiamate alle destinazioni PBX o PSTN.</span><span class="sxs-lookup"><span data-stu-id="e6610-121">The Outbound Routing component routes calls to PBX or PSTN destinations.</span></span> <span data-ttu-id="e6610-122">Applica le regole di autorizzazione della chiamata, come definito dal criterio vocale dell'utente, ai chiamanti e determina il gateway PSTN ottimale per il routing di ogni chiamata.</span><span class="sxs-lookup"><span data-stu-id="e6610-122">It applies call authorization rules, as defined by the user’s voice policy, to callers and determines the optimal PSTN gateway for routing each call.</span></span> <span data-ttu-id="e6610-123">Il componente di routing in uscita viene installato per impostazione predefinita in tutti i server Standard Edition e front end.</span><span class="sxs-lookup"><span data-stu-id="e6610-123">The Outbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

<span data-ttu-id="e6610-124">La logica di routing utilizzata dal componente di routing in uscita è in larga misura configurata dagli amministratori di rete o telefonici in base ai requisiti delle rispettive organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="e6610-124">The routing logic that is used by the Outbound Routing component is in large measure configured by network or telephony administrators according to the requirements of their organizations.</span></span>

</div>

<div>

## <a name="exchange-um-routing-component"></a><span data-ttu-id="e6610-125">Componente di routing della messaggistica unificata di Exchange</span><span class="sxs-lookup"><span data-stu-id="e6610-125">Exchange UM Routing Component</span></span>

<span data-ttu-id="e6610-126">Il componente di routing della messaggistica unificata di Exchange gestisce il routing tra Lync Server e i server che gestiscono la messaggistica unificata di Exchange per integrare Lync Server con le caratteristiche di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="e6610-126">The Exchange UM routing component handles routing between Lync Server and servers running Exchange Unified Messaging (UM), to integrate Lync Server with Unified Messaging features.</span></span>

<span data-ttu-id="e6610-127">Il componente di routing della messaggistica unificata di Exchange gestisce anche il reinstradamento della segreteria telefonica tramite la rete PSTN se i server Messaggistica unificata di Exchange</span><span class="sxs-lookup"><span data-stu-id="e6610-127">The Exchange UM routing component also handles rerouting of voice mail over the PSTN if Exchange UM servers are unavailable.</span></span> <span data-ttu-id="e6610-128">Se si hanno utenti di VoIP aziendale nei siti di succursale che non hanno un collegamento WAN resiliente a un sito centrale, l'appliance Survivable Branch distribuita nel sito della filiale offre la sopravvivenza della segreteria telefonica per gli utenti di Branch durante un'interruzione WAN.</span><span class="sxs-lookup"><span data-stu-id="e6610-128">If you have Enterprise Voice users at branch sites that do not have a resilient WAN link to a central site, the Survivable Branch Appliance that you deploy at the branch site provides voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="e6610-129">Quando il collegamento WAN non è disponibile, il Survivable Branch Appliance esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e6610-129">When the WAN link is unavailable, the Survivable Branch Appliance does the following:</span></span>

  - <span data-ttu-id="e6610-130">reindirizza le chiamate senza risposta tramite la rete PSTN al server Messaggistica unificata di Exchange nel sito centrale</span><span class="sxs-lookup"><span data-stu-id="e6610-130">reroutes unanswered calls over the PSTN to the Exchange Unified Messaging server in the central site</span></span>

  - <span data-ttu-id="e6610-131">consente a un utente di recuperare i messaggi della segreteria telefonica tramite la rete PSTN</span><span class="sxs-lookup"><span data-stu-id="e6610-131">provides the ability for a user to retrieve voice mail messages over the PSTN</span></span>

  - <span data-ttu-id="e6610-132">Accoda le notifiche delle chiamate perse e quindi le carica nel server Messaggistica unificata di Exchange quando viene ripristinato il collegamento WAN.</span><span class="sxs-lookup"><span data-stu-id="e6610-132">queues missed call notifications, and then uploads them to the Exchange UM server when the WAN link is restored.</span></span>

<span data-ttu-id="e6610-133">Per abilitare la reinstradazione della segreteria telefonica, è consigliabile che l'amministratore di Exchange configuri l'operatore automatico di messaggistica unificata di Exchange per accettare solo i messaggi.</span><span class="sxs-lookup"><span data-stu-id="e6610-133">To enable voice mail rerouting, we recommend that your Exchange administrator configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span>

<span data-ttu-id="e6610-134">Per informazioni dettagliate su queste funzionalità, vedere [pianificazione dell'integrazione della messaggistica unificata di Exchange in Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) e [pianificazione della resilienza aziendale in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md), rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="e6610-134">For details about these features, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Planning for Enterprise Voice resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md), respectively.</span></span>

</div>

<div>

## <a name="intercluster-routing-component"></a><span data-ttu-id="e6610-135">Componente di routing Intercluster</span><span class="sxs-lookup"><span data-stu-id="e6610-135">Intercluster Routing Component</span></span>

<span data-ttu-id="e6610-136">Il componente di routing Intercluster è responsabile per il routing delle chiamate al pool di registrar principale del destinatario.</span><span class="sxs-lookup"><span data-stu-id="e6610-136">The Intercluster routing component is responsible for routing calls to the callee’s primary Registrar pool.</span></span> <span data-ttu-id="e6610-137">Se non è disponibile, il componente instrada la chiamata al pool di registrar di backup del destinatario.</span><span class="sxs-lookup"><span data-stu-id="e6610-137">If that is unavailable, the component routes the call to the callee’s backup Registrar pool.</span></span> <span data-ttu-id="e6610-138">Se i pool di registrar primari e di backup del destinatario non sono raggiungibili tramite la rete IP, il componente di routing Intercluster reindirizza la chiamata tramite PSTN al numero di telefono dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e6610-138">If the callee’s primary and backup Registrar pools are unreachable over the IP network, the Intercluster routing component reroutes the call over the PSTN to the user’s telephone number.</span></span>

</div>

<div>

## <a name="other-front-end-server-components-required-for-voip"></a><span data-ttu-id="e6610-139">Altri componenti del server front-end necessari per VoIP</span><span class="sxs-lookup"><span data-stu-id="e6610-139">Other Front End Server Components Required for VoIP</span></span>

<span data-ttu-id="e6610-140">Altri componenti che risiedono nel server front-end o nel Director che offrono un supporto essenziale per VoIP, ma non sono componenti VoIP, includono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="e6610-140">Other components residing on the Front End Server or Director that provide essential support for VoIP, but are not themselves VoIP components, include the following:</span></span>

  - <span data-ttu-id="e6610-141">**Servizi utente.**</span><span class="sxs-lookup"><span data-stu-id="e6610-141">**User Services.**</span></span> <span data-ttu-id="e6610-142">Eseguire la ricerca in numero inverso sul numero di telefono di destinazione di ogni chiamata in arrivo e corrispondere tale numero all'URI SIP dell'utente di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e6610-142">Perform reverse number lookup on the destination phone number of each incoming call and match that number to the SIP URI of the destination user.</span></span> <span data-ttu-id="e6610-143">Usando queste informazioni, il componente di routing in ingresso distribuisce la chiamata agli endpoint SIP registrati di tale utente.</span><span class="sxs-lookup"><span data-stu-id="e6610-143">Using this information, the Inbound Routing component distributes the call to that user’s registered SIP endpoints.</span></span> <span data-ttu-id="e6610-144">Servizi utente è un componente principale in tutti i server e direttori front-end.</span><span class="sxs-lookup"><span data-stu-id="e6610-144">User Services is a core component on all Front End Servers and Directors.</span></span>

  - <span data-ttu-id="e6610-145">**User Replicator.**</span><span class="sxs-lookup"><span data-stu-id="e6610-145">**User Replicator.**</span></span> <span data-ttu-id="e6610-146">Estrae i numeri di telefono degli utenti da servizi di dominio Active Directory e li scrive nelle tabelle del database RTC, dove sono disponibili per i servizi utente e per il server della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="e6610-146">Extracts user phone numbers from Active Directory Domain Services and writes them to tables in the RTC database, where they are available to User Services and Address Book Server.</span></span> <span data-ttu-id="e6610-147">User Replicator è un componente principale in tutti i server front-end.</span><span class="sxs-lookup"><span data-stu-id="e6610-147">User Replicator is a core component on all Front End Servers.</span></span>

  - <span data-ttu-id="e6610-148">**Server Rubrica.**</span><span class="sxs-lookup"><span data-stu-id="e6610-148">**Address Book Server.**</span></span> <span data-ttu-id="e6610-149">Fornisce informazioni globali sugli elenchi di indirizzi da servizi di dominio Active Directory ai client Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e6610-149">Provides global address list information from Active Directory Domain Services to Lync Server clients.</span></span> <span data-ttu-id="e6610-150">Recupera inoltre le informazioni relative a utenti e contatti dal database RTC, scrive le informazioni nei file della Rubrica e quindi archivia i file in una cartella condivisa in cui vengono scaricati dai client Lync.</span><span class="sxs-lookup"><span data-stu-id="e6610-150">It also retrieves user and contact information from the RTC database, writes the information to the Address Book files, and then stores the files on a shared folder where they are downloaded by Lync clients.</span></span> <span data-ttu-id="e6610-151">Il server della Rubrica scrive le informazioni nel database RTCAb, usato dal servizio query Web della Rubrica per rispondere alle query di ricerca degli utenti da Microsoft Lync 2010 mobile.</span><span class="sxs-lookup"><span data-stu-id="e6610-151">The Address Book Server writes the information to the RTCAb database, which is used by the Address Book Web Query service to respond to user search queries from Microsoft Lync 2010 Mobile.</span></span> <span data-ttu-id="e6610-152">Si normalizza facoltativamente i numeri di telefono degli utenti aziendali scritti nel database RTC allo scopo di provisionare i contatti utente in Lync.</span><span class="sxs-lookup"><span data-stu-id="e6610-152">It optionally normalizes enterprise user phone numbers that are written to the RTC database for the purpose of provisioning user contacts in Lync.</span></span> <span data-ttu-id="e6610-153">Il servizio Rubrica viene installato per impostazione predefinita in tutti i server front-end.</span><span class="sxs-lookup"><span data-stu-id="e6610-153">The Address Book service is installed by default on all Front End Servers.</span></span> <span data-ttu-id="e6610-154">Il servizio query Web per la Rubrica viene installato per impostazione predefinita con i servizi Web di ogni server front-end.</span><span class="sxs-lookup"><span data-stu-id="e6610-154">The Address Book Web Query service is installed by default with the Web services on each Front End Servers.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

