---
title: Calcolatore di pianificazione della capacità di Lync Server 2013
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
ms.openlocfilehash: 26abf069d7c1686fe8abb804d6de4508ba6333fe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-capacity-planning-calculator-for-lync-server-2013"></a>Uso del calcolatore pianificazione capacità per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-11-21_

Il calcolatore Microsoft® Lync™ Server 2013 Capacity Planning Calculator è disponibile per <http://www.microsoft.com/en-us/download/details.aspx?id=36828>il download. È progettato per aiutarti a determinare i requisiti del server in base al numero di utenti e alle modalità di comunicazione abilitate presso l'organizzazione. Si immette il profilo dell'organizzazione e la calcolatrice fornisce indicazioni utili per pianificare la topologia.

Le raccomandazioni create dalla calcolatrice sono solo per scopi di pianificazione. È necessaria una simulazione di carico effettiva per verificare che Lync Server 2013 sia adeguatamente provisioning. Per eseguire test di stress in un carico simulato, usare lo strumento di analisi [dello stress e delle prestazioni di Lync Server 2013](http://go.microsoft.com/fwlink/?linkid=282724).

Dopo aver determinato il profilo utente e le modalità da abilitare per gli utenti, è il momento di usare la calcolatrice per pianificare il numero di server, la memoria e la larghezza di banda necessarie. Questa versione della calcolatrice non fornisce indicazioni per I requisiti di I/O su disco.

Questa calcolatrice completa il server [Microsoft Lync](http://go.microsoft.com/fwlink/?linkid=282725) e [Microsoft Lync](lync-server-2013-planning.md)server. Usare la calcolatrice dopo aver esaminato la guida e aver creato una topologia consigliata usando lo strumento pianificazione.

Puoi trarre vantaggio dalla calcolatrice se hai informazioni accurate e dettagliate sul profilo utente specifico. Ad esempio, la percentuale di utenti abilitati per la voce, le chiamate medie per utente per ora, la durata delle chiamate e la percentuale di utenti simultanei nelle conferenze possono fare una grande differenza nei requisiti del server. La precisione delle indicazioni create dalla calcolatrice dipende dall'esattezza delle informazioni fornite.

<div>

## <a name="using-the-capacity-calculator"></a>Uso del calcolatore capacità

La calcolatrice è un foglio di calcolo® di Microsoft Excel. Le celle di colore arancione sono per l'input da te. I valori predefiniti vengono immessi (80.000 utenti in un pool con dodici server front-end), ma è possibile modificare questi valori in base alle esigenze dell'organizzazione.

Il modello di utilizzo contiene le sezioni seguenti. Per calcolare i requisiti di capacità, immettere i dati come descritto:

**Messaggistica istantanea e presenza**

  - In numero di utenti digitare il numero di utenti a cui verrà eseguito l'accesso simultaneo. Questo numero è in genere 80% del numero totale di utenti con provisioning. Nella maggior parte dei casi, il 100% degli utenti simultanei verrà abilitato per la messaggistica istantanea e la presenza. Il valore predefinito è 80.000.

  - Il numero medio di contatti nell'elenco contatti indica il numero di contatti che stiamo usando per convalidare i requisiti di sistema. Questo numero non è modificabile.

**VoIP aziendale**

  - In utenti abilitati per VoIP aziendale digitare la percentuale di utenti abilitati per VoIP aziendale. Il valore predefinito è 60%.

  - In media numero di chiamate per utente per ora (picco) digitare il numero di chiamate per ora in cui si prevede che l'utente medio partecipi durante i periodi di caricamento massimo. Il valore predefinito è 4.

  - In percentuale delle chiamate che usano il bypass multimediale digitare la percentuale di chiamate effettuate dagli utenti che ignoreranno il server Mediation. Il valore predefinito è 65%.

  - In percentuale degli utenti vocali coinvolti nelle chiamate UC-PSTN digitare la percentuale delle chiamate dell'organizzazione che sono chiamate telefoniche UC-PSTN. Il valore predefinito è 60%

  - In percentuale di utenti vocali coinvolti nelle chiamate UC-UC viene visualizzata la percentuale di utenti abilitati per VoIP aziendale che verrà abilitata solo per le chiamate UC-UC. Questo numero viene calcolato in base all'input per la percentuale di utenti vocali abilitati per chiamate UC-PSTN.

**Conferenze**

  - In percentuale degli utenti nelle conferenze concorrenti digitare la percentuale di utenti che parteciperanno contemporaneamente alle conferenze. Il valore predefinito è 5%.

  - In percentuale delle conferenze con messaggistica istantanea di gruppo (senza voce) digitare la percentuale di conferenze le cui conferenze coinvolgono solo la messaggistica istantanea. ovvero non includere un componente audio. Il valore predefinito è 10%

  - In percentuale di utenti che usano servizi di conferenza telefonica con accesso esterno, digitare la percentuale di partecipanti simultanei alle conferenze che utilizzeranno i servizi di conferenza telefonica con accesso esterno. Il valore predefinito è 15%.

  - In percentuale delle conferenze che usano la voce digitare la percentuale di conferenze che includerà un componente audio.
    
      - Se il 20% delle conferenze vocali includerà anche un video normale, selezionare la casella di controllo Includi video (senza visualizzazione multipla).
    
      - Se il 20% delle conferenze includerà anche il video con più visualizzazioni, selezionare la casella di controllo Includi multi-visualizzazione.
    
      - Se 50% delle conferenze vocali includerà anche la condivisione delle applicazioni, selezionare la casella di controllo Includi condivisione applicazioni.
    
      - Se il 20% delle conferenze vocali include il caricamento dei dati, ad esempio le presentazioni di Microsoft PowerPoint®, selezionare la casella di controllo Includi Web Conferencing.

**Mobilità**

  - In percentuale degli utenti abilitati per la mobilità digitare la percentuale di utenti che verranno abilitati per la connessione a Lync Server tramite dispositivi mobili. Il valore predefinito è 40%.

Dopo aver immesso tutte le informazioni necessarie, il calcolatore della capacità stima le proprie esigenze. Le celle gialle mostrano i valori calcolati per i requisiti di CPU, memoria e larghezza di banda in base ai test eseguiti nei laboratori di prestazioni di Lync Server 2013. I numeri sono forniti come linee guida, non ogni singola variante viene testata e convalidata. Vengono calcolati i valori seguenti:

  - CPU front-end: percentuale di utilizzo della CPU se l'intero carico veniva gestito da un server front-end delle stesse specifiche del server usato in Microsoft testing.

  - Rete in Mbps: requisiti di larghezza di banda in megabit al secondo (Mbps) per il carico di lavoro corrispondente.

  - Memoria in GB: memoria necessaria in gigabyte (GB) per il carico di lavoro corrispondente.

Le celle verdi mostrano le raccomandazioni per il modello di utilizzo immesso.

  - Total Front End Servers: il numero di server fisici necessari si basa su server dedicati che esegue Lync Server 2013 con processore duale, hex-core, con 2.260 megacicli.

  - Tieni presente che è consigliabile abilitare l'hyperthreading ed è stato dimostrato che migliora le prestazioni per i server che supportano l'audio/video.

  - Edge Server: il numero di server perimetrali necessari, in base al 30% di tutti gli utenti simultanei che comunicano tramite Edge Server. Questa percentuale non può essere modificata nella calcolatrice.

  - Archiviazione/registrazione dei dettagli delle chiamate/qualità di Experience Services Store: il numero di archivi necessari per l'archiviazione o il monitoraggio delle caratteristiche, se abilitati nell'organizzazione.

  - Server di database back-end obbligatorio (obbligatorio per i pool): numero di server di database back-end necessari per supportare il carico di lavoro selezionato.

Inoltre, nella riga accanto a Total Front End Servers vengono fornite ulteriori informazioni sul carico dei server e della rete per tutti i carichi di lavoro pianificati combinati.

  - Carico medio della CPU: l'utilizzo medio della CPU per server front-end.

  - Rete in Mbps: l'allocazione di larghezza di banda necessaria per supportare il modello di utilizzo immesso.

  - Memoria in GB: memoria, in gigabyte, necessaria per ogni server front-end.

</div>

<div>

## <a name="adjusting-for-your-processors"></a>Regolazione per i processori

Tutte le figure di utilizzo della CPU nel foglio di calcolo presuppongono che ogni server disponga di un processore duale, hex-core con 2,26 GHz, almeno 32 GB di memoria e 8 o più unità disco rigido 10.000-RPM con almeno 72 GB di spazio libero su disco.

Se i server hanno processori diversi, è possibile modificare le cifre in base all'hardware.

</div>

</div>

<span> </span>

</div>

</div>

</div>

