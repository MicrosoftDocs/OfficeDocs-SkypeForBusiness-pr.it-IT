---
title: 'Lync Server 2013: modificare le impostazioni per i file di registro di aggiornamento dei dispositivi'
description: 'Lync Server 2013: modificare le impostazioni per i file di registro di aggiornamento dei dispositivi.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify settings for Device Update log files
ms:assetid: 9b57f126-1853-43b3-bbd4-06401e6498bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182554(v=OCS.15)
ms:contentKeyID: 48184975
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c2086e11a67207a00ca99773cc818106b16d05c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566972"
---
# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a><span data-ttu-id="a8d78-103">Modificare le impostazioni per i file di log degli aggiornamenti dei dispositivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8d78-103">Modify settings for Device Update log files in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8d78-104">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="a8d78-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="a8d78-105">È possibile modificare le impostazioni relative al modo in cui le informazioni sugli aggiornamenti dei dispositivi vengono registrate nell'organizzazione utilizzando il pannello di controllo di Lync Server o Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a8d78-105">You can change settings for how device update information is logged in your organization by using Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="a8d78-106">Nella tabella seguente vengono illustrate le impostazioni modificabili e gli strumenti utilizzati per modificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="a8d78-106">The following table shows which settings are modifiable, and which tool(s) you use to modify the settings.</span></span>

<span data-ttu-id="a8d78-107">Le impostazioni del registro possono essere modificate e applicate a livello globale o per sito.</span><span class="sxs-lookup"><span data-stu-id="a8d78-107">Log settings can be changed and applied globally, or per site.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a8d78-108">Per modificare</span><span class="sxs-lookup"><span data-stu-id="a8d78-108">To change</span></span></th>
<th><span data-ttu-id="a8d78-109">Uso</span><span class="sxs-lookup"><span data-stu-id="a8d78-109">Use</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a8d78-110">Dimensione massima, espressa in byte, di un file di registro</span><span class="sxs-lookup"><span data-stu-id="a8d78-110">The maximum size (in bytes) for a log file</span></span></p></td>
<td><p><span data-ttu-id="a8d78-111">Pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="a8d78-111">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="a8d78-112">-oppure-</span><span class="sxs-lookup"><span data-stu-id="a8d78-112">-or-</span></span></p>
<p><span data-ttu-id="a8d78-113">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="a8d78-113">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8d78-114">La quantità massima di informazioni (in byte) che possono essere conservate nella cache</span><span class="sxs-lookup"><span data-stu-id="a8d78-114">The maximum amount of information (in bytes) that can be held in the cache</span></span></p></td>
<td><p><span data-ttu-id="a8d78-115">Pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="a8d78-115">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="a8d78-116">-oppure-</span><span class="sxs-lookup"><span data-stu-id="a8d78-116">-or-</span></span></p>
<p><span data-ttu-id="a8d78-117">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="a8d78-117">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8d78-118">Frequenza (in minuti) per la scrittura di informazioni memorizzate nella cache nel file di registro</span><span class="sxs-lookup"><span data-stu-id="a8d78-118">How often (in minutes) to write cached information to the log file</span></span></p></td>
<td><p><span data-ttu-id="a8d78-119">Pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="a8d78-119">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="a8d78-120">-oppure-</span><span class="sxs-lookup"><span data-stu-id="a8d78-120">-or-</span></span></p>
<p><span data-ttu-id="a8d78-121">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="a8d78-121">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8d78-122">Durata (in giorni) per mantenere i file di registro</span><span class="sxs-lookup"><span data-stu-id="a8d78-122">How long (in days) to keep log files</span></span></p></td>
<td><p><span data-ttu-id="a8d78-123">Pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="a8d78-123">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="a8d78-124">-oppure-</span><span class="sxs-lookup"><span data-stu-id="a8d78-124">-or-</span></span></p>
<p><span data-ttu-id="a8d78-125">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="a8d78-125">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8d78-126">Quando (ora del giorno) per controllare i file scaduti che devono essere eliminati</span><span class="sxs-lookup"><span data-stu-id="a8d78-126">When (time of day) to check for expired files that should be deleted</span></span></p></td>
<td><p><span data-ttu-id="a8d78-127">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="a8d78-127">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8d78-128">Le estensioni di file di registro da consentire</span><span class="sxs-lookup"><span data-stu-id="a8d78-128">What log file extensions to permit</span></span></p></td>
<td><p><span data-ttu-id="a8d78-129">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="a8d78-129">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8d78-130">Quali tipi di file di registro mantenere</span><span class="sxs-lookup"><span data-stu-id="a8d78-130">Which log file types to retain</span></span></p></td>
<td><p><span data-ttu-id="a8d78-131">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="a8d78-131">Lync Server Management Shell</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="a8d78-132">Per modificare le impostazioni di registrazione tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="a8d78-132">To change logging settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a8d78-133">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a8d78-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a8d78-134">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a8d78-134">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="a8d78-135">Sulla barra di spostamento sinistra fare clic su **client**e quindi su **Configurazione log dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="a8d78-135">In the left navigation bar, click **Clients**, and then click **Device Log Configuration**.</span></span>

3.  <span data-ttu-id="a8d78-136">Nella pagina **Configurazione log dispositivo** fare doppio clic sulla configurazione che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="a8d78-136">On the **Device Log Configuration** page, double-click the configuration that you want to change.</span></span>

4.  <span data-ttu-id="a8d78-137">Nella finestra di dialogo **Modifica impostazione log** modificare una delle impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a8d78-137">In the **Edit Log Setting** dialog box, change any of the following settings:</span></span>
    
      - <span data-ttu-id="a8d78-138">**Dimensioni massime file (byte)**     Specifica la dimensione massima di un file di registro che può diventare prima che venga eliminata.</span><span class="sxs-lookup"><span data-stu-id="a8d78-138">**Maximum file size (bytes)**   Specifies the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="a8d78-139">Il valore predefinito è 1.024.000 byte (1 MB).</span><span class="sxs-lookup"><span data-stu-id="a8d78-139">The default is 1,024,000 bytes (1 MB).</span></span>
    
      - <span data-ttu-id="a8d78-140">**Dimensioni massime della cache (byte)**     Specifica la quantità massima di informazioni (in byte) che possono essere conservate nella cache dei file di registro prima che la cache debba essere cancellata e i dati vengano scritti in un file di registro.</span><span class="sxs-lookup"><span data-stu-id="a8d78-140">**Maximum cache size (bytes)**   Specifies the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="a8d78-141">Il valore predefinito è 512.000 byte (0,5 MB).</span><span class="sxs-lookup"><span data-stu-id="a8d78-141">The default is 512,000 bytes (0.5 MB).</span></span>
    
      - <span data-ttu-id="a8d78-142">**Numero di minuti in cui svuotare la cache (1-60)**     Indica la frequenza con cui le informazioni archiviate nella cache dei file di registro vengono scritte nel file di registro effettivo.</span><span class="sxs-lookup"><span data-stu-id="a8d78-142">**Number of minutes to flush cache (1-60)**   Indicates how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="a8d78-143">Dopo la registrazione dei dati, la cache viene svuotata.</span><span class="sxs-lookup"><span data-stu-id="a8d78-143">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="a8d78-144">Il valore predefinito è 5 minuti.</span><span class="sxs-lookup"><span data-stu-id="a8d78-144">The default is five minutes.</span></span>
    
      - <span data-ttu-id="a8d78-145">**Numero di giorni di conservazione dei file di registro (1-365)**     Specifica il numero di giorni in cui i file di registro vengono mantenuti prima che vengano eliminati.</span><span class="sxs-lookup"><span data-stu-id="a8d78-145">**Number of days to keep log files (1-365)**   Specifies the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="a8d78-146">Il valore predefinito è 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="a8d78-146">The default is 10 days.</span></span>

5.  <span data-ttu-id="a8d78-147">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="a8d78-147">Click **Commit**.</span></span>

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a8d78-148">Modifica delle impostazioni di registrazione tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a8d78-148">Changing Logging Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a8d78-149">È possibile modificare le impostazioni dei file di registro di aggiornamento del dispositivo utilizzando Windows PowerShell e il cmdlet **Set-CsDeviceUpdateConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="a8d78-149">Device update log file settings can be modified by using Windows PowerShell and the **Set-CsDeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="a8d78-150">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a8d78-150">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a8d78-151">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .</span><span class="sxs-lookup"><span data-stu-id="a8d78-151">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<span data-ttu-id="a8d78-152">Negli esempi riportati di seguito vengono illustrati alcuni dei modi in cui è possibile utilizzare **Set-CsDeviceUpdateConfiguration** per modificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="a8d78-152">The following examples show a couple of the ways that you can use **Set-CsDeviceUpdateConfiguration** to modify settings.</span></span>

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a><span data-ttu-id="a8d78-153">Per modificare la dimensione massima del file di registro e l'intervallo di pulizia dei registri</span><span class="sxs-lookup"><span data-stu-id="a8d78-153">To modify the maximum log file size and the log cleanup interval</span></span>

  - <span data-ttu-id="a8d78-154">Il comando seguente consente di modificare le impostazioni del registro degli aggiornamenti dei dispositivi applicati al sito Redmond.</span><span class="sxs-lookup"><span data-stu-id="a8d78-154">The following command modifies the device update log settings applied to the Redmond site.</span></span> <span data-ttu-id="a8d78-155">In questo esempio, la dimensione massima del file di registro è impostata su 204800 byte e l'intervallo di pulizia dei registri è impostato su 14 giorni.</span><span class="sxs-lookup"><span data-stu-id="a8d78-155">In this example, the maximum log file size is set to 204800 bytes and the log cleanup interval is set to 14 days.</span></span>
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a><span data-ttu-id="a8d78-156">Per modificare l'ora del giorno per la pulizia dei log</span><span class="sxs-lookup"><span data-stu-id="a8d78-156">To modify the log cleanup time of day</span></span>

  - <span data-ttu-id="a8d78-157">Questo comando consente di impostare il tempo di pulizia dei registri per il sito Redmond su 3:00 AM.</span><span class="sxs-lookup"><span data-stu-id="a8d78-157">This command sets the log cleanup time for the Redmond site to 3:00 AM.</span></span>
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

<span data-ttu-id="a8d78-158">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="a8d78-158">For details, see the Help topic for the [Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

