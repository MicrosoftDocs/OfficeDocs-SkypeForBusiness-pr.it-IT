---
title: 'Lync Server 2013: creare o modificare una raccolta di impostazioni di configurazione CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of CDR configuration settings
ms:assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721878(v=OCS.15)
ms:contentKeyID: 49733812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37ed8be52827f56b14c52f1bddd950ab39883cdf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763358"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-lync-server-2013"></a>Creare o modificare una raccolta di impostazioni di configurazione CDR in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

La registrazione dei dettagli delle chiamate (CDR) consente di tenere traccia dell'uso di elementi come sessioni di messaggistica istantanea peer-to-peer, chiamate telefoniche VoIP (Voice over Internet Protocol) e chiamate in conferenza. Questo dati di utilizzo include informazioni su chi ha chiamato chi, quando ha chiamato, e per quanto tempo ha parlato.

Quando si installa Microsoft Lync Server 2013, viene creata una singola raccolta globale di impostazioni di configurazione CDR. Gli amministratori hanno anche la possibilità di creare impostazioni personalizzate nell'ambito del sito. Ogni volta che vengono usate queste impostazioni con ambito sito, hanno la precedenza sulle impostazioni globali. Ad esempio, se si creano impostazioni con ambito sito per il sito Redmond, le impostazioni (invece delle impostazioni globali) verranno usate per gestire CDR in Redmond.

È possibile creare impostazioni di configurazione CDR usando il pannello di controllo di Lync Server o il cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) . È possibile usare il pannello di controllo di Lync Server o il cmdlet [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) per modificare le impostazioni esistenti. Se si usa il pannello di controllo di Lync Server per creare o modificare le impostazioni, le opzioni seguenti saranno disponibili:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Impostazione dell'interfaccia utente</th>
<th>Parametro di PowerShell</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nome</p></td>
<td><p>Identity</p></td>
<td><p>Identificatore univoco per le impostazioni di configurazione CDR da creare. Queste impostazioni possono essere create solo nell'ambito del sito.</p></td>
</tr>
<tr class="even">
<td><p>Abilitare il monitoraggio di CDRs</p></td>
<td><p>EnableCDR</p></td>
<td><p>Indica se CDR è abilitato o meno.</p></td>
</tr>
<tr class="odd">
<td><p>Abilitare l'eliminazione di CDRs</p></td>
<td><p>EnablePurging</p></td>
<td><p>Indica se i record CDR verranno eliminati periodicamente dal database CDR.</p></td>
</tr>
<tr class="even">
<td><p>Mantieni CDRs per la durata massima (giorni)</p></td>
<td><p>KeepCallDetailForDays</p></td>
<td><p>Indica il numero di giorni in cui i record CDR verranno conservati nel database CDR. Tutti i record antecedenti al numero di giorni specificato verranno eliminati automaticamente. Tieni presente che l'eliminazione verrà eseguita solo se l'eliminazione è stata abilitata.</p></td>
</tr>
<tr class="odd">
<td><p>Mantieni i dati del report degli errori per la durata massima (giorni)</p></td>
<td><p>KeepErrorReportForDays</p></td>
<td><p>Indica il numero di giorni in cui vengono mantenuti i report di errore CDR. Tutti i report antecedenti al numero di giorni specificato verranno eliminati automaticamente. I report di errore CDR sono report di diagnostica caricati dalle applicazioni client.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> I cmdlet New-CsCdrConfiguration e Set-CsCdrConfiguration includono opzioni aggiuntive non disponibili nel pannello di controllo di Lync Server. Per altre informazioni, vedere gli argomenti della Guida <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> e <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Set-CsCdrConfiguration</A> .



</div>

<div>

## <a name="to-create-cdr-configuration-settings-by-using-lync-server-control-panel"></a>Per creare impostazioni di configurazione CDR tramite il pannello di controllo di Lync Server

1.  Nel pannello di controllo di Lync Server fare clic su **monitoraggio e archiviazione**.

2.  Nella scheda **registrazione dettagli chiamata** fare clic su **nuovo**.

3.  Nella finestra di dialogo **Seleziona sito** selezionare il sito in cui devono essere create le nuove impostazioni di configurazione. Se la finestra di dialogo è vuota, significa che a tutti i siti è già stata assegnata una raccolta di impostazioni di configurazione CDR. Ogni sito è limitato a una singola raccolta di questo tipo. In questo caso, è possibile eliminare e ricreare le impostazioni oppure semplicemente modificare le impostazioni esistenti.

4.  Nella finestra di dialogo **nuova impostazione registrazione dettagli chiamata (CDR)** effettuare le selezioni desiderate e quindi fare clic su **commit**.

</div>

<div>

## <a name="to-modify-existing-cdr-configuration-settings-by-using-lync-server-control-panel"></a>Per modificare le impostazioni di configurazione CDR esistenti tramite il pannello di controllo di Lync Server

1.  Nel pannello di controllo di Lync Server fare clic su **monitoraggio e archiviazione**.

2.  Fare doppio clic sulla raccolta di impostazioni da modificare oppure selezionare la raccolta, fare clic su **modifica**e quindi su **Mostra dettagli**. Tieni presente che puoi modificare solo una singola raccolta alla volta. Per apportare le stesse modifiche a più raccolte, usare invece Lync Server Management Shell.

3.  Nella finestra di dialogo **Modifica impostazione registrazione dettagli chiamata (CDR)** effettuare le selezioni desiderate e quindi fare clic su **commit**.

</div>

<div>

## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Creazione di impostazioni di configurazione CDR con i cmdlet di Windows PowerShell

È possibile creare impostazioni di configurazione CDR anche tramite Windows PowerShell e il cmdlet **New-CsCdrConfiguration** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>Per creare una nuova raccolta di impostazioni di configurazione CDR

  - Questo comando crea una nuova raccolta di impostazioni di configurazione CDR applicate al sito Redmond:
    
        New-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>Per creare una raccolta di impostazioni di configurazione CDR che disabilitano la registrazione dei dettagli delle chiamate

  - Poiché non sono stati specificati parametri (ad eccezione del parametro di identità obbligatorio) nel comando precedente, la nuova raccolta di impostazioni di configurazione utilizzerà i valori predefiniti per tutte le relative proprietà. Per creare impostazioni che usano valori di proprietà diversi, includere semplicemente il parametro e il valore del parametro appropriati. Ad esempio, per creare una raccolta di impostazioni di configurazione dei dettagli delle chiamate che, per impostazione predefinita, Consenti Disabilita registrazione dettagli chiamata usa un comando simile al seguente:
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>Per specificare più valori di proprietà quando si crea una nuova raccolta di impostazioni di configurazione CDR

  - Puoi modificare più valori di proprietà includendo più parametri. Ad esempio, questo comando Configura le nuove impostazioni per conservare i record dei dettagli delle chiamate per 30 giorni e i report degli errori per 90 giorni:
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

</div>

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

