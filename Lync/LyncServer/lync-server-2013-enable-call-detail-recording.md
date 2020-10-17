---
title: 'Lync Server 2013: abilitare la registrazione dettagli chiamata'
description: 'Lync Server 2013: abilitare la registrazione dettagli chiamata.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable call detail recording
ms:assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520980(v=OCS.15)
ms:contentKeyID: 48183865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d565c78571e34cead61777381875c9c8d23dae1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542582"
---
# <a name="enable-call-detail-recording-in-lync-server-2013"></a><span data-ttu-id="b23f0-103">Abilitare la registrazione dettagli chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b23f0-103">Enable call detail recording in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b23f0-104">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="b23f0-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="b23f0-p101">La funzionalità di registrazione dettagli chiamata (CDR) registra le informazioni di utilizzo e di diagnostica per le attività peer-to-peer, tra cui la messaggistica istantanea, le chiamate VoIP (Voice over Internet Protocol), la condivisione applicazioni, il trasferimento file e le riunioni. I dati di utilizzo possono essere utilizzati per calcolare il rendimento dell'investimento, mentre i dati di diagnostica possono aiutare a risolvere problemi relativi alle attività peer-to-peer e alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="b23f0-p101">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings. The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span>

<span data-ttu-id="b23f0-107">Utilizzare la procedura seguente per abilitare la registrazione dettagli chiamata per l'intera organizzazione o per ogni sito dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b23f0-107">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b23f0-108">Per abilitare la registrazione dettagli chiamata, è necessario configurare il monitoraggio e un database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="b23f0-108">In order to enable CDR you must configure monitoring and a monitoring database.</span></span> <span data-ttu-id="b23f0-109">Per informazioni dettagliate, vedere <A href="lync-server-2013-deploying-monitoring.md">Deploying Monitoring in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b23f0-109">For details, see <A href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-cdr-with-lync-server-control-panel"></a><span data-ttu-id="b23f0-110">Per abilitare CDR con il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="b23f0-110">To enable CDR with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b23f0-111">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a un computer nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b23f0-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="b23f0-112">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b23f0-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b23f0-113">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b23f0-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b23f0-114">Nella barra di spostamento sinistra fare clic su **Monitoraggio e archiviazione** e quindi su **Registrazione dettagli chiamata**.</span><span class="sxs-lookup"><span data-stu-id="b23f0-114">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="b23f0-115">Nella pagina **Registrazione dettagli chiamata** fare clic sul sito appropriato nella tabella, su **Azione** e quindi su **Abilita registrazione dettagli chiamata**.</span><span class="sxs-lookup"><span data-stu-id="b23f0-115">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b23f0-116">La funzionalità di registrazione dettagli chiamata è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b23f0-116">CDR is enabled by default.</span></span>

    
    </div>

</div>

<div>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b23f0-117">Abilitazione di CDR tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b23f0-117">Enabling CDR by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b23f0-118">È possibile abilitare la funzionalità registrazione dettagli chiamata utilizzando Windows PowerShell e il cmdlet **Set-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="b23f0-118">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="b23f0-119">È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b23f0-119">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b23f0-120">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="b23f0-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="b23f0-121">Per abilitare la funzionalità CR per una sola postazione</span><span class="sxs-lookup"><span data-stu-id="b23f0-121">To enable CDR for a single location</span></span>

  - <span data-ttu-id="b23f0-122">Per abilitare la funzionalità di registrazione dettaglia chiamata, impostare il parametro EnableCDR su True ($True).</span><span class="sxs-lookup"><span data-stu-id="b23f0-122">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True

</div>

<div>

## <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="b23f0-123">Per disabilitare la funzionalità CDR per una sola postazione</span><span class="sxs-lookup"><span data-stu-id="b23f0-123">To disable CDR for a single location</span></span>

  - <span data-ttu-id="b23f0-124">Per disabilitare la funzionalità di registrazione dettaglia chiamata, impostare il parametro EnableCDR su False ($False).</span><span class="sxs-lookup"><span data-stu-id="b23f0-124">To disable CDR, set the EnableCDR parameter to False ($False).</span></span> <span data-ttu-id="b23f0-125">La disattivazione di CDR non disinstalla il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="b23f0-125">Disabling CDR does not uninstall monitoring.</span></span> <span data-ttu-id="b23f0-126">Interrompe la raccolta e l'archiviazione dei dati di registrazione dettagli chiamata.</span><span class="sxs-lookup"><span data-stu-id="b23f0-126">It pauses the collection and storage of CDR data.</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="b23f0-127">Per abilitare la funzionalità CDR in più postazioni con un solo comando</span><span class="sxs-lookup"><span data-stu-id="b23f0-127">To use a single command to enable CDR in multiple locations</span></span>

  - <span data-ttu-id="b23f0-128">Questo comando abilita la funzionalità CDR per tutte le impostazioni di configurazione CDR attualmente in uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b23f0-128">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True

</div>

<span data-ttu-id="b23f0-129">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="b23f0-129">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b23f0-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b23f0-130">See Also</span></span>


[<span data-ttu-id="b23f0-131">Pianificazione del monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b23f0-131">Planning for monitoring in Lync Server 2013</span></span>](lync-server-2013-planning-for-monitoring.md)  
[<span data-ttu-id="b23f0-132">Distribuzione del monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b23f0-132">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

