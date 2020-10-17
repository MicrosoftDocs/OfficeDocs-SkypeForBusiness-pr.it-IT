---
title: 'Lync Server 2013: flussi di chiamate di risposta vocale interattive'
description: 'Lync Server 2013: progetta flussi di chiamate di risposta vocale interattive.'
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
ms.openlocfilehash: ccf80c1e3226052d952697a4d9fb967f3b681c95
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555312"
---
# <a name="design-interactive-voice-response-call-flows-in-lync-server-2013"></a><span data-ttu-id="979bf-103">Progettare flussi di chiamate di risposta vocale interattivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="979bf-103">Design interactive voice response call flows in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="979bf-104">_**Ultimo argomento modificato:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="979bf-104">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="979bf-p101">È possibile utilizzare Interactive Voice Response (IVR) per ottenere informazioni dai chiamanti e indirizzare la chiamata verso la coda appropriata. Coppie di domande e risposte stabiliscono la coda da utilizzare. A seconda della risposta, il chiamante ascolterà una domanda aggiuntiva oppure verrà instradato alla coda appropriata. Le domande del sistema IVR e le risposte del chiamante vengono fornite all'agente addetto alla risposta che accetta la chiamata, fornendo importanti informazioni all'agente.</span><span class="sxs-lookup"><span data-stu-id="979bf-p101">You can use interactive voice response (IVR) to obtain information from callers and direct the call to the appropriate queue. Question-and-answer pairs determine which queue to use. Depending on the caller’s response, the caller either hears a follow-up question, or is routed to the appropriate queue. The IVR questions and the caller’s responses are provided to the responding agent who accepts the call, providing valuable information to the agent.</span></span>

<div>

## <a name="overview-of-ivr-features"></a><span data-ttu-id="979bf-109">Panoramica delle funzionalità del sistema IVR</span><span class="sxs-lookup"><span data-stu-id="979bf-109">Overview of IVR Features</span></span>

<span data-ttu-id="979bf-110">L'applicazione Response Group offre funzionalità di riconoscimento vocale e di sintesi vocale in 26 lingue.</span><span class="sxs-lookup"><span data-stu-id="979bf-110">The Response Group application offers speech recognition and text-to-speech capabilities in 26 languages.</span></span> <span data-ttu-id="979bf-111">È possibile immettere domande IVR utilizzando la sintesi vocale oppure un file WAVE (WAV) o Windows Media Audio (WMA).</span><span class="sxs-lookup"><span data-stu-id="979bf-111">You can enter IVR questions using text-to-speech or a wave (.wav) or Windows Media audio (.wma) file.</span></span> <span data-ttu-id="979bf-112">I chiamanti possono rispondere tramite input vocale o multifrequenza (DTMF, Dual-Tone Multi-Frequency).</span><span class="sxs-lookup"><span data-stu-id="979bf-112">Callers can respond by using voice or dual-tone multifrequency (DTMF) responses.</span></span>

<span data-ttu-id="979bf-p103">I flussi di lavoro interattivi supportano fino a due livelli di domande, con ogni domanda che prevede fino a quattro possibili risposte. Il sistema IVR rivolge al chiamante una domanda e, in base alla risposta del chiamante, lo instrada verso una coda oppure pone una seconda domanda. Anche la seconda domanda prevede quattro possibili risposte. A seconda della risposta alla domanda di secondo livello, il chiamante verrà instradato alla coda appropriata.</span><span class="sxs-lookup"><span data-stu-id="979bf-p103">Interactive workflows support up to two levels of questions, with each question having up to four possible answers. The IVR asks the caller a question, and depending on the caller’s response, routes the caller to a queue or asks a second question. The second question can also have four possible answers. Depending on the answer to the second-level question, the caller is routed to the appropriate queue.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="979bf-117">Quando si progettano flussi di chiamata utilizzando Lync Server Management Shell, è possibile definire i livelli di numero di domande IVR e qualsiasi numero di risposte.</span><span class="sxs-lookup"><span data-stu-id="979bf-117">When you design call flows by using Lync Server Management Shell, you can define any number levels of IVR questions and any number of answers.</span></span> <span data-ttu-id="979bf-118">Tuttavia, per la facilità di utilizzo del chiamante, è consigliabile non utilizzare più di tre livelli di domande, con non più di cinque risposte per ognuno.</span><span class="sxs-lookup"><span data-stu-id="979bf-118">However, for caller usability, we recommend that you not use more than three levels of questions, with not more than five answers each.</span></span> <span data-ttu-id="979bf-119">Inoltre, se si progetta un flusso di chiamata con più di due livelli di domande con più di quattro risposte ciascuna, non è possibile modificare il flusso di chiamata utilizzando il pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="979bf-119">In addition, if you design a call flow that has more than two levels of questions with more than four answers each, you cannot edit the call flow by using Lync Server 2013 Control Panel.</span></span>



</div>

<span data-ttu-id="979bf-120">Le domande del sistema IVR e le risposte del chiamante vengono fornite all'agente addetto alla risposta quando accetta la chiamata.</span><span class="sxs-lookup"><span data-stu-id="979bf-120">The IVR questions and the caller’s responses are provided to the responding agent who accepts the call.</span></span>

</div>

<div>

## <a name="working-with-speech-technologies"></a><span data-ttu-id="979bf-121">Utilizzo di tecnologie vocali</span><span class="sxs-lookup"><span data-stu-id="979bf-121">Working with Speech Technologies</span></span>

<span data-ttu-id="979bf-122">Le tecnologie vocali, quali il riconoscimento vocale e la sintesi vocale, consentono di ottimizzare l'esperienza utente e di accedere alle informazioni in modo più naturale ed efficace.</span><span class="sxs-lookup"><span data-stu-id="979bf-122">Speech technologies, such as speech recognition and text-to-speech, can enhance customer experience and let people access information more naturally and effectively.</span></span> <span data-ttu-id="979bf-123">Vi sono alcuni casi, tuttavia, in cui il testo specificato e/o la risposta vocale dell'utente non vengono riconosciuti correttamente dal motore di sintesi vocale.</span><span class="sxs-lookup"><span data-stu-id="979bf-123">However, there can be cases where the specified text or the user voice response is not recognized correctly by the speech engine.</span></span> <span data-ttu-id="979bf-124">Ad esempio, il \# simbolo "" viene convertito dal motore di sintesi vocale come parola "Number".</span><span class="sxs-lookup"><span data-stu-id="979bf-124">For example, the "\#" symbol is translated by the text-to-speech engine as the word "number."</span></span> <span data-ttu-id="979bf-125">È possibile correggere questo problema nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="979bf-125">This issue can be mitigated by the following:</span></span>

  - <span data-ttu-id="979bf-p106">Il motore di sintesi vocale consente al chiamante quattro tentativi per rispondere alla domanda. Se il chiamante risponde in modo errato alla domanda, ovvero la risposta non è una di quelle specificate, oppure non fornisce alcuna risposta, ottiene un'altra possibilità di rispondere. Il chiamante ha a disposizione cinque tentativi per rispondere alla domanda prima di essere disconnesso. È possibile configurare il sistema IVR per riprodurre un messaggio personalizzato dopo ogni errore del chiamante. La domanda viene ripetuta ogni volta.</span><span class="sxs-lookup"><span data-stu-id="979bf-p106">The speech engine gives the caller five attempts to answer the question. If the caller answers the question incorrectly (that is, the answer is not one of the specified responses) or does not provide an answer at all, the caller gets another chance to answer the question. The caller has five attempts to answer the question before being disconnected. You can configure the IVR to play a customized message after each caller error. The question is repeated each time.</span></span>

  - <span data-ttu-id="979bf-p107">Per ridurre la possibilità che il rumore ambientale venga interpretato come una risposta dal motore di sintesi vocale, utilizzare risposte più lunghe. Ad esempio, le risposte dovrebbero essere costituite da più di una sillaba e devono avere suoni diversi tra loro.</span><span class="sxs-lookup"><span data-stu-id="979bf-p107">To minimize the potential for ambient noise to be interpreted by the speech engine as a response, use longer responses. For example, responses should have more than one syllable and should sound significantly different from each other.</span></span>

  - <span data-ttu-id="979bf-p108">Se le domande prevedono risposte vocali e DTMF, configurare le risposte vocali con parole che rappresentano il concetto anziché la risposta DTMF. Ad esempio, anziché "Premere o dire uno" utilizzare "Premere 1 o dire fatturazione".</span><span class="sxs-lookup"><span data-stu-id="979bf-p108">If your questions have both speech and DTMF responses, configure the speech responses with words that represent the concept rather than the DTMF response. For example, instead of using "Press or say one" use "Press 1 or say billing."</span></span>

  - <span data-ttu-id="979bf-135">Dopo avere progettato il sistema IVR, chiamare il flusso di lavoro, ascoltare le richieste, fornire risposte vocali a ognuna delle richieste e verificare che il sistema funzioni nel modo previsto.</span><span class="sxs-lookup"><span data-stu-id="979bf-135">After you design your IVR, call the workflow, listen to the prompts, respond to each of the prompts using voice, and verify that the IVR sounds and behaves as expected.</span></span> <span data-ttu-id="979bf-136">È quindi possibile modificare il sistema IVR per correggere eventuali errori di interpretazione.</span><span class="sxs-lookup"><span data-stu-id="979bf-136">You can then modify the IVR to fix any interpretation issues.</span></span> <span data-ttu-id="979bf-137">Dopo l'esempio precedente, se è necessario fare riferimento alla \# chiave, è possibile riscrivere il prompt di IVR per utilizzare il nome della chiave anziché il \# simbolo.</span><span class="sxs-lookup"><span data-stu-id="979bf-137">Following the previous example, if you need to refer to the \# key, you can rewrite your IVR prompt to use the key name, rather than the \# symbol.</span></span> <span data-ttu-id="979bf-138">Ad esempio, "Per parlare con il reparto vendite, premere cancelletto".</span><span class="sxs-lookup"><span data-stu-id="979bf-138">For example, "To talk to sales, press the pound key."</span></span>

</div>

<div>

## <a name="ivr-design-examples"></a><span data-ttu-id="979bf-139">Esempi di progettazione del sistema IVR</span><span class="sxs-lookup"><span data-stu-id="979bf-139">IVR Design Examples</span></span>

<span data-ttu-id="979bf-140">Nelle sezioni seguenti sono riportati gli esempi di diversi scenari IRV e coppie di domande/risposte.</span><span class="sxs-lookup"><span data-stu-id="979bf-140">The following sections contain examples of different IVR scenarios and question-and-answer pairs.</span></span>

<div>

## <a name="ivr-with-one-level-of-questions"></a><span data-ttu-id="979bf-141">Sistema IVR con un livello di domande</span><span class="sxs-lookup"><span data-stu-id="979bf-141">IVR with One Level of Questions</span></span>

<span data-ttu-id="979bf-p110">Nell'esempio seguente è illustrato un sistema IVR con un singolo livello di domande. Il sistema utilizza il riconoscimento vocale per rilevare la risposta del chiamante.</span><span class="sxs-lookup"><span data-stu-id="979bf-p110">The following example shows an IVR that uses one level of questions. It uses speech recognition to detect the caller’s response.</span></span>

<span data-ttu-id="979bf-p111">**Domanda:** "Grazie per aver chiamato il reparto Risorse umane. Se desidera parlare con la sezione addetta alle retribuzioni, dica retribuzioni. Altrimenti, dica risorse umane".</span><span class="sxs-lookup"><span data-stu-id="979bf-p111">**Question:** "Thank you for calling Human Resources. If you would like to speak to payroll, say payroll. Otherwise, say HR."</span></span>

  - <span data-ttu-id="979bf-147">**Viene selezionata l'opzione 1:** il chiamante viene instradato alla sezione addetta alle retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="979bf-147">**Option 1 is selected:** The caller is routed to the payroll team.</span></span>

  - <span data-ttu-id="979bf-148">**Viene selezionata l'opzione 2:** il chiamante viene instradato al reparto Risorse umane.</span><span class="sxs-lookup"><span data-stu-id="979bf-148">**Option 2 is selected:** The caller is routed to the human resources team.</span></span>

<span data-ttu-id="979bf-149">Nella figura seguente viene illustrato il flusso delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="979bf-149">The following figure shows the call flow.</span></span>

<span data-ttu-id="979bf-150">**Flusso di chiamate interattivo a un livello**</span><span class="sxs-lookup"><span data-stu-id="979bf-150">**One-level interactive call flow**</span></span>

<span data-ttu-id="979bf-151">![Progettare flussi di chiamate tramite il respo Interactive Voice](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "Progettare flussi di chiamate tramite il respo Interactive Voice")</span><span class="sxs-lookup"><span data-stu-id="979bf-151">![Design Call Flows by Using Interactive Voice Respo](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "Design Call Flows by Using Interactive Voice Respo")</span></span>

</div>

<div>

## <a name="ivr-with-two-levels-of-questions"></a><span data-ttu-id="979bf-152">Sistema IVR con due livelli di domande</span><span class="sxs-lookup"><span data-stu-id="979bf-152">IVR with Two Levels of Questions</span></span>

<span data-ttu-id="979bf-p112">Nell'esempio seguente viene illustrato un sistema IVR con due livelli di domande. Il sistema consente ai chiamanti di rispondere tramite input vocale o DTMF con tastiera.</span><span class="sxs-lookup"><span data-stu-id="979bf-p112">The following example shows an IVR that uses two levels of questions. It allows callers to respond using either speech or DTMF keypad input.</span></span>

<span data-ttu-id="979bf-p113">**Domanda:** "Grazie per aver chiamato il supporto tecnico del reparto IT. Se il problema riguarda l'accesso di rete, prema 1 o dica Rete. Se il problema riguarda il software, prema 2 o dica Software. Se riguarda l'hardware, prema 3 o dica Hardware."</span><span class="sxs-lookup"><span data-stu-id="979bf-p113">**Question:** "Thank you for calling the IT Help Desk. If you have a network access problem, press 1 or say network. If you have a software problem, press 2 or say software. If you have a hardware problem, press 3 or say hardware."</span></span>

  - <span data-ttu-id="979bf-159">**Viene selezionata l'opzione 1:** il chiamante viene instradato al team del supporto di rete.</span><span class="sxs-lookup"><span data-stu-id="979bf-159">**Option 1 is selected:** The caller is routed to the network support team.</span></span>

  - <span data-ttu-id="979bf-160">**Viene selezionata l'opzione 2:** al chiamante viene formulata un'altra domanda.</span><span class="sxs-lookup"><span data-stu-id="979bf-160">**Option 2 is selected:** The caller is asked a follow-up question:</span></span>
    
    <span data-ttu-id="979bf-p114">**Domanda:** "Se il problema riguarda il sistema operativo, prema 1 o dica Sistema operativo. Se riguarda un'applicazione interna, prema 2 o dica Applicazione interna. Altrimenti, prema 3 o dica Altro".</span><span class="sxs-lookup"><span data-stu-id="979bf-p114">**Question:** "If this is an operating system problem, press 1 or say operating system. If this is a problem with an internal application, press 2 or say internal application. Otherwise, press 3 or say other."</span></span>
    
      - <span data-ttu-id="979bf-164">**Viene selezionata l'opzione 1:** il chiamante viene instradato al team del supporto del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="979bf-164">**Option 1 is selected:** The caller is routed to the operating systems support team.</span></span>
    
      - <span data-ttu-id="979bf-165">**Viene selezionata l'opzione 2:** il chiamante viene instradato al team del supporto delle applicazioni interne.</span><span class="sxs-lookup"><span data-stu-id="979bf-165">**Option 2 is selected:** The caller is routed to the internal applications support team.</span></span>
    
      - <span data-ttu-id="979bf-166">**Viene selezionata l'opzione 3:** il chiamante viene instradato al team del supporto software.</span><span class="sxs-lookup"><span data-stu-id="979bf-166">**Option 3 is selected:** The caller is routed to the software support team.</span></span>

  - <span data-ttu-id="979bf-167">**Viene selezionata l'opzione 3:** al chiamante viene formulata un'altra domanda.</span><span class="sxs-lookup"><span data-stu-id="979bf-167">**Option 3 is selected:** The caller is asked a follow-up question:</span></span>
    
    <span data-ttu-id="979bf-p115">**Domanda:** "Se il problema riguarda una stampante, prema 1. Altrimenti, prema 2".</span><span class="sxs-lookup"><span data-stu-id="979bf-p115">**Question:** "If this is a printer problem press 1. Otherwise, press 2."</span></span>
    
      - <span data-ttu-id="979bf-170">**Viene selezionata l'opzione 1:** il chiamante viene instradato al team del supporto delle stampanti.</span><span class="sxs-lookup"><span data-stu-id="979bf-170">**Option 1 is selected:** The caller is routed to the printer support team.</span></span>
    
      - <span data-ttu-id="979bf-171">**Viene selezionata l'opzione 2:** il chiamante viene instradato al team del supporto hardware.</span><span class="sxs-lookup"><span data-stu-id="979bf-171">**Option 2 is selected:** The caller is routed to the hardware support team.</span></span>

<span data-ttu-id="979bf-172">Nella figura seguente viene illustrato il flusso delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="979bf-172">The following figure shows the call flow.</span></span>

<span data-ttu-id="979bf-173">**Flusso di chiamate interattivo a due livelli**</span><span class="sxs-lookup"><span data-stu-id="979bf-173">**Two-level interactive call flow**</span></span>

<span data-ttu-id="979bf-174">![Progettare flussi di chiamate tramite il respo Interactive Voice](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "Progettare flussi di chiamate tramite il respo Interactive Voice")</span><span class="sxs-lookup"><span data-stu-id="979bf-174">![Design Call Flows by Using Interactive Voice Respo](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "Design Call Flows by Using Interactive Voice Respo")</span></span>

</div>

</div>

<div>

## <a name="best-practices"></a><span data-ttu-id="979bf-175">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="979bf-175">Best Practices</span></span>

<span data-ttu-id="979bf-176">Nell'elenco seguente vengono descritte alcune procedure consigliate nella progettazione del sistema IVR:</span><span class="sxs-lookup"><span data-stu-id="979bf-176">The following list describes some best practices for designing your IVR:</span></span>

  - <span data-ttu-id="979bf-p116">Consentire al chiamante di selezionare l'attività rapidamente. Evitare di includere troppe informazioni o messaggi di marketing lunghi nel sistema IVR.</span><span class="sxs-lookup"><span data-stu-id="979bf-p116">Let the caller get to the task quickly. Avoid providing too much information or lengthy marketing messages in your IVR.</span></span>

  - <span data-ttu-id="979bf-p117">Se si desidera includere un messaggio lungo, è consigliabile aggiungerlo alla fine della prima domanda anziché dopo il messaggio iniziale. I chiamanti possono ignorare il messaggio se fa parte della prima domanda rispondendo alla domanda, ma non possono ignorare il messaggio iniziale.</span><span class="sxs-lookup"><span data-stu-id="979bf-p117">If you want to include a lengthy message, consider appending it to the first question instead of to the welcome message. Callers can bypass the message if it is part of the first question by answering the question, but they cannot bypass the welcome message.</span></span>

  - <span data-ttu-id="979bf-p118">Parlare nella lingua del chiamante. Evitare uno stile formale e parlare in modo naturale.</span><span class="sxs-lookup"><span data-stu-id="979bf-p118">Speak in the caller’s language. Avoid stilted language. Speak naturally.</span></span>

  - <span data-ttu-id="979bf-p119">Scrivere domande efficienti ed efficaci. Rimuovere le opzioni non necessarie. Strutturare le informazioni in modo tale che la risposta prevista del chiamante sia alla fine della frase. Ad esempio, "Per parlare con il team vendite, prema 1".</span><span class="sxs-lookup"><span data-stu-id="979bf-p119">Write efficient and effective prompts. Remove any unnecessary options. Structure the information so that the caller’s expected response is at the end of the sentence. For example, “To speak to the sales team, press 1."</span></span>

  - <span data-ttu-id="979bf-p120">Scegliere risposte vocali semplici. Ad esempio, se si specificano sia risposte DTMF che risposte vocali, utilizzare "Per parlare con il team vendite, prema 1 o dica vendite".</span><span class="sxs-lookup"><span data-stu-id="979bf-p120">Make voice responses user friendly. For example, if you specify both DTMF and voice responses, use something like: "To speak to the sales team, press 1 or say sales."</span></span>

  - <span data-ttu-id="979bf-190">Testare il sistema IVR con un gruppo di utenti prima di distribuirlo nell'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="979bf-190">Test the IVR on a group of users before you deploy it across your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

