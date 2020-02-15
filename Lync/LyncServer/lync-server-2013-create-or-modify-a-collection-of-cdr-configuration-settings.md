---
title: 'Lync Server 2013: creare o modificare una raccolta di impostazioni di configurazione di registrazione dettagli chiamata'
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
ms.openlocfilehash: 234225364c8701432271c2cf5a48c9bb6d403103
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035632"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-lync-server-2013"></a>Creare o modificare una raccolta di impostazioni di configurazione di registrazione dettagli chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

La registrazione dettagli chiamata consente di tenere traccia dell'utilizzo di elementi quali le sessioni di messaggistica istantanea peer-to-peer, le chiamate telefoniche VoIP (Voice over Internet Protocol) e le conferenze telefoniche. Questi dati relativi all'utilizzo includono informazioni sull'utente chiamante e sull'utente chiamato, sulla data della chiamata e sulla durata della conversazione.

Quando si installa Microsoft Lync Server 2013, viene creata un'unica raccolta globale di impostazioni di configurazione di registrazione dettagli chiamata. Gli amministratori hanno inoltre la possibilità di creare impostazioni personalizzato con ambito sito. Ogni volta che vengono utilizzate tali impostazioni con ambito sito, queste avranno la precedenza rispetto alle impostazioni globali. Ad esempio, se si creano impostazioni con ambito sito per il sito Redmond, tali impostazioni (anziché le impostazioni globali) verranno utilizzate per gestire la registrazione dettagli chiamata in Redmond.

È possibile creare impostazioni di configurazione di registrazione dettagli chiamata utilizzando il pannello di controllo di Lync Server o il cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) . È possibile utilizzare il pannello di controllo di Lync Server o il cmdlet [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) per modificare le impostazioni esistenti. Se si utilizza il pannello di controllo di Lync Server per creare o modificare le impostazioni, saranno disponibili le opzioni seguenti:


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
<td><p>Identità</p></td>
<td><p>Identificatore univoco delle impostazioni di configurazione di registrazione dettagli chiamata che si desidera creare. Queste impostazioni possono essere create solo nell'ambito del sito.</p></td>
</tr>
<tr class="even">
<td><p>Abilita monitoraggio registrazioni dettagli chiamata</p></td>
<td><p>EnableCDR</p></td>
<td><p>Indica se la registrazione dettagli chiamata è abilitata o meno.</p></td>
</tr>
<tr class="odd">
<td><p>Abilita eliminazione registrazioni dettagli chiamata</p></td>
<td><p>EnablePurging</p></td>
<td><p>Indica se le registrazioni dettagli chiamata saranno eliminate periodicamente dal relativo database.</p></td>
</tr>
<tr class="even">
<td><p>Mantieni registrazioni dettagli chiamata per durata massima (giorni)</p></td>
<td><p>KeepCallDetailForDays</p></td>
<td><p>Indica per quanti giorni le registrazioni dettagli chiamata verranno mantenute nel relativo database. Le eventuali registrazioni antecedenti al numero di giorni specificato verranno eliminate automaticamente. Si noti che questa operazione verrà eseguita soltanto se è stata abilitata l'eliminazione.</p></td>
</tr>
<tr class="odd">
<td><p>Mantieni dati delle segnalazioni errori per durata massima (giorni)</p></td>
<td><p>KeepErrorReportForDays</p></td>
<td><p>Indica per quanti giorni verranno mantenuti i rapporti sugli errori di registrazione dettagli chiamata. Gli eventuali rapporti antecedenti al numero di giorni specificato verranno eliminati automaticamente. I rapporti sugli errori di registrazione dettagli chiamata sono rapporti di diagnostica caricati da applicazioni client.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> I cmdlet New-CsCdrConfiguration e Set-CsCdrConfiguration includono opzioni aggiuntive non disponibili nel pannello di controllo di Lync Server. Per ulteriori informazioni, vedere gli argomenti della Guida di <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> e <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Set-CsCdrConfiguration</A> .



</div>

<div>

## <a name="to-create-cdr-configuration-settings-by-using-lync-server-control-panel"></a>Per creare le impostazioni di configurazione di registrazione dettagli chiamata utilizzando il pannello di controllo di Lync Server

1.  Nel pannello di controllo di Lync Server, fare clic su **monitoraggio e archiviazione**.

2.  Nella scheda **registrazione dettagli chiamata** fare clic su **nuovo**.

3.  Nella finestra di dialogo **Seleziona un sito** selezionare il sito in cui devono essere create le nuove impostazioni di configurazione. Se la finestra di dialogo è vuota, è stata già assegnata una raccolta di impostazioni di configurazione di registrazione dettagli chiamata a tutti i siti. Ogni sito è limitato a una sola raccolta di questo tipo. In tal caso, è possibile eliminare e quindi ricreare le impostazioni oppure modificare semplicemente le impostazioni esistenti.

4.  Nella finestra di dialogo **Nuova impostazione di registrazione dettagli chiamata** selezionare le opzioni desiderate e quindi fare clic su **Commit**.

</div>

<div>

## <a name="to-modify-existing-cdr-configuration-settings-by-using-lync-server-control-panel"></a>Per modificare le impostazioni di configurazione di registrazione dettagli chiamata esistenti utilizzando il pannello di controllo di Lync Server

1.  Nel pannello di controllo di Lync Server, fare clic su **monitoraggio e archiviazione**.

2.  Fare doppio clic sulla raccolta di impostazioni da modificare oppure selezionare la raccolta, fare clic su **modifica**e quindi su **Mostra dettagli**. Si noti che è possibile modificare solo una singola raccolta alla volta. Per apportare le stesse modifiche a più insiemi, utilizzare invece Lync Server Management Shell.

3.  Nella finestra di dialogo **Modifica impostazione di registrazione dettagli chiamata** selezionare le opzioni desiderate e quindi fare clic su **Commit**.

</div>

<div>

## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Creazione delle impostazioni di configurazione di registrazione dettagli chiamata tramite i cmdlet di Windows PowerShell

È possibile creare impostazioni di configurazione di registrazione dettagli chiamata anche utilizzando Windows PowerShell e il cmdlet **New-CsCdrConfiguration** . È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

<div>

## <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>Per creare una nuova raccolta di impostazioni di configurazione di registrazione dettagli chiamata

  - Il comando seguente crea una nuova raccolta di impostazioni di configurazione di registrazione dettagli chiamata applicate al sito Redmond:
    
        New-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>Per creare una raccolta di impostazioni di configurazione di registrazione dettagli chiamata che disabilitano la registrazione dettagli chiamata

  - Poiché nel comando precedente non sono stati specificati parametri, eccetto il parametro obbligatorio Identity, la nuova raccolta di impostazioni di configurazione utilizzerà i valori predefiniti per le relative proprietà. Per creare impostazioni basate su valori di proprietà diversi, è sufficiente includere il parametro appropriato e il valore corrispondente. Per creare ad esempio una raccolta di impostazioni di configurazione di registrazione dettagli chiamata che consentano per impostazione predefinita di disabilitare la registrazione dettagli chiamata, utilizzare un comando simile al seguente:
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>Per specificare più valori di proprietà quando si crea una nuova raccolta di impostazioni di configurazione di registrazione dettagli chiamata

  - È possibile modificare più valori di proprietà includendo più parametri. Il comando seguente ad esempio configura le nuove impostazioni in modo da mantenere le registrazioni dettagli chiamata per 30 giorni e i rapporti sugli errori per 90 giorni:
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

