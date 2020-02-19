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
ms.openlocfilehash: 657efcf53b48c0aab2df661ddf142587e02e235e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-lync-server-2013"></a>Eliminare una raccolta esistente di impostazioni di configurazione del trunk SIP in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-22_

Le impostazioni di configurazione dei trunk SIP consentono di definire le funzionalità e la relazione tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un sistema IP-PBX o un servizio Session Border Controller (SBC) nel provider di servizi. Queste impostazioni consentono di specificare quanto segue:

  - Se abilitare il bypass multimediale nei trunk.

  - Le condizioni in base alle quali vengono inviati pacchetti RTCP (Real-Time Control Protocol).

  - Se in ogni trunk è richiesta la crittografia SRTP (Secure Real-Time Protocol).

Quando si installa Microsoft Lync Server 2013, viene creata una raccolta globale di impostazioni di configurazione del trunk SIP. Questa raccolta globale di impostazioni non può essere eliminata. Tuttavia, è possibile utilizzare il pannello di controllo di Lync Server o il cmdlet [Remove-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15)) per "reimpostare" le proprietà della raccolta globale sui rispettivi valori predefiniti. Ad esempio, se la proprietà Enable3pccRefer è stata impostata su true, quando si reimposta la raccolta globale, la proprietà Enable3pccRefer restituirà il valore predefinito false.

Gli amministratori possono inoltre creare impostazioni di configurazione personalizzate per i trunk con ambito sito o servizio (per un gateway PSTN singolo) che possono essere rimosse. Quando si rimuovono le impostazioni personalizzate, tenere presente che:

  - Se si rimuovono le impostazioni con ambito servizio, il trunk SIP gestito da tali impostazioni verrà gestito dalle impostazioni applicate al rispettivo sito, se esistenti. In caso contrario, i trunk verranno gestiti dalla raccolta globale di impostazioni di configurazione dei trunk.

  - Se si rimuovono le impostazioni con ambito sito, i trunk SIP gestiti da tali impostazioni verranno gestiti dalla raccolta globale di impostazioni di configurazione dei trunk.

<div>

## <a name="to-remove-trunk-configuration-settings-with-lync-server-control-panel"></a>Per rimuovere le impostazioni di configurazione del trunk con il pannello di controllo di Lync Server

1.  Nel pannello di controllo di Lync Server, fare clic su **routing vocale** e quindi su **configurazione trunk**.

2.  Nella scheda **Configurazione trunk** selezionare la raccolta di impostazioni di configurazione dei trunk SIP da eliminare, fare clic su **Modifica**, quindi su **Elimina**. Per eliminare più raccolte con una sola operazione, fare clic sulla prima raccolta da eliminare, quindi sulle altre raccolte tenendo premuto il tasto CTRL.

3.  La proprietà **Stato** per la raccolta verrà aggiornata a **Commit non eseguito**. Per eseguire il commit delle modifiche e per eliminare la raccolta, fare clic su **Commit**, quindi su **Salva tutto**.

4.  Nella finestra di dialogo **Impostazioni di configurazione vocale di cui non è stato eseguito il commit** fare clic su **OK**.

5.  Nella finestra di dialogo **Pannello di controllo di Microsoft Lync Server 2013** fare clic su **OK**.

6.  Se si decide di non eliminare più la raccolta, fare clic su **Commit**, quindi su **Annulla tutte le modifiche di cui non è stato eseguito il commit**. Quando viene visualizzata la finestra di dialogo **Pannello di controllo di Microsoft Lync Server 2013**, fare clic su **OK**.

</div>

<div>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>Rimozione delle impostazioni di configurazione del trunk tramite i cmdlet di Windows PowerShell

È possibile eliminare le impostazioni di configurazione del trunk utilizzando Windows PowerShell e il cmdlet **Remove-CsTrunkConfiguration** . È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

<div>

## <a name="to-remove-a-specified-collection-of-settings"></a>Per rimuovere una raccolta specificata di impostazioni

  - Il comando seguente rimuove le impostazioni di configurazione dei trunk applicate al sito di Redmond:
    
        Remove-CsTrunkConfiguration -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a>Per rimuovere tutte le raccolte applicate all'ambito del sito

  - Questo comando rimuove tutte le impostazioni di configurazione dei trunk applicate all'ambito servizio:
    
        Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration

</div>

<div>

## <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a>Per rimuovere tutte le raccolte in cui è abilitato il bypass multimediale

  - Il comando seguente rimuove tutte le impostazioni di configurazione dei trunk in cui è stato abilitato il bypass multimediale:
    
        Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

