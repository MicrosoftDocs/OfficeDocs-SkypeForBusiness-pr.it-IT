---
title: 'Lync Server 2013: flussi di chiamate di risposta vocale interattive'
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
ms.openlocfilehash: 78032a23fce6bb210ecec6eb828178aabddf9b52
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="design-interactive-voice-response-call-flows-in-lync-server-2013"></a>Progettare flussi di chiamate di risposta vocale interattivi in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-25_

È possibile utilizzare Interactive Voice Response (IVR) per ottenere informazioni dai chiamanti e indirizzare la chiamata verso la coda appropriata. Coppie di domande e risposte stabiliscono la coda da utilizzare. A seconda della risposta, il chiamante ascolterà una domanda aggiuntiva oppure verrà instradato alla coda appropriata. Le domande del sistema IVR e le risposte del chiamante vengono fornite all'agente addetto alla risposta che accetta la chiamata, fornendo importanti informazioni all'agente.

<div>

## <a name="overview-of-ivr-features"></a>Panoramica delle funzionalità del sistema IVR

L'applicazione Response Group offre funzionalità di riconoscimento vocale e di sintesi vocale in 26 lingue. È possibile immettere domande IVR utilizzando la sintesi vocale oppure un file WAVE (WAV) o Windows Media Audio (WMA). I chiamanti possono rispondere tramite input vocale o multifrequenza (DTMF, Dual-Tone Multi-Frequency).

I flussi di lavoro interattivi supportano fino a due livelli di domande, con ogni domanda che prevede fino a quattro possibili risposte. Il sistema IVR rivolge al chiamante una domanda e, in base alla risposta del chiamante, lo instrada verso una coda oppure pone una seconda domanda. Anche la seconda domanda prevede quattro possibili risposte. A seconda della risposta alla domanda di secondo livello, il chiamante verrà instradato alla coda appropriata.

<div>


> [!NOTE]  
> Quando si progettano flussi di chiamata utilizzando Lync Server Management Shell, è possibile definire i livelli di numero di domande IVR e qualsiasi numero di risposte. Tuttavia, per la facilità di utilizzo del chiamante, è consigliabile non utilizzare più di tre livelli di domande, con non più di cinque risposte per ognuno. Inoltre, se si progetta un flusso di chiamata con più di due livelli di domande con più di quattro risposte ciascuna, non è possibile modificare il flusso di chiamata utilizzando il pannello di controllo di Lync Server 2013.



</div>

Le domande del sistema IVR e le risposte del chiamante vengono fornite all'agente addetto alla risposta quando accetta la chiamata.

</div>

<div>

## <a name="working-with-speech-technologies"></a>Utilizzo di tecnologie vocali

Le tecnologie vocali, quali il riconoscimento vocale e la sintesi vocale, consentono di ottimizzare l'esperienza utente e di accedere alle informazioni in modo più naturale ed efficace. Vi sono alcuni casi, tuttavia, in cui il testo specificato e/o la risposta vocale dell'utente non vengono riconosciuti correttamente dal motore di sintesi vocale. Ad esempio, il simbolo\#"" viene convertito dal motore di sintesi vocale come parola "Number". È possibile correggere questo problema nel modo seguente:

  - Il motore di sintesi vocale consente al chiamante quattro tentativi per rispondere alla domanda. Se il chiamante risponde in modo errato alla domanda, ovvero la risposta non è una di quelle specificate, oppure non fornisce alcuna risposta, ottiene un'altra possibilità di rispondere. Il chiamante ha a disposizione cinque tentativi per rispondere alla domanda prima di essere disconnesso. È possibile configurare il sistema IVR per riprodurre un messaggio personalizzato dopo ogni errore del chiamante. La domanda viene ripetuta ogni volta.

  - Per ridurre la possibilità che il rumore ambientale venga interpretato come una risposta dal motore di sintesi vocale, utilizzare risposte più lunghe. Ad esempio, le risposte dovrebbero essere costituite da più di una sillaba e devono avere suoni diversi tra loro.

  - Se le domande prevedono risposte vocali e DTMF, configurare le risposte vocali con parole che rappresentano il concetto anziché la risposta DTMF. Ad esempio, anziché "Premere o dire uno" utilizzare "Premere 1 o dire fatturazione".

  - Dopo avere progettato il sistema IVR, chiamare il flusso di lavoro, ascoltare le richieste, fornire risposte vocali a ognuna delle richieste e verificare che il sistema funzioni nel modo previsto. È quindi possibile modificare il sistema IVR per correggere eventuali errori di interpretazione. Dopo l'esempio precedente, se è necessario fare riferimento alla \# chiave, è possibile riscrivere il prompt di IVR per utilizzare il nome della chiave anziché il \# simbolo. Ad esempio, "Per parlare con il reparto vendite, premere cancelletto".

</div>

<div>

## <a name="ivr-design-examples"></a>Esempi di progettazione del sistema IVR

Nelle sezioni seguenti sono riportati gli esempi di diversi scenari IRV e coppie di domande/risposte.

<div>

## <a name="ivr-with-one-level-of-questions"></a>Sistema IVR con un livello di domande

Nell'esempio seguente è illustrato un sistema IVR con un singolo livello di domande. Il sistema utilizza il riconoscimento vocale per rilevare la risposta del chiamante.

**Domanda:** "Grazie per aver chiamato il reparto Risorse umane. Se desidera parlare con la sezione addetta alle retribuzioni, dica retribuzioni. Altrimenti, dica risorse umane".

  - **Viene selezionata l'opzione 1:** il chiamante viene instradato alla sezione addetta alle retribuzioni.

  - **Viene selezionata l'opzione 2:** il chiamante viene instradato al reparto Risorse umane.

Nella figura seguente viene illustrato il flusso delle chiamate.

**Flusso di chiamate interattivo a un livello**

![Progettare flussi di chiamate tramite il respo Interactive Voice](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "Progettare flussi di chiamate tramite il respo Interactive Voice")

</div>

<div>

## <a name="ivr-with-two-levels-of-questions"></a>Sistema IVR con due livelli di domande

Nell'esempio seguente viene illustrato un sistema IVR con due livelli di domande. Il sistema consente ai chiamanti di rispondere tramite input vocale o DTMF con tastiera.

**Domanda:** "Grazie per aver chiamato il supporto tecnico del reparto IT. Se il problema riguarda l'accesso di rete, prema 1 o dica Rete. Se il problema riguarda il software, prema 2 o dica Software. Se riguarda l'hardware, prema 3 o dica Hardware."

  - **Viene selezionata l'opzione 1:** il chiamante viene instradato al team del supporto di rete.

  - **Viene selezionata l'opzione 2:** al chiamante viene formulata un'altra domanda.
    
    **Domanda:** "Se il problema riguarda il sistema operativo, prema 1 o dica Sistema operativo. Se riguarda un'applicazione interna, prema 2 o dica Applicazione interna. Altrimenti, prema 3 o dica Altro".
    
      - **Viene selezionata l'opzione 1:** il chiamante viene instradato al team del supporto del sistema operativo.
    
      - **Viene selezionata l'opzione 2:** il chiamante viene instradato al team del supporto delle applicazioni interne.
    
      - **Viene selezionata l'opzione 3:** il chiamante viene instradato al team del supporto software.

  - **Viene selezionata l'opzione 3:** al chiamante viene formulata un'altra domanda.
    
    **Domanda:** "Se il problema riguarda una stampante, prema 1. Altrimenti, prema 2".
    
      - **Viene selezionata l'opzione 1:** il chiamante viene instradato al team del supporto delle stampanti.
    
      - **Viene selezionata l'opzione 2:** il chiamante viene instradato al team del supporto hardware.

Nella figura seguente viene illustrato il flusso delle chiamate.

**Flusso di chiamate interattivo a due livelli**

![Progettare flussi di chiamate tramite il respo Interactive Voice](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "Progettare flussi di chiamate tramite il respo Interactive Voice")

</div>

</div>

<div>

## <a name="best-practices"></a>Procedure consigliate

Nell'elenco seguente vengono descritte alcune procedure consigliate nella progettazione del sistema IVR:

  - Consentire al chiamante di selezionare l'attività rapidamente. Evitare di includere troppe informazioni o messaggi di marketing lunghi nel sistema IVR.

  - Se si desidera includere un messaggio lungo, è consigliabile aggiungerlo alla fine della prima domanda anziché dopo il messaggio iniziale. I chiamanti possono ignorare il messaggio se fa parte della prima domanda rispondendo alla domanda, ma non possono ignorare il messaggio iniziale.

  - Parlare nella lingua del chiamante. Evitare uno stile formale e parlare in modo naturale.

  - Scrivere domande efficienti ed efficaci. Rimuovere le opzioni non necessarie. Strutturare le informazioni in modo tale che la risposta prevista del chiamante sia alla fine della frase. Ad esempio, "Per parlare con il team vendite, prema 1".

  - Scegliere risposte vocali semplici. Ad esempio, se si specificano sia risposte DTMF che risposte vocali, utilizzare "Per parlare con il team vendite, prema 1 o dica vendite".

  - Testare il sistema IVR con un gruppo di utenti prima di distribuirlo nell'intera organizzazione.

</div>

</div>

<span> </span>

</div>

</div>

</div>

