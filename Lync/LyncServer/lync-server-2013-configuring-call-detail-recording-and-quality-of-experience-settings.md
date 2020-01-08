---
title: Configurazione delle impostazioni di Registrazione dettagli chiamata e Qualità percepita dagli utenti
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring call detail recording and Quality of Experience settings
ms:assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204621(v=OCS.15)
ms:contentKeyID: 48183223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 67c9759faad4ed96cdf65d8bd22c5778512933de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-call-detail-recording-and-quality-of-experience-settings-in-lync-server-2013"></a>Configurazione della registrazione dei dettagli delle chiamate e della qualità delle impostazioni dell'esperienza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-17_

Dopo avere associato un archivio di monitoraggio con un pool Front-End, configurare l'archivio di monitoraggio e quindi installato e configurato SQL Server Reporting Services e monitoraggio dei report è possibile gestire la registrazione dei dettagli delle chiamate (CDR) e la qualità dell'esperienza (QoE) monitoraggio tramite Lync Server Management Shell. I cmdlet di Lync Server Management Shell consentono di abilitare e disabilitare il monitoraggio CDR e/o QoE per un determinato sito o per l'intera distribuzione di Lync Server. Questa operazione può essere eseguita con un comando semplice come questo:

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $False

Quando si installa Microsoft Lync Server 2013, viene installata anche una raccolta predefinita di impostazioni di configurazione globali sia per CDR che per QoE. Nella tabella seguente sono illustrati i valori predefiniti per alcune delle impostazioni più comuni usate per la registrazione dei dettagli delle chiamate:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Proprietà</th>
<th>Descrizione</th>
<th>Valore predefinito</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnableCDR</p></td>
<td><p>Indica se CDR è abilitato o meno. Se true, tutti i record CDR verranno raccolti e scritti nel database di monitoraggio.</p></td>
<td><p>True</p></td>
</tr>
<tr class="even">
<td><p>EnablePurging</p></td>
<td><p>Indica se i record CDR verranno eliminati periodicamente dal database. Se true, i record verranno eliminati dopo il periodo di tempo specificato dalle proprietà KeepCallDetailForDays (per i record CDR) e KeepErrorReportForDays (per gli errori CDR). Se false, i record CDR verranno mantenuti indefinitamente.</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>KeepCallDetailForDays</p></td>
<td><p>Indica il numero di giorni in cui i record CDR verranno conservati nel database. tutti i record antecedenti al numero di giorni specificato verranno eliminati automaticamente. Tuttavia, questo problema si verificherà solo se l'eliminazione è stata abilitata.</p>
<p>KeepCallDetailForDays può essere impostato su un valore intero compreso tra 1 e 2562 giorni (circa 7 anni).</p></td>
<td><p>60 giorni</p></td>
</tr>
<tr class="even">
<td><p>KeepErrorReportForDays</p></td>
<td><p>Indica il numero di giorni in cui vengono mantenuti i report di errore CDR; tutti i report antecedenti al numero di giorni specificato verranno eliminati automaticamente. I report di errore CDR sono report di diagnostica caricati da applicazioni client come Microsoft Lync 2013.</p>
<p>Puoi impostare questa proprietà su qualsiasi valore intero compreso tra 1 e 2562 giorni.</p></td>
<td><p>60 giorni</p></td>
</tr>
</tbody>
</table>


Allo stesso modo, i valori predefiniti per le impostazioni QoE selezionate sono illustrati in questa tabella:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Proprietà</th>
<th>Descrizione</th>
<th>Valore predefinito</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnableQoE</p></td>
<td><p>Indica se è abilitato il monitoraggio QoE. Se true, tutti i record QoE verranno raccolti e scritti nel database di monitoraggio.</p></td>
<td><p>True</p></td>
</tr>
<tr class="even">
<td><p>EnablePurging</p></td>
<td><p>Indica se i record QoE verranno eliminati periodicamente dal database. Se true, i record verranno eliminati dopo il periodo di tempo specificato dalla proprietà KeepQoEDataForDays. Se false, i record QoE verranno mantenuti indefinitamente.</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>KeepQoEDataForDays</p></td>
<td><p>Indica il numero di giorni in cui i record QoE verranno conservati nel database; tutti i record antecedenti al numero di giorni specificato verranno eliminati automaticamente. Tuttavia, questo problema si verificherà solo se l'eliminazione è stata abilitata.</p>
<p>KeepCallDetailForDays può essere impostato su qualsiasi valore intero compreso tra 1 e 2562 giorni.</p></td>
<td><p>60 giorni</p></td>
</tr>
</tbody>
</table>


Se è necessario modificare queste impostazioni globali, è possibile usare i cmdlet Set-CsCdrConfiguration e Set-CsQoEConfiguration. Ad esempio, questo comando (eseguito da Lync Server Management Shell) Disabilita il monitoraggio CDR nell'ambito globale; Questa operazione viene eseguita impostando la proprietà EnableCDR su false ($False):

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $False

Tieni presente che la disabilitazione del monitoraggio non dissocia l'archivio di monitoraggio dal pool Front-End, né Disinstalla o influisce in altro modo sul database di monitoraggio del backend. Quando si usa Lync Server Management Shell per disabilitare il monitoraggio CDR o QoE, è possibile interrompere temporaneamente il server Lync dalla raccolta e dall'archiviazione dei dati di monitoraggio. Se si vuole riprendere, in questo caso, la raccolta e l'archiviazione dei dati CDR, è sufficiente impostare la proprietà EnableCDR su true ($True):

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

Analogamente, questo comando Disabilita l'eliminazione dei record QoE nell'ambito globale:

    Set-CsQoEConfiguration -Identity "global" -EnablePurging $False

Oltre alle impostazioni globali, le impostazioni delle configurazioni CDR e QoE possono essere assegnate all'ambito del sito. In questo caso è disponibile un'ulteriore flessibilità di gestione per il monitoraggio. ad esempio, un amministratore può abilitare il monitoraggio CDR per il sito Redmond, ma disabilitare il monitoraggio CDR per il sito di Dublino. Per creare nuove impostazioni di configurazione CDR nell'ambito del sito, usare un comando simile al seguente:

    New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

Tieni presente che le impostazioni configurate nell'ambito del sito hanno la precedenza sulle impostazioni configurate nell'ambito globale. Supponiamo ad esempio che il monitoraggio CDR sia abilitato nell'ambito globale, ma disabilitato nell'ambito del sito (per il sito Redmond). Ciò significa che le informazioni relative alla registrazione dei dettagli delle chiamate non verranno archiviate per gli utenti nel sito Redmond. Tuttavia, gli utenti di altri siti, ovvero gli utenti gestiti dalle impostazioni globali anziché dalle impostazioni del sito Redmond, riceveranno le informazioni di registrazione dei dettagli delle chiamate archiviate.

Le nuove impostazioni di configurazione QoE possono essere create nell'ambito del sito usando un comando come questo:

    New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15

Per altre informazioni, digitare i comandi seguenti all'interno di Lync Server Management Shell:

    Get-Help New-CsCdrConfiguration | more
    Get-Help Set-CsCdrConfiguration | more
    Get-Help New-CsQoEConfiguration | more
    Get-Help Set-CsQoEConfiguration | more

</div>

<span> </span>

</div>

</div>

</div>

