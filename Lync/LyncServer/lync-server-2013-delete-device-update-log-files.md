---
title: 'Lync Server 2013: eliminare i file di registro degli aggiornamenti dei dispositivi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete Device Update log files
ms:assetid: 58d4097f-5bbf-4824-a04d-2a6555cd93c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994039(v=OCS.15)
ms:contentKeyID: 51803949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 685b3e34c0f2bd5392f71899564d0738e814b616
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-device-update-log-files-in-lync-server-2013"></a><span data-ttu-id="b031c-102">Eliminare i file di registro degli aggiornamenti dei dispositivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b031c-102">Delete Device Update log files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b031c-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="b031c-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="b031c-104">Il servizio Web aggiornamento dispositivi conserva una vasta raccolta di file di registro.</span><span class="sxs-lookup"><span data-stu-id="b031c-104">The Device Update Web service keeps an extensive collection of log files.</span></span> <span data-ttu-id="b031c-105">Questo insieme include sia i registri di controllo eseguiti dal servizio stesso sia i file di log caricati dai dispositivi client.</span><span class="sxs-lookup"><span data-stu-id="b031c-105">This collection includes both audit logs conducted by the service itself and log files uploaded from client devices.</span></span> <span data-ttu-id="b031c-106">Per impedire il riempimento del server con i registri del servizio Web aggiornamento dispositivi, è probabile che si desideri cancellarlo dai file di registro che sono stati in circolazione per un determinato numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="b031c-106">To prevent the server from filling up with Device Update Web service logs, you’ll probably want to clear it of log files that have been around for a certain number of days.</span></span> <span data-ttu-id="b031c-107">Impostare questo numero di giorni in base all'attività di aggiornamento e al numero di dispositivi client nell'organizzazione e utilizzando il pannello di controllo di Lync Server o Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b031c-107">Set this number of days based on update activity and the number of client devices in your organization, and by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="to-clear-the-device-update-log-by-using-lync-server-control-panel"></a><span data-ttu-id="b031c-108">Per cancellare il log degli aggiornamenti del dispositivo utilizzando il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="b031c-108">To clear the device update log by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b031c-109">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b031c-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b031c-110">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b031c-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="b031c-111">Sulla barra di spostamento sinistra fare clic su **client**e quindi su **Configurazione log dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="b031c-111">In the left navigation bar, click **Clients**, and then click **Device Log Configuration**.</span></span>

3.  <span data-ttu-id="b031c-112">Nella pagina **Configurazione log dispositivo** fare doppio clic sulla configurazione che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="b031c-112">On the **Device Log Configuration** page, double-click the configuration that you want to change.</span></span>

4.  <span data-ttu-id="b031c-113">Nella finestra di dialogo **Modifica impostazione log** , in **numero di giorni per mantenere i file di registro (1-365)**, specificare un numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="b031c-113">In the **Edit Log Setting** dialog box, in **Number of days to keep log files (1-365)**, specifiy a number of days.</span></span>

5.  <span data-ttu-id="b031c-114">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="b031c-114">Click **Commit**.</span></span> <span data-ttu-id="b031c-115">Vengono eliminati tutti i file presenti nel server per un numero di giorni maggiore di quello specificato.</span><span class="sxs-lookup"><span data-stu-id="b031c-115">All files that have been on the server for more than the specified number of day are deleted.</span></span> <span data-ttu-id="b031c-116">Questa impostazione si applica a questa configurazione fino a quando non viene modificata.</span><span class="sxs-lookup"><span data-stu-id="b031c-116">This setting will apply to this configuration until you change it.</span></span>

</div>

<div>

## <a name="clearing-the-device-update-log-by-using-the-windows-powershell-cmdlets"></a><span data-ttu-id="b031c-117">Cancellazione del log degli aggiornamenti del dispositivo tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b031c-117">Clearing the Device Update Log by Using the Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b031c-118">Per cancellare i log degli aggiornamenti dei dispositivi, è possibile utilizzare Windows PowerShell e il cmdlet **Clear-CsDeviceUpdateLog** .</span><span class="sxs-lookup"><span data-stu-id="b031c-118">You can clear device update logs by using Windows PowerShell and the **Clear-CsDeviceUpdateLog** cmdlet.</span></span> <span data-ttu-id="b031c-119">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b031c-119">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b031c-120">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="b031c-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-clear-device-update-logs-on-one-server"></a><span data-ttu-id="b031c-121">Per cancellare i log degli aggiornamenti dei dispositivi su un server</span><span class="sxs-lookup"><span data-stu-id="b031c-121">To clear device update logs on one server</span></span>

  - <span data-ttu-id="b031c-122">Il comando seguente rimuove il log degli aggiornamenti del dispositivo sul server Web atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="b031c-122">The following command clears the device update log on the Web server atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="b031c-123">Tutte le voci di registro risalenti a più di 10 giorni prima (il valore specificato dal parametro DaysBack) verranno rimosse dal registro.</span><span class="sxs-lookup"><span data-stu-id="b031c-123">All log entries more than 10 days old (the value specified by the DaysBack parameter) will be removed from the log.</span></span>
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

</div>

<div>

## <a name="to-clear-all-device-update-logs"></a><span data-ttu-id="b031c-124">Per cancellare tutti i log degli aggiornamenti dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="b031c-124">To clear all device update logs</span></span>

  - <span data-ttu-id="b031c-125">Questo comando consente di rimuovere le voci obsolete (in questo esempio, le voci con più di 10 giorni) da tutti i log degli aggiornamenti dei dispositivi attualmente in uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b031c-125">This command removes outdated entries (in this example, entries more than 10 days old) from all the device update logs currently in use in your organization.</span></span>
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

</div>

<span data-ttu-id="b031c-126">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) .</span><span class="sxs-lookup"><span data-stu-id="b031c-126">For details, see the Help topic for the [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

