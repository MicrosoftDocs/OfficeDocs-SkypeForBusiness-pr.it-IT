---
title: 'Lync Server 2013: configurazione degli intervalli di porte per i client Microsoft Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Microsoft Lync clients
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6405ff6738315476efb7ee65f6d5e020a7cf28a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-microsoft-lync-clients-in-lync-server-2013"></a>Configurazione degli intervalli di porte per i client Microsoft Lync in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-04-22_

Per impostazione predefinita, le applicazioni client di Lync possono usare una qualsiasi porta tra le porte 1024 e 65535 quando si partecipa a una sessione di comunicazione; il motivo è che gli intervalli di porte specifici non vengono abilitati automaticamente per i client. Per poter usare la qualità del servizio, è tuttavia necessario riassegnare i vari tipi di traffico (audio, video, multimediale, condivisione applicazioni e trasferimento di file) a una serie di intervalli di porte univoci. Questa operazione può essere eseguita usando il cmdlet Set-CsConferencingConfiguration.

<div>


> [!NOTE]  
> Gli utenti finali non possono apportare queste modifiche. Le modifiche alle porte possono essere eseguite solo dagli amministratori tramite il cmdlet Set-CsConferencingConfiguration.



</div>

Per determinare gli intervalli di porte attualmente usati per le sessioni di comunicazione, è possibile eseguire il comando seguente all'interno di Microsoft Lync Server 2013 Management Shell:

    Get-CsConferencingConfiguration

Supponendo che non siano state apportate modifiche alle impostazioni di conferenza dopo l'installazione di Lync Server 2013, è consigliabile recuperare le informazioni che includono questi valori di proprietà:

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

Se si osserva attentamente l'output precedente, verranno visualizzati due elementi importanti. Prima di tutto, la proprietà ClientMediaPortRangeEnabled è impostata su false:

    ClientMediaPortRangeEnabled : False

Questo è importante perché, quando questa proprietà è impostata su false, i client Lync useranno qualsiasi porta disponibile tra le porte 1024 e 65535 quando sono coinvolte in una sessione di comunicazione; Questo vale indipendentemente da qualsiasi altra impostazione della porta, ad esempio ClientMediaPort o ClientVideoPort. Se si vuole limitare l'utilizzo a un set di porte specificato (e si vuole eseguire questa operazione se si prevede di implementare la qualità del servizio), è necessario prima di tutto abilitare gli intervalli di porta del supporto client. Questa operazione può essere eseguita usando il comando di Windows PowerShell seguente:

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

Il comando precedente consente di abilitare gli intervalli di porta multimediali del client per la raccolta globale delle impostazioni di configurazione delle conferenze; Queste impostazioni possono tuttavia essere applicate anche all'ambito del sito e/o all'ambito del servizio (solo per il servizio di conferenza Server). Per abilitare gli intervalli della porta multimediale client per un sito o un server specifico, specificare l'identità del sito o del server quando si chiama Set-CsConferencingConfiguration:

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

In alternativa, puoi usare questo comando per abilitare simultaneamente gli intervalli di porta per tutte le impostazioni di configurazione della conferenza:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

La seconda cosa importante che si noterà è che l'output di esempio mostra che, per impostazione predefinita, gli intervalli di porte multimediali impostati per ogni tipo di traffico di rete sono identici:

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

Per implementare QoS, ognuno di questi intervalli di porte dovrà essere univoco. Ad esempio, è possibile configurare gli intervalli di porte come questo:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di traffico client</th>
<th>Inizio porta</th>
<th>Intervallo di porte</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>50020</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Video</p></td>
<td><p>58000</p></td>
<td><p>20</p></td>
</tr>
<tr class="odd">
<td><p>Condivisione applicazioni</p></td>
<td><p>42000</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Trasferimento di file</p></td>
<td><p>42020</p></td>
<td><p>20</p></td>
</tr>
</tbody>
</table>


Nella tabella precedente gli intervalli di porte client rappresentano un sottoinsieme degli intervalli di porte configurati per i server. Ad esempio, nei server la condivisione delle applicazioni è stata configurata per l'uso delle porte da 40803 a 49151; nei computer client la condivisione delle applicazioni è configurata per l'uso delle porte da 42000 a 42019. Anche questa operazione viene eseguita principalmente per semplificare l'amministrazione di QoS: le porte client non devono rappresentare un sottoinsieme delle porte usate nel server. Ad esempio, nei computer client è possibile configurare la condivisione delle applicazioni per usare, per dire, le porte da 10000 a 10019. Tuttavia, è consigliabile rendere gli intervalli della porta del client un sottoinsieme degli intervalli di porte del server.

Inoltre, potresti aver notato che le porte di 8348 sono state accantonate per la condivisione delle applicazioni sui server, ma solo 20 porte sono state accantonate per la condivisione delle applicazioni nei client. Anche questo è consigliato, ma non è una regola difficile e veloce. In generale, è possibile considerare ogni porta disponibile per rappresentare una singola sessione di comunicazione: se sono disponibili porte di 100 in un intervallo di porte che significa che il computer in questione può partecipare, al massimo, a 100 sessioni di comunicazione in qualsiasi momento. Poiché i server probabilmente parteciperanno a molte più conversazioni rispetto ai client, è opportuno aprire molte più porte nei server che nei client. L'impostazione di 20 porte per la condivisione delle applicazioni in un client significa che un utente può partecipare a 20 sessioni di condivisione applicazioni nel dispositivo specificato e contemporaneamente. Questo dovrebbe risultare sufficiente per la stragrande maggioranza degli utenti.

Per assegnare gli intervalli di porte precedenti alla raccolta globale di impostazioni di configurazione per i servizi di conferenza, è possibile usare il comando Lync Server Management Shell seguente:

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

In alternativa, usare questo comando per assegnare gli stessi intervalli di porte per tutte le impostazioni di configurazione per i servizi di conferenza:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

I singoli utenti devono disconnettersi da Lync e quindi eseguire nuovamente l'accesso prima che le modifiche abbiano effetto.

<div>


> [!NOTE]  
> Puoi anche abilitare gli intervalli di porta multimediali del client e quindi assegnare questi intervalli di porte usando un singolo comando. Ad esempio:<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>



</div>

</div>

<span> </span>

</div>

</div>

</div>

