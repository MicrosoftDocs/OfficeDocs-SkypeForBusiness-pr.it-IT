---
title: 'Lync Server 2013: abilitare la registrazione dettagli chiamata'
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
ms.openlocfilehash: 2b033827600fc962ab5ea9df5c8848ed1533c75e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-detail-recording-in-lync-server-2013"></a><span data-ttu-id="9a190-102">Abilitare la registrazione dettagli chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a190-102">Enable call detail recording in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a190-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="9a190-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="9a190-104">Registrazione dettagli chiamata (CDR) registra l'uso e le informazioni di diagnostica sulle attività peer-to-peer, tra cui messaggistica istanza, chiamate VoIP (Voice over Internet Protocol), condivisione di applicazioni, trasferimento di file e riunioni.</span><span class="sxs-lookup"><span data-stu-id="9a190-104">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings.</span></span> <span data-ttu-id="9a190-105">I dati sull'utilizzo possono essere usati per calcolare il ritorno sugli investimenti (ROI) e i dati di diagnostica possono essere usati per risolvere le attività e le riunioni peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="9a190-105">The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span>

<span data-ttu-id="9a190-106">Usare la procedura seguente per abilitare CDR per l'intera organizzazione o per ogni sito dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9a190-106">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9a190-107">Per abilitare CDR è necessario configurare il monitoraggio e un database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="9a190-107">In order to enable CDR you must configure monitoring and a monitoring database.</span></span> <span data-ttu-id="9a190-108">Per informazioni dettagliate, vedere <A href="lync-server-2013-deploying-monitoring.md">distribuzione del monitoraggio in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9a190-108">For details, see <A href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-cdr-with-lync-server-control-panel"></a><span data-ttu-id="9a190-109">Per abilitare CDR con il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="9a190-109">To enable CDR with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9a190-110">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9a190-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="9a190-111">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9a190-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9a190-112">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9a190-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9a190-113">Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **registrazione dettagli chiamata**.</span><span class="sxs-lookup"><span data-stu-id="9a190-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="9a190-114">Nella pagina **registrazione dettagli chiamata** fare clic sul sito appropriato nella tabella, fare clic su **azione**e quindi su **Abilita CDR**.</span><span class="sxs-lookup"><span data-stu-id="9a190-114">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9a190-115">CDR è abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="9a190-115">CDR is enabled by default.</span></span>

    
    </div>

</div>

<div>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9a190-116">Attivazione di CDR tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9a190-116">Enabling CDR by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9a190-117">È possibile abilitare CDR usando Windows PowerShell e il cmdlet **Set-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="9a190-117">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="9a190-118">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a190-118">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9a190-119">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="9a190-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="9a190-120">Per abilitare CDR per una singola posizione</span><span class="sxs-lookup"><span data-stu-id="9a190-120">To enable CDR for a single location</span></span>

  - <span data-ttu-id="9a190-121">Per disabilitare CDR, imposta il parametro EnableCDR su true ($True).</span><span class="sxs-lookup"><span data-stu-id="9a190-121">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True

</div>

<div>

## <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="9a190-122">Per disabilitare CDR per una singola posizione</span><span class="sxs-lookup"><span data-stu-id="9a190-122">To disable CDR for a single location</span></span>

  - <span data-ttu-id="9a190-123">Per disabilitare CDR, imposta il parametro EnableCDR su false ($False).</span><span class="sxs-lookup"><span data-stu-id="9a190-123">To disable CDR, set the EnableCDR parameter to False ($False).</span></span> <span data-ttu-id="9a190-124">La disattivazione di CDR non disinstalla il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="9a190-124">Disabling CDR does not uninstall monitoring.</span></span> <span data-ttu-id="9a190-125">Sospende la raccolta e lo spazio di archiviazione dei dati CDR.</span><span class="sxs-lookup"><span data-stu-id="9a190-125">It pauses the collection and storage of CDR data.</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="9a190-126">Per usare un singolo comando per abilitare CDR in più posizioni</span><span class="sxs-lookup"><span data-stu-id="9a190-126">To use a single command to enable CDR in multiple locations</span></span>

  - <span data-ttu-id="9a190-127">Questo comando consente a CDR di usare tutte le impostazioni di configurazione CDR attualmente in uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9a190-127">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True

</div>

<span data-ttu-id="9a190-128">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="9a190-128">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9a190-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a190-129">See Also</span></span>


[<span data-ttu-id="9a190-130">Pianificazione del monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a190-130">Planning for monitoring in Lync Server 2013</span></span>](lync-server-2013-planning-for-monitoring.md)  
[<span data-ttu-id="9a190-131">Distribuzione del monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a190-131">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

