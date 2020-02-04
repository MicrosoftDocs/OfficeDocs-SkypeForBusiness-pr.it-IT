---
title: 'Lync Server 2013: fogli di lavoro di backup e ripristino'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration worksheets
ms:assetid: 26c78155-0306-41ac-845b-7ad58000a1d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202169(v=OCS.15)
ms:contentKeyID: 51541460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 390d6289daf8075c873e90319642f0e74b61d835
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a>Fogli di lavoro di backup e ripristino per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-18_

Il piano di backup e ripristino per l'organizzazione deve contenere informazioni dettagliate su come e quando eseguire il backup di dati e impostazioni. È possibile usare i fogli di lavoro presentati in questo articolo per documentare queste informazioni per la distribuzione specifica e per i requisiti di backup e ripristino dell'organizzazione.

Usare i fogli di lavoro seguenti per registrare le informazioni necessarie per eseguire il backup e il ripristino di database, archivio file e informazioni sulle impostazioni per un pool di Lync Server o un server Standard Edition. Conservare una o più copie di questi fogli di lavoro in una posizione sicura in modo che siano facilmente accessibili se è necessario ripristinare Lync Server.

<div>


> [!NOTE]  
> I fogli di lavoro in questa sezione coprono solo le informazioni necessarie per ripristinare i dati e le impostazioni dei database e server di Lync Server. Se è necessario documentare altre informazioni di ripristino, ad esempio le informazioni per la reinstallazione di sistemi operativi e altro software, usare i piani di distribuzione dell'organizzazione e i piani di backup e ripristino per rispondere a tali requisiti.



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a>Foglio di lavoro backup e ripristino di database

Usare la tabella seguente per registrare le informazioni necessarie per eseguire il backup e ripristinare i database di Lync Server.

### <a name="database-information-for-backup-and-restoration"></a>Informazioni sul database per il backup e il ripristino

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Database</th>
<th>Nome server (FQDN)</th>
<th>Pianificazione del backup</th>
<th>Strumento di backup del database</th>
<th>Set di backup</th>
<th>Destinazione di backup</th>
<th>Note</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Database RTC sul server back-end per i dati utente</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p>Cmdlet <strong>Export-CsUserData</strong></p></td>
<td><p>Nome</p>
<p>Scadenza</p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p>Database di LcsLog (nome predefinito) in archiviazione del server di database</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Strumento di gestione di SQL Server</p></td>
<td><p>Nome</p>
<p>Scadenza</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>Database di LcsCdr per il monitoraggio del server di database per record dettagli chiamata (CDRs)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Strumento di gestione di SQL Server</p></td>
<td><p>Nome</p>
<p>Scadenza</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p>Database di QoEMetrics sul server di database di monitoraggio per i dati di qualità dell'esperienza (QoE)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Strumento di gestione di SQL Server</p></td>
<td><p>Nome</p>
<p>Scadenza</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>Database di chat persistente</p></td>
<td></td>
<td></td>
<td><p>Strumento di gestione di SQL Server o cmdlet <strong>Export-CsPersistentChatData</strong></p></td>
<td><p>Nome</p>
<p>Scadenza</p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


Non è necessario alcun backup o ripristino dei database seguenti:

  - RTCDyn. I dati utente temporanei in questo database non sono necessari per il ripristino del servizio.

  - RTCAb. Il database della Rubrica viene ricreato automaticamente dall'elenco indirizzi globale (GAL) in servizi di dominio Active Directory.

  - Rgsdyn. I dati del servizio Response Group temporaneo in questo database non sono necessari per il ripristino del servizio.

  - Cpsdyn. Le informazioni dinamiche per l'applicazione per il parcheggio delle chiamate non sono necessarie per il ripristino del servizio.

  - MgcComp. Il database di conformità per la chat persistente non è necessario per il ripristino del servizio.

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a>Foglio di lavoro backup e ripristino del file Store

Usare la tabella seguente per registrare le informazioni necessarie per eseguire il backup e ripristinare gli archivi di file. Gli archivi di file contengono dati, ad esempio i metadati del contenuto della riunione, i registri di conformità delle riunioni, i registri di aggiornamento per gli aggiornamenti dei dispositivi e i file audio per il Response Group, il parcheggio delle chiamate e le applicazioni

### <a name="file-store-information-for-backup-and-restoration"></a>Informazioni sull'archiviazione dei file per il backup e il ripristino

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Contenuto</th>
<th>Nome server (FQDN)</th>
<th>Pianificazione del backup</th>
<th>Strumento backup file System</th>
<th>Condivisione file di cui eseguire il backup *</th>
<th>Destinazione di backup</th>
<th>Note</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Archivio file di Lync Server</p></td>
<td></td>
<td></td>
<td><p>Strumento di backup standard, ad esempio Robocopy</p></td>
<td><p>In file server per Enterprise Edition. In Standard Edition per impostazione predefinita, per la distribuzione di Standard Edition. In genere, una per ogni sito.</p></td>
<td></td>
<td><p>Non è necessario eseguire il backup dei file denominati <strong>meeting. Active</strong> . Questi file sono in uso e sono bloccati durante una riunione.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a>Foglio di lavoro backup e ripristino delle impostazioni

Usare la tabella seguente per registrare le informazioni necessarie per eseguire il backup e il ripristino delle impostazioni.

### <a name="settings-information-for-backup-and-restoration"></a>Informazioni sulle impostazioni per il backup e il ripristino

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Database</th>
<th>Nome server (FQDN)</th>
<th>Pianificazione del backup</th>
<th>Strumento di backup</th>
<th>Nome file di configurazione (con estensione XML)</th>
<th>Percorso di backup</th>
<th>Note</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Database XDS in Central Management store per la configurazione della topologia (globale)</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p>Cmdlet <strong>Export-CsConfiguration</strong></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p>Database LIS in Central Management store per le informazioni sulla posizione di E9-1-1 (globale)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Cmdlet <strong>Export-CsLisConfiguration</strong></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p>Database di RgsConfig nel server back-end per la configurazione del gruppo di risposte (pool)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Cmdlet <strong>Export-CsRgsConfiguration</strong></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

