---
title: 'Lync Server 2013: Pianificazione per il ripristino di emergenza dei Response Group'
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
ms.openlocfilehash: db3a196a258198fe0bc65b533841544decd96aa2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a>Pianificazione per il ripristino di emergenza dei Response Group in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

In questa sezione vengono illustrati alcuni modi per preparare i gruppi di risposte per il ripristino di emergenza e viene fornita una panoramica del processo di ripristino di emergenza.

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a>Preparazione per il ripristino di emergenza di Response Group

Quando si preparano ed eseguono procedure di ripristino di emergenza, tenere presente quanto segue.

<div>


> [!NOTE]  
> In un ambiente di coesistenza sono supportati solo i gruppi di risposta di Lync Server 2013 per le procedure di ripristino di emergenza descritte in questo documento.



</div>

  - Pianificare il ripristino di emergenza quando si esegue la pianificazione della capacità. Per la capacità di ripristino di emergenza, ogni pool in un pool associato deve essere in grado di gestire i carichi di lavoro di tutti i gruppi di risposta in entrambi i pool. Per informazioni dettagliate sulla pianificazione della capacità dei gruppi di risposta, vedere [pianificazione della capacità per il gruppo di risposte in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).

  - È possibile eseguire copie di backup regolari di tutte le configurazioni di Response Group in tutti i pool Front end in cui è stata distribuita l'applicazione Response Group usando la procedura di esportazione descritta in questo documento. Per informazioni dettagliate, vedere procedure per il [ripristino di emergenza di Response Group in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md). Conservare le copie di backup in una posizione sicura.

  - Mantenere una copia di backup separata di tutti i file audio originali usati per l'applicazione Response Group, incluse le registrazioni e i file di musica in attesa. Conservare i file di backup in una posizione sicura.

  - Per il ripristino di emergenza di Lync Server 2013, tutte le impostazioni del gruppo di risposte devono avere nomi univoci nella distribuzione. Questo requisito si applica ai flussi di lavoro, alle code, ai gruppi di agenti, ai set di festività e alle ore di lavoro. Devi verificare che questo requisito venga soddisfatto quando i pool primari e di backup sono ancora attivi e prima di iniziare qualsiasi procedura di failover. Se si verificano conflitti di nome durante l'importazione di dati di Response Group nel pool di backup, l'importazione non riesce. Per completare la procedura di importazione e failover, è necessario risolvere i conflitti di nome rinominando l'oggetto Response Group nel pool di backup oppure usando il cmdlet **Import-CsRgsConfiguration** con il parametro – ResolveNameConflicts per risolvere automaticamente il conflitto aggiungendo un numero identificativo univoco all'oggetto Response Group.

  - In generale, ti consigliamo di eseguire backup giornalieri, ma se hai un volume elevato di modifiche, potresti voler pianificare backup più frequenti. La quantità di informazioni che è possibile perdere in caso di emergenza dipende dalla frequenza dei backup, nonché dalla frequenza e dal volume delle modifiche.

  - È possibile importare gruppi di risposte in un pool di backup prima che si verifichi un'operazione di emergenza o failover. L'importazione dei gruppi di risposta in anticipo riduce i tempi di inattività, perché il servizio di Response Group di Lync Server può essere ripristinato nel pool di backup non appena le chiamate vengono instradate al pool di backup.
    
    <div>
    

    > [!NOTE]  
    > L'applicazione Response Group non può raggiungere gli agenti ospitati in un pool inattivo fino al completamento del failover. Durante questo periodo, l'applicazione Response Group elabora le chiamate come se tali agenti non fossero disponibili.

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a>Processo di ripristino di emergenza di Response Group

In caso di emergenza, è possibile recuperare i gruppi di risposte usando uno dei metodi di ripristino seguenti:

  - Eseguire il failover in un pool di backup e quindi eseguire il failback nel pool originale.

  - Eseguire il failover in un pool di backup, creare un nuovo pool con un nome di dominio completo diverso (FQDN) e quindi importare i gruppi di risposta nel nuovo pool.

Durante la fase di failover del ripristino di emergenza, i gruppi di risposte si trovano in più pool: nel pool principale (non disponibile) e nel pool di backup. I gruppi di risposte in entrambi i pool hanno lo stesso nome e lo stesso proprietario (il pool principale), ma hanno genitori diversi.

Quando si recupera creando un nuovo pool con un nome di dominio completo diverso, è necessario assegnare il nuovo pool come proprietario dei gruppi di risposta durante l'importazione. La proprietà dei gruppi di risposte rimane con il pool originale, a meno che non si riassegni esplicitamente la proprietà usando il parametro – OverwriteOwner con il cmdlet **Import-CsRgsConfiguration** .

<div>


> [!NOTE]  
> Devi anche usare il parametro – OverwriteOwner se hai ricostruito il pool durante il ripristino (ovvero il database del gruppo di risposte è vuoto), indipendentemente dal fatto che tu usi o meno lo stesso nome FQDN. Non è necessario usare il parametro – OverwriteOwner se non è stato ricostruito il pool, ma è possibile usare questo parametro ogni volta che si importano i gruppi di risposte nel pool principale.



</div>

Puoi definire solo un set di impostazioni di configurazione per il gruppo di risposte a livello di applicazione per ogni pool. Queste impostazioni includono la configurazione predefinita per la musica in blocco, il file audio predefinito per la musica in blocco, il periodo di risponderia dell'agente e la configurazione del contesto delle chiamate. Per visualizzare queste impostazioni di configurazione, eseguire il cmdlet **Get-CsRgsConfiguration** . Per informazioni dettagliate sul cmdlet **Get-CsRgsConfiguration** , vedere [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).

Puoi trasferire queste impostazioni a livello di applicazione da un pool a un altro usando il cmdlet **Import-CsRgsConfiguration** con il parametro – ReplaceExistingSettings, ma in questo modo le impostazioni vengono ignorate nel pool di destinazione.

<div>


> [!IMPORTANT]  
> Questo vincolo relativo al trasferimento delle impostazioni in un altro pool è vero solo per le impostazioni a livello di applicazione e per il file audio predefinito per la musica in blocco. Non si applica a gruppi di agenti, code, flussi di lavoro, orari di ufficio e set di festività.



</div>

Se non si vuole sostituire le impostazioni a livello di applicazione nel pool di backup durante una catastrofe e il pool principale non può essere recuperato, le impostazioni a livello di applicazione del pool primario andranno perse. Se è necessario creare un nuovo pool per sostituire il pool principale durante il ripristino, con lo stesso nome di dominio completo o con un nome di dominio completo diverso, non è possibile recuperare le impostazioni originali a livello di applicazione. In questo caso, devi configurare il nuovo pool con queste impostazioni e includere il file audio per la musica in attesa.

Se si decide di usare il cmdlet **Import-CsRgsConfiguration** per trasferire le impostazioni a livello di applicazione dal pool principale al pool di backup durante un periodo di emergenza, è possibile trasferire le impostazioni dal pool di backup al nuovo pool durante il ripristino nello stesso modo in cui sono state trasferite dal pool principale al pool di backup.

La tabella seguente illustra una panoramica dei passaggi necessari per recuperare i Response Group.

Per informazioni dettagliate sull'esecuzione di questa procedura, vedere procedure per il [ripristino di emergenza di Response Group in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).

### <a name="response-group-disaster-recovery-steps"></a>Passaggi per il ripristino di emergenza di Response Group

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
<td><p>In base a una routine, eseguire il cmdlet <strong>Export-CsRgsConfiguration</strong> per creare backup di tutte le configurazioni di Response Group in tutti i pool Front end in cui viene distribuita l'applicazione Response Group.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>Durante l'interruzione</p></td>
<td><p>Eseguire il cmdlet <strong>Import-CsRgsConfiguration</strong> per importare la configurazione del servizio di risposta di Lync Server dal pool primario al pool di backup.</p>
<div>

> [!NOTE]  
> Usa il parametro – ReplaceExistingSettings se vuoi sostituire le impostazioni del gruppo di risposta a livello di applicazione nel pool di backup con le impostazioni del pool principale. Se non si trasferiscono le impostazioni a livello di applicazione dal pool principale al pool di backup e il pool principale non può essere recuperato, le impostazioni verranno perse dal pool principale.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="odd">
<td><p>Dopo l'importazione</p></td>
<td><p>Eseguire i cmdlet di Response Group con il parametro – ShowAll (per visualizzare tutti i gruppi di risposta) o il parametro – Owner (per visualizzare solo i gruppi di risposta importati) per verificare che tutte le configurazioni di Response Group siano state importate nel pool di backup.</p>
<div>

> [!IMPORTANT]  
> Se non si usa il parametro – ShowAll o il parametro – Owner, i gruppi di risposta importati nel pool di backup non verranno elencati nei risultati restituiti dai cmdlet.


</div>
<p>Eseguire i cmdlet seguenti:</p>
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
<li><p>Effettuare una chiamata di prova a un gruppo di risposte importato nel pool di backup e verificare che la chiamata sia gestita correttamente.</p></li>
<li><p>Tutti gli agenti formali devono accedere di nuovo ai loro gruppi formali nel pool di backup.</p></li>
<li><p>Gestire le modifiche alla configurazione:</p>
<p>I gruppi di risposta nel pool di backup, se importati nel pool di backup o di proprietà del pool di backup, possono essere modificati come di consueto durante l'interruzione.</p>
<div>

> [!IMPORTANT]  
> Per gestire i gruppi di risposta importati nel pool di backup, è necessario usare Lync Server Management Shell. Non è possibile usare il pannello di controllo di Lync Server per gestire questi gruppi di risposta mentre si trovano nel pool di backup.


</div></li>
</ul></td>
<td><p>N/D</p></td>
</tr>
<tr class="odd">
<td><p>Dopo il ripristino, prima di failback</p></td>
<td><p>Eseguire il cmdlet <strong>Export-CsRgsConfiguration</strong> specificando il parametro-source come pool di backup e il parametro – Owner come pool principale per esportare i gruppi di risposte di proprietà del pool principale dal pool di backup.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>Dopo il failback</p></td>
<td><ul>
<li><p>Eseguire il cmdlet <strong>Import-CsRgsConfiguration</strong> per importare di nuovo i gruppi di risposte nel pool principale.</p>
<div>

> [!NOTE]  
> Se il pool principale non può essere recuperato e si distribuisce un nuovo pool per sostituirlo, usare il parametro – ReplaceExistingSettings per trasferire le impostazioni a livello di applicazione dal pool di backup al nuovo pool. Se non si trasferiscono le impostazioni dal pool di backup, il nuovo pool utilizzerà le impostazioni predefinite.


</div></li>
<li><p>Eseguire i cmdlet seguenti con il parametro – ShowAll (per visualizzare tutti i gruppi di risposta) o il parametro – Owner (per visualizzare solo i gruppi di risposta importati) per verificare che tutte le configurazioni di Response Group siano state correttamente importate nel pool principale:</p>
<ul>
<li><p><strong>Get-CsRgsWorkflow</strong></p></li>
<li><p><strong>Get-CsRgsQueue</strong></p></li>
<li><p><strong>Get-CsRgsAgentGroup</strong></p></li>
<li><p><strong>Get-CsRgsHoursOfBusiness</strong></p></li>
<li><p><strong>Get-CsRgsHolidaySet</strong></p></li>
</ul></li>
<li><p>Eseguire una chiamata di prova a un gruppo di risposte importato di nuovo nel pool principale e verificare che la chiamata sia gestita correttamente.</p></li>
<li><p>Facoltativamente, eseguire il cmdlet <strong>Export-CsRgsConfiguration</strong> nel pool di backup con il parametro – RemoveExportedConfiguration per rimuovere i gruppi di risposte di proprietà del pool principale dal pool di backup.</p></li>
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

