---
title: "Lync Server 2013: configurazione degli intervalli di porte per le conferenze, l'applicazione e i Mediation Server"
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
ms.openlocfilehash: ecd505990b9a060c3b669700ea9192dc1ad6b84c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a>Configurazione degli intervalli di porte in Lync Server 2013 per i servizi di conferenza, applicazione e Mediation Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2015-04-30_

Per implementare Qualità del servizio, è necessario configurare intervalli di porte identici per la condivisione di audio, video e applicazioni sui server per conferenze, sui server applicazioni e sui Mediation Server. Questi intervalli non devono sovrapporsi in alcun modo. Ecco un semplice esempio. Supponiamo di usare le porte 10000-10999 dei server per conferenze per il video. Questo significa che le stesse porte devono essere riservate alle funzioni video anche sui server applicazioni e sui Mediation Server. in caso contrario, QoS non funzionerà come previsto.

Analogamente, supponiamo di riservare le porte 10000-10999 per il video e le porte 10500-11999 per l'audio. Questa configurazione crea problemi al funzionamento di Qualità del servizio, perché gli intervalli delle porte si sovrappongono. Con QoS ogni modalità deve disporre di un set di porte esclusivo. Se si usano le porte 10000-10999 per il video, è necessario usare un altro intervallo, ad esempio 11000-11999, per l'audio.

Per impostazione predefinita, gli intervalli di porte audio e video non si sovrappongono in Microsoft Lync Server 2013; Tuttavia, gli intervalli di porte assegnati alla sovrapposizione di condivisione delle applicazioni con gli intervalli di porte audio e video. Che, a sua incirca, significa che nessuno di questi intervalli è univoco. È possibile verificare gli intervalli di porte esistenti per i servizi di conferenza, applicazione e Mediation Server eseguendo i tre comandi seguenti dall'interno di Lync Server 2013 Management Shell:

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> Come si vede nei comandi precedenti, a ciascun tipo di porta (audio, video e condivisione di applicazioni) sono assegnati due valori di proprietà separati: PortStart e PortCount. PortStart indica la prima porta usata per la modalità in questione. Ad esempio, se AudioPortStart corrisponde a 50000, significa che la prima porta usata per il traffico audio è la porta 50000. Se AudioPortCount corrisponde a 2 (che non è un valore valido, ma che useremo qui puramente a titolo di esempio), significa che per l'audio sono allocate solo due porte. Se la prima porta è la porta 50000 e ci sono due porte in tutto, la seconda porta deve essere la porta 50001 (negli intervalli di porte le porte devono essere contigue). Di conseguenza, l'intervallo di porte per l'audio deve essere costituito dalle porte da 50000 a 50001 comprese.<BR>Si noti anche che i server applicazioni e i Mediation Server supportano QoS solo per l'audio. Per questi server non è quindi necessario modificare le porte di condivisione video o applicazioni.



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
<th>Server per conferenze</th>
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


Come indicato in precedenza, quando si configurano le porte di Lync Server per QoS, è necessario assicurarsi che: 1) le impostazioni della porta audio siano identiche tra i propri servizi di conferenza, applicazioni e Mediation Server. e 2) gli intervalli di porte non si sovrappongono. Se si osserva la tabella precedente, si nota che gli intervalli di porte sono identici per i tre tipi di server. Ad esempio, la porta audio iniziale corrisponde alla porta 49152 per ciascun tipo di server. Anche il numero totale di porte riservate all'audio in ciascun server è identico: 8348. Tuttavia gli intervalli di porte si sovrappongono: le porte audio iniziano in corrispondenza della porta 49152, ma lo stesso avviene per le porte riservate alla condivisione delle applicazioni. Per ottimizzare l'uso di Quality of Service, è necessario riconfigurare la condivisione delle applicazioni in modo che usi un intervallo esclusivo, ad esempio impostando l'inizio alla porta 40803 e l'uso di 8348 porte. Perché 8348 porte? Se si aggiungono questi valori insieme--40803 + 8348--questo significa che la condivisione di applicazioni utilizzerà le porte 40803 tramite la porta 49150. Poiché le porte audio iniziano con la porta 49152, gli intervalli di porte non si sovrappongono più.

Dopo aver selezionato il nuovo intervallo di porte per la condivisione applicazioni, è possibile eseguire la modifica mediante il cmdlet Set-CsConferencingServer. Questa modifica non è necessaria per i server applicazioni e i Mediation Server, perché questi server non gestiscono il traffico relativo alla condivisione applicazioni. Per questi server i valori delle porte devono essere modificati solo se si decide di riassegnare le porte usate per il traffico audio.

Per modificare i valori delle porte per la condivisione delle applicazioni in un singolo server Conferencing, eseguire un comando simile a questo dall'interno di Lync Server Management Shell:

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

Se invece si vogliono eseguire queste modifiche in tutti i server per conferenze, è possibile eseguire questo comando:

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

Dopo la modifica delle impostazioni relative alle porte, è necessario arrestare e riavviare tutti i servizi interessati dalle modifiche.

Non è obbligatorio che i server per conferenze, i server applicazioni e i Mediation Server condividano esattamente lo stesso intervallo di porte. L'unico requisito è che ogni server abbia un intervallo di porte esclusivo. Tuttavia, in genere l'amministrazione è più semplice se si usa lo stesso intervallo di porte per tutti i server.

</div>

<span> </span>

</div>

</div>

</div>

