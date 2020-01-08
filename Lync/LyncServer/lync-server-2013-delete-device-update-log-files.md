---
title: 'Lync Server 2013: eliminare i file di log degli aggiornamenti dei dispositivi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete Device Update log files
ms:assetid: 58d4097f-5bbf-4824-a04d-2a6555cd93c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994039(v=OCS.15)
ms:contentKeyID: 51803949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99fb9e6109c6f27e2985de18c2fcdf804dd184c7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-device-update-log-files-in-lync-server-2013"></a>Eliminare i file di log di aggiornamento dei dispositivi in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

Il servizio Web Update del dispositivo mantiene una vasta raccolta di file di log. Questa raccolta include sia i log di controllo eseguiti dal servizio stesso che i file di log caricati dai dispositivi client. Per evitare che il server venga compilato con i registri del servizio Web Update del dispositivo, è probabile che sia necessario cancellarlo dai file di log che si trovano in giro per un determinato numero di giorni. Impostare questo numero di giorni in base all'attività di aggiornamento e al numero di dispositivi client nell'organizzazione e tramite il pannello di controllo di Lync Server o Lync Server Management Shell.

<div>

## <a name="to-clear-the-device-update-log-by-using-lync-server-control-panel"></a>Per cancellare il log degli aggiornamenti del dispositivo usando il pannello di controllo di Lync Server

1.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Sulla barra di spostamento sinistra fare clic su **client**e quindi su **Configurazione log dei dispositivi**.

3.  Nella pagina **Configurazione log dispositivo** fare doppio clic sulla configurazione che si vuole modificare.

4.  Nella finestra di dialogo **Modifica impostazioni log** , in **numero di giorni per conservare i file di log (1-365)**, specificare un numero di giorni.

5.  Fare clic su **Commit**. Tutti i file che sono stati nel server per un numero maggiore di quello specificato del giorno vengono eliminati. Questa impostazione verrà applicata a questa configurazione fino a quando non la modifichi.

</div>

<div>

## <a name="clearing-the-device-update-log-by-using-the-windows-powershell-cmdlets"></a>Cancellazione del log di aggiornamento del dispositivo con i cmdlet di Windows PowerShell

È possibile cancellare i registri di aggiornamento dei dispositivi usando Windows PowerShell e il cmdlet **Clear-CsDeviceUpdateLog** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.

<div>


> [!NOTE]  
> Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Lync Server 2010 con Remote PowerShell" at.



</div>

<div>

## <a name="to-clear-device-update-logs-on-one-server"></a>Per cancellare i registri di aggiornamento dei dispositivi in un server

  - Il comando seguente cancella il log di aggiornamento del dispositivo sul server Web atl-cs-001.litwareinc.com. Tutte le voci di log che superano i 10 giorni (il valore specificato dal parametro DaysBack) verranno rimosse dal log.
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

</div>

<div>

## <a name="to-clear-all-device-update-logs"></a>Per cancellare tutti i registri di aggiornamento dei dispositivi

  - Questo comando rimuove le voci obsolete (in questo esempio, le voci che superano i 10 giorni) da tutti i registri di aggiornamento dei dispositivi attualmente in uso nell'organizzazione.
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

</div>

Per informazioni dettagliate, vedere l'argomento della Guida relativo al cmdlet [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

