---
title: 'Lync Server 2013: Visualizzare le impostazioni di configurazione di Aggiornamento dispositivi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Device Update configuration settings
ms:assetid: aa6a70a9-bd77-4606-b797-ea6a3bab9cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994059(v=OCS.15)
ms:contentKeyID: 51803970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01edeb2d40fae7b82ac35fb5561a1332f67c9e11
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731096"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-device-update-configuration-settings-in-lync-server-2013"></a>Visualizzare le impostazioni di configurazione di Aggiornamento dispositivi in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-20_

Per visualizzare le impostazioni di configurazione del servizio di aggiornamento del dispositivo, è possibile usare Lync Server Management Shell e il cmdlet **Get-CsDeviceUpdateConfiguration** , che è possibile eseguire da lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell

<div>


> [!NOTE]  
> Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Lync Server 2010 con Remote PowerShell" at.



</div>

<div>


<div>


  - Per visualizzare informazioni su tutte le route vocali, digitare il comando seguente in Lync Server Management Shell e premere INVIO:
    
        Get-CsDeviceUpdateConfiguration
    
    Questo comando restituisce informazioni simili a quelle seguenti:
    
        Identity               : Global
        ValidLogFileTypes      : {Watson, Config, Diaglog, CELog}
        ValidLogFileExtensions : {.dmp, .clg, .clg1, .clg2...}
        MaxLogFileSize         : 1024000
        MaxLogCacheLimit       : 512000
        LogCleanUpInterval     : 10.00:00:00
        LogFlushInterval       : 00:05:00
        LogCleanUpTimeOfDay    :

</div>

Per informazioni dettagliate su questo cmdlet, vedere l'argomento della guida su [Get-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateConfiguration).

</div>

</div>

<span> </span>

</div>

</div>

</div>

