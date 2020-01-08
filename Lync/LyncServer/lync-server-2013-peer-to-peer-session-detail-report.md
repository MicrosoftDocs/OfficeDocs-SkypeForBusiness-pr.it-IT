---
title: 'Lync Server 2013: report Dettagli sessione peer-to-peer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Peer-to-Peer Session Detail Report
ms:assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558659(v=OCS.15)
ms:contentKeyID: 48184416
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec73febb248a8b61979c0aad2df6977c9feccb91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984297"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-session-detail-report-in-lync-server-2013"></a>Report Dettagli sessione peer-to-peer in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-06-06_

Il report Dettagli sessione peer-to-peer restituisce informazioni dettagliate su una sessione peer-to-peer. Ad esempio, se selezioni una sessione di messaggistica istantanea, il report indica il numero di messaggi inviati da ognuno dei due utenti della sessione.

<div>

## <a name="accessing-the-peer-to-peer-session-detail-report"></a>Accesso al report Dettagli sessione peer-to-peer

È possibile accedere al report Dettagli sessione peer-to-peer da uno dei report seguenti (a cui è possibile accedere tutti dalla Home page dei report di monitoraggio):

  - Rapporto inventario telefoni IP

  - Rapporto attività utente

  - Rapporto controllo di ammissione di chiamata

  - Rapporto Elenco errori

Dal report Dettagli sessione peer-to-peer è possibile accedere al report di [diagnostica in Lync Server 2013](lync-server-2013-diagnostic-report.md) facendo clic sulla metrica rapporto di diagnostica (Dettagli). Per accedere al report errori principali, è anche possibile fare clic su una delle due metriche seguenti:

  - Risposta

  - ID diagnostica

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a>Sfruttare al meglio il report Dettagli sessione peer-to-peer

Il report Dettagli sessione peer-to-peer include un numero elevato di metriche, molte delle quali potrebbero non essere familiari con gli amministratori di sistema. Spesso, tuttavia, è possibile visualizzare una descrizione comando che offre una breve descrizione di tale metrica semplicemente tenendo il mouse sopra l'etichetta metrica.

Tieni presente che le metriche effettive visualizzate in un determinato report dipendono dal tipo di sessione peer-to-peer selezionata. Una sessione audio/video segnalerà un set di metriche diverso rispetto a una sessione di messaggistica istantanea.

È anche possibile tenere il mouse sopra il codice di risposta e le metriche degli ID diagnostici per ottenere una descrizione dei valori seguenti:

</div>

<div>

## <a name="filters"></a>Filtri

Nessuno. Non è possibile filtrare il report del dettaglio della sessione peer-to-peer.

</div>

<div>

## <a name="session-information-metrics"></a>Metriche delle informazioni sulla sessione

Nella tabella seguente sono elencate le informazioni fornite nel report Dettagli sessione peer-to-peer per ogni sessione.

### <a name="session-information-metrics"></a>Metriche delle informazioni sulla sessione

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>FQDN del pool</strong></p></td>
<td><p>Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale coinvolto nella sessione.</p></td>
</tr>
<tr class="even">
<td><p><strong>Invitare il tempo</strong></p></td>
<td><p>Data e ora in cui l'invito alla sessione è stato inviato in origine.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tempo di risposta</strong></p></td>
<td><p>Data e ora in cui è stata ricevuta l'accettazione dell'invito.</p></td>
</tr>
<tr class="even">
<td><p><strong>Dall'utente</strong></p></td>
<td><p>Indirizzo SIP dell'utente che ha avviato la sessione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Dall'agente utente</strong></p></td>
<td><p>Software usato dall'endpoint dell'utente che ha avviato la sessione.</p></td>
</tr>
<tr class="even">
<td><p><strong>È da utente interno</strong></p></td>
<td><p>Indica se l'utente che ha avviato la sessione è stato connesso alla rete interna.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Viene dall'utente integrato con il telefono da tavolo</strong></p></td>
<td><p>Indica se l'endpoint usato dall'utente che ha avviato la sessione è integrato con il telefono desktop.</p></td>
</tr>
<tr class="even">
<td><p><strong>Priorità della sessione</strong></p></td>
<td><p>Priorità assegnata alla sessione. Le priorità valide sono: sconosciuto; Non urgente; Normale Urgente e di emergenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Codice di risposta</strong></p></td>
<td><p>Codice di risposta SIP inviato quando la sessione non è riuscita.</p></td>
</tr>
<tr class="even">
<td><p><strong>Front-end</strong></p></td>
<td><p>Nome del server front-end usato nella conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tempo di acquisizione</strong></p></td>
<td><p>Data e ora in cui sono state registrate le informazioni sulla sessione.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ora di fine</strong></p></td>
<td><p>Data e ora di fine della sessione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>All'utente</strong></p></td>
<td><p>Indirizzo SIP dell'utente invitato alla sessione.</p></td>
</tr>
<tr class="even">
<td><p><strong>All'agente utente</strong></p></td>
<td><p>Software usato dall'endpoint dell'utente invitato alla sessione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>È l'utente interno</strong></p></td>
<td><p>Indica se l'utente invitato alla sessione è stato connesso alla rete interna.</p></td>
</tr>
<tr class="even">
<td><p><strong>È l'utente integrato con il telefono da tavolo</strong></p></td>
<td><p>Indica se l'endpoint usato dall'utente invitato alla sessione è integrato con il telefono desktop.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Viene riprovata la sessione</strong></p></td>
<td><p>Indica se la sessione è un tentativo di riprovare una sessione che non è riuscita in precedenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>ID diagnostica</strong></p></td>
<td><p>Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori. Posizionare il puntatore del mouse sul numero di ID per visualizzare informazioni aggiuntive su tale ID.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-modalities"></a>Metriche per le modalità

Nella tabella seguente sono elencate le informazioni fornite nel report Dettagli sessione peer-to-peer per ogni modalità di sessione.

### <a name="metrics-for-modalities"></a>Metriche per le modalità

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Si può ordinare su questo elemento?</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Modalità</strong></p></td>
<td><p>No</p></td>
<td><p>Modalità usate nella sessione. Ad esempio, messaggistica istantanea (IM) o trasferimento di file.</p></td>
</tr>
<tr class="even">
<td><p><strong>Da messaggi utente</strong></p></td>
<td><p>No</p></td>
<td><p>Numero di messaggi inviati dall'utente che ha avviato la sessione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Per i messaggi degli utenti</strong></p></td>
<td><p>No</p></td>
<td><p>Numero di messaggi inviati dall'utente che è stato invitato a partecipare alla sessione.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-diagnostic-reports"></a>Metriche per i report di diagnostica

Nella tabella seguente sono elencate le informazioni fornite nel report Dettagli sessione peer-to-peer per ogni report di diagnostica.

### <a name="metrics-for-diagnostic-reports"></a>Metriche per i report di diagnostica

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Si può ordinare su questo elemento?</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Dettaglio</strong></p></td>
<td><p>No</p></td>
<td><p>Quando si fa clic su questo elemento, il report Mostra il rapporto di diagnostica per la sessione.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tempo di report</strong></p></td>
<td><p>No</p></td>
<td><p>Data e ora in cui il report è stato registrato.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Richiesta</strong></p></td>
<td><p>No</p></td>
<td><p>Tipo di richiesta SIP. Ad esempio, invita o BYE.</p></td>
</tr>
<tr class="even">
<td><p><strong>ID diagnostica</strong></p></td>
<td><p>No</p></td>
<td><p>Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo di contenuto</strong></p></td>
<td><p>No</p></td>
<td><p>Tipo di contenuto multimediale usato nella conferenza. Ad esempio, un tipo di contenuto comune è Application/sdp. Il protocollo SDP (Session Description Protocol) è un protocollo Internet standard usato per gli annunci di sessione, gli inviti alla sessione e altre forme di avvio delle sessioni multimediali.</p></td>
</tr>
<tr class="even">
<td><p><strong>Segnalato da</strong></p></td>
<td><p>No</p></td>
<td><p>Computer (ovvero client o server) che ha segnalato il problema.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

