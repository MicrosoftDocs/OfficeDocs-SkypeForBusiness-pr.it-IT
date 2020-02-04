---
title: 'Lync Server 2013: configurazione degli intervalli di porte per le conferenze, le applicazioni e i server di mediazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Conferencing, Application, and Mediation servers
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
ms.date: 05/01/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54aab5efbca06d918cc2dbeccc0e36aee9d4abf8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756300"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a>Configurazione di intervalli di porte in Lync Server 2013 per i servizi di conferenza, applicazione e mediazione

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2015-04-30_

Per implementare la qualità del servizio, è necessario configurare intervalli di porte identici per la condivisione di audio, video e applicazioni in servizi di conferenza, applicazione e mediazione; Inoltre, questi intervalli di porte non devono sovrapporsi in alcun modo. Per usare un semplice esempio, supponiamo di usare le porte da 10000 a 10999 per il video nei server di conferenza. Ciò significa che devi anche prenotare le porte da 10000 a 10999 per il video nell'applicazione e nei server di mediazione. In caso contrario, QoS non funzionerà come previsto.

Allo stesso modo, supponiamo di prenotare le porte da 10000 a 10999 per il video, ma di prenotare le porte da 10500 a 11999 per l'audio. Ciò può creare problemi per la qualità del servizio, perché gli intervalli di porte si sovrappongono. Con QoS ogni modalità deve avere un set di porte univoco: se si usano le porte da 10000 a 10999 per il video, è necessario usare un intervallo diverso, ad esempio da 11000 a 11999 per l'audio.

Per impostazione predefinita, gli intervalli di porte audio e video non si sovrappongono in Microsoft Lync Server 2013; Tuttavia, gli intervalli di porte assegnati alla sovrapposizione di condivisione delle applicazioni con gli intervalli di porte audio e video. Il che, a sua volta, indica che nessuno di questi intervalli è univoco. Puoi verificare gli intervalli di porte esistenti per i servizi di conferenza, applicazione e mediazione eseguendo i seguenti tre comandi dall'interno di Lync Server 2013 Management Shell:

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> Come si può vedere nei comandi precedenti, ogni tipo di porta-audio, video e condivisione applicazioni-viene assegnato due valori di proprietà distinti: l'inizio della porta e il numero di porta. L'inizio della porta indica la prima porta usata per tale modalità; ad esempio, se la porta audio Start è uguale a 50000, significa che la prima porta usata per il traffico audio è la porta 50000. Se il numero di porta audio è 2 (che non è un valore valido, ma viene usato qui per scopi illustrativi), ciò significa che solo 2 porte vengono allocate per l'audio. Se la prima porta è la porta 50000 e sono presenti un totale di due porte, significa che la seconda porta deve essere la porta 50001 (gli intervalli di porta devono essere contigui). Di conseguenza, l'intervallo di porte per l'audio sarebbe porte da 50000 a 50001, inclusi.<BR>Nota anche che Application Server e Mediation Server supportano solo QoS per l'audio; non è necessario modificare le porte di condivisione di video o applicazioni nei server delle applicazioni o nei server di mediazione.



</div>

Se si eseguono i tre comandi precedenti, si noterà che i valori di porta predefiniti per Lync Server 2013 sono configurati in questo modo:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Proprietà</th>
<th>Server delle conferenze</th>
<th>Server applicazioni</th>
<th>Mediation Server</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AudioPortStart</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
</tr>
<tr class="even">
<td><p>AudioPortCount</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>VideoPortStart</p></td>
<td><p>57501</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>VideoPortCount</p></td>
<td><p>8034</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationSharingPortStart</p></td>
<td><p>49152</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>ApplicationSharingPortCount</p></td>
<td><p>16383</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>


Come indicato in precedenza, quando si configurano le porte di Lync Server per QoS, è necessario assicurarsi che: 1) le impostazioni della porta audio siano identiche tra i servizi di conferenza, applicazione e mediazione. e 2) gli intervalli di porte non si sovrappongono. Se si guarda attentamente la tabella precedente, si vedrà che gli intervalli di porta sono identici tra i tre tipi di server. Ad esempio, la porta audio iniziale è impostata su porta 49152 su ogni tipo di server e il numero totale di porte riservate per l'audio in ogni server è identico: 8348. Tuttavia, gli intervalli di porte si sovrappongono: le porte audio iniziano dalla porta 49152, ma anche le porte sono riservate per la condivisione delle applicazioni. Per usare in modo ottimale la qualità del servizio, la condivisione delle applicazioni deve essere riconfigurata in modo da usare un intervallo di porte univoco. Ad esempio, puoi configurare la condivisione delle applicazioni per iniziare dalla porta 40803 e usare le porte di 8348. (Perché le porte di 8348? Se Aggiungi questi valori insieme, 40803 + 8348, significa che la condivisione delle applicazioni userà le porte 40803 tramite la porta 49150. Poiché le porte audio non iniziano fino alla porta 49152, non si avranno più intervalli di porte sovrapposti.

Dopo aver selezionato il nuovo intervallo di porte per la condivisione delle applicazioni, è possibile apportare le modifiche usando il cmdlet Set-CsConferencingServer. Questa modifica non deve essere eseguita nei server delle applicazioni o nei server di mediazione, perché questi server non gestiscono il traffico di condivisione delle applicazioni. È necessario modificare i valori di porta solo in questi server se si decide di riassegnare le porte usate per il traffico audio.

Per modificare i valori di porta per la condivisione delle applicazioni in un singolo server di conferenza, eseguire un comando simile a questo da Lync Server Management Shell:

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

Se si vogliono apportare queste modifiche in tutti i server dei servizi di conferenza, è possibile eseguire questo comando:

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

Dopo aver modificato le impostazioni della porta, è necessario interrompere e quindi riavviare ogni servizio interessato dalle modifiche.

Non è obbligatorio che i server di conferenza, i server delle applicazioni e i Mediation Server condividano esattamente lo stesso intervallo di porte; l'unico requisito vero è l'impostazione degli intervalli di porte univoci in tutti i server. Tuttavia, l'amministrazione sarà in genere più semplice se usi lo stesso set di porte in tutti i server.

</div>

<span> </span>

</div>

</div>

</div>

