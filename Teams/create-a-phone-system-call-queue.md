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
ms.openlocfilehash: 2744a989225098b47814c53cb089de7a0ee6cfe4
ms.sourcegitcommit: a47bd5194672820380d30722b60779ce2d8a8f78
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "41664375"
---
# <a name="create-a-cloud-call-queue"></a><span data-ttu-id="9dcdc-103">Creare una coda delle chiamate nel cloud</span><span class="sxs-lookup"><span data-stu-id="9dcdc-103">Create a Cloud call queue</span></span>

<span data-ttu-id="9dcdc-104">Le code delle chiamate cloud possono essere fornite:</span><span class="sxs-lookup"><span data-stu-id="9dcdc-104">Cloud call queues can provide:</span></span>

- <span data-ttu-id="9dcdc-105">Messaggio di saluto.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-105">A greeting message.</span></span>
- <span data-ttu-id="9dcdc-106">Musica mentre le persone sono in attesa.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-106">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="9dcdc-107">Reindirizzamento delle chiamate per chiamare gli agenti in liste di distribuzione via mail e gruppi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-107">Redirecting calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="9dcdc-108">Impostazione di parametri diversi, ad esempio la dimensione massima della coda, il timeout e le opzioni di gestione delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-108">Setting different parameters such as queue maximum size, timeout, and call handling options.</span></span>
- <span data-ttu-id="9dcdc-109">Segreteria telefonica condivisa per i chiamanti per l'uscita di un messaggio per un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-109">Shared voicemail for callers to leave a message for an organization.</span></span>

<span data-ttu-id="9dcdc-110">Non si associa direttamente un numero di telefono a una coda di chiamata, ma il numero di telefono è associato a un [account delle risorse](manage-resource-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="9dcdc-110">You don't directly associate a phone number to a call queue, instead the phone number is associated to a [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="9dcdc-111">Una coda di chiamata può essere chiamata direttamente o accessibile tramite una selezione in un operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-111">A call queue can be dialed directly or accessed by a selection on an auto attendant.</span></span>

<span data-ttu-id="9dcdc-112">Il chiamante sente la musica mentre è in attesa e la chiamata si connette agli agenti di chiamata in ordine *First in, First out* (FIFO).</span><span class="sxs-lookup"><span data-stu-id="9dcdc-112">The caller hears music while they are on hold, and the call connects to the call agents in *First In, First Out* (FIFO) order.</span></span>

<span data-ttu-id="9dcdc-113">Tutte le chiamate nella coda vengono inviate agli agenti da uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="9dcdc-113">All calls in the queue are sent to agents by one of the following methods:</span></span>

- <span data-ttu-id="9dcdc-114">Con il routing di Attendant, la prima chiamata nella coda squilla tutti gli agenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-114">With attendant routing, the first call in the queue  rings all agents at the same time.</span></span>
- <span data-ttu-id="9dcdc-115">Con il routing seriale, la prima chiamata nella coda squilla tutti gli agenti di chiamata uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-115">With serial routing, the first call in the queue rings all call agents one by one.</span></span>
- <span data-ttu-id="9dcdc-116">Con Round Robin, il routing delle chiamate in arrivo è bilanciato in modo che ogni agente di chiamata ottenga lo stesso numero di chiamate dalla coda.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-116">With round robin, routing of incoming calls is balanced so that each call agent gets the same number of calls from the queue.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9dcdc-117">Gli agenti di chiamata **offline**, hanno impostato la loro presenza su non **disturbare** o hanno scelto di non ricevere chiamate nella coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-117">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue will not recieve calls.</span></span>

- <span data-ttu-id="9dcdc-118">Solo una notifica di chiamata in arrivo (per la chiamata a capo della coda) alla volta passa agli agenti di chiamata.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-118">Only one incoming call notification (for the call at the head of the queue) at a time goes to the call agents.</span></span>
- <span data-ttu-id="9dcdc-119">Una volta che un agente di chiamata accetta la chiamata, la prossima chiamata in arrivo in coda viene segnalata agli agenti di chiamata.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-119">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="9dcdc-120">Questo articolo si applica sia a Microsoft teams che a Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-120">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="9dcdc-121">Passaggio 1: iniziare</span><span class="sxs-lookup"><span data-stu-id="9dcdc-121">Step 1 — Get started</span></span>

<span data-ttu-id="9dcdc-122">Per iniziare a utilizzare le code di chiamata, è importante ricordare quanto segue.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-122">To get started using call queues, it's important to remember a few things:</span></span>

- <span data-ttu-id="9dcdc-123">È necessaria una coda di chiamata per avere un account di risorse associato.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-123">A call queue is required to have an associated resource account.</span></span> <span data-ttu-id="9dcdc-124">Per informazioni dettagliate sugli account delle risorse, vedere [gestire gli account delle risorse in teams](manage-resource-accounts.md) .</span><span class="sxs-lookup"><span data-stu-id="9dcdc-124">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="9dcdc-125">Quando si assegna un numero di telefono a un account delle risorse, è ora possibile usare la licenza per gli [utenti virtuali](teams-add-on-licensing/virtual-user.md)del sistema telefonico senza costi.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-125">When you assign a phone number to a resource account, you can now use the cost-free Phone System [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span> <span data-ttu-id="9dcdc-126">Sistema telefonico consente di usare i numeri di telefono a livello di organizzazione per l'operatore automatico a basso costo e i servizi di Accodamento chiamate.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-126">Phone System allows phone numbers at the organizational level for use with low-cost auto attendant and call queue services.</span></span>

> [!NOTE]
> <span data-ttu-id="9dcdc-127">I numeri di servizio di routing diretto per le code di chiamata sono supportati solo per gli utenti e gli agenti di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-127">Direct Routing service numbers for call queues are supported for Microsoft Teams users and agents only.</span></span>

> [!NOTE]
> <span data-ttu-id="9dcdc-128">Per reindirizzare le chiamate alle persone dell'organizzazione online, devono avere una licenza per il **sistema telefonico** e essere abilitate per VoIP aziendale o avere piani di chiamata di Office 365.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-128">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="9dcdc-129">Vedere [assegnare le licenze di Microsoft teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="9dcdc-129">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="9dcdc-130">Per abilitare VoIP aziendale, è possibile utilizzare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-130">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="9dcdc-131">Ad esempio, Esegui:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="9dcdc-131">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="9dcdc-132">Per altre informazioni sui piani di chiamate di Office 365, vedere [sistemi di telefonia e](calling-plan-landing-page.md) piani di chiamata e [piani di chiamata per Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="9dcdc-132">To learn more about Office 365 Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

- <span data-ttu-id="9dcdc-133">È possibile assegnare solo i numeri di telefono a pedaggio e numero verde delle code di chiamate cloud disponibili nell'interfaccia di **amministrazione di Microsoft teams** o trasferiti da un altro provider di servizi.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-133">You can only assign Cloud call queues toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider.</span></span> <span data-ttu-id="9dcdc-134">I crediti per le comunicazioni sono necessari per i numeri di servizio gratuiti.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-134">Communications Credits are required for toll-free service numbers.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9dcdc-135">I numeri di telefono di utenti (abbonati) non possono essere assegnati a code di chiamata, ma solo numeri di telefono di servizio a pagamento o numeri verdi.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-135">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>

- <span data-ttu-id="9dcdc-136">I client seguenti sono supportati per gli agenti di chiamata associati a una coda di chiamata cloud:</span><span class="sxs-lookup"><span data-stu-id="9dcdc-136">The following clients are supported for call agents associated to a Cloud call queue:</span></span>

  - <span data-ttu-id="9dcdc-137">Client desktop Skype for business 2016 (versioni 32 e 64 bit)</span><span class="sxs-lookup"><span data-stu-id="9dcdc-137">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="9dcdc-138">Client desktop Lync 2013 (versioni 32 e 64 bit)</span><span class="sxs-lookup"><span data-stu-id="9dcdc-138">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="9dcdc-139">Tutti i modelli di telefono IP supportati per Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-139">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="9dcdc-140">Vedere [ottenere telefoni per Skype for business online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="9dcdc-140">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>

  - <span data-ttu-id="9dcdc-141">Client Mac Skype for Business (versione 16.8.196 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="9dcdc-141">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="9dcdc-142">Client Android Skype for Business (versione 6.16.0.9 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="9dcdc-142">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="9dcdc-143">Client iPhone Skype for Business (versione 6.16.0 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="9dcdc-143">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="9dcdc-144">Client Mac Skype for Business (versione 6.16.0 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="9dcdc-144">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="9dcdc-145">Client Windows Microsoft Teams (versioni a 32 bit e 64 bit)</span><span class="sxs-lookup"><span data-stu-id="9dcdc-145">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="9dcdc-146">Client Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="9dcdc-146">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="9dcdc-147">App per iPhone di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9dcdc-147">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="9dcdc-148">App Microsoft teams Android</span><span class="sxs-lookup"><span data-stu-id="9dcdc-148">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="9dcdc-149">Le code di chiamata assegnate a un numero di routing diretto non supportano i client di Skype for business, i client Lync o i telefoni IP Skype for business come agenti.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-149">Call queues that are assigned a direct routing number will not support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="step-2--get-or-transfer-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="9dcdc-150">Passaggio 2: ottenere o trasferire numeri di servizio a pagamento o a numero verde</span><span class="sxs-lookup"><span data-stu-id="9dcdc-150">Step 2 — Get or transfer toll or toll-free service phone numbers</span></span>

<span data-ttu-id="9dcdc-151">Prima di poter creare e configurare le code di chiamata, è necessario ottenere o trasferire i numeri di servizio a pagamento o a pedaggio esistenti.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-151">Before you can create and set up your call queues, you need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="9dcdc-152">Per ottenere i numeri di servizio, vedere [recupero di numeri di telefono](getting-service-phone-numbers.md) o se si vuole trasferire un numero di servizio esistente, vedere trasferire i [numeri di telefono in Office 365](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="9dcdc-152">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span> <span data-ttu-id="9dcdc-153">Dopo aver ottenuto il pedaggio o i numeri di telefono del servizio gratuito, verranno visualizzati nei numeri di telefono della**segreteria** > **telefonica**dell'interfaccia di amministrazione > di **Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-153">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**.</span></span> <span data-ttu-id="9dcdc-154">I numeri verdi saranno elencati con un **tipo** di servizio numero **-gratuito**.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-154">Toll free numbers will be listed with a **Number type** of **Service — Toll-Free**.</span></span>

> [!NOTE]
> <span data-ttu-id="9dcdc-155">Se si è al di fuori degli Stati Uniti, non è possibile usare l'interfaccia di amministrazione di Microsoft teams per ottenere i numeri di servizio.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-155">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="9dcdc-156">Vai a [gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) per vedere come farlo dall'esterno degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-156">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="9dcdc-157">Quando si configurano più operatori automatici, in genere si assegna un numero di telefono all'account delle risorse dell'operatore automatico principale.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-157">When you set up multiple auto attendants, you would usually assign a phone number to the main auto attendant's resource account.</span></span> <span data-ttu-id="9dcdc-158">Gli account delle risorse associati agli operatori automatici annidati o alle code di chiamata spesso non hanno bisogno di numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-158">Resource accounts associated to nested auto attendants or call queues often don't need phone numbers.</span></span> <span data-ttu-id="9dcdc-159">L'operatore automatico può indirizzare i chiamanti alle code di chiamata o agli operatori automatici annidati anche se non hanno un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-159">That auto attendant can direct callers to your call queues or nested auto attendants even if they don't have a phone number.</span></span> <span data-ttu-id="9dcdc-160">In questi casi, è possibile creare tutti gli operatori automatici e le code di chiamata nel sistema senza assegnare le opzioni del tastierino e quindi modificare le impostazioni in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-160">In those situations, you can create all auto attendants and call queues in your system without assigning dialpad options, and then edit the settings later.</span></span> <span data-ttu-id="9dcdc-161">Una coda di chiamata o un operatore automatico deve esistere per impostarla come opzione di menu.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-161">A call queue or auto attendant must exist to set it as a menu option.</span></span>

## <a name="step-3--create-a-call-queue"></a><span data-ttu-id="9dcdc-162">Passaggio 3: creare una coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="9dcdc-162">Step 3 — Create a call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="9dcdc-163">Ogni coda di chiamata è necessaria per avere un [account di risorse](manage-resource-accounts.md)associato.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-163">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="9dcdc-164">Devi prima creare l'account della risorsa, quindi puoi associarlo alla coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-164">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="use-the-microsoft-teams-admin-center"></a><span data-ttu-id="9dcdc-165">Usare l'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9dcdc-165">Use the Microsoft Teams admin center</span></span>

<span data-ttu-id="9dcdc-166">Nell'interfaccia di **amministrazione di Microsoft teams**,**code di chiamata** **vocale** > , quindi fare clic su **+ Aggiungi nuovo**:</span><span class="sxs-lookup"><span data-stu-id="9dcdc-166">In the **Microsoft Teams admin center**, **Voice** > **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-display-name-and-resource-account"></a><span data-ttu-id="9dcdc-167">Impostare il nome visualizzato e l'account delle risorse</span><span class="sxs-lookup"><span data-stu-id="9dcdc-167">Set the display name and resource account</span></span>

![Screenshot di una nuova coda di chiamata, con callout numerati](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="9dcdc-169">![Icona del numero 1, fa riferimento a un callout nel](media/teamscallout1.png)
**nome** dello screenshot precedente immettere un nome visualizzato descrittivo per la coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-169">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="9dcdc-170">Questo nome è obbligatorio e può contenere fino a 64 caratteri, inclusi gli spazi.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-170">This name is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="9dcdc-171">Questo nome viene visualizzato nella notifica per la chiamata in arrivo.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-171">This name is displayed in the notification for the incoming call.</span></span>

* * *

<span data-ttu-id="9dcdc-172">![Icona del numero 2, fa riferimento a un callout nello screenshot](media/teamscallout2.png)
precedente**Aggiungi account** Selezionare un account di risorse.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-172">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="9dcdc-173">Per avere un account delle risorse sono necessarie tutte le code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-173">All call queues are required to have a resource account.</span></span> <span data-ttu-id="9dcdc-174">Gli account delle risorse non sono obbligatori per avere un numero di telefono a pagamento o senza pedaggio.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-174">Resource accounts aren't required to have a service toll or toll-free phone number.</span></span>

<span data-ttu-id="9dcdc-175">Se non sono presenti elenchi, ottenere i numeri di servizio e assegnarli a un account di risorse prima di creare la coda di chiamata, come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-175">If there aren't any listed,  get service numbers and assign them to a Resource account before you create the call queue, as described earlier.</span></span> <span data-ttu-id="9dcdc-176">Per ottenere i numeri di servizio, vedere [ottenere i numeri di telefono del servizio](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="9dcdc-176">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span> <span data-ttu-id="9dcdc-177">Vedere [gestire gli account delle risorse in teams](manage-resource-accounts.md) per informazioni specifiche su come assegnare un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-177">See [Manage resource accounts in Teams](manage-resource-accounts.md) for specifics on how to assign a phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="9dcdc-178">Se si vuole o è necessario assegnare un **dominio** , assegnarlo all'account delle risorse per la coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-178">If you want or need to assign a **Domain** you would  assign it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="9dcdc-179">Impostare il saluto e la musica durante l'attesa</span><span class="sxs-lookup"><span data-stu-id="9dcdc-179">Set the greeting and music played while on hold</span></span>

![screenshot delle opzioni di saluto e musica, con callout numerati](media/1d395a93-7cab-4178-9295-12d5379e20de.png)

* * *

<span data-ttu-id="9dcdc-181">![Icona del numero 1, fa riferimento a un callout nello screenshot](media/teamscallout1.png)
precedente che**saluta** il messaggio di saluto facoltativo riprodotto per le persone che chiamano il numero della coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-181">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Greeting** the optional greeting played for people who call the call queue number.</span></span>

<span data-ttu-id="9dcdc-182">È possibile caricare un file audio (formati. wav,. mp3 o. WMA).</span><span class="sxs-lookup"><span data-stu-id="9dcdc-182">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

<span data-ttu-id="9dcdc-183">![Icona del numero 2, fa riferimento a un callout nella schermata](media/teamscallout2.png)
precedente musica in**attesa** è possibile usare la musica predefinita in attesa fornita con la coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-183">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**Music on hold** You can use the default Music on Hold provided with the call queue.</span></span> <span data-ttu-id="9dcdc-184">È anche possibile caricare un file audio in formato WAV, MP3 o WMA da usare come musica personalizzata in attesa.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-184">You can also upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="9dcdc-185">Selezionare le opzioni di segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="9dcdc-185">Select the call answering options</span></span>

![Screenshot delle opzioni di segreteria telefonica](media/5d249515-d532-4af2-90da-011404028b89.png) 

<span data-ttu-id="9dcdc-187">![Icona del numero 1, fa riferimento a un callout nello screenshot](media/teamscallout1.png)
precedente**chiamare agenti e gruppi** per aggiungere singoli agenti direttamente, senza aggiungerli a un gruppo, fare clic su **Aggiungi utenti**.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-187">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Call agents and groups** To add individual agents directly, without adding them to a group, click **Add users**.</span></span> <span data-ttu-id="9dcdc-188">Inserire singoli agenti nell'ordine in cui si vuole che ricevano la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-188">Put individual agents in the order in which you want them to receive the call.</span></span> <span data-ttu-id="9dcdc-189">È possibile aggiungere fino a 20 singoli agenti (per aggiungere più di 20, inserirli in un gruppo).</span><span class="sxs-lookup"><span data-stu-id="9dcdc-189">You can add up to 20 individual agents (to add more than 20, put them in a group).</span></span>

<span data-ttu-id="9dcdc-190">Le chiamate vengono instradate prima a singoli agenti, quindi agli agenti in gruppi.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-190">Calls are routed first to individual agents, then to the agents in groups.</span></span> 

<span data-ttu-id="9dcdc-191">È possibile selezionare fino a 200 gli agenti di chiamata che appartengono a una delle seguenti liste di distribuzione o gruppi:</span><span class="sxs-lookup"><span data-stu-id="9dcdc-191">You can select up to 200 call agents who belong to any of the following mailing lists or groups:</span></span>

- <span data-ttu-id="9dcdc-192">Gruppo Office 365</span><span class="sxs-lookup"><span data-stu-id="9dcdc-192">Office 365 group</span></span>
- <span data-ttu-id="9dcdc-193">Gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="9dcdc-193">Security group</span></span>
- <span data-ttu-id="9dcdc-194">Elenco di distribuzione</span><span class="sxs-lookup"><span data-stu-id="9dcdc-194">Distribution list</span></span>

<span data-ttu-id="9dcdc-195">Gli agenti di chiamata selezionati devono essere:</span><span class="sxs-lookup"><span data-stu-id="9dcdc-195">Call agents selected must be:</span></span> 

- <span data-ttu-id="9dcdc-196">Utenti online con licenza di sistema telefonico e VoIP aziendale abilitato</span><span class="sxs-lookup"><span data-stu-id="9dcdc-196">Online users with a Phone System license and Enterprise Voice enabled</span></span> 
- <span data-ttu-id="9dcdc-197">Utenti online con un piano per le chiamate</span><span class="sxs-lookup"><span data-stu-id="9dcdc-197">Online users with a Calling Plan</span></span>
- <span data-ttu-id="9dcdc-198">Utenti di Skype for Business Server locale</span><span class="sxs-lookup"><span data-stu-id="9dcdc-198">On-premises Skype for Business Server users</span></span>

  > [!NOTE]
  > <span data-ttu-id="9dcdc-199">Questo vale anche se vuoi reindirizzare le chiamate agli utenti dell'organizzazione online.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-199">This also applies if you want to redirect calls to people in your organization who are online.</span></span> <span data-ttu-id="9dcdc-200">Questi utenti devono avere una licenza per il **sistema telefonico** e VoIP aziendale abilitato **o** avere un piano di chiamata.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-200">These individuals must have a **Phone System** license and Enterprise Voice enabled **or** have a Calling Plan.</span></span> <span data-ttu-id="9dcdc-201">Per altre informazioni, vedere [assegnare licenze Skype for business](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [assegnare licenze Microsoft teams](https://docs.microsoft.com/microsoftteams/assign-teams-licenses)o [quale piano per le chiamate è giusto per l'utente?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span><span class="sxs-lookup"><span data-stu-id="9dcdc-201">For more information, see [Assign Skype for Business licenses](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [Assign Microsoft Teams licenses](https://docs.microsoft.com/microsoftteams/assign-teams-licenses), or [Which Calling Plan is right for you?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span></span>

 <span data-ttu-id="9dcdc-202">Per abilitare un agente per VoIP aziendale, è possibile usare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-202">To enable an agent for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="9dcdc-203">Ad esempio, Esegui:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="9dcdc-203">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="9dcdc-204">Utenti con una licenza di **sistema telefonico** o un piano di chiamata aggiunto a un gruppo di Office 365; una lista di distribuzione abilitata per la posta elettronica; o un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-204">Users with a **Phone System** license or a Calling Plan that are added to either an Office 365 Group; a mail-enabled Distribution List; or a Security Group.</span></span> <span data-ttu-id="9dcdc-205">Quando si aggiunge un agente in una lista di distribuzione o un gruppo di sicurezza come agente della coda di chiamata, è possibile che la prima chiamata arrivi fino a tre ore.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-205">When you add an agent in a distribution list or a security group as a call queue agent, it can take up to three hours for the first call to arrive.</span></span> <span data-ttu-id="9dcdc-206">Una lista di distribuzione o un gruppo di sicurezza appena creato può richiedere fino a 48 ore per diventare disponibile per l'uso con le code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-206">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="9dcdc-207">I Gruppi di Office 365 appena creati sono disponibili quasi immediatamente.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-207">Newly created Office 365 Groups are available almost immediately.</span></span>

- <span data-ttu-id="9dcdc-208">Se gli agenti usano l'app Microsoft teams per le chiamate alla coda di chiamata, devono essere in modalità TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-208">If your agents are using the Microsoft Teams App for call queue calls, they need to be in TeamsOnly mode.</span></span>

<span data-ttu-id="9dcdc-209">![Icona del numero 2, fa riferimento a un callout nel metodo di](media/teamscallout2.png)
**routing** dello screenshot precedente è possibile **scegliere Attendant**, **seriale**o **Round Robin** come metodo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-209">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**Routing method** You can choose either **Attendant**, **Serial**, or **Round Robin** as the distribution method.</span></span> <span data-ttu-id="9dcdc-210">Tutte le code di chiamata nuove ed esistenti hanno il routing di Attendant selezionato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-210">All new and existing call queues have attendant routing selected by default.</span></span> <span data-ttu-id="9dcdc-211">Quando viene usato il routing di Attendant, la prima chiamata nella coda squilla tutti gli agenti di chiamata contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-211">When attendant routing is used, the first call in the queue rings all call agents at the same time.</span></span> <span data-ttu-id="9dcdc-212">Il primo agente di chiamata a prendere la chiamata riceve la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-212">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="9dcdc-213">Il **routing degli assistenti** fa sì che la prima chiamata nella coda squilli tutti gli agenti di chiamata contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-213">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="9dcdc-214">Il primo agente di chiamata a prendere la chiamata riceve la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-214">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="9dcdc-215">**Routing seriale** le chiamate in arrivo squillano tutti gli agenti di chiamata uno alla volta, dall'inizio dell'elenco agente chiamate.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-215">**Serial routing** incoming calls ring all call agents one by one, from the beginning of the call agent list.</span></span> <span data-ttu-id="9dcdc-216">Non è possibile ordinare gli agenti nell'elenco agente chiamate.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-216">Agents can't be ordered within the call agent list.</span></span> <span data-ttu-id="9dcdc-217">Se un agente respinge o non prende una chiamata, la chiamata suonerà l'agente successivo e proverà tutti gli agenti finché non viene prelevato o non viene ritirato.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-217">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>
  > [!NOTE]
  > <span data-ttu-id="9dcdc-218">Con il routing seriale, per gli agenti **offline** o che hanno impostato la loro presenza su **non disturbare**, la chiamata verrà instradata a tali utenti e non riesce a connettere l'utente non disponibile, il routing all'agente successivo nell'elenco degli agenti.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-218">With Serial routing, for agents who are **Offline** or have set their presence to **Do not Disturb**, the call will be routed to those users and fail to connect unavailable user, the routing to the next agent in the agent list.</span></span> <span data-ttu-id="9dcdc-219">Questo non è il caso se l'agente ha **scelto** di ricevere chiamate dalla coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-219">This is not the case if the agent has **opted out** of getting calls from the call queue.</span></span> <span data-ttu-id="9dcdc-220">Per ridurre l'intervallo di tempo che la chiamata instrada all'agente successivo in linea, il tempo di avviso dell'agente può essere ridotto.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-220">To reduce the time interval the call routes to next agent in line, Agent Alert time can be decreased.</span></span>
- <span data-ttu-id="9dcdc-221">**Round Robin** bilancia il routing delle chiamate in arrivo in modo che ogni agente di chiamata ottenga lo stesso numero di chiamate dalla coda.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-221">**Round robin** balances routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="9dcdc-222">Questo potrebbe essere auspicabile in un ambiente di vendita in entrata per assicurare la parità di opportunità tra tutti gli agenti di chiamata.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-222">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="9dcdc-223">Selezionare un'opzione di opt-out per l'agente</span><span class="sxs-lookup"><span data-stu-id="9dcdc-223">Select an agent opt-out option</span></span>

![Screenshot delle opzioni di opt-out per gli agenti, con callout numerati](media/99279eff-db61-4acf-9b62-64be84b6414b.png)

* * *

<span data-ttu-id="9dcdc-225">![Icona del numero 1, fa riferimento a un callout nell'agente di](media/teamscallout1.png)
screenshot precedente**può rifiutare di ricevere chiamate** per consentire agli agenti della coda di chiamata di rifiutare di accettare chiamate da una coda specifica abilitando questa opzione.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-225">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Agent can opt out of getting calls** You can choose to allow call queue agents to opt-out of taking calls from a particular queue by enabling this option.</span></span>

<span data-ttu-id="9dcdc-226">L'abilitazione di questa opzione consente a tutti gli agenti in questa coda di avviare o interrompere la ricezione delle chiamate da questa coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-226">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="9dcdc-227">Puoi revocare il privilegio di esclusione dell'agente in qualsiasi momento, deselezionando la casella di controllo, includendo nuovamente automaticamente tutti gli agenti a questa coda (impostazione predefinita per tutti gli agenti).</span><span class="sxs-lookup"><span data-stu-id="9dcdc-227">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="9dcdc-228">Per accedere all'opzione opt-out, gli agenti possono:</span><span class="sxs-lookup"><span data-stu-id="9dcdc-228">To access the opt-out option, agents can:</span></span>

 1. <span data-ttu-id="9dcdc-229">Aprire **Opzioni** nel proprio client desktop di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-229">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="9dcdc-230">Nella scheda **Inoltro chiamata** di chiamata, fare clic sul collegamento **Modifica impostazioni online**.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-230">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="9dcdc-231">Nella pagina impostazioni utente fare clic su **code di chiamata**e quindi deselezionare le caselle di controllo per escludere le code.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-231">On the user settings page, click **Call Queues**, and then clear the check boxes to opt-out of queues.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9dcdc-232">Gli agenti che usano app o endpoint diversi da Skype for business desktop possono accedere all'opzione opt-out dal portale [https://aka.ms/cqsettings](https://aka.ms/cqsettings)delle impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-232">Agents using apps or endpoints other than Skype for Business Desktop can access the opt-out option from the user settings portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span></span>
    >
    > <span data-ttu-id="9dcdc-233">Se gli agenti si trovano nei client desktop di Microsoft teams, possono rifiutare l'opt-out usando le impostazioni di chiamata.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-233">If the agents are in Microsoft Teams desktop clients, then they can opt-out by using the Call Settings.</span></span> 

<span data-ttu-id="9dcdc-234">![Icona del numero 2, fa riferimento a un callout nell'impostazione di](media/teamscallout2.png)
**avviso dell'agente** screenshot precedente</span><span class="sxs-lookup"><span data-stu-id="9dcdc-234">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="9dcdc-235">In questo modo viene definita la durata di un agente notificato di una chiamata prima che i metodi di routing seriale o Round Robin vengano spostati nell'agente successivo.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-235">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="9dcdc-236">L'impostazione predefinita è 30 secondi, ma può essere impostata per un massimo di 3 minuti.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-236">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="9dcdc-237">Impostare le opzioni di gestione di overflow e timeout delle chiamate</span><span class="sxs-lookup"><span data-stu-id="9dcdc-237">Set the call overflow and timeout handling options</span></span>

![Screenshot delle opzioni di gestione dell'overflow, con callout numerati](media/3f018734-16fe-458b-827d-71fc25155cde.png)

* * *

<span data-ttu-id="9dcdc-239">![Icona del numero 1, fa riferimento a un callout nelle](media/teamscallout1.png)
**chiamate massime** dello screenshot precedente nella coda usare questa impostazione per impostare le chiamate massime che possono essere attese contemporaneamente nella coda.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-239">![Icon of the number 1, references a callout in the previous screenshot](media/teamscallout1.png)
**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="9dcdc-240">Il valore predefinito è 50, ma può variare da 0 a 200.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-240">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="9dcdc-241">Quando viene raggiunto questo limite, la chiamata viene gestita nel modo in cui viene impostata la posizione in **cui viene raggiunto il numero massimo di chiamate** .</span><span class="sxs-lookup"><span data-stu-id="9dcdc-241">When this limit is reached, the call is handled in the way you set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

<span data-ttu-id="9dcdc-242">![Icona del numero 2, fa riferimento a un callout nello screenshot](media/teamscallout2.png)
precedente**quando il numero massimo di chiamate viene raggiunto** quando la coda di chiamata raggiunge la dimensione massima (impostata con le **chiamate massime nell'impostazione della coda** ), è possibile scegliere cosa succede alle nuove chiamate in arrivo.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-242">![Icon of the number 2, references a callout in the previous screenshot](media/teamscallout2.png)
**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="9dcdc-243">**Disconnetti** La chiamata è disconnessa.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-243">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="9dcdc-244">**Reindirizza a** Quando si sceglie questo pulsante, selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9dcdc-244">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="9dcdc-245">**Persona nella tua azienda** Un utente online con una licenza di **sistema telefonico** ed essere abilitato per VoIP aziendale o avere un piano per le chiamate.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-245">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="9dcdc-246">È possibile configurarlo in modo che il chiamante possa essere inviato alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-246">You can set it up so the caller can be sent to voicemail.</span></span> <span data-ttu-id="9dcdc-247">A questo scopo, seleziona una **persona nella tua azienda** e imposta questa persona affinché le chiamate vengano inoltrate direttamente alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-247">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="9dcdc-248">Per informazioni sulle licenze necessarie per la segreteria telefonica, vedere [configurare la segreteria telefonica cloud](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="9dcdc-248">To learn about licenses required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="9dcdc-249">**Applicazione vocale** Selezionare il nome di un account di risorsa associato a una coda di chiamata o a un operatore automatico già creato.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-249">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

* * *

<span data-ttu-id="9dcdc-250">![Icona del numero 3, fa riferimento a un callout nello screenshot](media/teamscallout3.png)
precedente**chiamata timeout: periodo di attesa massimo** è anche possibile decidere la quantità di tempo in cui una chiamata può essere mandata nella coda prima che venga interrotta e debba essere reindirizzata o disconnessa.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-250">![Icon of the number 3, references a callout in the previous screenshot](media/teamscallout3.png)
**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="9dcdc-251">Il punto in cui viene reindirizzato si basa su come impostare l'impostazione quando viene impostato il timeout **di una chiamata** .</span><span class="sxs-lookup"><span data-stu-id="9dcdc-251">Where it is redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="9dcdc-252">Puoi impostare un tempo da 0 a 45 minuti.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-252">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="9dcdc-253">Puoi impostare il valore di timeout in secondi, a intervalli di 15 secondi.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-253">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="9dcdc-254">In questo modo è possibile modificare il flusso delle chiamate con maggiore granularità.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-254">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="9dcdc-255">Ad esempio, puoi specificare che le chiamate non risposte da un agente entro 30 secondi passa a un operatore automatico di ricerca della directory.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-255">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

<span data-ttu-id="9dcdc-256">![Icona del numero 4, fa riferimento a un callout nello screenshot](media/teamscallout4.png)
precedente**quando** la chiamata supera il limite impostato nel periodo di **tempo in cui una chiamata può attendere nell'** impostazione della coda, è possibile scegliere cosa accade alla chiamata:</span><span class="sxs-lookup"><span data-stu-id="9dcdc-256">![Icon of the number 4, references a callout in the previous screenshot](media/teamscallout4.png)
**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to the call:</span></span>

- <span data-ttu-id="9dcdc-257">**Disconnetti** La chiamata è disconnessa.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-257">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="9dcdc-258">**Reindirizzare la chiamata a** Quando si sceglie questa opzione, sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9dcdc-258">**Redirect this call to** When you choose this, you have these options:</span></span>
  - <span data-ttu-id="9dcdc-259">**Persona nella tua azienda** Un utente online con una licenza di **sistema telefonico** ed essere abilitato per VoIP aziendale o per avere piani di chiamata.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-259">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="9dcdc-260">Per configurarlo in modo che la persona che chiama può essere inviata alla segreteria telefonica, selezionare una **persona nella società** e impostare questa persona per inoltrare le chiamate direttamente alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-260">To set it up so the person calling in can be sent to voicemail, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="9dcdc-261">Per informazioni sulle licenze necessarie per la segreteria telefonica, vedere [configurare la segreteria telefonica cloud](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="9dcdc-261">To learn about licenses required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="9dcdc-262">**App vocale** Selezionare il nome di un account di risorsa associato a una coda di chiamata o a un operatore automatico già creato.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-262">**Voice app** Select the name of a resource account associated with either a call queue or auto attendant that you already created.</span></span>

## <a name="change-caller-id-for-outbound-calls"></a><span data-ttu-id="9dcdc-263">Modificare l'ID chiamante per le chiamate in uscita</span><span class="sxs-lookup"><span data-stu-id="9dcdc-263">Change Caller ID for outbound calls</span></span>

<span data-ttu-id="9dcdc-264">Per proteggere l'identità di un agente di chiamata, modificare l'ID chiamante per le chiamate in uscita in una coda di chiamata, un operatore automatico o un numero di servizio con il cmdlet **New-CsCallingLineIdentity** , come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="9dcdc-264">To protect a call agent's identity, change their caller ID for outbound calls to a call queue, auto attendant, or any service number with the **New-CsCallingLineIdentity** cmdlet as in the following example:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="9dcdc-265">Applicare quindi il criterio all'utente con il cmdlet **Grant-CallingLineIdentity** , come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="9dcdc-265">Then apply the policy to the user with the **Grant-CallingLineIdentity** cmdlet as in the following example:</span></span> 

``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="9dcdc-266">Per altre informazioni, vedere [come può essere usato l'ID chiamante nell'organizzazione](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="9dcdc-266">For more information, see [How can caller ID be used in your organization](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="9dcdc-267">Cmdlet della coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="9dcdc-267">Call queue cmdlets</span></span>

<span data-ttu-id="9dcdc-268">Puoi anche utilizzare Windows PowerShell per creare e configurare code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-268">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="9dcdc-269">Ecco i cmdlet usati per gestire una coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-269">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="9dcdc-270">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="9dcdc-270">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="9dcdc-271">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="9dcdc-271">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="9dcdc-272">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="9dcdc-272">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="9dcdc-273">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="9dcdc-273">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="9dcdc-274">Altre informazioni su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9dcdc-274">More about Windows PowerShell</span></span>

- <span data-ttu-id="9dcdc-275">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-275">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="9dcdc-276">Con Windows PowerShell è possibile gestire Office 365 e Microsoft teams con un unico punto di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-276">With Windows PowerShell, you can manage Office 365 and Microsoft Teams with a single point of administration.</span></span> <span data-ttu-id="9dcdc-277">Può semplificare il lavoro quotidiano, quando si hanno più attività da eseguire.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-277">It can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="9dcdc-278">Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="9dcdc-278">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="9dcdc-279">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="9dcdc-279">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="9dcdc-280">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="9dcdc-280">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="9dcdc-281">Windows PowerShell offre numerosi vantaggi in velocità, semplicità e produttività nell'interfaccia di amministrazione di Microsoft teams quando si apportano modifiche per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="9dcdc-281">Windows PowerShell has many advantages in speed, simplicity, and productivity over the Microsoft Teams admin center when you make changes for many users at once.</span></span> <span data-ttu-id="9dcdc-282">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="9dcdc-282">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="9dcdc-283">Gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9dcdc-283">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="9dcdc-284">Configurare il computer per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9dcdc-284">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="9dcdc-285">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="9dcdc-285">Related topics</span></span>

[<span data-ttu-id="9dcdc-286">Ecco cosa offre il Sistema telefonico in Office 365</span><span class="sxs-lookup"><span data-stu-id="9dcdc-286">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

<span data-ttu-id="9dcdc-287">[Recuperare numeri di telefono del servizio](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="9dcdc-287">[Getting service phone numbers](getting-service-phone-numbers.md)</span></span>

[<span data-ttu-id="9dcdc-288">Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica</span><span class="sxs-lookup"><span data-stu-id="9dcdc-288">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="9dcdc-289">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="9dcdc-289">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
