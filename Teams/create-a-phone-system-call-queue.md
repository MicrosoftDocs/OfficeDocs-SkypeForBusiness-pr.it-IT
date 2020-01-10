---
title: Creare una coda di chiamata
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: phans, wasseemh
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.callqueues.overview"
ms.custom:
- Phone System
description: Informazioni su come configurare il sistema telefonico per le code delle chiamate cloud con Microsoft teams.
ms.openlocfilehash: 95cf9701705950d997e1d200fee117b5f8f9738b
ms.sourcegitcommit: 2fab6105dfc4c225de8c09ab79d9c2c273a3e4f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/10/2020
ms.locfileid: "41005182"
---
# <a name="create-a-cloud-call-queue"></a><span data-ttu-id="afcff-103">Creare una coda delle chiamate nel cloud</span><span class="sxs-lookup"><span data-stu-id="afcff-103">Create a Cloud call queue</span></span>

<span data-ttu-id="afcff-104">Le code delle chiamate cloud possono essere fornite:</span><span class="sxs-lookup"><span data-stu-id="afcff-104">Cloud call queues can provide:</span></span>

- <span data-ttu-id="afcff-105">Messaggio di saluto.</span><span class="sxs-lookup"><span data-stu-id="afcff-105">A greeting message.</span></span>
- <span data-ttu-id="afcff-106">Musica mentre le persone sono in attesa.</span><span class="sxs-lookup"><span data-stu-id="afcff-106">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="afcff-107">Reindirizzamento delle chiamate per chiamare gli agenti in liste di distribuzione via mail e gruppi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="afcff-107">Redirecting calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="afcff-108">Impostazione di parametri diversi, ad esempio la dimensione massima della coda, il timeout e le opzioni di gestione delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="afcff-108">Setting different parameters such as queue maximum size, timeout, and call handling options.</span></span>
- <span data-ttu-id="afcff-109">Segreteria telefonica condivisa per i chiamanti per l'uscita di un messaggio per un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="afcff-109">Shared voicemail for callers to leave a message for an organization.</span></span>

<span data-ttu-id="afcff-110">Per associare un numero di telefono a una coda di chiamata, è possibile usare un [account di risorse](manage-resource-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="afcff-110">You would associate a phone number to a call queue using a [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="afcff-111">Una coda di chiamata può essere chiamata direttamente o accessibile tramite una selezione in un operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="afcff-111">A call queue can be dialed directly or accessed by a selection on an auto attendant.</span></span>

<span data-ttu-id="afcff-112">Il chiamante sente la musica mentre è in attesa e la chiamata si connette agli agenti di chiamata in ordine *First in, First out* (FIFO).</span><span class="sxs-lookup"><span data-stu-id="afcff-112">The caller hears music while they are on hold, and the call connects to the call agents in *First In, First Out* (FIFO) order.</span></span>

<span data-ttu-id="afcff-113">Tutte le chiamate nella coda vengono inviate agli agenti da uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="afcff-113">All calls in the queue are sent to agents by one of the following methods:</span></span>

- <span data-ttu-id="afcff-114">Con il routing di Attendant, la prima chiamata nella coda squilla tutti gli agenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="afcff-114">With attendant routing, the first call in the queue  rings all agents at the same time.</span></span>
- <span data-ttu-id="afcff-115">Con il routing seriale, la prima chiamata nella coda squilla tutti gli agenti di chiamata uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="afcff-115">With serial routing, the first call in the queue rings all call agents one by one.</span></span>
- <span data-ttu-id="afcff-116">Con Round Robin, il routing delle chiamate in arrivo è bilanciato in modo che ogni agente di chiamata ottenga lo stesso numero di chiamate dalla coda.</span><span class="sxs-lookup"><span data-stu-id="afcff-116">With round robin, routing of incoming calls is balanced so that each call agent gets the same number of calls from the queue.</span></span>

    > [!NOTE]
    > <span data-ttu-id="afcff-117">Gli agenti di chiamata **offline**, hanno impostato la loro presenza su non **disturbare** o hanno scelto di non ricevere chiamate nella coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="afcff-117">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue will not recieve calls.</span></span>

- <span data-ttu-id="afcff-118">Solo una notifica di chiamata in arrivo (per la chiamata a capo della coda) alla volta passa agli agenti di chiamata.</span><span class="sxs-lookup"><span data-stu-id="afcff-118">Only one incoming call notification (for the call at the head of the queue) at a time goes to the call agents.</span></span>
- <span data-ttu-id="afcff-119">Una volta che un agente di chiamata accetta la chiamata, la prossima chiamata in arrivo in coda viene segnalata agli agenti di chiamata.</span><span class="sxs-lookup"><span data-stu-id="afcff-119">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="afcff-120">Questo articolo si applica sia a Microsoft teams che a Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="afcff-120">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="afcff-121">Passaggio 1: iniziare</span><span class="sxs-lookup"><span data-stu-id="afcff-121">Step 1 — Get started</span></span>

<span data-ttu-id="afcff-122">Per iniziare a utilizzare le code di chiamata, è importante ricordare quanto segue.</span><span class="sxs-lookup"><span data-stu-id="afcff-122">To get started using call queues, it's important to remember a few things:</span></span>

- <span data-ttu-id="afcff-123">È necessaria una coda di chiamata per avere un account di risorse associato.</span><span class="sxs-lookup"><span data-stu-id="afcff-123">A call queue is required to have an associated resource account.</span></span> <span data-ttu-id="afcff-124">Per informazioni dettagliate sugli account delle risorse, vedere [gestire gli account delle risorse in teams](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="afcff-124">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="afcff-125">Quando si assegna un numero di telefono a un account delle risorse, è ora possibile usare la licenza per gli [utenti virtuali](teams-add-on-licensing/virtual-user.md)del sistema telefonico senza costi.</span><span class="sxs-lookup"><span data-stu-id="afcff-125">When you assign a phone number to a resource account, you can now use the cost-free Phone System [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span> <span data-ttu-id="afcff-126">Sistema telefonico consente di usare i numeri di telefono a livello di organizzazione per l'operatore automatico a basso costo e i servizi di Accodamento chiamate.</span><span class="sxs-lookup"><span data-stu-id="afcff-126">Phone System allows phone numbers at the organizational level for use with low-cost auto attendant and call queue services.</span></span>

> [!NOTE]
> <span data-ttu-id="afcff-127">I numeri di servizio di routing diretto per le code di chiamata sono supportati solo per gli utenti e gli agenti di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="afcff-127">Direct Routing service numbers for call queues are supported for Microsoft Teams users and agents only.</span></span>

> [!NOTE]
> <span data-ttu-id="afcff-128">Per reindirizzare le chiamate alle persone dell'organizzazione online, devono avere una licenza per il **sistema telefonico** e essere abilitate per VoIP aziendale o avere piani di chiamata di Office 365.</span><span class="sxs-lookup"><span data-stu-id="afcff-128">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="afcff-129">Vedere [assegnare licenze di Skype for business](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) o [assegnare licenze di Microsoft teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="afcff-129">See [Assign Skype for Business licenses](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="afcff-130">Per abilitare VoIP aziendale, è possibile utilizzare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="afcff-130">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="afcff-131">Ad esempio, Esegui:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="afcff-131">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="afcff-132">Per altre informazioni sui piani di chiamate di Office 365, vedere [sistemi di telefonia e](calling-plan-landing-page.md) piani di chiamata e [piani di chiamata per Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="afcff-132">To learn more about Office 365 Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

- <span data-ttu-id="afcff-133">È possibile assegnare solo i numeri di telefono a pedaggio e numero verde delle code di chiamate cloud disponibili nell'interfaccia di **amministrazione di Microsoft teams** o trasferiti da un altro provider di servizi.</span><span class="sxs-lookup"><span data-stu-id="afcff-133">You can only assign Cloud call queues toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider.</span></span> <span data-ttu-id="afcff-134">I crediti per le comunicazioni sono necessari per i numeri di servizio gratuiti.</span><span class="sxs-lookup"><span data-stu-id="afcff-134">Communications Credits are required for toll-free service numbers.</span></span>

    > [!NOTE]
    > <span data-ttu-id="afcff-135">I numeri di telefono di utenti (abbonati) non possono essere assegnati a code di chiamata, ma solo numeri di telefono di servizio a pagamento o numeri verdi.</span><span class="sxs-lookup"><span data-stu-id="afcff-135">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>

- <span data-ttu-id="afcff-136">I client seguenti sono supportati per gli agenti di chiamata associati a una coda di chiamata cloud:</span><span class="sxs-lookup"><span data-stu-id="afcff-136">The following clients are supported for call agents associated to a Cloud call queue:</span></span>

  - <span data-ttu-id="afcff-137">Client desktop Skype for business 2016 (versioni 32 e 64 bit)</span><span class="sxs-lookup"><span data-stu-id="afcff-137">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="afcff-138">Client desktop Lync 2013 (versioni 32 e 64 bit)</span><span class="sxs-lookup"><span data-stu-id="afcff-138">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="afcff-139">Tutti i modelli di telefono IP supportati per Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="afcff-139">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="afcff-140">Vedere [ottenere telefoni per Skype for business online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="afcff-140">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>

  - <span data-ttu-id="afcff-141">Client Mac Skype for Business (versione 16.8.196 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="afcff-141">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="afcff-142">Client Android Skype for Business (versione 6.16.0.9 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="afcff-142">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="afcff-143">Client iPhone Skype for Business (versione 6.16.0 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="afcff-143">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="afcff-144">Client Mac Skype for Business (versione 6.16.0 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="afcff-144">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="afcff-145">Client Windows Microsoft Teams (versioni a 32 bit e 64 bit)</span><span class="sxs-lookup"><span data-stu-id="afcff-145">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="afcff-146">Client Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="afcff-146">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="afcff-147">App per iPhone di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="afcff-147">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="afcff-148">App Microsoft teams Android</span><span class="sxs-lookup"><span data-stu-id="afcff-148">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="afcff-149">Le code di chiamata assegnate a un numero di routing diretto non supportano i client di Skype for business, i client Lync o i telefoni IP Skype for business come agenti.</span><span class="sxs-lookup"><span data-stu-id="afcff-149">Call queues that are assigned a direct routing number will not support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span> 

## <a name="step-2--getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="afcff-150">Passaggio 2: ottenere o trasferire numeri di telefono del servizio a pagamento o a numero verde</span><span class="sxs-lookup"><span data-stu-id="afcff-150">Step 2 — Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="afcff-151">Prima di poter creare e configurare le code di chiamata, è necessario ottenere o trasferire i numeri di servizio a pagamento o a pedaggio esistenti.</span><span class="sxs-lookup"><span data-stu-id="afcff-151">Before you can create and set up your call queues, you need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="afcff-152">Dopo aver ottenuto il numero di telefono o i numeri di servizio gratuiti, verranno visualizzati nei**numeri** > di telefono della**segreteria** > telefonica di **Microsoft teams** > **Add** > e il **tipo di numero** verrà elencato come **servizio, senza numero verde**.</span><span class="sxs-lookup"><span data-stu-id="afcff-152">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers** > **ADD** >, and the **Number type** will be listed as **Service — Toll-Free**.</span></span> <span data-ttu-id="afcff-153">Per ottenere i numeri di servizio, vedere [recupero di numeri di telefono](getting-service-phone-numbers.md) o se si vuole trasferire un numero di servizio esistente, vedere trasferire i [numeri di telefono in Office 365](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="afcff-153">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="afcff-154">Se si è al di fuori degli Stati Uniti, non è possibile usare l'interfaccia di amministrazione di Microsoft teams per ottenere i numeri di servizio.</span><span class="sxs-lookup"><span data-stu-id="afcff-154">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="afcff-155">Vai a [gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) per vedere come farlo dall'esterno degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="afcff-155">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="afcff-156">Quando si configura più operatori automatici, è possibile assegnare un numero di telefono solo all'account delle risorse dell'operatore automatico principale, che può indirizzare i chiamanti alle code di chiamata o agli operatori automatici annidati.</span><span class="sxs-lookup"><span data-stu-id="afcff-156">When setting up multiple auto attendants you may only assign a phone number to the main auto attendant's resource account, which can direct callers to your call queues or nested auto attendants.</span></span> <span data-ttu-id="afcff-157">In questi casi, è possibile creare tutti gli operatori automatici e le code di chiamata nel sistema senza assegnare le opzioni del tastierino e quindi modificare le impostazioni in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="afcff-157">In those situations, you create all auto attendants and call queues in your system without assigning dialpad options, and then edit the settings later.</span></span> <span data-ttu-id="afcff-158">Questa operazione è necessaria perché non è consentito creare un'opzione che collega a una coda di chiamata o a un operatore automatico che non esiste ancora.</span><span class="sxs-lookup"><span data-stu-id="afcff-158">This is necessary because you aren't allowed to create an option linking to a call queue or auto attendant that does not yet exist.</span></span>

## <a name="step-3--create-a-new-call-queue"></a><span data-ttu-id="afcff-159">Passaggio 3: creare una nuova coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="afcff-159">Step 3 — Create a new call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="afcff-160">Ogni coda di chiamata è necessaria per avere un [account di risorse](manage-resource-accounts.md)associato.</span><span class="sxs-lookup"><span data-stu-id="afcff-160">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="afcff-161">Devi prima creare l'account della risorsa, quindi puoi associarlo alla coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="afcff-161">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="afcff-162">Uso dell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="afcff-162">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="afcff-163">Nell'interfaccia di **amministrazione di Microsoft teams**,**code di chiamata** **vocale** > , quindi fare clic su **+ Aggiungi nuovo**:</span><span class="sxs-lookup"><span data-stu-id="afcff-163">In the **Microsoft Teams admin center**, **Voice** > **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-call-queue-display-name-and-resource-account"></a><span data-ttu-id="afcff-164">Impostare il nome visualizzato della coda di chiamata e l'account delle risorse</span><span class="sxs-lookup"><span data-stu-id="afcff-164">Set the call queue display name and resource account</span></span>

![Screenshot di una nuova coda di chiamata, con callout numerati](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="afcff-166">![Icona del numero 1, facendo riferimento a un callout nel](media/sfbcallout1.png)
**nome** dello screenshot precedente immettere un nome visualizzato descrittivo per la coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="afcff-166">![Icon of the number 1, referencing a callout in the previous screenshot](media/sfbcallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="afcff-167">Questo nome è obbligatorio e può contenere fino a 64 caratteri, inclusi gli spazi.</span><span class="sxs-lookup"><span data-stu-id="afcff-167">This name is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="afcff-168">Questo nome viene visualizzato nella notifica per la chiamata in arrivo.</span><span class="sxs-lookup"><span data-stu-id="afcff-168">This name is displayed in the notification for the incoming call.</span></span>

* * *

![Icona del numero 2, che fa riferimento a un callout nella schermata precedente](media/sfbcallout2.png)

<span data-ttu-id="afcff-170">**Aggiungere account** Selezionare un account di risorse.</span><span class="sxs-lookup"><span data-stu-id="afcff-170">**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="afcff-171">L'account delle risorse può o non può essere associato a un numero di telefono a pagamento o a pagamento gratuito per la coda di chiamata, ma per ogni coda di chiamata è necessario un account di risorse associato.</span><span class="sxs-lookup"><span data-stu-id="afcff-171">The resource account may or may not be associated with a service toll or toll-free phone number for the call queue, but each call queue requires an associated resource account.</span></span>

<span data-ttu-id="afcff-172">Se non sono presenti elenchi, è necessario ottenere i numeri di servizio e assegnarli a un account delle risorse prima di poter creare la coda di chiamata, come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="afcff-172">If there aren't any listed, you need to get service numbers and assign them to a Resource account before you can create this call queue, as described earlier.</span></span> <span data-ttu-id="afcff-173">Per ottenere i numeri di servizio, vedere [ottenere i numeri di telefono del servizio](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="afcff-173">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span> <span data-ttu-id="afcff-174">Si crea un account delle risorse come descritto in [gestire gli account delle risorse in teams](manage-resource-accounts.md) se si vuole che la coda di chiamata disponga di un numero di telefono associato.</span><span class="sxs-lookup"><span data-stu-id="afcff-174">You create a resource account as described in [Manage resource accounts in Teams](manage-resource-accounts.md) if you want your call queue to have an associated phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="afcff-175">Se si vuole o è necessario assegnare un **dominio** , assegnarlo all'account delle risorse per la coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="afcff-175">If you want or need to assign a **Domain** you would do so by assigning it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="afcff-176">Impostare il saluto e la musica durante l'attesa</span><span class="sxs-lookup"><span data-stu-id="afcff-176">Set the greeting and music played while on hold</span></span>

![screenshot delle opzioni di saluto e musica, con callout numerati](media/1d395a93-7cab-4178-9295-12d5379e20de.png)

* * *

![Icona del numero 1, che fa riferimento a un callout nella schermata precedente](media/sfbcallout1.png)

<span data-ttu-id="afcff-179">Il **Saluto** è opzionale.</span><span class="sxs-lookup"><span data-stu-id="afcff-179">**Greeting** is optional.</span></span> <span data-ttu-id="afcff-180">Questo è il messaggio di saluto che viene riprodotto per le persone che chiamano il numero della coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="afcff-180">This is the greeting that is played for people who call in to the call queue number.</span></span>

<span data-ttu-id="afcff-181">È possibile caricare un file audio (formati. wav,. mp3 o. WMA).</span><span class="sxs-lookup"><span data-stu-id="afcff-181">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

![Icona del numero 2, che fa riferimento a un callout nella schermata precedente](media/sfbcallout2.png)

<span data-ttu-id="afcff-183">**Musica in attesa** È possibile usare la musica predefinita in attesa fornita con la coda di chiamata oppure è possibile caricare un file audio in formato WAV, MP3 o WMA da usare come musica personalizzata in attesa.</span><span class="sxs-lookup"><span data-stu-id="afcff-183">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="afcff-184">Selezionare le opzioni di segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="afcff-184">Select the call answering options</span></span>

![Screenshot delle opzioni di segreteria telefonica](media/5d249515-d532-4af2-90da-011404028b89.png) 

<span data-ttu-id="afcff-186">Per aggiungere direttamente singoli agenti, senza aggiungerli a un gruppo, fare clic su **Aggiungi utenti**.</span><span class="sxs-lookup"><span data-stu-id="afcff-186">To add individual agents directly, without adding them to a group, click **Add users**.</span></span> <span data-ttu-id="afcff-187">Inserire singoli agenti nell'ordine in cui si vuole che ricevano la chiamata.</span><span class="sxs-lookup"><span data-stu-id="afcff-187">Put individual agents in the order in which you want them to receive the call.</span></span> <span data-ttu-id="afcff-188">È possibile aggiungere fino a 20 singoli agenti (per aggiungere più di 20, inserirli in un gruppo).</span><span class="sxs-lookup"><span data-stu-id="afcff-188">You can add up to 20 individual agents (to add more than 20, put them in a group).</span></span>

<span data-ttu-id="afcff-189">Le chiamate vengono instradate prima a singoli agenti, quindi agli agenti in gruppi.</span><span class="sxs-lookup"><span data-stu-id="afcff-189">Calls are routed first to individual agents, then to the agents in groups.</span></span> 

<span data-ttu-id="afcff-190">È possibile selezionare fino a 200 gli agenti di chiamata che appartengono a una delle seguenti liste di distribuzione o gruppi:</span><span class="sxs-lookup"><span data-stu-id="afcff-190">You can select up to 200 call agents who belong to any of the following mailing lists or groups:</span></span>

- <span data-ttu-id="afcff-191">Gruppo Office 365</span><span class="sxs-lookup"><span data-stu-id="afcff-191">Office 365 group</span></span>
- <span data-ttu-id="afcff-192">Gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="afcff-192">Security group</span></span>
- <span data-ttu-id="afcff-193">Elenco di distribuzione</span><span class="sxs-lookup"><span data-stu-id="afcff-193">Distribution list</span></span>

<span data-ttu-id="afcff-194">Gli agenti di chiamata selezionati devono essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="afcff-194">Call agents selected must be one of the following:</span></span> 

- <span data-ttu-id="afcff-195">Utenti online con licenza di sistema telefonico e VoIP aziendale abilitato</span><span class="sxs-lookup"><span data-stu-id="afcff-195">Online users with a Phone System license and Enterprise Voice enabled</span></span> 
- <span data-ttu-id="afcff-196">Utenti online con un piano per le chiamate</span><span class="sxs-lookup"><span data-stu-id="afcff-196">Online users with a Calling Plan</span></span>
- <span data-ttu-id="afcff-197">Utenti di Skype for Business Server locale</span><span class="sxs-lookup"><span data-stu-id="afcff-197">On-premises Skype for Business Server users</span></span>

  > [!NOTE]
  > <span data-ttu-id="afcff-198">Questo vale anche se vuoi reindirizzare le chiamate agli utenti dell'organizzazione online.</span><span class="sxs-lookup"><span data-stu-id="afcff-198">This also applies if you want to redirect calls to people in your organization who are online.</span></span> <span data-ttu-id="afcff-199">Questi utenti devono avere una licenza per il **sistema telefonico** e VoIP aziendale abilitato **o** avere un piano di chiamata.</span><span class="sxs-lookup"><span data-stu-id="afcff-199">These individuals must have a **Phone System** license and Enterprise Voice enabled **or** have a Calling Plan.</span></span> <span data-ttu-id="afcff-200">Per altre informazioni, vedere [assegnare licenze Skype for business](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [assegnare licenze Microsoft teams](https://docs.microsoft.com/microsoftteams/assign-teams-licenses)o [quale piano per le chiamate è giusto per l'utente?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span><span class="sxs-lookup"><span data-stu-id="afcff-200">For more information, see [Assign Skype for Business licenses](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [Assign Microsoft Teams licenses](https://docs.microsoft.com/microsoftteams/assign-teams-licenses), or [Which Calling Plan is right for you?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span></span>

 <span data-ttu-id="afcff-201">Per abilitare un agente per VoIP aziendale, è possibile usare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="afcff-201">To enable an agent for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="afcff-202">Ad esempio, Esegui:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="afcff-202">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="afcff-203">Utenti con una licenza di **sistema telefonico** o un piano di chiamata aggiunto a un gruppo di Office 365; una lista di distribuzione abilitata per la posta elettronica; o un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="afcff-203">Users with a **Phone System** license or a Calling Plan that are added to either an Office 365 Group; a mail-enabled Distribution List; or a Security Group.</span></span> <span data-ttu-id="afcff-204">Per iniziare a ricevere chiamate da una coda di chiamata, potrebbero essere necessarie fino a tre ore per un nuovo agente aggiunto in una lista di distribuzione o un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="afcff-204">It might take up to three hours for a newly added agent in a distribution list, or a security group, to start receiving calls from a call queue.</span></span> <span data-ttu-id="afcff-205">Una lista di distribuzione o un gruppo di sicurezza appena creato può richiedere fino a 48 ore per diventare disponibile per l'uso con le code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="afcff-205">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="afcff-206">I Gruppi di Office 365 appena creati sono disponibili quasi immediatamente.</span><span class="sxs-lookup"><span data-stu-id="afcff-206">Newly created Office 365 Groups are available almost immediately.</span></span>

- <span data-ttu-id="afcff-207">Se gli agenti usano l'app Microsoft teams per eseguire chiamate in coda di chiamata, devono essere in modalità TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="afcff-207">If your agents are using Microsoft Teams App to take call queue calls, they need to be in TeamsOnly mode.</span></span>

![Screenshot del riquadro Aggiungi agenti chiamata](media/skype-for-business-add-agents-to-call-queue.png)

![Icona del numero 2, che fa riferimento a un callout nella schermata precedente](media/sfbcallout2.png)

<span data-ttu-id="afcff-210">**Metodo di routing** Per il metodo di distribuzione delle code di chiamata, è possibile scegliere **Supervisore**, **seriale**o **Round Robin** .</span><span class="sxs-lookup"><span data-stu-id="afcff-210">**Routing method** You can choose either **Attendant**, **Serial**, or **Round Robin** for your call queue distribution method.</span></span> <span data-ttu-id="afcff-211">Tutte le code di chiamata nuovi ed esistenti hanno l'instradamento operatore selezionato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="afcff-211">All new and existing call queues will have attendant routing selected by default.</span></span> <span data-ttu-id="afcff-212">Quando viene usato il routing di Attendant, la prima chiamata nella coda squilla tutti gli agenti di chiamata contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="afcff-212">When attendant routing is used, the first call in the queue rings all call agents at the same time.</span></span> <span data-ttu-id="afcff-213">Il primo agente di chiamata a prendere la chiamata riceve la chiamata.</span><span class="sxs-lookup"><span data-stu-id="afcff-213">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="afcff-214">Il **routing degli assistenti** fa sì che la prima chiamata nella coda squilli tutti gli agenti di chiamata contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="afcff-214">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="afcff-215">Il primo agente di chiamata a prendere la chiamata riceve la chiamata.</span><span class="sxs-lookup"><span data-stu-id="afcff-215">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="afcff-216">**Routing seriale** chiamate in arrivo chiama gli agenti di chiamata uno alla volta, a partire dall'inizio dell'elenco dell'agente di chiamata.</span><span class="sxs-lookup"><span data-stu-id="afcff-216">**Serial routing** incoming calls ring call agents one by one, starting from the beginning of the call agent list.</span></span> <span data-ttu-id="afcff-217">Non è possibile ordinare gli agenti nell'elenco agente chiamate.</span><span class="sxs-lookup"><span data-stu-id="afcff-217">Agents cannot be ordered within the call agent list.</span></span> <span data-ttu-id="afcff-218">Se un agente rifiuta o non seleziona una chiamata, la chiamata squillerà all'agente successivo nell'elenco e cercherà tutti gli agenti uno alla volta fino a quando non verrà risposta o va in timeout in attesa nella coda.</span><span class="sxs-lookup"><span data-stu-id="afcff-218">If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>
  > [!NOTE]
  > <span data-ttu-id="afcff-219">L'instradamento seriale ignorerà gli agenti che sono **Non in linea**, che hanno impostato la presenza su **Non disturbare**o hanno **Rinunciato** scegliendo di non ricevere chiamate da questa coda.</span><span class="sxs-lookup"><span data-stu-id="afcff-219">Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span>
- <span data-ttu-id="afcff-220">**Round Robin** bilancia il routing delle chiamate in arrivo in modo che ogni agente di chiamata ottenga lo stesso numero di chiamate dalla coda.</span><span class="sxs-lookup"><span data-stu-id="afcff-220">**Round robin** balances routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="afcff-221">Questo potrebbe essere auspicabile in un ambiente di vendita in entrata per assicurare la parità di opportunità tra tutti gli agenti di chiamata.</span><span class="sxs-lookup"><span data-stu-id="afcff-221">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="afcff-222">Selezionare un'opzione di opt-out per l'agente</span><span class="sxs-lookup"><span data-stu-id="afcff-222">Select an agent opt-out option</span></span>

![Screenshot delle opzioni di opt-out per gli agenti, con callout numerati](media/99279eff-db61-4acf-9b62-64be84b6414b.png)

* * *

![Icona del numero 1, che fa riferimento a un callout nella schermata precedente](media/sfbcallout1.png)

<span data-ttu-id="afcff-225">**L'agente può rifiutare di ricevere chiamate** È possibile scegliere di consentire agli agenti della coda di chiamata di rifiutare l'annullamento delle chiamate da una coda specifica abilitando questa opzione.</span><span class="sxs-lookup"><span data-stu-id="afcff-225">**Agent can opt out of getting calls** You can choose to allow call queue agents to opt-out of taking calls from a particular queue by enabling this option.</span></span>

<span data-ttu-id="afcff-226">L'abilitazione di questa opzione consente a tutti gli agenti in questa coda di avviare o interrompere la ricezione delle chiamate da questa coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="afcff-226">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="afcff-227">Puoi revocare il privilegio di esclusione dell'agente in qualsiasi momento, deselezionando la casella di controllo, includendo nuovamente automaticamente tutti gli agenti a questa coda (impostazione predefinita per tutti gli agenti).</span><span class="sxs-lookup"><span data-stu-id="afcff-227">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="afcff-228">Per accedere all'opzione di esclusione, gli agenti possono eseguire le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="afcff-228">To access the opt-out option, agents can do the following:</span></span>

 1. <span data-ttu-id="afcff-229">Aprire **Opzioni** nel proprio client desktop di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="afcff-229">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="afcff-230">Nella scheda **Inoltro chiamata** di chiamata, fare clic sul collegamento **Modifica impostazioni online**.</span><span class="sxs-lookup"><span data-stu-id="afcff-230">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="afcff-231">Nella pagina impostazioni utente fare clic su **code di chiamata**e quindi deselezionare le caselle di controllo relative alle code per cui si desidera escludere l'opt-out.</span><span class="sxs-lookup"><span data-stu-id="afcff-231">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt-out.</span></span>

    > [!NOTE]
    > <span data-ttu-id="afcff-232">Gli agenti che usano app o endpoint diversi da Skype for business desktop possono accedere all'opzione opt-out dal portale [https://aka.ms/cqsettings](https://aka.ms/cqsettings)delle impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="afcff-232">Agents using apps or endpoints other than Skype for Business Desktop can access the opt-out option from the user settings portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span></span>
    >
    > <span data-ttu-id="afcff-233">Se gli agenti si trovano nei client desktop di Microsoft teams, possono rifiutare l'opt-out usando le impostazioni di chiamata.</span><span class="sxs-lookup"><span data-stu-id="afcff-233">If the agents are in Microsoft Teams desktop clients, then they can opt-out by using the Call Settings.</span></span> 

![screenshot delle impostazioni di chiamata opt-out](media/create-a-phone-system-call-queue-image1.png)

<span data-ttu-id="afcff-235">![Icona del numero 2, che fa riferimento a un callout nell'](media/sfbcallout2.png)
**impostazione di avviso dell'agente** screenshot precedente</span><span class="sxs-lookup"><span data-stu-id="afcff-235">![Icon of the number 2, referencing a callout in the previous screenshot](media/sfbcallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="afcff-236">In questo modo viene definita la durata di un agente notificato di una chiamata prima che i metodi di routing seriale o Round Robin vengano spostati nell'agente successivo.</span><span class="sxs-lookup"><span data-stu-id="afcff-236">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="afcff-237">L'impostazione predefinita è 30 secondi, ma può essere impostata per un massimo di 3 minuti.</span><span class="sxs-lookup"><span data-stu-id="afcff-237">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="afcff-238">Impostare le opzioni di gestione di overflow e timeout delle chiamate</span><span class="sxs-lookup"><span data-stu-id="afcff-238">Set the call overflow and timeout handling options</span></span>

![Screenshot delle opzioni di gestione dell'overflow, con callout numerati](media/3f018734-16fe-458b-827d-71fc25155cde.png)

* * *

![Icona del numero 1, che fa riferimento a un callout nella schermata precedente](media/sfbcallout1.png)

<span data-ttu-id="afcff-241">**Chiamate massime in coda** Consente di impostare il numero massimo di chiamate che possono aspettare in coda contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="afcff-241">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="afcff-242">Il valore predefinito è 50, ma può variare da 0 a 200.</span><span class="sxs-lookup"><span data-stu-id="afcff-242">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="afcff-243">Quando viene raggiunto questo limite, la chiamata viene gestita nel modo in cui viene impostata la posizione in **cui viene raggiunto il numero massimo di chiamate** .</span><span class="sxs-lookup"><span data-stu-id="afcff-243">When this limit is reached, the call is handled in the way you set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

![Icona del numero 2, che fa riferimento a un callout nella schermata precedente](media/sfbcallout2.png)

<span data-ttu-id="afcff-245">**Quando viene raggiunto il numero massimo di chiamate** Quando la coda di chiamata raggiunge le dimensioni massime (impostate usando le **chiamate massime nell'impostazione della coda** ), è possibile scegliere cosa succede alle nuove chiamate in arrivo.</span><span class="sxs-lookup"><span data-stu-id="afcff-245">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="afcff-246">**Disconnetti** La chiamata è disconnessa.</span><span class="sxs-lookup"><span data-stu-id="afcff-246">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="afcff-247">**Reindirizza a** Quando si sceglie questo pulsante, selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="afcff-247">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="afcff-248">**Persona nella tua azienda** Un utente online con una licenza di **sistema telefonico** ed essere abilitato per VoIP aziendale o avere un piano per le chiamate.</span><span class="sxs-lookup"><span data-stu-id="afcff-248">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="afcff-249">È possibile configurarlo in modo che il chiamante possa essere inviato alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="afcff-249">You can set it up so the caller can be sent to voicemail.</span></span> <span data-ttu-id="afcff-250">A questo scopo, seleziona una **persona nella tua azienda** e imposta questa persona affinché le chiamate vengano inoltrate direttamente alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="afcff-250">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="afcff-251">Per informazioni sulle licenze necessarie per la segreteria telefonica, vedere [configurare la segreteria telefonica cloud](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="afcff-251">To learn about licenses required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="afcff-252">**Applicazione vocale** Selezionare il nome di un account di risorsa associato a una coda di chiamata o a un operatore automatico già creato.</span><span class="sxs-lookup"><span data-stu-id="afcff-252">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

* * *

![Icona del numero 3, che fa riferimento a un callout nella schermata precedente](media/sfbcallout3.png)

<span data-ttu-id="afcff-254">**Timeout chiamata: tempo massimo di attesa** Puoi anche decidere quanto tempo può rimanere in attesa di una chiamata nella coda prima che venga interrotto e debba essere reindirizzato o disconnesso.</span><span class="sxs-lookup"><span data-stu-id="afcff-254">**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="afcff-255">Il punto in cui viene reindirizzato si basa su come impostare l'impostazione quando viene impostato il timeout **di una chiamata** .</span><span class="sxs-lookup"><span data-stu-id="afcff-255">Where it is redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="afcff-256">Puoi impostare un tempo da 0 a 45 minuti.</span><span class="sxs-lookup"><span data-stu-id="afcff-256">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="afcff-257">Puoi impostare il valore di timeout in secondi, a intervalli di 15 secondi.</span><span class="sxs-lookup"><span data-stu-id="afcff-257">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="afcff-258">In questo modo è possibile modificare il flusso delle chiamate con maggiore granularità.</span><span class="sxs-lookup"><span data-stu-id="afcff-258">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="afcff-259">Ad esempio, puoi specificare che le chiamate non risposte da un agente entro 30 secondi passa a un operatore automatico di ricerca della directory.</span><span class="sxs-lookup"><span data-stu-id="afcff-259">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

![Icona del numero 4, che fa riferimento a un callout nella schermata precedente](media/sfbcallout4.png)

<span data-ttu-id="afcff-261">**Timeout chiamata** Quando la chiamata raggiunge il limite impostato sul periodo di **attesa di una chiamata nell'impostazione della coda** , è possibile scegliere cosa succede a questa chiamata:</span><span class="sxs-lookup"><span data-stu-id="afcff-261">**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>

- <span data-ttu-id="afcff-262">**Disconnetti** La chiamata è disconnessa.</span><span class="sxs-lookup"><span data-stu-id="afcff-262">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="afcff-263">**Reindirizzare la chiamata a** Quando si sceglie questa opzione, sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="afcff-263">**Redirect this call to** When you choose this, you have these options:</span></span>
  - <span data-ttu-id="afcff-264">**Persona nella tua azienda** Un utente online con una licenza di **sistema telefonico** ed essere abilitato per VoIP aziendale o per avere piani di chiamata.</span><span class="sxs-lookup"><span data-stu-id="afcff-264">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="afcff-265">Puoi impostarla in modo che la persona che chiama possa essere passata alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="afcff-265">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="afcff-266">A questo scopo, seleziona una **persona nella tua azienda** e imposta questa persona affinché le chiamate vengano inoltrate direttamente alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="afcff-266">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="afcff-267">Per informazioni sulle licenze necessarie per la segreteria telefonica, vedere [configurare la segreteria telefonica cloud](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="afcff-267">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="afcff-268">**Applicazione vocale** Selezionare il nome di un account di risorsa associato a una coda di chiamata o a un operatore automatico già creato.</span><span class="sxs-lookup"><span data-stu-id="afcff-268">**Voice application** Select the name of a resource account associated with either a call queue or auto attendant that has already been created.</span></span>

## <a name="change-a-users-caller-id-for-outbound-calls"></a><span data-ttu-id="afcff-269">Modificare l'ID chiamante di un utente per le chiamate in uscita</span><span class="sxs-lookup"><span data-stu-id="afcff-269">Change a user's Caller ID for outbound calls</span></span>

<span data-ttu-id="afcff-270">Puoi proteggere l'identità di un utente modificando l'ID chiamante per le chiamate in uscita in una coda di chiamata, un operatore automatico o un numero di servizio usando il cmdlet **New-CsCallingLineIdentity** .</span><span class="sxs-lookup"><span data-stu-id="afcff-270">You can protect a user's identity by changing their caller ID for outbound calls to a call queue, auto attendant, or any service number instead using the **New-CsCallingLineIdentity** cmdlet.</span></span>

<span data-ttu-id="afcff-271">Per farlo, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="afcff-271">To do this, run:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="afcff-272">Quindi applica il criterio per l'utente utilizzando il cmdlet \*\* Grant-CallingLineIdentity.\*\*</span><span class="sxs-lookup"><span data-stu-id="afcff-272">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet.</span></span> <span data-ttu-id="afcff-273">Per farlo, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="afcff-273">To do this, run:</span></span>

``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="afcff-274">Per altre informazioni su come impostare le impostazioni dell'ID chiamante nell'organizzazione [, vedere come si può usare l'ID chiamante nell'organizzazione](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="afcff-274">You can get more information on how to set caller ID settings in your organization in the article [How can caller ID be used in your organization](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="afcff-275">Cmdlet della coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="afcff-275">Call queue cmdlets</span></span>

<span data-ttu-id="afcff-276">Puoi anche utilizzare Windows PowerShell per creare e configurare code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="afcff-276">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="afcff-277">Ecco i cmdlet usati per gestire una coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="afcff-277">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="afcff-278">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="afcff-278">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="afcff-279">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="afcff-279">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="afcff-280">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="afcff-280">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="afcff-281">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="afcff-281">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="afcff-282">Altre informazioni su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="afcff-282">More about Windows PowerShell</span></span>

- <span data-ttu-id="afcff-283">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="afcff-283">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="afcff-284">Con Windows PowerShell è possibile gestire Office 365 e Microsoft teams con un unico punto di amministrazione in grado di semplificare il lavoro quotidiano, quando si hanno più attività da eseguire.</span><span class="sxs-lookup"><span data-stu-id="afcff-284">With Windows PowerShell, you can manage Office 365 and Microsoft Teams with a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="afcff-285">Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="afcff-285">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="afcff-286">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="afcff-286">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="afcff-287">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="afcff-287">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="afcff-288">Windows PowerShell offre numerosi vantaggi in termini di velocità, semplicità e produttività nell'interfaccia di amministrazione di Microsoft teams, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="afcff-288">Windows PowerShell has many advantages in speed, simplicity, and productivity over the Microsoft Teams admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="afcff-289">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="afcff-289">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="afcff-290">Gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="afcff-290">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="afcff-291">Configurare il computer per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="afcff-291">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="afcff-292">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="afcff-292">Related topics</span></span>

[<span data-ttu-id="afcff-293">Ecco cosa offre il Sistema telefonico in Office 365</span><span class="sxs-lookup"><span data-stu-id="afcff-293">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

<span data-ttu-id="afcff-294">[Recuperare numeri di telefono del servizio](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="afcff-294">[Getting service phone numbers](getting-service-phone-numbers.md)</span></span>

[<span data-ttu-id="afcff-295">Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica</span><span class="sxs-lookup"><span data-stu-id="afcff-295">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="afcff-296">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="afcff-296">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
