---
title: 'Lync Server 2013: creare o modificare una raccolta di impostazioni di configurazione CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of CDR configuration settings
ms:assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721878(v=OCS.15)
ms:contentKeyID: 49733812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44ec5383a8050370ba259350aed4528765838b47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977439"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="f1373-102">Creare o modificare una raccolta di impostazioni di configurazione CDR in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1373-102">Create or modify a collection of CDR configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1373-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="f1373-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="f1373-104">La registrazione dei dettagli delle chiamate (CDR) consente di tenere traccia dell'uso di elementi come sessioni di messaggistica istantanea peer-to-peer, chiamate telefoniche VoIP (Voice over Internet Protocol) e chiamate in conferenza.</span><span class="sxs-lookup"><span data-stu-id="f1373-104">Call detail recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls.</span></span> <span data-ttu-id="f1373-105">Questo dati di utilizzo include informazioni su chi ha chiamato chi, quando ha chiamato, e per quanto tempo ha parlato.</span><span class="sxs-lookup"><span data-stu-id="f1373-105">This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="f1373-106">Quando si installa Microsoft Lync Server 2013, viene creata una singola raccolta globale di impostazioni di configurazione CDR.</span><span class="sxs-lookup"><span data-stu-id="f1373-106">When you install Microsoft Lync Server 2013 a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="f1373-107">Gli amministratori hanno anche la possibilità di creare impostazioni personalizzate nell'ambito del sito.</span><span class="sxs-lookup"><span data-stu-id="f1373-107">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="f1373-108">Ogni volta che vengono usate queste impostazioni con ambito sito, hanno la precedenza sulle impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="f1373-108">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="f1373-109">Ad esempio, se si creano impostazioni con ambito sito per il sito Redmond, le impostazioni (invece delle impostazioni globali) verranno usate per gestire CDR in Redmond.</span><span class="sxs-lookup"><span data-stu-id="f1373-109">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage CDR in Redmond.</span></span>

<span data-ttu-id="f1373-110">È possibile creare impostazioni di configurazione CDR usando il pannello di controllo di Lync Server o il cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="f1373-110">You can create CDR configuration settings by using either Lync Server Control Panel or the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span> <span data-ttu-id="f1373-111">È possibile usare il pannello di controllo di Lync Server o il cmdlet [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) per modificare le impostazioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="f1373-111">You can use Lync Server Control Panel or the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet to modify existing settings.</span></span> <span data-ttu-id="f1373-112">Se si usa il pannello di controllo di Lync Server per creare o modificare le impostazioni, le opzioni seguenti saranno disponibili:</span><span class="sxs-lookup"><span data-stu-id="f1373-112">If you are using Lync Server Control Panel to create or modify settings, the following options will be available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f1373-113">Impostazione dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="f1373-113">UI Setting</span></span></th>
<th><span data-ttu-id="f1373-114">Parametro di PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1373-114">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="f1373-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f1373-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1373-116">Nome</span><span class="sxs-lookup"><span data-stu-id="f1373-116">Name</span></span></p></td>
<td><p><span data-ttu-id="f1373-117">Identity</span><span class="sxs-lookup"><span data-stu-id="f1373-117">Identity</span></span></p></td>
<td><p><span data-ttu-id="f1373-118">Identificatore univoco per le impostazioni di configurazione CDR da creare.</span><span class="sxs-lookup"><span data-stu-id="f1373-118">Unique identifier for the CDR configuration settings being created.</span></span> <span data-ttu-id="f1373-119">Queste impostazioni possono essere create solo nell'ambito del sito.</span><span class="sxs-lookup"><span data-stu-id="f1373-119">These settings can only be created at the site scope.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1373-120">Abilitare il monitoraggio di CDRs</span><span class="sxs-lookup"><span data-stu-id="f1373-120">Enable monitoring of CDRs</span></span></p></td>
<td><p><span data-ttu-id="f1373-121">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="f1373-121">EnableCDR</span></span></p></td>
<td><p><span data-ttu-id="f1373-122">Indica se CDR è abilitato o meno.</span><span class="sxs-lookup"><span data-stu-id="f1373-122">Indicates whether or not CDR is enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1373-123">Abilitare l'eliminazione di CDRs</span><span class="sxs-lookup"><span data-stu-id="f1373-123">Enable purging of CDRs</span></span></p></td>
<td><p><span data-ttu-id="f1373-124">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="f1373-124">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="f1373-125">Indica se i record CDR verranno eliminati periodicamente dal database CDR.</span><span class="sxs-lookup"><span data-stu-id="f1373-125">Indicates whether or not CDR records will periodically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1373-126">Mantieni CDRs per la durata massima (giorni)</span><span class="sxs-lookup"><span data-stu-id="f1373-126">Keep CDRs for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="f1373-127">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="f1373-127">KeepCallDetailForDays</span></span></p></td>
<td><p><span data-ttu-id="f1373-128">Indica il numero di giorni in cui i record CDR verranno conservati nel database CDR.</span><span class="sxs-lookup"><span data-stu-id="f1373-128">Indicates the number of days that CDR records will be kept in the CDR database.</span></span> <span data-ttu-id="f1373-129">Tutti i record antecedenti al numero di giorni specificato verranno eliminati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f1373-129">Any records older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="f1373-130">Tieni presente che l'eliminazione verrà eseguita solo se l'eliminazione è stata abilitata.</span><span class="sxs-lookup"><span data-stu-id="f1373-130">(Note that purging will take only place if purging has been enabled.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1373-131">Mantieni i dati del report degli errori per la durata massima (giorni)</span><span class="sxs-lookup"><span data-stu-id="f1373-131">Keep error report data for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="f1373-132">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="f1373-132">KeepErrorReportForDays</span></span></p></td>
<td><p><span data-ttu-id="f1373-133">Indica il numero di giorni in cui vengono mantenuti i report di errore CDR.</span><span class="sxs-lookup"><span data-stu-id="f1373-133">Indicates the number of days that CDR error reports are kept.</span></span> <span data-ttu-id="f1373-134">Tutti i report antecedenti al numero di giorni specificato verranno eliminati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f1373-134">Any reports older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="f1373-135">I report di errore CDR sono report di diagnostica caricati dalle applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="f1373-135">CDR error reports are diagnostic reports uploaded by client applications.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="f1373-136">I cmdlet New-CsCdrConfiguration e Set-CsCdrConfiguration includono opzioni aggiuntive non disponibili nel pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f1373-136">The New-CsCdrConfiguration and Set-CsCdrConfiguration cmdlets include additional options not available in Lync Server Control Panel.</span></span> <span data-ttu-id="f1373-137">Per altre informazioni, vedere gli argomenti della Guida <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> e <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Set-CsCdrConfiguration</A> .</span><span class="sxs-lookup"><span data-stu-id="f1373-137">See the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> and the <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Set-CsCdrConfiguration</A> help topics for more information.</span></span>



</div>

<div>

## <a name="to-create-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="f1373-138">Per creare impostazioni di configurazione CDR tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="f1373-138">To create CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f1373-139">Nel pannello di controllo di Lync Server fare clic su **monitoraggio e archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="f1373-139">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="f1373-140">Nella scheda **registrazione dettagli chiamata** fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f1373-140">On the **Call Detail Recording** tab, click **New**.</span></span>

3.  <span data-ttu-id="f1373-141">Nella finestra di dialogo **Seleziona sito** selezionare il sito in cui devono essere create le nuove impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f1373-141">In the **Select a Site** dialog box, select the site where the new configuration settings are to be created.</span></span> <span data-ttu-id="f1373-142">Se la finestra di dialogo è vuota, significa che a tutti i siti è già stata assegnata una raccolta di impostazioni di configurazione CDR.</span><span class="sxs-lookup"><span data-stu-id="f1373-142">If the dialog box is empty, that means all of your sites have already been assigned a collection of CDR configuration settings.</span></span> <span data-ttu-id="f1373-143">Ogni sito è limitato a una singola raccolta di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="f1373-143">Each site is limited to a single such collection.</span></span> <span data-ttu-id="f1373-144">In questo caso, è possibile eliminare e ricreare le impostazioni oppure semplicemente modificare le impostazioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="f1373-144">In that case you can either delete and then re-create the settings, or simply modify the existing settings.</span></span>

4.  <span data-ttu-id="f1373-145">Nella finestra di dialogo **nuova impostazione registrazione dettagli chiamata (CDR)** effettuare le selezioni desiderate e quindi fare clic su **commit**.</span><span class="sxs-lookup"><span data-stu-id="f1373-145">In the **New Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-existing-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="f1373-146">Per modificare le impostazioni di configurazione CDR esistenti tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="f1373-146">To modify existing CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f1373-147">Nel pannello di controllo di Lync Server fare clic su **monitoraggio e archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="f1373-147">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="f1373-148">Fare doppio clic sulla raccolta di impostazioni da modificare oppure selezionare la raccolta, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="f1373-148">Double-click the collection of settings to be modified, or select the collection, click **Edit**, and then click **Show Details**.</span></span> <span data-ttu-id="f1373-149">Tieni presente che puoi modificare solo una singola raccolta alla volta.</span><span class="sxs-lookup"><span data-stu-id="f1373-149">Note that you can only modify a single collection at a time.</span></span> <span data-ttu-id="f1373-150">Per apportare le stesse modifiche a più raccolte, usare invece Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f1373-150">To make the same changes to multiple collections, use the Lync Server Management Shell instead.</span></span>

3.  <span data-ttu-id="f1373-151">Nella finestra di dialogo **Modifica impostazione registrazione dettagli chiamata (CDR)** effettuare le selezioni desiderate e quindi fare clic su **commit**.</span><span class="sxs-lookup"><span data-stu-id="f1373-151">In the **Edit Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f1373-152">Creazione di impostazioni di configurazione CDR con i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1373-152">Creating CDR Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f1373-153">È possibile creare impostazioni di configurazione CDR anche tramite Windows PowerShell e il cmdlet **New-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="f1373-153">You can create CDR configuration settings can also be created by using Windows PowerShell and the **New-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="f1373-154">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1373-154">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f1373-155">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="f1373-155">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="f1373-156">Per creare una nuova raccolta di impostazioni di configurazione CDR</span><span class="sxs-lookup"><span data-stu-id="f1373-156">To create a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="f1373-157">Questo comando crea una nuova raccolta di impostazioni di configurazione CDR applicate al sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="f1373-157">This command creates a new collection of CDR configuration settings applied to the Redmond site:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="f1373-158">Per creare una raccolta di impostazioni di configurazione CDR che disabilitano la registrazione dei dettagli delle chiamate</span><span class="sxs-lookup"><span data-stu-id="f1373-158">To create a collection of CDR configuration settings that disable call detail recording</span></span>

  - <span data-ttu-id="f1373-159">Poiché non sono stati specificati parametri (ad eccezione del parametro di identità obbligatorio) nel comando precedente, la nuova raccolta di impostazioni di configurazione utilizzerà i valori predefiniti per tutte le relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="f1373-159">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> <span data-ttu-id="f1373-160">Per creare impostazioni che usano valori di proprietà diversi, includere semplicemente il parametro e il valore del parametro appropriati.</span><span class="sxs-lookup"><span data-stu-id="f1373-160">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="f1373-161">Ad esempio, per creare una raccolta di impostazioni di configurazione dei dettagli delle chiamate che, per impostazione predefinita, Consenti Disabilita registrazione dettagli chiamata usa un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="f1373-161">For example, to create a collection of Call Detail configuration settings that, by default, allow disable Call Detail recording use a command like this:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="f1373-162">Per specificare più valori di proprietà quando si crea una nuova raccolta di impostazioni di configurazione CDR</span><span class="sxs-lookup"><span data-stu-id="f1373-162">To specify multiple property values when creating a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="f1373-163">Puoi modificare più valori di proprietà includendo più parametri.</span><span class="sxs-lookup"><span data-stu-id="f1373-163">You can modify multiple property values by including multiple parameters.</span></span> <span data-ttu-id="f1373-164">Ad esempio, questo comando Configura le nuove impostazioni per conservare i record dei dettagli delle chiamate per 30 giorni e i report degli errori per 90 giorni:</span><span class="sxs-lookup"><span data-stu-id="f1373-164">For example, this command configures the new settings to keep Call Detail records for 30 days and error reports for 90 days:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

</div>

<span data-ttu-id="f1373-165">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="f1373-165">For more information, see the help topic for the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

