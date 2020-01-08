---
title: 'Lync Server 2013: rimuovere una regola di aggiornamento del dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remove a Device Update rule
ms:assetid: ad6e0c6a-cda4-4147-92d5-48bc393ac456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994066(v=OCS.15)
ms:contentKeyID: 51803977
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3776fe2b80e301e02c099f3c6154afc1c382d0d7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981887"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-device-update-rule-in-lync-server-2013"></a>Rimuovere una regola di aggiornamento del dispositivo in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

La rimozione di una regola di aggiornamento dei dispositivi Elimina definitivamente la coda di aggiornamento del dispositivo.

La rimozione di una regola è diversa da quella di disinstallare un aggiornamento dai dispositivi della distribuzione o dai dispositivi di test. Per disinstallare un aggiornamento approvato dalla distribuzione, è possibile *ripristinare* la regola di aggiornamento del dispositivo. Per informazioni dettagliate, vedere [ripristinare una regola di aggiornamento dei dispositivi in Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md). Per disinstallare un aggiornamento non approvato dai dispositivi di test, è possibile *reimpostarlo* . Per informazioni dettagliate, vedere [reimpostare una regola di aggiornamento dei dispositivi in Lync Server 2013](lync-server-2013-reset-a-device-update-rule.md).

È possibile rimuovere una regola di aggiornamento del dispositivo usando il pannello di controllo di Lync Server o Windows PowerShell.

<div>

## <a name="to-remove-device-update-rules-by-using-lync-server-control-panel"></a>Per rimuovere le regole di aggiornamento dei dispositivi tramite il pannello di controllo di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento **aggiornamento dispositivi** .

4.  Nella pagina **Update Device** eseguire una delle operazioni seguenti:
    
      - Per rimuovere una regola, selezionare la regola che si vuole eliminare.
    
      - Per rimuovere tutte le regole, fare clic sul menu **modifica** e quindi su **Seleziona tutto**.

5.  Fare clic su **modifica**e quindi su **Elimina**.

</div>

<div>

## <a name="removing-device-update-rules-by-using-windows-powershell-cmdlets"></a>Rimozione delle regole di aggiornamento dei dispositivi con i cmdlet di Windows PowerShell

Le regole di aggiornamento dei dispositivi possono essere rimosse anche tramite Windows PowerShell e il cmdlet **Remove-CsDeviceUpdateRule** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-remove-a-single-device-update-rule-from-a-server"></a>Per rimuovere una regola di aggiornamento di un singolo dispositivo da un server

  - Il comando seguente rimuove la regola di aggiornamento del dispositivo d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 dal server Web in atl-cs-001.litwareinc.com.
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-remove-all-the-device-update-rules-from-a-server"></a>Per rimuovere tutte le regole di aggiornamento dei dispositivi da un server

  - Questo comando rimuove tutte le regole di aggiornamento del dispositivo dal server Web in atl-cs-001.litwareinc.com.
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

</div>

Per informazioni dettagliate, vedere l'argomento della Guida relativo al cmdlet [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Approvare una regola di aggiornamento del dispositivo in Lync Server 2013](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

