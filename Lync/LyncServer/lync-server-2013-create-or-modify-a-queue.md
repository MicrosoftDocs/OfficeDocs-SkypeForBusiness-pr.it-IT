---
title: 'Lync Server 2013: creare o modificare una coda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a queue
ms:assetid: b9d6366a-839f-4651-a01d-9254546cadeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205207(v=OCS.15)
ms:contentKeyID: 48185247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96b6bc1e5f956b5b975e14f07a3c37f2802d1b39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980018"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-queue-in-lync-server-2013"></a><span data-ttu-id="90e14-102">Creare o modificare una coda in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90e14-102">Create or modify a queue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90e14-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="90e14-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="90e14-104">Usare una delle procedure seguenti per creare o modificare una coda.</span><span class="sxs-lookup"><span data-stu-id="90e14-104">Use one of the following procedures to create or modify a queue.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-queue"></a><span data-ttu-id="90e14-105">Per usare il pannello di controllo di Lync Server per creare o modificare una coda</span><span class="sxs-lookup"><span data-stu-id="90e14-105">To use Lync Server Control Panel to create or modify a queue</span></span>

1.  <span data-ttu-id="90e14-106">Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="90e14-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="90e14-107">Se si è uno dei responsabili del gruppo di risposte delegati per un flusso di lavoro gestito, è possibile creare o modificare code di Response Group e assegnarle ai flussi di lavoro gestiti.</span><span class="sxs-lookup"><span data-stu-id="90e14-107">If you are one of the delegated Response Group Managers for a managed workflow, you can create or modify response group queues and assign them to the workflows that you manage.</span></span>

    
    </div>

2.  <span data-ttu-id="90e14-108">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="90e14-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="90e14-109">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="90e14-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="90e14-110">Nella barra di spostamento sinistra fare clic su **Response Groups**, quindi fare clic su **Accoda**.</span><span class="sxs-lookup"><span data-stu-id="90e14-110">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>

4.  <span data-ttu-id="90e14-111">Nella pagina **coda** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="90e14-111">On the **Queue** page, do one of the following:</span></span>
    
      - <span data-ttu-id="90e14-112">Per creare una nuova coda, fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="90e14-112">To create a new queue, click **New**.</span></span> <span data-ttu-id="90e14-113">In **Seleziona un servizio**Digitare parte o tutto il nome del servizio **ApplicationServer** in cui si vuole aggiungere la coda nel campo di ricerca.</span><span class="sxs-lookup"><span data-stu-id="90e14-113">In **Select a Service**, type part or all of the name of the **ApplicationServer** service where you want to add the queue in the search field.</span></span> <span data-ttu-id="90e14-114">Nell'elenco dei servizi risultante fare clic sul servizio desiderato e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="90e14-114">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="90e14-115">Per modificare una coda esistente, digitare tutto o parte del nome della coda nel campo di ricerca.</span><span class="sxs-lookup"><span data-stu-id="90e14-115">To modify an existing queue, type all or part of the queue name in the search field.</span></span> <span data-ttu-id="90e14-116">Nell'elenco di code risultante fare clic sulla coda desiderata, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="90e14-116">In the resulting list of queues, click the queue that you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="90e14-117">In **nome**Digitare un nome identificativo per la coda.</span><span class="sxs-lookup"><span data-stu-id="90e14-117">In **Name**, type an identifying name for the queue.</span></span>

6.  <span data-ttu-id="90e14-118">In **Descrizione**Digitare una descrizione per la coda.</span><span class="sxs-lookup"><span data-stu-id="90e14-118">In **Description**, type a description for the queue.</span></span>

7.  <span data-ttu-id="90e14-119">In **gruppi**specificare i gruppi che si desidera assegnare alla coda.</span><span class="sxs-lookup"><span data-stu-id="90e14-119">In **Groups**, specify the groups you want to assign to the queue.</span></span> <span data-ttu-id="90e14-120">Esegui una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="90e14-120">Do one of the following:</span></span>
    
      - <span data-ttu-id="90e14-121">Per aggiungere un gruppo alla coda, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="90e14-121">To add a group to the queue, click **Select**.</span></span> <span data-ttu-id="90e14-122">Nel campo **Seleziona gruppi** digitare tutto o parte del nome del gruppo di agenti che si vuole assegnare alla coda, fare clic sul gruppo di agenti desiderato e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="90e14-122">In the **Select Groups** search field, type all or part of the name of the agent group that you want to assign to the queue, click the agent group that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="90e14-123">Per rimuovere un gruppo dalla coda, nell'elenco dei gruppi di agenti fare clic sul gruppo che si desidera rimuovere e quindi fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="90e14-123">To remove a group from the queue, in the list of agent groups, click the group that you want to remove, and then click **Remove**.</span></span>
    
      - <span data-ttu-id="90e14-124">Per modificare l'ordine in cui vengono cercati gli agenti, nell'elenco dei gruppi di agenti fare clic su un gruppo e quindi fare clic sulla freccia su o freccia giù.</span><span class="sxs-lookup"><span data-stu-id="90e14-124">To change the order in which agents are searched, in the list of agent groups, click a group, and then click the up arrow or down arrow.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="90e14-125">Quando il server Cerca un agente disponibile per la coda, usa l'ordine dei gruppi.</span><span class="sxs-lookup"><span data-stu-id="90e14-125">When the server searches for an available agent for the queue, it uses group order.</span></span> <span data-ttu-id="90e14-126">Il primo gruppo dell'elenco viene quindi cercato per primo, seguito dal secondo gruppo nell'elenco e così via.</span><span class="sxs-lookup"><span data-stu-id="90e14-126">That is, the first group in the list is searched first, followed by the second group in the list, and so on.</span></span>

        
        </div>

8.  <span data-ttu-id="90e14-127">Per specificare un periodo di tempo massimo per il chiamante in attesa in attesa prima che un agente risponda alla chiamata, selezionare la casella di controllo **Abilita timeout coda** e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="90e14-127">To specify a maximum period of time for a caller to wait on hold before an agent answers the call, select the **Enable queue time-out** check box, and then do the following:</span></span>
    
    1.  <span data-ttu-id="90e14-128">Nel **periodo di timeout (secondi)** specificare il numero massimo di secondi in cui il chiamante attende che un agente risponda alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="90e14-128">In **Time-out period (seconds)**, specify the maximum number of seconds a caller waits for an agent to answer the call.</span></span>
    
    2.  <span data-ttu-id="90e14-129">In **azione chiamata**selezionare l'azione che si verifica quando una chiamata ha un timeout come segue:</span><span class="sxs-lookup"><span data-stu-id="90e14-129">In **Call Action**, select the action that occurs when a call times out as follows:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="90e14-130">Per disconnettere la chiamata dopo il timeout, fare clic su **Disconnetti**.</span><span class="sxs-lookup"><span data-stu-id="90e14-130">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
      - <span data-ttu-id="90e14-131">Per inoltrare la chiamata alla segreteria telefonica, fare clic su **inoltra alla**segreteria telefonica e quindi, nel campo **indirizzo SIP** , digitare un indirizzo di segreteria\<telefonica\>@\<nel formato\> SIP: nomeutente nomedominio (ad esempio, SIP:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="90e14-131">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip:\<username\>@\<domainname\> (for example, sip:bob@contoso.com).</span></span>
    
      - <span data-ttu-id="90e14-132">Per inoltrare la chiamata a un altro numero di telefono, fare clic su **inoltra al numero**di telefono e quindi, nel campo **indirizzo SIP** , digitare il numero di\<telefono\>@\<nel formato\> SIP: Number NomeDominio (ad esempio, SIP:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="90e14-132">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip:\<number\>@\<domainname\> (for example, sip:+14255550121@contoso.com).</span></span>
    
      - <span data-ttu-id="90e14-133">Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra all'indirizzo SIP**e quindi, nel campo **indirizzo SIP** , digitare l'URI per l'utente nel formato\<SIP\>@\<: nomeutente\>NomeDominio.</span><span class="sxs-lookup"><span data-stu-id="90e14-133">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip:\<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="90e14-134">Per inoltrare la chiamata a un'altra coda, fare clic su **Inoltra a un'altra coda**e quindi passare alla coda che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="90e14-134">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>

9.  <span data-ttu-id="90e14-135">Per specificare un numero massimo di chiamate che la coda può contenere, selezionare la casella di controllo **attiva l'overflow delle code** e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="90e14-135">To specify a maximum number of calls that the queue can hold, select the **Enable queue overflow** check box, and then do the following:</span></span>
    
    1.  <span data-ttu-id="90e14-136">In **numero massimo di chiamate**selezionare il numero massimo di chiamate che la coda deve contenere.</span><span class="sxs-lookup"><span data-stu-id="90e14-136">In **Maximum number of calls**, select the maximum number of calls that you want the queue to hold.</span></span>
    
    2.  <span data-ttu-id="90e14-137">In **inoltra la chiamata**selezionare la chiamata da inoltrare quando la coda è piena: chiamata più **recente** o **chiamata più vecchia**.</span><span class="sxs-lookup"><span data-stu-id="90e14-137">In **Forward the call**, select which call is to be forwarded when the queue is full: **Newest Call** or **Oldest Call**.</span></span>
    
    3.  <span data-ttu-id="90e14-138">In **azione chiamata**selezionare l'azione che si verifica quando la soglia di overflow viene soddisfatta come segue:</span><span class="sxs-lookup"><span data-stu-id="90e14-138">In **Call action**, select the action that occurs when the overflow threshold is met as follows:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="90e14-139">Per disconnettere la chiamata dopo il timeout, fare clic su **Disconnetti**.</span><span class="sxs-lookup"><span data-stu-id="90e14-139">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
      - <span data-ttu-id="90e14-140">Per inoltrare la chiamata alla segreteria telefonica, fare clic su **inoltra alla**segreteria telefonica e quindi, nel campo **indirizzo SIP** , digitare un indirizzo di segreteria\<telefonica\>@\<nel formato\> SIP: nomeutente nomedominio (ad esempio, SIP:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="90e14-140">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip:\<username\>@\<domainname\> (for example, sip:bob@contoso.com).</span></span>
    
      - <span data-ttu-id="90e14-141">Per inoltrare la chiamata a un altro numero di telefono, fare clic su **inoltra al numero**di telefono e quindi, nel campo **indirizzo SIP** , digitare il numero di\<telefono\>@\<nel formato\> SIP: Number NomeDominio (ad esempio, SIP:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="90e14-141">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip:\<number\>@\<domainname\> (for example, sip:+14255550121@contoso.com).</span></span>
    
      - <span data-ttu-id="90e14-142">Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra all'indirizzo SIP**e quindi, nel campo **indirizzo SIP** , digitare l'URI per l'utente nel formato\<SIP\>@\<: nomeutente\>NomeDominio.</span><span class="sxs-lookup"><span data-stu-id="90e14-142">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip:\<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="90e14-143">Per inoltrare la chiamata a un'altra coda, fare clic su **Inoltra a un'altra coda**e quindi passare alla coda che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="90e14-143">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>

10. <span data-ttu-id="90e14-144">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="90e14-144">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-queue"></a><span data-ttu-id="90e14-145">Per usare Windows PowerShell per creare o modificare una coda</span><span class="sxs-lookup"><span data-stu-id="90e14-145">To use Windows PowerShell to create or modify a queue</span></span>

1.  <span data-ttu-id="90e14-146">Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="90e14-146">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="90e14-147">Se si è uno dei responsabili del gruppo di risposte delegati per un flusso di lavoro gestito, sarà possibile creare gruppi di agenti e code e assegnare gruppi di agenti alle code.</span><span class="sxs-lookup"><span data-stu-id="90e14-147">If you are one of the delegated Response Group Managers for a managed workflow, you will be able to create agent groups and queues, and assign agent groups to queues.</span></span>

    
    </div>

2.  <span data-ttu-id="90e14-148">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="90e14-148">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="90e14-149">Creare il prompt da riprodurre quando viene soddisfatta la soglia di timeout della coda e salvarla in una variabile.</span><span class="sxs-lookup"><span data-stu-id="90e14-149">Create the prompt to be played when the queue timeout threshold is met, and save it in a variable.</span></span> <span data-ttu-id="90e14-150">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="90e14-150">At the command line, run:</span></span>
    
        $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="90e14-151">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="90e14-151">For example:</span></span>
    
        "All agents are currently busy. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="90e14-152">Per usare un file audio per la richiesta, usare il cmdlet <STRONG>Import-CsRgsAudioFile</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="90e14-152">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="90e14-153">Per informazioni dettagliate, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span><span class="sxs-lookup"><span data-stu-id="90e14-153">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="90e14-154">Definire l'azione da intraprendere quando viene soddisfatta la soglia di timeout della coda e salvarla in una variabile.</span><span class="sxs-lookup"><span data-stu-id="90e14-154">Define the action to be taken when the queue timeout threshold is met, and save it in a variable.</span></span> <span data-ttu-id="90e14-155">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="90e14-155">At the command line, run:</span></span>
    
        $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="90e14-156">Per informazioni dettagliate sulle possibili azioni e sulla relativa sintassi, vedere <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span><span class="sxs-lookup"><span data-stu-id="90e14-156">For details about possible actions and their syntax, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="90e14-157">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="90e14-157">For example:</span></span>
    
        $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate

5.  <span data-ttu-id="90e14-158">Creare il prompt da riprodurre quando viene soddisfatta la soglia di overflow della coda e salvarla in una variabile.</span><span class="sxs-lookup"><span data-stu-id="90e14-158">Create the prompt to be played when the queue overflow threshold is met, and save it in a variable.</span></span> <span data-ttu-id="90e14-159">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="90e14-159">At the command line, run:</span></span>
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="90e14-160">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="90e14-160">For example:</span></span>
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="90e14-161">Per usare un file audio per la richiesta, usare il cmdlet <STRONG>Import-CsRgsAudioFile</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="90e14-161">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="90e14-162">Per informazioni dettagliate, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span><span class="sxs-lookup"><span data-stu-id="90e14-162">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

6.  <span data-ttu-id="90e14-163">Definire l'azione da intraprendere quando viene soddisfatta la soglia di overflow della coda e salvarla in una variabile.</span><span class="sxs-lookup"><span data-stu-id="90e14-163">Define the action to be taken when the queue overflow threshold is met, and save it in a variable.</span></span> <span data-ttu-id="90e14-164">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="90e14-164">At the command line, run:</span></span>
    
        $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="90e14-165">Per informazioni dettagliate sulle possibili azioni e sulla relativa sintassi, vedere <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span><span class="sxs-lookup"><span data-stu-id="90e14-165">For details about possible actions and their syntax, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="90e14-166">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="90e14-166">For example:</span></span>
    
        $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate

7.  <span data-ttu-id="90e14-167">Recuperare il nome del servizio per il servizio Response Group e assegnarlo a una variabile.</span><span class="sxs-lookup"><span data-stu-id="90e14-167">Retrieve the service name for the Response Group service and assign it to a variable.</span></span> <span data-ttu-id="90e14-168">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="90e14-168">At the command line, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;

8.  <span data-ttu-id="90e14-169">Ottenere l'identità del gruppo di agenti da assegnare alla coda.</span><span class="sxs-lookup"><span data-stu-id="90e14-169">Get the identity of the agent group to be assigned to the queue.</span></span> <span data-ttu-id="90e14-170">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="90e14-170">At the command line, run:</span></span>
    
        $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="90e14-171">Per informazioni dettagliate sulla creazione del gruppo di agenti, vedere <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">New-CsRgsAgentGroup</A></span><span class="sxs-lookup"><span data-stu-id="90e14-171">For details about creating the agent group, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">New-CsRgsAgentGroup</A></span></span>

    
    </div>

9.  <span data-ttu-id="90e14-172">Creare la coda.</span><span class="sxs-lookup"><span data-stu-id="90e14-172">Create the queue.</span></span> <span data-ttu-id="90e14-173">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="90e14-173">At the command line, run:</span></span>
    
        $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
    
    <span data-ttu-id="90e14-174">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="90e14-174">For example:</span></span>
    
        $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;

10. <span data-ttu-id="90e14-175">Verificare che la coda sia stata creata.</span><span class="sxs-lookup"><span data-stu-id="90e14-175">Confirm that the queue is created.</span></span> <span data-ttu-id="90e14-176">Eseguire</span><span class="sxs-lookup"><span data-stu-id="90e14-176">Run:</span></span>
    
        Get-CsRgsQueue -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="90e14-177">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90e14-177">See Also</span></span>


[<span data-ttu-id="90e14-178">New-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="90e14-178">New-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue)  
[<span data-ttu-id="90e14-179">Set-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="90e14-179">Set-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsQueue)  
[<span data-ttu-id="90e14-180">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="90e14-180">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[<span data-ttu-id="90e14-181">New-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="90e14-181">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
[<span data-ttu-id="90e14-182">Get-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="90e14-182">Get-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsQueue)  
[<span data-ttu-id="90e14-183">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="90e14-183">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
[<span data-ttu-id="90e14-184">Remove-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="90e14-184">Remove-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsQueue)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

