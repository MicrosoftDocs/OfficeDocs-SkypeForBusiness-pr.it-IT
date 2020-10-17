---
title: 'Lync Server 2013: Componenti VoIP di front end server'
description: 'Lync Server 2013: Componenti VoIP di front end server.'
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
ms.openlocfilehash: f9390d06cf6277ef79ec2ec785bad4b497bc04a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567092"
---
# <a name="front-end-server-voip-components-for-lync-server-2013"></a><span data-ttu-id="6f2c3-103">Componenti VoIP di front end server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f2c3-103">Front End Server VoIP components for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f2c3-104">_**Ultimo argomento modificato:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="6f2c3-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="6f2c3-105">I componenti VoIP presenti nei front end server sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="6f2c3-105">The VoIP components located on Front End Servers are as follows:</span></span>

  - <span data-ttu-id="6f2c3-106">Servizio di conversione</span><span class="sxs-lookup"><span data-stu-id="6f2c3-106">Translation Service</span></span>

  - <span data-ttu-id="6f2c3-107">Componente di routing in ingresso</span><span class="sxs-lookup"><span data-stu-id="6f2c3-107">Inbound Routing component</span></span>

  - <span data-ttu-id="6f2c3-108">Componente di routing in uscita</span><span class="sxs-lookup"><span data-stu-id="6f2c3-108">Outbound Routing component</span></span>

  - <span data-ttu-id="6f2c3-109">Componente di routing per Messaggistica unificata di Exchange</span><span class="sxs-lookup"><span data-stu-id="6f2c3-109">Exchange UM Routing component</span></span>

  - <span data-ttu-id="6f2c3-110">Componente di routing tra cluster</span><span class="sxs-lookup"><span data-stu-id="6f2c3-110">Intercluster Routing component</span></span>

  - [<span data-ttu-id="6f2c3-111">Componente Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f2c3-111">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)

<div>

## <a name="translation-service"></a><span data-ttu-id="6f2c3-112">Servizio di conversione</span><span class="sxs-lookup"><span data-stu-id="6f2c3-112">Translation Service</span></span>

<span data-ttu-id="6f2c3-p101">Il servizio di conversione è il componente server responsabile della conversione di un numero composto nel formato E.164 o in un altro formato, in base alle regole di normalizzazione definite dall'amministratore. Questo servizio può eseguire la conversione in formati diversi dal formato E.164 se nell'organizzazione viene utilizzato un sistema di numerazione privato oppure un gateway o un PBX che non supporta il formato E.164.</span><span class="sxs-lookup"><span data-stu-id="6f2c3-p101">The Translation Service is the server component that is responsible for translating a dialed number into the E.164 format or another format, according to the normalization rules that are defined by the administrator. The Translation Service can translate to formats other than E.164 if your organization uses a private numbering system or uses a gateway or PBX that does not support E.164.</span></span>

</div>

<div>

## <a name="inbound-routing-component"></a><span data-ttu-id="6f2c3-115">Componente di routing in ingresso</span><span class="sxs-lookup"><span data-stu-id="6f2c3-115">Inbound Routing Component</span></span>

<span data-ttu-id="6f2c3-116">Il componente di routing in ingresso gestisce le chiamate in ingresso tenendo generalmente conto delle preferenze specificate dagli utenti nei client di Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="6f2c3-116">The Inbound Routing component handles incoming calls largely according to preferences that are specified by users on their Enterprise Voice clients.</span></span> <span data-ttu-id="6f2c3-117">Consente inoltre di utilizzare le funzionalità di chiamata ai delegati e di squillo simultaneo, se configurate dall'utente.</span><span class="sxs-lookup"><span data-stu-id="6f2c3-117">It also facilitates delegate ringing and simultaneous ringing, if configured by the user.</span></span> <span data-ttu-id="6f2c3-118">Gli utenti possono ad esempio specificare se le chiamate senza risposta devono essere inoltrate o semplicemente registrate a scopo di notifica.</span><span class="sxs-lookup"><span data-stu-id="6f2c3-118">For example, users specify whether unanswered calls are forwarded or simply logged for notification.</span></span> <span data-ttu-id="6f2c3-119">Se l'inoltro di chiamata è abilitato, gli utenti possono specificare se le chiamate senza risposta devono essere inoltrate a un altro numero o a un server di messaggistica unificata di Exchange configurato per fornire il risponditore automatico.</span><span class="sxs-lookup"><span data-stu-id="6f2c3-119">If call forwarding is enabled, users can specify whether unanswered calls should be forwarded to another number or to a Exchange UM server that has been configured to provide call answering.</span></span> <span data-ttu-id="6f2c3-120">Il componente di routing in ingresso viene installato per impostazione predefinita in tutti i server Standard Edition e front end server.</span><span class="sxs-lookup"><span data-stu-id="6f2c3-120">The Inbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

</div>

<div>

## <a name="outbound-routing-component"></a><span data-ttu-id="6f2c3-121">Componente di routing in uscita</span><span class="sxs-lookup"><span data-stu-id="6f2c3-121">Outbound Routing Component</span></span>

<span data-ttu-id="6f2c3-122">Il componente di routing in uscita instrada le chiamate a destinazioni PBX o PSTN.</span><span class="sxs-lookup"><span data-stu-id="6f2c3-122">The Outbound Routing component routes calls to PBX or PSTN destinations.</span></span> <span data-ttu-id="6f2c3-123">Applica ai chiamanti le regole di autorizzazione per le chiamate, secondo quanto definito dal criterio vocale dell'utente, e determina il gateway PSTN ottimale per il routing di ogni chiamata.</span><span class="sxs-lookup"><span data-stu-id="6f2c3-123">It applies call authorization rules, as defined by the user’s voice policy, to callers and determines the optimal PSTN gateway for routing each call.</span></span> <span data-ttu-id="6f2c3-124">Il componente di routing in uscita viene installato per impostazione predefinita in tutti i server Standard Edition e front end server.</span><span class="sxs-lookup"><span data-stu-id="6f2c3-124">The Outbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

<span data-ttu-id="6f2c3-125">La logica di routing utilizzata dal componente di routing in uscita viene in buona parte configurata dagli amministratori di rete o di telefonia in base ai requisiti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6f2c3-125">The routing logic that is used by the Outbound Routing component is in large measure configured by network or telephony administrators according to the requirements of their organizations.</span></span>

</div>

<div>

## <a name="exchange-um-routing-component"></a><span data-ttu-id="6f2c3-126">Componente di routing per Messaggistica unificata di Exchange</span><span class="sxs-lookup"><span data-stu-id="6f2c3-126">Exchange UM Routing Component</span></span>

<span data-ttu-id="6f2c3-127">Il componente di routing della messaggistica unificata di Exchange gestisce il routing tra Lync Server e i server che eseguono la messaggistica unificata di Exchange, per integrare Lync Server con le funzionalità di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="6f2c3-127">The Exchange UM routing component handles routing between Lync Server and servers running Exchange Unified Messaging (UM), to integrate Lync Server with Unified Messaging features.</span></span>

<span data-ttu-id="6f2c3-128">Il componente di routing della messaggistica unificata di Exchange gestisce anche il reinstradamento della segreteria telefonica tramite la rete PSTN se i server Messaggistica unificata di Exchange</span><span class="sxs-lookup"><span data-stu-id="6f2c3-128">The Exchange UM routing component also handles rerouting of voice mail over the PSTN if Exchange UM servers are unavailable.</span></span> <span data-ttu-id="6f2c3-129">Se si dispone di utenti di VoIP aziendale nei siti di succursale che non dispongono di un collegamento WAN resiliente a un sito centrale, il Survivable Branch Appliance distribuito nel sito di succursale fornisce la sopravvivenza dei messaggi vocali per gli utenti di succursale durante un'interruzione della rete WAN.</span><span class="sxs-lookup"><span data-stu-id="6f2c3-129">If you have Enterprise Voice users at branch sites that do not have a resilient WAN link to a central site, the Survivable Branch Appliance that you deploy at the branch site provides voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="6f2c3-130">Quando il collegamento WAN non è disponibile, Survivable Branch Appliance effettua le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6f2c3-130">When the WAN link is unavailable, the Survivable Branch Appliance does the following:</span></span>

  - <span data-ttu-id="6f2c3-131">Reinstrada le chiamate senza risposta sulla rete PSTN verso il server di Messaggistica unificata di Exchange nel sito centrale</span><span class="sxs-lookup"><span data-stu-id="6f2c3-131">reroutes unanswered calls over the PSTN to the Exchange Unified Messaging server in the central site</span></span>

  - <span data-ttu-id="6f2c3-132">Consente a un utente di recuperare i messaggi di segreteria telefonica sulla rete PSTN</span><span class="sxs-lookup"><span data-stu-id="6f2c3-132">provides the ability for a user to retrieve voice mail messages over the PSTN</span></span>

  - <span data-ttu-id="6f2c3-133">Accoda le notifiche di chiamate senza risposta e quindi le carica nel server di Messaggistica unificata di Exchange quando viene ripristinato il collegamento WAN</span><span class="sxs-lookup"><span data-stu-id="6f2c3-133">queues missed call notifications, and then uploads them to the Exchange UM server when the WAN link is restored.</span></span>

<span data-ttu-id="6f2c3-134">Per abilitare il rerouting della segreteria telefonica, è consigliabile che l'amministratore di Exchange configuri l'operatore automatico di messaggistica unificata di Exchange per accettare solo i messaggi.</span><span class="sxs-lookup"><span data-stu-id="6f2c3-134">To enable voice mail rerouting, we recommend that your Exchange administrator configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span>

<span data-ttu-id="6f2c3-135">Per informazioni dettagliate su queste funzionalità, vedere [pianificazione dell'integrazione della messaggistica unificata di Exchange in Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) e [pianificazione della resilienza di VoIP aziendale in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md), rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="6f2c3-135">For details about these features, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Planning for Enterprise Voice resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md), respectively.</span></span>

</div>

<div>

## <a name="intercluster-routing-component"></a><span data-ttu-id="6f2c3-136">Componente di routing tra cluster</span><span class="sxs-lookup"><span data-stu-id="6f2c3-136">Intercluster Routing Component</span></span>

<span data-ttu-id="6f2c3-p105">Il componente di routing tra cluster è responsabile del routing delle chiamate al pool di registrazione principale del destinatario della chiamata. Se il pool non è disponibile, il componente instrada la chiamata al pool di registrazione di backup del destinatario della chiamata. Se i pool di registrazione principale e di backup del destinatario della chiamata non sono raggiungibili sulla rete IP, il componente di routing tra cluster reinstrada la chiamata sulla rete PSTN al numero di telefono dell'utente.</span><span class="sxs-lookup"><span data-stu-id="6f2c3-p105">The Intercluster routing component is responsible for routing calls to the callee’s primary Registrar pool. If that is unavailable, the component routes the call to the callee’s backup Registrar pool. If the callee’s primary and backup Registrar pools are unreachable over the IP network, the Intercluster routing component reroutes the call over the PSTN to the user’s telephone number.</span></span>

</div>

<div>

## <a name="other-front-end-server-components-required-for-voip"></a><span data-ttu-id="6f2c3-140">Altri componenti di Front End Server necessari per VoIP</span><span class="sxs-lookup"><span data-stu-id="6f2c3-140">Other Front End Server Components Required for VoIP</span></span>

<span data-ttu-id="6f2c3-141">Gli altri componenti che risiedono nel front end server o nel Director che forniscono un supporto essenziale per VoIP, ma non sono propri componenti VoIP, includono quanto segue:</span><span class="sxs-lookup"><span data-stu-id="6f2c3-141">Other components residing on the Front End Server or Director that provide essential support for VoIP, but are not themselves VoIP components, include the following:</span></span>

  - <span data-ttu-id="6f2c3-142">**Servizi utente.**</span><span class="sxs-lookup"><span data-stu-id="6f2c3-142">**User Services.**</span></span> <span data-ttu-id="6f2c3-143">Consente di eseguire la ricerca inversa nel numero di telefono di destinazione per ogni chiamata in arrivo e di associare tale numero all'URI SIP dell'utente di destinazione.</span><span class="sxs-lookup"><span data-stu-id="6f2c3-143">Perform reverse number lookup on the destination phone number of each incoming call and match that number to the SIP URI of the destination user.</span></span> <span data-ttu-id="6f2c3-144">Queste informazioni vengono usate dal componente di routing in ingresso per distribuire la chiamata agli endpoint SIP registrati dell'utente.</span><span class="sxs-lookup"><span data-stu-id="6f2c3-144">Using this information, the Inbound Routing component distributes the call to that user’s registered SIP endpoints.</span></span> <span data-ttu-id="6f2c3-145">Servizi utente è un componente di base di tutti i Front End Server e direttori.</span><span class="sxs-lookup"><span data-stu-id="6f2c3-145">User Services is a core component on all Front End Servers and Directors.</span></span>

  - <span data-ttu-id="6f2c3-146">**User Replicator.**</span><span class="sxs-lookup"><span data-stu-id="6f2c3-146">**User Replicator.**</span></span> <span data-ttu-id="6f2c3-147">Estrae i numeri di telefono degli utenti da servizi di dominio Active Directory e li scrive nelle tabelle del database RTC, in cui sono disponibili per i servizi utente e per il server della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="6f2c3-147">Extracts user phone numbers from Active Directory Domain Services and writes them to tables in the RTC database, where they are available to User Services and Address Book Server.</span></span> <span data-ttu-id="6f2c3-148">User Replicator è un componente di base di tutti i Front End Server.</span><span class="sxs-lookup"><span data-stu-id="6f2c3-148">User Replicator is a core component on all Front End Servers.</span></span>

  - <span data-ttu-id="6f2c3-149">**Server della Rubrica.**</span><span class="sxs-lookup"><span data-stu-id="6f2c3-149">**Address Book Server.**</span></span> <span data-ttu-id="6f2c3-150">Fornisce informazioni sull'elenco indirizzi globale da servizi di dominio Active Directory ai client di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6f2c3-150">Provides global address list information from Active Directory Domain Services to Lync Server clients.</span></span> <span data-ttu-id="6f2c3-151">Vengono inoltre recuperate le informazioni relative a utenti e contatti dal database RTC, vengono scritte le informazioni nei file della Rubrica e quindi i file vengono archiviati in una cartella condivisa in cui vengono scaricati dai client Lync.</span><span class="sxs-lookup"><span data-stu-id="6f2c3-151">It also retrieves user and contact information from the RTC database, writes the information to the Address Book files, and then stores the files on a shared folder where they are downloaded by Lync clients.</span></span> <span data-ttu-id="6f2c3-152">Il server della Rubrica scrive le informazioni nel database di RTCAb, che viene utilizzato dal servizio di query Web della Rubrica per rispondere alle query di ricerca degli utenti da Microsoft Lync 2010 mobile.</span><span class="sxs-lookup"><span data-stu-id="6f2c3-152">The Address Book Server writes the information to the RTCAb database, which is used by the Address Book Web Query service to respond to user search queries from Microsoft Lync 2010 Mobile.</span></span> <span data-ttu-id="6f2c3-153">Facoltativamente normalizza i numeri di telefono degli utenti dell'organizzazione scritti nel database RTC allo scopo di provisioning dei contatti utente in Lync.</span><span class="sxs-lookup"><span data-stu-id="6f2c3-153">It optionally normalizes enterprise user phone numbers that are written to the RTC database for the purpose of provisioning user contacts in Lync.</span></span> <span data-ttu-id="6f2c3-154">Il servizio Rubrica è installato per impostazione predefinita in tutti i Front End Server.</span><span class="sxs-lookup"><span data-stu-id="6f2c3-154">The Address Book service is installed by default on all Front End Servers.</span></span> <span data-ttu-id="6f2c3-155">Il servizio query Web della Rubrica viene installato per impostazione predefinita con i servizi Web in ogni Front End Server.</span><span class="sxs-lookup"><span data-stu-id="6f2c3-155">The Address Book Web Query service is installed by default with the Web services on each Front End Servers.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

