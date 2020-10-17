---
title: "Lync Server 2013: eliminare una raccolta di impostazioni di configurazione per l'aggiornamento dei dispositivi"
description: "Lync Server 2013: eliminare una raccolta di impostazioni di configurazione per l'aggiornamento dei dispositivi."
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
ms.openlocfilehash: b3a03227869f68a52a30ea94db33bfb954b7e122
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566652"
---
# <a name="delete-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="ef9c2-103">Eliminare una raccolta di impostazioni di configurazione per l'aggiornamento dei dispositivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef9c2-103">Delete a collection of Device Update configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef9c2-104">_**Ultimo argomento modificato:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="ef9c2-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="ef9c2-105">È inoltre possibile eliminare le impostazioni di configurazione per l'aggiornamento dei dispositivi utilizzando Windows PowerShell e il cmdlet **Remove-CsdeviceUpdateConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="ef9c2-105">Device update configuration settings can also be deleted by using Windows PowerShell and the **Remove-CsdeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="ef9c2-106">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ef9c2-106">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ef9c2-107">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="ef9c2-107">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="to-remove-a-specific-collection-of-device-update-configuration-settings"></a><span data-ttu-id="ef9c2-108">Per rimuovere una raccolta specifica di impostazioni di configurazione per l'aggiornamento dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="ef9c2-108">To remove a specific collection of device update configuration settings</span></span>

  - <span data-ttu-id="ef9c2-109">Questo comando consente di eliminare le impostazioni di configurazione di aggiornamento dei dispositivi applicate al sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="ef9c2-109">This command deletes the device update configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsDeviceUpdateConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-device-update-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="ef9c2-110">Per rimuovere tutte le impostazioni di configurazione dell'aggiornamento dei dispositivi applicate all'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="ef9c2-110">To remove all the device update configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="ef9c2-111">Questo comando consente di eliminare tutte le impostazioni di configurazione di aggiornamento dei dispositivi applicate all'ambito del sito:</span><span class="sxs-lookup"><span data-stu-id="ef9c2-111">This command deletes all the device update configuration settings applied to the site scope:</span></span>
    
        Get-CsDeviceUpdateConfiguration -Filter "site:*" | Remove-CsDeviceUpdateConfiguration

</div>

<div>

## <a name="to-remove-device-update-configuration-settings-based-on-the-value-of-the-logcleanupinterval-property"></a><span data-ttu-id="ef9c2-112">Per rimuovere le impostazioni di configurazione dell'aggiornamento dei dispositivi in base al valore della proprietà LogCleanUpInterval</span><span class="sxs-lookup"><span data-stu-id="ef9c2-112">To remove device update configuration settings based on the value of the LogCleanUpInterval property</span></span>

  - <span data-ttu-id="ef9c2-113">Con il comando seguente vengono eliminate tutte le impostazioni di configurazione dell'aggiornamento dei dispositivi in cui l'intervallo di pulizia del registro è maggiore di 10 giorni (10,00:00:00):</span><span class="sxs-lookup"><span data-stu-id="ef9c2-113">The following command deletes all the device update configuration settings where the log cleanup interval is greater than 10 days (10.00:00:00):</span></span>
    
        Get-CsDeviceUpdateConfiguration | Where-Object {$_.LogCleanUpInterval -gt "10.00:00:00" | Remove-CsDeviceUpdateConfiguration

</div>

<span data-ttu-id="ef9c2-114">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="ef9c2-114">For details, see the Help topic for the [Remove-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

