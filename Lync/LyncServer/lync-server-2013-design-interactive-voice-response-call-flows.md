---
title: 'Lync Server 2013: Progettare i flussi di chiamate del sistema IVR (Interactive Voice Response)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Design interactive voice response call flows
ms:assetid: f3477f0a-3ad5-4b13-a73c-046aa451db19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413020(v=OCS.15)
ms:contentKeyID: 48185826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 487fa3d4842ad67f3433966a08a889e454450351
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978862"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="design-interactive-voice-response-call-flows-in-lync-server-2013"></a>Progettare i flussi di chiamate del sistema IVR (Interactive Voice Response) in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-25_

Puoi usare la risposta vocale interattiva (IVR) per ottenere informazioni dai chiamanti e indirizzare la chiamata alla coda appropriata. Le coppie domande e risposte determinano la coda da usare. A seconda della risposta del chiamante, il chiamante sente una domanda di completamento o viene instradato alla coda appropriata. Le domande IVR e le risposte del chiamante vengono fornite all'agente che risponde che accetta la chiamata, fornendo informazioni preziose all'agente.

<div>

## <a name="overview-of-ivr-features"></a>Panoramica delle funzionalità IVR

L'applicazione Response Group offre funzionalità di riconoscimento vocale e di sintesi vocale in 26 lingue. È possibile immettere domande IVR usando un file di sintesi vocale o Wave (con estensione wav) o Windows Media Audio (con estensione WMA). I chiamanti possono rispondere usando le risposte DTMF (Voice o Dual-Tone Multifrequency).

I flussi di lavoro interattivi supportano fino a due livelli di domande, con ogni domanda che contiene fino a quattro possibili risposte. Il IVR chiede una domanda al chiamante e, a seconda della risposta del chiamante, instrada il chiamante in una coda o pone una seconda domanda. La seconda domanda può anche avere quattro risposte possibili. A seconda della risposta alla domanda di secondo livello, il chiamante viene indirizzato alla coda appropriata.

<div>


> [!NOTE]  
> Quando si progetta il flusso delle chiamate tramite Lync Server Management Shell, è possibile definire qualsiasi livello numerico di domande IVR e qualsiasi numero di risposte. Tuttavia, per l'usabilità del chiamante, ti consigliamo di non usare più di tre livelli di domande, con non più di cinque risposte ciascuna. Inoltre, se si progetta un flusso di chiamata con più di due livelli di domande con più di quattro risposte, non è possibile modificare il flusso delle chiamate usando il pannello di controllo di Lync Server 2013.



</div>

Le domande IVR e le risposte del chiamante vengono fornite all'agente che risponde che accetta la chiamata.

</div>

<div>

## <a name="working-with-speech-technologies"></a>Uso delle tecnologie per la sintesi vocale

Le tecnologie vocali, ad esempio il riconoscimento vocale e la sintesi vocale, possono migliorare l'esperienza dei clienti e consentire agli utenti di accedere alle informazioni in modo più naturale ed efficace. Tuttavia, possono esserci casi in cui il testo specificato o la risposta vocale dell'utente non vengono riconosciuti correttamente dal motore vocale. Ad esempio, il simbolo\#"" viene tradotto dal motore di sintesi vocale come parola "numero". Questo problema può essere mitigato dalle operazioni seguenti:

  - Il motore vocale assegna al chiamante cinque tentativi per rispondere alla domanda. Se il chiamante risponde alla domanda in modo non corretto (ovvero la risposta non è una delle risposte specificate) o non fornisce una risposta, il chiamante riceverà un'altra opportunità per rispondere alla domanda. Il chiamante ha cinque tentativi per rispondere alla domanda prima di essere disconnessa. Puoi configurare il IVR per riprodurre un messaggio personalizzato dopo ogni errore del chiamante. La domanda viene ripetuta ogni volta.

  - Per ridurre al minimo la possibilità di interpretare il rumore ambientale dal motore vocale come risposta, usare risposte più lunghe. Ad esempio, le risposte dovrebbero avere più di una sillaba e dovrebbero sembrare molto diverse tra loro.

  - Se le domande hanno risposte sia vocali che DTMF, configurare le risposte vocali con parole che rappresentano il concetto piuttosto che la risposta DTMF. Ad esempio, invece di usare "premi o pronuncia uno" USA "premi 1 o pronuncia fatturazione".

  - Dopo aver progettato il tuo IVR, chiama il flusso di lavoro, ascolta le richieste, Rispondi a ogni prompt usando la voce e verifica che i suoni IVR e si comportano come previsto. Puoi quindi modificare il IVR per risolvere eventuali problemi di interpretazione. Dopo l'esempio precedente, se è necessario fare riferimento alla \# chiave, è possibile riscrivere il prompt di IVR per usare il nome della chiave anziché il \# simbolo. Ad esempio, "per comunicare con le vendite, premi il tasto cancelletto".

</div>

<div>

## <a name="ivr-design-examples"></a>Esempi di progettazione IVR

Le sezioni seguenti contengono esempi di diversi scenari IVR e coppie domande e risposte.

<div>

## <a name="ivr-with-one-level-of-questions"></a>IVR con un livello di domande

L'esempio seguente mostra un IVR che usa un livello di domande. Usa il riconoscimento vocale per rilevare la risposta del chiamante.

**Domanda:** "Grazie per aver chiamato le risorse umane. Se si vuole parlare con il libro paga, dire libro paga. In caso contrario, dire HR. "

  - L' **opzione 1 è selezionata:** Il chiamante viene indirizzato al team paghe.

  - **Opzione 2 selezionata:** Il chiamante viene indirizzato al team risorse umane.

La figura seguente mostra il flusso delle chiamate.

**Flusso delle chiamate interattive a un livello**

![Progettazione dei flussi di chiamata]tramite il(images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "flusso delle chiamate") interattive tramite respo vocale

</div>

<div>

## <a name="ivr-with-two-levels-of-questions"></a>IVR con due livelli di domande

L'esempio seguente mostra un IVR che usa due livelli di domande. Consente ai chiamanti di rispondere usando l'input della tastiera vocale o DTMF.

**Domanda:** "Grazie per aver chiamato l'help desk IT. Se si ha un problema di accesso alla rete, premere 1 o Say Network. Se si ha un problema con il software, premere 2 o dire software. Se si ha un problema hardware, premere 3 o dire hardware.

  - L' **opzione 1 è selezionata:** Il chiamante viene indirizzato al team di supporto della rete.

  - **Opzione 2 selezionata:** Al chiamante viene posta una domanda di follow-up:
    
    **Domanda:** "Se si tratta di un problema di sistema operativo, premere 1 o dire sistema operativo. Se si tratta di un problema con un'applicazione interna, premere 2 o dire applicazione interna. In caso contrario, premere 3 o dire altro.
    
      - L' **opzione 1 è selezionata:** Il chiamante viene indirizzato al team di supporto dei sistemi operativi.
    
      - **Opzione 2 selezionata:** Il chiamante viene indirizzato al team di supporto delle applicazioni interne.
    
      - **Opzione 3 selezionata:** Il chiamante viene indirizzato al team di supporto software.

  - **Opzione 3 selezionata:** Al chiamante viene posta una domanda di follow-up:
    
    **Domanda:** "Se si tratta di un problema di stampante, premere 1. In caso contrario, premere 2. "
    
      - L' **opzione 1 è selezionata:** Il chiamante viene indirizzato al team di supporto della stampante.
    
      - **Opzione 2 selezionata:** Il chiamante viene indirizzato al team di supporto hardware.

La figura seguente mostra il flusso delle chiamate.

**Flusso delle chiamate interattive a due livelli**

![Progettazione dei flussi di chiamata]tramite il(images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "flusso delle chiamate") interattive tramite respo vocale

</div>

</div>

<div>

## <a name="best-practices"></a>Procedure consigliate

Nell'elenco seguente vengono illustrate alcune procedure consigliate per la progettazione del dispositivo IVR:

  - Consentire al chiamante di accedere rapidamente all'attività. Evitare di fornire troppe informazioni o lunghi messaggi di marketing nel sistema IVR.

  - Se si vuole includere un messaggio lungo, valutare la possibilità di accodarlo alla prima domanda anziché al messaggio di benvenuto. I chiamanti possono ignorare il messaggio se fa parte della prima domanda rispondendo alla domanda, ma non possono ignorare il messaggio di benvenuto.

  - Parla nella lingua del chiamante. Evitare la lingua stilata. Parla in modo naturale.

  - Scrivere richieste efficienti ed efficaci. Rimuovere eventuali opzioni non necessarie. Strutturare le informazioni in modo che la risposta prevista del chiamante si trovi alla fine della frase. Ad esempio, "per parlare con il team di vendita, premere 1".

  - Rendere le risposte vocali intuitive. Ad esempio, se specifichi sia il DTMF che le risposte vocali, USA qualcosa di simile a: "per parlare con il team di vendita, premi 1 o pronuncia vendite".

  - Testare il IVR su un gruppo di utenti prima di distribuirlo nell'organizzazione.

</div>

</div>

<span> </span>

</div>

</div>

</div>

