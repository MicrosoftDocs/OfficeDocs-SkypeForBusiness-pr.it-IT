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
ms.openlocfilehash: abfe8c9848e5e015a22bcc7975c6bbdaf1c7465e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-microsoft-lync-clients-in-lync-server-2013"></a>Configurazione degli intervalli di porte per i client Microsoft Lync in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-04-22_

Per impostazione predefinita, le applicazioni client di Lync possono utilizzare qualsiasi porta tra le porte 1024 e 65535 quando sono coinvolte in una sessione di comunicazione. Ciò è dovuto al fatto che gli intervalli di porte specifici non sono abilitati automaticamente per i client. Per poter utilizzare la qualità del servizio, tuttavia, sarà necessario riassegnare i diversi tipi di traffico (audio, video, multimediale, condivisione applicazioni e trasferimento file) a una serie di intervalli di porte univoci. A tale scopo, è possibile utilizzare il cmdlet Set-CsConferencingConfiguration.

<div>


> [!NOTE]  
> Gli utenti finali non possono apportare queste modifiche da soli. Le modifiche apportate alle porte possono essere eseguite solo dagli amministratori utilizzando il cmdlet Set-CsConferencingConfiguration.



</div>

È possibile determinare quali intervalli di porte sono attualmente utilizzati per le sessioni di comunicazione eseguendo il comando riportato di seguito dall'interno di Microsoft Lync Server 2013 Management Shell:

    Get-CsConferencingConfiguration

Presupponendo che non siano state apportate modifiche alle impostazioni di conferenza dopo l'installazione di Lync Server 2013, è consigliabile recuperare le informazioni che includono i valori delle proprietà seguenti:

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

Se si osserva attentamente l'output precedente, si noteranno due aspetti importanti. Innanzitutto, la proprietà ClientMediaPortRangeEnabled è impostata su False:

    ClientMediaPortRangeEnabled : False

Questo è importante perché, quando questa proprietà è impostata su false, i client Lync utilizzeranno qualsiasi porta disponibile tra le porte 1024 e 65535 quando sono coinvolte in una sessione di comunicazione. Questo è vero, indipendentemente da altre impostazioni di porta, ad esempio ClientMediaPort o ClientVideoPort. Se si desidera limitare l'utilizzo a un set specifico di porte (e questo è un elemento che si desidera eseguire se si prevede di implementare la qualità del servizio), è necessario innanzitutto abilitare gli intervalli di porte del supporto client. Che è possibile eseguire utilizzando il comando di Windows PowerShell seguente:

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

Il comando precedente abilita gli intervalli di porte multimediali dei client per la raccolta globale delle impostazioni di configurazione delle conferenze. Tali impostazioni, tuttavia, possono essere applicate anche all'ambito del sito e/o all'ambito del servizio (solo per il servizio Conferencing Server). Per abilitare gli intervalli di porte multimediali dei client per un determinato sito o server, specificare l'identità del sito o del server quando si chiama Set-CsConferencingConfiguration:

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

In alternativa, è possibile usare questo comando per abilitare contemporaneamente gli intervalli di porte per tutte le impostazioni di configurazione delle conferenze:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

Il secondo aspetto importante da osservare è l'output di esempio. Questo mostra che, per impostazione predefinita, gli intervalli di porte multimediali impostati per ogni tipo di traffico di rete sono identici:

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

Per implementare QoS, è necessario che ciascuno di questi intervalli di porte sia univoco. È ad esempio possibile configurare gli intervalli di porte in questo modo:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di traffico client</th>
<th>Inizio intervallo porte</th>
<th>Intervallo porte</th>
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


Nella tabella precedente gli intervalli di porte dei client rappresentano un subset degli intervalli di porte configurati per i server. Sui server, ad esempio, la condivisione applicazioni è configurata in modo da usare le porte da 40803 a 49151, mentre sui computer client la condivisione applicazioni è configurata in modo da usare le porte da 42000 a 42019. Questo consente, ancora una volta, di semplificare l'amministrazione di Qualità del servizio, in quanto non è necessario che le porte dei client rappresentino un subset delle porte usate sul server. Sui computer client è ad esempio possibile configurare la condivisione applicazioni in modo da usare le porte da 10000 a 10019. È tuttavia consigliabile impostare gli intervalli di porte dei client come subset degli intervalli di porte dei server.

Si sarà inoltre notato che sono state riservate 8348 porte per la condivisione applicazioni sui server e che solo 20 porte sono state messe da parte per la condivisione applicazioni sui client. Anche questa regola è consigliata, sebbene non sia categorica. In genere, è possibile considerare che ogni porta disponibile rappresenti una singola sessione di comunicazione: la disponibilità di 100 porte in un intervallo di porte, indica che il computer in questione può partecipare a non più di 100 sessioni di comunicazione in un dato momento. Poiché è probabile che i server verranno coinvolti in un numero di conversazioni di gran lunga superiore a quelle dei client, è ragionevole aprire molte più porte sui server che non sui client. La scelta di riservare 20 porte per la condivisione applicazioni su un client significa che un utente può partecipare contemporaneamente a 20 sessioni di condivisione applicazioni sul dispositivo specificato. Questa configurazione dovrebbe soddisfare la maggior parte degli utenti.

Per assegnare gli intervalli di porte precedenti alla raccolta globale di impostazioni di configurazione delle conferenze, è possibile utilizzare il seguente comando di Lync Server Management Shell:

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

In alternativa, usare il comando per assegnare questi stessi intervalli di porte per tutte le impostazioni di configurazione delle conferenze:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

I singoli utenti devono disconnettersi da Lync e quindi rieseguire l'accesso prima che queste modifiche siano effettivamente effettive.

<div>


> [!NOTE]  
> È anche possibile abilitare gli intervalli di porte multimediali dei client e quindi assegnarli con un singolo comando. Ad esempio:<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>



</div>

</div>

<span> </span>

</div>

</div>

</div>

