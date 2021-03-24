---
title: Pianificare una coda di chiamate cloud
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Panoramica dell'utilizzo di un operatore automatico cloud con Skype for Business Server 2019.
ms.openlocfilehash: 62731691f4e56c923d2dd8fa6057f244776ec65b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110492"
---
# <a name="plan-cloud-call-queues"></a><span data-ttu-id="865de-103">Pianificare le code delle chiamate cloud</span><span class="sxs-lookup"><span data-stu-id="865de-103">Plan Cloud call queues</span></span>

<span data-ttu-id="865de-104">La coda delle chiamate cloud è un servizio che accetta le chiamate dei clienti, riproduce un messaggio di saluto e quindi le inserisce in una coda di attesa durante la ricerca di un elenco preconfigurato di agenti per rispondere a queste chiamate.</span><span class="sxs-lookup"><span data-stu-id="865de-104">Cloud call queue is a service that accepts customer calls, plays a greeting message, and then places these calls in a wait queue while searching a pre-configured list of agents to answer these calls.</span></span> <span data-ttu-id="865de-105">È possibile definire il set di agenti nelle liste di distribuzione abilitate alla posta o nei gruppi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="865de-105">You can define the set of agents in mail-enabled distribution lists or security groups.</span></span> <span data-ttu-id="865de-106">L'organizzazione può avere una o più code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="865de-106">Your organization can have one or many call queues.</span></span> <span data-ttu-id="865de-107">Le code di chiamata vengono in genere utilizzate in combinazione con gli operatori automatici.</span><span class="sxs-lookup"><span data-stu-id="865de-107">Call queues are usually used in combination with auto attendants.</span></span>

<span data-ttu-id="865de-108">Inoltre, le code delle chiamate cloud possono fornire:</span><span class="sxs-lookup"><span data-stu-id="865de-108">In addition, Cloud call queues can provide:</span></span>

- <span data-ttu-id="865de-109">Musica mentre i chiamanti sono in attesa di attesa</span><span class="sxs-lookup"><span data-stu-id="865de-109">Music while callers are waiting on hold</span></span>
- <span data-ttu-id="865de-110">Impostazioni personalizzate per le opzioni di dimensione massima, timeout e gestione delle chiamate della coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="865de-110">Customized settings for call queue maximum size, timeout, and call handling options</span></span>

<span data-ttu-id="865de-111">A ogni coda di chiamata viene assegnato un **account** di risorsa (vedere [Configurare](configure-onprem-ra.md)gli account delle risorse) nel sistema Skype for Business Server 2019 che verrà collegato direttamente a una coda di chiamata nell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="865de-111">Each call queue is assigned a **resource account** (see [Configure resource accounts](configure-onprem-ra.md)) on your Skype for Business Server 2019 system that will be linked directly to a call queue in the Microsoft Teams admin center.</span></span> <span data-ttu-id="865de-112">Per ulteriori dettagli sulle code di chiamata e sulle opzioni e le funzionalità disponibili per le code di chiamata, vedere Create [a Cloud call queue.](/MicrosoftTeams/create-a-phone-system-call-queue)</span><span class="sxs-lookup"><span data-stu-id="865de-112">See [Create a Cloud call queue](/MicrosoftTeams/create-a-phone-system-call-queue) for more detail on what call queues are and what options and features exist for call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="865de-113">È possibile assegnare più numeri di telefono a una coda di chiamata, ma devono essere numeri di servizio Microsoft, numeri di instradamento diretto o numeri ibridi.</span><span class="sxs-lookup"><span data-stu-id="865de-113">You can assign multiple phone numbers to a call queue, but they must be Microsoft service numbers, Direct Routing numbers, or hybrid numbers.</span></span>

## <a name="requirements"></a><span data-ttu-id="865de-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="865de-114">Requirements</span></span>

<span data-ttu-id="865de-115">I requisiti seguenti presuppongono che Skype for Business Server 2019 sia già stato distribuito in una topologia supportata.</span><span class="sxs-lookup"><span data-stu-id="865de-115">The following requirements assume that you already have Skype for Business Server 2019 deployed in a supported topology.</span></span>  <span data-ttu-id="865de-116">I requisiti dipendono dal proprio scenario:</span><span class="sxs-lookup"><span data-stu-id="865de-116">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="865de-117">Per una nuova configurazione delle code di chiamata cloud, seguire i passaggi descritti in [Configure resource accounts](configure-onprem-ra.md).</span><span class="sxs-lookup"><span data-stu-id="865de-117">For a new configuration of Cloud call queues, follow the steps outlined in [Configure resource accounts](configure-onprem-ra.md).</span></span> <span data-ttu-id="865de-118">Dovrai creare account delle risorse online o in Skype for Business Server 2019 e potrebbe anche essere necessario associare un numero di telefono alla coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="865de-118">You will need to create resource accounts either online or in Skype for Business Server 2019, and you may also need to associate a phone number with the call queue.</span></span>

<span data-ttu-id="865de-119">Oltre ai requisiti indicati in precedenza, è necessario configurare i requisiti seguenti per la connessione al servizio di coda delle chiamate di Microsoft Cloud:</span><span class="sxs-lookup"><span data-stu-id="865de-119">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud call queue service:</span></span>

- <span data-ttu-id="865de-120">Connettività ibrida.</span><span class="sxs-lookup"><span data-stu-id="865de-120">Hybrid connectivity.</span></span> <span data-ttu-id="865de-121">Se è già stato distribuito Skype for Business Server e si desidera abilitare le code di chiamata cloud per gli utenti locali, è necessario assicurarsi di avere configurato la connettività ibrida tra gli ambienti locali e online.</span><span class="sxs-lookup"><span data-stu-id="865de-121">If you already have Skype for Business Server deployed, and you want to enable Cloud call queues for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="865de-122">Questa operazione viene talvolta definita configurazione di dominio diviso.</span><span class="sxs-lookup"><span data-stu-id="865de-122">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="865de-123">Per ulteriori informazioni, vedere Pianificare la connettività ibrida tra Skype for Business Server e [Microsoft 365 o Office 365](plan-hybrid-connectivity.md) e Configurare la connettività ibrida tra Skype for Business Server e [Microsoft 365 o Office 365.](configure-hybrid-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="865de-123">For more information, see [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="865de-124">Se stai assegnando un numero di telefono a un account della risorsa, ora puoi usare la licenza utente virtuale sistema telefonico gratuita.</span><span class="sxs-lookup"><span data-stu-id="865de-124">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="865de-125">In questo modo sono disponibili funzionalità del sistema telefonico per i numeri di telefono a livello dell'organizzazione e consente di creare funzionalità di operatore automatico e coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="865de-125">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

- <span data-ttu-id="865de-126">Creare un account di risorsa [locale](configure-onprem-ra.md) per ogni coda di chiamata e assegnare una licenza e un numero di telefono, se necessario.</span><span class="sxs-lookup"><span data-stu-id="865de-126">Create an on-premises [resource account](configure-onprem-ra.md) for each call queue, and assign a license and phone number if required.</span></span>  

<span data-ttu-id="865de-127">Quando si dispone di una struttura solida che soddisfa le proprie esigenze e di uno script che guida i clienti in modo efficiente, passare a [Configurare gli account delle risorse.](configure-onprem-ra.md)</span><span class="sxs-lookup"><span data-stu-id="865de-127">When you have a solid structure that meets your needs and a script that guides customers efficiently, proceed to  [Configure resource accounts](configure-onprem-ra.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="865de-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="865de-128">See Also</span></span>

[<span data-ttu-id="865de-129">Configurare gli account delle risorse</span><span class="sxs-lookup"><span data-stu-id="865de-129">Configure resource accounts</span></span>](configure-onprem-ra.md)

[<span data-ttu-id="865de-130">Abilitazione della registrazione di prompt personalizzati tramite l'interfaccia telefonica</span><span class="sxs-lookup"><span data-stu-id="865de-130">Enable custom prompt recording using the telephone user interface</span></span>](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[<span data-ttu-id="865de-131">Cosa sono gli operatori automatici cloud?</span><span class="sxs-lookup"><span data-stu-id="865de-131">What are Cloud auto attendants?</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[<span data-ttu-id="865de-132">Configurare un operatore automatico cloud</span><span class="sxs-lookup"><span data-stu-id="865de-132">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[<span data-ttu-id="865de-133">Pianificare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="865de-133">Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](plan-hybrid-connectivity.md)

[<span data-ttu-id="865de-134">Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="865de-134">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](configure-hybrid-connectivity.md)

[<span data-ttu-id="865de-135">Gestire gli account di risorsa in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="865de-135">Manage resource accounts in Microsoft Teams</span></span>](/MicrosoftTeams/manage-resource-accounts)