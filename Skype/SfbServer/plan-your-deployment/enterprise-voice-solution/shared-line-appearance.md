---
title: Pianificare l'aspetto della linea condivisa in Skype for Business Server 2015
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
description: Leggere questo argomento per informazioni su come effettuare la pianificazione di SLA (Shared Line Appearance) in Skype for Business Server 2015, novembre 2015 Cumulative Update.
ms.openlocfilehash: d7fa13b36c232e37c79e8509de71b4ac29ceff72
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813346"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="87d6f-103">Pianificare l'aspetto della linea condivisa in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="87d6f-103">Plan for Shared Line Appearance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="87d6f-104">Leggere questo argomento per informazioni su come effettuare la pianificazione di SLA (Shared Line Appearance) in Skype for Business Server 2015, novembre 2015 Cumulative Update.</span><span class="sxs-lookup"><span data-stu-id="87d6f-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="87d6f-105">L'aspetto della linea condivisa è una funzionalità di Skype for business per la gestione di più chiamate su un numero specifico denominato numero condiviso.</span><span class="sxs-lookup"><span data-stu-id="87d6f-105">Shared Line Appearance is a feature in Skype for Business for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="87d6f-106">SLA è in grado di configurare qualsiasi utente di Skype for business abilitato VoIP aziendale come numero condiviso con più righe per rispondere a più chiamate.</span><span class="sxs-lookup"><span data-stu-id="87d6f-106">SLA can configure any enterprise voice enabled Skype for Business user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="87d6f-107">Le chiamate non vengono effettivamente ricevute sul numero condiviso, ma vengono inoltrate agli utenti che agiscono come delegati per il numero condiviso.</span><span class="sxs-lookup"><span data-stu-id="87d6f-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="87d6f-108">Uno qualsiasi dei delegati può prendere la chiamata mentre il resto dei delegati riceve una notifica sul telefono di chi ha ricevuto la chiamata e quale linea si è occupata di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="87d6f-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="87d6f-109">Sia il numero di righe che i delegati sono configurabili per un numero condiviso in SLA.</span><span class="sxs-lookup"><span data-stu-id="87d6f-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="87d6f-110">Inoltre, le opzioni avanzate, come BusyOption (cosa succede in una situazione in cui tutte le linee sono occupate) e MissedCallOption (il caso in cui nessuno dei delegati prelevare una chiamata), possono essere configurate anche per un numero condiviso.</span><span class="sxs-lookup"><span data-stu-id="87d6f-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>
  
<span data-ttu-id="87d6f-111">SLA è supportato solo sui seguenti dispositivi telefonici (non è supportato per i client Skype for business su computer, telefoni cellulari o altri dispositivi):</span><span class="sxs-lookup"><span data-stu-id="87d6f-111">SLA is supported only on the following phone devices (it is not supported for Skype for Business clients on computers, mobile phones, or other devices):</span></span> 
  
- <span data-ttu-id="87d6f-112">Polycom VVX300 with Firmware Update 5.4.1</span><span class="sxs-lookup"><span data-stu-id="87d6f-112">Polycom VVX300 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="87d6f-113">Polycom VVX400 with Firmware Update 5.4.1</span><span class="sxs-lookup"><span data-stu-id="87d6f-113">Polycom VVX400 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="87d6f-114">Polycom VVX500 with Firmware Update 5.4.1</span><span class="sxs-lookup"><span data-stu-id="87d6f-114">Polycom VVX500 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="87d6f-115">Polycom VVX600 with Firmware Update 5.4.1</span><span class="sxs-lookup"><span data-stu-id="87d6f-115">Polycom VVX600 with firmware update 5.4.1</span></span>
    
<span data-ttu-id="87d6f-116">SLA è una nuova funzionalità in Skype for Business Server, novembre 2015 aggiornamento cumulativo.</span><span class="sxs-lookup"><span data-stu-id="87d6f-116">SLA is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="87d6f-117">Per informazioni sulla distribuzione di SLA, vedere [deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="87d6f-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).</span></span>
  
## <a name="feature-list"></a><span data-ttu-id="87d6f-118">Elenco funzionalità</span><span class="sxs-lookup"><span data-stu-id="87d6f-118">Feature List</span></span>

<span data-ttu-id="87d6f-119">La configurazione di un gruppo di SLA consente di abilitare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="87d6f-119">Setting up an SLA group enables the following:</span></span>
  
- <span data-ttu-id="87d6f-120">Tutti i delegati del gruppo possono rispondere alle chiamate in ingresso allo stesso numero condiviso.</span><span class="sxs-lookup"><span data-stu-id="87d6f-120">All delegates in the group can answer inbound calls to the same shared number.</span></span> <span data-ttu-id="87d6f-121">Le chiamate possono essere basate su PSTN o SIP.</span><span class="sxs-lookup"><span data-stu-id="87d6f-121">The calls can be PSTN-based or SIP-based.</span></span>
    
- <span data-ttu-id="87d6f-122">I delegati possono conservare e raccogliere le chiamate.</span><span class="sxs-lookup"><span data-stu-id="87d6f-122">Delegates can hold and pick up calls.</span></span>
    
- <span data-ttu-id="87d6f-123">I delegati possono trasferire le chiamate a un numero esterno al gruppo di SLA.</span><span class="sxs-lookup"><span data-stu-id="87d6f-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>
    
- <span data-ttu-id="87d6f-124">I delegati possono vedere quante chiamate sono attualmente sul numero condiviso e visualizzare lo stato di ognuna di queste chiamate.</span><span class="sxs-lookup"><span data-stu-id="87d6f-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>
    
- <span data-ttu-id="87d6f-125">È possibile configurare un numero massimo di chiamate simultanee per il numero condiviso.</span><span class="sxs-lookup"><span data-stu-id="87d6f-125">You can configure a maximum number of concurrent calls for the shared number.</span></span> <span data-ttu-id="87d6f-126">È inoltre possibile impostare il modo in cui si desidera che vengano gestite altre chiamate dopo che è stato raggiunto il limite massimo.</span><span class="sxs-lookup"><span data-stu-id="87d6f-126">You can also set how you want additional calls to be handled after this maximum is reached.</span></span> <span data-ttu-id="87d6f-127">Le chiamate in eccesso possono essere rifiutate con un segnale di occupato, inoltrate a un numero alternativo o inoltrate alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="87d6f-127">Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>
    
- <span data-ttu-id="87d6f-128">È possibile configurare la modalità di gestione delle chiamate senza risposta (chiamate non ritirate dopo un determinato periodo di tempo).</span><span class="sxs-lookup"><span data-stu-id="87d6f-128">You can configure how you want missed calls (calls not picked up after a certain time) to be handled.</span></span> <span data-ttu-id="87d6f-129">Se si Abilita la segreteria telefonica per l'identità del gruppo, le chiamate perse passano automaticamente alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="87d6f-129">If you enable voice mail for the group identity, missed calls automatically go to voice mail.</span></span> <span data-ttu-id="87d6f-130">Se non si dispone della segreteria telefonica abilitata per l'identità del gruppo (numero condiviso), è possibile scegliere se le chiamate perse devono essere rifiutate con un segnale di occupato, inoltrato a un numero alternativo o disconnesso.</span><span class="sxs-lookup"><span data-stu-id="87d6f-130">If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>
    

