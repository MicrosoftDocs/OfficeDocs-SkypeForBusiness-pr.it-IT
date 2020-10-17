---
title: 'Lync Server 2013: fogli di lavoro per il backup e il ripristino'
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
ms.openlocfilehash: 161a8577558705c773974b1cc733337b29b6dbd5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532623"
---
# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a>Fogli di lavoro per il backup e il ripristino di Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-18_

Il piano di backup e ripristino per l'organizzazione deve contenere informazioni dettagliate su come e quando si esegue il backup dei dati e delle impostazioni. È possibile utilizzare i fogli di lavoro presentati in questo articolo per documentare queste informazioni per la distribuzione specifica e per i requisiti di backup e ripristino dell'organizzazione.

Utilizzare i fogli di lavoro seguenti per registrare le informazioni necessarie per il backup e il ripristino di database, archivio file e informazioni sulle impostazioni di un pool di Lync Server o di un server Standard Edition. Mantenere una o più copie di questi fogli di lavoro in una posizione sicura in modo che siano facilmente accessibili se è necessario ripristinare Lync Server.

<div>


> [!NOTE]  
> Nei fogli di lavoro di questa sezione vengono riportate solo le informazioni necessarie per ripristinare i dati e le impostazioni dei database e server di Lync Server. Se è necessario documentare altre informazioni di ripristino, ad esempio le informazioni per la reinstallazione di sistemi operativi e altro software, utilizzare i piani di distribuzione dell'organizzazione e i piani di backup e ripristino per soddisfare tali requisiti.



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a>Foglio di lavoro per il backup e il ripristino del database

Utilizzare la tabella seguente per registrare le informazioni necessarie per eseguire il backup e il ripristino dei database di Lync Server.

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
<td><p>LcsLog (nome predefinito) database sul server di database di archiviazione</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Strumento di gestione di SQL Server</p></td>
<td><p>Nome</p>
<p>Scadenza</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>Database di LcsCdr per il monitoraggio del server di database per i record dettagli chiamata (CDRs)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Strumento di gestione di SQL Server</p></td>
<td><p>Nome</p>
<p>Scadenza</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p>Database di QoEMetrics per il monitoraggio del server di database per i dati QoE (Quality of Experience)</p></td>
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


Non è necessario eseguire il backup o il ripristino dei database seguenti:

  - RTCDyn. I dati utente temporanei in questo database non sono necessari per il ripristino del servizio.

  - RTCAb. Il database della Rubrica viene automaticamente ricreato dall'elenco indirizzi globale (GAL, Global Address List) in servizi di dominio Active Directory.

  - Rgsdyn. I dati del servizio Response Group transienti in questo database non sono necessari per il ripristino del servizio.

  - Cpsdyn. Le informazioni dinamiche per l'applicazione Parcheggio di chiamata non sono necessarie per il ripristino del servizio.

  - MgcComp. Il database di conformità per la chat persistente non è necessario per il ripristino del servizio.

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a>Foglio di lavoro per il backup e il ripristino dell'archivio file

Utilizzare la tabella seguente per registrare le informazioni necessarie per eseguire il backup e il ripristino degli archivi di file. Gli archivi file contengono dati quali i metadati del contenuto della riunione, i registri di conformità delle riunioni, i registri di aggiornamento per gli aggiornamenti dei dispositivi e i file audio per il Response Group, il parcheggio di chiamata e le applicazioni di annuncio.

### <a name="file-store-information-for-backup-and-restoration"></a>Informazioni sull'archivio file per il backup e il ripristino

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
<th>Strumento di backup del file System</th>
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
<td><p>Su file server per Enterprise Edition. In Standard Edition per impostazione predefinita, per la distribuzione di Standard Edition. In genere, una per ogni sito.</p></td>
<td></td>
<td><p>Non eseguire il backup dei file denominati <strong>Meeting.Active</strong>. Questi file sono in uso e sono bloccati durante una riunione.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a>Foglio di lavoro per il backup e il ripristino delle impostazioni

Utilizzare la tabella seguente per registrare le informazioni necessarie per il backup e il ripristino delle impostazioni.

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
<th>Nome del file di configurazione (con estensione XML)</th>
<th>Percorso di backup</th>
<th>Note</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Database di XDS nell'archivio di gestione centrale per la configurazione della topologia (globale)</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p>Cmdlet <strong>Export-CsConfiguration</strong></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p>Database LIS nell'archivio di gestione centrale per le informazioni sulla posizione di E9-1-1 (globale)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Cmdlet <strong>Export-CsLisConfiguration</strong></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p>Database di RgsConfig nel server back-end per la configurazione di Response Group (pool)</p></td>
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

