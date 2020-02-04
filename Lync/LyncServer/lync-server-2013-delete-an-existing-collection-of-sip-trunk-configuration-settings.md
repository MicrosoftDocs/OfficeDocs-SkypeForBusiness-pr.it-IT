---
title: Eliminare una raccolta esistente di impostazioni di configurazione del trunk SIP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of SIP trunk configuration settings
ms:assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688024(v=OCS.15)
ms:contentKeyID: 49733614
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0dbb07a11cd96a330d503dc18db9102a7b33ca3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-lync-server-2013"></a>Eliminare una raccolta esistente di impostazioni di configurazione del trunk SIP in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-22_

Le impostazioni di configurazione trunk SIP definiscono la relazione e le funzionalità tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un PBX (IP-Public Branch Exchange) o un SBC (Session Border Controller) presso il provider di servizi. Queste impostazioni eseguono operazioni come specifica:

  - Se il bypass multimediale deve essere abilitato nei trunk.

  - Condizioni in cui vengono inviati i pacchetti RTCP (Real-Time Transport Control Protocol).

  - Indipendentemente dal fatto che sia necessaria o meno la crittografia SRTP (Real-Time Protocol) in ogni trunk.

Quando si installa Microsoft Lync Server 2013, viene creata una raccolta globale di impostazioni di configurazione trunk SIP. Questa raccolta globale di impostazioni non può essere eliminata. Tuttavia, puoi usare il pannello di controllo di Lync Server o il cmdlet [Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15)) per "reimpostare" i valori predefiniti delle proprietà della raccolta globale. Se ad esempio è stata impostata la proprietà Enable3pccRefer su true, quando si reimposta la raccolta globale la proprietà Enable3pccRefer restituirà il valore predefinito false.

Gli amministratori possono anche creare impostazioni di configurazione trunk personalizzate nell'ambito del sito o nell'ambito del servizio (per un singolo gateway PSTN); Queste impostazioni personalizzate possono essere rimosse. Quando si rimuovono queste impostazioni personalizzate, tieni presente quanto segue:

  - Se si rimuovono le impostazioni dell'ambito del servizio, il trunk SIP gestito da tali impostazioni verrà gestito dalle impostazioni applicate al sito, se esistenti. Se le impostazioni del sito non esistono, i trunk verranno quindi gestiti dalla raccolta globale delle impostazioni di configurazione del trunk.

  - Se si rimuovono le impostazioni con ambito sito, i trunk SIP gestiti da tali impostazioni verranno ora gestiti dalla raccolta globale delle impostazioni di configurazione del trunk.

<div>

## <a name="to-remove-trunk-configuration-settings-with-lync-server-control-panel"></a>Per rimuovere le impostazioni di configurazione del trunk con il pannello di controllo di Lync Server

1.  Nel pannello di controllo di Lync Server fare clic su **routing vocale** e quindi su **configurazione trunk**.

2.  Nella scheda **configurazione trunk** selezionare la raccolta di impostazioni di configurazione trunk SIP da eliminare, fare clic su **modifica** e quindi su **Elimina**. Per eliminare più raccolte nella stessa operazione, fare clic sulla prima raccolta da eliminare, quindi tenere premuto CTRL e fare clic su eventuali raccolte aggiuntive che si desidera rimuovere.

3.  La proprietà **state** per la raccolta verrà aggiornata in **UNCOMMITTED**. Per eseguire il commit delle modifiche e per eliminare la raccolta, fare clic su **commit** e quindi su **commit tutti**.

4.  Nella finestra di dialogo **impostazioni di configurazione vocale non impegnata** fare clic su **OK**.

5.  Nella finestra di dialogo **Pannello di controllo di Microsoft Lync Server 2013** fare clic su **OK**.

6.  Se si cambia idea e si decide di non eliminare la raccolta, fare clic su **commit** e quindi su **Annulla tutte le modifiche non salvate**. Quando viene visualizzata la finestra di dialogo **Pannello di controllo di Microsoft Lync Server 2013** , fare clic su **OK**.

</div>

<div>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>Rimozione delle impostazioni di configurazione del trunk tramite i cmdlet di Windows PowerShell

Puoi eliminare le impostazioni di configurazione del trunk usando Windows PowerShell e il cmdlet **Remove-CsTrunkConfiguration** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-remove-a-specified-collection-of-settings"></a>Per rimuovere una raccolta di impostazioni specificata

  - Il comando seguente rimuove le impostazioni di configurazione trunk applicate al sito Redmond:
    
        Remove-CsTrunkConfiguration -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a>Per rimuovere tutte le raccolte applicate all'ambito del sito

  - Questo comando rimuove tutte le impostazioni di configurazione trunk applicate all'ambito del servizio:
    
        Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration

</div>

<div>

## <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a>Per rimuovere tutte le raccolte in cui è abilitato il bypass multimediale

  - Il comando seguente rimuove tutte le impostazioni di configurazione trunk in cui è stato abilitato il bypass multimediale:
    
        Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration

</div>

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

