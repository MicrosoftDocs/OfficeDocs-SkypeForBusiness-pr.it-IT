---
title: "Lync Server 2013: pianificare l'aspetto delle linee condivise"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Shared Line Appearance
ms:assetid: a35c83d8-f531-445b-a8d2-d5d8cec77c6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712151(v=OCS.15)
ms:contentKeyID: 72522136
ms.date: 03/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef6bb768ca892aa684613d1261d88266237ab111
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a><span data-ttu-id="04a34-102">Pianificare l'aspetto delle linee condivise in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04a34-102">Plan for Shared Line Appearance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04a34-103">_**Ultimo argomento modificato:** 2016-03-21_</span><span class="sxs-lookup"><span data-stu-id="04a34-103">_**Topic Last Modified:** 2016-03-21_</span></span>

<span data-ttu-id="04a34-104">Leggere questo argomento per informazioni su come effettuare la pianificazione di SLA (Shared Line Appearance) in Lync Server 2013, aggiornamento cumulativo aprile 2016.</span><span class="sxs-lookup"><span data-stu-id="04a34-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="04a34-105">L'aspetto delle linee condivise è una funzionalità di Lync Server 2013, aggiornamento cumulativo di aprile 2016 per la gestione di più chiamate su un numero specifico denominato numero condiviso.</span><span class="sxs-lookup"><span data-stu-id="04a34-105">Shared Line Appearance is a feature in Lync Server 2013, Cumulative Update April 2016 for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="04a34-106">SLA è in grado di configurare qualsiasi utente Lync abilitato per VoIP aziendale come numero condiviso con più righe per rispondere a più chiamate.</span><span class="sxs-lookup"><span data-stu-id="04a34-106">SLA can configure any enterprise voice enabled Lync user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="04a34-107">Le chiamate non vengono effettivamente ricevute sul numero condiviso, ma vengono inoltrate agli utenti che agiscono come delegati per il numero condiviso.</span><span class="sxs-lookup"><span data-stu-id="04a34-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="04a34-108">Uno qualsiasi dei delegati può prendere la chiamata mentre il resto dei delegati riceve una notifica sul telefono di chi ha ricevuto la chiamata e quale linea si è occupata di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="04a34-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="04a34-109">Sia il numero di righe che i delegati sono configurabili per un numero condiviso in SLA.</span><span class="sxs-lookup"><span data-stu-id="04a34-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="04a34-110">Inoltre, le opzioni avanzate, come BusyOption (cosa succede in una situazione in cui tutte le linee sono occupate) e MissedCallOption (il caso in cui nessuno dei delegati prelevare una chiamata), possono essere configurate anche per un numero condiviso.</span><span class="sxs-lookup"><span data-stu-id="04a34-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>

<span data-ttu-id="04a34-111">SLA è supportato solo sui seguenti dispositivi telefonici (non è supportato per i client Lync su computer, telefoni cellulari o altri dispositivi):</span><span class="sxs-lookup"><span data-stu-id="04a34-111">SLA is supported only on the following phone devices (it is not supported for Lync clients on computers, mobile phones, or other devices):</span></span>

  - <span data-ttu-id="04a34-112">Polycom VVX300 with Firmware Update 5.4.1</span><span class="sxs-lookup"><span data-stu-id="04a34-112">Polycom VVX300 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="04a34-113">Polycom VVX400 with Firmware Update 5.4.1</span><span class="sxs-lookup"><span data-stu-id="04a34-113">Polycom VVX400 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="04a34-114">Polycom VVX500 with Firmware Update 5.4.1</span><span class="sxs-lookup"><span data-stu-id="04a34-114">Polycom VVX500 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="04a34-115">Polycom VVX600 with Firmware Update 5.4.1</span><span class="sxs-lookup"><span data-stu-id="04a34-115">Polycom VVX600 with firmware update 5.4.1</span></span>

<span data-ttu-id="04a34-116">SLA è una nuova funzionalità di Lync Server 2013, aggiornamento cumulativo aprile 2016.</span><span class="sxs-lookup"><span data-stu-id="04a34-116">SLA is a new feature in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="04a34-117">Per informazioni sulla distribuzione di SLA, vedere [deploy Shared Line Appearance in Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="04a34-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).</span></span>

<div>

## <a name="feature-list"></a><span data-ttu-id="04a34-118">Elenco funzionalità</span><span class="sxs-lookup"><span data-stu-id="04a34-118">Feature List</span></span>

<span data-ttu-id="04a34-119">La configurazione di un gruppo di SLA consente di abilitare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="04a34-119">Setting up an SLA group enables the following:</span></span>

  - <span data-ttu-id="04a34-120">Tutti i delegati del gruppo possono rispondere alle chiamate in ingresso allo stesso numero condiviso.</span><span class="sxs-lookup"><span data-stu-id="04a34-120">All delegates in the group can answer inbound calls to the same shared number.</span></span> <span data-ttu-id="04a34-121">Le chiamate possono essere basate su PSTN o SIP.</span><span class="sxs-lookup"><span data-stu-id="04a34-121">The calls can be PSTN-based or SIP-based.</span></span>

  - <span data-ttu-id="04a34-122">I delegati possono conservare e raccogliere le chiamate.</span><span class="sxs-lookup"><span data-stu-id="04a34-122">Delegates can hold and pick up calls.</span></span>

  - <span data-ttu-id="04a34-123">I delegati possono trasferire le chiamate a un numero esterno al gruppo di SLA.</span><span class="sxs-lookup"><span data-stu-id="04a34-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>

  - <span data-ttu-id="04a34-124">I delegati possono vedere quante chiamate sono attualmente sul numero condiviso e visualizzare lo stato di ognuna di queste chiamate.</span><span class="sxs-lookup"><span data-stu-id="04a34-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>

  - <span data-ttu-id="04a34-125">È possibile configurare un numero massimo di chiamate simultanee per il numero condiviso.</span><span class="sxs-lookup"><span data-stu-id="04a34-125">You can configure a maximum number of concurrent calls for the shared number.</span></span> <span data-ttu-id="04a34-126">È inoltre possibile impostare il modo in cui si desidera che vengano gestite altre chiamate dopo che è stato raggiunto il limite massimo.</span><span class="sxs-lookup"><span data-stu-id="04a34-126">You can also set how you want additional calls to be handled after this maximum is reached.</span></span> <span data-ttu-id="04a34-127">Le chiamate in eccesso possono essere rifiutate con un segnale di occupato, inoltrate a un numero alternativo o inoltrate alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="04a34-127">Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>

  - <span data-ttu-id="04a34-128">È possibile configurare la modalità di gestione delle chiamate senza risposta (chiamate non ritirate dopo un determinato periodo di tempo).</span><span class="sxs-lookup"><span data-stu-id="04a34-128">You can configure how you want missed calls (calls not picked up after a certain time) to be handled.</span></span> <span data-ttu-id="04a34-129">Se si Abilita la segreteria telefonica per l'identità del gruppo, le chiamate perse passano automaticamente alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="04a34-129">If you enable voice mail for the group identity, missed calls automatically go to voice mail.</span></span> <span data-ttu-id="04a34-130">Se non si dispone della segreteria telefonica abilitata per l'identità del gruppo (numero condiviso), è possibile scegliere se le chiamate perse devono essere rifiutate con un segnale di occupato, inoltrato a un numero alternativo o disconnesso.</span><span class="sxs-lookup"><span data-stu-id="04a34-130">If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

