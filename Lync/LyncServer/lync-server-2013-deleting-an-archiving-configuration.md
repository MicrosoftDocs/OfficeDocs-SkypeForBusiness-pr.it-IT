---
title: 'Lync Server 2013: eliminazione di una configurazione di archiviazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an Archiving configuration
ms:assetid: a8744d39-5cf2-474c-9a99-a0f3a37f846f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205167(v=OCS.15)
ms:contentKeyID: 48185093
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b864bb96ea7d342dbfd449cc9a151b0d7c2dee6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202472"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-an-archiving-configuration-in-lync-server-2013"></a><span data-ttu-id="4d12e-102">Eliminazione di una configurazione di archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d12e-102">Deleting an Archiving configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d12e-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="4d12e-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="4d12e-104">È possibile eliminare la configurazione di un sito o la configurazione di un pool.</span><span class="sxs-lookup"><span data-stu-id="4d12e-104">You can delete a site configuration or pool configuration.</span></span> <span data-ttu-id="4d12e-105">La configurazione globale non può essere rimossa.</span><span class="sxs-lookup"><span data-stu-id="4d12e-105">The global configuration cannot be removed.</span></span> <span data-ttu-id="4d12e-106">Se si elimina la configurazione globale, viene reimpostata automaticamente sui valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="4d12e-106">If you delete the global configuration, it is automatically reset to the default values.</span></span> <span data-ttu-id="4d12e-107">Per informazioni dettagliate sulla modalità di implementazione delle configurazioni di archiviazione, incluse le opzioni che è possibile specificare e la gerarchia delle configurazioni di archiviazione, vedere [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, alla distribuzione o alla documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="4d12e-107">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>

## <a name="to-delete-a-site-or-pool-configuration-for-archiving"></a><span data-ttu-id="4d12e-108">Per eliminare la configurazione di un sito o di un pool per l'archiviazione</span><span class="sxs-lookup"><span data-stu-id="4d12e-108">To delete a site or pool configuration for archiving</span></span>

1.  <span data-ttu-id="4d12e-109">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="4d12e-109">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4d12e-110">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4d12e-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4d12e-111">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4d12e-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4d12e-112">Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Configurazione archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="4d12e-112">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="4d12e-113">Nell'elenco delle configurazioni di archiviazione fare clic sulla configurazione di sito o di pool che si desidera eliminare, fare clic su **Modifica** e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="4d12e-113">In the list of archiving configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="4d12e-114">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="4d12e-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="removing-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4d12e-115">Rimozione delle impostazioni di configurazione dell'archiviazione tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d12e-115">Removing Archiving Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4d12e-116">È possibile eliminare le impostazioni di configurazione dell'archiviazione utilizzando Windows PowerShell e il cmdlet **Remove-CsArchivingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="4d12e-116">Archiving configuration settings can be deleted by using Windows PowerShell and the **Remove-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="4d12e-117">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4d12e-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4d12e-118">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="4d12e-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-archiving-configuration-settings"></a><span data-ttu-id="4d12e-119">Per rimuovere una raccolta specificata di impostazioni di configurazione di archiviazione</span><span class="sxs-lookup"><span data-stu-id="4d12e-119">To remove a specified collection of archiving configuration settings</span></span>

  - <span data-ttu-id="4d12e-120">Il comando seguente rimuove le impostazioni della configurazione di archiviazione applicate al sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="4d12e-120">The following command removes the archiving configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-archiving-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="4d12e-121">Per rimuovere tutte le impostazioni di configurazione di archiviazione applicate all'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="4d12e-121">To remove all the archiving configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="4d12e-122">Questo comando rimuove tutte le impostazioni della configurazione di archiviazione applicate all'ambito del servizio:</span><span class="sxs-lookup"><span data-stu-id="4d12e-122">This command removes all the archiving configuration settings applied to the service scope:</span></span>
    
        Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration

</div>

<div>

## <a name="to-remove-archiving-configuration-settings-based-on-a-specified-property-value"></a><span data-ttu-id="4d12e-123">Per rimuovere le impostazioni di configurazione dell'archiviazione in base a un valore della proprietà specificato</span><span class="sxs-lookup"><span data-stu-id="4d12e-123">To remove archiving configuration settings based on a specified property value</span></span>

  - <span data-ttu-id="4d12e-124">Questo comando rimuove tutte le impostazioni della configurazione di archiviazione in cui l'archiviazione di Exchange è stata disabilitata:</span><span class="sxs-lookup"><span data-stu-id="4d12e-124">This command removes all the archiving configuration settings where Exchange archiving has been disabled:</span></span>
    
        Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration

</div>

<span data-ttu-id="4d12e-125">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="4d12e-125">For more information, see the help topic for the [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4d12e-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d12e-126">See Also</span></span>


[<span data-ttu-id="4d12e-127">Funzionamento dell'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d12e-127">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="4d12e-128">Gestione dell'archiviazione delle comunicazioni interne ed esterne in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d12e-128">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

