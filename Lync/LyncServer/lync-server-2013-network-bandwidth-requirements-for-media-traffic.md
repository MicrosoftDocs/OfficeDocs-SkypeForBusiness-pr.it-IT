---
title: Requisiti di larghezza di banda di rete di Lync Server 2013 per il traffico multimediale
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network bandwidth requirements for media traffic
ms:assetid: 83e83b16-0f0e-4d87-901a-0faa4618cdc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688118(v=OCS.15)
ms:contentKeyID: 49733716
ms.date: 09/25/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 684f13a10c066e8902bed0024d7546017450ee9e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765927"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-bandwidth-requirements-for-media-traffic-in-lync-server-2013"></a>Requisiti di larghezza di banda di rete per il traffico multimediale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2015-09-24_

Una parte importante della pianificazione della rete garantisce che la rete sia in grado di gestire il traffico multimediale generato da Lync Server. Questa sezione consente di pianificare il traffico multimediale.

<div>

## <a name="media-traffic-network-usage"></a>Utilizzo della rete per il traffico multimediale

L'utilizzo della larghezza di banda del traffico multimediale può essere difficile da calcolare a causa del numero di variabili diverse, ad esempio l'uso dei codec, la risoluzione e i livelli di attività. L'utilizzo della larghezza di banda è una funzione del codec usato e dell'attività del flusso, che variano tra loro in scenari diversi. Nella tabella seguente sono elencati i codec audio usati comunemente negli scenari di Lync Server 2013.

### <a name="audio-codec-bandwidth"></a>Larghezza di banda del codec audio

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>Codec audio</th>
<th>Scenari</th>
<th>Bitrate del payload audio (KBPS)</th>
<th>Payload di larghezza di banda audio e solo intestazione IP (Kbps)</th>
<th>Payload audio con larghezza di banda, intestazione IP, UDP, RTP e SRTP (Kbps)</th>
<th>Payload audio a larghezza di banda, intestazione IP, UDP, RTP, SRTP e correzione degli errori in avanti (Kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTAudio a banda larga</p></td>
<td><p>Peer-to-peer</p></td>
<td><p>29,0</p></td>
<td><p>45,0</p></td>
<td><p>57,0</p></td>
<td><p>86,0</p></td>
</tr>
<tr class="even">
<td><p>RTAudio stretta</p></td>
<td><p>Peer-to-peer, PSTN</p></td>
<td><p>11,8</p></td>
<td><p>27,8</p></td>
<td><p>39,8</p></td>
<td><p>51,6</p></td>
</tr>
<tr class="odd">
<td><p>G. 722</p></td>
<td><p>Servizi di conferenza</p></td>
<td><p>64,0</p></td>
<td><p>80,0</p></td>
<td><p>95,6</p></td>
<td><p>159,6</p></td>
</tr>
<tr class="even">
<td><p>Stereo G. 722</p></td>
<td><p>Servizi di conferenza peer-to-peer</p></td>
<td><p>128,0</p></td>
<td><p>144,0</p></td>
<td><p>159,6</p></td>
<td><p>223,6</p></td>
</tr>
<tr class="odd">
<td><p>G. 711</p></td>
<td><p>Servizi di conferenza PSTN</p></td>
<td><p>64,0</p></td>
<td><p>80,0</p></td>
<td><p>92,0</p></td>
<td><p>156,0</p></td>
</tr>
<tr class="even">
<td><p>Sirena</p></td>
<td><p>Servizi di conferenza</p></td>
<td><p>16,0</p></td>
<td><p>32,0</p></td>
<td><p>47,6</p></td>
<td><p>63,6</p></td>
</tr>
</tbody>
</table>


I numeri di larghezza di banda nella tabella precedente si basano su pacchettizzazione 20ms (pacchetti di 50 al secondo) e per sirena e G. 722 includono l'overhead di protocollo di trasporto in tempo reale (SRTP) aggiuntivo protetto da scenari di conferenza e si presuppone che il flusso sia 100% attivo. La correzione degli errori in avanti (FEC) viene usata in modo dinamico quando c'è perdita di pacchetti sul collegamento per mantenere la qualità del flusso audio.

La versione stereo del codec G. 722 viene usata dai sistemi basati sul sistema room di Lync, che consente l'acquisizione di microfoni stereo per consentire agli ascoltatori di distinguere meglio più chiacchieroni nella sala riunioni.

Per il video, il codec predefinito è lo standard di codifica video avanzato H. 264/MPEG-4 parte 10, insieme alle estensioni di codifica video scalabili per la scalabilità temporale. Per mantenere l'interoperabilità con i client Lync 2010 o Office Communicator 2007 R2, il codec RTVideo viene ancora usato per le chiamate peer-to-peer tra Lync 2013 e i client legacy. Nelle sessioni di conferenza con entrambi i client Lync 2013 e Legacy l'endpoint Lync 2013 può codificare il video con codec video e inviare il Bitstream H. 264 a Lync 2013 e RTVideo Bitstream ai client Lync 2010 o Office Communicator 2007 R2.

La larghezza di banda necessaria dipende dalla risoluzione, dalla qualità e dalla frequenza dei fotogrammi. Per ogni risoluzione, sono disponibili due velocità in bit interessanti:

  - **Bitrate massimo del payload**   questo è il bitrate che verrà usato da un endpoint 2013 di Lync per la risoluzione alla frequenza massima di fotogrammi supportata per la risoluzione. Questo valore è interessante perché consente il video di altissima qualità e frequenza dei fotogrammi.

  - **Bitrate minimo del payload**   questo è il bitrate sotto il quale un endpoint di Lync 2013 passa alla risoluzione inferiore successiva. Per garantire una determinata risoluzione, il bitrate del payload video disponibile non deve scendere al di sotto di questo bitrate minimo per la risoluzione. Questo valore è interessante in modo che sia possibile comprendere il valore più basso possibile nei casi in cui il bitrate massimo non è disponibile o pratico. Per alcuni utenti, un video a basso bitrate potrebbe essere considerato un'esperienza video inaccettabile, quindi prestare attenzione quando si considerano questi bitrate minimi per il payload video. Tieni presente che per le scene video con poco o nessun movimento dell'utente, il bitrate effettivo può anche essere inferiore alla frequenza minima.

Lync 2013 supporta molte più risoluzioni. In questo modo puoi migliorare la larghezza di banda della rete e la ricezione di funzionalità client. Inoltre, le proporzioni predefinite per Lync 2013 sono state modificate in 16:9. Le proporzioni di 4:3 sono ancora supportate per le webcam che non consentono l'acquisizione in proporzioni 16:9.

### <a name="video-resolution-bandwidth"></a>Larghezza di banda di risoluzione video

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Codec video</th>
<th>Risoluzione e proporzioni</th>
<th>Bitrate massimo del payload video (Kbps)</th>
<th>Bitrate minimo del payload video (Kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>H. 264</p></td>
<td><p>320x180 (16:9)</p>
<p>212x160 (4:3)</p></td>
<td><p>250</p></td>
<td><p>15</p></td>
</tr>
<tr class="even">
<td><p>H. 264/RTVideo</p></td>
<td><p>424x240 (16:9))</p>
<p>320x240 (4:3</p></td>
<td><p>350</p></td>
<td><p>100</p></td>
</tr>
<tr class="odd">
<td><p>H. 264</p></td>
<td><p>480x270 (16:9)</p>
<p>424x320 (4:3)</p></td>
<td><p>450</p></td>
<td><p>200</p></td>
</tr>
<tr class="even">
<td><p>H. 264/RTVideo</p></td>
<td><p>640x360 (16:9)</p>
<p>640x480 (4:3)</p></td>
<td><p>800</p></td>
<td><p>300</p></td>
</tr>
<tr class="odd">
<td><p>H. 264</p></td>
<td><p>848x480 (16:9)</p></td>
<td><p>1500</p></td>
<td><p>400</p></td>
</tr>
<tr class="even">
<td><p>H. 264</p></td>
<td><p>960x540 (16:9)</p></td>
<td><p>2000</p></td>
<td><p>500</p></td>
</tr>
<tr class="odd">
<td><p>H. 264/RTVideo</p></td>
<td><p>1280x720 (16:9)</p></td>
<td><p>2500</p></td>
<td><p>700</p></td>
</tr>
<tr class="even">
<td><p>H. 264</p></td>
<td><p>1920x1080 (16:9)</p></td>
<td><p>4000</p></td>
<td><p>1500</p></td>
</tr>
<tr class="odd">
<td><p>H. 264/RTVideo</p></td>
<td><p>960x144 (20:3)</p></td>
<td><p>500</p></td>
<td><p>15</p></td>
</tr>
<tr class="even">
<td><p>H. 264</p></td>
<td><p>1280x192 (20:3)</p></td>
<td><p>1000</p></td>
<td><p>250</p></td>
</tr>
<tr class="odd">
<td><p>H. 264</p></td>
<td><p>1920x288 (20:3)</p></td>
<td><p>2000</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


Video FEC è incluso nel video bitrate payload quando viene usato in modo che non ci siano valori separati con il video FEC e senza video FEC.

Gli endpoint non eseguono il flusso continuo di pacchetti audio o video. A seconda dello scenario, sono presenti diversi livelli di attività di flusso che indicano la frequenza di invio dei pacchetti per un flusso. L'attività di un flusso dipende dall'elemento multimediale e dallo scenario e non dipende dal codec usato. In uno scenario peer-to-peer:

  - Gli endpoint inviano flussi audio solo quando gli utenti parlano.

  - Entrambi i partecipanti ricevono flussi audio.

  - Se viene usato il video, entrambi gli endpoint inviano e ricevono flussi video durante l'intera chiamata.

  - Per le scene video con movimenti poco o nessuno, il bitrate effettivo può essere temporaneamente molto basso perché il codec video salterà la codifica delle aree del video senza modifiche.

In uno scenario di conferenza:

  - Gli endpoint inviano flussi audio solo quando gli utenti parlano.

  - Tutti i partecipanti ricevono flussi audio.

  - Se viene usato il video, tutti i partecipanti possono ricevere fino a cinque flussi video di ricezione e uno stream video panoramico (ad esempio, aspect ratio 20:3). Per impostazione predefinita, i cinque flussi video di ricezione si basano sulla cronologia degli oratori attivi, ma gli utenti possono anche selezionare manualmente i partecipanti da cui vogliono ricevere un flusso video.

  - Ogni partecipante che attiva il flusso video di invio dell'utente invierà uno o più flussi video. Lync 2013 aggiunge la possibilità di inviare fino a cinque flussi video per ottimizzare la qualità del video per tutti i client di ricezione. Il numero effettivo di flussi video inviati viene determinato dal mittente in base alle funzionalità della CPU, alla larghezza di banda di uplink disponibile e al numero di client di ricezione che richiedono un determinato flusso video. Il caso più comune è che si sta inviando un flusso video H. 264 e uno RTVideo nel caso in cui un client legacy partecipi alla conferenza. Un altro scenario comune è che diversi flussi video H. 264, ad esempio con risoluzioni video diverse, vengono inviati per ospitare diverse richieste di ricevitore.

Oltre alla larghezza di banda necessaria per il traffico RTP (Real-Time Transport Protocol) per i supporti audio e video, è necessaria la larghezza di banda per il protocollo di controllo del trasporto in tempo reale (RTCP). RTCP viene usato per segnalare le statistiche e il controllo fuori banda del flusso RTP. Per la pianificazione, usare i numeri di larghezza di banda nella tabella seguente per il traffico RTCP. Questi valori rappresentano la larghezza di banda massima usata per RTCP e differiscono tra i flussi audio e video a causa delle differenze tra i dati del controllo

### <a name="rtcp-bandwidth"></a>Larghezza di banda RTCP

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Contenuti multimediali</th>
<th>Larghezza di banda massima RTCP (Kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>5</p></td>
</tr>
<tr class="even">
<td><p>Video (solo H. 264 o RTVideo inviati/ricevuti)</p></td>
<td><p>10</p></td>
</tr>
<tr class="odd">
<td><p>Video (H. 264 e RTVideo inviati/ricevuti)</p></td>
<td><p>15</p></td>
</tr>
</tbody>
</table>


Per scopi di pianificazione della capacità, le due larghezze di banda seguenti sono interessanti:

  - **Larghezza di banda massima senza FEC**   la larghezza di banda massima che verrà utilizzata da un flusso, inclusa l'attività tipica del flusso e il codec tipico usato nello scenario senza FEC.Questa è la larghezza di banda quando il flusso si trova all'attività di 100% e non è disponibile alcuna perdita di pacchetti che attiva l'uso di FEC.Questo è interessante per calcolare la quantità di larghezza di banda che deve essere allocata per consentire l'uso del codec in uno scenario specifico. 

  - **Larghezza di banda massima con FEC**   la larghezza di banda massima usata da un flusso, inclusa l'attività tipica dello Stream e il codec tipico usato nello scenario con FEC. Questa è la larghezza di banda quando il flusso è a 100% di attività e la perdita di pacchetti attiva l'uso di FEC per migliorare la qualità. Questo è interessante per calcolare la quantità di larghezza di banda che deve essere allocata per consentire l'utilizzo del codec in uno scenario specifico e consentire l'uso di FEC per preservare la qualità in condizioni di perdita di pacchetti. 

Le tabelle seguenti elencano anche un valore di larghezza di banda aggiuntivo, la **larghezza di banda tipica**. Si tratta della larghezza di banda media utilizzata da un flusso, inclusa l'attività tipica dello Stream e il codec tipico usato nello scenario. Questa larghezza di banda può essere usata per avvicinare la quantità di larghezza di banda in un dato momento al traffico multimediale, ma non deve essere usata per la pianificazione della capacità, perché le singole chiamate supereranno questo valore quando il livello di attività è superiore alla media. La larghezza di banda tipica del flusso video nelle tabelle seguenti si basa su una combinazione di risoluzioni video diverse, come osservato nei dati dei clienti misurati. Ad esempio, nelle sessioni peer-to-peer la maggior parte degli utenti utilizzerebbe la finestra di rendering video predefinita, mentre una certa percentuale di utenti aumenterebbe o ingrandirebbe l'applicazione Lync per consentire risoluzioni video più elevate.

Le tabelle seguenti includono questi tre valori di larghezza di banda per i vari scenari.

### <a name="audiovideo-capacity-planning-for-peer-to-peer-sessions"></a>Pianificazione della capacità audio/video per le sessioni peer-to-peer

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Contenuti multimediali</th>
<th>Codec</th>
<th>Larghezza di banda tipica del flusso (Kbps)</th>
<th>Larghezza di banda massima del flusso senza FEC</th>
<th>Larghezza di banda massima del flusso con FEC</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>RTAudio a banda larga</p></td>
<td><p>39,8</p></td>
<td><p>62</p></td>
<td><p>91</p></td>
</tr>
<tr class="even">
<td><p>Audio</p></td>
<td><p>RTAudio stretta</p></td>
<td><p>29,3</p></td>
<td><p>44,8</p></td>
<td><p>56,6</p></td>
</tr>
<tr class="odd">
<td><p>Video principale quando si chiamano endpoint di Lync 2013</p></td>
<td><p>H. 264</p></td>
<td><p>460</p></td>
<td><p>4010 (per la risoluzione massima di 1920x1080)</p></td>
<td><p>Non applicabile</p></td>
</tr>
<tr class="even">
<td><p>Video principale quando si chiamano gli endpoint di Lync 2010 o Office Communicator 2007 R2</p></td>
<td><p>RTVideo</p></td>
<td><p>460</p></td>
<td><p>2510 (per la risoluzione massima di 1280x720)</p></td>
<td><p>Non applicabile</p></td>
</tr>
<tr class="odd">
<td><p>Video panoramico quando si chiamano endpoint di Lync 2013</p></td>
<td><p>H. 264</p></td>
<td><p>190</p></td>
<td><p>2010 (per la risoluzione massima di 1920x288)</p></td>
<td><p>Non applicabile</p></td>
</tr>
<tr class="even">
<td><p>Video panoramico quando si chiamano gli endpoint di Lync 2010 o Office Communicator 2007 R2</p></td>
<td><p>RTVideo</p></td>
<td><p>190</p></td>
<td><p>510 (per la risoluzione massima di 960x144)</p></td>
<td><p>Non applicabile</p></td>
</tr>
</tbody>
</table>


### <a name="audiovideo-capacity-planning-for-conferences"></a>Pianificazione della capacità audio/video per le conferenze

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Contenuti multimediali</th>
<th>Codec tipico</th>
<th>Larghezza di banda tipica del flusso (Kbps)</th>
<th>Larghezza di banda massima del flusso senza FEC</th>
<th>Larghezza di banda massima del flusso con FEC</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>G. 722</p></td>
<td><p>46,1</p></td>
<td><p>100,6</p></td>
<td><p>164,6</p></td>
</tr>
<tr class="even">
<td><p>Audio</p></td>
<td><p>Sirena</p></td>
<td><p>25,5</p></td>
<td><p>52,6</p></td>
<td><p>68,6</p></td>
</tr>
<tr class="odd">
<td><p>Ricezione video principale</p></td>
<td><p>H. 264 e/o RTVideo</p></td>
<td><p>260</p></td>
<td><p>8015</p></td>
<td><p>Non applicabile</p></td>
</tr>
<tr class="even">
<td><p>Invio video principale</p></td>
<td><p>H. 264 e/o RTVideo</p></td>
<td><p>270</p></td>
<td><p>8015</p></td>
<td><p>Non applicabile</p></td>
</tr>
<tr class="odd">
<td><p>Ricezione video panoramico</p></td>
<td><p>H. 264 e/o RTVideo</p></td>
<td><p>190</p></td>
<td><p>2010 (per la risoluzione massima di 1920x288)</p></td>
<td><p>Non applicabile</p></td>
</tr>
<tr class="even">
<td><p>Invio video panoramico</p></td>
<td><p>H. 264 e/o RTVideo</p></td>
<td><p>190</p></td>
<td><p>2515 (per l'invio di Bitstream usando più risoluzioni/codec</p></td>
<td><p>Non applicabile</p></td>
</tr>
</tbody>
</table>


Per il video principale, la larghezza di banda di flusso standard e massima è la larghezza di banda aggregata su tutti i flussi video ricevuti e su tutti i flussi video inviati rispettivamente. Anche con più flussi video, la larghezza di banda video tipica è più piccola rispetto allo scenario peer-to-peer, poiché molte videoconferenze usano la condivisione di contenuto che porta a finestre video molto più piccole e quindi a risoluzioni video più piccole. La larghezza di banda complessiva del payload video aggregato supportata è di 8000 kbps sia per i flussi di invio che di ricezione che verrebbero usati ad esempio se sono presenti due flussi video di 1920x1080p in arrivo.

La tipica larghezza di banda del flusso per il video panoramico si basa sui dispositivi attualmente disponibili che vengono trasmessi solo al video panoramico di 960x144. Una volta che i dispositivi con il video panoramico di 1920x288 diventano disponibili, la larghezza di banda tipica del flusso dovrebbe aumentare.

### <a name="audio-capacity-planning-for-pstn"></a>Pianificazione della capacità audio per PSTN

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Contenuti multimediali</th>
<th>Codec tipico</th>
<th>Larghezza di banda tipica del flusso (Kbps)</th>
<th>Larghezza di banda massima del flusso senza FEC</th>
<th>Larghezza di banda massima del flusso con FEC</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>G. 711 (inclusi i partecipanti PSTN nelle conferenze)</p></td>
<td><p>64,8</p></td>
<td><p>97</p></td>
<td><p>161</p></td>
</tr>
<tr class="even">
<td><p>Audio</p></td>
<td><p>RTAudio stretta</p></td>
<td><p>30,9</p></td>
<td><p>44,8</p></td>
<td><p>56,6</p></td>
</tr>
</tbody>
</table>


I numeri di larghezza di banda di rete in queste tabelle rappresentano solo il traffico unidirezionale e includono 5 kbps per il sovraccarico del traffico di RTCP per ogni flusso. Per il video viene usata la velocità in bit massima del video per calcolare il flusso massimo.

</div>

</div>

<span> </span>

</div>

</div>

</div>

