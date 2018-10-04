---
title: Creare una coda di chiamata del Sistema telefonico
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: "Informazioni su come configurare Sistema telefonico per le code di chiamata di Office 365 (Cloud PBX) per fornire un messaggio di saluto, una musica di attesa e per reindirizzare le chiamate ad agenti nelle liste di distribuzione e gruppi di protezione dell'organizzazione. È inoltre possibile impostare la dimensione massima della coda, il timeout e le opzioni di gestione delle chiamate. "
ms.openlocfilehash: 1952d6d180f5b9662b1e598ceb9d0b8d230640c2
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375150"
---
# <a name="create-a-phone-system-call-queue"></a><span data-ttu-id="6bd61-104">Creare una coda di chiamata del Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="6bd61-104">Create a Phone System call queue</span></span>

<span data-ttu-id="6bd61-p102">Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold. You can create single or multiple call queues for your organization.</span><span class="sxs-lookup"><span data-stu-id="6bd61-p102">Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold. You can create single or multiple call queues for your organization.</span></span>
  
<span data-ttu-id="6bd61-107">Le code di chiamata di Sistema possono fornire:</span><span class="sxs-lookup"><span data-stu-id="6bd61-107">Phone System call queues can provide:</span></span>
  
- <span data-ttu-id="6bd61-108">Un saluto aziendale.</span><span class="sxs-lookup"><span data-stu-id="6bd61-108">An organizational greeting.</span></span>
    
- <span data-ttu-id="6bd61-109">Musica mentre le persone sono in attesa.</span><span class="sxs-lookup"><span data-stu-id="6bd61-109">Music while people are waiting on hold.</span></span>
    
- <span data-ttu-id="6bd61-110">Reindirizzamento delle chiamate per chiamare agenti in gruppi di protezione e le liste di distribuzione abilitati alla posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="6bd61-110">Redirecting of calls to call agents in mail-enabled distribution lists and security groups.</span></span>
    
- <span data-ttu-id="6bd61-111">Configurare le impostazioni per la dimensione massima della coda di chiamata, timeout e le opzioni di gestione delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="6bd61-111">Making settings for call queue maximum size, timeout, and call handling options.</span></span>
    
<span data-ttu-id="6bd61-p103">When someone calls in to a phone number that is set up up with a call queue, they will hear a greeting first (if any is set up), and then they will be put in the queue and wait for the next available call agent. The person calling in will hear music while they are on hold waiting, and the calls will be offered to the call agents in the  *First In, First Out*  (FIFO) manner.</span><span class="sxs-lookup"><span data-stu-id="6bd61-p103">When someone calls in to a phone number that is set up up with a call queue, they will hear a greeting first (if any is set up), and then they will be put in the queue and wait for the next available call agent. The person calling in will hear music while they are on hold waiting, and the calls will be offered to the call agents in the  *First In, First Out*  (FIFO) manner.</span></span>
  
<span data-ttu-id="6bd61-114">Tutte le chiamate in attesa nella coda verranno distribuite tramite una modalità routing operatore oppure la modalità di routing seriale:</span><span class="sxs-lookup"><span data-stu-id="6bd61-114">All calls waiting in the queue will be distributed using an attendant routing mode or serial routing mode:</span></span>
  
- <span data-ttu-id="6bd61-115">Con l'operatore di routing, la prima chiamata nella coda deve squillare tutti gli agenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="6bd61-115">With attendant routing, the first call in the queue will ring all agents at the same time.</span></span>
    
- <span data-ttu-id="6bd61-116">Con l'instradamento seriale, la prima chiamata della squillerà a tutti gli agenti di chiamata uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="6bd61-116">With serial routing, the first call in the queue will ring all call agents one by one.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6bd61-117">Non verranno chiamati agli agenti chiamata che sono **Non in linea**, che hanno impostato la presenza su **Non disturbare,** oppure sono usciti dalla coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="6bd61-117">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue won't be called.</span></span>
  
- <span data-ttu-id="6bd61-118">Solo una notifica di chiamata in arrivo (per la chiamata in cima alla coda) per volta viene inviata agli agenti di chiamata.</span><span class="sxs-lookup"><span data-stu-id="6bd61-118">Only one incoming call notification (for the call at the head of the queue) at a time will be sent to the call agents.</span></span>
    
- <span data-ttu-id="6bd61-119">Una volta che un agente di chiamata accetta la chiamata, la prossima chiamata in arrivo in coda viene segnalata agli agenti di chiamata.</span><span class="sxs-lookup"><span data-stu-id="6bd61-119">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>
    
## <a name="step-1---getting-started"></a><span data-ttu-id="6bd61-120">Fase 1 - Attività iniziali</span><span class="sxs-lookup"><span data-stu-id="6bd61-120">Step 1 - Getting started</span></span>

<span data-ttu-id="6bd61-121">Per iniziare a utilizzare le code di chiamata, è importante ricordare quanto segue.</span><span class="sxs-lookup"><span data-stu-id="6bd61-121">To get started using call queues, it's important to remember a few things:</span></span>
  
- <span data-ttu-id="6bd61-p104">Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license. The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for call queues. The number of call queues you can have is dependent on the number of **Phone System** and **Audio Conferencing** licenses that are assigned in your organization. To learn more about licensing, go [here](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="6bd61-p104">Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license. The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for call queues. The number of call queues you can have is dependent on the number of **Phone System** and **Audio Conferencing** licenses that are assigned in your organization. To learn more about licensing, go [here](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6bd61-p105">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). To enable them for Enterprise Voice, you can use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="6bd61-p105">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). To enable them for Enterprise Voice, you can use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="6bd61-130">Per ulteriori informazioni sui piani di chiamata di Office 365, consulta [Che cosa sono i Piani di chiamata in Office 365?](/microsoftteams/what-are-calling-plans-in-office-365)  e [Piani di chiamata per Office 365](/microsoftteams/calling-plans-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="6bd61-130">To learn more about Office 365 Calling Plans, see [What are Calling Plans in Office 365?](/microsoftteams/what-are-calling-plans-in-office-365) and [Calling Plans for Office 365](/microsoftteams/calling-plans-for-office-365).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6bd61-131">Gli utenti ospitati in locale con Lync Server 2010 non sono supportati come un agenti di coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="6bd61-131">Users hosted on-premises using Lync Server 2010 aren't supported as a Call Queue Agents.</span></span> 
  
- <span data-ttu-id="6bd61-p106">You can only assign toll and toll-free service phone numbers that you got in the **Skype for Business admin center** or transferred from another service provider to Phone System call queues. To get and use toll-free service numbers, you need to set up Communications Credits.</span><span class="sxs-lookup"><span data-stu-id="6bd61-p106">You can only assign toll and toll-free service phone numbers that you got in the **Skype for Business admin center** or transferred from another service provider to Phone System call queues. To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6bd61-134">I numeri di telefono di utenti (abbonati) non possono essere assegnati a code di chiamata, ma solo numeri di telefono di servizio a pagamento o numeri verdi.</span><span class="sxs-lookup"><span data-stu-id="6bd61-134">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span> 
  
- <span data-ttu-id="6bd61-135">Quando si distribuiscono le chiamate in arrivo dalla coda di chiamata di un sistema telefonico, questi client sono supportati per gli agenti di chiamata:</span><span class="sxs-lookup"><span data-stu-id="6bd61-135">When you are distributing the incoming calls from an Phone System call queue, these clients are supported for call agents:</span></span>
    
  - <span data-ttu-id="6bd61-136">Client desktop Skype for Business 2016 (versioni a 32 e 64 bit)</span><span class="sxs-lookup"><span data-stu-id="6bd61-136">Skype for Business desktop client 2016 (32 and 64-bit versions)</span></span>
    
  - <span data-ttu-id="6bd61-137">Client desktop Lync 2013 (versioni a 32 e 64 bit)</span><span class="sxs-lookup"><span data-stu-id="6bd61-137">Lync desktop client 2013 (32 and 64-bit versions)</span></span>
    
  - <span data-ttu-id="6bd61-p107">All IP phone models supported for Skype for Business Online. See [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="6bd61-p107">All IP phone models supported for Skype for Business Online. See [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).</span></span>
    
  - <span data-ttu-id="6bd61-140">Client Mac Skype for Business (versione 16.8.196 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="6bd61-140">Mac Skype for Business Client (version 16.8.196 and later)</span></span> 
    
  - <span data-ttu-id="6bd61-141">Client Android Skype for Business (versione 6.16.0.9 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="6bd61-141">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
    
  - <span data-ttu-id="6bd61-142">Client iPhone Skype for Business (versione 6.16.0 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="6bd61-142">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
    
  - <span data-ttu-id="6bd61-143">Client Mac Skype for Business (versione 6.16.0 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="6bd61-143">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="6bd61-144">Client Microsoft Teams Windows (versioni a 32 e 64 bit)</span><span class="sxs-lookup"><span data-stu-id="6bd61-144">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="6bd61-145">Client Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="6bd61-145">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="6bd61-146">Microsoft Teams iPhone app</span><span class="sxs-lookup"><span data-stu-id="6bd61-146">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="6bd61-147">Team di Microsoft app Android</span><span class="sxs-lookup"><span data-stu-id="6bd61-147">Microsoft Teams Android app</span></span>
    
## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="6bd61-148">Fase 2 - Ottenere o trasferire numeri di servizio a pagamento o a numero verde</span><span class="sxs-lookup"><span data-stu-id="6bd61-148">Step 2 - Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="6bd61-p108">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).</span><span class="sxs-lookup"><span data-stu-id="6bd61-p108">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6bd61-p109">If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go to [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.</span><span class="sxs-lookup"><span data-stu-id="6bd61-p109">If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go to [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.</span></span>
  
## <a name="step-3---create-a-new-call-queue"></a><span data-ttu-id="6bd61-154">Fase 3 - Creare una nuova coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="6bd61-154">Step 3 - Create a new Call Queue</span></span>

<span data-ttu-id="6bd61-155">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="6bd61-155">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="6bd61-156">Nell' **interfaccia di amministrazione di Skype for Business**, fai clic su **Instradamento chiamate** > **Code di chiamata**, poi fai clic su **Aggiungi nuovo**.</span><span class="sxs-lookup"><span data-stu-id="6bd61-156">In the **Skype for Business admin center**, click **Call routing** > **Call queues**, then click **Add new**:</span></span>
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a><span data-ttu-id="6bd61-157">Imposta il nome visualizzato della coda di chiamata, il numero di telefono e il dominio (se presente)</span><span class="sxs-lookup"><span data-stu-id="6bd61-157">Set the call queue display name, phone number and domain (if any)</span></span>

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
<span data-ttu-id="6bd61-159">![Numero 1](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="6bd61-159">![Number 1](../images/sfbcallout1.png)</span></span><br/>
<span data-ttu-id="6bd61-p110">**Nome** Immetti un nome visualizzato descrittivo per la coda di chiamata. È obbligatorio e può contenere fino a 64 caratteri, spazi inclusi.</span><span class="sxs-lookup"><span data-stu-id="6bd61-p110">**Name** Enter a descriptive display name for the call queue. This is required and can contain up to 64 characters, including spaces. </span></span><br/> <span data-ttu-id="6bd61-162">Questo nome verrà visualizzato nella notifica per la chiamata in arrivo.</span><span class="sxs-lookup"><span data-stu-id="6bd61-162">This name will be displayed in the notification for the incoming call.</span></span>
***
<span data-ttu-id="6bd61-163">![Numero 2](../images/sfbcallout2.png)</span><span class="sxs-lookup"><span data-stu-id="6bd61-163">![Number 2](../images/sfbcallout2.png)</span></span><br/><span data-ttu-id="6bd61-p111">**Phone number** Select a service toll or toll-free phone number for the call queue. This is optional. </span><span class="sxs-lookup"><span data-stu-id="6bd61-p111">**Phone number** Select a service toll or toll-free phone number for the call queue. This is optional. </span></span><br/> <span data-ttu-id="6bd61-p112">If there aren't any listed, you need to get service numbers before you can create this call queue. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="6bd61-p112">If there aren't any listed, you need to get service numbers before you can create this call queue. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md)</span></span>
***
<span data-ttu-id="6bd61-168">![Numero 3](../images/sfbcallout3.png)</span><span class="sxs-lookup"><span data-stu-id="6bd61-168">![Number 3](../images/sfbcallout3.png)</span></span><br/><span data-ttu-id="6bd61-p113">**Dominio** Se è disponibile, scegli il dominio di Office 365 che desideri utilizzare. Questa opzione è disponibile solo se disponi di più di un dominio utilizzato con Office 365. Se ne hai più di uno, devi scegliere il nome di dominio dall'elenco. </span><span class="sxs-lookup"><span data-stu-id="6bd61-p113">**Domain** If this is available, choose the Office 365 domain you want to use. This is only available if you have more than one domain being used with Office 365. If you have more than one, you must chose the domain name from the list. </span></span><br/> <span data-ttu-id="6bd61-172">Ad esempio, puoi avere un dominio come:  _contoso.com or redmond.contoso.com_</span><span class="sxs-lookup"><span data-stu-id="6bd61-172">For example, you could have a domain like:  _contoso.com or redmond.contoso.com_</span></span>
   
### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="6bd61-173">Impostare il saluto e la musica durante l'attesa</span><span class="sxs-lookup"><span data-stu-id="6bd61-173">Set the greeting and music played while on hold</span></span>

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
<span data-ttu-id="6bd61-175">![Numero 1](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="6bd61-175">![Number 1](../images/sfbcallout1.png)</span></span><br/><span data-ttu-id="6bd61-p114">**Greeting** is optional. This is the greeting that is played for people who call in to the call queue number. </span><span class="sxs-lookup"><span data-stu-id="6bd61-p114">**Greeting** is optional. This is the greeting that is played for people who call in to the call queue number. </span></span><br/> <span data-ttu-id="6bd61-178">È possibile caricare un file audio (formati. wav, MP3 o. wma).</span><span class="sxs-lookup"><span data-stu-id="6bd61-178">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>
***
<span data-ttu-id="6bd61-179">![Numero 2](../images/sfbcallout2.png)</span><span class="sxs-lookup"><span data-stu-id="6bd61-179">![Number 2](../images/sfbcallout2.png)</span></span><br/><span data-ttu-id="6bd61-180">**Musica di attesa** È possibile utilizzare l'impostazione predefinita, la musica di attesa fornita con la coda chiamata oppure è possibile caricare un file audio nel formato con estensione wav, mp3 o. wma da utilizzare come musica personalizzata in attesa.</span><span class="sxs-lookup"><span data-stu-id="6bd61-180">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span> 
   

### <a name="select-the-call-distribution-method"></a><span data-ttu-id="6bd61-181">Selezionare il metodo di distribuzione di chiamata</span><span class="sxs-lookup"><span data-stu-id="6bd61-181">Select the call distribution method</span></span>

![Mostra le opzioni per il metodo di distribuzione delle chiamate](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
<span data-ttu-id="6bd61-183">![Numero 1](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="6bd61-183">![Number 1](../images/sfbcallout1.png)</span></span><br/><span data-ttu-id="6bd61-p115">**Call distribution method** You can choose either **Attendant** or **Serial** for your call queue distribution method. All new and existing call queues will have attendant routing selected by default. To use serial routing, you must explicitly choose the **Serial** routing option in UI and cmdlets. </span><span class="sxs-lookup"><span data-stu-id="6bd61-p115">**Call distribution method** You can choose either **Attendant** or **Serial** for your call queue distribution method. All new and existing call queues will have attendant routing selected by default. To use serial routing, you must explicitly choose the **Serial** routing option in UI and cmdlets. </span></span><br/><br/> <span data-ttu-id="6bd61-p116">When serial routing is chosen and the call queue is saved, the calls from the queue will ring your agents one by one, starting from the beginning of the agent list. If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span><span class="sxs-lookup"><span data-stu-id="6bd61-p116">When serial routing is chosen and the call queue is saved, the calls from the queue will ring your agents one by one, starting from the beginning of the agent list. If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>   

> [!NOTE]
> <span data-ttu-id="6bd61-189">L'instradamento seriale ignorerà gli agenti che sono **Non in linea**, che hanno impostato la presenza su **Non disturbare**o hanno **Rinunciato** scegliendo di non ricevere chiamate da questa coda.</span><span class="sxs-lookup"><span data-stu-id="6bd61-189">Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span> 
   
### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="6bd61-190">Selezionare un opzione di esclusione</span><span class="sxs-lookup"><span data-stu-id="6bd61-190">Select an agent opt out option</span></span>

![Mostra la casella di controllo di esclusione](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
<span data-ttu-id="6bd61-192">![Numero 1](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="6bd61-192">![Number 1](../images/sfbcallout1.png)</span></span><br/><span data-ttu-id="6bd61-193">**Opzione esclusione agente** Puoi scegliere di consentire agli agenti di coda di chiamata di disattivare la risposta alle chiamate provenienti da una coda particolare selezionando **Opzione esclusione agente**.</span><span class="sxs-lookup"><span data-stu-id="6bd61-193">**Agent Opt out option** You can choose to allow call queue agents to opt out of taking calls from a particular queue by selecting **Agent Opt out option**.</span></span>  <br/> <span data-ttu-id="6bd61-p117">Enabling this option allows all agents in this queue to start or stop receiving call from this call queue at will. You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).  </span><span class="sxs-lookup"><span data-stu-id="6bd61-p117">Enabling this option allows all agents in this queue to start or stop receiving call from this call queue at will. You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).  </span></span><br/><br/> <span data-ttu-id="6bd61-196">Per accedere all'opzione di esclusione, gli agenti possono eseguire le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="6bd61-196">To access the opt-out option, agents can do the following:</span></span>
 1. <span data-ttu-id="6bd61-197">Aprire **Opzioni** nel proprio client desktop di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="6bd61-197">Open **Options** in their desktop Skype for Business client.</span></span> 
 2. <span data-ttu-id="6bd61-198">Nella scheda **Inoltro chiamata** di chiamata, fare clic sul collegamento **Modifica impostazioni online**.</span><span class="sxs-lookup"><span data-stu-id="6bd61-198">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="6bd61-199">Nella pagina Impostazioni utente, fare clic su **Coda chiamate** e quindi deselezionare le caselle di controllo per una o più code per cui desiderano consentire il modo esclusione.</span><span class="sxs-lookup"><span data-stu-id="6bd61-199">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt out.</span></span>
 
    > [!NOTE] 
    > <span data-ttu-id="6bd61-200">Agenti su Mac, mobile o client Lync 2013 o Hybrid Voice oppure utenti ospitati localmente con Skype per 2015 Business server, possono andare su [https://aka.ms/cqsettings](https://aka.ms/cqsettings) per accedere all'opzione di esclusione.</span><span class="sxs-lookup"><span data-stu-id="6bd61-200">Agents using Mac, mobile, or Lync 2013 clients, or Hybrid Voice users who are hosted on-premises using Skype for Business 2015 server, can go to [https://aka.ms/cqsettings](https://aka.ms/cqsettings) to access the opt out option.</span></span>
   
### <a name="add-call-agents-to-a-call-queue"></a><span data-ttu-id="6bd61-201">Aggiungere agenti di chiamata a una coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="6bd61-201">Add call agents to a call queue</span></span>

![Set up call queues.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![Numero 1](../images/sfbcallout1.png)<br/><br/><span data-ttu-id="6bd61-204">Gli agenti di chiamata (50 massimo) possono essere:</span><span class="sxs-lookup"><span data-stu-id="6bd61-204">Call agents (50 maximum) can be:</span></span>
* <span data-ttu-id="6bd61-205">Un utente in linea con una licenza di **Sistema telefonico** e abilitato per Enterprise Voice o con un Piano di chiamata.</span><span class="sxs-lookup"><span data-stu-id="6bd61-205">An Online user with a **Phone System** license and enabled for Enterprise Voice or with a Calling Plan.</span></span> <br/><br/> <span data-ttu-id="6bd61-p118">**Note:**  To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). To enable them for Enterprise Voice, you can use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="6bd61-p118">**Note:**  To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). To enable them for Enterprise Voice, you can use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span> <br/><br/>
* <span data-ttu-id="6bd61-p119">Online users with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group. It might take up to 30 minutes for a new agent added for a distribution list or a security group to start receiving calls from a call queue. A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues. Newly created Office 365 Groups are available almost immediately. </span><span class="sxs-lookup"><span data-stu-id="6bd61-p119">Online users with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group. It might take up to 30 minutes for a new agent added for a distribution list or a security group to start receiving calls from a call queue. A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues. Newly created Office 365 Groups are available almost immediately. </span></span><br/> 

  > [!NOTE] 
  > <span data-ttu-id="6bd61-214">Gli utenti ospitati in locale con Lync Server 2010 non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="6bd61-214">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span>           
   
### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a><span data-ttu-id="6bd61-215">Impostare la dimensione massima della coda e il tempo massimo di attesa</span><span class="sxs-lookup"><span data-stu-id="6bd61-215">Set the maximum queue size and maximum wait time</span></span>

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
<span data-ttu-id="6bd61-217">![Numero 1](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="6bd61-217">![Number 1](../images/sfbcallout1.png)</span></span><br/><br/><span data-ttu-id="6bd61-p120">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time. The default is 50, but it can range from 0 to 200.When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.</span><span class="sxs-lookup"><span data-stu-id="6bd61-p120">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time. The default is 50, but it can range from 0 to 200.When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.</span></span>
***
<span data-ttu-id="6bd61-220">![Numero 2](../images/sfbcallout2.png)</span><span class="sxs-lookup"><span data-stu-id="6bd61-220">![Number 2](../images/sfbcallout2.png)</span></span><br/><br/><span data-ttu-id="6bd61-221">**Quando viene raggiunto il numero massimo di chiamate** Quando la coda di chiamate raggiunge la dimensione massima (impostata utilizzando l'impostazione **massimo chiama nella coda** ), è possibile scegliere cosa accade a nuove chiamate in arrivo.</span><span class="sxs-lookup"><span data-stu-id="6bd61-221">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>
* <span data-ttu-id="6bd61-222">**Disconnetti con segnale di occupato** La chiamata verrà disconnessa.</span><span class="sxs-lookup"><span data-stu-id="6bd61-222">**Disconnect with a busy signal** The call will be disconnected.</span></span>
* <span data-ttu-id="6bd61-223">**Inoltrare la chiamata** Quando si sceglie questo, si disporrà di queste opzioni:</span><span class="sxs-lookup"><span data-stu-id="6bd61-223">**Forward this call to** When you choose this, you will have these options:</span></span>
  * <span data-ttu-id="6bd61-p121">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. </span><span class="sxs-lookup"><span data-stu-id="6bd61-p121">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. </span></span><br/> <br/><span data-ttu-id="6bd61-227">Per ulteriori informazioni sulle licenze necessarie per la segreteria telefonica, consulta [Configurare i messaggi vocali in Sistema telefonico](/microsoftteams/set-up-phone-system-voicemail).</span><span class="sxs-lookup"><span data-stu-id="6bd61-227">To learn about licensing required for voicemail, see [Set up Phone System voicemail](/microsoftteams/set-up-phone-system-voicemail).</span></span> 
     
    > [!Note]
    > <span data-ttu-id="6bd61-228">Gli utenti ospitati in locale con Lync Server 2010 non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="6bd61-228">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span><br/>
     
  * <span data-ttu-id="6bd61-229">**Coda di chiamata** È necessario avere già creato un'altra coda di chiamata, ma dopo aver eseguito, è possibile selezionare la coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="6bd61-229">**Call Queue** You must have already created another call queue, but after you do, you can select that call queue.</span></span>
  * <span data-ttu-id="6bd61-p122">**Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="6bd61-p122">**Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).</span></span>
***
<span data-ttu-id="6bd61-232">![Numero 3](../images/sfbcallout3.png)</span><span class="sxs-lookup"><span data-stu-id="6bd61-232">![Number 3](../images/sfbcallout3.png)</span></span><br/><br/><span data-ttu-id="6bd61-p123">**Quanto tempo può aspettare una chiamata in coda** Puoi anche decidere quanto tempo una chiamata può restare in attesa in coda prima che vada in timeout e debba essere reindirizzata o scollegata. La destinazione è basata sull'impostazione **Quando una chiamata va in timeout**. Puoi impostare un tempo da 0 a 45 minuti. </span><span class="sxs-lookup"><span data-stu-id="6bd61-p123">**How long a call can wait in the queue** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected. Where it will be redirected is based on how you set the **When a call times out** setting. You can set a time from 0 to 45 minutes. </span></span><br/><br/> <span data-ttu-id="6bd61-p124">The timeout value can be set in seconds, at 15-second intervals. This allows you to manipulate the call flow with finer granularity. For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search Auto Attendant.</span><span class="sxs-lookup"><span data-stu-id="6bd61-p124">The timeout value can be set in seconds, at 15-second intervals. This allows you to manipulate the call flow with finer granularity. For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search Auto Attendant.</span></span> 

***
<span data-ttu-id="6bd61-239">![Numero 4](../images/sfbcallout4.png)</span><span class="sxs-lookup"><span data-stu-id="6bd61-239">![Number 4](../images/sfbcallout4.png)</span></span><br/><br/><span data-ttu-id="6bd61-240">**Quando una chiamata va in timeout** Quando la chiamata raggiunge il limite impostato nell'impostazione **Quanto tempo può aspettare una chiamata in coda**, puoi scegliere cosa succede alla chiamata:</span><span class="sxs-lookup"><span data-stu-id="6bd61-240">**When a call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>
* <span data-ttu-id="6bd61-241">**Disconnetti** La chiamata verrà disconnessa.</span><span class="sxs-lookup"><span data-stu-id="6bd61-241">**Disconnect** The call will be disconnected.</span></span>
* <span data-ttu-id="6bd61-242">**Inoltrare la chiamata** Quando si sceglie questo, si disporrà di queste opzioni:</span><span class="sxs-lookup"><span data-stu-id="6bd61-242">**Forward this call to** When you choose this, you will have these options:</span></span>
  * <span data-ttu-id="6bd61-p125">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. </span><span class="sxs-lookup"><span data-stu-id="6bd61-p125">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. </span></span></br><br/>  <span data-ttu-id="6bd61-246">Per ulteriori informazioni sulle licenze necessarie per la segreteria telefonica, consulta [Configurare i messaggi vocali in Sistema telefonico](/microsoftteams/set-up-phone-system-voicemail).</span><span class="sxs-lookup"><span data-stu-id="6bd61-246">To learn about licensing required for voicemail, see [Set up Phone System voicemail](/microsoftteams/set-up-phone-system-voicemail).</span></span> 

    > [!Note]
    > <span data-ttu-id="6bd61-247">Gli utenti ospitati in locale con Lync Server 2010 non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="6bd61-247">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span><br/>

  * <span data-ttu-id="6bd61-248">**Coda di chiamata** È necessario avere già creato un'altra coda di chiamata, ma dopo aver eseguito, è possibile selezionare la coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="6bd61-248">**Call Queue** You must have already created another call queue, but after you do, you can select that call queue.</span></span>
  * <span data-ttu-id="6bd61-p126">**Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="6bd61-p126">**Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).</span></span>
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a><span data-ttu-id="6bd61-251">Modificare l'ID chiamante dell'utente per farlo diventare un numero di telefono della coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="6bd61-251">Changing the user's Caller ID to be a call queue's phone number</span></span>

<span data-ttu-id="6bd61-252">Puoi proteggere l'identità di un utente modificando l'ID chiamante per le chiamate in uscita a una coda di chiamata, mediante la creazione di un criterio utilizzando il cmdlet **New-CallingLineIdentity**.</span><span class="sxs-lookup"><span data-stu-id="6bd61-252">You can protect a user's identity by changing their caller ID for the outbound calls to a call queue instead by creating a policy using the **New-CallingLineIdentity** cmdlet.</span></span>
  
<span data-ttu-id="6bd61-253">Per farlo, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="6bd61-253">To do this, run:</span></span>
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="6bd61-p127">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet. To do this, run:</span><span class="sxs-lookup"><span data-stu-id="6bd61-p127">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet. To do this, run:</span></span>
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="6bd61-256">È possibile ottenere ulteriori informazioni su come apportare modifiche alle impostazioni di ID chiamante nell'organizzazione [qui](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="6bd61-256">You can get more information on how to make changes to caller ID settings in your organization [here](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="want-to-know-more"></a><span data-ttu-id="6bd61-257">Per saperne di più</span><span class="sxs-lookup"><span data-stu-id="6bd61-257">Want to know more?</span></span>

<span data-ttu-id="6bd61-258">Puoi anche utilizzare Windows PowerShell per creare e configurare code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="6bd61-258">You can also use Windows PowerShell to create and set up call queues.</span></span>
  
### <a name="call-queue-cmdlets"></a><span data-ttu-id="6bd61-259">Cmdlet della coda di chiamata</span><span class="sxs-lookup"><span data-stu-id="6bd61-259">Call queue cmdlets</span></span>

<span data-ttu-id="6bd61-260">Questi sono i cmdlet necessari per gestire una coda di chiamata.</span><span class="sxs-lookup"><span data-stu-id="6bd61-260">Here are the cmdlets that you need to manage a call queue.</span></span>
  
- [<span data-ttu-id="6bd61-261">New-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="6bd61-261">New-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
- [<span data-ttu-id="6bd61-262">Set-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="6bd61-262">Set-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
- [<span data-ttu-id="6bd61-263">Get-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="6bd61-263">Get-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
- [<span data-ttu-id="6bd61-264">Remove-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="6bd61-264">Remove-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
### <a name="more-about-windows-powershell"></a><span data-ttu-id="6bd61-265">Altre informazioni su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6bd61-265">More about Windows PowerShell</span></span>

- <span data-ttu-id="6bd61-p128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span><span class="sxs-lookup"><span data-stu-id="6bd61-p128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="6bd61-269">Introduzione a Windows Powershell e Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="6bd61-269">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="6bd61-270">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="6bd61-270">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="6bd61-p129">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="6bd61-p129">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="6bd61-273">Gestire Office 365 con Windows PowerShell nel modo migliore</span><span class="sxs-lookup"><span data-stu-id="6bd61-273">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="6bd61-274">Usare Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6bd61-274">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="6bd61-275">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6bd61-275">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="6bd61-276">See also</span><span class="sxs-lookup"><span data-stu-id="6bd61-276">Related topics</span></span>
[<span data-ttu-id="6bd61-277">Ecco cosa offre il Sistema telefonico in Office 365</span><span class="sxs-lookup"><span data-stu-id="6bd61-277">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="6bd61-278">Ottenere numeri di servizio per Skype for Business e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6bd61-278">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="6bd61-279">Disponibilità di Audioconferenza e Piani per chiamate per paese e area geografica</span><span class="sxs-lookup"><span data-stu-id="6bd61-279">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
