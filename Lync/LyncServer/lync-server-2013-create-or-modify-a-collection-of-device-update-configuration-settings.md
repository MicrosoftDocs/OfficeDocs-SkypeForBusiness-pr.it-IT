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
ms.openlocfilehash: a3f58e67a0d1fc8f6b01fecfbab7c7ff7dd8f31d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035602"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="0b3d1-102">Creare o modificare una raccolta di impostazioni di configurazione per l'aggiornamento dei dispositivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b3d1-102">Create or modify a collection of Device Update configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b3d1-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="0b3d1-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="0b3d1-104">È possibile creare le impostazioni di configurazione per l'aggiornamento dei dispositivi (solo nell'ambito del sito) utilizzando Windows PowerShell e il cmdlet **New-CsDeviceUpdateConfiguration** e modificarli utilizzando il cmdlet **Set-CsDeviceUpdateConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="0b3d1-104">Device update configuration settings can be created (at the site scope only) by using Windows PowerShell and the **New-CsDeviceUpdateConfiguration** cmdlet and modified by using the **Set-CsDeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="0b3d1-105">Questi cmdlet possono essere eseguiti da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0b3d1-105">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="0b3d1-106">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="0b3d1-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="to-create-device-update-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="0b3d1-107">Per creare impostazioni di configurazione per l'aggiornamento dei dispositivi che utilizzano i valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="0b3d1-107">To create device update configuration settings that use the default values</span></span>

  - <span data-ttu-id="0b3d1-108">Questo comando consente di creare un nuovo set di impostazioni di configurazione per l'aggiornamento dei dispositivi per il sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="0b3d1-108">This command creates a new set of device update configuration settings for the Redmond site:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="0b3d1-109">Poiché nel comando precedente non sono stati specificati parametri diversi dal parametro Identity obbligatorio, la nuova raccolta di impostazioni di configurazione utilizzerà i valori predefiniti per tutte le proprietà.</span><span class="sxs-lookup"><span data-stu-id="0b3d1-109">Because no parameters other than the mandatory Identity parameter were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-device-update-configuration-settings"></a><span data-ttu-id="0b3d1-110">Per modificare un singolo valore di proprietà durante la creazione di impostazioni di configurazione di aggiornamento dispositivi</span><span class="sxs-lookup"><span data-stu-id="0b3d1-110">To change a single property value when creating device update configuration settings</span></span>

  - <span data-ttu-id="0b3d1-111">Per creare impostazioni basate su valori di proprietà diversi, è sufficiente includere il parametro appropriato e il valore corrispondente.</span><span class="sxs-lookup"><span data-stu-id="0b3d1-111">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="0b3d1-112">Ad esempio, per creare una raccolta di impostazioni di configurazione per l'aggiornamento dei dispositivi che, per impostazione predefinita, Elimina i file di registro obsoleti ogni 21 giorni, utilizzare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="0b3d1-112">For example, to create a collection of device update configuration settings that, by default, deletes old log files every 21 days, use a command like this one:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-device-update-configuration-settings"></a><span data-ttu-id="0b3d1-113">Per modificare più valori di proprietà durante la creazione di impostazioni di configurazione per l'aggiornamento dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="0b3d1-113">To change multiple property values when creating device update configuration settings</span></span>

  - <span data-ttu-id="0b3d1-114">È possibile modificare più valori di proprietà includendo più parametri.</span><span class="sxs-lookup"><span data-stu-id="0b3d1-114">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="0b3d1-115">Ad esempio, questo comando consente di impostare l'intervallo di pulizia dei registri su 21 giorni e l'intervallo di incasso dei registri su 30 minuti:</span><span class="sxs-lookup"><span data-stu-id="0b3d1-115">For example, this command sets the log cleanup interval to 21 days and the log flush interval to 30 minutes:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00" -LogFlushInterval "00:30:00"

</div>

<span data-ttu-id="0b3d1-116">Per informazioni dettagliate sulla modifica delle impostazioni di configurazione dei dispositivi esistenti, vedere l'argomento della Guida relativo al cmdlet [Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="0b3d1-116">For details about modifying existing device configuration settings, see the Help topic for the [Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="0b3d1-117">Per informazioni dettagliate sulla creazione di raccolte di impostazioni di configurazione, vedere l'argomento della Guida relativo al cmdlet [New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="0b3d1-117">For details about creating collections of configuration settings, see the Help topic for the [New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

