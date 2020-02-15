---
title: 'Lync Server 2013: eliminare i file di registro degli aggiornamenti dei dispositivi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete Device Update log files
ms:assetid: 58d4097f-5bbf-4824-a04d-2a6555cd93c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994039(v=OCS.15)
ms:contentKeyID: 51803949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f5b8ed6d087bb7b80ba93aead7c3ab530c82000
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048487"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-device-update-log-files-in-lync-server-2013"></a>Eliminare i file di registro degli aggiornamenti dei dispositivi in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

Il servizio Web aggiornamento dispositivi conserva una vasta raccolta di file di registro. Questo insieme include sia i registri di controllo eseguiti dal servizio stesso sia i file di log caricati dai dispositivi client. Per impedire il riempimento del server con i registri del servizio Web aggiornamento dispositivi, è probabile che si desideri cancellarlo dai file di registro che sono stati in circolazione per un determinato numero di giorni. Impostare questo numero di giorni in base all'attività di aggiornamento e al numero di dispositivi client nell'organizzazione e utilizzando il pannello di controllo di Lync Server o Lync Server Management Shell.

<div>

## <a name="to-clear-the-device-update-log-by-using-lync-server-control-panel"></a>Per cancellare il log degli aggiornamenti del dispositivo utilizzando il pannello di controllo di Lync Server

1.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Sulla barra di spostamento sinistra fare clic su **client**e quindi su **Configurazione log dispositivo**.

3.  Nella pagina **Configurazione log dispositivo** fare doppio clic sulla configurazione che si desidera modificare.

4.  Nella finestra di dialogo **Modifica impostazione log** , in **numero di giorni per mantenere i file di registro (1-365)**, specificare un numero di giorni.

5.  Fare clic su **Commit**. Vengono eliminati tutti i file presenti nel server per un numero di giorni maggiore di quello specificato. Questa impostazione si applica a questa configurazione fino a quando non viene modificata.

</div>

<div>

## <a name="clearing-the-device-update-log-by-using-the-windows-powershell-cmdlets"></a>Cancellazione del log degli aggiornamenti del dispositivo tramite i cmdlet di Windows PowerShell

Per cancellare i log degli aggiornamenti dei dispositivi, è possibile utilizzare Windows PowerShell e il cmdlet **Clear-CsDeviceUpdateLog** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.

<div>


> [!NOTE]  
> Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 using Remote PowerShell" at.



</div>

<div>

## <a name="to-clear-device-update-logs-on-one-server"></a>Per cancellare i log degli aggiornamenti dei dispositivi su un server

  - Il comando seguente rimuove il log degli aggiornamenti del dispositivo sul server Web atl-cs-001.litwareinc.com. Tutte le voci di registro risalenti a più di 10 giorni prima (il valore specificato dal parametro DaysBack) verranno rimosse dal registro.
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

</div>

<div>

## <a name="to-clear-all-device-update-logs"></a>Per cancellare tutti i log degli aggiornamenti dei dispositivi

  - Questo comando consente di rimuovere le voci obsolete (in questo esempio, le voci con più di 10 giorni) da tutti i log degli aggiornamenti dei dispositivi attualmente in uso nell'organizzazione.
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

