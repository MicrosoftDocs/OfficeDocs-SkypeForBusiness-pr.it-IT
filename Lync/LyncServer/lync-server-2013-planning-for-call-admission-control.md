---
title: 'Lync Server 2013: Pianificazione del servizio Controllo di ammissione di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for call admission control (CAC)
ms:assetid: ca367138-adf5-4119-bc40-5ddf335ed22f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398842(v=OCS.15)
ms:contentKeyID: 48185652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1af07a3f0b067f4dae3835c682cb51e6fefdcf21
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976158"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="e9369-102">Pianificazione del servizio Controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9369-102">Planning for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9369-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="e9369-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="e9369-104">Per le applicazioni UC (Unified Communications) basate su IP, come la telefonia, il video e la condivisione di applicazioni, la larghezza di banda disponibile delle reti aziendali non viene in genere considerata un fattore limitante all'interno degli ambienti LAN.</span><span class="sxs-lookup"><span data-stu-id="e9369-104">For unified communications (UC) applications that are IP-based, such as telephony, video, and application sharing, the available bandwidth of enterprise networks is not generally considered to be a limiting factor within LAN environments.</span></span> <span data-ttu-id="e9369-105">Tuttavia, nei collegamenti WAN che interconnettono i siti, la larghezza di banda della rete può essere limitata.</span><span class="sxs-lookup"><span data-stu-id="e9369-105">However, on WAN links that interconnect sites, network bandwidth can be limited.</span></span> <span data-ttu-id="e9369-106">Quando un afflusso di traffico di rete esegue l'oversubscription di un collegamento WAN, vengono usati meccanismi correnti come l'accodamento, il buffer e l'eliminazione dei pacchetti per risolvere la congestione.</span><span class="sxs-lookup"><span data-stu-id="e9369-106">When an influx of network traffic oversubscribes a WAN link, current mechanisms such as queuing, buffering, and packet dropping are used to resolve the congestion.</span></span> <span data-ttu-id="e9369-107">Il traffico aggiuntivo viene in genere ritardato finché la congestione della rete non si semplifica o, se necessario, il traffico viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="e9369-107">The extra traffic is typically delayed until the network congestion eases or, if necessary, the traffic is dropped.</span></span> <span data-ttu-id="e9369-108">Per il traffico dati convenzionale in tali situazioni, il client ricevente può recuperare.</span><span class="sxs-lookup"><span data-stu-id="e9369-108">For conventional data traffic in such situations, the receiving client can recover.</span></span> <span data-ttu-id="e9369-109">Per il traffico in tempo reale, ad esempio le comunicazioni unificate, la congestione della rete non può essere risolta in questo modo, perché il traffico delle comunicazioni unificate è sensibile sia alla latenza che alla perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="e9369-109">For real-time traffic such as unified communications, network congestion cannot be resolved in this manner, because the unified communications traffic is sensitive to both latency and packet loss.</span></span> <span data-ttu-id="e9369-110">La congestione della rete WAN può causare una scarsa qualità dell'esperienza (QoE) per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="e9369-110">Congestion on the WAN can result in a poor Quality of Experience (QoE) for users.</span></span> <span data-ttu-id="e9369-111">Per il traffico in tempo reale in condizioni congestionate, è preferibile negare le chiamate piuttosto che ottenere connessioni con qualità scadente.</span><span class="sxs-lookup"><span data-stu-id="e9369-111">For real-time traffic in congested conditions, it is better to deny calls than to provide connections with poor quality.</span></span>

<span data-ttu-id="e9369-112">Il controllo di ammissione di chiamata (CAC) determina se la larghezza di banda della rete è sufficiente per stabilire una sessione in tempo reale di qualità accettabile.</span><span class="sxs-lookup"><span data-stu-id="e9369-112">Call admission control (CAC) determines whether there is sufficient network bandwidth to establish a real-time session of acceptable quality.</span></span> <span data-ttu-id="e9369-113">In Lync Server 2013, CAC controlla il traffico in tempo reale solo per l'audio e il video, ma non influisce sul traffico dei dati.</span><span class="sxs-lookup"><span data-stu-id="e9369-113">In Lync Server 2013, CAC controls real-time traffic only for audio and video, but it does not affect data traffic.</span></span> <span data-ttu-id="e9369-114">Se il percorso WAN predefinito non ha la larghezza di banda necessaria, il CAC può provare a instradare la chiamata tramite un percorso Internet o la rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="e9369-114">If the default WAN path does not have the required bandwidth, CAC can attempt to route the call through an Internet path or the public switched telephone network (PSTN).</span></span> <span data-ttu-id="e9369-115">CAC è disponibile solo in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e9369-115">CAC is available only in Lync Server.</span></span>

<span data-ttu-id="e9369-116">Questa sezione descrive la funzionalità controllo ammissione chiamata e spiega come pianificare il comando CAC.</span><span class="sxs-lookup"><span data-stu-id="e9369-116">This section describes the call admission control functionality and explains how to plan for CAC.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e9369-117">Lync Server include tre funzionalità vocali avanzate per l'organizzazione: controllo di ammissione delle chiamate (CAC), servizi di emergenza (E9-1-1) e bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="e9369-117">Lync Server has three advanced Enterprise Voice features: call admission control (CAC), emergency services (E9-1-1), and media bypass.</span></span> <span data-ttu-id="e9369-118">Per una panoramica delle informazioni sulla pianificazione comuni a tutte e tre queste caratteristiche, vedere <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">impostazioni di rete per le funzionalità vocali avanzate di Enterprise in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e9369-118">For an overview of planning information that is common to all three of these features, see <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network settings for the advanced Enterprise Voice features in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e9369-119">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="e9369-119">In This Section</span></span>

  - [<span data-ttu-id="e9369-120">Panoramica del controllo di ammissione alle chiamate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9369-120">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)

  - [<span data-ttu-id="e9369-121">Definizione dei requisiti dell'organizzazione per il controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9369-121">Defining your requirements for call admission control in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [<span data-ttu-id="e9369-122">Esempio: raccogliere i requisiti per il controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9369-122">Example: Gathering your requirements for call admission control in Lync Server 2013</span></span>](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [<span data-ttu-id="e9369-123">Componenti e topologie per il servizio Controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9369-123">Components and topologies for CAC in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-cac.md)

  - [<span data-ttu-id="e9369-124">Procedure consigliate per il controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9369-124">Best practices for call admission control in Lync Server 2013</span></span>](lync-server-2013-best-practices-for-call-admission-control.md)

  - [<span data-ttu-id="e9369-125">Elenco di controllo di distribuzione per il controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9369-125">Deployment checklist for call admission control in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

