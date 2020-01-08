---
title: 'Lync Server 2013: ripristinare una regola di aggiornamento del dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restore a Device Update rule
ms:assetid: ac490baf-c7a0-48d9-8fd0-ba5729489341
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994061(v=OCS.15)
ms:contentKeyID: 51803972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90eeb82e710b6ea65bc32184685497494dbef8d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restore-a-device-update-rule-in-lync-server-2013"></a>Ripristinare una regola di aggiornamento del dispositivo in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

Per disinstallare una regola di aggiornamento del dispositivo dai dispositivi della distribuzione, ripristinarla. Ripristinando una regola di aggiornamento dei dispositivi viene disinstallata l'aggiornamento e viene reinstallata la versione precedente di tale regola.

È possibile ripristinare una regola di aggiornamento dei dispositivi tramite il pannello di controllo di Lync Server o Windows PowerShell.

<div>

## <a name="to-restore-device-update-rules-by-using-lync-server-control-panel"></a>Per ripristinare le regole di aggiornamento dei dispositivi tramite il pannello di controllo di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento **aggiornamento dispositivi** .

4.  Nella pagina **Update Device** eseguire una delle operazioni seguenti:
    
      - Per ripristinare una regola, selezionare la regola.
    
      - Per ripristinare tutte le regole, fare clic su **modifica**e quindi su **Seleziona tutto**.

5.  Fare clic sul menu **azione** e quindi su **Ripristina**.

</div>

<div>

## <a name="restoring-device-update-rules-by-using-windows-powershell-cmdlets"></a>Ripristino delle regole di aggiornamento dei dispositivi tramite i cmdlet di Windows PowerShell

Le regole per gli aggiornamenti dei dispositivi possono essere ripristinate anche tramite Windows PowerShell e il cmdlet **Restore-CsDeviceUpdateRule** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.

<div>


> [!NOTE]  
> Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Lync Server 2010 con Remote PowerShell" at.



</div>

<div>

## <a name="to-restore-a-single-device-update-rule-on-a-server"></a>Per ripristinare una regola di aggiornamento di un singolo dispositivo in un server

  - Il comando seguente ripristina la regola di aggiornamento del dispositivo d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 sul server Web atl-cs-001.litwareinc.com:
    
        Restore-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-restore-all-the-device-update-rules-on-a-server"></a>Per ripristinare tutte le regole di aggiornamento dei dispositivi in un server

  - Questo comando Ripristina tutte le regole di aggiornamento dei dispositivi sul server Web atl-cs-001.litwareinc.com:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Restore-CsDeviceUpdateRule

</div>

Per informazioni dettagliate, vedere l'argomento della Guida relativo al cmdlet [Restore-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

