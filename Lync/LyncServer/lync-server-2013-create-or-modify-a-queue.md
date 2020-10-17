---
title: 'Lync Server 2013: creare o modificare una coda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a queue
ms:assetid: b9d6366a-839f-4651-a01d-9254546cadeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205207(v=OCS.15)
ms:contentKeyID: 48185247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a4c85dd6da5ba15a6ce946c4e331e09c8617974
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525823"
---
# <a name="create-or-modify-a-queue-in-lync-server-2013"></a><span data-ttu-id="2316a-102">Creare o modificare una coda in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2316a-102">Create or modify a queue in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2316a-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="2316a-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="2316a-104">Per creare o modificare una coda, utilizzare una delle procedure illustrate di seguito.</span><span class="sxs-lookup"><span data-stu-id="2316a-104">Use one of the following procedures to create or modify a queue.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-queue"></a><span data-ttu-id="2316a-105">Per utilizzare il pannello di controllo di Lync Server per creare o modificare una coda</span><span class="sxs-lookup"><span data-stu-id="2316a-105">To use Lync Server Control Panel to create or modify a queue</span></span>

1.  <span data-ttu-id="2316a-106">Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.</span><span class="sxs-lookup"><span data-stu-id="2316a-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2316a-107">Se si è uno dei responsabili di Response Group delegati per un flusso di lavoro gestito, è possibile creare o modificare le code di Response Group e assegnarle ai flussi di lavoro gestiti personalmente.</span><span class="sxs-lookup"><span data-stu-id="2316a-107">If you are one of the delegated Response Group Managers for a managed workflow, you can create or modify response group queues and assign them to the workflows that you manage.</span></span>

    
    </div>

2.  <span data-ttu-id="2316a-108">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2316a-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2316a-109">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2316a-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2316a-110">Sulla barra di spostamento sinistra fare clic su **Response Group** e quindi su **Coda**.</span><span class="sxs-lookup"><span data-stu-id="2316a-110">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>

4.  <span data-ttu-id="2316a-111">Nella pagina **Coda** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2316a-111">On the **Queue** page, do one of the following:</span></span>
    
      - <span data-ttu-id="2316a-112">Per creare una nuova coda, fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="2316a-112">To create a new queue, click **New**.</span></span> <span data-ttu-id="2316a-113">In **Seleziona un servizio** digitare nel campo di ricerca parte oppure tutto il nome del servizio **ApplicationServer** in cui si intende aggiungere la coda.</span><span class="sxs-lookup"><span data-stu-id="2316a-113">In **Select a Service**, type part or all of the name of the **ApplicationServer** service where you want to add the queue in the search field.</span></span> <span data-ttu-id="2316a-114">Nell'elenco di servizi risultante fare clic sul servizio desiderato e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2316a-114">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="2316a-p103">Per modificare una coda esistente, digitare tutto o una parte del nome della coda nel campo di ricerca. Nell'elenco di code risultante fare clic sulla coda desiderata, su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="2316a-p103">To modify an existing queue, type all or part of the queue name in the search field. In the resulting list of queues, click the queue that you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="2316a-117">In **Nome** digitare un nome identificativo della coda.</span><span class="sxs-lookup"><span data-stu-id="2316a-117">In **Name**, type an identifying name for the queue.</span></span>

6.  <span data-ttu-id="2316a-118">In **Descrizione** digitare una descrizione per la coda.</span><span class="sxs-lookup"><span data-stu-id="2316a-118">In **Description**, type a description for the queue.</span></span>

7.  <span data-ttu-id="2316a-p104">In **Gruppi** specificare i gruppo che si desidera assegnare alla coda. Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2316a-p104">In **Groups**, specify the groups you want to assign to the queue. Do one of the following:</span></span>
    
      - <span data-ttu-id="2316a-p105">Per aggiungere un gruppo alla coda, fare clic su **Seleziona**. Nel campo di ricerca **Seleziona gruppi** digitare tutto o parte del nome del gruppo di agenti che si intende assegnare alla coda, fare clic sul gruppo desiderato e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2316a-p105">To add a group to the queue, click **Select**. In the **Select Groups** search field, type all or part of the name of the agent group that you want to assign to the queue, click the agent group that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="2316a-123">Per rimuovere un gruppo dalla coda, nell'elenco di gruppi di agenti fare clic sul gruppo che si desidera rimuovere e quindi fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="2316a-123">To remove a group from the queue, in the list of agent groups, click the group that you want to remove, and then click **Remove**.</span></span>
    
      - <span data-ttu-id="2316a-124">Per modificare l'ordine in cui gli agenti vengono ricercati, nell'elenco di gruppi di agenti fare clic su un gruppo e quindi sulla freccia rivolta verso l'alto o verso il basso.</span><span class="sxs-lookup"><span data-stu-id="2316a-124">To change the order in which agents are searched, in the list of agent groups, click a group, and then click the up arrow or down arrow.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="2316a-p106">Per la ricerca di un agente disponibile per la coda, il server utilizza l'ordine dei gruppi. La ricerca pertanto viene eseguita prima nel primo gruppo, quindi nel secondo gruppo dell'elenco e così via.</span><span class="sxs-lookup"><span data-stu-id="2316a-p106">When the server searches for an available agent for the queue, it uses group order. That is, the first group in the list is searched first, followed by the second group in the list, and so on.</span></span>

        
        </div>

8.  <span data-ttu-id="2316a-127">Per specificare un periodo di tempo massimo in cui un chiamante resta in attesa prima che un agente risponda alla chiamata, selezionare la casella di controllo **Abilita timeout coda** e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2316a-127">To specify a maximum period of time for a caller to wait on hold before an agent answers the call, select the **Enable queue time-out** check box, and then do the following:</span></span>
    
    1.  <span data-ttu-id="2316a-128">In **Periodo di timeout (secondi)** specificare il numero massimo di secondi che un chiamante può attendere prima che un agente risponda alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="2316a-128">In **Time-out period (seconds)**, specify the maximum number of seconds a caller waits for an agent to answer the call.</span></span>
    
    2.  <span data-ttu-id="2316a-129">In **Azione chiamata** selezionare l'azione che deve essere eseguita quando si verifica il timeout di una chiamata, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="2316a-129">In **Call Action**, select the action that occurs when a call times out as follows:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="2316a-130">Per disconnettere la chiamata dopo il timeout, fare clic su **Disconnetti**.</span><span class="sxs-lookup"><span data-stu-id="2316a-130">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
      - <span data-ttu-id="2316a-131">Per inoltrare la chiamata alla segreteria telefonica, fare clic su **Inoltra a**segreteria telefonica e quindi nel campo **indirizzo SIP** digitare un indirizzo di segreteria telefonica nel formato SIP: \<username\> @ \<domainname\> (ad esempio, SIP:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="2316a-131">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip:\<username\>@\<domainname\> (for example, sip:bob@contoso.com).</span></span>
    
      - <span data-ttu-id="2316a-132">Per inoltrare la chiamata a un altro numero di telefono, fare clic su **Inoltra a numero di telefono**e quindi nel campo **indirizzo SIP** digitare il numero di telefono nel formato SIP: \<number\> @ \<domainname\> (ad esempio, SIP:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="2316a-132">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip:\<number\>@\<domainname\> (for example, sip:+14255550121@contoso.com).</span></span>
    
      - <span data-ttu-id="2316a-133">Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra a indirizzo SIP**e quindi nel campo **indirizzo SIP** digitare l'URI dell'utente nel formato SIP: \<username\> @ \<domainname\> .</span><span class="sxs-lookup"><span data-stu-id="2316a-133">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip:\<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="2316a-134">Per inoltrare la chiamata a un'altra coda, fare clic su **Inoltra a un'altra coda** e quindi selezionare la coda che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="2316a-134">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>

9.  <span data-ttu-id="2316a-135">Per specificare il numero massimo di chiamate che possono essere contenute nella coda, selezionare la casella di controllo **Abilita overflow coda** e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2316a-135">To specify a maximum number of calls that the queue can hold, select the **Enable queue overflow** check box, and then do the following:</span></span>
    
    1.  <span data-ttu-id="2316a-136">In **Numero massimo di chiamate** selezionare il numero massimo di chiamate che possono essere contenute nella coda.</span><span class="sxs-lookup"><span data-stu-id="2316a-136">In **Maximum number of calls**, select the maximum number of calls that you want the queue to hold.</span></span>
    
    2.  <span data-ttu-id="2316a-137">In **Inoltra la chiamata** selezionare quale chiamata dovrà essere inoltrata quando la coda è piena, ovvero **Chiamata più recente** o **Chiamata meno recente**.</span><span class="sxs-lookup"><span data-stu-id="2316a-137">In **Forward the call**, select which call is to be forwarded when the queue is full: **Newest Call** or **Oldest Call**.</span></span>
    
    3.  <span data-ttu-id="2316a-138">In **Azione chiamata** selezionare l'azione che deve essere eseguita quando viene raggiunta la soglia di overflow, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="2316a-138">In **Call action**, select the action that occurs when the overflow threshold is met as follows:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="2316a-139">Per disconnettere la chiamata dopo il timeout, fare clic su **Disconnetti**.</span><span class="sxs-lookup"><span data-stu-id="2316a-139">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
      - <span data-ttu-id="2316a-140">Per inoltrare la chiamata alla segreteria telefonica, fare clic su **Inoltra a**segreteria telefonica e quindi nel campo **indirizzo SIP** digitare un indirizzo di segreteria telefonica nel formato SIP: \<username\> @ \<domainname\> (ad esempio, SIP:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="2316a-140">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip:\<username\>@\<domainname\> (for example, sip:bob@contoso.com).</span></span>
    
      - <span data-ttu-id="2316a-141">Per inoltrare la chiamata a un altro numero di telefono, fare clic su **Inoltra a numero di telefono**e quindi nel campo **indirizzo SIP** digitare il numero di telefono nel formato SIP: \<number\> @ \<domainname\> (ad esempio, SIP:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="2316a-141">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip:\<number\>@\<domainname\> (for example, sip:+14255550121@contoso.com).</span></span>
    
      - <span data-ttu-id="2316a-142">Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra a indirizzo SIP**e quindi nel campo **indirizzo SIP** digitare l'URI dell'utente nel formato SIP: \<username\> @ \<domainname\> .</span><span class="sxs-lookup"><span data-stu-id="2316a-142">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip:\<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="2316a-143">Per inoltrare la chiamata a un'altra coda, fare clic su **Inoltra a un'altra coda** e quindi selezionare la coda che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="2316a-143">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>

10. <span data-ttu-id="2316a-144">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="2316a-144">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-queue"></a><span data-ttu-id="2316a-145">Per utilizzare Windows PowerShell per creare o modificare una coda</span><span class="sxs-lookup"><span data-stu-id="2316a-145">To use Windows PowerShell to create or modify a queue</span></span>

1.  <span data-ttu-id="2316a-146">Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.</span><span class="sxs-lookup"><span data-stu-id="2316a-146">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2316a-147">Se si è uno dei responsabili di Response Group delegati per un flusso di lavoro gestito, è possibile creare gruppi di agenti e code, nonché assegnare i gruppi di agenti alle code.</span><span class="sxs-lookup"><span data-stu-id="2316a-147">If you are one of the delegated Response Group Managers for a managed workflow, you will be able to create agent groups and queues, and assign agent groups to queues.</span></span>

    
    </div>

2.  <span data-ttu-id="2316a-148">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2316a-148">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="2316a-p107">Creare la richiesta da riprodurre quando viene raggiunta la soglia di timeout della coda e salvarla in una variabile. Nella riga di comando eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="2316a-p107">Create the prompt to be played when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="2316a-151">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2316a-151">For example:</span></span>
    
        "All agents are currently busy. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2316a-152">Per utilizzare un file audio per il messaggio, eseguire il cmdlet <STRONG>Import-CsRgsAudioFile</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="2316a-152">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="2316a-153">Per informazioni dettagliate, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span><span class="sxs-lookup"><span data-stu-id="2316a-153">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="2316a-p109">Definire l'azione da eseguire quando viene raggiunta la soglia di timeout della coda e salvarla in una variabile. Nella riga di comando eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="2316a-p109">Define the action to be taken when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2316a-156">Per informazioni dettagliate sulle possibili azioni e sulla relativa sintassi, vedere <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span><span class="sxs-lookup"><span data-stu-id="2316a-156">For details about possible actions and their syntax, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="2316a-157">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2316a-157">For example:</span></span>
    
        $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate

5.  <span data-ttu-id="2316a-p110">Creare la richiesta da riprodurre quando viene raggiunta la soglia di overflow della coda e salvarla in una variabile. Nella riga di comando eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="2316a-p110">Create the prompt to be played when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="2316a-160">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2316a-160">For example:</span></span>
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2316a-161">Per utilizzare un file audio per il messaggio, eseguire il cmdlet <STRONG>Import-CsRgsAudioFile</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="2316a-161">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="2316a-162">Per informazioni dettagliate, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span><span class="sxs-lookup"><span data-stu-id="2316a-162">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

6.  <span data-ttu-id="2316a-p112">Definire l'azione da eseguire quando viene raggiunta la soglia di overflow della coda e salvarla in una variabile. Nella riga di comando eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="2316a-p112">Define the action to be taken when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2316a-165">Per informazioni dettagliate sulle possibili azioni e sulla relativa sintassi, vedere <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span><span class="sxs-lookup"><span data-stu-id="2316a-165">For details about possible actions and their syntax, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="2316a-166">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2316a-166">For example:</span></span>
    
        $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate

7.  <span data-ttu-id="2316a-167">Recuperare il nome del servizio Response Group e assegnarlo a una variabile.</span><span class="sxs-lookup"><span data-stu-id="2316a-167">Retrieve the service name for the Response Group service and assign it to a variable.</span></span> <span data-ttu-id="2316a-168">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="2316a-168">At the command line, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;

8.  <span data-ttu-id="2316a-169">Ottenere l'identità del gruppo di agenti da assegnare alla coda.</span><span class="sxs-lookup"><span data-stu-id="2316a-169">Get the identity of the agent group to be assigned to the queue.</span></span> <span data-ttu-id="2316a-170">Nella riga di comando eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="2316a-170">At the command line, run:</span></span>
    
        $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2316a-171">Per informazioni dettagliate sulla creazione del gruppo di agenti, vedere <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">New-CsRgsAgentGroup</A></span><span class="sxs-lookup"><span data-stu-id="2316a-171">For details about creating the agent group, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">New-CsRgsAgentGroup</A></span></span>

    
    </div>

9.  <span data-ttu-id="2316a-p115">Creare la coda. Nella riga di comando eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="2316a-p115">Create the queue. At the command line, run:</span></span>
    
        $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
    
    <span data-ttu-id="2316a-174">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2316a-174">For example:</span></span>
    
        $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;

10. <span data-ttu-id="2316a-p116">Verificare che la coda sia stata creata. Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="2316a-p116">Confirm that the queue is created. Run:</span></span>
    
        Get-CsRgsQueue -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2316a-177">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2316a-177">See Also</span></span>


[<span data-ttu-id="2316a-178">New-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="2316a-178">New-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue)  
[<span data-ttu-id="2316a-179">Set-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="2316a-179">Set-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsQueue)  
[<span data-ttu-id="2316a-180">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="2316a-180">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[<span data-ttu-id="2316a-181">New-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="2316a-181">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
[<span data-ttu-id="2316a-182">Get-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="2316a-182">Get-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsQueue)  
[<span data-ttu-id="2316a-183">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="2316a-183">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
[<span data-ttu-id="2316a-184">Remove-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="2316a-184">Remove-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsQueue)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

