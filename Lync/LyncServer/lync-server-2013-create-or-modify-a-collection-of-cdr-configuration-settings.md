---
title: 'Lync Server 2013: creare o modificare una raccolta di impostazioni di configurazione di registrazione dettagli chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of CDR configuration settings
ms:assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721878(v=OCS.15)
ms:contentKeyID: 49733812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 828c02e11d9e5adfe7028dd8d224c10df14c2247
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190469"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="42912-102">Creare o modificare una raccolta di impostazioni di configurazione di registrazione dettagli chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42912-102">Create or modify a collection of CDR configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42912-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="42912-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="42912-p101">La registrazione dettagli chiamata consente di tenere traccia dell'utilizzo di elementi quali le sessioni di messaggistica istantanea peer-to-peer, le chiamate telefoniche VoIP (Voice over Internet Protocol) e le conferenze telefoniche. Questi dati relativi all'utilizzo includono informazioni sull'utente chiamante e sull'utente chiamato, sulla data della chiamata e sulla durata della conversazione.</span><span class="sxs-lookup"><span data-stu-id="42912-p101">Call detail recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="42912-106">Quando si installa Microsoft Lync Server 2013, viene creata un'unica raccolta globale di impostazioni di configurazione di registrazione dettagli chiamata.</span><span class="sxs-lookup"><span data-stu-id="42912-106">When you install Microsoft Lync Server 2013 a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="42912-107">Gli amministratori hanno inoltre la possibilità di creare impostazioni personalizzato con ambito sito.</span><span class="sxs-lookup"><span data-stu-id="42912-107">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="42912-108">Ogni volta che vengono utilizzate tali impostazioni con ambito sito, queste avranno la precedenza rispetto alle impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="42912-108">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="42912-109">Ad esempio, se si creano impostazioni con ambito sito per il sito Redmond, tali impostazioni (anziché le impostazioni globali) verranno utilizzate per gestire la registrazione dettagli chiamata in Redmond.</span><span class="sxs-lookup"><span data-stu-id="42912-109">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage CDR in Redmond.</span></span>

<span data-ttu-id="42912-110">È possibile creare impostazioni di configurazione di registrazione dettagli chiamata utilizzando il pannello di controllo di Lync Server o il cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="42912-110">You can create CDR configuration settings by using either Lync Server Control Panel or the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span> <span data-ttu-id="42912-111">È possibile utilizzare il pannello di controllo di Lync Server o il cmdlet [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) per modificare le impostazioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="42912-111">You can use Lync Server Control Panel or the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet to modify existing settings.</span></span> <span data-ttu-id="42912-112">Se si utilizza il pannello di controllo di Lync Server per creare o modificare le impostazioni, saranno disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="42912-112">If you are using Lync Server Control Panel to create or modify settings, the following options will be available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42912-113">Impostazione dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="42912-113">UI Setting</span></span></th>
<th><span data-ttu-id="42912-114">Parametro di PowerShell</span><span class="sxs-lookup"><span data-stu-id="42912-114">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="42912-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="42912-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42912-116">Name</span><span class="sxs-lookup"><span data-stu-id="42912-116">Name</span></span></p></td>
<td><p><span data-ttu-id="42912-117">Identità</span><span class="sxs-lookup"><span data-stu-id="42912-117">Identity</span></span></p></td>
<td><p><span data-ttu-id="42912-p104">Identificatore univoco delle impostazioni di configurazione di registrazione dettagli chiamata che si desidera creare. Queste impostazioni possono essere create solo nell'ambito del sito.</span><span class="sxs-lookup"><span data-stu-id="42912-p104">Unique identifier for the CDR configuration settings being created. These settings can only be created at the site scope.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42912-120">Abilita monitoraggio registrazioni dettagli chiamata</span><span class="sxs-lookup"><span data-stu-id="42912-120">Enable monitoring of CDRs</span></span></p></td>
<td><p><span data-ttu-id="42912-121">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="42912-121">EnableCDR</span></span></p></td>
<td><p><span data-ttu-id="42912-122">Indica se la registrazione dettagli chiamata è abilitata o meno.</span><span class="sxs-lookup"><span data-stu-id="42912-122">Indicates whether or not CDR is enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42912-123">Abilita eliminazione registrazioni dettagli chiamata</span><span class="sxs-lookup"><span data-stu-id="42912-123">Enable purging of CDRs</span></span></p></td>
<td><p><span data-ttu-id="42912-124">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="42912-124">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="42912-125">Indica se le registrazioni dettagli chiamata saranno eliminate periodicamente dal relativo database.</span><span class="sxs-lookup"><span data-stu-id="42912-125">Indicates whether or not CDR records will periodically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42912-126">Mantieni registrazioni dettagli chiamata per durata massima (giorni)</span><span class="sxs-lookup"><span data-stu-id="42912-126">Keep CDRs for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="42912-127">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="42912-127">KeepCallDetailForDays</span></span></p></td>
<td><p><span data-ttu-id="42912-p105">Indica per quanti giorni le registrazioni dettagli chiamata verranno mantenute nel relativo database. Le eventuali registrazioni antecedenti al numero di giorni specificato verranno eliminate automaticamente. Si noti che questa operazione verrà eseguita soltanto se è stata abilitata l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="42912-p105">Indicates the number of days that CDR records will be kept in the CDR database. Any records older than the specified number of days will automatically be deleted. (Note that purging will take only place if purging has been enabled.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42912-131">Mantieni dati delle segnalazioni errori per durata massima (giorni)</span><span class="sxs-lookup"><span data-stu-id="42912-131">Keep error report data for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="42912-132">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="42912-132">KeepErrorReportForDays</span></span></p></td>
<td><p><span data-ttu-id="42912-p106">Indica per quanti giorni verranno mantenuti i rapporti sugli errori di registrazione dettagli chiamata. Gli eventuali rapporti antecedenti al numero di giorni specificato verranno eliminati automaticamente. I rapporti sugli errori di registrazione dettagli chiamata sono rapporti di diagnostica caricati da applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="42912-p106">Indicates the number of days that CDR error reports are kept. Any reports older than the specified number of days will automatically be deleted. CDR error reports are diagnostic reports uploaded by client applications.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="42912-136">I cmdlet New-CsCdrConfiguration e Set-CsCdrConfiguration includono opzioni aggiuntive non disponibili nel pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="42912-136">The New-CsCdrConfiguration and Set-CsCdrConfiguration cmdlets include additional options not available in Lync Server Control Panel.</span></span> <span data-ttu-id="42912-137">Per ulteriori informazioni, vedere gli argomenti della Guida di <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> e <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Set-CsCdrConfiguration</A> .</span><span class="sxs-lookup"><span data-stu-id="42912-137">See the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> and the <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Set-CsCdrConfiguration</A> help topics for more information.</span></span>



</div>

<div>

## <a name="to-create-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="42912-138">Per creare le impostazioni di configurazione di registrazione dettagli chiamata utilizzando il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="42912-138">To create CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="42912-139">Nel pannello di controllo di Lync Server, fare clic su **monitoraggio e archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="42912-139">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="42912-140">Nella scheda **registrazione dettagli chiamata** fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="42912-140">On the **Call Detail Recording** tab, click **New**.</span></span>

3.  <span data-ttu-id="42912-p108">Nella finestra di dialogo **Seleziona un sito** selezionare il sito in cui devono essere create le nuove impostazioni di configurazione. Se la finestra di dialogo è vuota, è stata già assegnata una raccolta di impostazioni di configurazione di registrazione dettagli chiamata a tutti i siti. Ogni sito è limitato a una sola raccolta di questo tipo. In tal caso, è possibile eliminare e quindi ricreare le impostazioni oppure modificare semplicemente le impostazioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="42912-p108">In the **Select a Site** dialog box, select the site where the new configuration settings are to be created. If the dialog box is empty, that means all of your sites have already been assigned a collection of CDR configuration settings. Each site is limited to a single such collection. In that case you can either delete and then re-create the settings, or simply modify the existing settings.</span></span>

4.  <span data-ttu-id="42912-145">Nella finestra di dialogo **Nuova impostazione di registrazione dettagli chiamata** selezionare le opzioni desiderate e quindi fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="42912-145">In the **New Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-existing-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="42912-146">Per modificare le impostazioni di configurazione di registrazione dettagli chiamata esistenti utilizzando il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="42912-146">To modify existing CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="42912-147">Nel pannello di controllo di Lync Server, fare clic su **monitoraggio e archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="42912-147">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="42912-148">Fare doppio clic sulla raccolta di impostazioni da modificare oppure selezionare la raccolta, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="42912-148">Double-click the collection of settings to be modified, or select the collection, click **Edit**, and then click **Show Details**.</span></span> <span data-ttu-id="42912-149">Si noti che è possibile modificare solo una singola raccolta alla volta.</span><span class="sxs-lookup"><span data-stu-id="42912-149">Note that you can only modify a single collection at a time.</span></span> <span data-ttu-id="42912-150">Per apportare le stesse modifiche a più insiemi, utilizzare invece Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="42912-150">To make the same changes to multiple collections, use the Lync Server Management Shell instead.</span></span>

3.  <span data-ttu-id="42912-151">Nella finestra di dialogo **Modifica impostazione di registrazione dettagli chiamata** selezionare le opzioni desiderate e quindi fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="42912-151">In the **Edit Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="42912-152">Creazione delle impostazioni di configurazione di registrazione dettagli chiamata tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="42912-152">Creating CDR Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="42912-153">È possibile creare impostazioni di configurazione di registrazione dettagli chiamata anche utilizzando Windows PowerShell e il cmdlet **New-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="42912-153">You can create CDR configuration settings can also be created by using Windows PowerShell and the **New-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="42912-154">È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="42912-154">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="42912-155">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="42912-155">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="42912-156">Per creare una nuova raccolta di impostazioni di configurazione di registrazione dettagli chiamata</span><span class="sxs-lookup"><span data-stu-id="42912-156">To create a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="42912-157">Il comando seguente crea una nuova raccolta di impostazioni di configurazione di registrazione dettagli chiamata applicate al sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="42912-157">This command creates a new collection of CDR configuration settings applied to the Redmond site:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="42912-158">Per creare una raccolta di impostazioni di configurazione di registrazione dettagli chiamata che disabilitano la registrazione dettagli chiamata</span><span class="sxs-lookup"><span data-stu-id="42912-158">To create a collection of CDR configuration settings that disable call detail recording</span></span>

  - <span data-ttu-id="42912-p111">Poiché nel comando precedente non sono stati specificati parametri, eccetto il parametro obbligatorio Identity, la nuova raccolta di impostazioni di configurazione utilizzerà i valori predefiniti per le relative proprietà. Per creare impostazioni basate su valori di proprietà diversi, è sufficiente includere il parametro appropriato e il valore corrispondente. Per creare ad esempio una raccolta di impostazioni di configurazione di registrazione dettagli chiamata che consentano per impostazione predefinita di disabilitare la registrazione dettagli chiamata, utilizzare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="42912-p111">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Call Detail configuration settings that, by default, allow disable Call Detail recording use a command like this:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="42912-162">Per specificare più valori di proprietà quando si crea una nuova raccolta di impostazioni di configurazione di registrazione dettagli chiamata</span><span class="sxs-lookup"><span data-stu-id="42912-162">To specify multiple property values when creating a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="42912-p112">È possibile modificare più valori di proprietà includendo più parametri. Il comando seguente ad esempio configura le nuove impostazioni in modo da mantenere le registrazioni dettagli chiamata per 30 giorni e i rapporti sugli errori per 90 giorni:</span><span class="sxs-lookup"><span data-stu-id="42912-p112">You can modify multiple property values by including multiple parameters. For example, this command configures the new settings to keep Call Detail records for 30 days and error reports for 90 days:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

</div>

<span data-ttu-id="42912-165">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="42912-165">For more information, see the help topic for the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

