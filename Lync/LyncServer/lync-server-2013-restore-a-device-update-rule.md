---
title: 'Lync Server 2013: ripristinare una regola di aggiornamento del dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restore a Device Update rule
ms:assetid: ac490baf-c7a0-48d9-8fd0-ba5729489341
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994061(v=OCS.15)
ms:contentKeyID: 51803972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9fc1d493de7126bd9462b0d9b5acf7f8a731035
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144773"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restore-a-device-update-rule-in-lync-server-2013"></a>Ripristinare una regola di aggiornamento del dispositivo in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

Per disinstallare una regola di aggiornamento dei dispositivi dal dispositivo nella distribuzione, ripristinarla. Il ripristino di una regola di aggiornamento dei dispositivi Disinstalla l'aggiornamento e reinstalla la versione precedente di tale regola.

È possibile ripristinare una regola di aggiornamento dei dispositivi utilizzando il pannello di controllo di Lync Server o Windows PowerShell.

<div>

## <a name="to-restore-device-update-rules-by-using-lync-server-control-panel"></a>Per ripristinare le regole di aggiornamento dei dispositivi tramite il pannello di controllo di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento **Aggiorna dispositivo** .

4.  Nella pagina **aggiornamento dispositivi** eseguire una delle operazioni seguenti:
    
      - Per ripristinare una regola, selezionare la regola.
    
      - Per ripristinare tutte le regole, fare clic su **modifica**, quindi fare clic su **Seleziona tutto**.

5.  Fare clic sul menu **azione** e quindi su **Ripristina**.

</div>

<div>

## <a name="restoring-device-update-rules-by-using-windows-powershell-cmdlets"></a>Ripristino delle regole di aggiornamento dei dispositivi tramite i cmdlet di Windows PowerShell

Le regole per gli aggiornamenti dei dispositivi possono essere ripristinate anche utilizzando Windows PowerShell e il cmdlet **Restore-CsDeviceUpdateRule** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.

<div>


> [!NOTE]  
> Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 using Remote PowerShell" at.



</div>

<div>

## <a name="to-restore-a-single-device-update-rule-on-a-server"></a>Per ripristinare una regola di aggiornamento di un singolo dispositivo su un server

  - Il comando seguente ripristina la regola di aggiornamento dei dispositivi d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 sul server Web atl-cs-001.litwareinc.com:
    
        Restore-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-restore-all-the-device-update-rules-on-a-server"></a>Per ripristinare tutte le regole di aggiornamento dei dispositivi in un server

  - Questo comando Ripristina tutte le regole di aggiornamento dei dispositivi sul server Web atl-cs-001.litwareinc.com:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Restore-CsDeviceUpdateRule

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Restore-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

