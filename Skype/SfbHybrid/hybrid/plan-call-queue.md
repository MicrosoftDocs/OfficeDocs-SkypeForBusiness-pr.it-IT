---
title: Pianificare una coda di chiamata cloud
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Panoramica sull'utilizzo di un operatore automatico cloud con Skype for Business Server 2019.
ms.openlocfilehash: 24a0bba82ef38288f5c96cc7c51ce1bfb88c8f05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735226"
---
# <a name="plan-cloud-call-queues"></a><span data-ttu-id="fb7b6-103">Pianificare le code di chiamata cloud</span><span class="sxs-lookup"><span data-stu-id="fb7b6-103">Plan Cloud call queues</span></span>

<span data-ttu-id="fb7b6-104">La coda di chiamata cloud è un servizio che accetta le chiamate dei clienti, riproduce un messaggio di saluto e quindi inserisce tali chiamate in una coda di attesa durante la ricerca di un elenco di agenti preconfigurato per rispondere alle chiamate.</span><span class="sxs-lookup"><span data-stu-id="fb7b6-104">Cloud call queue is a service that accepts customer calls, plays a greeting message, and then places these calls in a wait queue while searching a pre-configured list of agents to answer these calls.</span></span> <span data-ttu-id="fb7b6-105">È possibile definire il set di agenti nelle liste di distribuzione o nei gruppi di sicurezza abilitati alla posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="fb7b6-105">You can define the set of agents in mail-enabled distribution lists or security groups.</span></span> <span data-ttu-id="fb7b6-106">L'organizzazione può disporre di una o più code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="fb7b6-106">Your organization can have one or many call queues.</span></span> <span data-ttu-id="fb7b6-107">Le code di chiamata vengono in genere utilizzate in combinazione con gli operatori automatici.</span><span class="sxs-lookup"><span data-stu-id="fb7b6-107">Call queues are usually used in combination with auto attendants.</span></span>

<span data-ttu-id="fb7b6-108">Inoltre, le code di chiamata cloud possono fornire:</span><span class="sxs-lookup"><span data-stu-id="fb7b6-108">In addition, Cloud call queues can provide:</span></span>

- <span data-ttu-id="fb7b6-109">Musica durante l'attesa dei chiamanti</span><span class="sxs-lookup"><span data-stu-id="fb7b6-109">Music while callers are waiting on hold</span></span>
- <span data-ttu-id="fb7b6-110">Impostazioni personalizzate per la dimensione massima della coda di chiamata, il timeout e le opzioni di gestione delle chiamate</span><span class="sxs-lookup"><span data-stu-id="fb7b6-110">Customized settings for call queue maximum size, timeout, and call handling options</span></span>

<span data-ttu-id="fb7b6-111">A ogni coda di chiamata viene assegnato un **account risorse** (vedere [Configure Resource accounts](configure-onprem-ra.md)) sul sistema Skype for Business Server 2019 che verrà collegato direttamente a una coda di chiamata nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="fb7b6-111">Each call queue is assigned a **resource account** (see [Configure resource accounts](configure-onprem-ra.md)) on your Skype for Business Server 2019 system that will be linked directly to a call queue in the Microsoft Teams admin center.</span></span> <span data-ttu-id="fb7b6-112">Per ulteriori informazioni sulle code di chiamata, vedere [creare una coda di chiamata cloud](/MicrosoftTeams/create-a-phone-system-call-queue) e quali opzioni e caratteristiche esistono per le code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="fb7b6-112">See [Create a Cloud call queue](/MicrosoftTeams/create-a-phone-system-call-queue) for more detail on what call queues are and what options and features exist for call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="fb7b6-113">È possibile assegnare più numeri di telefono a una coda di chiamata, ma devono essere numeri di servizio Microsoft o numeri ibridi.</span><span class="sxs-lookup"><span data-stu-id="fb7b6-113">You can assign multiple phone numbers to a call queue, but they must be Microsoft service numbers or hybrid numbers.</span></span>

## <a name="requirements"></a><span data-ttu-id="fb7b6-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fb7b6-114">Requirements</span></span>

<span data-ttu-id="fb7b6-115">I requisiti seguenti presumono che si disponga già di Skype for Business Server 2019 distribuito in una topologia supportata.</span><span class="sxs-lookup"><span data-stu-id="fb7b6-115">The following requirements assume that you already have Skype for Business Server 2019 deployed in a supported topology.</span></span>  <span data-ttu-id="fb7b6-116">I requisiti dipendono dallo scenario:</span><span class="sxs-lookup"><span data-stu-id="fb7b6-116">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="fb7b6-117">Per una nuova configurazione delle code di chiamata cloud, seguire i passaggi descritti in [Configure Resource accounts](configure-onprem-ra.md).</span><span class="sxs-lookup"><span data-stu-id="fb7b6-117">For a new configuration of Cloud call queues, follow the steps outlined in [Configure resource accounts](configure-onprem-ra.md).</span></span> <span data-ttu-id="fb7b6-118">Sarà necessario creare gli account delle risorse online o in Skype for Business Server 2019 e potrebbe anche essere necessario associare un numero di telefono alla coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="fb7b6-118">You will need to create resource accounts either online or in Skype for Business Server 2019, and you may also need to associate a phone number with the call queue.</span></span>

<span data-ttu-id="fb7b6-119">Oltre ai requisiti di cui sopra, è necessario configurare i requisiti seguenti per la connessione al servizio code di chiamata Microsoft Cloud:</span><span class="sxs-lookup"><span data-stu-id="fb7b6-119">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud call queue service:</span></span>

- <span data-ttu-id="fb7b6-120">Connettività ibrida.</span><span class="sxs-lookup"><span data-stu-id="fb7b6-120">Hybrid connectivity.</span></span> <span data-ttu-id="fb7b6-121">Se è già stato distribuito Skype for Business Server e si desidera abilitare le code di chiamata cloud per gli utenti locali, è necessario verificare di disporre della connettività ibrida configurata tra gli ambienti locali e online.</span><span class="sxs-lookup"><span data-stu-id="fb7b6-121">If you already have Skype for Business Server deployed, and you want to enable Cloud call queues for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="fb7b6-122">A volte viene chiamata configurazione di un dominio diviso.</span><span class="sxs-lookup"><span data-stu-id="fb7b6-122">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="fb7b6-123">Per ulteriori informazioni, vedere [pianificare la connettività ibrida tra Skype for Business Server e office 365](plan-hybrid-connectivity.md) e [configurare la connettività ibrida tra Skype for Business server e Office 365](configure-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="fb7b6-123">For more information, see [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="fb7b6-124">Se si assegna un numero di telefono a un account delle risorse, è ora possibile utilizzare la licenza per l'utente virtuale del sistema telefonico senza costi.</span><span class="sxs-lookup"><span data-stu-id="fb7b6-124">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="fb7b6-125">Questo fornisce funzionalità del sistema telefonico ai numeri di telefono a livello di organizzazione e consente di creare funzionalità di operatore automatico e coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="fb7b6-125">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

- <span data-ttu-id="fb7b6-126">Creare un [account delle risorse](configure-onprem-ra.md) locale per ogni coda di chiamata e assegnare una licenza e un numero di telefono, se necessario.</span><span class="sxs-lookup"><span data-stu-id="fb7b6-126">Create an on-premises [resource account](configure-onprem-ra.md) for each call queue, and assign a license and phone number if required.</span></span>  

## <a name="additional-planning-resources"></a><span data-ttu-id="fb7b6-127">Risorse di pianificazione aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fb7b6-127">Additional planning resources</span></span>

<span data-ttu-id="fb7b6-128">L'esercitazione intitolata [Small Business example-configurare un operatore automatico](/microsoftteams/tutorial-org-aa) passa attraverso il processo di raccolta di informazioni sulle esigenze degli utenti, la pianificazione di una struttura di operatori automatici e degli utenti (e possibilmente code di chiamata), la scrittura delle istruzioni di menu e l'implementazione del piano nell'interfaccia di amministrazione online.</span><span class="sxs-lookup"><span data-stu-id="fb7b6-128">The tutorial titled [Small business example - Set up an auto attendant](/microsoftteams/tutorial-org-aa) goes through the process of gathering information about user needs, planning a structure of auto attendants and users (and possibly call queues), writing the menu prompts, and implementing the plan in the Online Admin center.</span></span> <span data-ttu-id="fb7b6-129">esaminare l'esercitazione e utilizzare gli esercizi che non è possibile creare il piano.</span><span class="sxs-lookup"><span data-stu-id="fb7b6-129">review the tutorial and use the exercises there t create your plan.</span></span>

<span data-ttu-id="fb7b6-130">Quando si dispone di una struttura solida in grado di soddisfare le proprie esigenze e uno script che guida i clienti in modo efficiente, procedere alla [configurazione degli account delle risorse](configure-onprem-ra.md).</span><span class="sxs-lookup"><span data-stu-id="fb7b6-130">When you have a solid structure that meets your needs and a script that guides customers efficiently, proceed to  [Configure resource accounts](configure-onprem-ra.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fb7b6-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb7b6-131">See Also</span></span>

[<span data-ttu-id="fb7b6-132">Configurare gli account delle risorse</span><span class="sxs-lookup"><span data-stu-id="fb7b6-132">Configure resource accounts</span></span>](configure-onprem-ra.md)

[<span data-ttu-id="fb7b6-133">Abilitazione della registrazione di prompt personalizzati tramite l'interfaccia telefonica</span><span class="sxs-lookup"><span data-stu-id="fb7b6-133">Enable custom prompt recording using the telephone user interface</span></span>](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[<span data-ttu-id="fb7b6-134">Che cosa sono gli operatori automatici cloud?</span><span class="sxs-lookup"><span data-stu-id="fb7b6-134">What are Cloud auto attendants?</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[<span data-ttu-id="fb7b6-135">Configurare un operatore automatico cloud</span><span class="sxs-lookup"><span data-stu-id="fb7b6-135">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[<span data-ttu-id="fb7b6-136">Pianificare la connettività ibrida tra Skype for Business Server e Office 365</span><span class="sxs-lookup"><span data-stu-id="fb7b6-136">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](plan-hybrid-connectivity.md)

[<span data-ttu-id="fb7b6-137">Configurare la connettività ibrida tra Skype for Business Server e Office 365</span><span class="sxs-lookup"><span data-stu-id="fb7b6-137">Configure hybrid connectivity between Skype for Business Server and Office 365</span></span>](configure-hybrid-connectivity.md)

[<span data-ttu-id="fb7b6-138">Gestire gli account delle risorse in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fb7b6-138">Manage resource accounts in Microsoft Teams</span></span>](/MicrosoftTeams/manage-resource-accounts)
