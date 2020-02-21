---
title: 'Lync Server 2013: approvazione di una regola di aggiornamento del dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Approve a Device Update rule
ms:assetid: 9dbb1c9a-be0f-4e13-9234-05501ab43ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994053(v=OCS.15)
ms:contentKeyID: 51803964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25c6fad9547e9c738523ac0f460d3e6696d1920a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204427"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="approve-a-device-update-rule-in-lync-server-2013"></a>Approvazione di una regola di aggiornamento del dispositivo in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

Dopo aver importato una regola di aggiornamento dei dispositivi, questa viene installata nei dispositivi di test. Se il testing ha esito positivo e si desidera eseguire l'aggiornamento all'organizzazione, approvarlo utilizzando il pannello di controllo di Lync Server o Windows PowerShell.

<div>

## <a name="to-approve-a-device-update-rule-by-using-lync-server-control-panel"></a>Per approvare una regola di aggiornamento dei dispositivi tramite il pannello di controllo di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella pagina **aggiornamento dispositivi** eseguire una delle operazioni seguenti:
    
      - Per approvare una regola, selezionare la regola.
    
      - Per approvare tutte le regole, fare clic su **modifica**e quindi su **Seleziona tutto**.

4.  Fare clic su **azione**e quindi su **approva**.

</div>

<div>

## <a name="approving-a-device-update-rule-by-using-windows-powershell-cmdlets"></a>Approvazione di una regola di aggiornamento dei dispositivi tramite i cmdlet di Windows PowerShell

È inoltre possibile approvare le regole di aggiornamento dei dispositivi utilizzando Windows PowerShell e il cmdlet **approva-CsDeviceUpdateRule** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.

<div>


> [!NOTE]  
> Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 using Remote PowerShell" at.



</div>

<div>

## <a name="to-approve-a-single-device-update-rule"></a>Per approvare una regola di aggiornamento di un singolo dispositivo

  - Il comando seguente approva la regola di aggiornamento dei dispositivi d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 trovata nel server Web atl-cs-001.litwareinc.com:
    
        Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

</div>

<div>

## <a name="to-approve-multiple-device-update-rules"></a>Per approvare le regole per l'aggiornamento di più dispositivi

  - Questo comando approva tutte le regole di aggiornamento del dispositivo per i dispositivi con marchio Microsoft:
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Approve-CsDeviceUpdateRule

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Approval-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Importare le regole di aggiornamento del dispositivo in Lync Server 2013](lync-server-2013-import-device-update-rules.md)  
[Ripristinare una regola di aggiornamento del dispositivo in Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

