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
ms.openlocfilehash: 4dbccfd145ad8143edab10f92a10901e626075e2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-quality-of-experience-in-lync-server-2013"></a><span data-ttu-id="3cbfd-102">Abilitare la qualità dell'esperienza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3cbfd-102">Enable Quality of Experience in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3cbfd-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="3cbfd-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="3cbfd-104">La qualità dell'esperienza (QoE) registra i dati numerici che indicano la qualità del supporto e le informazioni sui partecipanti, i nomi di dispositivo, i driver, gli indirizzi IP e i tipi di endpoint coinvolti in chiamate e sessioni.</span><span class="sxs-lookup"><span data-stu-id="3cbfd-104">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions.</span></span> <span data-ttu-id="3cbfd-105">Per informazioni dettagliate, vedere [pianificazione del monitoraggio in Lync Server 2013](lync-server-2013-planning-for-monitoring.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="3cbfd-105">For details, see [Planning for monitoring in Lync Server 2013](lync-server-2013-planning-for-monitoring.md) in the Planning documentation.</span></span>

<span data-ttu-id="3cbfd-106">Usare la procedura seguente per abilitare QoE per l'intera organizzazione o per ogni sito dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3cbfd-106">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3cbfd-107">Per abilitare QoE, è prima necessario configurare il monitoraggio e un database back-end di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="3cbfd-107">To enable QoE, you must first configure monitoring and a monitoring back-end database.</span></span> <span data-ttu-id="3cbfd-108">Per informazioni dettagliate, vedere <A href="lync-server-2013-deploying-monitoring.md">distribuzione del monitoraggio in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3cbfd-108">For details, see <A href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-qoe-by-using-lync-server-control-panel"></a><span data-ttu-id="3cbfd-109">Per abilitare QoE tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="3cbfd-109">To enable QoE by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="3cbfd-110">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3cbfd-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="3cbfd-111">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3cbfd-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3cbfd-112">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3cbfd-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3cbfd-113">Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **qualità dei dati dell'esperienza**.</span><span class="sxs-lookup"><span data-stu-id="3cbfd-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="3cbfd-114">Nella pagina **qualità di dati esperienza** fare clic sulla raccolta appropriata dalla tabella, fare clic su **azione**e quindi su **Abilita QoE**.</span><span class="sxs-lookup"><span data-stu-id="3cbfd-114">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>

</div>

<div>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3cbfd-115">Abilitazione di QoE usando i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3cbfd-115">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3cbfd-116">Puoi abilitare QoE usando Windows PowerShell e il cmdlet **Set-CsQoEConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="3cbfd-116">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="3cbfd-117">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3cbfd-117">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3cbfd-118">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="3cbfd-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="3cbfd-119">Per abilitare QoE per una singola posizione</span><span class="sxs-lookup"><span data-stu-id="3cbfd-119">To enable QoE for a single location</span></span>

  - <span data-ttu-id="3cbfd-120">Per abilitare QoE, imposta il parametro EnableQoE su true ($True).</span><span class="sxs-lookup"><span data-stu-id="3cbfd-120">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True

</div>

<div>

## <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="3cbfd-121">Per disabilitare QoE per una singola posizione</span><span class="sxs-lookup"><span data-stu-id="3cbfd-121">To disable QoE for a single location</span></span>

  - <span data-ttu-id="3cbfd-122">Per disabilitare QoE, imposta il parametro EnableQoE su false ($False).</span><span class="sxs-lookup"><span data-stu-id="3cbfd-122">To disable QoE, set the EnableQoE parameter to False ($False).</span></span> <span data-ttu-id="3cbfd-123">Questo non disinstalla il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="3cbfd-123">This does not uninstall monitoring.</span></span> <span data-ttu-id="3cbfd-124">Sospende la raccolta e lo spazio di archiviazione dei dati QoE.</span><span class="sxs-lookup"><span data-stu-id="3cbfd-124">It pauses the collection and storage of QoE data.</span></span>
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="3cbfd-125">Per usare un singolo comando per abilitare QoE in più posizioni</span><span class="sxs-lookup"><span data-stu-id="3cbfd-125">To use a single command to enable QoE in multiple locations</span></span>

  - <span data-ttu-id="3cbfd-126">Questo comando abilita QoE per tutte le impostazioni di configurazione QoE attualmente in uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3cbfd-126">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True

</div>

<span data-ttu-id="3cbfd-127">Per informazioni dettagliate, vedere [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration).</span><span class="sxs-lookup"><span data-stu-id="3cbfd-127">For details, see [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3cbfd-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3cbfd-128">See Also</span></span>


[<span data-ttu-id="3cbfd-129">Pianificazione del monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3cbfd-129">Planning for monitoring in Lync Server 2013</span></span>](lync-server-2013-planning-for-monitoring.md)  
[<span data-ttu-id="3cbfd-130">Distribuzione del monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3cbfd-130">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

