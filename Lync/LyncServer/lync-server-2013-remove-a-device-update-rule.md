---
title: 'Lync Server 2013: rimuovere una regola di aggiornamento del dispositivo'
description: 'Lync Server 2013: rimuovere una regola di aggiornamento del dispositivo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a Device Update rule
ms:assetid: ad6e0c6a-cda4-4147-92d5-48bc393ac456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994066(v=OCS.15)
ms:contentKeyID: 51803977
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f0ed7436331377200a5b8719cf32a8195179402
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555782"
---
# <a name="remove-a-device-update-rule-in-lync-server-2013"></a>Rimuovere una regola di aggiornamento del dispositivo in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

La rimozione di una regola di aggiornamento dei dispositivi porta definitivamente fuori dalla coda di aggiornamento del dispositivo.

La rimozione di una regola è diversa dalla disinstallazione di un aggiornamento dai dispositivi della distribuzione o dai dispositivi di test. Per disinstallare un aggiornamento approvato dalla distribuzione, è necessario *ripristinare* la regola di aggiornamento dei dispositivi. Per ulteriori informazioni, vedere [ripristinare una regola di aggiornamento dei dispositivi in Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md). Per disinstallare un aggiornamento che non sono stati approvati dai dispositivi di test, è necessario *reimpostarlo* . Per ulteriori informazioni, vedere [reimpostare una regola di aggiornamento dei dispositivi in Lync Server 2013](lync-server-2013-reset-a-device-update-rule.md).

È possibile rimuovere una regola di aggiornamento dei dispositivi utilizzando il pannello di controllo di Lync Server o Windows PowerShell.

<div>

## <a name="to-remove-device-update-rules-by-using-lync-server-control-panel"></a>Per rimuovere le regole di aggiornamento dei dispositivi tramite il pannello di controllo di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento **Aggiorna dispositivo** .

4.  Nella pagina **aggiornamento dispositivi** eseguire una delle operazioni seguenti:
    
      - Per rimuovere una regola, selezionare la regola che si desidera eliminare.
    
      - Per rimuovere tutte le regole, fare clic sul menu **modifica** e quindi fare clic su **Seleziona tutto**.

5.  Fare clic su **Modifica** e quindi scegliere **Elimina**.

</div>

<div>

## <a name="removing-device-update-rules-by-using-windows-powershell-cmdlets"></a>Rimozione delle regole di aggiornamento dei dispositivi tramite i cmdlet di Windows PowerShell

Le regole di aggiornamento dei dispositivi possono essere rimosse anche utilizzando Windows PowerShell e il cmdlet **Remove-CsDeviceUpdateRule** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-remove-a-single-device-update-rule-from-a-server"></a>Per rimuovere una regola di aggiornamento di un singolo dispositivo da un server

  - Il comando seguente rimuove la regola di aggiornamento dei dispositivi d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 dal server Web su atl-cs-001.litwareinc.com.
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-remove-all-the-device-update-rules-from-a-server"></a>Per rimuovere tutte le regole di aggiornamento dei dispositivi da un server

  - Questo comando rimuove tutte le regole di aggiornamento dei dispositivi dal server Web in atl-cs-001.litwareinc.com.
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Approvazione di una regola di aggiornamento del dispositivo in Lync Server 2013](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

