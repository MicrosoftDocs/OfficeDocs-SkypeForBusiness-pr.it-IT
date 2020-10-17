---
title: 'Lync Server 2013: requisiti di backup e ripristino: strumenti e autorizzazioni'
description: 'Lync Server 2013: requisiti di backup e ripristino: strumenti e autorizzazioni.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: tools and permissions'
ms:assetid: 35ec2e33-f33e-4f84-9e64-6550fd78aa52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202171(v=OCS.15)
ms:contentKeyID: 51541465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36327d1214854586b44024f126bbd87acad6c4b2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553468"
---
# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a>Requisiti di backup e ripristino in Lync Server 2013: Tools and Permissions

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-17_

In questo argomento vengono identificati gli strumenti che è possibile utilizzare per eseguire il backup e il ripristino di Lync Server 2013, le autorizzazioni necessarie e la possibilità di eseguire comandi in remoto o localmente. In particolare, questo argomento si concentra sugli strumenti forniti con Lync Server per il backup e il ripristino.

<div>

## <a name="backups"></a>Backup

Per eseguire il backup di Lync Server, utilizzare gli strumenti identificati nella tabella seguente. Tutti i comandi di cui è necessario eseguire il backup di Lync Server possono essere scritti in remoto e possono essere eseguiti in modalità remota.

### <a name="tools-for-backing-up-lync-server"></a>Strumenti per il backup di Lync Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Per il backup di questo componente:</th>
<th>Utilizzare questo strumento o cmdlet:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dati di configurazione della topologia (Xds.mdf)</p></td>
<td><p>Export-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Dati del servizio Informazioni percorso (E9-1-1) (Lis.mdf)</p></td>
<td><p>Export-CsLisConfiguration</p></td>
</tr>
<tr class="odd">
<td><p>Dati di configurazione di Response Group (RgsConfig.mdf)</p></td>
<td><p>Export-CsRgsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Dati utente permanenti (database rtcxds. MDF)</p>
<p>ID conferenza</p></td>
<td><p>Export-CsUserData</p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p>Database di archiviazione (LcsLog.mdf)</p></li>
<li><p>Database di registrazione dettagli chiamata di monitoraggio (LcsCDR.mdf)</p></li>
<li><p>Database QoE di monitoraggio (QoEMetrics.mdf)</p></li>
</ul></td>
<td><p>Strumento dei database di SQL Server, ad esempio SQL Server Management Studio</p></td>
</tr>
<tr class="even">
<td><p>Database di chat persistente (MGC. MDF)</p></td>
<td><p>Procedure di backup o Export-CsPersistentChatData di SQL Server. Export-CsPersistentChatData Esporta i dati della chat persistente come file.</p></td>
</tr>
<tr class="odd">
<td><p>Tutti gli archivi file: archivio file di Lync Server, archivio file di archiviazione</p>
<div>

> [!NOTE]  
> Non eseguire il backup dei file denominati <STRONG>Meeting.Active</STRONG>. Questi file sono in uso e bloccati mentre è in corso una riunione.


</div></td>
<td><p>Strumento di gestione del file System standard, ad esempio Robocopy.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a>Ripristino

Per ripristinare Lync Server, utilizzare gli strumenti riportati nella tabella seguente. Tutti i comandi necessari per il ripristino di Lync Server possono essere scritti tramite script. Alcuni possono essere eseguiti in remoto, mentre altri devono essere eseguiti localmente, come specificato nella tabella seguente.

### <a name="tools-for-restoring-lync-server"></a>Strumenti per il ripristino di Lync Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Per eseguire questa operazione:</th>
<th>Utilizzare questo strumento o cmdlet:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Creare un computer nuovo o pulito</p></td>
<td><ul>
<li><p>Software di installazione del sistema operativo Windows</p></li>
<li><p>Software di installazione di SQL Server</p></li>
<li><p>Snap-in MMC (Microsoft Management Console) Certificati, per ripristinare certificati con una chiave privata esportabile</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Ripristinare dati dell'archivio file</p></td>
<td><p>Strumento di gestione del file system standard, ad esempio Robocopy</p></td>
</tr>
<tr class="odd">
<td><p>Ricreare database vuoti e impostare le autorizzazioni per gli elementi seguenti:</p>
<ul>
<li><p>Archivio di gestione centrale</p></li>
<li><p>Server back-end</p></li>
<li><p>Database di monitoraggio</p></li>
<li><p>Database di archiviazione</p></li>
</ul></td>
<td><p>Install-CsDatabase</p></td>
</tr>
<tr class="even">
<td><p>Ripristinare il puntatore di servizi di dominio Active Directory all'archivio di gestione centrale</p>
<div>

> [!NOTE]  
> Se a un certo punto si perde il punto di connessione del servizio, è possibile eseguire di nuovo questo cmdlet.


</div></td>
<td><p>Set-CsConfigurationStoreLocation</p></td>
</tr>
<tr class="odd">
<td><p>Importare la topologia, i criteri e le impostazioni di configurazione nell'archivio di gestione centrale (XDS. MDF)</p></td>
<td><p>Import-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Pubblicare e abilitare la topologia</p></td>
<td><p>Strumento di generazione topologia</p>
<p>-oppure-</p>
<p>Publish-CsTopology e Enable-CsTopology</p></td>
</tr>
<tr class="odd">
<td><p>Abilitare l'ultima topologia pubblicata</p></td>
<td><p>Enable-CsTopology</p></td>
</tr>
<tr class="even">
<td><p>Reinstallare i componenti di Lync Server</p></td>
<td><p>Installazione di Lync Server</p>
<div>

> [!NOTE]  
> Si trova nella cartella di installazione di Lync Server o nel file multimediale in \setup\amd64\Setup.exe.


</div></td>
</tr>
<tr class="odd">
<td><p>Ripristinare i dati di Informazioni percorso (E9-1-1) (Lis.mdf)</p></td>
<td><p>Import-CsLisConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Ripristinare i dati utente permanenti (rtcxds. MDF)</p></td>
<td><p>Import-CsUserData</p></td>
</tr>
<tr class="odd">
<td><p>Ripristinare i dati di configurazione di Response Group (RgsConfig.mdf)</p></td>
<td><p>Import-CsRgsConfiguration</p>
<div>

> [!NOTE]  
> Se la configurazione viene ripristinata in un pool appena distribuito che non dispone di dati di Response Group nel database, è consigliabile utilizzare l'opzione – OverwriteOwner. Utilizzare questa opzione anche se i dati ripristinati sono presenti in un pool con lo stesso nome di dominio completo (FQDN). In caso contrario, l'importazione non avrà esito positivo, a causa degli oggetti contatto ai Response Group già esistenti in Active Directory.


</div></td>
</tr>
<tr class="even">
<td><p>Ripristinare i database seguenti:</p>
<ul>
<li><p>Database di archiviazione (LcsLog.mdf)</p></li>
<li><p>Database di monitoraggio: database di registrazione dettagli chiamata (LcsCDR.mdf) e database QoE (QoEMetrics.mdf)</p></li>
</ul></td>
<td><p>Strumenti di gestione dei database di SQL Server</p></td>
</tr>
<tr class="odd">
<td><p>Database di chat persistente (MGS. MDF)</p></td>
<td><p>Procedure di ripristino di SQL Server o Import-CsPersistentChatData. È possibile utilizzare Import-CsPersistentChatData con un file creato da Export-CsPersistentChatData e i dati verranno importati nel database di Persistent Chat.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a>Autorizzazioni necessarie

Gli utenti devono essere membri del gruppo **RTCUniversalServerAdmins** per eseguire tutti i comandi descritti in questo argomento. La maggior parte dei comandi di backup e ripristino non supporta il controllo di accesso basato sui ruoli (RBAC). Due eccezioni sono i cmdlet di Persistent Chat Export-CsPersistentChatData e Import-CsPersistentChatData, che devono essere eseguiti da un utente membro del gruppo ruolo CsPersistentChatAdministrator. Per eseguire la distribuzione guidata di Lync Server, è necessario che un utente sia anche membro del gruppo amministratori locale.

</div>

</div>

<span> </span>

</div>

</div>

</div>

