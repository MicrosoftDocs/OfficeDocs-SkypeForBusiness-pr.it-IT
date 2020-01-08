---
title: 'Lync Server 2013: requisiti di backup e ripristino: strumenti e autorizzazioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Backup and restoration requirements: tools and permissions'
ms:assetid: 35ec2e33-f33e-4f84-9e64-6550fd78aa52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202171(v=OCS.15)
ms:contentKeyID: 51541465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53128d99abfd438c174b98544889781b5f29b57b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979812"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a>Requisiti di backup e ripristino in Lync Server 2013: strumenti e autorizzazioni

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-17_

Questo argomento identifica gli strumenti che è possibile usare per eseguire il backup e il ripristino di Lync Server 2013, le autorizzazioni necessarie e se è possibile eseguire comandi in remoto o localmente. In particolare, questo argomento si basa sugli strumenti forniti con Lync Server per il backup e il ripristino.

<div>

## <a name="backups"></a>Backup

Per eseguire il backup di Lync Server, usare gli strumenti identificati nella tabella seguente. Tutti i comandi necessari per eseguire il backup di Lync Server possono essere creati tramite script e possono essere eseguiti in remoto.

### <a name="tools-for-backing-up-lync-server"></a>Strumenti per il backup di Lync Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Per eseguire il backup:</th>
<th>Usare questo strumento o cmdlet:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dati di configurazione della topologia (XDS. MDF)</p></td>
<td><p>Export-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Dati del servizio informazioni sulla posizione (E9-1-1) (LIS. MDF)</p></td>
<td><p>Export-CsLisConfiguration</p></td>
</tr>
<tr class="odd">
<td><p>Dati di configurazione dei gruppi di risposte (RgsConfig. MDF)</p></td>
<td><p>Export-CsRgsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Dati utente permanenti (database rtcxds. MDF)</p>
<p>ID conferenza</p></td>
<td><p>Export-CsUserData</p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p>Database di archiviazione (LcsLog. MDF)</p></li>
<li><p>Monitoraggio del database di record dettagli chiamata (LcsCDR. MDF)</p></li>
<li><p>Monitoraggio del database QoE (QoEMetrics. MDF)</p></li>
</ul></td>
<td><p>Strumento database di SQL Server, ad esempio SQL Server Management Studio</p></td>
</tr>
<tr class="even">
<td><p>Database di chat persistente (MGC. MDF)</p></td>
<td><p>Procedure di backup di SQL Server o Export-CsPersistentChatData. Export-CsPersistentChatData Esporta i dati della chat persistente come file.</p></td>
</tr>
<tr class="odd">
<td><p>Tutti gli archivi di file: Lync Server file Store, archiviazione file Store</p>
<div>

> [!NOTE]  
> Non è necessario eseguire il backup dei file denominati <STRONG>meeting. Active</STRONG> . Questi file sono in uso e bloccati durante una riunione.


</div></td>
<td><p>Strumento di gestione del file System standard, ad esempio Robocopy.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a>Restauro

Per ripristinare Lync Server, usare gli strumenti della tabella seguente. Tutti i comandi necessari per ripristinare Lync Server possono essere creati tramite script. Alcune possono essere eseguite in remoto, ma altre devono essere eseguite localmente, come specificato nella tabella seguente.

### <a name="tools-for-restoring-lync-server"></a>Strumenti per il ripristino di Lync Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Procedi come segue.</th>
<th>Usare questo strumento o cmdlet:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Creare un computer nuovo o pulito</p></td>
<td><ul>
<li><p>Software di installazione del sistema operativo Windows</p></li>
<li><p>Software di installazione di SQL Server</p></li>
<li><p>Snap-in certificati di Microsoft Management Console (MMC), se il ripristino di certificati con una chiave privata esportabile</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Ripristinare i dati dell'archivio file</p></td>
<td><p>Strumento di gestione del file System standard, ad esempio Robocopy</p></td>
</tr>
<tr class="odd">
<td><p>Ricreare database vuoti e impostare le autorizzazioni per gli elementi seguenti:</p>
<ul>
<li><p>Central Management store</p></li>
<li><p>Server back-end</p></li>
<li><p>Database di monitoraggio</p></li>
<li><p>Database di archiviazione</p></li>
</ul></td>
<td><p>Install-CsDatabase</p></td>
</tr>
<tr class="even">
<td><p>Ripristinare il puntatore di servizi di dominio Active Directory a Central Management store</p>
<div>

> [!NOTE]  
> Se si perde il punto di connessione del servizio in qualsiasi momento, è possibile rieseguire questo cmdlet.


</div></td>
<td><p>Set-CsConfigurationStoreLocation</p></td>
</tr>
<tr class="odd">
<td><p>Importare la topologia, i criteri e le impostazioni di configurazione in Central Management store (XDS. MDF)</p></td>
<td><p>Import-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Pubblicare e abilitare la topologia</p></td>
<td><p>Generatore di topologie</p>
<p>o</p>
<p>Publish-CsTopology e Enable-CsTopology</p></td>
</tr>
<tr class="odd">
<td><p>Abilitare l'ultima topologia pubblicata</p></td>
<td><p>Enable-CsTopology</p></td>
</tr>
<tr class="even">
<td><p>Reinstallare i componenti di Lync Server</p></td>
<td><p>Configurazione di Lync Server</p>
<div>

> [!NOTE]  
> Disponibile nella cartella di installazione di Lync Server o in un file multimediale in \setup\amd64\Setup.exe.


</div></td>
</tr>
<tr class="odd">
<td><p>Ripristinare le informazioni sulla posizione (E9-1-1) dati (LIS. MDF)</p></td>
<td><p>Import-CsLisConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Ripristinare i dati utente permanenti (rtcxds. MDF)</p></td>
<td><p>Import-CsUserData</p></td>
</tr>
<tr class="odd">
<td><p>Ripristinare i dati di configurazione di Response Group (RgsConfig. MDF)</p></td>
<td><p>Import-CsRgsConfiguration</p>
<div>

> [!NOTE]  
> Se la configurazione viene ripristinata in un pool appena distribuito che non contiene dati del gruppo di risposte nel database, è necessario usare l'opzione – OverwriteOwner. Usare questa opzione anche se i dati da ripristinare si trova in un pool con lo stesso nome di dominio completo (FQDN). In caso contrario, l'importazione non avrà esito positivo, a causa degli oggetti contatto per i gruppi di risposte già esistenti in Active Directory.


</div></td>
</tr>
<tr class="even">
<td><p>Ripristinare i database seguenti:</p>
<ul>
<li><p>Database di archiviazione (LcsLog. MDF)</p></li>
<li><p>Database di monitoraggio: database di record dettagli chiamata (LcsCDR. MDF) e database QoE (QoEMetrics. MDF)</p></li>
</ul></td>
<td><p>Strumenti di gestione di database di SQL Server</p></td>
</tr>
<tr class="odd">
<td><p>Database di chat persistente (MGS. MDF)</p></td>
<td><p>Procedure di ripristino di SQL Server o Import-CsPersistentChatData. È possibile usare Import-CsPersistentChatData con un file creato da Export-CsPersistentChatData e i dati verranno importati nel database della chat persistente.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a>Autorizzazioni necessarie

Gli utenti devono essere membri del gruppo **RTCUniversalServerAdmins** per eseguire tutti i comandi descritti in questo argomento. La maggior parte dei comandi di backup e ripristino non supporta il controllo di accesso basato sui ruoli (RBAC). Due eccezioni sono i cmdlet per la chat persistente Export-CsPersistentChatData e Import-CsPersistentChatData, che devono essere eseguiti da un utente membro del gruppo CsPersistentChatAdministrator. Per eseguire la distribuzione guidata di Lync Server, un utente deve essere anche membro del gruppo di amministratori locale.

</div>

</div>

<span> </span>

</div>

</div>

</div>

