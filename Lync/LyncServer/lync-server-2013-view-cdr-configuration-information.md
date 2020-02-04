---
title: 'Lync Server 2013: visualizzare le informazioni sulla configurazione di CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View CDR configuration information
ms:assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688096(v=OCS.15)
ms:contentKeyID: 49733695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f13bbc63d65786823ae49895358216a903878192
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-cdr-configuration-information-in-lync-server-2013"></a>Visualizzare le informazioni di configurazione CDR in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

La registrazione dei dettagli delle chiamate (CDR) consente di tenere traccia dell'uso di elementi come sessioni di messaggistica istantanea peer-to-peer, chiamate telefoniche VoIP (Voice over Internet Protocol) e chiamate in conferenza. Questo dati di utilizzo include informazioni su chi ha chiamato chi, quando ha chiamato, e per quanto tempo ha parlato.

Quando si installa Microsoft Lync Server 2013, viene creata una singola raccolta globale di impostazioni di configurazione CDR. Gli amministratori hanno anche la possibilità di creare raccolte di impostazioni personalizzate che possono essere applicate a singoli siti. Per visualizzare le impostazioni di configurazione CDR in uso nell'organizzazione, è possibile usare il pannello di controllo di Lync Server o il cmdlet [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) .

<div>

## <a name="to-view-cdr-configuration-information-by-using-lync-server-control-panel"></a>Per visualizzare le informazioni di configurazione CDR tramite il pannello di controllo di Lync Server

1.  Nel pannello di controllo di Lync Server fare clic su **monitoraggio e archiviazione**.

2.  Nella scheda **registrazione dettagli chiamata** verrà visualizzato un elenco di tutte le impostazioni di configurazione CDR. per ogni raccolta di impostazioni verrà visualizzato il **nome**della raccolta; indipendentemente dal fatto che CDR sia stato abilitato (la proprietà **CDR** ); e indipendentemente dal fatto che l'eliminazione sia stata abilitata (la proprietà **cancellazione CDR** ). Per visualizzare informazioni dettagliate su una raccolta, fare doppio clic sulla raccolta oppure selezionare la raccolta appropriata, fare clic su **modifica**e quindi su **Mostra dettagli**. Tieni presente che puoi visualizzare solo informazioni dettagliate per una singola raccolta di impostazioni di configurazione CDR alla volta.

</div>

<div>

## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni di configurazione CDR tramite i cmdlet di Windows PowerShell

Per visualizzare le impostazioni di configurazione CDR, è possibile usare Windows PowerShell e il cmdlet Get-CsCdrConfiguration. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-view-cdr-configuration-information"></a>Per visualizzare le informazioni sulla configurazione CDR

  - Per visualizzare informazioni su tutte le impostazioni di configurazione CDR, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:
    
        Get-CsCdrConfiguration
    
    Questo restituirà informazioni simili alla seguente:
    
        Identity               : Global
        EnableCDR              : True
        EnablePurging          : True
        KeepCallDetailForDays  : 90
        KeepErrorReportForDays : 60
        PurgeHourOfDay         : 2

</div>

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

