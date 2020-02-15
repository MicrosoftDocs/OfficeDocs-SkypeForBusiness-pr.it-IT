---
title: "Lync Server 2013: eliminare una raccolta di impostazioni di configurazione per l'aggiornamento dei dispositivi"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a collection of Device Update configuration settings
ms:assetid: 1a649136-34a9-42a7-a5b3-a78bbfe93f36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994019(v=OCS.15)
ms:contentKeyID: 51803928
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 345e1ad4c621ce6330b1b1a34c97664d080d6575
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044068"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a>Eliminare una raccolta di impostazioni di configurazione per l'aggiornamento dei dispositivi in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-20_

È inoltre possibile eliminare le impostazioni di configurazione per l'aggiornamento dei dispositivi utilizzando Windows PowerShell e il cmdlet **Remove-CsdeviceUpdateConfiguration** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

<div>


<div>

## <a name="to-remove-a-specific-collection-of-device-update-configuration-settings"></a>Per rimuovere una raccolta specifica di impostazioni di configurazione per l'aggiornamento dei dispositivi

  - Questo comando consente di eliminare le impostazioni di configurazione di aggiornamento dei dispositivi applicate al sito Redmond:
    
        Remove-CsDeviceUpdateConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-device-update-configuration-settings-applied-to-the-site-scope"></a>Per rimuovere tutte le impostazioni di configurazione dell'aggiornamento dei dispositivi applicate all'ambito del sito

  - Questo comando consente di eliminare tutte le impostazioni di configurazione di aggiornamento dei dispositivi applicate all'ambito del sito:
    
        Get-CsDeviceUpdateConfiguration -Filter "site:*" | Remove-CsDeviceUpdateConfiguration

</div>

<div>

## <a name="to-remove-device-update-configuration-settings-based-on-the-value-of-the-logcleanupinterval-property"></a>Per rimuovere le impostazioni di configurazione dell'aggiornamento dei dispositivi in base al valore della proprietà LogCleanUpInterval

  - Con il comando seguente vengono eliminate tutte le impostazioni di configurazione dell'aggiornamento dei dispositivi in cui l'intervallo di pulizia del registro è maggiore di 10 giorni (10,00:00:00):
    
        Get-CsDeviceUpdateConfiguration | Where-Object {$_.LogCleanUpInterval -gt "10.00:00:00" | Remove-CsDeviceUpdateConfiguration

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

