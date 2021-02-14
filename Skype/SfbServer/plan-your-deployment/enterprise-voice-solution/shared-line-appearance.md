---
title: Pianificare l'aspetto della linea condivisa in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/21/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: Leggere questo argomento per informazioni su come pianificare l'aspetto linea condivisa (SLA) in Skype for Business Server 2015, aggiornamento cumulativo di novembre 2015.
ms.openlocfilehash: d7fa13b36c232e37c79e8509de71b4ac29ceff72
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813346"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="f7bad-103">Pianificare l'aspetto della linea condivisa in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f7bad-103">Plan for Shared Line Appearance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f7bad-104">Leggere questo argomento per informazioni su come pianificare l'aspetto linea condivisa (SLA) in Skype for Business Server 2015, aggiornamento cumulativo di novembre 2015.</span><span class="sxs-lookup"><span data-stu-id="f7bad-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="f7bad-105">L'aspetto linea condivisa è una funzionalità di Skype for Business per la gestione di più chiamate su un numero specifico denominato numero condiviso.</span><span class="sxs-lookup"><span data-stu-id="f7bad-105">Shared Line Appearance is a feature in Skype for Business for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="f7bad-106">Sla can configure any enterprise voice enabled Skype for Business user as a shared number with multiple lines to respond to multiple calls.</span><span class="sxs-lookup"><span data-stu-id="f7bad-106">SLA can configure any enterprise voice enabled Skype for Business user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="f7bad-107">Le chiamate non vengono effettivamente ricevute sul numero condiviso, ma vengono inoltrate agli utenti che fungono da delegati per il numero condiviso.</span><span class="sxs-lookup"><span data-stu-id="f7bad-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="f7bad-108">Uno qualsiasi dei delegati può riprendere la chiamata mentre il resto dei delegati ottiene una notifica sul telefono su chi ha preso la chiamata e quale linea è diventata occupata di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="f7bad-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="f7bad-109">Sia il numero di righe che i delegati sono configurabili per un numero condiviso nel contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="f7bad-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="f7bad-110">Inoltre, le opzioni avanzate, come BusyOption (cosa accade in una situazione in cui tutte le linee sono occupate) e MissedCallOption (nel caso in cui nessuno dei delegati preleva una chiamata), possono anche essere configurate per un numero condiviso.</span><span class="sxs-lookup"><span data-stu-id="f7bad-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>
  
<span data-ttu-id="f7bad-111">Sla is supported only on the following phone devices (it is not supported for Skype for Business clients on computers, mobile phones, or other devices):</span><span class="sxs-lookup"><span data-stu-id="f7bad-111">SLA is supported only on the following phone devices (it is not supported for Skype for Business clients on computers, mobile phones, or other devices):</span></span> 
  
- <span data-ttu-id="f7bad-112">Polycom VVX300 con aggiornamento del firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="f7bad-112">Polycom VVX300 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="f7bad-113">Polycom VVX400 con aggiornamento del firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="f7bad-113">Polycom VVX400 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="f7bad-114">Polycom VVX500 con aggiornamento del firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="f7bad-114">Polycom VVX500 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="f7bad-115">Polycom VVX600 con aggiornamento del firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="f7bad-115">Polycom VVX600 with firmware update 5.4.1</span></span>
    
<span data-ttu-id="f7bad-116">SLA is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span><span class="sxs-lookup"><span data-stu-id="f7bad-116">SLA is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="f7bad-117">Per informazioni sulla distribuzione del contratto di servizio, vedere [Deploy Shared Line Appearance in Skype for Business Server 2015.](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md)</span><span class="sxs-lookup"><span data-stu-id="f7bad-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).</span></span>
  
## <a name="feature-list"></a><span data-ttu-id="f7bad-118">Elenco caratteristiche</span><span class="sxs-lookup"><span data-stu-id="f7bad-118">Feature List</span></span>

<span data-ttu-id="f7bad-119">La configurazione di un gruppo di contratti di servizio consente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f7bad-119">Setting up an SLA group enables the following:</span></span>
  
- <span data-ttu-id="f7bad-120">Tutti i delegati del gruppo possono rispondere alle chiamate in ingresso allo stesso numero condiviso.</span><span class="sxs-lookup"><span data-stu-id="f7bad-120">All delegates in the group can answer inbound calls to the same shared number.</span></span> <span data-ttu-id="f7bad-121">Le chiamate possono essere basate su PSTN o SIP.</span><span class="sxs-lookup"><span data-stu-id="f7bad-121">The calls can be PSTN-based or SIP-based.</span></span>
    
- <span data-ttu-id="f7bad-122">I delegati possono contenere e riprendere le chiamate.</span><span class="sxs-lookup"><span data-stu-id="f7bad-122">Delegates can hold and pick up calls.</span></span>
    
- <span data-ttu-id="f7bad-123">I delegati possono trasferire le chiamate a un numero esterno al gruppo sla.</span><span class="sxs-lookup"><span data-stu-id="f7bad-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>
    
- <span data-ttu-id="f7bad-124">I delegati possono visualizzare il numero di chiamate attualmente presenti nel numero condiviso e visualizzare lo stato di ognuna di queste chiamate.</span><span class="sxs-lookup"><span data-stu-id="f7bad-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>
    
- <span data-ttu-id="f7bad-125">È possibile configurare un numero massimo di chiamate simultanee per il numero condiviso.</span><span class="sxs-lookup"><span data-stu-id="f7bad-125">You can configure a maximum number of concurrent calls for the shared number.</span></span> <span data-ttu-id="f7bad-126">È inoltre possibile impostare la modalità di gestione delle chiamate aggiuntive una volta raggiunto questo valore massimo.</span><span class="sxs-lookup"><span data-stu-id="f7bad-126">You can also set how you want additional calls to be handled after this maximum is reached.</span></span> <span data-ttu-id="f7bad-127">Le chiamate in eccesso possono essere rifiutate con un segnale di occupato, inoltrate a un numero alternativo o inoltrate alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="f7bad-127">Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>
    
- <span data-ttu-id="f7bad-128">È possibile configurare la modalità di gestione delle chiamate senza risposta (chiamate non effettuate dopo un determinato periodo di tempo).</span><span class="sxs-lookup"><span data-stu-id="f7bad-128">You can configure how you want missed calls (calls not picked up after a certain time) to be handled.</span></span> <span data-ttu-id="f7bad-129">Se si abilita la segreteria telefonica per l'identità del gruppo, le chiamate senza risposta passano automaticamente alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="f7bad-129">If you enable voice mail for the group identity, missed calls automatically go to voice mail.</span></span> <span data-ttu-id="f7bad-130">Se la segreteria telefonica non è abilitata per l'identità del gruppo (numero condiviso), è possibile scegliere che le chiamate senza risposta siano rifiutate con un segnale di occupato, inoltrate a un numero alternativo o disconnesse.</span><span class="sxs-lookup"><span data-stu-id="f7bad-130">If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>
    

