---
title: 'Lync Server 2013: creare o modificare una coda'
description: 'Lync Server 2013: creare o modificare una coda.'
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
ms.openlocfilehash: cbd8d6d00df8d6a09ef5861d876bd1363db09e3d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574532"
---
# <a name="create-or-modify-a-queue-in-lync-server-2013"></a><span data-ttu-id="a20da-103">Creare o modificare una coda in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a20da-103">Create or modify a queue in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a20da-104">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="a20da-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="a20da-105">Per creare o modificare una coda, utilizzare una delle procedure illustrate di seguito.</span><span class="sxs-lookup"><span data-stu-id="a20da-105">Use one of the following procedures to create or modify a queue.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-queue"></a><span data-ttu-id="a20da-106">Per utilizzare il pannello di controllo di Lync Server per creare o modificare una coda</span><span class="sxs-lookup"><span data-stu-id="a20da-106">To use Lync Server Control Panel to create or modify a queue</span></span>

1.  <span data-ttu-id="a20da-107">Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.</span><span class="sxs-lookup"><span data-stu-id="a20da-107">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a20da-108">Se si è uno dei responsabili di Response Group delegati per un flusso di lavoro gestito, è possibile creare o modificare le code di Response Group e assegnarle ai flussi di lavoro gestiti personalmente.</span><span class="sxs-lookup"><span data-stu-id="a20da-108">If you are one of the delegated Response Group Managers for a managed workflow, you can create or modify response group queues and assign them to the workflows that you manage.</span></span>

    
    </div>

2.  <span data-ttu-id="a20da-109">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a20da-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a20da-110">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a20da-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a20da-111">Sulla barra di spostamento sinistra fare clic su **Response Group** e quindi su **Coda**.</span><span class="sxs-lookup"><span data-stu-id="a20da-111">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>

4.  <span data-ttu-id="a20da-112">Nella pagina **Coda** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a20da-112">On the **Queue** page, do one of the following:</span></span>
    
      - <span data-ttu-id="a20da-113">Per creare una nuova coda, fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="a20da-113">To create a new queue, click **New**.</span></span> <span data-ttu-id="a20da-114">In **Seleziona un servizio** digitare nel campo di ricerca parte oppure tutto il nome del servizio **ApplicationServer** in cui si intende aggiungere la coda.</span><span class="sxs-lookup"><span data-stu-id="a20da-114">In **Select a Service**, type part or all of the name of the **ApplicationServer** service where you want to add the queue in the search field.</span></span> <span data-ttu-id="a20da-115">Nell'elenco di servizi risultante fare clic sul servizio desiderato e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a20da-115">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="a20da-p103">Per modificare una coda esistente, digitare tutto o una parte del nome della coda nel campo di ricerca. Nell'elenco di code risultante fare clic sulla coda desiderata, su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="a20da-p103">To modify an existing queue, type all or part of the queue name in the search field. In the resulting list of queues, click the queue that you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="a20da-118">In **Nome** digitare un nome identificativo della coda.</span><span class="sxs-lookup"><span data-stu-id="a20da-118">In **Name**, type an identifying name for the queue.</span></span>

6.  <span data-ttu-id="a20da-119">In **Descrizione** digitare una descrizione per la coda.</span><span class="sxs-lookup"><span data-stu-id="a20da-119">In **Description**, type a description for the queue.</span></span>

7.  <span data-ttu-id="a20da-p104">In **Gruppi** specificare i gruppo che si desidera assegnare alla coda. Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a20da-p104">In **Groups**, specify the groups you want to assign to the queue. Do one of the following:</span></span>
    
      - <span data-ttu-id="a20da-p105">Per aggiungere un gruppo alla coda, fare clic su **Seleziona**. Nel campo di ricerca **Seleziona gruppi** digitare tutto o parte del nome del gruppo di agenti che si intende assegnare alla coda, fare clic sul gruppo desiderato e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a20da-p105">To add a group to the queue, click **Select**. In the **Select Groups** search field, type all or part of the name of the agent group that you want to assign to the queue, click the agent group that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="a20da-124">Per rimuovere un gruppo dalla coda, nell'elenco di gruppi di agenti fare clic sul gruppo che si desidera rimuovere e quindi fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="a20da-124">To remove a group from the queue, in the list of agent groups, click the group that you want to remove, and then click **Remove**.</span></span>
    
      - <span data-ttu-id="a20da-125">Per modificare l'ordine in cui gli agenti vengono ricercati, nell'elenco di gruppi di agenti fare clic su un gruppo e quindi sulla freccia rivolta verso l'alto o verso il basso.</span><span class="sxs-lookup"><span data-stu-id="a20da-125">To change the order in which agents are searched, in the list of agent groups, click a group, and then click the up arrow or down arrow.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a20da-p106">Per la ricerca di un agente disponibile per la coda, il server utilizza l'ordine dei gruppi. La ricerca pertanto viene eseguita prima nel primo gruppo, quindi nel secondo gruppo dell'elenco e così via.</span><span class="sxs-lookup"><span data-stu-id="a20da-p106">When the server searches for an available agent for the queue, it uses group order. That is, the first group in the list is searched first, followed by the second group in the list, and so on.</span></span>

        
        </div>

8.  <span data-ttu-id="a20da-128">Per specificare un periodo di tempo massimo in cui un chiamante resta in attesa prima che un agente risponda alla chiamata, selezionare la casella di controllo **Abilita timeout coda** e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a20da-128">To specify a maximum period of time for a caller to wait on hold before an agent answers the call, select the **Enable queue time-out** check box, and then do the following:</span></span>
    
    1.  <span data-ttu-id="a20da-129">In **Periodo di timeout (secondi)** specificare il numero massimo di secondi che un chiamante può attendere prima che un agente risponda alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="a20da-129">In **Time-out period (seconds)**, specify the maximum number of seconds a caller waits for an agent to answer the call.</span></span>
    
    2.  <span data-ttu-id="a20da-130">In **Azione chiamata** selezionare l'azione che deve essere eseguita quando si verifica il timeout di una chiamata, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a20da-130">In **Call Action**, select the action that occurs when a call times out as follows:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="a20da-131">Per disconnettere la chiamata dopo il timeout, fare clic su **Disconnetti**.</span><span class="sxs-lookup"><span data-stu-id="a20da-131">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
      - <span data-ttu-id="a20da-132">Per inoltrare la chiamata alla segreteria telefonica, fare clic su **Inoltra a**segreteria telefonica e quindi nel campo **indirizzo SIP** digitare un indirizzo di segreteria telefonica nel formato SIP: \<username\> @ \<domainname\> (ad esempio, SIP:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="a20da-132">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip:\<username\>@\<domainname\> (for example, sip:bob@contoso.com).</span></span>
    
      - <span data-ttu-id="a20da-133">Per inoltrare la chiamata a un altro numero di telefono, fare clic su **Inoltra a numero di telefono**e quindi nel campo **indirizzo SIP** digitare il numero di telefono nel formato SIP: \<number\> @ \<domainname\> (ad esempio, SIP:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="a20da-133">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip:\<number\>@\<domainname\> (for example, sip:+14255550121@contoso.com).</span></span>
    
      - <span data-ttu-id="a20da-134">Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra a indirizzo SIP**e quindi nel campo **indirizzo SIP** digitare l'URI dell'utente nel formato SIP: \<username\> @ \<domainname\> .</span><span class="sxs-lookup"><span data-stu-id="a20da-134">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip:\<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="a20da-135">Per inoltrare la chiamata a un'altra coda, fare clic su **Inoltra a un'altra coda** e quindi selezionare la coda che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="a20da-135">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>

9.  <span data-ttu-id="a20da-136">Per specificare il numero massimo di chiamate che possono essere contenute nella coda, selezionare la casella di controllo **Abilita overflow coda** e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a20da-136">To specify a maximum number of calls that the queue can hold, select the **Enable queue overflow** check box, and then do the following:</span></span>
    
    1.  <span data-ttu-id="a20da-137">In **Numero massimo di chiamate** selezionare il numero massimo di chiamate che possono essere contenute nella coda.</span><span class="sxs-lookup"><span data-stu-id="a20da-137">In **Maximum number of calls**, select the maximum number of calls that you want the queue to hold.</span></span>
    
    2.  <span data-ttu-id="a20da-138">In **Inoltra la chiamata** selezionare quale chiamata dovrà essere inoltrata quando la coda è piena, ovvero **Chiamata più recente** o **Chiamata meno recente**.</span><span class="sxs-lookup"><span data-stu-id="a20da-138">In **Forward the call**, select which call is to be forwarded when the queue is full: **Newest Call** or **Oldest Call**.</span></span>
    
    3.  <span data-ttu-id="a20da-139">In **Azione chiamata** selezionare l'azione che deve essere eseguita quando viene raggiunta la soglia di overflow, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a20da-139">In **Call action**, select the action that occurs when the overflow threshold is met as follows:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="a20da-140">Per disconnettere la chiamata dopo il timeout, fare clic su **Disconnetti**.</span><span class="sxs-lookup"><span data-stu-id="a20da-140">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
      - <span data-ttu-id="a20da-141">Per inoltrare la chiamata alla segreteria telefonica, fare clic su **Inoltra a**segreteria telefonica e quindi nel campo **indirizzo SIP** digitare un indirizzo di segreteria telefonica nel formato SIP: \<username\> @ \<domainname\> (ad esempio, SIP:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="a20da-141">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip:\<username\>@\<domainname\> (for example, sip:bob@contoso.com).</span></span>
    
      - <span data-ttu-id="a20da-142">Per inoltrare la chiamata a un altro numero di telefono, fare clic su **Inoltra a numero di telefono**e quindi nel campo **indirizzo SIP** digitare il numero di telefono nel formato SIP: \<number\> @ \<domainname\> (ad esempio, SIP:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="a20da-142">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip:\<number\>@\<domainname\> (for example, sip:+14255550121@contoso.com).</span></span>
    
      - <span data-ttu-id="a20da-143">Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra a indirizzo SIP**e quindi nel campo **indirizzo SIP** digitare l'URI dell'utente nel formato SIP: \<username\> @ \<domainname\> .</span><span class="sxs-lookup"><span data-stu-id="a20da-143">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip:\<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="a20da-144">Per inoltrare la chiamata a un'altra coda, fare clic su **Inoltra a un'altra coda** e quindi selezionare la coda che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="a20da-144">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>

10. <span data-ttu-id="a20da-145">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="a20da-145">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-queue"></a><span data-ttu-id="a20da-146">Per utilizzare Windows PowerShell per creare o modificare una coda</span><span class="sxs-lookup"><span data-stu-id="a20da-146">To use Windows PowerShell to create or modify a queue</span></span>

1.  <span data-ttu-id="a20da-147">Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.</span><span class="sxs-lookup"><span data-stu-id="a20da-147">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a20da-148">Se si è uno dei responsabili di Response Group delegati per un flusso di lavoro gestito, è possibile creare gruppi di agenti e code, nonché assegnare i gruppi di agenti alle code.</span><span class="sxs-lookup"><span data-stu-id="a20da-148">If you are one of the delegated Response Group Managers for a managed workflow, you will be able to create agent groups and queues, and assign agent groups to queues.</span></span>

    
    </div>

2.  <span data-ttu-id="a20da-149">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a20da-149">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="a20da-p107">Creare la richiesta da riprodurre quando viene raggiunta la soglia di timeout della coda e salvarla in una variabile. Nella riga di comando eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="a20da-p107">Create the prompt to be played when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="a20da-152">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a20da-152">For example:</span></span>
    
        "All agents are currently busy. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a20da-153">Per utilizzare un file audio per il messaggio, eseguire il cmdlet <STRONG>Import-CsRgsAudioFile</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a20da-153">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="a20da-154">Per informazioni dettagliate, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span><span class="sxs-lookup"><span data-stu-id="a20da-154">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="a20da-p109">Definire l'azione da eseguire quando viene raggiunta la soglia di timeout della coda e salvarla in una variabile. Nella riga di comando eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="a20da-p109">Define the action to be taken when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a20da-157">Per informazioni dettagliate sulle possibili azioni e sulla relativa sintassi, vedere <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span><span class="sxs-lookup"><span data-stu-id="a20da-157">For details about possible actions and their syntax, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="a20da-158">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a20da-158">For example:</span></span>
    
        $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate

5.  <span data-ttu-id="a20da-p110">Creare la richiesta da riprodurre quando viene raggiunta la soglia di overflow della coda e salvarla in una variabile. Nella riga di comando eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="a20da-p110">Create the prompt to be played when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="a20da-161">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a20da-161">For example:</span></span>
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a20da-162">Per utilizzare un file audio per il messaggio, eseguire il cmdlet <STRONG>Import-CsRgsAudioFile</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a20da-162">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="a20da-163">Per informazioni dettagliate, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span><span class="sxs-lookup"><span data-stu-id="a20da-163">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

6.  <span data-ttu-id="a20da-p112">Definire l'azione da eseguire quando viene raggiunta la soglia di overflow della coda e salvarla in una variabile. Nella riga di comando eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="a20da-p112">Define the action to be taken when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a20da-166">Per informazioni dettagliate sulle possibili azioni e sulla relativa sintassi, vedere <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span><span class="sxs-lookup"><span data-stu-id="a20da-166">For details about possible actions and their syntax, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="a20da-167">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a20da-167">For example:</span></span>
    
        $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate

7.  <span data-ttu-id="a20da-168">Recuperare il nome del servizio Response Group e assegnarlo a una variabile.</span><span class="sxs-lookup"><span data-stu-id="a20da-168">Retrieve the service name for the Response Group service and assign it to a variable.</span></span> <span data-ttu-id="a20da-169">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="a20da-169">At the command line, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;

8.  <span data-ttu-id="a20da-170">Ottenere l'identità del gruppo di agenti da assegnare alla coda.</span><span class="sxs-lookup"><span data-stu-id="a20da-170">Get the identity of the agent group to be assigned to the queue.</span></span> <span data-ttu-id="a20da-171">Nella riga di comando eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="a20da-171">At the command line, run:</span></span>
    
        $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a20da-172">Per informazioni dettagliate sulla creazione del gruppo di agenti, vedere <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">New-CsRgsAgentGroup</A></span><span class="sxs-lookup"><span data-stu-id="a20da-172">For details about creating the agent group, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">New-CsRgsAgentGroup</A></span></span>

    
    </div>

9.  <span data-ttu-id="a20da-p115">Creare la coda. Nella riga di comando eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="a20da-p115">Create the queue. At the command line, run:</span></span>
    
        $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
    
    <span data-ttu-id="a20da-175">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a20da-175">For example:</span></span>
    
        $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;

10. <span data-ttu-id="a20da-p116">Verificare che la coda sia stata creata. Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="a20da-p116">Confirm that the queue is created. Run:</span></span>
    
        Get-CsRgsQueue -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a20da-178">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a20da-178">See Also</span></span>


[<span data-ttu-id="a20da-179">New-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="a20da-179">New-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue)  
[<span data-ttu-id="a20da-180">Set-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="a20da-180">Set-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsQueue)  
[<span data-ttu-id="a20da-181">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="a20da-181">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[<span data-ttu-id="a20da-182">New-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="a20da-182">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
[<span data-ttu-id="a20da-183">Get-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="a20da-183">Get-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsQueue)  
[<span data-ttu-id="a20da-184">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="a20da-184">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
[<span data-ttu-id="a20da-185">Remove-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="a20da-185">Remove-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsQueue)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

