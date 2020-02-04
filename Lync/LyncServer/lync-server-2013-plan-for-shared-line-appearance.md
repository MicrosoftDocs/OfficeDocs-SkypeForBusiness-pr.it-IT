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
ms.openlocfilehash: 755bff84b8902e346135139d1c8c5b26c55605c1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a><span data-ttu-id="52067-102">Pianificare l'aspetto della linea condivisa in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52067-102">Plan for Shared Line Appearance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52067-103">_**Argomento Ultima modifica:** 2016-03-21_</span><span class="sxs-lookup"><span data-stu-id="52067-103">_**Topic Last Modified:** 2016-03-21_</span></span>

<span data-ttu-id="52067-104">Leggere questo argomento per informazioni su come pianificare l'aspetto della linea condivisa (SLA) in Lync Server 2013, aggiornamento cumulativo aprile 2016.</span><span class="sxs-lookup"><span data-stu-id="52067-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="52067-105">L'aspetto delle linee condivise è una funzionalità di Lync Server 2013, aggiornamento cumulativo aprile 2016 per la gestione di più chiamate su un numero specifico denominato numero condiviso.</span><span class="sxs-lookup"><span data-stu-id="52067-105">Shared Line Appearance is a feature in Lync Server 2013, Cumulative Update April 2016 for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="52067-106">SLA può configurare un utente di Lync abilitato per VoIP aziendale come numero condiviso con più linee per rispondere a più chiamate.</span><span class="sxs-lookup"><span data-stu-id="52067-106">SLA can configure any enterprise voice enabled Lync user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="52067-107">Le chiamate non vengono effettivamente ricevute sul numero condiviso, ma vengono inoltrate agli utenti che agiscono come delegati per il numero condiviso.</span><span class="sxs-lookup"><span data-stu-id="52067-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="52067-108">Uno qualsiasi dei delegati può prendere la chiamata mentre il resto dei delegati riceve una notifica al telefono su chi ha ricevuto la chiamata e quale linea si è occupata di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="52067-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="52067-109">Sia il numero di righe che i delegati sono configurabili per un numero condiviso in SLA.</span><span class="sxs-lookup"><span data-stu-id="52067-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="52067-110">Inoltre, le opzioni avanzate, ad esempio BusyOption (cosa succede in una situazione in cui tutte le linee sono occupate) e MissedCallOption (il caso in cui nessuno dei delegati prende una chiamata), possono essere configurate anche per un numero condiviso.</span><span class="sxs-lookup"><span data-stu-id="52067-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>

<span data-ttu-id="52067-111">SLA è supportato solo nei dispositivi telefonici seguenti (non è supportato per i client Lync su computer, telefoni cellulari o altri dispositivi):</span><span class="sxs-lookup"><span data-stu-id="52067-111">SLA is supported only on the following phone devices (it is not supported for Lync clients on computers, mobile phones, or other devices):</span></span>

  - <span data-ttu-id="52067-112">Polycom VVX300 con aggiornamento firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="52067-112">Polycom VVX300 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="52067-113">Polycom VVX400 con aggiornamento firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="52067-113">Polycom VVX400 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="52067-114">Polycom VVX500 con aggiornamento firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="52067-114">Polycom VVX500 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="52067-115">Polycom VVX600 con aggiornamento firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="52067-115">Polycom VVX600 with firmware update 5.4.1</span></span>

<span data-ttu-id="52067-116">SLA è una nuova funzionalità di Lync Server 2013, aggiornamento cumulativo aprile 2016.</span><span class="sxs-lookup"><span data-stu-id="52067-116">SLA is a new feature in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="52067-117">Per informazioni sulla distribuzione di SLA, vedere [distribuire l'aspetto delle linee condivise in Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="52067-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).</span></span>

<div>

## <a name="feature-list"></a><span data-ttu-id="52067-118">Elenco delle caratteristiche</span><span class="sxs-lookup"><span data-stu-id="52067-118">Feature List</span></span>

<span data-ttu-id="52067-119">La configurazione di un gruppo di SLA consente la seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="52067-119">Setting up an SLA group enables the following:</span></span>

  - <span data-ttu-id="52067-120">Tutti i delegati del gruppo possono rispondere alle chiamate in ingresso allo stesso numero condiviso.</span><span class="sxs-lookup"><span data-stu-id="52067-120">All delegates in the group can answer inbound calls to the same shared number.</span></span> <span data-ttu-id="52067-121">Le chiamate possono essere basate su PSTN o SIP.</span><span class="sxs-lookup"><span data-stu-id="52067-121">The calls can be PSTN-based or SIP-based.</span></span>

  - <span data-ttu-id="52067-122">I delegati possono tenere e ritirare le chiamate.</span><span class="sxs-lookup"><span data-stu-id="52067-122">Delegates can hold and pick up calls.</span></span>

  - <span data-ttu-id="52067-123">I delegati possono trasferire le chiamate a un numero esterno al gruppo SLA.</span><span class="sxs-lookup"><span data-stu-id="52067-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>

  - <span data-ttu-id="52067-124">I delegati possono vedere quante chiamate sono attualmente sul numero condiviso e visualizzare lo stato di ognuna di queste chiamate.</span><span class="sxs-lookup"><span data-stu-id="52067-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>

  - <span data-ttu-id="52067-125">Puoi configurare un numero massimo di chiamate simultanee per il numero condiviso.</span><span class="sxs-lookup"><span data-stu-id="52067-125">You can configure a maximum number of concurrent calls for the shared number.</span></span> <span data-ttu-id="52067-126">È anche possibile impostare la modalità di gestione delle chiamate aggiuntive dopo il raggiungimento del massimo.</span><span class="sxs-lookup"><span data-stu-id="52067-126">You can also set how you want additional calls to be handled after this maximum is reached.</span></span> <span data-ttu-id="52067-127">Le chiamate in eccesso possono essere rifiutate con un segnale di occupato, inoltrato a un numero alternativo oppure inoltrato alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="52067-127">Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>

  - <span data-ttu-id="52067-128">È possibile configurare la modalità di gestione delle chiamate perse (le chiamate non vengono raccolte dopo un determinato periodo di tempo).</span><span class="sxs-lookup"><span data-stu-id="52067-128">You can configure how you want missed calls (calls not picked up after a certain time) to be handled.</span></span> <span data-ttu-id="52067-129">Se si Abilita la segreteria telefonica per l'identità del gruppo, le chiamate perse vengono automaticamente inoltrate alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="52067-129">If you enable voice mail for the group identity, missed calls automatically go to voice mail.</span></span> <span data-ttu-id="52067-130">Se non si dispone della segreteria telefonica abilitata per l'identità del gruppo (numero condiviso), è possibile scegliere di rifiutare le chiamate perse con un segnale di occupato, inoltrato a un numero alternativo o disconnesso.</span><span class="sxs-lookup"><span data-stu-id="52067-130">If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

