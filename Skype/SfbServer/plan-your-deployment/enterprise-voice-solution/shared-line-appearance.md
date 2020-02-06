---
title: Pianificare l'aspetto della linea condivisa in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Leggere questo argomento per informazioni su come pianificare l'uso di SLA (Shared Line Appearance) in Skype for Business Server 2015, aggiornamento cumulativo di novembre 2015.
ms.openlocfilehash: 14f0f6cbd163ecff42543d3ad57bed0020434cfb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802436"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="2e4d5-103">Pianificare l'aspetto della linea condivisa in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2e4d5-103">Plan for Shared Line Appearance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2e4d5-104">Leggere questo argomento per informazioni su come pianificare l'uso di SLA (Shared Line Appearance) in Skype for Business Server 2015, aggiornamento cumulativo di novembre 2015.</span><span class="sxs-lookup"><span data-stu-id="2e4d5-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="2e4d5-105">L'aspetto delle linee condivise è una funzionalità di Skype for business per la gestione di più chiamate su un numero specifico denominato numero condiviso.</span><span class="sxs-lookup"><span data-stu-id="2e4d5-105">Shared Line Appearance is a feature in Skype for Business for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="2e4d5-106">SLA può configurare qualsiasi utente di Skype for business abilitato per VoIP aziendale come numero condiviso con più linee per rispondere a più chiamate.</span><span class="sxs-lookup"><span data-stu-id="2e4d5-106">SLA can configure any enterprise voice enabled Skype for Business user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="2e4d5-107">Le chiamate non vengono effettivamente ricevute sul numero condiviso, ma vengono inoltrate agli utenti che agiscono come delegati per il numero condiviso.</span><span class="sxs-lookup"><span data-stu-id="2e4d5-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="2e4d5-108">Uno qualsiasi dei delegati può prendere la chiamata mentre il resto dei delegati riceve una notifica al telefono su chi ha ricevuto la chiamata e quale linea si è occupata di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="2e4d5-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="2e4d5-109">Sia il numero di righe che i delegati sono configurabili per un numero condiviso in SLA.</span><span class="sxs-lookup"><span data-stu-id="2e4d5-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="2e4d5-110">Inoltre, le opzioni avanzate, ad esempio BusyOption (cosa succede in una situazione in cui tutte le linee sono occupate) e MissedCallOption (il caso in cui nessuno dei delegati prende una chiamata), possono essere configurate anche per un numero condiviso.</span><span class="sxs-lookup"><span data-stu-id="2e4d5-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>
  
<span data-ttu-id="2e4d5-111">SLA è supportato solo nei dispositivi telefonici seguenti (non è supportato per i client Skype for business su computer, telefoni cellulari o altri dispositivi):</span><span class="sxs-lookup"><span data-stu-id="2e4d5-111">SLA is supported only on the following phone devices (it is not supported for Skype for Business clients on computers, mobile phones, or other devices):</span></span> 
  
- <span data-ttu-id="2e4d5-112">Polycom VVX300 con aggiornamento firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="2e4d5-112">Polycom VVX300 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="2e4d5-113">Polycom VVX400 con aggiornamento firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="2e4d5-113">Polycom VVX400 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="2e4d5-114">Polycom VVX500 con aggiornamento firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="2e4d5-114">Polycom VVX500 with firmware update 5.4.1</span></span>
    
- <span data-ttu-id="2e4d5-115">Polycom VVX600 con aggiornamento firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="2e4d5-115">Polycom VVX600 with firmware update 5.4.1</span></span>
    
<span data-ttu-id="2e4d5-116">SLA è una nuova funzionalità in Skype for Business Server, aggiornamento cumulativo di novembre 2015.</span><span class="sxs-lookup"><span data-stu-id="2e4d5-116">SLA is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> 
  
<span data-ttu-id="2e4d5-117">Per informazioni sulla distribuzione di SLA, vedere [distribuire l'aspetto delle linee condivise in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="2e4d5-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).</span></span>
  
## <a name="feature-list"></a><span data-ttu-id="2e4d5-118">Elenco delle caratteristiche</span><span class="sxs-lookup"><span data-stu-id="2e4d5-118">Feature List</span></span>

<span data-ttu-id="2e4d5-119">La configurazione di un gruppo di SLA consente la seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="2e4d5-119">Setting up an SLA group enables the following:</span></span>
  
- <span data-ttu-id="2e4d5-120">Tutti i delegati del gruppo possono rispondere alle chiamate in ingresso allo stesso numero condiviso.</span><span class="sxs-lookup"><span data-stu-id="2e4d5-120">All delegates in the group can answer inbound calls to the same shared number.</span></span> <span data-ttu-id="2e4d5-121">Le chiamate possono essere basate su PSTN o SIP.</span><span class="sxs-lookup"><span data-stu-id="2e4d5-121">The calls can be PSTN-based or SIP-based.</span></span>
    
- <span data-ttu-id="2e4d5-122">I delegati possono tenere e ritirare le chiamate.</span><span class="sxs-lookup"><span data-stu-id="2e4d5-122">Delegates can hold and pick up calls.</span></span>
    
- <span data-ttu-id="2e4d5-123">I delegati possono trasferire le chiamate a un numero esterno al gruppo SLA.</span><span class="sxs-lookup"><span data-stu-id="2e4d5-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>
    
- <span data-ttu-id="2e4d5-124">I delegati possono vedere quante chiamate sono attualmente sul numero condiviso e visualizzare lo stato di ognuna di queste chiamate.</span><span class="sxs-lookup"><span data-stu-id="2e4d5-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>
    
- <span data-ttu-id="2e4d5-125">Puoi configurare un numero massimo di chiamate simultanee per il numero condiviso.</span><span class="sxs-lookup"><span data-stu-id="2e4d5-125">You can configure a maximum number of concurrent calls for the shared number.</span></span> <span data-ttu-id="2e4d5-126">È anche possibile impostare la modalità di gestione delle chiamate aggiuntive dopo il raggiungimento del massimo.</span><span class="sxs-lookup"><span data-stu-id="2e4d5-126">You can also set how you want additional calls to be handled after this maximum is reached.</span></span> <span data-ttu-id="2e4d5-127">Le chiamate in eccesso possono essere rifiutate con un segnale di occupato, inoltrato a un numero alternativo oppure inoltrato alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="2e4d5-127">Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>
    
- <span data-ttu-id="2e4d5-128">È possibile configurare la modalità di gestione delle chiamate perse (le chiamate non vengono raccolte dopo un determinato periodo di tempo).</span><span class="sxs-lookup"><span data-stu-id="2e4d5-128">You can configure how you want missed calls (calls not picked up after a certain time) to be handled.</span></span> <span data-ttu-id="2e4d5-129">Se si Abilita la segreteria telefonica per l'identità del gruppo, le chiamate perse vengono automaticamente inoltrate alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="2e4d5-129">If you enable voice mail for the group identity, missed calls automatically go to voice mail.</span></span> <span data-ttu-id="2e4d5-130">Se non si dispone della segreteria telefonica abilitata per l'identità del gruppo (numero condiviso), è possibile scegliere di rifiutare le chiamate perse con un segnale di occupato, inoltrato a un numero alternativo o disconnesso.</span><span class="sxs-lookup"><span data-stu-id="2e4d5-130">If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>
    

