---
title: 'Lync Server 2013: modificare le impostazioni per i file di registro di aggiornamento dei dispositivi'
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
ms.openlocfilehash: 770682cfed17d9b029688275469351c1cfdf9f4d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050548"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a><span data-ttu-id="89da9-102">Modificare le impostazioni per i file di log degli aggiornamenti dei dispositivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89da9-102">Modify settings for Device Update log files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89da9-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="89da9-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="89da9-104">È possibile modificare le impostazioni relative al modo in cui le informazioni sugli aggiornamenti dei dispositivi vengono registrate nell'organizzazione utilizzando il pannello di controllo di Lync Server o Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="89da9-104">You can change settings for how device update information is logged in your organization by using Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="89da9-105">Nella tabella seguente vengono illustrate le impostazioni modificabili e gli strumenti utilizzati per modificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="89da9-105">The following table shows which settings are modifiable, and which tool(s) you use to modify the settings.</span></span>

<span data-ttu-id="89da9-106">Le impostazioni del registro possono essere modificate e applicate a livello globale o per sito.</span><span class="sxs-lookup"><span data-stu-id="89da9-106">Log settings can be changed and applied globally, or per site.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="89da9-107">Per modificare</span><span class="sxs-lookup"><span data-stu-id="89da9-107">To change</span></span></th>
<th><span data-ttu-id="89da9-108">Uso</span><span class="sxs-lookup"><span data-stu-id="89da9-108">Use</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="89da9-109">Dimensione massima, espressa in byte, di un file di registro</span><span class="sxs-lookup"><span data-stu-id="89da9-109">The maximum size (in bytes) for a log file</span></span></p></td>
<td><p><span data-ttu-id="89da9-110">Pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="89da9-110">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="89da9-111">-oppure-</span><span class="sxs-lookup"><span data-stu-id="89da9-111">-or-</span></span></p>
<p><span data-ttu-id="89da9-112">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="89da9-112">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89da9-113">La quantità massima di informazioni (in byte) che possono essere conservate nella cache</span><span class="sxs-lookup"><span data-stu-id="89da9-113">The maximum amount of information (in bytes) that can be held in the cache</span></span></p></td>
<td><p><span data-ttu-id="89da9-114">Pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="89da9-114">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="89da9-115">-oppure-</span><span class="sxs-lookup"><span data-stu-id="89da9-115">-or-</span></span></p>
<p><span data-ttu-id="89da9-116">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="89da9-116">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89da9-117">Frequenza (in minuti) per la scrittura di informazioni memorizzate nella cache nel file di registro</span><span class="sxs-lookup"><span data-stu-id="89da9-117">How often (in minutes) to write cached information to the log file</span></span></p></td>
<td><p><span data-ttu-id="89da9-118">Pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="89da9-118">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="89da9-119">-oppure-</span><span class="sxs-lookup"><span data-stu-id="89da9-119">-or-</span></span></p>
<p><span data-ttu-id="89da9-120">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="89da9-120">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89da9-121">Durata (in giorni) per mantenere i file di registro</span><span class="sxs-lookup"><span data-stu-id="89da9-121">How long (in days) to keep log files</span></span></p></td>
<td><p><span data-ttu-id="89da9-122">Pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="89da9-122">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="89da9-123">-oppure-</span><span class="sxs-lookup"><span data-stu-id="89da9-123">-or-</span></span></p>
<p><span data-ttu-id="89da9-124">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="89da9-124">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89da9-125">Quando (ora del giorno) per controllare i file scaduti che devono essere eliminati</span><span class="sxs-lookup"><span data-stu-id="89da9-125">When (time of day) to check for expired files that should be deleted</span></span></p></td>
<td><p><span data-ttu-id="89da9-126">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="89da9-126">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89da9-127">Le estensioni di file di registro da consentire</span><span class="sxs-lookup"><span data-stu-id="89da9-127">What log file extensions to permit</span></span></p></td>
<td><p><span data-ttu-id="89da9-128">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="89da9-128">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89da9-129">Quali tipi di file di registro mantenere</span><span class="sxs-lookup"><span data-stu-id="89da9-129">Which log file types to retain</span></span></p></td>
<td><p><span data-ttu-id="89da9-130">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="89da9-130">Lync Server Management Shell</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="89da9-131">Per modificare le impostazioni di registrazione tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="89da9-131">To change logging settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="89da9-132">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="89da9-132">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="89da9-133">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="89da9-133">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="89da9-134">Sulla barra di spostamento sinistra fare clic su **client**e quindi su **Configurazione log dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="89da9-134">In the left navigation bar, click **Clients**, and then click **Device Log Configuration**.</span></span>

3.  <span data-ttu-id="89da9-135">Nella pagina **Configurazione log dispositivo** fare doppio clic sulla configurazione che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="89da9-135">On the **Device Log Configuration** page, double-click the configuration that you want to change.</span></span>

4.  <span data-ttu-id="89da9-136">Nella finestra di dialogo **Modifica impostazione log** modificare una delle impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="89da9-136">In the **Edit Log Setting** dialog box, change any of the following settings:</span></span>
    
      - <span data-ttu-id="89da9-137">**Dimensioni massime file (byte)**   consente di specificare la dimensione massima che un file di registro può diventare prima che venga eliminato.</span><span class="sxs-lookup"><span data-stu-id="89da9-137">**Maximum file size (bytes)**   Specifies the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="89da9-138">Il valore predefinito è 1.024.000 byte (1 MB).</span><span class="sxs-lookup"><span data-stu-id="89da9-138">The default is 1,024,000 bytes (1 MB).</span></span>
    
      - <span data-ttu-id="89da9-139">**Dimensioni massime cache (byte)**   consente di specificare la quantità massima di informazioni (in byte) che possono essere conservate nella cache dei file di registro prima che la cache debba essere deselezionata e che i dati vengano scritti in un file di registro.</span><span class="sxs-lookup"><span data-stu-id="89da9-139">**Maximum cache size (bytes)**   Specifies the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="89da9-140">Il valore predefinito è 512.000 byte (0,5 MB).</span><span class="sxs-lookup"><span data-stu-id="89da9-140">The default is 512,000 bytes (0.5 MB).</span></span>
    
      - <span data-ttu-id="89da9-141">**Il numero di minuti in cui svuotare la cache (1-60)**   indica la frequenza con cui le informazioni archiviate nella cache dei file di registro vengono scritte nel file di registro effettivo.</span><span class="sxs-lookup"><span data-stu-id="89da9-141">**Number of minutes to flush cache (1-60)**   Indicates how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="89da9-142">Dopo la registrazione dei dati, la cache viene svuotata.</span><span class="sxs-lookup"><span data-stu-id="89da9-142">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="89da9-143">Il valore predefinito è 5 minuti.</span><span class="sxs-lookup"><span data-stu-id="89da9-143">The default is five minutes.</span></span>
    
      - <span data-ttu-id="89da9-144">**Numero di giorni di conservazione dei file di registro (1-365)**   specifica il numero di giorni in cui i file di registro vengono mantenuti prima che vengano eliminati.</span><span class="sxs-lookup"><span data-stu-id="89da9-144">**Number of days to keep log files (1-365)**   Specifies the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="89da9-145">Il valore predefinito è 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="89da9-145">The default is 10 days.</span></span>

5.  <span data-ttu-id="89da9-146">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="89da9-146">Click **Commit**.</span></span>

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="89da9-147">Modifica delle impostazioni di registrazione tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="89da9-147">Changing Logging Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="89da9-148">È possibile modificare le impostazioni dei file di registro di aggiornamento del dispositivo utilizzando Windows PowerShell e il cmdlet **Set-CsDeviceUpdateConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="89da9-148">Device update log file settings can be modified by using Windows PowerShell and the **Set-CsDeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="89da9-149">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89da9-149">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="89da9-150">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="89da9-150">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<span data-ttu-id="89da9-151">Negli esempi riportati di seguito vengono illustrati alcuni dei modi in cui è possibile utilizzare **Set-CsDeviceUpdateConfiguration** per modificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="89da9-151">The following examples show a couple of the ways that you can use **Set-CsDeviceUpdateConfiguration** to modify settings.</span></span>

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a><span data-ttu-id="89da9-152">Per modificare la dimensione massima del file di registro e l'intervallo di pulizia dei registri</span><span class="sxs-lookup"><span data-stu-id="89da9-152">To modify the maximum log file size and the log cleanup interval</span></span>

  - <span data-ttu-id="89da9-153">Il comando seguente consente di modificare le impostazioni del registro degli aggiornamenti dei dispositivi applicati al sito Redmond.</span><span class="sxs-lookup"><span data-stu-id="89da9-153">The following command modifies the device update log settings applied to the Redmond site.</span></span> <span data-ttu-id="89da9-154">In questo esempio, la dimensione massima del file di registro è impostata su 204800 byte e l'intervallo di pulizia dei registri è impostato su 14 giorni.</span><span class="sxs-lookup"><span data-stu-id="89da9-154">In this example, the maximum log file size is set to 204800 bytes and the log cleanup interval is set to 14 days.</span></span>
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a><span data-ttu-id="89da9-155">Per modificare l'ora del giorno per la pulizia dei log</span><span class="sxs-lookup"><span data-stu-id="89da9-155">To modify the log cleanup time of day</span></span>

  - <span data-ttu-id="89da9-156">Questo comando consente di impostare il tempo di pulizia dei registri per il sito Redmond su 3:00 AM.</span><span class="sxs-lookup"><span data-stu-id="89da9-156">This command sets the log cleanup time for the Redmond site to 3:00 AM.</span></span>
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

<span data-ttu-id="89da9-157">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="89da9-157">For details, see the Help topic for the [Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

