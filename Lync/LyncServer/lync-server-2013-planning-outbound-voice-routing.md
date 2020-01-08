---
title: 'Lync Server 2013: Pianificazione del routing vocale in uscita'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning outbound voice routing
ms:assetid: 37c55fa4-175a-4190-b9e4-c2e5ac7b9261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425853(v=OCS.15)
ms:contentKeyID: 48183835
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5315b18e83b84980ff6d61e5385626e104a5e1e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-outbound-voice-routing-in-lync-server-2013"></a>Pianificazione del routing vocale in uscita in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

Il routing delle chiamate in uscita si applica alle chiamate destinate a un gateway PSTN (Public Switched Telephone Network), trunk o PBX (Private Branch Exchange). Quando un utente effettua una chiamata, il server normalizza il numero di telefono in formato E. 164, se necessario, e tenta di associarlo a un URI SIP. Se il server non riesce a eseguire la corrispondenza, applica la logica di routing delle chiamate in uscita in base alla stringa di chiamata fornita. La logica viene definita configurando le impostazioni del server descritte nella tabella seguente.

### <a name="lync-server-outbound-call-routing-settings"></a>Impostazioni di routing delle chiamate in uscita di Lync Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Oggetto</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dial Plan</p></td>
<td><p>Un dial plan è un set denominato di regole di normalizzazione che converte i numeri di telefono per una posizione denominata, un singolo utente o un oggetto contatto in un unico formato standard (E. 164) per scopi di autorizzazione del telefono e routing delle chiamate.</p></td>
</tr>
<tr class="even">
<td><p>Regola di normalizzazione</p></td>
<td><p>Le regole di normalizzazione definiscono il modo in cui i numeri di telefono espressi in diversi formati devono essere instradati per ogni posizione, utente o oggetto contatto specificato. La stessa stringa di chiamata può essere interpretata e tradotta in modo diverso, a seconda della posizione in cui è stata chiamata e della persona o dell'oggetto contatto che effettua la chiamata. Un set di regole di normalizzazione associato a una determinata posizione costituisce un dial plan.</p></td>
</tr>
<tr class="odd">
<td><p>Criteri vocali</p></td>
<td><p>Un criterio vocale associa uno o più record di utilizzo PSTN a un utente o a un gruppo di utenti. Un criterio vocale offre anche un elenco delle funzionalità di chiamata che è possibile abilitare o disabilitare.</p></td>
</tr>
<tr class="even">
<td><p>Record utilizzo PSTN</p></td>
<td><p>Un record di utilizzo PSTN specifica una classe di chiamata, ad esempio Internal, local o Long Distance, che può essere eseguita da vari utenti o gruppi di utenti in un'organizzazione.</p></td>
</tr>
<tr class="odd">
<td><p>Route chiamata</p></td>
<td><p>Una route di chiamata associa i numeri di telefono di destinazione con tronchi particolari e record di utilizzo PSTN. Un gateway PSTN è considerato un trunk.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>Contenuto della sezione

Questa sezione contiene linee guida per la configurazione delle impostazioni del server di routing delle chiamate in uscita seguenti:

  - <span></span>  
    [Dial plan e regole di normalizzazione in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md)

  - <span></span>  
    [Criteri vocali in Lync Server 2013](lync-server-2013-voice-policies.md)

  - <span></span>  
    [Record utilizzo PSTN in Lync Server 2013](lync-server-2013-pstn-usage-records.md)

  - <span></span>  
    [Route vocali in Lync Server 2013](lync-server-2013-voice-routes.md)

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Trunking SIP in Lync Server 2013](lync-server-2013-sip-trunking.md)  
[Connessioni SIP dirette in Lync Server 2013](lync-server-2013-direct-sip-connections.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

