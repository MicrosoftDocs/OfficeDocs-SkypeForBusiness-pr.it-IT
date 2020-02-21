---
title: Creare o modificare una raccolta di impostazioni di configurazione per l'aggiornamento dei dispositivi
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Device Update configuration settings
ms:assetid: 3e8ce95f-a8c8-417c-b1f7-0f759a567aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994029(v=OCS.15)
ms:contentKeyID: 51803938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1cba65da0e8c1e01c5cf5666b13b98cc2009baf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180103"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a>Creare o modificare una raccolta di impostazioni di configurazione per l'aggiornamento dei dispositivi in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

È possibile creare le impostazioni di configurazione per l'aggiornamento dei dispositivi (solo nell'ambito del sito) utilizzando Windows PowerShell e il cmdlet **New-CsDeviceUpdateConfiguration** e modificarli utilizzando il cmdlet **Set-CsDeviceUpdateConfiguration** . Questi cmdlet possono essere eseguiti da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.

<div>


> [!NOTE]
> Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 using Remote PowerShell" at.



</div>

<div>


<div>

## <a name="to-create-device-update-configuration-settings-that-use-the-default-values"></a>Per creare impostazioni di configurazione per l'aggiornamento dei dispositivi che utilizzano i valori predefiniti

  - Questo comando consente di creare un nuovo set di impostazioni di configurazione per l'aggiornamento dei dispositivi per il sito Redmond:
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond"
    
    Poiché nel comando precedente non sono stati specificati parametri diversi dal parametro Identity obbligatorio, la nuova raccolta di impostazioni di configurazione utilizzerà i valori predefiniti per tutte le proprietà.

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-device-update-configuration-settings"></a>Per modificare un singolo valore di proprietà durante la creazione di impostazioni di configurazione di aggiornamento dispositivi

  - Per creare impostazioni basate su valori di proprietà diversi, è sufficiente includere il parametro appropriato e il valore corrispondente. Ad esempio, per creare una raccolta di impostazioni di configurazione per l'aggiornamento dei dispositivi che, per impostazione predefinita, Elimina i file di registro obsoleti ogni 21 giorni, utilizzare un comando simile al seguente:
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-device-update-configuration-settings"></a>Per modificare più valori di proprietà durante la creazione di impostazioni di configurazione per l'aggiornamento dei dispositivi

  - È possibile modificare più valori di proprietà includendo più parametri. Ad esempio, questo comando consente di impostare l'intervallo di pulizia dei registri su 21 giorni e l'intervallo di incasso dei registri su 30 minuti:
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00" -LogFlushInterval "00:30:00"

</div>

Per informazioni dettagliate sulla modifica delle impostazioni di configurazione dei dispositivi esistenti, vedere l'argomento della Guida relativo al cmdlet [Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15)) . Per informazioni dettagliate sulla creazione di raccolte di impostazioni di configurazione, vedere l'argomento della Guida relativo al cmdlet [New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

