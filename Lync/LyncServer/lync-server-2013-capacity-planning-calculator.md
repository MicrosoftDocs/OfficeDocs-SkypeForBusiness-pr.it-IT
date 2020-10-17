---
title: Lync Server 2013 Capacity Planning Calculator
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2013 capacity planning calculator
ms:assetid: e86c1f05-1393-408a-9549-6001572ec50d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362852(v=OCS.15)
ms:contentKeyID: 56280894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 230b731bf7b63a1ce86b5652d9e3d3b2956c94a3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512823"
---
# <a name="using-the-capacity-planning-calculator-for-lync-server-2013"></a>Utilizzo del calcolatore di pianificazione della capacità per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-11-21_

Microsoft® Lync™ Server 2013 Capacity Planning Calculator è disponibile per il download all'indirizzo <https://www.microsoft.com/download/details.aspx?id=36828> . È stato creato per facilitare la determinazione dei requisiti del server in base al numero di utenti e alle modalità di comunicazione abilitate nell'organizzazione. Immettere il profilo dell'organizzazione e la calcolatrice fornisce consigli utili per la pianificazione della topologia.

I suggerimenti creati dalla calcolatrice sono solo a scopo di pianificazione. È necessaria una simulazione di carico effettiva per garantire che Lync Server 2013 sia adeguatamente provisioning. Per eseguire il test di stress con un carico simulato, utilizzare lo strumento di analisi [dello stress e delle prestazioni di Lync Server 2013](https://go.microsoft.com/fwlink/?linkid=282724).

Dopo aver determinato il profilo utente e le modalità che si desidera abilitare per gli utenti, è opportuno utilizzare la calcolatrice per pianificare il numero di server, la memoria e la larghezza di banda necessaria. Questa versione della calcolatrice non fornisce indicazioni per I requisiti di I/O su disco.

Questo calcolatore è complementare a [Microsoft Lync Server](https://go.microsoft.com/fwlink/?linkid=282725) e [Microsoft Lync Server](lync-server-2013-planning.md). Utilizzare la calcolatrice dopo aver esaminato la guida e aver creato una topologia consigliata tramite lo strumento di pianificazione.

Se si dispone di informazioni accurate e dettagliate sul profilo utente specifico, è possibile trarre vantaggio dalla calcolatrice. Ad esempio, la percentuale di utenti abilitati per la voce, le chiamate medie per utente all'ora, la durata delle chiamate e la percentuale di utenti simultanei nelle conferenze possono fare una differenza enorme nei requisiti del server. L'accuratezza dei suggerimenti creati dalla calcolatrice dipende dall'accuratezza delle informazioni fornite.

<div>

## <a name="using-the-capacity-calculator"></a>Utilizzo del calcolatore capacità

La calcolatrice è un foglio di calcolo di Microsoft Excel®. Le celle di colore arancione sono per l'input dell'utente. I valori predefiniti vengono immessi (80.000 utenti in un pool con dodici Front End Server), ma è possibile modificare questi valori in base alle esigenze dell'organizzazione.

Il modello di utilizzo contiene le sezioni seguenti. Per calcolare i requisiti di capacità, immettere i dati come descritto di:

**Messaggistica istantanea e presenza**

  - In numero di utenti digitare il numero di utenti a cui verrà effettuato l'accesso simultaneo. Questo numero è in genere 80% del numero totale di utenti di cui è stato effettuato il provisioning. Nella maggior parte dei casi, il 100% degli utenti simultanei verrà abilitato per la messaggistica istantanea e la presenza. Il valore predefinito è 80.000.

  - Numero medio di contatti nell'elenco contatti indica il numero di contatti utilizzati per convalidare i requisiti di sistema. Questo numero non è modificabile.

**VoIP aziendale**

  - In utenti abilitati per VoIP aziendale, digitare la percentuale di utenti abilitati per VoIP aziendale. Il valore predefinito è 60%.

  - In media il numero di chiamate per utente all'ora (picco), digitare il numero di chiamate all'ora in cui si prevede che l'utente medio partecipi in periodi di carico di picco. Il valore predefinito è 4.

  - In percentuale delle chiamate che utilizzano il bypass multimediale, digitare la percentuale di chiamate effettuate dagli utenti che ignoreranno il Mediation Server. Il valore predefinito è 65%.

  - In percentuale degli utenti vocali coinvolti nelle chiamate di messaggistica UNIFICAta PSTN, digitare la percentuale delle chiamate dell'organizzazione che sono chiamate telefoniche UC-PSTN. Il valore predefinito è 60%

  - In percentuale di utenti vocali coinvolti nelle chiamate UC-UC viene visualizzata la percentuale di utenti abilitati per VoIP aziendale che verranno abilitati solo per le chiamate UC-UC. Questo numero viene calcolato in base all'input per la percentuale di utenti vocali abilitati per le chiamate UC-PSTN.

**Conferenze**

  - In percentuale degli utenti nelle conferenze simultanee, digitare la percentuale di utenti che parteciperanno contemporaneamente a conferenze. Il valore predefinito è 5%.

  - In percentuale delle conferenze con solo gruppo di messaggistica istantanea (nessuna voce), digitare la percentuale di conferenze le cui conferenze coinvolgono solo la messaggistica istantanea; ovvero, che non includono un componente audio. Il valore predefinito è 10%

  - In percentuale di utenti che utilizzano le conferenze telefoniche con accesso esterno, digitare la percentuale di partecipanti simultanei alle conferenze che utilizzeranno le conferenze telefoniche con accesso esterno. Il valore predefinito è 15%.

  - In percentuale delle conferenze che utilizzano la voce, digitare la percentuale di conferenze che includerà un componente audio.
    
      - Se il 20% delle conferenze vocali includerà anche un video normale, selezionare la casella di controllo Includi video (nessuna visualizzazione multipla).
    
      - Se il 20% delle conferenze includerà anche video con più visualizzazioni, selezionare la casella di controllo Includi Multi View.
    
      - Se il 50% delle conferenze vocali includerà anche la condivisione di applicazioni, selezionare la casella di controllo Includi la condivisione di applicazioni.
    
      - Se il 20% delle conferenze vocali include i caricamenti di dati, ad esempio le presentazioni di Microsoft PowerPoint®, selezionare la casella di controllo Includi Web Conferencing.

**Mobilità**

  - In percentuale degli utenti abilitati per la mobilità, digitare la percentuale di utenti che saranno abilitati per la connessione a Lync Server tramite dispositivi mobili. Il valore predefinito è 40%.

Dopo aver immesso tutte le informazioni necessarie, la calcolatrice della capacità stima i propri requisiti. Le celle gialle mostrano i valori calcolati per i requisiti di CPU, memoria e larghezza di banda in base ai test eseguiti in Lync Server 2013 Performance Labs. I numeri sono forniti come linee guida, non ogni singola variante viene testata e convalidata. Vengono calcolati i valori seguenti:

  - CPU front-end: percentuale di utilizzo della CPU se l'intero carico veniva gestito da un front end server delle stesse specifiche del server utilizzato in Microsoft testing.

  - Rete in Mbps: requisiti di larghezza di banda in megabit al secondo (Mbps) per il carico di lavoro corrispondente.

  - Memoria in GB: memoria necessaria in gigabyte (GB) per il carico di lavoro corrispondente.

Le celle verdi mostrano suggerimenti per il modello di utilizzo immesso.

  - Total front end server: il numero di server fisici necessari si basa su server dedicati che eseguono Lync Server 2013 con processore duale, hex-core, con 2.260 megacicli.

  - Si noti che è consigliabile abilitare l'Hyper-Threading ed è stato dimostrato che è possibile migliorare le prestazioni per i server che supportano audio/video.

  - Server perimetrali: il numero di server perimetrali necessari, in base al 30% di tutti gli utenti simultanei che comunicano con i server perimetrali. Questa percentuale non può essere modificata nella calcolatrice.

  - Archiviazione/registrazione dettagli chiamata/archivio qualità dei servizi di esperienza: il numero di archivi necessari per le funzionalità di archiviazione o di monitoraggio, se sono abilitati nell'organizzazione.

  - Server database back-end necessario (pool necessari): il numero di server di database back-end necessari per il supporto del carico di lavoro selezionato.

Inoltre, nella riga accanto a Total front end server, vengono fornite ulteriori informazioni sul carico sui server e sulla rete per tutti i carichi di lavoro pianificati combinati.

  - Carico medio della CPU: l'utilizzo medio della CPU per Front End Server.

  - Rete in Mbps: l'allocazione di larghezza di banda necessaria per supportare il modello di utilizzo immesso.

  - Memoria in GB: memoria, in gigabyte, obbligatoria per ogni Front End Server.

</div>

<div>

## <a name="adjusting-for-your-processors"></a>Adattamento delle cifre ai processori disponibili

Tutte le figure di utilizzo della CPU nel foglio di calcolo presuppongono che ogni server disponga di un processore duale, un hex-core con 2,26 GHz, almeno 32 GB di memoria e 8 o più unità disco rigido a 10.000-RPM con almeno 72 GB di spazio libero su disco.

Se nei server sono disponibili processori diversi, è possibile modificare le figure in modo che corrispondano all'hardware.

</div>

</div>

<span> </span>

</div>

</div>

</div>

