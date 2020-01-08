---
title: 'Lync Server 2013: eliminare i file di log degli aggiornamenti dei dispositivi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete Device Update log files
ms:assetid: 58d4097f-5bbf-4824-a04d-2a6555cd93c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994039(v=OCS.15)
ms:contentKeyID: 51803949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99fb9e6109c6f27e2985de18c2fcdf804dd184c7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-device-update-log-files-in-lync-server-2013"></a><span data-ttu-id="09ff2-102">Eliminare i file di log di aggiornamento dei dispositivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09ff2-102">Delete Device Update log files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09ff2-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="09ff2-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="09ff2-104">Il servizio Web Update del dispositivo mantiene una vasta raccolta di file di log.</span><span class="sxs-lookup"><span data-stu-id="09ff2-104">The Device Update Web service keeps an extensive collection of log files.</span></span> <span data-ttu-id="09ff2-105">Questa raccolta include sia i log di controllo eseguiti dal servizio stesso che i file di log caricati dai dispositivi client.</span><span class="sxs-lookup"><span data-stu-id="09ff2-105">This collection includes both audit logs conducted by the service itself and log files uploaded from client devices.</span></span> <span data-ttu-id="09ff2-106">Per evitare che il server venga compilato con i registri del servizio Web Update del dispositivo, è probabile che sia necessario cancellarlo dai file di log che si trovano in giro per un determinato numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="09ff2-106">To prevent the server from filling up with Device Update Web service logs, you’ll probably want to clear it of log files that have been around for a certain number of days.</span></span> <span data-ttu-id="09ff2-107">Impostare questo numero di giorni in base all'attività di aggiornamento e al numero di dispositivi client nell'organizzazione e tramite il pannello di controllo di Lync Server o Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="09ff2-107">Set this number of days based on update activity and the number of client devices in your organization, and by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="to-clear-the-device-update-log-by-using-lync-server-control-panel"></a><span data-ttu-id="09ff2-108">Per cancellare il log degli aggiornamenti del dispositivo usando il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="09ff2-108">To clear the device update log by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="09ff2-109">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="09ff2-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="09ff2-110">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="09ff2-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="09ff2-111">Sulla barra di spostamento sinistra fare clic su **client**e quindi su **Configurazione log dei dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="09ff2-111">In the left navigation bar, click **Clients**, and then click **Device Log Configuration**.</span></span>

3.  <span data-ttu-id="09ff2-112">Nella pagina **Configurazione log dispositivo** fare doppio clic sulla configurazione che si vuole modificare.</span><span class="sxs-lookup"><span data-stu-id="09ff2-112">On the **Device Log Configuration** page, double-click the configuration that you want to change.</span></span>

4.  <span data-ttu-id="09ff2-113">Nella finestra di dialogo **Modifica impostazioni log** , in **numero di giorni per conservare i file di log (1-365)**, specificare un numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="09ff2-113">In the **Edit Log Setting** dialog box, in **Number of days to keep log files (1-365)**, specifiy a number of days.</span></span>

5.  <span data-ttu-id="09ff2-114">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="09ff2-114">Click **Commit**.</span></span> <span data-ttu-id="09ff2-115">Tutti i file che sono stati nel server per un numero maggiore di quello specificato del giorno vengono eliminati.</span><span class="sxs-lookup"><span data-stu-id="09ff2-115">All files that have been on the server for more than the specified number of day are deleted.</span></span> <span data-ttu-id="09ff2-116">Questa impostazione verrà applicata a questa configurazione fino a quando non la modifichi.</span><span class="sxs-lookup"><span data-stu-id="09ff2-116">This setting will apply to this configuration until you change it.</span></span>

</div>

<div>

## <a name="clearing-the-device-update-log-by-using-the-windows-powershell-cmdlets"></a><span data-ttu-id="09ff2-117">Cancellazione del log di aggiornamento del dispositivo con i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="09ff2-117">Clearing the Device Update Log by Using the Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="09ff2-118">È possibile cancellare i registri di aggiornamento dei dispositivi usando Windows PowerShell e il cmdlet **Clear-CsDeviceUpdateLog** .</span><span class="sxs-lookup"><span data-stu-id="09ff2-118">You can clear device update logs by using Windows PowerShell and the **Clear-CsDeviceUpdateLog** cmdlet.</span></span> <span data-ttu-id="09ff2-119">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09ff2-119">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="09ff2-120">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="09ff2-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-clear-device-update-logs-on-one-server"></a><span data-ttu-id="09ff2-121">Per cancellare i registri di aggiornamento dei dispositivi in un server</span><span class="sxs-lookup"><span data-stu-id="09ff2-121">To clear device update logs on one server</span></span>

  - <span data-ttu-id="09ff2-122">Il comando seguente cancella il log di aggiornamento del dispositivo sul server Web atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="09ff2-122">The following command clears the device update log on the Web server atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="09ff2-123">Tutte le voci di log che superano i 10 giorni (il valore specificato dal parametro DaysBack) verranno rimosse dal log.</span><span class="sxs-lookup"><span data-stu-id="09ff2-123">All log entries more than 10 days old (the value specified by the DaysBack parameter) will be removed from the log.</span></span>
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

</div>

<div>

## <a name="to-clear-all-device-update-logs"></a><span data-ttu-id="09ff2-124">Per cancellare tutti i registri di aggiornamento dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="09ff2-124">To clear all device update logs</span></span>

  - <span data-ttu-id="09ff2-125">Questo comando rimuove le voci obsolete (in questo esempio, le voci che superano i 10 giorni) da tutti i registri di aggiornamento dei dispositivi attualmente in uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="09ff2-125">This command removes outdated entries (in this example, entries more than 10 days old) from all the device update logs currently in use in your organization.</span></span>
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

</div>

<span data-ttu-id="09ff2-126">Per informazioni dettagliate, vedere l'argomento della Guida relativo al cmdlet [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) .</span><span class="sxs-lookup"><span data-stu-id="09ff2-126">For details, see the Help topic for the [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

