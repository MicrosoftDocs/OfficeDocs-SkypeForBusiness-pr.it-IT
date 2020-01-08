---
title: Configurazione delle impostazioni di Registrazione dettagli chiamata e Qualità percepita dagli utenti
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring call detail recording and Quality of Experience settings
ms:assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204621(v=OCS.15)
ms:contentKeyID: 48183223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 67c9759faad4ed96cdf65d8bd22c5778512933de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-call-detail-recording-and-quality-of-experience-settings-in-lync-server-2013"></a><span data-ttu-id="38e70-102">Configurazione della registrazione dei dettagli delle chiamate e della qualità delle impostazioni dell'esperienza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38e70-102">Configuring call detail recording and Quality of Experience settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38e70-103">_**Argomento Ultima modifica:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="38e70-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="38e70-104">Dopo avere associato un archivio di monitoraggio con un pool Front-End, configurare l'archivio di monitoraggio e quindi installato e configurato SQL Server Reporting Services e monitoraggio dei report è possibile gestire la registrazione dei dettagli delle chiamate (CDR) e la qualità dell'esperienza (QoE) monitoraggio tramite Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="38e70-104">After you have associated a monitoring store with a Front End pool, set up the monitoring store, and then installed and configured SQL Server Reporting Services and Monitoring Reports you can manage Call Detail Recording (CDR) and Quality of Experience (QoE) monitoring by using Lync Server Management Shell.</span></span> <span data-ttu-id="38e70-105">I cmdlet di Lync Server Management Shell consentono di abilitare e disabilitare il monitoraggio CDR e/o QoE per un determinato sito o per l'intera distribuzione di Lync Server. Questa operazione può essere eseguita con un comando semplice come questo:</span><span class="sxs-lookup"><span data-stu-id="38e70-105">Lync Server Management Shell cmdlets allow you to enable and disable CDR and/or QoE monitoring for a particular site or for your entire Lync Server deployment; that can be done with a command as simple as this:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $False

<span data-ttu-id="38e70-106">Quando si installa Microsoft Lync Server 2013, viene installata anche una raccolta predefinita di impostazioni di configurazione globali sia per CDR che per QoE.</span><span class="sxs-lookup"><span data-stu-id="38e70-106">When you install Microsoft Lync Server 2013, you will also install a predefined collection of global configuration settings for both CDR and QoE.</span></span> <span data-ttu-id="38e70-107">Nella tabella seguente sono illustrati i valori predefiniti per alcune delle impostazioni più comuni usate per la registrazione dei dettagli delle chiamate:</span><span class="sxs-lookup"><span data-stu-id="38e70-107">Default values for some of the more commonly-used settings used by Call Detail Recording are shown in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38e70-108">Proprietà</span><span class="sxs-lookup"><span data-stu-id="38e70-108">Property</span></span></th>
<th><span data-ttu-id="38e70-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38e70-109">Description</span></span></th>
<th><span data-ttu-id="38e70-110">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="38e70-110">Default Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38e70-111">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="38e70-111">EnableCDR</span></span></p></td>
<td><p><span data-ttu-id="38e70-112">Indica se CDR è abilitato o meno.</span><span class="sxs-lookup"><span data-stu-id="38e70-112">Indicates whether or not CDR is enabled.</span></span> <span data-ttu-id="38e70-113">Se true, tutti i record CDR verranno raccolti e scritti nel database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="38e70-113">If True, all CDR records will be collected and written to the monitoring database.</span></span></p></td>
<td><p><span data-ttu-id="38e70-114">True</span><span class="sxs-lookup"><span data-stu-id="38e70-114">True</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38e70-115">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="38e70-115">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="38e70-116">Indica se i record CDR verranno eliminati periodicamente dal database.</span><span class="sxs-lookup"><span data-stu-id="38e70-116">Indicates whether or not CDR records will periodically be deleted from the database.</span></span> <span data-ttu-id="38e70-117">Se true, i record verranno eliminati dopo il periodo di tempo specificato dalle proprietà KeepCallDetailForDays (per i record CDR) e KeepErrorReportForDays (per gli errori CDR).</span><span class="sxs-lookup"><span data-stu-id="38e70-117">If True, records will be deleted after the time period specified by the properties KeepCallDetailForDays (for CDR records) and KeepErrorReportForDays (for CDR errors).</span></span> <span data-ttu-id="38e70-118">Se false, i record CDR verranno mantenuti indefinitamente.</span><span class="sxs-lookup"><span data-stu-id="38e70-118">If False, CDR records will be maintained indefinitely.</span></span></p></td>
<td><p><span data-ttu-id="38e70-119">True</span><span class="sxs-lookup"><span data-stu-id="38e70-119">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38e70-120">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="38e70-120">KeepCallDetailForDays</span></span></p></td>
<td><p><span data-ttu-id="38e70-121">Indica il numero di giorni in cui i record CDR verranno conservati nel database. tutti i record antecedenti al numero di giorni specificato verranno eliminati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="38e70-121">Indicates the number of days that CDR records will be kept in the database; any records older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="38e70-122">Tuttavia, questo problema si verificherà solo se l'eliminazione è stata abilitata.</span><span class="sxs-lookup"><span data-stu-id="38e70-122">However, this will occur only if purging has been enabled.</span></span></p>
<p><span data-ttu-id="38e70-123">KeepCallDetailForDays può essere impostato su un valore intero compreso tra 1 e 2562 giorni (circa 7 anni).</span><span class="sxs-lookup"><span data-stu-id="38e70-123">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days (approximately 7 years).</span></span></p></td>
<td><p><span data-ttu-id="38e70-124">60 giorni</span><span class="sxs-lookup"><span data-stu-id="38e70-124">60 days</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38e70-125">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="38e70-125">KeepErrorReportForDays</span></span></p></td>
<td><p><span data-ttu-id="38e70-126">Indica il numero di giorni in cui vengono mantenuti i report di errore CDR; tutti i report antecedenti al numero di giorni specificato verranno eliminati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="38e70-126">Indicates the number of days that CDR error reports are kept; any reports older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="38e70-127">I report di errore CDR sono report di diagnostica caricati da applicazioni client come Microsoft Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="38e70-127">CDR error reports are diagnostic reports uploaded by client applications such as Microsoft Lync 2013.</span></span></p>
<p><span data-ttu-id="38e70-128">Puoi impostare questa proprietà su qualsiasi valore intero compreso tra 1 e 2562 giorni.</span><span class="sxs-lookup"><span data-stu-id="38e70-128">You can set this property to any integer value between 1 and 2562 days.</span></span></p></td>
<td><p><span data-ttu-id="38e70-129">60 giorni</span><span class="sxs-lookup"><span data-stu-id="38e70-129">60 days</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="38e70-130">Allo stesso modo, i valori predefiniti per le impostazioni QoE selezionate sono illustrati in questa tabella:</span><span class="sxs-lookup"><span data-stu-id="38e70-130">Similarly, default values for selected QoE settings are shown in this table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38e70-131">Proprietà</span><span class="sxs-lookup"><span data-stu-id="38e70-131">Property</span></span></th>
<th><span data-ttu-id="38e70-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38e70-132">Description</span></span></th>
<th><span data-ttu-id="38e70-133">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="38e70-133">Default Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38e70-134">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="38e70-134">EnableQoE</span></span></p></td>
<td><p><span data-ttu-id="38e70-135">Indica se è abilitato il monitoraggio QoE.</span><span class="sxs-lookup"><span data-stu-id="38e70-135">Indicates whether or not QoE monitoring is enabled.</span></span> <span data-ttu-id="38e70-136">Se true, tutti i record QoE verranno raccolti e scritti nel database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="38e70-136">If True, all QoE records will be collected and written to the monitoring database.</span></span></p></td>
<td><p><span data-ttu-id="38e70-137">True</span><span class="sxs-lookup"><span data-stu-id="38e70-137">True</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38e70-138">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="38e70-138">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="38e70-139">Indica se i record QoE verranno eliminati periodicamente dal database.</span><span class="sxs-lookup"><span data-stu-id="38e70-139">Indicates whether or not QoE records will periodically be deleted from the database.</span></span> <span data-ttu-id="38e70-140">Se true, i record verranno eliminati dopo il periodo di tempo specificato dalla proprietà KeepQoEDataForDays.</span><span class="sxs-lookup"><span data-stu-id="38e70-140">If True, records will be deleted after the time period specified by the KeepQoEDataForDays property.</span></span> <span data-ttu-id="38e70-141">Se false, i record QoE verranno mantenuti indefinitamente.</span><span class="sxs-lookup"><span data-stu-id="38e70-141">If False, QoE records will be maintained indefinitely.</span></span></p></td>
<td><p><span data-ttu-id="38e70-142">True</span><span class="sxs-lookup"><span data-stu-id="38e70-142">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38e70-143">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="38e70-143">KeepQoEDataForDays</span></span></p></td>
<td><p><span data-ttu-id="38e70-144">Indica il numero di giorni in cui i record QoE verranno conservati nel database; tutti i record antecedenti al numero di giorni specificato verranno eliminati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="38e70-144">Indicates the number of days that QoE records will be kept in the database; any records older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="38e70-145">Tuttavia, questo problema si verificherà solo se l'eliminazione è stata abilitata.</span><span class="sxs-lookup"><span data-stu-id="38e70-145">However, this will occur only if purging has been enabled.</span></span></p>
<p><span data-ttu-id="38e70-146">KeepCallDetailForDays può essere impostato su qualsiasi valore intero compreso tra 1 e 2562 giorni.</span><span class="sxs-lookup"><span data-stu-id="38e70-146">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days.</span></span></p></td>
<td><p><span data-ttu-id="38e70-147">60 giorni</span><span class="sxs-lookup"><span data-stu-id="38e70-147">60 days</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="38e70-148">Se è necessario modificare queste impostazioni globali, è possibile usare i cmdlet Set-CsCdrConfiguration e Set-CsQoEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="38e70-148">If you need to modify these global settings you can do so by using the Set-CsCdrConfiguration and the Set-CsQoEConfiguration cmdlets.</span></span> <span data-ttu-id="38e70-149">Ad esempio, questo comando (eseguito da Lync Server Management Shell) Disabilita il monitoraggio CDR nell'ambito globale; Questa operazione viene eseguita impostando la proprietà EnableCDR su false ($False):</span><span class="sxs-lookup"><span data-stu-id="38e70-149">For example, this command (run from within the Lync Server Management Shell) disables CDR monitoring at the global scope; that's done by setting the EnableCDR property to False ($False):</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $False

<span data-ttu-id="38e70-150">Tieni presente che la disabilitazione del monitoraggio non dissocia l'archivio di monitoraggio dal pool Front-End, né Disinstalla o influisce in altro modo sul database di monitoraggio del backend.</span><span class="sxs-lookup"><span data-stu-id="38e70-150">Note that disabling monitoring does not dissociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="38e70-151">Quando si usa Lync Server Management Shell per disabilitare il monitoraggio CDR o QoE, è possibile interrompere temporaneamente il server Lync dalla raccolta e dall'archiviazione dei dati di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="38e70-151">When you use Lync Server Management Shell to disable either CDR or QoE monitoring all you really do is temporarily stop Lync Server from collecting and archiving monitoring data.</span></span> <span data-ttu-id="38e70-152">Se si vuole riprendere, in questo caso, la raccolta e l'archiviazione dei dati CDR, è sufficiente impostare la proprietà EnableCDR su true ($True):</span><span class="sxs-lookup"><span data-stu-id="38e70-152">If you want to resume, in this case, the collection and archiving of CDR data, all you need to do is set the EnableCDR property back to True ($True):</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

<span data-ttu-id="38e70-153">Analogamente, questo comando Disabilita l'eliminazione dei record QoE nell'ambito globale:</span><span class="sxs-lookup"><span data-stu-id="38e70-153">Similarly, this command disables the purging of QoE records at the global scope:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnablePurging $False

<span data-ttu-id="38e70-154">Oltre alle impostazioni globali, le impostazioni delle configurazioni CDR e QoE possono essere assegnate all'ambito del sito.</span><span class="sxs-lookup"><span data-stu-id="38e70-154">In addition to the global settings, CDR and QoE configurations settings can be assigned to the site scope.</span></span> <span data-ttu-id="38e70-155">In questo caso è disponibile un'ulteriore flessibilità di gestione per il monitoraggio. ad esempio, un amministratore può abilitare il monitoraggio CDR per il sito Redmond, ma disabilitare il monitoraggio CDR per il sito di Dublino.</span><span class="sxs-lookup"><span data-stu-id="38e70-155">This provides additional management flexibility when it comes to monitoring; for example, an administrator can enable CDR monitoring for the Redmond site but disable CDR monitoring for the Dublin site.</span></span> <span data-ttu-id="38e70-156">Per creare nuove impostazioni di configurazione CDR nell'ambito del sito, usare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="38e70-156">To create new CDR configuration settings at the site scope, use a command similar to this:</span></span>

    New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

<span data-ttu-id="38e70-157">Tieni presente che le impostazioni configurate nell'ambito del sito hanno la precedenza sulle impostazioni configurate nell'ambito globale.</span><span class="sxs-lookup"><span data-stu-id="38e70-157">Keep in mind that settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="38e70-158">Supponiamo ad esempio che il monitoraggio CDR sia abilitato nell'ambito globale, ma disabilitato nell'ambito del sito (per il sito Redmond).</span><span class="sxs-lookup"><span data-stu-id="38e70-158">For example, suppose CDR monitoring is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="38e70-159">Ciò significa che le informazioni relative alla registrazione dei dettagli delle chiamate non verranno archiviate per gli utenti nel sito Redmond.</span><span class="sxs-lookup"><span data-stu-id="38e70-159">That means that call detail recording information will not be archived for users in the Redmond site.</span></span> <span data-ttu-id="38e70-160">Tuttavia, gli utenti di altri siti, ovvero gli utenti gestiti dalle impostazioni globali anziché dalle impostazioni del sito Redmond, riceveranno le informazioni di registrazione dei dettagli delle chiamate archiviate.</span><span class="sxs-lookup"><span data-stu-id="38e70-160">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording information archived.</span></span>

<span data-ttu-id="38e70-161">Le nuove impostazioni di configurazione QoE possono essere create nell'ambito del sito usando un comando come questo:</span><span class="sxs-lookup"><span data-stu-id="38e70-161">New QoE configuration settings can be created at the site scope by using a command like this one:</span></span>

    New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15

<span data-ttu-id="38e70-162">Per altre informazioni, digitare i comandi seguenti all'interno di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="38e70-162">For more information, type the following commands from within the Lync Server Management Shell:</span></span>

    Get-Help New-CsCdrConfiguration | more
    Get-Help Set-CsCdrConfiguration | more
    Get-Help New-CsQoEConfiguration | more
    Get-Help Set-CsQoEConfiguration | more

</div>

<span> </span>

</div>

</div>

</div>

