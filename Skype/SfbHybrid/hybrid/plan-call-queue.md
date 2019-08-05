---
title: Pianificare una coda di chiamata cloud
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Panoramica dell'uso di un operatore automatico cloud con Skype for Business Server 2019.
ms.openlocfilehash: bcb1f14ed9dfc3471b146a318a97700c362f115c
ms.sourcegitcommit: 868db85f0126e8f56d711ea590ad44acce8f96f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2019
ms.locfileid: "36185543"
---
# <a name="plan-cloud-call-queues"></a><span data-ttu-id="dfe97-103">Pianificare le code delle chiamate cloud</span><span class="sxs-lookup"><span data-stu-id="dfe97-103">Plan Cloud call queues</span></span>

<span data-ttu-id="dfe97-104">La coda delle chiamate cloud è un servizio che accetta le chiamate dei clienti, riproduce un messaggio di saluto e quindi inserisce queste chiamate in una coda di attesa durante la ricerca di un elenco preconfigurato di agenti per rispondere a queste chiamate.</span><span class="sxs-lookup"><span data-stu-id="dfe97-104">Cloud call queue is a service that accepts customer calls, plays a greeting message, and then places these calls in a wait queue while searching a pre-configured list of agents to answer these calls.</span></span> <span data-ttu-id="dfe97-105">Puoi definire il set di agenti in liste di distribuzione o gruppi di sicurezza abilitati alla posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="dfe97-105">You can define the set of agents in mail-enabled distribution lists or security groups.</span></span> <span data-ttu-id="dfe97-106">L'organizzazione può avere una o più code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="dfe97-106">Your organization can have one or many call queues.</span></span> <span data-ttu-id="dfe97-107">Le code di chiamata vengono in genere usate in combinazione con gli operatori automatici.</span><span class="sxs-lookup"><span data-stu-id="dfe97-107">Call queues are usually used in combination with auto attendants.</span></span>

<span data-ttu-id="dfe97-108">Inoltre, le code delle chiamate cloud possono prevedere:</span><span class="sxs-lookup"><span data-stu-id="dfe97-108">In addition, Cloud call queues can provide:</span></span>

- <span data-ttu-id="dfe97-109">Musica quando i chiamanti attendono il blocco</span><span class="sxs-lookup"><span data-stu-id="dfe97-109">Music while callers are waiting on hold</span></span>
- <span data-ttu-id="dfe97-110">Impostazioni personalizzate per le opzioni di gestione delle chiamate e delle dimensioni massime della coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="dfe97-110">Customized settings for call queue maximum size, timeout, and call handling options</span></span>

<span data-ttu-id="dfe97-111">A ogni coda di chiamata viene assegnato un **account di risorse** (vedere [configurare gli account delle risorse](configure-onprem-ra.md)) nel sistema Skype for Business Server 2019 che verrà collegato direttamente a una coda di chiamata nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="dfe97-111">Each call queue is assigned a **resource account** (see [Configure resource accounts](configure-onprem-ra.md)) on your Skype for Business Server 2019 system that will be linked directly to a call queue in the Microsoft Teams admin center.</span></span> <span data-ttu-id="dfe97-112">Per altre informazioni sulle code di chiamata, vedere [creare una coda di chiamata cloud](/MicrosoftTeams/create-a-phone-system-call-queue) e quali sono le opzioni e le funzionalità disponibili per le code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="dfe97-112">See [Create a Cloud call queue](/MicrosoftTeams/create-a-phone-system-call-queue) for more detail on what call queues are and what options and features exist for call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="dfe97-113">È possibile assegnare più numeri di telefono a una coda di chiamata, ma devono essere numeri di servizio Microsoft o numeri ibridi.</span><span class="sxs-lookup"><span data-stu-id="dfe97-113">You can assign multiple phone numbers to a call queue, but they must be Microsoft service numbers or hybrid numbers.</span></span>

## <a name="requirements"></a><span data-ttu-id="dfe97-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dfe97-114">Requirements</span></span>

<span data-ttu-id="dfe97-115">I requisiti seguenti presuppongono che si disponga già di Skype for Business Server 2019 distribuito in una topologia supportata.</span><span class="sxs-lookup"><span data-stu-id="dfe97-115">The following requirements assume that you already have Skype for Business Server 2019 deployed in a supported topology.</span></span>  <span data-ttu-id="dfe97-116">I requisiti dipendono dallo scenario:</span><span class="sxs-lookup"><span data-stu-id="dfe97-116">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="dfe97-117">Per una nuova configurazione delle code di chiamata cloud, seguire i passaggi descritti in configurare gli [account risorse](configure-onprem-ra.md).</span><span class="sxs-lookup"><span data-stu-id="dfe97-117">For a new configuration of Cloud call queues, follow the steps outlined in [Configure resource accounts](configure-onprem-ra.md).</span></span> <span data-ttu-id="dfe97-118">Sarà necessario creare gli account delle risorse online o in Skype for Business Server 2019 e potrebbe essere necessario associare un numero di telefono alla coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="dfe97-118">You will need to create resource accounts either online or in Skype for Business Server 2019, and you may also need to associate a phone number with the call queue.</span></span>

<span data-ttu-id="dfe97-119">Oltre ai requisiti descritti sopra, i requisiti seguenti devono essere configurati per la connessione al servizio code di chiamata Microsoft Cloud:</span><span class="sxs-lookup"><span data-stu-id="dfe97-119">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud call queue service:</span></span>

- <span data-ttu-id="dfe97-120">Connettività ibrida.</span><span class="sxs-lookup"><span data-stu-id="dfe97-120">Hybrid connectivity.</span></span> <span data-ttu-id="dfe97-121">Se è già stato implementato Skype for Business Server e si vogliono abilitare le code di chiamata cloud per gli utenti locali, è necessario assicurarsi di avere configurato la connettività ibrida tra gli ambienti locali e online.</span><span class="sxs-lookup"><span data-stu-id="dfe97-121">If you already have Skype for Business Server deployed, and you want to enable Cloud call queues for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="dfe97-122">Questa operazione viene talvolta definita configurazione di domini divisi.</span><span class="sxs-lookup"><span data-stu-id="dfe97-122">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="dfe97-123">Per altre informazioni, vedere [pianificare la connettività ibrida tra Skype for Business Server e office 365](plan-hybrid-connectivity.md) e [configurare la connettività ibrida tra Skype for Business server e Office 365](configure-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="dfe97-123">For more information, see [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="dfe97-124">Se si sta assegnando un numero di telefono a un account di risorse, è ora possibile usare la licenza per gli utenti virtuali del sistema telefonico senza costi.</span><span class="sxs-lookup"><span data-stu-id="dfe97-124">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="dfe97-125">In questo modo le funzionalità del sistema telefonico sono disponibili per i numeri di telefono a livello di organizzazione e consentono di creare funzionalità di operatore automatico e coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="dfe97-125">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

- <span data-ttu-id="dfe97-126">Creare un [account di risorse](configure-onprem-ra.md) locale per ogni coda di chiamata e assegnare una licenza e un numero di telefono, se necessario.</span><span class="sxs-lookup"><span data-stu-id="dfe97-126">Create an on-premises [resource account](configure-onprem-ra.md) for each call queue, and assign a license and phone number if required.</span></span>  

## <a name="additional-planning-resources"></a><span data-ttu-id="dfe97-127">Risorse di pianificazione aggiuntive</span><span class="sxs-lookup"><span data-stu-id="dfe97-127">Additional planning resources</span></span>

<span data-ttu-id="dfe97-128">Esempio di esercitazione intitolato [Small Business-configurare un operatore automatico](/microsoftteams/tutorial-org-aa) durante il processo di raccolta di informazioni sulle esigenze degli utenti, la pianificazione di una struttura di operatori automatici e gli utenti (e possibilmente le code di chiamata), la scrittura delle istruzioni del menu e implementazione del piano nell'interfaccia di amministrazione online.</span><span class="sxs-lookup"><span data-stu-id="dfe97-128">The tutorial titled [Small business example - Set up an auto attendant](/microsoftteams/tutorial-org-aa) goes through the process of gathering information about user needs, planning a structure of auto attendants and users (and possibly call queues), writing the menu prompts, and implementing the plan in the Online Admin center.</span></span> <span data-ttu-id="dfe97-129">esaminare l'esercitazione e usare gli esercizi che non creano il piano.</span><span class="sxs-lookup"><span data-stu-id="dfe97-129">review the tutorial and use the exercises there t create your plan.</span></span>

<span data-ttu-id="dfe97-130">Quando si ha una struttura solida che soddisfa le proprie esigenze e uno script che guida in modo efficiente i clienti, procedere alla [configurazione degli account delle risorse](configure-onprem-ra.md).</span><span class="sxs-lookup"><span data-stu-id="dfe97-130">When you have a solid structure that meets your needs and a script that guides customers efficiently, proceed to  [Configure resource accounts](configure-onprem-ra.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dfe97-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dfe97-131">See Also</span></span>

[<span data-ttu-id="dfe97-132">Configurare gli account delle risorse</span><span class="sxs-lookup"><span data-stu-id="dfe97-132">Configure resource accounts</span></span>](configure-onprem-ra.md)

[<span data-ttu-id="dfe97-133">Abilitare la registrazione di una richiesta personalizzata con l'interfaccia utente telefonica</span><span class="sxs-lookup"><span data-stu-id="dfe97-133">Enable custom prompt recording using the telephone user interface</span></span>](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[<span data-ttu-id="dfe97-134">Cosa sono gli operatori automatici cloud?</span><span class="sxs-lookup"><span data-stu-id="dfe97-134">What are Cloud auto attendants?</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[<span data-ttu-id="dfe97-135">Configurare un operatore automatico cloud</span><span class="sxs-lookup"><span data-stu-id="dfe97-135">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[<span data-ttu-id="dfe97-136">Pianificare la connettività ibrida tra Skype for Business Server e Office 365</span><span class="sxs-lookup"><span data-stu-id="dfe97-136">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](plan-hybrid-connectivity.md)

[<span data-ttu-id="dfe97-137">Configurare la connettività ibrida tra Skype for Business Server e Office 365</span><span class="sxs-lookup"><span data-stu-id="dfe97-137">Configure hybrid connectivity between Skype for Business Server and Office 365</span></span>](configure-hybrid-connectivity.md)

[<span data-ttu-id="dfe97-138">Gestire gli account delle risorse in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dfe97-138">Manage resource accounts in Microsoft Teams</span></span>](/MicrosoftTeams/manage-resource-accounts)
