---
title: 'Lync Server 2013: configurazione degli scenari di esempio video'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video example scenarios
ms:assetid: da0d61a2-7ac4-4562-bf6a-18473a29acb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205297(v=OCS.15)
ms:contentKeyID: 48185536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbdd47056b97da1ba3ac1bf884cc3e8bd9aaf43f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a>Configurazione di scenari di esempio video per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-02_

Lync 2013 aggiunge nuove funzionalità video per supportare il video della visualizzazione della raccolta e del video in alta definizione (HD) di 1920 x 1080. Le misurazioni basate sui dati dei clienti mostrano che la larghezza di banda video tipica è aumentata solo leggermente rispetto a Lync 2010, ma la larghezza di banda massima del flusso video è aumentata a causa del supporto di Full HD (per i dettagli, vedere la sezione "utilizzo della rete del traffico multimediale" nei [requisiti di larghezza di banda per il traffico multimediale in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)). Gli amministratori possono pertanto limitare la larghezza di banda video per alcuni utenti, ad esempio gli utenti di una filiale con meno capacità di rete, e contribuire a garantire la migliore qualità possibile per gli altri utenti, ad esempio i dirigenti.

La tabella seguente contiene un elenco di impostazioni consigliate per la configurazione di video per diverse capacità di rete. Queste impostazioni limitano alcuni scenari utente all'invio e alla ricezione di video con risoluzione superiore (vedi colonna più a destra). L'impostazione minima consentirà di ottenere un video della raccolta non disponibile, a causa della larghezza di banda massima di ricezione della rete.

### <a name="recommended-video-settings"></a>Impostazioni video consigliate

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
<th>-</th>
<th>AllowMultiView</th>
<th>EnableMultiViewJoin</th>
<th>VideoBitRateKB</th>
<th>TotalReceiveVideoBitRateKB</th>
<th>Risoluzione video prevista per un video di qualità ottimale</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Procedure</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>8000</p></td>
<td><p>8000</p></td>
<td><p>Peer-to-peer: risoluzione video fino a 1920 x 1080</p>
<p>Visualizzazione raccolta: fino a 2 1920 x 1080 video o più video di risoluzione più piccoli</p></td>
</tr>
<tr class="even">
<td><p>Good</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>2500</p></td>
<td><p>2500</p></td>
<td><p>Peer-to-peer: risoluzione video fino a 1280 x 720</p>
<p>Visualizzazione raccolta: fino a 5 640 x 360 risoluzione video</p></td>
</tr>
<tr class="odd">
<td><p>Media</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>1000</p></td>
<td><p>1000</p></td>
<td><p>Peer-to-peer: risoluzione video fino a 960 x 540</p>
<p>Visualizzazione raccolta: fino a 5 424 x 240 risoluzione video</p></td>
</tr>
<tr class="even">
<td><p>Minimo</p></td>
<td><p>True</p></td>
<td><p>False</p></td>
<td><p>350</p></td>
<td><p>350</p></td>
<td><p>Peer-to-peer: risoluzione video fino a 424 x 240</p>
<p>Visualizzazione raccolta: non disponibile</p></td>
</tr>
</tbody>
</table>


È possibile usare le informazioni nella tabella precedente per distribuire le nuove caratteristiche di conferenza video e video HD per alcuni utenti dell'organizzazione, consentendo di risoluzioni video diverse per gli altri.

Nell'esempio seguente l'amministratore esegue il rollback delle nuove caratteristiche video con la qualità video più alta disponibile solo per i dirigenti. Per i dipendenti in una filiale remota con capacità di rete ridotta, viene distribuita solo l'impostazione minima della tabella precedente. Per tutti gli altri dipendenti, viene distribuita l'impostazione "buona" della tabella precedente.

Per implementare le nuove funzionalità per i dirigenti, l'amministratore crea un criterio per le conferenze denominato ExecutiveVideo. I criteri per i servizi di conferenza includono le impostazioni seguenti:

  - VideoBitRateKB è impostato su 8000 kbps

  - TotalReceiveVideoBitRateKB è impostato su 8000 kbps

  - AllowMultiview è impostato su true

  - EnableMultiviewJoin è impostato su true

Per i dipendenti della filiale, l'amministratore crea un criterio per i servizi di conferenza denominato BranchOfficeVideo. I criteri per i servizi di conferenza includono le impostazioni seguenti:

  - VideoBitRateKB è impostato su 350 Kbps

  - TotalReceiveVideoBitRateKB è impostato su 350 Kbps

  - AllowMultiview è impostato su true

  - EnableMultiviewJoin è impostato su false

Per tutti gli altri dipendenti, l'amministratore crea un criterio per i servizi di conferenza denominato StandardVideo. I criteri per i servizi di conferenza includono le impostazioni seguenti:

  - VideoBitRateKB è impostato su 2500 kbps

  - TotalReceiveVideoBitRateKB è impostato su 2500 kbps

  - AllowMultiview è impostato su true

  - EnableMultiviewJoin è impostato su true

L'amministratore assegna i criteri di conferenza agli utenti come indicato di seguito:

  - I criteri di conferenza ExecutiveVideo sono assegnati ai dirigenti.

  - I criteri di conferenza BranchOfficeVideo sono assegnati a tutti i dipendenti della filiale.

  - I criteri di conferenza StandardVideo sono assegnati a tutti gli altri dipendenti.

Queste assegnazioni dei criteri di conferenza generano l'esperienza utente seguente:

  - Tutte le conferenze organizzate da qualsiasi visualizzazione della raccolta di supporto utenti, ma i dipendenti della filiale non possono provare la visualizzazione della raccolta.

  - Per tutte le conferenze a due o più partecipanti, i dirigenti possono inviare video Full HD di 1920 x 1080, se l'hardware e il collegamento di rete lo supportano e possono ricevere il video completo di 1920 x 1080 in cui gli altri client partecipanti lo supportano.

  - I dipendenti che non sono dirigenti sperimentano risoluzioni più basse rispetto ai dirigenti delle conferenze a due o più partecipanti, ma ottengono comunque una buona risoluzione.

  - I dipendenti che si trovano nella filiale otterranno una qualità video ottimale nelle chiamate in due parti quando Lync Visualizza le dimensioni predefinite della finestra del video. Tuttavia, se la finestra di Lync è ingrandita a schermo intero, la risoluzione del video non aumenta. Per le conferenze multiparte, i dipendenti della filiale vedranno solo un video attivo.

</div>

<span> </span>

</div>

</div>

</div>

