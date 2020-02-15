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
ms.openlocfilehash: 085a87d24efed3f9f5e1a5d2d30c29c9b8461693
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a>Configurazione di scenari di esempio video per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-02_

Lync 2013 aggiunge nuove funzionalità video per il supporto del video per la visualizzazione di video e raccolta di 1920 x 1080 Full High Definition (HD). Le misure basate sui dati dei clienti mostrano che la larghezza di banda video tipica è aumentata solo leggermente rispetto a Lync 2010, ma la larghezza di banda massima del flusso video è aumentata a causa del supporto di Full HD (per informazioni dettagliate, vedere la sezione "utilizzo di Network Traffic media" nei [requisiti di larghezza di banda di rete per il traffico multimediale in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)). Gli amministratori possono quindi limitare la larghezza di banda video per determinati utenti, ad esempio gli utenti in una succursale con meno capacità di rete, e contribuire a garantire la migliore qualità video possibile per gli altri utenti, ad esempio i dirigenti.

Nella tabella seguente viene fornito un elenco delle impostazioni consigliate per la configurazione di video per le diverse capacità di rete. Queste impostazioni impediscono ad alcuni scenari degli utenti di inviare e ricevere video con risoluzione superiore (vedere la colonna a destra). L'impostazione minima consentirà la mancata disponibilità del video della raccolta a causa della larghezza di banda massima della rete di ricezione.

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
<th>Risoluzione video prevista per un video di qualità buona</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Elevate</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>8000</p></td>
<td><p>8000</p></td>
<td><p>Risoluzione video peer-to-peer: fino a 1920 x 1080</p>
<p>Visualizzazione raccolta: fino a 2 1920 x 1080 video o più video con risoluzione più piccola</p></td>
</tr>
<tr class="even">
<td><p>Buone</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>2500</p></td>
<td><p>2500</p></td>
<td><p>Risoluzione video peer-to-peer: fino a 1280 x 720</p>
<p>Visualizzazione raccolta: fino a 5 640 x 360 risoluzione video</p></td>
</tr>
<tr class="odd">
<td><p>Medio</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>1000</p></td>
<td><p>1000</p></td>
<td><p>Risoluzione video peer-to-peer: fino a 960 x 540</p>
<p>Visualizzazione raccolta: fino a 5 424 x 240 risoluzione video</p></td>
</tr>
<tr class="even">
<td><p>Minimo</p></td>
<td><p>True</p></td>
<td><p>False</p></td>
<td><p>350</p></td>
<td><p>350</p></td>
<td><p>Risoluzione video peer-to-peer: fino a 424 x 240</p>
<p>Visualizzazione raccolta: non disponibile</p></td>
</tr>
</tbody>
</table>


È possibile utilizzare le informazioni contenute nella tabella precedente per distribuire le nuove funzionalità di conferenza video HD e visualizzazione raccolta per alcuni utenti dell'organizzazione, consentendo di risoluzioni video diverse per gli altri.

Nell'esempio seguente, l'amministratore esegue il rollback delle nuove funzionalità video con la qualità video più alta disponibile solo per i dirigenti. Per i dipendenti di una filiale remota con capacità di rete ridotta, viene distribuita solo l'impostazione minima della tabella precedente. Per tutti gli altri dipendenti, viene distribuita l'impostazione "buona" dalla tabella precedente.

Per implementare le nuove funzionalità ai dirigenti, l'amministratore crea un criterio di conferenza denominato ExecutiveVideo. I criteri di conferenza sono disponibili nelle impostazioni seguenti:

  - VideoBitRateKB è impostato su 8000 kbps

  - TotalReceiveVideoBitRateKB è impostato su 8000 kbps

  - AllowMultiview è impostato su true

  - EnableMultiviewJoin è impostato su true

Per i dipendenti della succursale, l'amministratore crea un criterio di conferenza denominato BranchOfficeVideo. I criteri di conferenza sono disponibili nelle impostazioni seguenti:

  - VideoBitRateKB è impostato su 350 Kbps

  - TotalReceiveVideoBitRateKB è impostato su 350 Kbps

  - AllowMultiview è impostato su true

  - EnableMultiviewJoin è impostato su false

Per tutti gli altri dipendenti, l'amministratore crea un criterio di conferenza denominato StandardVideo. I criteri di conferenza sono disponibili nelle impostazioni seguenti:

  - VideoBitRateKB è impostato su 2500 kbps

  - TotalReceiveVideoBitRateKB è impostato su 2500 kbps

  - AllowMultiview è impostato su true

  - EnableMultiviewJoin è impostato su true

L'amministratore assegna i criteri di conferenza agli utenti, come indicato di seguito:

  - I criteri di conferenza di ExecutiveVideo sono assegnati ai dirigenti.

  - Il criterio di conferenza BranchOfficeVideo viene assegnato a tutti i dipendenti della succursale.

  - Il criterio di conferenza StandardVideo viene assegnato a tutti gli altri dipendenti.

Queste assegnazioni dei criteri di conferenza determinano l'esperienza utente seguente:

  - Tutte le conferenze organizzate da qualsiasi visualizzazione raccolta supporto utenti, ma i dipendenti della succursale non possono sperimentare la visualizzazione della raccolta.

  - Per tutte le conferenze a due o più parti, i dirigenti possono inviare video Full HD 1920 x 1080, se il loro collegamento hardware e di rete lo supporta, e possono ricevere un video Full HD da 1920 x 1080 in cui gli altri client dei partecipanti lo supportano.

  - I dipendenti che non sono dirigenti sperimentano risoluzioni più basse rispetto ai dirigenti nelle conferenze a due o più parti, ma ottengono comunque una buona risoluzione.

  - I dipendenti che si trovano nella succursale ricevono una buona qualità video nelle chiamate a due parti quando Lync Visualizza le dimensioni predefinite della finestra video. Tuttavia, se la finestra di Lync è ingrandita a schermo intero, la risoluzione video non aumenterà. Per le conferenze con più partecipanti, i dipendenti della succursale vedranno un solo video attivo.

</div>

<span> </span>

</div>

</div>

</div>

