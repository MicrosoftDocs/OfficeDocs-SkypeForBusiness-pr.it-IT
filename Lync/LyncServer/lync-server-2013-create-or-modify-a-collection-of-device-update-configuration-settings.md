---
title: Creare o modificare una raccolta di impostazioni di configurazione di aggiornamento dei dispositivi
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of Device Update configuration settings
ms:assetid: 3e8ce95f-a8c8-417c-b1f7-0f759a567aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994029(v=OCS.15)
ms:contentKeyID: 51803938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d5b53ff6e876a2c5226b6728e0ebde95d55e7ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a>Creare o modificare una raccolta di impostazioni di configurazione di aggiornamento dei dispositivi in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

Le impostazioni di configurazione per l'aggiornamento dei dispositivi possono essere create (solo nell'ambito del sito) tramite Windows PowerShell e il cmdlet **New-CsDeviceUpdateConfiguration** e modificate tramite il cmdlet **Set-CsDeviceUpdateConfiguration** . Questi cmdlet possono essere eseguiti da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.

<div>


> [!NOTE]
> Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Lync Server 2010 con Remote PowerShell" at.



</div>

<div>


<div>

## <a name="to-create-device-update-configuration-settings-that-use-the-default-values"></a>Per creare impostazioni di configurazione per l'aggiornamento dei dispositivi che usano i valori predefiniti

  - Questo comando crea un nuovo set di impostazioni di configurazione per l'aggiornamento dei dispositivi per il sito Redmond:
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond"
    
    Dato che nel comando precedente non sono stati specificati parametri diversi da quelli di identità obbligatoria, la nuova raccolta di impostazioni di configurazione userà i valori predefiniti per tutte le proprietà.

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-device-update-configuration-settings"></a>Per modificare un valore di proprietà Single durante la creazione di impostazioni di configurazione di aggiornamento dispositivi

  - Per creare impostazioni che usano valori di proprietà diversi, includere semplicemente il parametro e il valore del parametro appropriati. Ad esempio, per creare una raccolta di impostazioni di configurazione di aggiornamento dei dispositivi che, per impostazione predefinita, Elimina i file di log obsoleti ogni 21 giorni, usa un comando come questo:
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-device-update-configuration-settings"></a>Per modificare più valori di proprietà durante la creazione di impostazioni di configurazione di aggiornamento dei dispositivi

  - Più valori di proprietà possono essere modificati includendo più parametri. Questo comando, ad esempio, imposta l'intervallo di pulizia del log su 21 giorni e l'intervallo di svuotamento del log su 30 minuti:
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00" -LogFlushInterval "00:30:00"

</div>

Per informazioni dettagliate sulla modifica delle impostazioni di configurazione dei dispositivi esistenti, vedere l'argomento della Guida relativo al cmdlet [Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg398320(v=OCS.15)) . Per informazioni dettagliate sulla creazione di raccolte di impostazioni di configurazione, vedere l'argomento della Guida relativo al cmdlet [New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425761(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

