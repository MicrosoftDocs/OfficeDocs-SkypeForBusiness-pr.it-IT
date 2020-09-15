---
title: Rispondere alle chiamate all'operatore automatico e alla coda di chiamata
ms.reviewer: waseemh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: Descrive gli operatori automatici del cloud e le code di chiamata e spiega come rispondere alle chiamate in teams.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 95719bc95cc752888964a5f404e6f8050ebf3fa4
ms.sourcegitcommit: 67c686810d37bffda72a6e92155d9c8ec86bfae6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2020
ms.locfileid: "47766860"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a><span data-ttu-id="c69de-103">Rispondere alle chiamate degli operatori automatici e delle code delle chiamate direttamente da Teams</span><span class="sxs-lookup"><span data-stu-id="c69de-103">Answer auto attendant and call queue calls directly from Teams</span></span>
===========================================================

<span data-ttu-id="c69de-104">Gli utenti del team possono ricevere e rispondere alle chiamate dagli operatori automatici del cloud e chiamare le code direttamente dal client teams.</span><span class="sxs-lookup"><span data-stu-id="c69de-104">Teams users can receive and answer calls from Cloud auto attendants and call queues directly from their Teams client.</span></span>

## <a name="what-are-auto-attendants-and-call-queues"></a><span data-ttu-id="c69de-105">Cosa sono gli operatori automatici e le code di chiamata?</span><span class="sxs-lookup"><span data-stu-id="c69de-105">What are auto attendants and call queues?</span></span>

<span data-ttu-id="c69de-106">Gli operatori automatici Cloud includono una serie di richieste vocali o un file audio che i chiamanti sentono al posto di un operatore umano quando chiamano un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c69de-106">Cloud auto attendants provide a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization.</span></span> <span data-ttu-id="c69de-107">L'operatore automatico consente ai chiamanti di spostarsi nel sistema di menu, effettuare chiamate o individuare utenti mediante tastiera a toni DTMF (Dual Tone Multi-Frequency) o input vocali con riconoscimento vocale.</span><span class="sxs-lookup"><span data-stu-id="c69de-107">An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span>

<span data-ttu-id="c69de-108">Le code delle chiamate Cloud includono i messaggi di saluto usati quando qualcuno chiama un numero di telefono per l'organizzazione, la possibilità di inserire automaticamente le chiamate in attesa e la possibilità di cercare l'agente di chiamata disponibile per gestire la chiamata mentre le persone che chiamano ascoltano musica in attesa.</span><span class="sxs-lookup"><span data-stu-id="c69de-108">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="c69de-109">È possibile creare code di chiamata singole o multiple per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c69de-109">You can create single or multiple call queues for your organization.</span></span>

## <a name="handling-an-auto-attendant-or-call-queue-call"></a><span data-ttu-id="c69de-110">Gestione di una chiamata tramite operatore automatico o coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="c69de-110">Handling an auto attendant or call queue call</span></span>

<span data-ttu-id="c69de-111">Gli utenti potranno distinguere le chiamate in arrivo da un operatore automatico o da una coda di chiamata prima di rispondere alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="c69de-111">Users will be able to differentiate incoming calls from an auto attendant or call queue before they answer the call.</span></span> <span data-ttu-id="c69de-112">Insieme al nome e/o al numero del chiamante, ogni chiamata includerà informazioni su chi il chiamante stava provando a raggiungere, offrendo agli utenti un contesto migliore per l'indirizzamento del chiamante.</span><span class="sxs-lookup"><span data-stu-id="c69de-112">Along with the name and/or number of the caller, each call will include information about who the caller was trying to reach, giving users a better context for addressing the caller.</span></span>

<span data-ttu-id="c69de-113">La figura seguente mostra come verrà visualizzata una chiamata in arrivo da un operatore automatico o da una coda di chiamata a un utente.</span><span class="sxs-lookup"><span data-stu-id="c69de-113">The following illustration shows how an incoming call from an auto attendant or call queue will appear to a user.</span></span>

![Schermata di una notifica di chiamata in arrivo](media/answer-auto-attendant-and-call-queue-calls-image1.png)

<span data-ttu-id="c69de-115">Una volta risolta una chiamata tramite operatore automatico o coda di chiamata, l'utente può elaborare la chiamata come qualsiasi altra chiamata &#x2014; può aggiungere o effettuare una conferenza in un altro utente o trasferire la chiamata a un'altra persona.</span><span class="sxs-lookup"><span data-stu-id="c69de-115">Once an auto attendant or call queue call is answered, the user can process the call like any other call &#x2014; they can add or conference in another user or transfer the call to another party.</span></span> <span data-ttu-id="c69de-116">Inoltre, le chiamate all'operatore automatico verranno inoltrate in base alla configurazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c69de-116">Also, auto attendant calls will be forwarded based on the user's configuration.</span></span>

> [!NOTE] 
> <span data-ttu-id="c69de-117">Le chiamate delle code di chiamata non vengono inoltrate in base alla configurazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c69de-117">Call queue calls are not forwarded based on the user's configuration.</span></span> <span data-ttu-id="c69de-118">In questo modo, i chiamanti rimarranno nella coda finché un agente non può rispondere alla chiamata e il chiamante non viene inoltrato inaspettatamente.</span><span class="sxs-lookup"><span data-stu-id="c69de-118">This is to ensure callers remain in the queue until an agent can answer the call and the caller isn't forwarded unexpectedly.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="c69de-119">Client supportati</span><span class="sxs-lookup"><span data-stu-id="c69de-119">Supported clients</span></span>

<span data-ttu-id="c69de-120">Il supporto per le chiamate all'operatore automatico e alla coda di chiamata è disponibile nei client seguenti:</span><span class="sxs-lookup"><span data-stu-id="c69de-120">Support for auto attendant and call queue calls is available in the following clients:</span></span>

-    <span data-ttu-id="c69de-121">Client Microsoft Teams Windows (versioni a 32 e 64 bit)</span><span class="sxs-lookup"><span data-stu-id="c69de-121">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>
-    <span data-ttu-id="c69de-122">Client Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="c69de-122">Microsoft Teams Mac client</span></span>
-    <span data-ttu-id="c69de-123">App per iPhone di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c69de-123">Microsoft Teams iPhone app</span></span>
-    <span data-ttu-id="c69de-124">App Microsoft teams Android</span><span class="sxs-lookup"><span data-stu-id="c69de-124">Microsoft Teams Android app</span></span>

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a><span data-ttu-id="c69de-125">Configurare l'operatore automatico e il supporto delle code di chiamata per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c69de-125">Configure auto attendant and call queue support for Microsoft Teams</span></span>

<span data-ttu-id="c69de-126">Per ricevere le chiamate all'operatore automatico e alla coda di chiamata in Microsoft teams, è necessario configurare i criteri di interoperabilità e i criteri di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="c69de-126">To receive auto attendant and call queue calls on Microsoft Teams, you need to configure your interoperability policy and upgrade policy.</span></span> <span data-ttu-id="c69de-127">Verificare [la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="c69de-127">Please review [Migration and interoperability for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span> <span data-ttu-id="c69de-128">Se non si dispone di un operatore automatico e/o di una coda di chiamata configurata e si desidera eseguire questa operazione, vedere [configurare un operatore automatico cloud](create-a-phone-system-auto-attendant.md) e [creare una coda di chiamata cloud](create-a-phone-system-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="c69de-128">If you do not have auto attendant and/or call queue configured and would like to do so, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md) and [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="c69de-129">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="c69de-129">Known Issues</span></span>

<span data-ttu-id="c69de-130">Quando gli agenti della coda di chiamata ricevono una chiamata sul dispositivo mobile, le chiamate possono continuare a essere bloccate se il dispositivo è bloccato.</span><span class="sxs-lookup"><span data-stu-id="c69de-130">When a call queue agents receives a call on their mobile device, calls may go on hold if the device is locked.</span></span> <span data-ttu-id="c69de-131">L'utente deve sbloccare prima il dispositivo e quindi rispondere alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="c69de-131">User must unlock device first and then answer the call.</span></span>


## <a name="related-topics"></a><span data-ttu-id="c69de-132">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="c69de-132">Related topics</span></span>

-    [<span data-ttu-id="c69de-133">Che cos'è il sistema telefonico in Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="c69de-133">What is Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
-    [<span data-ttu-id="c69de-134">Creare una coda di chiamata cloud</span><span class="sxs-lookup"><span data-stu-id="c69de-134">Create a Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
-    [<span data-ttu-id="c69de-135">Cosa sono gli operatori automatici cloud?</span><span class="sxs-lookup"><span data-stu-id="c69de-135">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)
-    [<span data-ttu-id="c69de-136">Configurare un operatore automatico cloud</span><span class="sxs-lookup"><span data-stu-id="c69de-136">Set up a Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

