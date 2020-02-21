---
title: "Lync Server 2013: abilitare la qualità dell'esperienza"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Quality of Experience
ms:assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182583(v=OCS.15)
ms:contentKeyID: 48185385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 539408bfaa32565ef76312e1b0d96767edecc169
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-quality-of-experience-in-lync-server-2013"></a><span data-ttu-id="f9383-102">Abilitare la qualità dell'esperienza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9383-102">Enable Quality of Experience in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9383-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="f9383-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="f9383-104">La qualità percepita dagli utenti (QoE, Quality of Experience) registra dati numerici che indicano la qualità multimediale e le informazioni sui partecipanti, i nomi di dispositivi, i driver, gli indirizzi IP e i tipi di endpoint coinvolti nelle chiamate e nelle sessioni.</span><span class="sxs-lookup"><span data-stu-id="f9383-104">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions.</span></span> <span data-ttu-id="f9383-105">Per informazioni dettagliate, vedere [Planning for monitoring in Lync Server 2013](lync-server-2013-planning-for-monitoring.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="f9383-105">For details, see [Planning for monitoring in Lync Server 2013](lync-server-2013-planning-for-monitoring.md) in the Planning documentation.</span></span>

<span data-ttu-id="f9383-106">Utilizzare la procedura che segue per abilitare QoE per l'intera organizzazione o per ogni suo sito.</span><span class="sxs-lookup"><span data-stu-id="f9383-106">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f9383-107">Per abilitare QoE, è innanzitutto necessario configurare il monitoraggio e un database back-end Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="f9383-107">To enable QoE, you must first configure monitoring and a monitoring back-end database.</span></span> <span data-ttu-id="f9383-108">Per informazioni dettagliate, vedere <A href="lync-server-2013-deploying-monitoring.md">Deploying Monitoring in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f9383-108">For details, see <A href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-qoe-by-using-lync-server-control-panel"></a><span data-ttu-id="f9383-109">Per abilitare QoE utilizzando il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="f9383-109">To enable QoE by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f9383-110">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a un computer nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f9383-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="f9383-111">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f9383-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f9383-112">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f9383-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f9383-113">Sulla barra di spostamento sinistra fare clic su **Monitoraggio e archiviazione** e quindi su **Dati QoE**.</span><span class="sxs-lookup"><span data-stu-id="f9383-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="f9383-114">Nella pagina **Dati QoE** fare clic sulla raccolta appropriata nella tabella, su **Azione** e quindi su **Abilita QoE**.</span><span class="sxs-lookup"><span data-stu-id="f9383-114">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>

</div>

<div>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f9383-115">Abilitazione di QoE tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f9383-115">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f9383-116">È possibile abilitare QoE utilizzando Windows PowerShell e il cmdlet **Set-CsQoEConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="f9383-116">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="f9383-117">È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f9383-117">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f9383-118">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="f9383-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="f9383-119">Per abilitare QoE per una singola posizione</span><span class="sxs-lookup"><span data-stu-id="f9383-119">To enable QoE for a single location</span></span>

  - <span data-ttu-id="f9383-120">Per abilitare QoE, impostare il parametro EnableQoE su True ($True).</span><span class="sxs-lookup"><span data-stu-id="f9383-120">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True

</div>

<div>

## <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="f9383-121">Per disabilitare QoE per una singola posizione</span><span class="sxs-lookup"><span data-stu-id="f9383-121">To disable QoE for a single location</span></span>

  - <span data-ttu-id="f9383-p105">Per disabilitare QoE, impostare il parametro EnableQoE su False ($False). Questa operazione non comporta la disinstallazione del monitoraggio. Determina solo la sospensione della raccolta e dell'archiviazione di dati QoE.</span><span class="sxs-lookup"><span data-stu-id="f9383-p105">To disable QoE, set the EnableQoE parameter to False ($False). This does not uninstall monitoring. It pauses the collection and storage of QoE data.</span></span>
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="f9383-125">Per utilizzare un singolo comando per abilitare QoE in più posizioni</span><span class="sxs-lookup"><span data-stu-id="f9383-125">To use a single command to enable QoE in multiple locations</span></span>

  - <span data-ttu-id="f9383-126">Il comando seguente abilita QoE per tutte le impostazioni di configurazione QoE attualmente in uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f9383-126">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True

</div>

<span data-ttu-id="f9383-127">Per informazioni dettagliate, vedere [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration).</span><span class="sxs-lookup"><span data-stu-id="f9383-127">For details, see [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f9383-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9383-128">See Also</span></span>


[<span data-ttu-id="f9383-129">Pianificazione del monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9383-129">Planning for monitoring in Lync Server 2013</span></span>](lync-server-2013-planning-for-monitoring.md)  
[<span data-ttu-id="f9383-130">Distribuzione del monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9383-130">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

