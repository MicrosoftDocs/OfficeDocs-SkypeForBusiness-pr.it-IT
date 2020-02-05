---
title: Creare o modificare una coda in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b9d6366a-839f-4651-a01d-9254546cadeb
description: Creare o modificare una coda di Response Group in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 8cd306e849eeddd8a11b76604826084c0eb9b41d
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767869"
---
# <a name="create-or-modify-a-queue-in-skype-for-business"></a><span data-ttu-id="00d10-103">Creare o modificare una coda in Skype for business</span><span class="sxs-lookup"><span data-stu-id="00d10-103">Create or modify a queue in Skype for Business</span></span>
 
<span data-ttu-id="00d10-104">Creare o modificare una coda di Response Group in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="00d10-104">Create or modify a Response Group queue, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="00d10-105">Le code contengono i chiamanti finché un agente non risponde alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="00d10-105">Queues hold callers until an agent answers the call.</span></span> <span data-ttu-id="00d10-106">Quando l'applicazione Response Group cerca un agente disponibile, esegue la ricerca in gruppi di agenti nell'ordine in cui vengono elencati.</span><span class="sxs-lookup"><span data-stu-id="00d10-106">When the Response Group application searches for an available agent, it searches agent groups in the order that you list them.</span></span> <span data-ttu-id="00d10-107">È possibile selezionare i gruppi di agenti assegnati alla coda e specificare il comportamento della coda, ad esempio limitando il numero di chiamate che la coda può contenere e il periodo di tempo in cui una chiamata attende finché un agente non risponde alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="00d10-107">You can select the agent groups that are assigned to the queue and specify queue behavior, such as limiting the number of calls that the queue can hold and the period of time that a call waits until an agent answers the call.</span></span>
  
<span data-ttu-id="00d10-108">Usare una delle procedure seguenti per creare o modificare una coda.</span><span class="sxs-lookup"><span data-stu-id="00d10-108">Use one of the following procedures to create or modify a queue.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a><span data-ttu-id="00d10-109">Per usare il pannello di controllo di Skype for Business Server per creare o modificare una coda</span><span class="sxs-lookup"><span data-stu-id="00d10-109">To use Skype for Business Server Control Panel to create or modify a queue</span></span>

1. <span data-ttu-id="00d10-110">Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="00d10-110">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="00d10-111">Se si è uno dei responsabili del gruppo di risposte delegati per un flusso di lavoro gestito, è possibile creare o modificare code di Response Group e assegnarle ai flussi di lavoro gestiti.</span><span class="sxs-lookup"><span data-stu-id="00d10-111">If you are one of the delegated Response Group Managers for a managed workflow, you can create or modify response group queues and assign them to the workflows that you manage.</span></span> 
  
2. <span data-ttu-id="00d10-112">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="00d10-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="00d10-113">Nella barra di spostamento sinistra fare clic su **Response Groups**, quindi fare clic su **Accoda**.</span><span class="sxs-lookup"><span data-stu-id="00d10-113">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>
    
4. <span data-ttu-id="00d10-114">Nella pagina **coda** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="00d10-114">On the **Queue** page, do one of the following:</span></span>
    
   - <span data-ttu-id="00d10-115">Per creare una nuova coda, fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="00d10-115">To create a new queue, click **New**.</span></span> <span data-ttu-id="00d10-116">In **Seleziona un servizio**Digitare parte o tutto il nome del servizio **ApplicationServer** in cui si vuole aggiungere la coda nel campo di ricerca.</span><span class="sxs-lookup"><span data-stu-id="00d10-116">In **Select a Service**, type part or all of the name of the **ApplicationServer** service where you want to add the queue in the search field.</span></span> <span data-ttu-id="00d10-117">Nell'elenco dei servizi risultante fare clic sul servizio desiderato e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="00d10-117">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="00d10-118">Per modificare una coda esistente, digitare tutto o parte del nome della coda nel campo di ricerca.</span><span class="sxs-lookup"><span data-stu-id="00d10-118">To modify an existing queue, type all or part of the queue name in the search field.</span></span> <span data-ttu-id="00d10-119">Nell'elenco di code risultante fare clic sulla coda desiderata, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="00d10-119">In the resulting list of queues, click the queue that you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="00d10-120">In **nome**Digitare un nome identificativo per la coda.</span><span class="sxs-lookup"><span data-stu-id="00d10-120">In **Name**, type an identifying name for the queue.</span></span>
    
6. <span data-ttu-id="00d10-121">In **Descrizione**Digitare una descrizione per la coda.</span><span class="sxs-lookup"><span data-stu-id="00d10-121">In **Description**, type a description for the queue.</span></span>
    
7. <span data-ttu-id="00d10-122">In **gruppi**specificare i gruppi che si desidera assegnare alla coda.</span><span class="sxs-lookup"><span data-stu-id="00d10-122">In **Groups**, specify the groups you want to assign to the queue.</span></span> <span data-ttu-id="00d10-123">Esegui una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="00d10-123">Do one of the following:</span></span> 
    
   - <span data-ttu-id="00d10-124">Per aggiungere un gruppo alla coda, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="00d10-124">To add a group to the queue, click **Select**.</span></span> <span data-ttu-id="00d10-125">Nel campo **Seleziona gruppi** digitare tutto o parte del nome del gruppo di agenti che si vuole assegnare alla coda, fare clic sul gruppo di agenti desiderato e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="00d10-125">In the **Select Groups** search field, type all or part of the name of the agent group that you want to assign to the queue, click the agent group that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="00d10-126">Per rimuovere un gruppo dalla coda, nell'elenco dei gruppi di agenti fare clic sul gruppo che si desidera rimuovere e quindi fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="00d10-126">To remove a group from the queue, in the list of agent groups, click the group that you want to remove, and then click **Remove**.</span></span>
    
   - <span data-ttu-id="00d10-127">Per modificare l'ordine in cui vengono cercati gli agenti, nell'elenco dei gruppi di agenti fare clic su un gruppo e quindi fare clic sulla freccia su o freccia giù.</span><span class="sxs-lookup"><span data-stu-id="00d10-127">To change the order in which agents are searched, in the list of agent groups, click a group, and then click the up arrow or down arrow.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="00d10-128">Quando il server Cerca un agente disponibile per la coda, usa l'ordine dei gruppi.</span><span class="sxs-lookup"><span data-stu-id="00d10-128">When the server searches for an available agent for the queue, it uses group order.</span></span> <span data-ttu-id="00d10-129">Il primo gruppo dell'elenco viene quindi cercato per primo, seguito dal secondo gruppo nell'elenco e così via.</span><span class="sxs-lookup"><span data-stu-id="00d10-129">That is, the first group in the list is searched first, followed by the second group in the list, and so on.</span></span> 
  
8. <span data-ttu-id="00d10-130">Per specificare un periodo di tempo massimo per il chiamante in attesa in attesa prima che un agente risponda alla chiamata, selezionare la casella di controllo **Abilita timeout coda** e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="00d10-130">To specify a maximum period of time for a caller to wait on hold before an agent answers the call, select the **Enable queue time-out** check box, and then do the following:</span></span>
    
    <span data-ttu-id="00d10-131">un.</span><span class="sxs-lookup"><span data-stu-id="00d10-131">a.</span></span> <span data-ttu-id="00d10-132">Nel **periodo di timeout (secondi)** specificare il numero massimo di secondi in cui il chiamante attende che un agente risponda alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="00d10-132">In **Time-out period (seconds)**, specify the maximum number of seconds a caller waits for an agent to answer the call.</span></span>
    
    <span data-ttu-id="00d10-133">b.</span><span class="sxs-lookup"><span data-stu-id="00d10-133">b.</span></span> <span data-ttu-id="00d10-134">In **azione chiamata**selezionare l'azione che si verifica quando una chiamata ha un timeout come segue:</span><span class="sxs-lookup"><span data-stu-id="00d10-134">In **Call Action**, select the action that occurs when a call times out as follows:</span></span>
    
   - <span data-ttu-id="00d10-135">Per disconnettere la chiamata dopo il timeout, fare clic su **Disconnetti**.</span><span class="sxs-lookup"><span data-stu-id="00d10-135">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
   - <span data-ttu-id="00d10-136">Per inoltrare la chiamata alla segreteria telefonica, fare clic su **inoltra alla**segreteria telefonica e quindi, nel campo **indirizzo SIP** , digitare un indirizzo di segreteria telefonica nel formato SIP: \* \<\>nomeutente\*@ \*\<NomeDominio\> \* (ad esempio, SIP:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="00d10-136">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip: *\<username\>*@ *\<domainname\>* (for example, sip:bob@contoso.com).</span></span>
    
   - <span data-ttu-id="00d10-137">Per inoltrare la chiamata a un altro numero di telefono, fare clic su **inoltra al numero**di telefono e quindi, nel campo **indirizzo SIP** , digitare il numero di telefono nel formato SIP: \* \<\>Number\*@ *\<\> NomeDominio* (ad esempio, SIP:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="00d10-137">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip: *\<number\>*@ *\<domainname\>* (for example, sip:+14255550121@contoso.com).</span></span>
    
   - <span data-ttu-id="00d10-138">Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra all'indirizzo SIP**e quindi, nel campo **indirizzo SIP** , digitare l'URI per l'utente nel formato SIP: _ \<\>nomeutente_@ _\<NomeDominio\>_.</span><span class="sxs-lookup"><span data-stu-id="00d10-138">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip: _\<username\>_@ _\<domainname\>_.</span></span>
    
   - <span data-ttu-id="00d10-139">Per inoltrare la chiamata a un'altra coda, fare clic su **Inoltra a un'altra coda**e quindi passare alla coda che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="00d10-139">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>
    
9. <span data-ttu-id="00d10-140">Per specificare un numero massimo di chiamate che la coda può contenere, selezionare la casella di controllo **attiva l'overflow delle code** e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="00d10-140">To specify a maximum number of calls that the queue can hold, select the **Enable queue overflow** check box, and then do the following:</span></span>
    
    <span data-ttu-id="00d10-141">un.</span><span class="sxs-lookup"><span data-stu-id="00d10-141">a.</span></span> <span data-ttu-id="00d10-142">In **numero massimo di chiamate**selezionare il numero massimo di chiamate che la coda deve contenere.</span><span class="sxs-lookup"><span data-stu-id="00d10-142">In **Maximum number of calls**, select the maximum number of calls that you want the queue to hold.</span></span> 
    
    <span data-ttu-id="00d10-143">b.</span><span class="sxs-lookup"><span data-stu-id="00d10-143">b.</span></span> <span data-ttu-id="00d10-144">In **inoltra la chiamata**selezionare la chiamata da inoltrare quando la coda è piena: chiamata più **recente** o **chiamata più vecchia**.</span><span class="sxs-lookup"><span data-stu-id="00d10-144">In **Forward the call**, select which call is to be forwarded when the queue is full: **Newest Call** or **Oldest Call**.</span></span>
    
    <span data-ttu-id="00d10-145">c.</span><span class="sxs-lookup"><span data-stu-id="00d10-145">c.</span></span> <span data-ttu-id="00d10-146">In **azione chiamata**selezionare l'azione che si verifica quando la soglia di overflow viene soddisfatta come segue:</span><span class="sxs-lookup"><span data-stu-id="00d10-146">In **Call action**, select the action that occurs when the overflow threshold is met as follows:</span></span>
    
   - <span data-ttu-id="00d10-147">Per disconnettere la chiamata dopo il timeout, fare clic su **Disconnetti**.</span><span class="sxs-lookup"><span data-stu-id="00d10-147">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
   - <span data-ttu-id="00d10-148">Per inoltrare la chiamata alla segreteria telefonica, fare clic su **inoltra alla**segreteria telefonica e quindi, nel campo **indirizzo SIP** , digitare un indirizzo di segreteria telefonica nel formato SIP: \* \<\>nomeutente\*@ \*\<NomeDominio\> \* (ad esempio, SIP:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="00d10-148">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip: *\<username\>*@ *\<domainname\>* (for example, sip:bob@contoso.com).</span></span>
    
   - <span data-ttu-id="00d10-149">Per inoltrare la chiamata a un altro numero di telefono, fare clic su **inoltra al numero**di telefono e quindi, nel campo **indirizzo SIP** , digitare il numero di telefono nel formato SIP: \* \<\>Number\*@ *\<\> NomeDominio* (ad esempio, SIP:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="00d10-149">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip: *\<number\>*@ *\<domainname\>* (for example, sip:+14255550121@contoso.com).</span></span>
    
   - <span data-ttu-id="00d10-150">Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra all'indirizzo SIP**e quindi, nel campo **indirizzo SIP** , digitare l'URI per l'utente nel formato SIP: _ \<\>nomeutente_@ _\<NomeDominio\>_.</span><span class="sxs-lookup"><span data-stu-id="00d10-150">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip: _\<username\>_@ _\<domainname\>_.</span></span>
    
   - <span data-ttu-id="00d10-151">Per inoltrare la chiamata a un'altra coda, fare clic su **Inoltra a un'altra coda**e quindi passare alla coda che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="00d10-151">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>
    
10. <span data-ttu-id="00d10-152">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="00d10-152">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a><span data-ttu-id="00d10-153">Per usare Skype for Business Server Management Shell per creare o modificare una coda</span><span class="sxs-lookup"><span data-stu-id="00d10-153">To use Skype for Business Server Management Shell to create or modify a queue</span></span>

1. <span data-ttu-id="00d10-154">Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="00d10-154">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="00d10-155">Se si è uno dei responsabili del gruppo di risposte delegati per un flusso di lavoro gestito, sarà possibile creare gruppi di agenti e code e assegnare gruppi di agenti alle code.</span><span class="sxs-lookup"><span data-stu-id="00d10-155">If you are one of the delegated Response Group Managers for a managed workflow, you will be able to create agent groups and queues, and assign agent groups to queues.</span></span> 
  
2. <span data-ttu-id="00d10-156">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="00d10-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="00d10-157">Creare il prompt da riprodurre quando viene soddisfatta la soglia di timeout della coda e salvarla in una variabile.</span><span class="sxs-lookup"><span data-stu-id="00d10-157">Create the prompt to be played when the queue timeout threshold is met, and save it in a variable.</span></span> <span data-ttu-id="00d10-158">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="00d10-158">At the command line, run:</span></span>
    
   ```powershell
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   <span data-ttu-id="00d10-159">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="00d10-159">For example:</span></span>
    
   ```console
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > <span data-ttu-id="00d10-160">Per usare un file audio per la richiesta, usare il cmdlet **Import-CsRgsAudioFile** .</span><span class="sxs-lookup"><span data-stu-id="00d10-160">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="00d10-161">Per informazioni dettagliate, vedere [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="00d10-161">For details, see [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
4. <span data-ttu-id="00d10-162">Definire l'azione da intraprendere quando viene soddisfatta la soglia di timeout della coda e salvarla in una variabile.</span><span class="sxs-lookup"><span data-stu-id="00d10-162">Define the action to be taken when the queue timeout threshold is met, and save it in a variable.</span></span> <span data-ttu-id="00d10-163">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="00d10-163">At the command line, run:</span></span>
    
   ```powershell
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > <span data-ttu-id="00d10-164">Per informazioni dettagliate sulle possibili azioni e sulla relativa sintassi, vedere [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="00d10-164">For details about possible actions and their syntax, see [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span> 
  
    <span data-ttu-id="00d10-165">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="00d10-165">For example:</span></span>
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. <span data-ttu-id="00d10-166">Creare il prompt da riprodurre quando viene soddisfatta la soglia di overflow della coda e salvarla in una variabile.</span><span class="sxs-lookup"><span data-stu-id="00d10-166">Create the prompt to be played when the queue overflow threshold is met, and save it in a variable.</span></span> <span data-ttu-id="00d10-167">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="00d10-167">At the command line, run:</span></span>
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   <span data-ttu-id="00d10-168">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="00d10-168">For example:</span></span>
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
   ```

      > [!NOTE]
      > <span data-ttu-id="00d10-169">Per usare un file audio per la richiesta, usare il cmdlet **Import-CsRgsAudioFile** .</span><span class="sxs-lookup"><span data-stu-id="00d10-169">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="00d10-170">Per informazioni dettagliate, vedere [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="00d10-170">For details, see [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
6. <span data-ttu-id="00d10-171">Definire l'azione da intraprendere quando viene soddisfatta la soglia di overflow della coda e salvarla in una variabile.</span><span class="sxs-lookup"><span data-stu-id="00d10-171">Define the action to be taken when the queue overflow threshold is met, and save it in a variable.</span></span> <span data-ttu-id="00d10-172">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="00d10-172">At the command line, run:</span></span>
    
   ```powershell
   $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

    > [!NOTE]
    > <span data-ttu-id="00d10-173">Per informazioni dettagliate sulle possibili azioni e sulla relativa sintassi, vedere [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="00d10-173">For details about possible actions and their syntax, see [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span> 
  
    <span data-ttu-id="00d10-174">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="00d10-174">For example:</span></span>
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. <span data-ttu-id="00d10-175">Recuperare il nome del servizio per il servizio Response Group e assegnarlo a una variabile.</span><span class="sxs-lookup"><span data-stu-id="00d10-175">Retrieve the service name for the Response Group service and assign it to a variable.</span></span> <span data-ttu-id="00d10-176">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="00d10-176">At the command line, run:</span></span>
    
   ```powershell
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. <span data-ttu-id="00d10-177">Ottenere l'identità del gruppo di agenti da assegnare alla coda.</span><span class="sxs-lookup"><span data-stu-id="00d10-177">Get the identity of the agent group to be assigned to the queue.</span></span> <span data-ttu-id="00d10-178">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="00d10-178">At the command line, run:</span></span>
    
   ```powershell
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > <span data-ttu-id="00d10-179">Per informazioni dettagliate sulla creazione del gruppo di agenti, vedere [New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="00d10-179">For details about creating the agent group, see [New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)</span></span>
  
9. <span data-ttu-id="00d10-180">Creare la coda.</span><span class="sxs-lookup"><span data-stu-id="00d10-180">Create the queue.</span></span> <span data-ttu-id="00d10-181">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="00d10-181">At the command line, run:</span></span>
    
   ```powershell
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   <span data-ttu-id="00d10-182">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="00d10-182">For example:</span></span>
    
   ```powershell
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. <span data-ttu-id="00d10-183">Verificare che la coda sia stata creata.</span><span class="sxs-lookup"><span data-stu-id="00d10-183">Confirm that the queue is created.</span></span> <span data-ttu-id="00d10-184">Eseguire</span><span class="sxs-lookup"><span data-stu-id="00d10-184">Run:</span></span>
    
    ```powershell
    Get-CsRgsQueue -Name "Help Desk"
    ```

## <a name="see-also"></a><span data-ttu-id="00d10-185">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00d10-185">See also</span></span>

[<span data-ttu-id="00d10-186">New-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="00d10-186">New-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="00d10-187">Set-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="00d10-187">Set-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="00d10-188">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="00d10-188">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[<span data-ttu-id="00d10-189">New-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="00d10-189">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[<span data-ttu-id="00d10-190">Get-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="00d10-190">Get-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="00d10-191">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="00d10-191">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[<span data-ttu-id="00d10-192">Remove-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="00d10-192">Remove-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csrgsqueue?view=skype-ps)
