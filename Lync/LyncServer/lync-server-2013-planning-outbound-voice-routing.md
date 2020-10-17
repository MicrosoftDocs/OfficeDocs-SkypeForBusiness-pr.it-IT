---
title: 'Lync Server 2013: pianificazione del routing vocale in uscita'
description: 'Lync Server 2013: pianificazione del routing vocale in uscita.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning outbound voice routing
ms:assetid: 37c55fa4-175a-4190-b9e4-c2e5ac7b9261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425853(v=OCS.15)
ms:contentKeyID: 48183835
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 057f81b995e231c2025a9fcb07e675086a662efe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563982"
---
# <a name="planning-outbound-voice-routing-in-lync-server-2013"></a>Pianificazione del routing vocale in uscita in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

Il routing delle chiamate in uscita viene applicato alle chiamate destinate a un gateway PSTN (Public Switched Telephone Network), al trunk o a un PBX (Private Branch Exchange). Quando un utente effettua una chiamata, il server normalizza il numero di telefono convertendolo nel formato E.164, se necessario, e tenta di associarlo a un URI SIP. Se il server non riesce a trovare una corrispondenza, applica la logica di routing delle chiamate in uscita in base alla stringa di composizione fornita. È possibile definire tale logica configurando le impostazioni del server descritte nella tabella seguente.

### <a name="lync-server-outbound-call-routing-settings"></a>Impostazioni del server di routing delle chiamate in uscita Lync Server

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
<td><p>Dial plan</p></td>
<td><p>Per dial plan si intende un set denominato di regole di normalizzazione che consente di convertire i numeri di telefono relativi a una località, a un utente o a un oggetto contatto specifico in un unico formato standard (E.164) ai fini dell'autorizzazione del telefono e del routing della chiamata.</p></td>
</tr>
<tr class="even">
<td><p>Regola di normalizzazione</p></td>
<td><p>Le regole di normalizzazione definiscono come devono essere instradati numeri di telefono espressi in formati diversi per ogni località, utente oppure oggetto contatto specificato. La stessa stringa di composizione può essere interpretata e convertita in modo diverso a seconda della località da cui viene composta e della persona o dell'oggetto contatto che effettua la chiamata. Un insieme di regole di normalizzazione associate a una determinata località costituisce un dial plan.</p></td>
</tr>
<tr class="odd">
<td><p>Criterio vocale</p></td>
<td><p>Un criterio vocale associa uno o più record di utilizzo PSTN a un utente o a un gruppo di utenti. Un criterio vocale fornisce inoltre un elenco di funzionalità di chiamata che è possibile abilitare o disabilitare.</p></td>
</tr>
<tr class="even">
<td><p>Record di utilizzo PSTN</p></td>
<td><p>Un record di utilizzo PSTN specifica un tipo di chiamata (ad esempio interna, locale o interurbana) che può essere effettuata da diversi utenti o gruppi di utenti di un'organizzazione.</p></td>
</tr>
<tr class="odd">
<td><p>Route di chiamata</p></td>
<td><p>Una route di chiamata associa i numeri di telefono di destinazione a trunk e record di utilizzo PSTN specifici. Un gateway PSTN viene considerato un trunk.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>Argomenti della sezione

In questa sezione vengono fornite le linee guida per la configurazione delle impostazioni seguenti del server di routing delle chiamate in uscita:

  - <span></span>  
    [Dial plan e regole di normalizzazione in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md)

  - <span></span>  
    [Criteri vocali in Lync Server 2013](lync-server-2013-voice-policies.md)

  - <span></span>  
    [Record di utilizzo PSTN in Lync Server 2013](lync-server-2013-pstn-usage-records.md)

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

