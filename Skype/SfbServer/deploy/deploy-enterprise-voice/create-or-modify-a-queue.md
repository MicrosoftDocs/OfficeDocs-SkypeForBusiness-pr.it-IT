---
title: Creare o modificare una coda in Skype for business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 9ab714b974601599f591880886a2cf64e35262ba
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808676"
---
# <a name="create-or-modify-a-queue-in-skype-for-business"></a><span data-ttu-id="cce26-103">Creare o modificare una coda in Skype for business</span><span class="sxs-lookup"><span data-stu-id="cce26-103">Create or modify a queue in Skype for Business</span></span>
 
<span data-ttu-id="cce26-104">Creare o modificare una coda di Response Group in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="cce26-104">Create or modify a Response Group queue, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="cce26-105">Le code contengono i chiamanti fino a quando un agente non risponde alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="cce26-105">Queues hold callers until an agent answers the call.</span></span> <span data-ttu-id="cce26-106">Quando l'applicazione Response Group cerca un agente disponibile, Cerca i gruppi di agenti nell'ordine in cui vengono elencati.</span><span class="sxs-lookup"><span data-stu-id="cce26-106">When the Response Group application searches for an available agent, it searches agent groups in the order that you list them.</span></span> <span data-ttu-id="cce26-107">È possibile selezionare i gruppi di agenti assegnati alla coda e specificare il comportamento di quest'ultima, ad esempio limitando il numero di chiamate che possono essere contenute nella coda e per quanto tempo una chiamata può restare in attesa che un agente risponda.</span><span class="sxs-lookup"><span data-stu-id="cce26-107">You can select the agent groups that are assigned to the queue and specify queue behavior, such as limiting the number of calls that the queue can hold and the period of time that a call waits until an agent answers the call.</span></span>
  
<span data-ttu-id="cce26-108">Per creare o modificare una coda, utilizzare una delle procedure illustrate di seguito.</span><span class="sxs-lookup"><span data-stu-id="cce26-108">Use one of the following procedures to create or modify a queue.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a><span data-ttu-id="cce26-109">Per utilizzare il pannello di controllo di Skype for Business Server per creare o modificare una coda</span><span class="sxs-lookup"><span data-stu-id="cce26-109">To use Skype for Business Server Control Panel to create or modify a queue</span></span>

1. <span data-ttu-id="cce26-110">Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.</span><span class="sxs-lookup"><span data-stu-id="cce26-110">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cce26-111">Se si è uno dei responsabili di Response Group delegati per un flusso di lavoro gestito, è possibile creare o modificare le code di Response Group e assegnarle ai flussi di lavoro gestiti personalmente.</span><span class="sxs-lookup"><span data-stu-id="cce26-111">If you are one of the delegated Response Group Managers for a managed workflow, you can create or modify response group queues and assign them to the workflows that you manage.</span></span> 
  
2. <span data-ttu-id="cce26-112">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cce26-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="cce26-113">Sulla barra di spostamento sinistra fare clic su **Response Group** e quindi su **Coda**.</span><span class="sxs-lookup"><span data-stu-id="cce26-113">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>
    
4. <span data-ttu-id="cce26-114">Nella pagina **Coda** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cce26-114">On the **Queue** page, do one of the following:</span></span>
    
   - <span data-ttu-id="cce26-115">Per creare una nuova coda, fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="cce26-115">To create a new queue, click **New**.</span></span> <span data-ttu-id="cce26-116">In **Seleziona un servizio** digitare nel campo di ricerca parte oppure tutto il nome del servizio **ApplicationServer** in cui si intende aggiungere la coda.</span><span class="sxs-lookup"><span data-stu-id="cce26-116">In **Select a Service**, type part or all of the name of the **ApplicationServer** service where you want to add the queue in the search field.</span></span> <span data-ttu-id="cce26-117">Nell'elenco di servizi risultante fare clic sul servizio desiderato e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cce26-117">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="cce26-p103">Per modificare una coda esistente, digitare tutto o una parte del nome della coda nel campo di ricerca. Nell'elenco di code risultante fare clic sulla coda desiderata, su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="cce26-p103">To modify an existing queue, type all or part of the queue name in the search field. In the resulting list of queues, click the queue that you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="cce26-120">In **Nome** digitare un nome identificativo della coda.</span><span class="sxs-lookup"><span data-stu-id="cce26-120">In **Name**, type an identifying name for the queue.</span></span>
    
6. <span data-ttu-id="cce26-121">In **Descrizione** digitare una descrizione per la coda.</span><span class="sxs-lookup"><span data-stu-id="cce26-121">In **Description**, type a description for the queue.</span></span>
    
7. <span data-ttu-id="cce26-p104">In **Gruppi** specificare i gruppo che si desidera assegnare alla coda. Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cce26-p104">In **Groups**, specify the groups you want to assign to the queue. Do one of the following:</span></span> 
    
   - <span data-ttu-id="cce26-p105">Per aggiungere un gruppo alla coda, fare clic su **Seleziona**. Nel campo di ricerca **Seleziona gruppi** digitare tutto o parte del nome del gruppo di agenti che si intende assegnare alla coda, fare clic sul gruppo desiderato e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cce26-p105">To add a group to the queue, click **Select**. In the **Select Groups** search field, type all or part of the name of the agent group that you want to assign to the queue, click the agent group that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="cce26-126">Per rimuovere un gruppo dalla coda, nell'elenco di gruppi di agenti fare clic sul gruppo che si desidera rimuovere e quindi fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="cce26-126">To remove a group from the queue, in the list of agent groups, click the group that you want to remove, and then click **Remove**.</span></span>
    
   - <span data-ttu-id="cce26-127">Per modificare l'ordine in cui gli agenti vengono ricercati, nell'elenco di gruppi di agenti fare clic su un gruppo e quindi sulla freccia rivolta verso l'alto o verso il basso.</span><span class="sxs-lookup"><span data-stu-id="cce26-127">To change the order in which agents are searched, in the list of agent groups, click a group, and then click the up arrow or down arrow.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="cce26-p106">Per la ricerca di un agente disponibile per la coda, il server utilizza l'ordine dei gruppi. La ricerca pertanto viene eseguita prima nel primo gruppo, quindi nel secondo gruppo dell'elenco e così via.</span><span class="sxs-lookup"><span data-stu-id="cce26-p106">When the server searches for an available agent for the queue, it uses group order. That is, the first group in the list is searched first, followed by the second group in the list, and so on.</span></span> 
  
8. <span data-ttu-id="cce26-130">Per specificare un periodo di tempo massimo in cui un chiamante resta in attesa prima che un agente risponda alla chiamata, selezionare la casella di controllo **Abilita timeout coda** e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cce26-130">To specify a maximum period of time for a caller to wait on hold before an agent answers the call, select the **Enable queue time-out** check box, and then do the following:</span></span>
    
    <span data-ttu-id="cce26-131">a.</span><span class="sxs-lookup"><span data-stu-id="cce26-131">a.</span></span> <span data-ttu-id="cce26-132">In **Periodo di timeout (secondi)** specificare il numero massimo di secondi che un chiamante può attendere prima che un agente risponda alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="cce26-132">In **Time-out period (seconds)**, specify the maximum number of seconds a caller waits for an agent to answer the call.</span></span>
    
    <span data-ttu-id="cce26-133">b.</span><span class="sxs-lookup"><span data-stu-id="cce26-133">b.</span></span> <span data-ttu-id="cce26-134">In **Azione chiamata** selezionare l'azione che deve essere eseguita quando si verifica il timeout di una chiamata, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="cce26-134">In **Call Action**, select the action that occurs when a call times out as follows:</span></span>
    
   - <span data-ttu-id="cce26-135">Per disconnettere la chiamata dopo il timeout, fare clic su **Disconnetti**.</span><span class="sxs-lookup"><span data-stu-id="cce26-135">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
   - <span data-ttu-id="cce26-136">Per inoltrare la chiamata alla segreteria telefonica, fare clic su **Inoltra a** segreteria telefonica e quindi nel campo **indirizzo SIP** digitare un indirizzo di segreteria telefonica nel formato SIP: *\<username\>* @  *\<domainname\>* (ad esempio, SIP:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="cce26-136">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip: *\<username\>*@ *\<domainname\>* (for example, sip:bob@contoso.com).</span></span>
    
   - <span data-ttu-id="cce26-137">Per inoltrare la chiamata a un altro numero di telefono, fare clic su **Inoltra a numero di telefono** e quindi nel campo **indirizzo SIP** digitare il numero di telefono nel formato SIP: *\<number\>* @  *\<domainname\>* (ad esempio, SIP:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="cce26-137">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip: *\<number\>*@ *\<domainname\>* (for example, sip:+14255550121@contoso.com).</span></span>
    
   - <span data-ttu-id="cce26-138">Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra a indirizzo SIP** e quindi nel campo **indirizzo SIP** digitare l'URI dell'utente nel formato SIP: _\<username\>_ @  _\<domainname\>_ .</span><span class="sxs-lookup"><span data-stu-id="cce26-138">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip: _\<username\>_@ _\<domainname\>_.</span></span>
    
   - <span data-ttu-id="cce26-139">Per inoltrare la chiamata a un'altra coda, fare clic su **Inoltra a un'altra coda** e quindi selezionare la coda che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="cce26-139">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>
    
9. <span data-ttu-id="cce26-140">Per specificare il numero massimo di chiamate che possono essere contenute nella coda, selezionare la casella di controllo **Abilita overflow coda** e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cce26-140">To specify a maximum number of calls that the queue can hold, select the **Enable queue overflow** check box, and then do the following:</span></span>
    
    <span data-ttu-id="cce26-141">a.</span><span class="sxs-lookup"><span data-stu-id="cce26-141">a.</span></span> <span data-ttu-id="cce26-142">In **Numero massimo di chiamate** selezionare il numero massimo di chiamate che possono essere contenute nella coda.</span><span class="sxs-lookup"><span data-stu-id="cce26-142">In **Maximum number of calls**, select the maximum number of calls that you want the queue to hold.</span></span> 
    
    <span data-ttu-id="cce26-143">b.</span><span class="sxs-lookup"><span data-stu-id="cce26-143">b.</span></span> <span data-ttu-id="cce26-144">In **Inoltra la chiamata** selezionare quale chiamata dovrà essere inoltrata quando la coda è piena, ovvero **Chiamata più recente** o **Chiamata meno recente**.</span><span class="sxs-lookup"><span data-stu-id="cce26-144">In **Forward the call**, select which call is to be forwarded when the queue is full: **Newest Call** or **Oldest Call**.</span></span>
    
    <span data-ttu-id="cce26-145">c.</span><span class="sxs-lookup"><span data-stu-id="cce26-145">c.</span></span> <span data-ttu-id="cce26-146">In **Azione chiamata** selezionare l'azione che deve essere eseguita quando viene raggiunta la soglia di overflow, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="cce26-146">In **Call action**, select the action that occurs when the overflow threshold is met as follows:</span></span>
    
   - <span data-ttu-id="cce26-147">Per disconnettere la chiamata dopo il timeout, fare clic su **Disconnetti**.</span><span class="sxs-lookup"><span data-stu-id="cce26-147">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
   - <span data-ttu-id="cce26-148">Per inoltrare la chiamata alla segreteria telefonica, fare clic su **Inoltra a** segreteria telefonica e quindi nel campo **indirizzo SIP** digitare un indirizzo di segreteria telefonica nel formato SIP: *\<username\>* @  *\<domainname\>* (ad esempio, SIP:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="cce26-148">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip: *\<username\>*@ *\<domainname\>* (for example, sip:bob@contoso.com).</span></span>
    
   - <span data-ttu-id="cce26-149">Per inoltrare la chiamata a un altro numero di telefono, fare clic su **Inoltra a numero di telefono** e quindi nel campo **indirizzo SIP** digitare il numero di telefono nel formato SIP: *\<number\>* @  *\<domainname\>* (ad esempio, SIP:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="cce26-149">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip: *\<number\>*@ *\<domainname\>* (for example, sip:+14255550121@contoso.com).</span></span>
    
   - <span data-ttu-id="cce26-150">Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra a indirizzo SIP** e quindi nel campo **indirizzo SIP** digitare l'URI dell'utente nel formato SIP: _\<username\>_ @  _\<domainname\>_ .</span><span class="sxs-lookup"><span data-stu-id="cce26-150">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip: _\<username\>_@ _\<domainname\>_.</span></span>
    
   - <span data-ttu-id="cce26-151">Per inoltrare la chiamata a un'altra coda, fare clic su **Inoltra a un'altra coda** e quindi selezionare la coda che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="cce26-151">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>
    
10. <span data-ttu-id="cce26-152">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="cce26-152">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a><span data-ttu-id="cce26-153">Per utilizzare Skype for Business Server Management Shell per creare o modificare una coda</span><span class="sxs-lookup"><span data-stu-id="cce26-153">To use Skype for Business Server Management Shell to create or modify a queue</span></span>

1. <span data-ttu-id="cce26-154">Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.</span><span class="sxs-lookup"><span data-stu-id="cce26-154">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cce26-155">Se si è uno dei responsabili di Response Group delegati per un flusso di lavoro gestito, è possibile creare gruppi di agenti e code, nonché assegnare i gruppi di agenti alle code.</span><span class="sxs-lookup"><span data-stu-id="cce26-155">If you are one of the delegated Response Group Managers for a managed workflow, you will be able to create agent groups and queues, and assign agent groups to queues.</span></span> 
  
2. <span data-ttu-id="cce26-156">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="cce26-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="cce26-p112">Creare la richiesta da riprodurre quando viene raggiunta la soglia di timeout della coda e salvarla in una variabile. Nella riga di comando eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="cce26-p112">Create the prompt to be played when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```powershell
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   <span data-ttu-id="cce26-159">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cce26-159">For example:</span></span>
    
   ```console
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > <span data-ttu-id="cce26-160">Per utilizzare un file audio per il messaggio, eseguire il cmdlet **Import-CsRgsAudioFile**.</span><span class="sxs-lookup"><span data-stu-id="cce26-160">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="cce26-161">Per informazioni dettagliate, vedere [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="cce26-161">For details, see [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
4. <span data-ttu-id="cce26-p114">Definire l'azione da eseguire quando viene raggiunta la soglia di timeout della coda e salvarla in una variabile. Nella riga di comando eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="cce26-p114">Define the action to be taken when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```powershell
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > <span data-ttu-id="cce26-164">Per informazioni dettagliate sulle possibili azioni e sulla relativa sintassi, vedere [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="cce26-164">For details about possible actions and their syntax, see [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span> 
  
    <span data-ttu-id="cce26-165">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cce26-165">For example:</span></span>
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. <span data-ttu-id="cce26-p115">Creare la richiesta da riprodurre quando viene raggiunta la soglia di overflow della coda e salvarla in una variabile. Nella riga di comando eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="cce26-p115">Create the prompt to be played when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   <span data-ttu-id="cce26-168">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cce26-168">For example:</span></span>
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
   ```

      > [!NOTE]
      > <span data-ttu-id="cce26-169">Per utilizzare un file audio per il messaggio, eseguire il cmdlet **Import-CsRgsAudioFile**.</span><span class="sxs-lookup"><span data-stu-id="cce26-169">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="cce26-170">Per informazioni dettagliate, vedere [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="cce26-170">For details, see [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
6. <span data-ttu-id="cce26-p117">Definire l'azione da eseguire quando viene raggiunta la soglia di overflow della coda e salvarla in una variabile. Nella riga di comando eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="cce26-p117">Define the action to be taken when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```powershell
   $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

    > [!NOTE]
    > <span data-ttu-id="cce26-173">Per informazioni dettagliate sulle possibili azioni e sulla relativa sintassi, vedere [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="cce26-173">For details about possible actions and their syntax, see [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span> 
  
    <span data-ttu-id="cce26-174">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cce26-174">For example:</span></span>
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. <span data-ttu-id="cce26-175">Recuperare il nome del servizio Response Group e assegnarlo a una variabile.</span><span class="sxs-lookup"><span data-stu-id="cce26-175">Retrieve the service name for the Response Group service and assign it to a variable.</span></span> <span data-ttu-id="cce26-176">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="cce26-176">At the command line, run:</span></span>
    
   ```powershell
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. <span data-ttu-id="cce26-177">Ottenere l'identità del gruppo di agenti da assegnare alla coda.</span><span class="sxs-lookup"><span data-stu-id="cce26-177">Get the identity of the agent group to be assigned to the queue.</span></span> <span data-ttu-id="cce26-178">Nella riga di comando eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="cce26-178">At the command line, run:</span></span>
    
   ```powershell
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > <span data-ttu-id="cce26-179">Per informazioni dettagliate sulla creazione del gruppo di agenti, vedere [New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="cce26-179">For details about creating the agent group, see [New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)</span></span>
  
9. <span data-ttu-id="cce26-p120">Creare la coda. Nella riga di comando eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="cce26-p120">Create the queue. At the command line, run:</span></span>
    
   ```powershell
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   <span data-ttu-id="cce26-182">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cce26-182">For example:</span></span>
    
   ```powershell
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. <span data-ttu-id="cce26-p121">Verificare che la coda sia stata creata. Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="cce26-p121">Confirm that the queue is created. Run:</span></span>
    
    ```powershell
    Get-CsRgsQueue -Name "Help Desk"
    ```

## <a name="see-also"></a><span data-ttu-id="cce26-185">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cce26-185">See also</span></span>

[<span data-ttu-id="cce26-186">New-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="cce26-186">New-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="cce26-187">Set-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="cce26-187">Set-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="cce26-188">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="cce26-188">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[<span data-ttu-id="cce26-189">New-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="cce26-189">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[<span data-ttu-id="cce26-190">Get-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="cce26-190">Get-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="cce26-191">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="cce26-191">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[<span data-ttu-id="cce26-192">Remove-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="cce26-192">Remove-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csrgsqueue?view=skype-ps)
