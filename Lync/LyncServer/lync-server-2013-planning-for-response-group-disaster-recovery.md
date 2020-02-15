---
title: 'Lync Server 2013: pianificazione per il ripristino di emergenza di Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for response group disaster recovery
ms:assetid: 14e0f5dc-77cd-42cd-a9c9-4d0da38fb1cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204699(v=OCS.15)
ms:contentKeyID: 48183482
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 049e07e72efba508add2135c6b77aebed2c38954
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050638"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a>Pianificazione del ripristino di emergenza di Response Group in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

In questa sezione vengono illustrati alcuni modi per preparare i Response Group per ripristini di emergenza e fornita una panoramica del processo di ripristino di emergenza.

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a>Preparazione per il ripristino di emergenza di Response Group

Durante la preparazione e l'esecuzione delle procedure di ripristino di emergenza, tenere presente quanto segue.

<div>


> [!NOTE]  
> In un ambiente di coesistenza, solo i Response Group di Lync Server 2013 sono supportati per le procedure di ripristino di emergenza descritte in questo documento.



</div>

  - Pianificare il ripristino di emergenza durante la pianificazione delle capacità. Per le capacità del ripristino di emergenza, ogni pool appartenente a una coppia deve essere in grado di gestire i carichi di lavoro di tutti i Response Group di entrambi i pool. Per informazioni dettagliate sulla pianificazione della capacità dei Response Group, vedere [Capacity Planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).

  - Eseguire regolarmente copie di backup di tutte le configurazioni di Response Group in tutti i pool Front end in cui è stata distribuita l'applicazione Response Group utilizzando la procedura di esportazione descritta in questo documento. Per ulteriori informazioni, vedere [procedure di ripristino di emergenza di Response Group in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md). Conservare le copie di backup in una posizione sicura.

  - Mantenere una copia di backup distinta di tutti i file audio originali utilizzati per l'applicazione Response Group, incluse le registrazioni e i file musicali in attesa. Conservare le copie di backup in una posizione sicura.

  - Per il ripristino di emergenza di Lync Server 2013, tutte le impostazioni di Response Group devono avere nomi univoci nella distribuzione. Questo requisito si applica a flussi di lavoro, code, gruppi di agenti, set di festività e orario di ufficio. È opportuno verificare che questo requisito sia soddisfatto quando i pool principale e di backup sono ancora attivi e prima di avviare una procedura di failover. Se vengono rilevati conflitti di nome durante l'importazione dei dati dei Response Group al pool di backup, l'importazione non riesce. Per completare l'importazione e la procedura di failover, è necessario risolvere i conflitti di nome rinominando l'oggetto Response Group nel pool di backup o utilizzando il cmdlet **Import-CsRgsConfiguration** con il parametro –ResolveNameConflicts affinché risolva automaticamente il conflitto aggiungendo un numero di identificazione univoco all'oggetto Response Group.

  - In generale, è consigliabile eseguire backup giornalieri, ma in presenza di un volume elevato di modifiche è possibile pianificare backup più frequenti. La quantità di informazioni che è possibile perdere in caso di emergenza varia in base alla frequenza dei backup, oltre che alla frequenza e al volume di modifiche.

  - È possibile importare i Response Group in un pool di backup prima di un'operazione di failover o di una situazione di emergenza. L'importazione anticipata dei Response Group consente di ridurre i tempi di inattività, poiché il servizio di risposta di Lync Server può essere ripristinato nel pool di backup non appena le chiamate vengono instradate al pool di backup.
    
    <div>
    

    > [!NOTE]  
    > L'applicazione Response Group non è in grado di raggiungere gli agenti ospitati in un pool inattivo finché non è stato completato il failover. Durante questo periodo, l'applicazione Response Group elabora le chiamate come se tali agenti non fossero disponibili.

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a>Processo di ripristino di emergenza dei Response Group

In caso di emergenza, è possibile ripristinare i Response Group utilizzando uno dei seguenti metodi di ripristino:

  - Eseguire il failover su un pool di backup e quindi il failback sul pool originale.

  - Eseguire il failover su un pool di backup, creare un nuovo pool con un nome di dominio completo (FQDN) differente, quindi importare i Response Group nel nuovo pool.

Durante la fase di failover del ripristino di emergenza, i Response Group risiedono sia nel pool principale (non disponibile) che in quello di backup. Tali Response Group hanno lo stesso nome e lo stesso proprietario (il pool principale), ma padri diversi.

Quando si esegue il ripristino creando un nuovo pool con un FQDN diverso, è necessario assegnare il nuovo pool come proprietario dei Response Group al momento dell'importazione. La proprietà dei Response Group rimane nel pool originale se non viene esplicitamente riassegnata dall'utente utilizzando il parametro –OverwriteOwner con il cmdlet **Import-CsRgsConfiguration**.

<div>


> [!NOTE]  
> È inoltre necessario utilizzare il parametro – OverwriteOwner se il pool è stato ricreato durante il ripristino (ovvero se il database di Response Group è vuoto), indipendentemente dal fatto che si utilizzi o meno lo stesso nome di dominio completo. Non è necessario utilizzare il parametro –OverwriteOwner se non si ricostruisce il pool, ma è possibile utilizzarlo ogniqualvolta si reimportano i Response Group nel pool principale.



</div>

È possibile definire un solo set di impostazioni di configurazione dei Response Group a livello di applicazione per ogni pool. Le impostazioni includono la configurazione di musica di attesa predefinita, il file audio di musica di attesa predefinita, il periodo di tolleranza di richiamata agente e la configurazione del contesto di chiamata. Per visualizzare queste impostazioni di configurazione, eseguire il cmdlet **Get-CsRgsConfiguration**. Per informazioni dettagliate sul cmdlet **Get-CsRgsConfiguration** , vedere [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).

È possibile trasferire queste impostazioni a livello di applicazione da un pool a un altro utilizzando il cmdlet **Import-CsRgsConfiguration** con parametro –ReplaceExistingSettings. L'operazione tuttavia sostituisce le impostazioni nel pool di destinazione.

<div>


> [!IMPORTANT]  
> Il vincolo sul trasferimento di impostazioni a un altro pool è valido solo per le impostazioni a livello di applicazione e per il file audio della musica di attesa predefinita. Non si applica a gruppi di agenti, code, flussi di lavoro, orario di ufficio e set di festività.



</div>

Se non si desidera sostituire le impostazioni a livello di applicazione nel pool di backup in caso di emergenza e il pool principale non può essere ripristinato, le impostazioni a livello di applicazione nel pool principale saranno perse. Se durante il ripristino è necessario creare un nuovo pool in sostituzione del pool principale con lo stesso FQDN o un FQDN diverso, non è possibile ripristinare le impostazioni a livello di applicazione originali. In questo caso, è necessario configurare il nuovo pool con queste impostazioni e includere il file audio di musica di attesa.

Se in caso di emergenza si decide di trasferire le impostazioni a livello di applicazione dal pool principale a quello di backup utilizzando il cmdlet **Import-CsRgsConfiguration**, è possibile trasferire le impostazioni dal pool di backup al nuovo pool durante il ripristino nello stesso modo in cui le si è trasferite dal pool principale a quello di backup.

Nella tabella seguente viene fornita una panoramica dei passaggi del processo di ripristino dei Response Group.

Per informazioni dettagliate sull'esecuzione di questi passaggi, vedere [procedure di ripristino di emergenza di Response Group in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).

### <a name="response-group-disaster-recovery-steps"></a>Procedura di ripristino di emergenza dei Response Group

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Passaggi</th>
<th>Gruppi e ruoli obbligatori</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Prima dell'interruzione</p></td>
<td><p>In base alla routine, eseguire il cmdlet <strong>Export-CsRgsConfiguration</strong> per creare backup di tutte le configurazioni di Response Group in tutti i pool Front end in cui viene distribuita l'applicazione Response Group.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>Durante l'interruzione</p></td>
<td><p>Eseguire il cmdlet <strong>Import-CsRgsConfiguration</strong> per importare la configurazione del servizio di Response Group del backup di Lync Server dal pool primario al pool di backup.</p>
<div>

> [!NOTE]  
> Utilizzare il parametro – ReplaceExistingSettings se si desidera sostituire le impostazioni del gruppo di risposta a livello di applicazione nel pool di backup con le impostazioni del pool primario. Se le impostazioni a livello di applicazione del pool principale non vengono trasferite al pool di backup e il pool principale non può essere ripristinato, le impostazioni del pool principale andranno perse.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="odd">
<td><p>Dopo l'importazione</p></td>
<td><p>Eseguire i cmdlet di Response Group con il parametro – ShowAll (per visualizzare tutti i Response Group) o il parametro – Owner (per visualizzare solo i Response Group importati) per verificare che tutte le configurazioni dei gruppi di risposta siano state importate nel pool di backup.</p>
<div>

> [!IMPORTANT]  
> Senza il parametro –ShowAll o –Owner, i Response Group importati nel pool di backup non saranno elencati nei risultati restituiti dai cmdlet.


</div>
<p>Eseguire i seguenti cmdlet:</p>
<ul>
<li><p><strong>Get-CsRgsWorkflow</strong></p></li>
<li><p><strong>Get-CsRgsQueue</strong></p></li>
<li><p><strong>Get-CsRgsAgentGroup</strong></p></li>
<li><p><strong>Get-CsRgsHoursOfBusiness</strong></p></li>
<li><p><strong>Get-CsRgsHolidaySet</strong></p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>Dopo il failover</p></td>
<td><ul>
<li><p>Effettuare una chiamata di prova a un Response Group importato nel pool di backup e verificare che sia gestita correttamente.</p></li>
<li><p>Tutti gli agenti formali devono effettuare di nuovo l'accesso ai propri gruppi formali nel pool di backup.</p></li>
<li><p>Gestire le modifiche di configurazione:</p>
<p>I Response Group contenuti nel pool di backup possono essere modificati come al solito durante l'interruzione, a prescindere se siano importati o di proprietà nel pool di backup.</p>
<div>

> [!IMPORTANT]  
> È necessario utilizzare Lync Server Management Shell per gestire i Response Group importati nel pool di backup. Non è possibile utilizzare il pannello di controllo di Lync Server per gestire questi Response Group mentre si trovano nel pool di backup.


</div></li>
</ul></td>
<td><p>N/D</p></td>
</tr>
<tr class="odd">
<td><p>Dopo il ripristino e prima del failback</p></td>
<td><p>Eseguire il cmdlet <strong>Export-CsRgsConfiguration</strong> specificando il parametro -Source come pool di backup e il parametro –Owner come pool principale per esportare i Response Group di proprietà del pool principale dal pool di backup.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>Dopo il failback</p></td>
<td><ul>
<li><p>Eseguire il cmdlet <strong>Import-CsRgsConfiguration</strong> per importare di nuovo i Response Group nel pool principale.</p>
<div>

> [!NOTE]  
> Se il pool principale non è ripristinabile e in sostituzione viene distribuito un nuovo pool, utilizzare il parametro –ReplaceExistingSettings per trasferire le impostazione a livello di applicazione dal pool di backup al nuovo pool. In caso contrario, il nuovo pool utilizzerà le impostazioni predefinite.


</div></li>
<li><p>Eseguire i cmdlet riportati di seguito con il parametro –ShowAll, se si desidera visualizzare tutti i Response Group, o il parametro –Owner, se si desidera visualizzare solo i Response Group importati, per verificare che tutte le configurazioni dei Response Group siano state reimportate correttamente nel pool principale:</p>
<ul>
<li><p><strong>Get-CsRgsWorkflow</strong></p></li>
<li><p><strong>Get-CsRgsQueue</strong></p></li>
<li><p><strong>Get-CsRgsAgentGroup</strong></p></li>
<li><p><strong>Get-CsRgsHoursOfBusiness</strong></p></li>
<li><p><strong>Get-CsRgsHolidaySet</strong></p></li>
</ul></li>
<li><p>Effettuare una chiamata di prova a un Response Group reimportato nel pool principale e verificare che sia gestita correttamente.</p></li>
<li><p>Facoltativamente, eseguire il cmdlet <strong>Export-CsRgsConfiguration</strong> nel pool di backup con il parametro –RemoveExportedConfiguration per rimuovere i Response Group di proprietà del pool principale dal pool di backup.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

