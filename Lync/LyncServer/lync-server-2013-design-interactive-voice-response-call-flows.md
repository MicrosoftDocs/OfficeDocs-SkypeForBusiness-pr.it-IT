---
title: 'Lync Server 2013: Progettare i flussi di chiamate del sistema IVR (Interactive Voice Response)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Design interactive voice response call flows
ms:assetid: f3477f0a-3ad5-4b13-a73c-046aa451db19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413020(v=OCS.15)
ms:contentKeyID: 48185826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd53ac8d06ec336940abe53d7da1353faf4f9414
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="design-interactive-voice-response-call-flows-in-lync-server-2013"></a><span data-ttu-id="3f164-102">Progettare i flussi di chiamate del sistema IVR (Interactive Voice Response) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f164-102">Design interactive voice response call flows in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f164-103">_**Argomento Ultima modifica:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="3f164-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="3f164-104">Puoi usare la risposta vocale interattiva (IVR) per ottenere informazioni dai chiamanti e indirizzare la chiamata alla coda appropriata.</span><span class="sxs-lookup"><span data-stu-id="3f164-104">You can use interactive voice response (IVR) to obtain information from callers and direct the call to the appropriate queue.</span></span> <span data-ttu-id="3f164-105">Le coppie domande e risposte determinano la coda da usare.</span><span class="sxs-lookup"><span data-stu-id="3f164-105">Question-and-answer pairs determine which queue to use.</span></span> <span data-ttu-id="3f164-106">A seconda della risposta del chiamante, il chiamante sente una domanda di completamento o viene instradato alla coda appropriata.</span><span class="sxs-lookup"><span data-stu-id="3f164-106">Depending on the caller’s response, the caller either hears a follow-up question, or is routed to the appropriate queue.</span></span> <span data-ttu-id="3f164-107">Le domande IVR e le risposte del chiamante vengono fornite all'agente che risponde che accetta la chiamata, fornendo informazioni preziose all'agente.</span><span class="sxs-lookup"><span data-stu-id="3f164-107">The IVR questions and the caller’s responses are provided to the responding agent who accepts the call, providing valuable information to the agent.</span></span>

<div>

## <a name="overview-of-ivr-features"></a><span data-ttu-id="3f164-108">Panoramica delle funzionalità IVR</span><span class="sxs-lookup"><span data-stu-id="3f164-108">Overview of IVR Features</span></span>

<span data-ttu-id="3f164-109">L'applicazione Response Group offre funzionalità di riconoscimento vocale e di sintesi vocale in 26 lingue.</span><span class="sxs-lookup"><span data-stu-id="3f164-109">The Response Group application offers speech recognition and text-to-speech capabilities in 26 languages.</span></span> <span data-ttu-id="3f164-110">È possibile immettere domande IVR usando un file di sintesi vocale o Wave (con estensione wav) o Windows Media Audio (con estensione WMA).</span><span class="sxs-lookup"><span data-stu-id="3f164-110">You can enter IVR questions using text-to-speech or a wave (.wav) or Windows Media audio (.wma) file.</span></span> <span data-ttu-id="3f164-111">I chiamanti possono rispondere usando le risposte DTMF (Voice o Dual-Tone Multifrequency).</span><span class="sxs-lookup"><span data-stu-id="3f164-111">Callers can respond by using voice or dual-tone multifrequency (DTMF) responses.</span></span>

<span data-ttu-id="3f164-112">I flussi di lavoro interattivi supportano fino a due livelli di domande, con ogni domanda che contiene fino a quattro possibili risposte.</span><span class="sxs-lookup"><span data-stu-id="3f164-112">Interactive workflows support up to two levels of questions, with each question having up to four possible answers.</span></span> <span data-ttu-id="3f164-113">Il IVR chiede una domanda al chiamante e, a seconda della risposta del chiamante, instrada il chiamante in una coda o pone una seconda domanda.</span><span class="sxs-lookup"><span data-stu-id="3f164-113">The IVR asks the caller a question, and depending on the caller’s response, routes the caller to a queue or asks a second question.</span></span> <span data-ttu-id="3f164-114">La seconda domanda può anche avere quattro risposte possibili.</span><span class="sxs-lookup"><span data-stu-id="3f164-114">The second question can also have four possible answers.</span></span> <span data-ttu-id="3f164-115">A seconda della risposta alla domanda di secondo livello, il chiamante viene indirizzato alla coda appropriata.</span><span class="sxs-lookup"><span data-stu-id="3f164-115">Depending on the answer to the second-level question, the caller is routed to the appropriate queue.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3f164-116">Quando si progetta il flusso delle chiamate tramite Lync Server Management Shell, è possibile definire qualsiasi livello numerico di domande IVR e qualsiasi numero di risposte.</span><span class="sxs-lookup"><span data-stu-id="3f164-116">When you design call flows by using Lync Server Management Shell, you can define any number levels of IVR questions and any number of answers.</span></span> <span data-ttu-id="3f164-117">Tuttavia, per l'usabilità del chiamante, ti consigliamo di non usare più di tre livelli di domande, con non più di cinque risposte ciascuna.</span><span class="sxs-lookup"><span data-stu-id="3f164-117">However, for caller usability, we recommend that you not use more than three levels of questions, with not more than five answers each.</span></span> <span data-ttu-id="3f164-118">Inoltre, se si progetta un flusso di chiamata con più di due livelli di domande con più di quattro risposte, non è possibile modificare il flusso delle chiamate usando il pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3f164-118">In addition, if you design a call flow that has more than two levels of questions with more than four answers each, you cannot edit the call flow by using Lync Server 2013 Control Panel.</span></span>



</div>

<span data-ttu-id="3f164-119">Le domande IVR e le risposte del chiamante vengono fornite all'agente che risponde che accetta la chiamata.</span><span class="sxs-lookup"><span data-stu-id="3f164-119">The IVR questions and the caller’s responses are provided to the responding agent who accepts the call.</span></span>

</div>

<div>

## <a name="working-with-speech-technologies"></a><span data-ttu-id="3f164-120">Uso delle tecnologie per la sintesi vocale</span><span class="sxs-lookup"><span data-stu-id="3f164-120">Working with Speech Technologies</span></span>

<span data-ttu-id="3f164-121">Le tecnologie vocali, ad esempio il riconoscimento vocale e la sintesi vocale, possono migliorare l'esperienza dei clienti e consentire agli utenti di accedere alle informazioni in modo più naturale ed efficace.</span><span class="sxs-lookup"><span data-stu-id="3f164-121">Speech technologies, such as speech recognition and text-to-speech, can enhance customer experience and let people access information more naturally and effectively.</span></span> <span data-ttu-id="3f164-122">Tuttavia, possono esserci casi in cui il testo specificato o la risposta vocale dell'utente non vengono riconosciuti correttamente dal motore vocale.</span><span class="sxs-lookup"><span data-stu-id="3f164-122">However, there can be cases where the specified text or the user voice response is not recognized correctly by the speech engine.</span></span> <span data-ttu-id="3f164-123">Ad esempio, il simbolo\#"" viene tradotto dal motore di sintesi vocale come parola "numero".</span><span class="sxs-lookup"><span data-stu-id="3f164-123">For example, the "\#" symbol is translated by the text-to-speech engine as the word "number."</span></span> <span data-ttu-id="3f164-124">Questo problema può essere mitigato dalle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3f164-124">This issue can be mitigated by the following:</span></span>

  - <span data-ttu-id="3f164-125">Il motore vocale assegna al chiamante cinque tentativi per rispondere alla domanda.</span><span class="sxs-lookup"><span data-stu-id="3f164-125">The speech engine gives the caller five attempts to answer the question.</span></span> <span data-ttu-id="3f164-126">Se il chiamante risponde alla domanda in modo non corretto (ovvero la risposta non è una delle risposte specificate) o non fornisce una risposta, il chiamante riceverà un'altra opportunità per rispondere alla domanda.</span><span class="sxs-lookup"><span data-stu-id="3f164-126">If the caller answers the question incorrectly (that is, the answer is not one of the specified responses) or does not provide an answer at all, the caller gets another chance to answer the question.</span></span> <span data-ttu-id="3f164-127">Il chiamante ha cinque tentativi per rispondere alla domanda prima di essere disconnessa.</span><span class="sxs-lookup"><span data-stu-id="3f164-127">The caller has five attempts to answer the question before being disconnected.</span></span> <span data-ttu-id="3f164-128">Puoi configurare il IVR per riprodurre un messaggio personalizzato dopo ogni errore del chiamante.</span><span class="sxs-lookup"><span data-stu-id="3f164-128">You can configure the IVR to play a customized message after each caller error.</span></span> <span data-ttu-id="3f164-129">La domanda viene ripetuta ogni volta.</span><span class="sxs-lookup"><span data-stu-id="3f164-129">The question is repeated each time.</span></span>

  - <span data-ttu-id="3f164-130">Per ridurre al minimo la possibilità di interpretare il rumore ambientale dal motore vocale come risposta, usare risposte più lunghe.</span><span class="sxs-lookup"><span data-stu-id="3f164-130">To minimize the potential for ambient noise to be interpreted by the speech engine as a response, use longer responses.</span></span> <span data-ttu-id="3f164-131">Ad esempio, le risposte dovrebbero avere più di una sillaba e dovrebbero sembrare molto diverse tra loro.</span><span class="sxs-lookup"><span data-stu-id="3f164-131">For example, responses should have more than one syllable and should sound significantly different from each other.</span></span>

  - <span data-ttu-id="3f164-132">Se le domande hanno risposte sia vocali che DTMF, configurare le risposte vocali con parole che rappresentano il concetto piuttosto che la risposta DTMF.</span><span class="sxs-lookup"><span data-stu-id="3f164-132">If your questions have both speech and DTMF responses, configure the speech responses with words that represent the concept rather than the DTMF response.</span></span> <span data-ttu-id="3f164-133">Ad esempio, invece di usare "premi o pronuncia uno" USA "premi 1 o pronuncia fatturazione".</span><span class="sxs-lookup"><span data-stu-id="3f164-133">For example, instead of using "Press or say one" use "Press 1 or say billing."</span></span>

  - <span data-ttu-id="3f164-134">Dopo aver progettato il tuo IVR, chiama il flusso di lavoro, ascolta le richieste, Rispondi a ogni prompt usando la voce e verifica che i suoni IVR e si comportano come previsto.</span><span class="sxs-lookup"><span data-stu-id="3f164-134">After you design your IVR, call the workflow, listen to the prompts, respond to each of the prompts using voice, and verify that the IVR sounds and behaves as expected.</span></span> <span data-ttu-id="3f164-135">Puoi quindi modificare il IVR per risolvere eventuali problemi di interpretazione.</span><span class="sxs-lookup"><span data-stu-id="3f164-135">You can then modify the IVR to fix any interpretation issues.</span></span> <span data-ttu-id="3f164-136">Dopo l'esempio precedente, se è necessario fare riferimento alla \# chiave, è possibile riscrivere il prompt di IVR per usare il nome della chiave anziché il \# simbolo.</span><span class="sxs-lookup"><span data-stu-id="3f164-136">Following the previous example, if you need to refer to the \# key, you can rewrite your IVR prompt to use the key name, rather than the \# symbol.</span></span> <span data-ttu-id="3f164-137">Ad esempio, "per comunicare con le vendite, premi il tasto cancelletto".</span><span class="sxs-lookup"><span data-stu-id="3f164-137">For example, "To talk to sales, press the pound key."</span></span>

</div>

<div>

## <a name="ivr-design-examples"></a><span data-ttu-id="3f164-138">Esempi di progettazione IVR</span><span class="sxs-lookup"><span data-stu-id="3f164-138">IVR Design Examples</span></span>

<span data-ttu-id="3f164-139">Le sezioni seguenti contengono esempi di diversi scenari IVR e coppie domande e risposte.</span><span class="sxs-lookup"><span data-stu-id="3f164-139">The following sections contain examples of different IVR scenarios and question-and-answer pairs.</span></span>

<div>

## <a name="ivr-with-one-level-of-questions"></a><span data-ttu-id="3f164-140">IVR con un livello di domande</span><span class="sxs-lookup"><span data-stu-id="3f164-140">IVR with One Level of Questions</span></span>

<span data-ttu-id="3f164-141">L'esempio seguente mostra un IVR che usa un livello di domande.</span><span class="sxs-lookup"><span data-stu-id="3f164-141">The following example shows an IVR that uses one level of questions.</span></span> <span data-ttu-id="3f164-142">Usa il riconoscimento vocale per rilevare la risposta del chiamante.</span><span class="sxs-lookup"><span data-stu-id="3f164-142">It uses speech recognition to detect the caller’s response.</span></span>

<span data-ttu-id="3f164-143">**Domanda:** "Grazie per aver chiamato le risorse umane.</span><span class="sxs-lookup"><span data-stu-id="3f164-143">**Question:** "Thank you for calling Human Resources.</span></span> <span data-ttu-id="3f164-144">Se si vuole parlare con il libro paga, dire libro paga.</span><span class="sxs-lookup"><span data-stu-id="3f164-144">If you would like to speak to payroll, say payroll.</span></span> <span data-ttu-id="3f164-145">In caso contrario, dire HR. "</span><span class="sxs-lookup"><span data-stu-id="3f164-145">Otherwise, say HR."</span></span>

  - <span data-ttu-id="3f164-146">L' **opzione 1 è selezionata:** Il chiamante viene indirizzato al team paghe.</span><span class="sxs-lookup"><span data-stu-id="3f164-146">**Option 1 is selected:** The caller is routed to the payroll team.</span></span>

  - <span data-ttu-id="3f164-147">**Opzione 2 selezionata:** Il chiamante viene indirizzato al team risorse umane.</span><span class="sxs-lookup"><span data-stu-id="3f164-147">**Option 2 is selected:** The caller is routed to the human resources team.</span></span>

<span data-ttu-id="3f164-148">La figura seguente mostra il flusso delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="3f164-148">The following figure shows the call flow.</span></span>

<span data-ttu-id="3f164-149">**Flusso delle chiamate interattive a un livello**</span><span class="sxs-lookup"><span data-stu-id="3f164-149">**One-level interactive call flow**</span></span>

<span data-ttu-id="3f164-150">![Progettare flussi di chiamate tramite il sistema IVR (Interactive Voice Response)](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "Progettare flussi di chiamate tramite il sistema IVR (Interactive Voice Response)")</span><span class="sxs-lookup"><span data-stu-id="3f164-150">![Design Call Flows by Using Interactive Voice Respo](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "Design Call Flows by Using Interactive Voice Respo")</span></span>

</div>

<div>

## <a name="ivr-with-two-levels-of-questions"></a><span data-ttu-id="3f164-151">IVR con due livelli di domande</span><span class="sxs-lookup"><span data-stu-id="3f164-151">IVR with Two Levels of Questions</span></span>

<span data-ttu-id="3f164-152">L'esempio seguente mostra un IVR che usa due livelli di domande.</span><span class="sxs-lookup"><span data-stu-id="3f164-152">The following example shows an IVR that uses two levels of questions.</span></span> <span data-ttu-id="3f164-153">Consente ai chiamanti di rispondere usando l'input della tastiera vocale o DTMF.</span><span class="sxs-lookup"><span data-stu-id="3f164-153">It allows callers to respond using either speech or DTMF keypad input.</span></span>

<span data-ttu-id="3f164-154">**Domanda:** "Grazie per aver chiamato l'help desk IT.</span><span class="sxs-lookup"><span data-stu-id="3f164-154">**Question:** "Thank you for calling the IT Help Desk.</span></span> <span data-ttu-id="3f164-155">Se si ha un problema di accesso alla rete, premere 1 o Say Network.</span><span class="sxs-lookup"><span data-stu-id="3f164-155">If you have a network access problem, press 1 or say network.</span></span> <span data-ttu-id="3f164-156">Se si ha un problema con il software, premere 2 o dire software.</span><span class="sxs-lookup"><span data-stu-id="3f164-156">If you have a software problem, press 2 or say software.</span></span> <span data-ttu-id="3f164-157">Se si ha un problema hardware, premere 3 o dire hardware.</span><span class="sxs-lookup"><span data-stu-id="3f164-157">If you have a hardware problem, press 3 or say hardware."</span></span>

  - <span data-ttu-id="3f164-158">L' **opzione 1 è selezionata:** Il chiamante viene indirizzato al team di supporto della rete.</span><span class="sxs-lookup"><span data-stu-id="3f164-158">**Option 1 is selected:** The caller is routed to the network support team.</span></span>

  - <span data-ttu-id="3f164-159">**Opzione 2 selezionata:** Al chiamante viene posta una domanda di follow-up:</span><span class="sxs-lookup"><span data-stu-id="3f164-159">**Option 2 is selected:** The caller is asked a follow-up question:</span></span>
    
    <span data-ttu-id="3f164-160">**Domanda:** "Se si tratta di un problema di sistema operativo, premere 1 o dire sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="3f164-160">**Question:** "If this is an operating system problem, press 1 or say operating system.</span></span> <span data-ttu-id="3f164-161">Se si tratta di un problema con un'applicazione interna, premere 2 o dire applicazione interna.</span><span class="sxs-lookup"><span data-stu-id="3f164-161">If this is a problem with an internal application, press 2 or say internal application.</span></span> <span data-ttu-id="3f164-162">In caso contrario, premere 3 o dire altro.</span><span class="sxs-lookup"><span data-stu-id="3f164-162">Otherwise, press 3 or say other."</span></span>
    
      - <span data-ttu-id="3f164-163">L' **opzione 1 è selezionata:** Il chiamante viene indirizzato al team di supporto dei sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="3f164-163">**Option 1 is selected:** The caller is routed to the operating systems support team.</span></span>
    
      - <span data-ttu-id="3f164-164">**Opzione 2 selezionata:** Il chiamante viene indirizzato al team di supporto delle applicazioni interne.</span><span class="sxs-lookup"><span data-stu-id="3f164-164">**Option 2 is selected:** The caller is routed to the internal applications support team.</span></span>
    
      - <span data-ttu-id="3f164-165">**Opzione 3 selezionata:** Il chiamante viene indirizzato al team di supporto software.</span><span class="sxs-lookup"><span data-stu-id="3f164-165">**Option 3 is selected:** The caller is routed to the software support team.</span></span>

  - <span data-ttu-id="3f164-166">**Opzione 3 selezionata:** Al chiamante viene posta una domanda di follow-up:</span><span class="sxs-lookup"><span data-stu-id="3f164-166">**Option 3 is selected:** The caller is asked a follow-up question:</span></span>
    
    <span data-ttu-id="3f164-167">**Domanda:** "Se si tratta di un problema di stampante, premere 1.</span><span class="sxs-lookup"><span data-stu-id="3f164-167">**Question:** "If this is a printer problem press 1.</span></span> <span data-ttu-id="3f164-168">In caso contrario, premere 2. "</span><span class="sxs-lookup"><span data-stu-id="3f164-168">Otherwise, press 2."</span></span>
    
      - <span data-ttu-id="3f164-169">L' **opzione 1 è selezionata:** Il chiamante viene indirizzato al team di supporto della stampante.</span><span class="sxs-lookup"><span data-stu-id="3f164-169">**Option 1 is selected:** The caller is routed to the printer support team.</span></span>
    
      - <span data-ttu-id="3f164-170">**Opzione 2 selezionata:** Il chiamante viene indirizzato al team di supporto hardware.</span><span class="sxs-lookup"><span data-stu-id="3f164-170">**Option 2 is selected:** The caller is routed to the hardware support team.</span></span>

<span data-ttu-id="3f164-171">La figura seguente mostra il flusso delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="3f164-171">The following figure shows the call flow.</span></span>

<span data-ttu-id="3f164-172">**Flusso delle chiamate interattive a due livelli**</span><span class="sxs-lookup"><span data-stu-id="3f164-172">**Two-level interactive call flow**</span></span>

<span data-ttu-id="3f164-173">![Progettare flussi di chiamate tramite il sistema IVR (Interactive Voice Response)](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "Progettare flussi di chiamate tramite il sistema IVR (Interactive Voice Response)")</span><span class="sxs-lookup"><span data-stu-id="3f164-173">![Design Call Flows by Using Interactive Voice Respo](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "Design Call Flows by Using Interactive Voice Respo")</span></span>

</div>

</div>

<div>

## <a name="best-practices"></a><span data-ttu-id="3f164-174">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="3f164-174">Best Practices</span></span>

<span data-ttu-id="3f164-175">Nell'elenco seguente vengono illustrate alcune procedure consigliate per la progettazione del dispositivo IVR:</span><span class="sxs-lookup"><span data-stu-id="3f164-175">The following list describes some best practices for designing your IVR:</span></span>

  - <span data-ttu-id="3f164-176">Consentire al chiamante di accedere rapidamente all'attività.</span><span class="sxs-lookup"><span data-stu-id="3f164-176">Let the caller get to the task quickly.</span></span> <span data-ttu-id="3f164-177">Evitare di fornire troppe informazioni o lunghi messaggi di marketing nel sistema IVR.</span><span class="sxs-lookup"><span data-stu-id="3f164-177">Avoid providing too much information or lengthy marketing messages in your IVR.</span></span>

  - <span data-ttu-id="3f164-178">Se si vuole includere un messaggio lungo, valutare la possibilità di accodarlo alla prima domanda anziché al messaggio di benvenuto.</span><span class="sxs-lookup"><span data-stu-id="3f164-178">If you want to include a lengthy message, consider appending it to the first question instead of to the welcome message.</span></span> <span data-ttu-id="3f164-179">I chiamanti possono ignorare il messaggio se fa parte della prima domanda rispondendo alla domanda, ma non possono ignorare il messaggio di benvenuto.</span><span class="sxs-lookup"><span data-stu-id="3f164-179">Callers can bypass the message if it is part of the first question by answering the question, but they cannot bypass the welcome message.</span></span>

  - <span data-ttu-id="3f164-180">Parla nella lingua del chiamante.</span><span class="sxs-lookup"><span data-stu-id="3f164-180">Speak in the caller’s language.</span></span> <span data-ttu-id="3f164-181">Evitare la lingua stilata.</span><span class="sxs-lookup"><span data-stu-id="3f164-181">Avoid stilted language.</span></span> <span data-ttu-id="3f164-182">Parla in modo naturale.</span><span class="sxs-lookup"><span data-stu-id="3f164-182">Speak naturally.</span></span>

  - <span data-ttu-id="3f164-183">Scrivere richieste efficienti ed efficaci.</span><span class="sxs-lookup"><span data-stu-id="3f164-183">Write efficient and effective prompts.</span></span> <span data-ttu-id="3f164-184">Rimuovere eventuali opzioni non necessarie.</span><span class="sxs-lookup"><span data-stu-id="3f164-184">Remove any unnecessary options.</span></span> <span data-ttu-id="3f164-185">Strutturare le informazioni in modo che la risposta prevista del chiamante si trovi alla fine della frase.</span><span class="sxs-lookup"><span data-stu-id="3f164-185">Structure the information so that the caller’s expected response is at the end of the sentence.</span></span> <span data-ttu-id="3f164-186">Ad esempio, "per parlare con il team di vendita, premere 1".</span><span class="sxs-lookup"><span data-stu-id="3f164-186">For example, “To speak to the sales team, press 1."</span></span>

  - <span data-ttu-id="3f164-187">Rendere le risposte vocali intuitive.</span><span class="sxs-lookup"><span data-stu-id="3f164-187">Make voice responses user friendly.</span></span> <span data-ttu-id="3f164-188">Ad esempio, se specifichi sia il DTMF che le risposte vocali, USA qualcosa di simile a: "per parlare con il team di vendita, premi 1 o pronuncia vendite".</span><span class="sxs-lookup"><span data-stu-id="3f164-188">For example, if you specify both DTMF and voice responses, use something like: "To speak to the sales team, press 1 or say sales."</span></span>

  - <span data-ttu-id="3f164-189">Testare il IVR su un gruppo di utenti prima di distribuirlo nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3f164-189">Test the IVR on a group of users before you deploy it across your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

