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
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Informazioni su come configurare il sistema telefonico per le code delle chiamate cloud con Microsoft teams.
ms.openlocfilehash: 887c92e398487d3e42f9fc560610683008760105
ms.sourcegitcommit: a49caec01ff724475d6670b303d851ddd8266c2c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2019
ms.locfileid: "36207182"
---
# <a name="create-a-cloud-call-queue"></a><span data-ttu-id="c9507-103">Creare una coda di chiamata cloud</span><span class="sxs-lookup"><span data-stu-id="c9507-103">Create a Cloud call queue</span></span>

<span data-ttu-id="c9507-104">Le code delle chiamate cloud possono essere fornite:</span><span class="sxs-lookup"><span data-stu-id="c9507-104">Cloud call queues can provide:</span></span>
 
- <span data-ttu-id="c9507-105">Messaggio di saluto.</span><span class="sxs-lookup"><span data-stu-id="c9507-105">A greeting message.</span></span>
- <span data-ttu-id="c9507-106">Musica mentre le persone sono in attesa.</span><span class="sxs-lookup"><span data-stu-id="c9507-106">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="c9507-107">Reindirizzamento delle chiamate agli agenti di chiamata nelle liste di distribuzione e nei gruppi di sicurezza abilitati alla posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="c9507-107">Redirecting of calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="c9507-108">Impostazioni parametri diversi, ad esempio la dimensione massima della coda, il timeout e le opzioni di gestione delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="c9507-108">Settings different parameters such as queue maximum size, timeout, and call handling options.</span></span>

<span data-ttu-id="c9507-109">Quando qualcuno chiama un numero di telefono associato a una coda di chiamata tramite un [account delle risorse](manage-resource-accounts.md):</span><span class="sxs-lookup"><span data-stu-id="c9507-109">When someone calls a phone number that is associated with a call queue via a [resource account](manage-resource-accounts.md):</span></span> 
1. <span data-ttu-id="c9507-110">Sente un saluto (se è configurato)</span><span class="sxs-lookup"><span data-stu-id="c9507-110">They  hear a greeting (if any is set up)</span></span> 
2. <span data-ttu-id="c9507-111">La chiamata viene inserita nella coda per attendere il successivo agente di chiamata disponibile.</span><span class="sxs-lookup"><span data-stu-id="c9507-111">Their call is put in the queue to wait for the next available call agent.</span></span> 
 

<span data-ttu-id="c9507-112">Il chiamante sente la musica mentre è in attesa e la chiamata si connette agli agenti di chiamata in ordine *First in, First out* (FIFO).</span><span class="sxs-lookup"><span data-stu-id="c9507-112">The caller hears music while they are on hold, and the call connects to the call agents in *First In, First Out* (FIFO) order.</span></span>
 
<span data-ttu-id="c9507-113">Tutte le chiamate nella coda vengono inviate agli agenti da uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9507-113">All calls in the queue are sent to agents by one of the following methods:</span></span>
 
- <span data-ttu-id="c9507-114">Con il routing di Attendant, la prima chiamata nella coda squilla tutti gli agenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="c9507-114">With attendant routing, the first call in the queue  rings all agents at the same time.</span></span>
- <span data-ttu-id="c9507-115">Con il routing seriale, la prima chiamata nella coda squilla tutti gli agenti di chiamata uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="c9507-115">With serial routing, the first call in the queue rings all call agents one by one.</span></span>
- <span data-ttu-id="c9507-116">Con Round Robin, il routing delle chiamate in arrivo è bilanciato in modo che ogni agente di chiamata ottenga lo stesso numero di chiamate dalla coda.</span><span class="sxs-lookup"><span data-stu-id="c9507-116">With round robin, routing of incoming calls is balanced so that each call agent gets the same number of calls from the queue.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c9507-117">Gli agenti di chiamata **offline**, hanno impostato la loro presenza \*\*\*\* su non disturbare o hanno scelto di non ricevere chiamate nella coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="c9507-117">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue will not recieve calls.</span></span>
 
- <span data-ttu-id="c9507-118">Solo una notifica di chiamata in arrivo (per la chiamata a capo della coda) alla volta passa agli agenti di chiamata.</span><span class="sxs-lookup"><span data-stu-id="c9507-118">Only one incoming call notification (for the call at the head of the queue) at a time goes to the call agents.</span></span>
- <span data-ttu-id="c9507-119">Una volta che un agente di chiamata accetta la chiamata, la prossima chiamata in arrivo in coda viene segnalata agli agenti di chiamata.</span><span class="sxs-lookup"><span data-stu-id="c9507-119">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="c9507-120">Questo articolo si applica sia a Microsoft teams che a Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="c9507-120">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="c9507-121">Passaggio 1: iniziare</span><span class="sxs-lookup"><span data-stu-id="c9507-121">Step 1 — Get started</span></span>

<span data-ttu-id="c9507-122">Per iniziare a utilizzare le code di chiamata, è importante ricordare quanto segue.</span><span class="sxs-lookup"><span data-stu-id="c9507-122">To get started using call queues, it's important to remember a few things:</span></span>
 
- <span data-ttu-id="c9507-123">È necessaria una coda di chiamata per avere un account di risorse associato.</span><span class="sxs-lookup"><span data-stu-id="c9507-123">A call queue is required to have an associated resource account.</span></span> <span data-ttu-id="c9507-124">Per informazioni dettagliate sugli account delle risorse, vedere [gestire gli account delle risorse in teams](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="c9507-124">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="c9507-125">Quando si assegna un numero di telefono a un account delle risorse, è ora possibile usare la licenza per gli [utenti virtuali](teams-add-on-licensing/virtual-user.md)del sistema telefonico senza costi.</span><span class="sxs-lookup"><span data-stu-id="c9507-125">When you assign a phone number to a resource account, you can now use the cost-free Phone System [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span> <span data-ttu-id="c9507-126">Sistema telefonico consente di usare i numeri di telefono a livello di organizzazione per l'operatore automatico a basso costo e i servizi di Accodamento chiamate.</span><span class="sxs-lookup"><span data-stu-id="c9507-126">Phone System allows phone numbers at the organizational level for use with low-cost auto attendant and call queue services.</span></span>

> [!NOTE]
> <span data-ttu-id="c9507-127">I numeri di servizio di routing diretto per le code di chiamata sono supportati solo per gli utenti e gli agenti di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="c9507-127">Direct Routing service numbers for call queues are supported for Microsoft Teams users and agents only.</span></span>

> [!NOTE]
> <span data-ttu-id="c9507-128">Per reindirizzare le chiamate alle persone dell'organizzazione online, devono avere una licenza per il **sistema telefonico** e essere abilitate per VoIP aziendale o avere piani di chiamata di Office 365.</span><span class="sxs-lookup"><span data-stu-id="c9507-128">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="c9507-129">Vedere [assegnare licenze di Skype for business](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) o [assegnare licenze di Microsoft teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="c9507-129">See [Assign Skype for Business licenses](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="c9507-130">Per abilitare VoIP aziendale, è possibile utilizzare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9507-130">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="c9507-131">Ad esempio, Esegui:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="c9507-131">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
 
- <span data-ttu-id="c9507-132">Per altre informazioni sui piani di chiamate di Office 365, vedere [sistemi di telefonia e](calling-plan-landing-page.md) piani di chiamata e [piani di chiamata per Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="c9507-132">To learn more about Office 365 Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

- <span data-ttu-id="c9507-133">È possibile assegnare solo i numeri di telefono a pedaggio e numero verde delle code di chiamate cloud disponibili nell'interfaccia di **amministrazione di Microsoft teams** o trasferiti da un altro provider di servizi.</span><span class="sxs-lookup"><span data-stu-id="c9507-133">You can only assign Cloud call queues toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider.</span></span> <span data-ttu-id="c9507-134">I crediti per le comunicazioni sono necessari per i numeri di servizio gratuiti.</span><span class="sxs-lookup"><span data-stu-id="c9507-134">Communications Credits are required for toll-free service numbers.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c9507-135">I numeri di telefono di utenti (abbonati) non possono essere assegnati a code di chiamata, ma solo numeri di telefono di servizio a pagamento o numeri verdi.</span><span class="sxs-lookup"><span data-stu-id="c9507-135">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>
 
- <span data-ttu-id="c9507-136">I client seguenti sono supportati per gli agenti di chiamata associati a una coda di chiamata cloud:</span><span class="sxs-lookup"><span data-stu-id="c9507-136">The following clients are supported for call agents associated to a Cloud call queue:</span></span>

  - <span data-ttu-id="c9507-137">Client desktop Skype for business 2016 (versioni 32 e 64 bit)</span><span class="sxs-lookup"><span data-stu-id="c9507-137">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="c9507-138">Client desktop Lync 2013 (versioni 32 e 64 bit)</span><span class="sxs-lookup"><span data-stu-id="c9507-138">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="c9507-139">Tutti i modelli di telefono IP supportati per Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="c9507-139">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="c9507-140">Vedere [ottenere telefoni per Skype for business online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="c9507-140">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>

  - <span data-ttu-id="c9507-141">Client Mac Skype for Business (versione 16.8.196 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="c9507-141">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="c9507-142">Client Android Skype for Business (versione 6.16.0.9 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="c9507-142">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="c9507-143">Client iPhone Skype for Business (versione 6.16.0 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="c9507-143">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="c9507-144">Client Mac Skype for Business (versione 6.16.0 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="c9507-144">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="c9507-145">Client Windows Microsoft Teams (versioni a 32 bit e 64 bit)</span><span class="sxs-lookup"><span data-stu-id="c9507-145">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="c9507-146">Client Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="c9507-146">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="c9507-147">App per iPhone di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c9507-147">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="c9507-148">App Microsoft teams Android</span><span class="sxs-lookup"><span data-stu-id="c9507-148">Microsoft Teams Android app</span></span>

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="c9507-149">Fase 2 - Ottenere o trasferire numeri di servizio a pagamento o a numero verde</span><span class="sxs-lookup"><span data-stu-id="c9507-149">Step 2 - Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="c9507-150">Prima di poter creare e configurare le code di chiamata, è necessario ottenere o trasferire i numeri di servizio a pagamento o a pedaggio esistenti.</span><span class="sxs-lookup"><span data-stu-id="c9507-150">Before you can create and set up your call queues, you need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="c9507-151">Dopo aver ottenuto i numeri di telefono del servizio a pagamento o a pedaggio, verranno visualizzati nei**numeri di telefono**della**voce** > del**portale** > dell'interfaccia di >  **amministrazione Microsoft teams**legacy e il tipo di **numero** verrà elencato come **Servizio gratuito-numero verde**.</span><span class="sxs-lookup"><span data-stu-id="c9507-151">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Legacy Portal** > **Voice** > **Phone numbers**, and the **Number type** will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="c9507-152">Per ottenere i numeri di servizio, vedere [recupero di numeri di telefono](getting-service-phone-numbers.md) o se si vuole trasferire un numero di servizio esistente, vedere trasferire i [numeri di telefono in Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="c9507-152">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
 
> [!NOTE]
> <span data-ttu-id="c9507-153">Se si è al di fuori degli Stati Uniti, non è possibile usare l'interfaccia di amministrazione di Microsoft teams per ottenere i numeri di servizio.</span><span class="sxs-lookup"><span data-stu-id="c9507-153">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="c9507-154">Vai a [gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) per vedere come farlo dall'esterno degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="c9507-154">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="c9507-155">Se si sta configurando più operatori automatici, potrebbe essere necessario assegnare un numero di telefono all'account delle risorse dell'operatore automatico principale, che può indirizzare i chiamanti alle code di chiamata o agli operatori automatici annidati.</span><span class="sxs-lookup"><span data-stu-id="c9507-155">If you are setting up multiple auto attendants, you may only need to assign a phone number to the main auto attendant's resource account, which can direct callers to your call queues or nested auto attendants.</span></span> <span data-ttu-id="c9507-156">In tali casi è consigliabile creare tutti gli operatori automatici e le code di chiamata nel sistema senza assegnare le opzioni del tastierino e quindi modificare le impostazioni in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="c9507-156">In those situations you should create all auto attendants and call queues in your system without assigning dialpad options, and then edit the settings later.</span></span> <span data-ttu-id="c9507-157">Questa operazione è necessaria perché non è consentito creare un'opzione che collega a una coda di chiamata o a un operatore automatico che non esiste ancora.</span><span class="sxs-lookup"><span data-stu-id="c9507-157">This is necessary because you aren't allowed to create an option linking to a call queue or auto attendant that does not yet exist.</span></span>
 
## <a name="step-3---create-a-new-call-queue"></a><span data-ttu-id="c9507-158">Passaggio 3-creare una nuova coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="c9507-158">Step 3 - Create a new call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="c9507-159">Ogni coda di chiamata è necessaria per avere un [account di risorse](manage-resource-accounts.md)associato.</span><span class="sxs-lookup"><span data-stu-id="c9507-159">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="c9507-160">Devi prima creare l'account della risorsa, quindi puoi associarlo alla coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="c9507-160">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c9507-161">Uso dell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c9507-161">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="c9507-162">Nell'interfaccia **di amministrazione di Microsoft teams**, code di**chiamata** **vocale** > , quindi fare clic su **+ Aggiungi nuovo**:</span><span class="sxs-lookup"><span data-stu-id="c9507-162">In the **Microsoft Teams admin center**, **Voice** > **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-call-queue-display-name-and-resource-account"></a><span data-ttu-id="c9507-163">Impostare il nome visualizzato della coda di chiamata e l'account delle risorse</span><span class="sxs-lookup"><span data-stu-id="c9507-163">Set the call queue display name and resource account</span></span>

![Screenshot di una nuova coda di chiamata, con callout numerati](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="c9507-165">![Icona del numero 1, facendo riferimento a un callout nel](media/sfbcallout1.png)
**nome** dello screenshot precedente immettere un nome visualizzato descrittivo per la coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="c9507-165">![Icon of the number 1, referencing a callout in the previous screenshot](media/sfbcallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="c9507-166">Questo nome è obbligatorio e può contenere fino a 64 caratteri, inclusi gli spazi.</span><span class="sxs-lookup"><span data-stu-id="c9507-166">This name is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="c9507-167">Questo nome viene visualizzato nella notifica per la chiamata in arrivo.</span><span class="sxs-lookup"><span data-stu-id="c9507-167">This name is displayed in the notification for the incoming call.</span></span>

* * *

![Icona del numero 2, che fa riferimento a un callout nella schermata precedente](media/sfbcallout2.png)

<span data-ttu-id="c9507-169">**Aggiungere account** Selezionare un account di risorse.</span><span class="sxs-lookup"><span data-stu-id="c9507-169">**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="c9507-170">L'account delle risorse può o non può essere associato a un numero di telefono a pagamento o a pagamento gratuito per la coda di chiamata, ma per ogni coda di chiamata è necessario un account di risorse associato.</span><span class="sxs-lookup"><span data-stu-id="c9507-170">The resource account may or may not be associated with a service toll or toll-free phone number for the call queue, but each call queue requires an associated resource account.</span></span>

<span data-ttu-id="c9507-171">Se non sono presenti elenchi, è necessario ottenere i numeri di servizio e assegnarli a un account delle risorse prima di poter creare la coda di chiamata, come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="c9507-171">If there aren't any listed, you need to get service numbers and assign them to a Resource account before you can create this call queue, as described earlier.</span></span> <span data-ttu-id="c9507-172">Per ottenere i numeri di servizio, vedere [ottenere i numeri di telefono del servizio](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="c9507-172">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span> <span data-ttu-id="c9507-173">È necessario creare un account delle risorse come descritto in [gestire gli account delle risorse in teams](manage-resource-accounts.md) se si vuole che la coda di chiamata disponga di un numero di telefono associato.</span><span class="sxs-lookup"><span data-stu-id="c9507-173">You'll need to create a resource account as described in [Manage resource accounts in Teams](manage-resource-accounts.md) if you want your call queue to have an associated phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="c9507-174">Se si vuole o è necessario assegnare un **dominio** , assegnarlo all'account delle risorse per la coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="c9507-174">If you want or need to assign a **Domain** you would do so by assigning it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="c9507-175">Impostare il saluto e la musica durante l'attesa</span><span class="sxs-lookup"><span data-stu-id="c9507-175">Set the greeting and music played while on hold</span></span>

![screenshot delle opzioni di saluto e musica, con callout numerati](media/1d395a93-7cab-4178-9295-12d5379e20de.png)
 
* * *

![Icona del numero 1, che fa riferimento a un callout nella schermata precedente](media/sfbcallout1.png)

<span data-ttu-id="c9507-178">Il **Saluto** è opzionale.</span><span class="sxs-lookup"><span data-stu-id="c9507-178">**Greeting** is optional.</span></span> <span data-ttu-id="c9507-179">Questo è il messaggio di saluto che viene riprodotto per le persone che chiamano il numero della coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="c9507-179">This is the greeting that is played for people who call in to the call queue number.</span></span>

<span data-ttu-id="c9507-180">È possibile caricare un file audio (formati. wav,. mp3 o. WMA).</span><span class="sxs-lookup"><span data-stu-id="c9507-180">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

![Icona del numero 2, che fa riferimento a un callout nella schermata precedente](media/sfbcallout2.png)

<span data-ttu-id="c9507-182">**Musica in attesa** È possibile usare la musica predefinita in attesa fornita con la coda di chiamata oppure è possibile caricare un file audio in formato WAV, MP3 o WMA da usare come musica personalizzata in attesa.</span><span class="sxs-lookup"><span data-stu-id="c9507-182">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="c9507-183">Selezionare le opzioni di segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="c9507-183">Select the call answering options</span></span>

![screenshot delle opzioni di segreteria telefonica con callout numerati](media/5d249515-d532-4af2-90da-011404028b89.png)

![Icona del numero 1, che fa riferimento a un callout nella schermata precedente](media/sfbcallout1.png)

<span data-ttu-id="c9507-186">È possibile selezionare fino a 200 gli agenti di chiamata che appartengono a una delle seguenti liste di distribuzione o gruppi:</span><span class="sxs-lookup"><span data-stu-id="c9507-186">You can select up to 200 call agents who belong to any of the following mailing lists or groups:</span></span>

- <span data-ttu-id="c9507-187">Gruppo Office 365</span><span class="sxs-lookup"><span data-stu-id="c9507-187">Office 365 group</span></span>
- <span data-ttu-id="c9507-188">Gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="c9507-188">Security group</span></span>
- <span data-ttu-id="c9507-189">Elenco di distribuzione</span><span class="sxs-lookup"><span data-stu-id="c9507-189">Distribution list</span></span>

<span data-ttu-id="c9507-190">Gli agenti di chiamata \*\*\*\* selezionati devono essere utenti online con licenza di **sistema telefonico** e VoIP aziendale abilitato **o** con un piano per le chiamate.</span><span class="sxs-lookup"><span data-stu-id="c9507-190">Call agents selected must **either** be online users with a **Phone System** license and Enterprise Voice enabled **or** have a Calling Plan.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c9507-191">Questo vale anche se vuoi reindirizzare le chiamate agli utenti dell'organizzazione online.</span><span class="sxs-lookup"><span data-stu-id="c9507-191">This also applies if you want to redirect calls to people in your organization who are online.</span></span> <span data-ttu-id="c9507-192">Questi utenti devono avere una licenza per il **sistema telefonico** e VoIP aziendale abilitato **o** avere un piano di chiamata.</span><span class="sxs-lookup"><span data-stu-id="c9507-192">These individuals must have a **Phone System** license and Enterprise Voice enabled **or** have a Calling Plan.</span></span> <span data-ttu-id="c9507-193">Per altre informazioni, vedere [assegnare licenze di Skype for business](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [assegnare licenze di Microsoft teams](https://docs.microsoft.com/microsoftteams/assign-teams-licenses)o [quale piano per le chiamate è giusto per l'utente?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span><span class="sxs-lookup"><span data-stu-id="c9507-193">For more information see [Assign Skype for Business licenses](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [Assign Microsoft Teams licenses](https://docs.microsoft.com/microsoftteams/assign-teams-licenses), or [Which Calling Plan is right for you?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span></span>

 <span data-ttu-id="c9507-194">Per abilitare un agente per VoIP aziendale, è possibile usare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9507-194">To enable an agent for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="c9507-195">Ad esempio, Esegui:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="c9507-195">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="c9507-196">Utenti online con una licenza di **sistema telefonico** o un piano di chiamata aggiunto a un gruppo di Office 365; una lista di distribuzione abilitata per la posta elettronica; o un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c9507-196">Online users with a **Phone System** license or a Calling Plan that are added to either an Office 365 Group; a mail-enabled Distribution List; or a Security Group.</span></span> <span data-ttu-id="c9507-197">Per iniziare a ricevere chiamate da una coda di chiamata, potrebbero essere necessarie fino a tre ore per un nuovo agente aggiunto in una lista di distribuzione o un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="c9507-197">It might take up to three hours for a newly added agent in a distribution list, or a security group, to start receiving calls from a call queue.</span></span> <span data-ttu-id="c9507-198">Una lista di distribuzione o un gruppo di sicurezza appena creato può richiedere fino a 48 ore per diventare disponibile per l'uso con le code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="c9507-198">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="c9507-199">I Gruppi di Office 365 appena creati sono disponibili quasi immediatamente.</span><span class="sxs-lookup"><span data-stu-id="c9507-199">Newly created Office 365 Groups are available almost immediately.</span></span>

- <span data-ttu-id="c9507-200">Se gli agenti usano l'app Microsoft teams per ricevere chiamate in coda di chiamata, devono essere in modalità TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="c9507-200">If your agents are using Microsoft Teams App to receive call queue calls, they need to be in TeamsOnly mode.</span></span>

![screenshot del riquadro Aggiungi agenti chiamata](media/skype-for-business-add-agents-to-call-queue.png)

![Icona del numero 2, che fa riferimento a un callout nella schermata precedente](media/sfbcallout2.png)

<span data-ttu-id="c9507-203">**Metodo di routing** Per il metodo di \*\*\*\* distribuzione delle code di chiamata, è possibile scegliere supervisore, **seriale**o **Round Robin** .</span><span class="sxs-lookup"><span data-stu-id="c9507-203">**Routing method** You can choose either **Attendant**, **Serial**, or **Round Robin** for your call queue distribution method.</span></span> <span data-ttu-id="c9507-204">Tutte le code di chiamata nuovi ed esistenti hanno l'instradamento operatore selezionato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c9507-204">All new and existing call queues will have attendant routing selected by default.</span></span> <span data-ttu-id="c9507-205">Quando viene usato il routing degli addetti, la prima chiamata nella coda suonerà tutti gli agenti di chiamata contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="c9507-205">When attendant routing is used, the first call in the queue will ring all of the call agents at the same time.</span></span> <span data-ttu-id="c9507-206">Il primo agente di chiamata a prendere la chiamata riceve la chiamata.</span><span class="sxs-lookup"><span data-stu-id="c9507-206">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="c9507-207">Il **routing** degli assistenti fa sì che la prima chiamata nella coda squilli tutti gli agenti di chiamata contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="c9507-207">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="c9507-208">Il primo agente di chiamata a prendere la chiamata riceve la chiamata.</span><span class="sxs-lookup"><span data-stu-id="c9507-208">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="c9507-209">Le chiamate in arrivo di **routing seriale** suoneranno gli agenti di chiamata uno alla volta, a partire dall'inizio dell'elenco agente chiamate.</span><span class="sxs-lookup"><span data-stu-id="c9507-209">**Serial routing** incoming calls will ring call agents one by one, starting from the beginning of the call agent list.</span></span> <span data-ttu-id="c9507-210">Non è possibile ordinare gli agenti nell'elenco agente chiamate.</span><span class="sxs-lookup"><span data-stu-id="c9507-210">Agents cannot be ordered within the call agent list.</span></span> <span data-ttu-id="c9507-211">Se un agente rifiuta o non seleziona una chiamata, la chiamata squillerà all'agente successivo nell'elenco e cercherà tutti gli agenti uno alla volta fino a quando non verrà risposta o va in timeout in attesa nella coda.</span><span class="sxs-lookup"><span data-stu-id="c9507-211">If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>
  > [!NOTE]
  > <span data-ttu-id="c9507-212">L'instradamento seriale ignorerà gli agenti che sono **Non in linea**, che hanno impostato la presenza su **Non disturbare**o hanno **Rinunciato** scegliendo di non ricevere chiamate da questa coda.</span><span class="sxs-lookup"><span data-stu-id="c9507-212">Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span>
- <span data-ttu-id="c9507-213">**Round Robin** bilancia il routing delle chiamate in arrivo in modo che ogni agente di chiamata otterrà lo stesso numero di chiamate dalla coda.</span><span class="sxs-lookup"><span data-stu-id="c9507-213">**Round robin** balances routing of incoming calls so that each call agent will get the same number of calls from the queue.</span></span> <span data-ttu-id="c9507-214">Questo potrebbe essere molto utile in un ambiente di vendita in entrata per assicurare pari opportunità tra tutti gli agenti di chiamata.</span><span class="sxs-lookup"><span data-stu-id="c9507-214">This may be very desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="c9507-215">Selezionare un'opzione di opt-out per l'agente</span><span class="sxs-lookup"><span data-stu-id="c9507-215">Select an agent opt-out option</span></span>

![screenshot delle opzioni di opt-out per gli agenti, con callout numerati](media/99279eff-db61-4acf-9b62-64be84b6414b.png)
 
* * *

![Icona del numero 1, che fa riferimento a un callout nella schermata precedente](media/sfbcallout1.png)

<span data-ttu-id="c9507-218">**L'agente può rifiutare di ricevere chiamate** È possibile scegliere di consentire agli agenti della coda di chiamata di rifiutare l'annullamento delle chiamate da una coda specifica abilitando questa opzione.</span><span class="sxs-lookup"><span data-stu-id="c9507-218">**Agent can opt out of getting calls** You can choose to allow call queue agents to opt-out of taking calls from a particular queue by enabling this option.</span></span>

<span data-ttu-id="c9507-219">L'abilitazione di questa opzione consente a tutti gli agenti in questa coda di avviare o interrompere la ricezione delle chiamate da questa coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="c9507-219">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="c9507-220">Puoi revocare il privilegio di esclusione dell'agente in qualsiasi momento, deselezionando la casella di controllo, includendo nuovamente automaticamente tutti gli agenti a questa coda (impostazione predefinita per tutti gli agenti).</span><span class="sxs-lookup"><span data-stu-id="c9507-220">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="c9507-221">Per accedere all'opzione di esclusione, gli agenti possono eseguire le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="c9507-221">To access the opt-out option, agents can do the following:</span></span>

 1. <span data-ttu-id="c9507-222">Aprire **Opzioni** nel proprio client desktop di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="c9507-222">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="c9507-223">Nella scheda **Inoltro chiamata** di chiamata, fare clic sul collegamento **Modifica impostazioni online**.</span><span class="sxs-lookup"><span data-stu-id="c9507-223">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="c9507-224">Nella pagina impostazioni utente fare clic su **code di chiamata**e quindi deselezionare le caselle di controllo relative alle code per cui si desidera escludere l'opt-out.</span><span class="sxs-lookup"><span data-stu-id="c9507-224">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt-out.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c9507-225">Gli agenti che usano app o endpoint diversi da Skype for business desktop possono accedere all'opzione opt-out dal portale [https://aka.ms/cqsettings](https://aka.ms/cqsettings)delle impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="c9507-225">Agents using apps or endpoints other than Skype for Business Desktop can access the opt-out option from the user settings portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span></span>

<span data-ttu-id="c9507-226">![Icona del numero 2, che fa riferimento a un callout nell'](media/sfbcallout2.png)
**impostazione di avviso dell'agente** screenshot precedente</span><span class="sxs-lookup"><span data-stu-id="c9507-226">![Icon of the number 2, referencing a callout in the previous screenshot](media/sfbcallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="c9507-227">In questo modo viene definita la durata di un agente notificato di una chiamata prima che i metodi di routing seriale o Round Robin vengano spostati nell'agente successivo.</span><span class="sxs-lookup"><span data-stu-id="c9507-227">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="c9507-228">L'impostazione predefinita è 30 secondi, ma può essere impostata per un massimo di 3 minuti.</span><span class="sxs-lookup"><span data-stu-id="c9507-228">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="c9507-229">Impostare le opzioni di gestione di overflow e timeout delle chiamate</span><span class="sxs-lookup"><span data-stu-id="c9507-229">Set the call overflow and timeout handling options</span></span>

![screenshot delle opzioni di gestione dell'overflow, con callout numerati](media/3f018734-16fe-458b-827d-71fc25155cde.png)
 
* * *

![Icona del numero 1, che fa riferimento a un callout nella schermata precedente](media/sfbcallout1.png)

<span data-ttu-id="c9507-232">**Chiamate massime in coda** Consente di impostare il numero massimo di chiamate che possono aspettare in coda contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="c9507-232">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="c9507-233">Il valore predefinito è 50, ma può variare da 0 a 200.</span><span class="sxs-lookup"><span data-stu-id="c9507-233">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="c9507-234">Quando viene raggiunto questo limite, la chiamata verrà gestita nel modo definito dall'impostazione **Quando viene raggiunto il numero massimo di chiamate**, di seguito.</span><span class="sxs-lookup"><span data-stu-id="c9507-234">When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

![Icona del numero 2, che fa riferimento a un callout nella schermata precedente](media/sfbcallout2.png)

<span data-ttu-id="c9507-236">**Quando viene raggiunto il numero massimo di chiamate** Quando la coda di chiamata raggiunge le dimensioni massime (impostate usando le **chiamate massime nell'impostazione della coda** ), è possibile scegliere cosa succede alle nuove chiamate in arrivo.</span><span class="sxs-lookup"><span data-stu-id="c9507-236">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="c9507-237">**Disconnetti** La chiamata verrà disconnessa.</span><span class="sxs-lookup"><span data-stu-id="c9507-237">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="c9507-238">**Reindirizza a** Quando si sceglie questo pulsante, selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9507-238">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="c9507-239">**Persona nella tua azienda** Un utente online con una licenza di **sistema telefonico** ed essere abilitato per VoIP aziendale o avere un piano per le chiamate.</span><span class="sxs-lookup"><span data-stu-id="c9507-239">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="c9507-240">Puoi impostarla in modo che la persona che chiama possa essere passata alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="c9507-240">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="c9507-241">A questo scopo, seleziona una **persona nella tua azienda** e imposta questa persona affinché le chiamate vengano inoltrate direttamente alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="c9507-241">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="c9507-242">Per informazioni sulle licenze necessarie per la segreteria telefonica, vedere [configurare la segreteria telefonica cloud](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="c9507-242">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="c9507-243">**Applicazione vocale** Selezionare il nome di una coda di chiamata o di un operatore automatico già creato.</span><span class="sxs-lookup"><span data-stu-id="c9507-243">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

* * *

![Icona del numero 3, che fa riferimento a un callout nella schermata precedente](media/sfbcallout3.png)

<span data-ttu-id="c9507-245">**Timeout chiamata: tempo massimo di attesa** Puoi anche decidere quanto tempo può rimanere in attesa di una chiamata nella coda prima che venga interrotto e debba essere reindirizzato o disconnesso.</span><span class="sxs-lookup"><span data-stu-id="c9507-245">**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="c9507-246">La destinazione è basata sull'impostazione **Quando una chiamata va in timeout**.</span><span class="sxs-lookup"><span data-stu-id="c9507-246">Where it will be redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="c9507-247">Puoi impostare un tempo da 0 a 45 minuti.</span><span class="sxs-lookup"><span data-stu-id="c9507-247">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="c9507-248">Puoi impostare il valore di timeout in secondi, a intervalli di 15 secondi.</span><span class="sxs-lookup"><span data-stu-id="c9507-248">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="c9507-249">In questo modo è possibile modificare il flusso delle chiamate con maggiore granularità.</span><span class="sxs-lookup"><span data-stu-id="c9507-249">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="c9507-250">Ad esempio, puoi specificare che le chiamate non risposte da un agente entro 30 secondi passa a un operatore automatico di ricerca della directory.</span><span class="sxs-lookup"><span data-stu-id="c9507-250">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

![Icona del numero 4, che fa riferimento a un callout nella schermata precedente](media/sfbcallout4.png)

<span data-ttu-id="c9507-252">**Timeout chiamata** Quando la chiamata raggiunge il limite impostato sul periodo di **attesa di una chiamata nell'impostazione della coda** , è possibile scegliere cosa succede a questa chiamata:</span><span class="sxs-lookup"><span data-stu-id="c9507-252">**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>

- <span data-ttu-id="c9507-253">**Disconnetti** La chiamata verrà disconnessa.</span><span class="sxs-lookup"><span data-stu-id="c9507-253">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="c9507-254">**Reindirizzare la chiamata a** Quando si sceglie questa opzione, saranno disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9507-254">**Redirect this call to** When you choose this, you will have these options:</span></span>
  - <span data-ttu-id="c9507-255">**Persona nella tua azienda** Un utente online con una licenza di **sistema telefonico** ed essere abilitato per VoIP aziendale o per avere piani di chiamata.</span><span class="sxs-lookup"><span data-stu-id="c9507-255">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="c9507-256">Puoi impostarla in modo che la persona che chiama possa essere passata alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="c9507-256">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="c9507-257">A questo scopo, seleziona una **persona nella tua azienda** e imposta questa persona affinché le chiamate vengano inoltrate direttamente alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="c9507-257">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="c9507-258">Per informazioni sulle licenze necessarie per la segreteria telefonica, vedere [configurare la segreteria telefonica cloud](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="c9507-258">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="c9507-259">**Applicazione vocale** Selezionare il nome di una coda di chiamata o di un operatore automatico già creato.</span><span class="sxs-lookup"><span data-stu-id="c9507-259">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

## <a name="changing-a-users-caller-id-for-outbound-calls"></a><span data-ttu-id="c9507-260">Modifica dell'ID chiamante di un utente per le chiamate in uscita</span><span class="sxs-lookup"><span data-stu-id="c9507-260">Changing a user's Caller ID for outbound calls</span></span>

<span data-ttu-id="c9507-261">Puoi proteggere l'identità di un utente modificando l'ID chiamante per le chiamate in uscita in una coda di chiamata, un operatore automatico o un numero di servizio creando un criterio usando il cmdlet **New-CsCallingLineIdentity** .</span><span class="sxs-lookup"><span data-stu-id="c9507-261">You can protect a user's identity by changing their caller ID for outbound calls to a call queue, auto attendant, or any service number instead by creating a policy using the **New-CsCallingLineIdentity** cmdlet.</span></span>

<span data-ttu-id="c9507-262">Per farlo, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c9507-262">To do this, run:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="c9507-263">Quindi applica il criterio per l'utente utilizzando il cmdlet \*\* Grant-CallingLineIdentity.\*\*</span><span class="sxs-lookup"><span data-stu-id="c9507-263">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet.</span></span> <span data-ttu-id="c9507-264">Per farlo, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c9507-264">To do this, run:</span></span>
 
``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="c9507-265">Per altre informazioni su come modificare le impostazioni dell'ID chiamante nell'organizzazione [, vedere come si può usare l'ID chiamante nell'organizzazione](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="c9507-265">You can get more information on how to make changes to caller ID settings in your organization in the article [How can caller ID be used in your organization](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="c9507-266">Cmdlet della coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="c9507-266">Call queue cmdlets</span></span>

<span data-ttu-id="c9507-267">Puoi anche utilizzare Windows PowerShell per creare e configurare code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="c9507-267">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="c9507-268">Questi sono i cmdlet necessari per gestire una coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="c9507-268">Here are the cmdlets that you need to manage a call queue.</span></span>
 
- [<span data-ttu-id="c9507-269">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="c9507-269">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="c9507-270">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="c9507-270">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="c9507-271">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="c9507-271">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="c9507-272">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="c9507-272">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="c9507-273">Altre informazioni su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9507-273">More about Windows PowerShell</span></span>

- <span data-ttu-id="c9507-274">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="c9507-274">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="c9507-275">Con Windows PowerShell è possibile gestire Office 365 e Microsoft teams usando un unico punto di amministrazione in grado di semplificare il lavoro quotidiano, quando si hanno più attività da eseguire.</span><span class="sxs-lookup"><span data-stu-id="c9507-275">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="c9507-276">Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="c9507-276">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="c9507-277">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c9507-277">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="c9507-278">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="c9507-278">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="c9507-279">Windows PowerShell offre numerosi vantaggi in termini di velocità, semplicità e produttività solo con l'interfaccia di amministrazione di Microsoft teams, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="c9507-279">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft Teams admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="c9507-280">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="c9507-280">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="c9507-281">Gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9507-281">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="c9507-282">Configurare il computer per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9507-282">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="c9507-283">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="c9507-283">Related topics</span></span>

[<span data-ttu-id="c9507-284">Ecco cosa offre il Sistema telefonico in Office 365</span><span class="sxs-lookup"><span data-stu-id="c9507-284">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="c9507-285">Recupero di numeri di telefono del servizio</span><span class="sxs-lookup"><span data-stu-id="c9507-285">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="c9507-286">Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica</span><span class="sxs-lookup"><span data-stu-id="c9507-286">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="c9507-287">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="c9507-287">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
