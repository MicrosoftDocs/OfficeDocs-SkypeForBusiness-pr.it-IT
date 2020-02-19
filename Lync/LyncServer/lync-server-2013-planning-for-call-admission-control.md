---
title: 'Lync Server 2013: pianificazione del controllo di ammissione di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for call admission control (CAC)
ms:assetid: ca367138-adf5-4119-bc40-5ddf335ed22f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398842(v=OCS.15)
ms:contentKeyID: 48185652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c89b289158b36aa811e09e9db628850693dac5a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139909"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="22451-102">Pianificazione del controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22451-102">Planning for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22451-103">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="22451-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="22451-p101">Per le applicazioni per comunicazioni unificate basate sul protocollo IP, ad esempio la telefonia, le comunicazioni video e la condivisione di applicazioni, la larghezza di banda disponibile delle reti aziendali non è considerata generalmente un fattore di limitazione negli ambienti LAN. Nei collegamenti WAN tra i siti tuttavia la larghezza di banda della rete può essere limitata. Quando si verifica un eccesso di sottoscrizione di un collegamento WAN da parte del traffico di rete, per risolvere il problema di congestione vengono utilizzati i meccanismi correnti, ad esempio l'accodamento, il buffering e l'eliminazione dei pacchetti. Il traffico in eccesso in genere viene ritardato finché non si risolve la congestione di rete o, se necessario, finché non viene eliminato il traffico. Per il traffico di dati convenzionali, in questi casi è possibile ripristinare il client di ricezione. Per il traffico in tempo reale, ad esempio le comunicazioni unificate, non è possibile risolvere la congestione in questo modo, poiché questo tipo di traffico è sensibile sia alla latenza che alla perdita di pacchetti. La congestione nella WAN può determinare una qualità percepita dagli utenti (QoE) scadente. Per il traffico in tempo reale in condizioni di congestione, è meglio rifiutare le chiamate anziché consentire connessioni di qualità scadente.</span><span class="sxs-lookup"><span data-stu-id="22451-p101">For unified communications (UC) applications that are IP-based, such as telephony, video, and application sharing, the available bandwidth of enterprise networks is not generally considered to be a limiting factor within LAN environments. However, on WAN links that interconnect sites, network bandwidth can be limited. When an influx of network traffic oversubscribes a WAN link, current mechanisms such as queuing, buffering, and packet dropping are used to resolve the congestion. The extra traffic is typically delayed until the network congestion eases or, if necessary, the traffic is dropped. For conventional data traffic in such situations, the receiving client can recover. For real-time traffic such as unified communications, network congestion cannot be resolved in this manner, because the unified communications traffic is sensitive to both latency and packet loss. Congestion on the WAN can result in a poor Quality of Experience (QoE) for users. For real-time traffic in congested conditions, it is better to deny calls than to provide connections with poor quality.</span></span>

<span data-ttu-id="22451-112">Il Servizio Controllo di ammissione di chiamata determina se è disponibile una larghezza di banda di rete sufficiente per stabilire una sessione in tempo reale di qualità accettabile.</span><span class="sxs-lookup"><span data-stu-id="22451-112">Call admission control (CAC) determines whether there is sufficient network bandwidth to establish a real-time session of acceptable quality.</span></span> <span data-ttu-id="22451-113">In Lync Server 2013, CAC controlla il traffico in tempo reale solo per l'audio e il video, ma non influisce sul traffico dei dati.</span><span class="sxs-lookup"><span data-stu-id="22451-113">In Lync Server 2013, CAC controls real-time traffic only for audio and video, but it does not affect data traffic.</span></span> <span data-ttu-id="22451-114">Se il percorso WAN predefinito non dispone della larghezza di banda necessaria, il servizio Controllo di ammissione di chiamata può tentare di instradare la chiamata tramite un percorso Internet o la rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="22451-114">If the default WAN path does not have the required bandwidth, CAC can attempt to route the call through an Internet path or the public switched telephone network (PSTN).</span></span> <span data-ttu-id="22451-115">Il servizio di controllo di ammissione è disponibile solo in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="22451-115">CAC is available only in Lync Server.</span></span>

<span data-ttu-id="22451-116">In questa sezione viene descritta la funzionalità di Controllo di ammissione di chiamata e viene illustrata la relativa pianificazione.</span><span class="sxs-lookup"><span data-stu-id="22451-116">This section describes the call admission control functionality and explains how to plan for CAC.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="22451-117">Lync Server dispone di tre funzionalità di VoIP aziendale avanzate: controllo di ammissione di chiamata (CAC), servizi di emergenza (E9-1-1) e bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="22451-117">Lync Server has three advanced Enterprise Voice features: call admission control (CAC), emergency services (E9-1-1), and media bypass.</span></span> <span data-ttu-id="22451-118">Per una panoramica delle informazioni di pianificazione comuni a tutte e tre queste caratteristiche, vedere <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">impostazioni di rete per le funzionalità di VoIP aziendale avanzate in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="22451-118">For an overview of planning information that is common to all three of these features, see <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network settings for the advanced Enterprise Voice features in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="22451-119">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="22451-119">In This Section</span></span>

  - [<span data-ttu-id="22451-120">Panoramica del controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22451-120">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)

  - [<span data-ttu-id="22451-121">Definizione dei requisiti per il controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22451-121">Defining your requirements for call admission control in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [<span data-ttu-id="22451-122">Esempio: raccolta dei requisiti per il controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22451-122">Example: Gathering your requirements for call admission control in Lync Server 2013</span></span>](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [<span data-ttu-id="22451-123">Componenti e topologie per il servizio di controllo di ammissione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22451-123">Components and topologies for CAC in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-cac.md)

  - [<span data-ttu-id="22451-124">Procedure consigliate per il controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22451-124">Best practices for call admission control in Lync Server 2013</span></span>](lync-server-2013-best-practices-for-call-admission-control.md)

  - [<span data-ttu-id="22451-125">Checklist di distribuzione per il controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22451-125">Deployment checklist for call admission control in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

