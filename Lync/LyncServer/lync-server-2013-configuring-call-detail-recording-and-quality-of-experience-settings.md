---
title: Configurazione delle impostazioni di registrazione dettagli chiamata e qualità delle esperienze
description: Configurazione delle impostazioni di registrazione dettagli chiamata e qualità delle esperienze.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring call detail recording and Quality of Experience settings
ms:assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204621(v=OCS.15)
ms:contentKeyID: 48183223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be0238701f561e6694786faec7fc914dcc9cda40
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567172"
---
# <a name="configuring-call-detail-recording-and-quality-of-experience-settings-in-lync-server-2013"></a><span data-ttu-id="07e1c-103">Configurazione delle impostazioni di registrazione dettagli chiamata e qualità delle esperienze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07e1c-103">Configuring call detail recording and Quality of Experience settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07e1c-104">_**Ultimo argomento modificato:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="07e1c-104">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="07e1c-105">Dopo aver associato un archivio di monitoraggio a un pool Front End, configurare l'archivio di monitoraggio e quindi aver installato e configurato SQL Server Reporting Services e Monitoring report è possibile gestire il monitoraggio di registrazione dettagli chiamata (CDR) e la qualità di esperienza (QoE) utilizzando Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="07e1c-105">After you have associated a monitoring store with a Front End pool, set up the monitoring store, and then installed and configured SQL Server Reporting Services and Monitoring Reports you can manage Call Detail Recording (CDR) and Quality of Experience (QoE) monitoring by using Lync Server Management Shell.</span></span> <span data-ttu-id="07e1c-106">I cmdlet di Lync Server Management Shell consentono di abilitare e disabilitare il monitoraggio di CDR e/o QoE per un sito specifico o per l'intera distribuzione di Lync Server. che è possibile eseguire con un comando così semplice:</span><span class="sxs-lookup"><span data-stu-id="07e1c-106">Lync Server Management Shell cmdlets allow you to enable and disable CDR and/or QoE monitoring for a particular site or for your entire Lync Server deployment; that can be done with a command as simple as this:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $False

<span data-ttu-id="07e1c-107">Quando si installa Microsoft Lync Server 2013, verrà installata anche una raccolta predefinita di impostazioni di configurazione globali per CDR e QoE.</span><span class="sxs-lookup"><span data-stu-id="07e1c-107">When you install Microsoft Lync Server 2013, you will also install a predefined collection of global configuration settings for both CDR and QoE.</span></span> <span data-ttu-id="07e1c-108">I valori predefiniti di alcune delle impostazioni usate più di frequente da CDR sono mostrati nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="07e1c-108">Default values for some of the more commonly-used settings used by Call Detail Recording are shown in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="07e1c-109">Proprietà</span><span class="sxs-lookup"><span data-stu-id="07e1c-109">Property</span></span></th>
<th><span data-ttu-id="07e1c-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="07e1c-110">Description</span></span></th>
<th><span data-ttu-id="07e1c-111">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="07e1c-111">Default Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07e1c-112">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="07e1c-112">EnableCDR</span></span></p></td>
<td><p><span data-ttu-id="07e1c-p103">Indica se la registrazione dettagli chiamata è abilitata o meno. Se è impostata su True, tutti i record CDR verranno raccolti e scritti nel database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="07e1c-p103">Indicates whether or not CDR is enabled. If True, all CDR records will be collected and written to the monitoring database.</span></span></p></td>
<td><p><span data-ttu-id="07e1c-115">Vero</span><span class="sxs-lookup"><span data-stu-id="07e1c-115">True</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e1c-116">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="07e1c-116">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="07e1c-p104">Indica se i record CDR verranno eliminati periodicamente dal database. Se è impostata su True, i record verranno eliminati dopo il periodo di tempo specificato dalle proprietà KeepCallDetailForDays (per record CDR) e KeepErrorReportForDays (per errori CDR). Se False, i record verranno mantenuti indefinitamente.</span><span class="sxs-lookup"><span data-stu-id="07e1c-p104">Indicates whether or not CDR records will periodically be deleted from the database. If True, records will be deleted after the time period specified by the properties KeepCallDetailForDays (for CDR records) and KeepErrorReportForDays (for CDR errors). If False, CDR records will be maintained indefinitely.</span></span></p></td>
<td><p><span data-ttu-id="07e1c-120">Vero</span><span class="sxs-lookup"><span data-stu-id="07e1c-120">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07e1c-121">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="07e1c-121">KeepCallDetailForDays</span></span></p></td>
<td><p><span data-ttu-id="07e1c-p105">Indica il numero di giorni per cui i record CDR verranno mantenuti nel database. Qualsiasi record che ha superato il numero di giorni specificato verrà eliminato automaticamente, ma solo se l'eliminazione è stata abilitata.</span><span class="sxs-lookup"><span data-stu-id="07e1c-p105">Indicates the number of days that CDR records will be kept in the database; any records older than the specified number of days will automatically be deleted. However, this will occur only if purging has been enabled.</span></span></p>
<p><span data-ttu-id="07e1c-124">KeepCallDetailForDays può essere impostato su qualsiasi valore intero compreso tra 1 e 2562 giorni (circa 7 anni).</span><span class="sxs-lookup"><span data-stu-id="07e1c-124">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days (approximately 7 years).</span></span></p></td>
<td><p><span data-ttu-id="07e1c-125">60 giorni</span><span class="sxs-lookup"><span data-stu-id="07e1c-125">60 days</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e1c-126">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="07e1c-126">KeepErrorReportForDays</span></span></p></td>
<td><p><span data-ttu-id="07e1c-127">Indica il numero di giorni in cui vengono mantenuti i report di errore di registrazione dettagli chiamata. gli eventuali rapporti precedenti al numero di giorni specificato verranno eliminati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="07e1c-127">Indicates the number of days that CDR error reports are kept; any reports older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="07e1c-128">I report di errore CDR sono rapporti di diagnostica caricati da applicazioni client quali Microsoft Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="07e1c-128">CDR error reports are diagnostic reports uploaded by client applications such as Microsoft Lync 2013.</span></span></p>
<p><span data-ttu-id="07e1c-129">È possibile impostare questa proprietà su qualsiasi valore intero compreso tra 1 e 2562 giorni.</span><span class="sxs-lookup"><span data-stu-id="07e1c-129">You can set this property to any integer value between 1 and 2562 days.</span></span></p></td>
<td><p><span data-ttu-id="07e1c-130">60 giorni</span><span class="sxs-lookup"><span data-stu-id="07e1c-130">60 days</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="07e1c-131">Analogamente, i valori predefiniti per le impostazioni QoE selezionate vengono mostrati nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="07e1c-131">Similarly, default values for selected QoE settings are shown in this table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="07e1c-132">Proprietà</span><span class="sxs-lookup"><span data-stu-id="07e1c-132">Property</span></span></th>
<th><span data-ttu-id="07e1c-133">Descrizione</span><span class="sxs-lookup"><span data-stu-id="07e1c-133">Description</span></span></th>
<th><span data-ttu-id="07e1c-134">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="07e1c-134">Default Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07e1c-135">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="07e1c-135">EnableQoE</span></span></p></td>
<td><p><span data-ttu-id="07e1c-p107">Indica se il monitoraggio QoE è abilitato. Se impostata su True, tutti i record QoE verranno raccolti e scritti nel database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="07e1c-p107">Indicates whether or not QoE monitoring is enabled. If True, all QoE records will be collected and written to the monitoring database.</span></span></p></td>
<td><p><span data-ttu-id="07e1c-138">Vero</span><span class="sxs-lookup"><span data-stu-id="07e1c-138">True</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e1c-139">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="07e1c-139">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="07e1c-p108">Indica se i record QoE verranno eliminati periodicamente dal database. Se è impostata su True, i record verranno eliminati dopo il periodo di tempo specificato dalle proprietà KeepQoEDataForDays. Se False, i record QoE verranno mantenuti indefinitamente.</span><span class="sxs-lookup"><span data-stu-id="07e1c-p108">Indicates whether or not QoE records will periodically be deleted from the database. If True, records will be deleted after the time period specified by the KeepQoEDataForDays property. If False, QoE records will be maintained indefinitely.</span></span></p></td>
<td><p><span data-ttu-id="07e1c-143">Vero</span><span class="sxs-lookup"><span data-stu-id="07e1c-143">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07e1c-144">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="07e1c-144">KeepQoEDataForDays</span></span></p></td>
<td><p><span data-ttu-id="07e1c-p109">Indica il numero di giorni per cui i record QoE verranno mantenuti nel database. Qualsiasi record che ha superato il numero di giorni specificato verrà eliminato automaticamente, ma solo se l'eliminazione è stata abilitata.</span><span class="sxs-lookup"><span data-stu-id="07e1c-p109">Indicates the number of days that QoE records will be kept in the database; any records older than the specified number of days will automatically be deleted. However, this will occur only if purging has been enabled.</span></span></p>
<p><span data-ttu-id="07e1c-147">KeepCallDetailForDays può essere impostato su qualsiasi valore intero compreso tra 1 e 2562 giorni.</span><span class="sxs-lookup"><span data-stu-id="07e1c-147">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days.</span></span></p></td>
<td><p><span data-ttu-id="07e1c-148">60 giorni</span><span class="sxs-lookup"><span data-stu-id="07e1c-148">60 days</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="07e1c-p110">Per modificare queste impostazioni globali, utilizzare i cmdlet Set-CsCdrConfiguration e Set-CsQoEConfiguration. Ad esempio, questo comando, eseguito entro Lync Server Management Shell, consente di disabilitare il monitoraggio CDR a livello di ambito globale. Per ottenere questo risultato, la proprietà EnableCDR viene impostata su False ($False):</span><span class="sxs-lookup"><span data-stu-id="07e1c-p110">If you need to modify these global settings you can do so by using the Set-CsCdrConfiguration and the Set-CsQoEConfiguration cmdlets. For example, this command (run from within the Lync Server Management Shell) disables CDR monitoring at the global scope; that's done by setting the EnableCDR property to False ($False):</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $False

<span data-ttu-id="07e1c-151">Si noti che la disabilitazione del monitoraggio non annulla l'associazione dell'archivio di monitoraggio dal pool Front End e non disinstallerà o influirà in alcun modo sul database di monitoraggio back-end.</span><span class="sxs-lookup"><span data-stu-id="07e1c-151">Note that disabling monitoring does not dissociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="07e1c-152">Quando si utilizza Lync Server Management Shell per disabilitare il monitoraggio CDR o QoE, tutto ciò che è effettivamente possibile è arrestare temporaneamente Lync Server dalla raccolta e dall'archiviazione dei dati di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="07e1c-152">When you use Lync Server Management Shell to disable either CDR or QoE monitoring all you really do is temporarily stop Lync Server from collecting and archiving monitoring data.</span></span> <span data-ttu-id="07e1c-153">Se, in questo caso, si desidera riprendere la raccolta e l'archiviazione di dati CDR, è sufficiente impostare di nuovo la proprietà EnableCDR su True ($True):</span><span class="sxs-lookup"><span data-stu-id="07e1c-153">If you want to resume, in this case, the collection and archiving of CDR data, all you need to do is set the EnableCDR property back to True ($True):</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

<span data-ttu-id="07e1c-154">Analogamente, questo comando disabilita l'eliminazione dei record QoE a livello di ambito globale:</span><span class="sxs-lookup"><span data-stu-id="07e1c-154">Similarly, this command disables the purging of QoE records at the global scope:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnablePurging $False

<span data-ttu-id="07e1c-p112">Oltre alle impostazioni globali, le impostazioni di configurazione di CDR e QoE possono essere assegnate all'ambito del sito. Ciò offre una maggiore flessibilità a livello di gestione per il monitoraggio. Ad esempio, un amministratore può abilitare il monitoraggio CDR per il sito di Redmond ma disabilitarlo per il sito di Dublino. Per creare nuove impostazioni di configurazione CDR a livello di ambito di sito, utilizzare un comando simile a questo:</span><span class="sxs-lookup"><span data-stu-id="07e1c-p112">In addition to the global settings, CDR and QoE configurations settings can be assigned to the site scope. This provides additional management flexibility when it comes to monitoring; for example, an administrator can enable CDR monitoring for the Redmond site but disable CDR monitoring for the Dublin site. To create new CDR configuration settings at the site scope, use a command similar to this:</span></span>

    New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

<span data-ttu-id="07e1c-p113">È necessario ricordare che le impostazioni configurate a livello di ambito di sito hanno priorità maggiore rispetto alle impostazioni configurate a livello di ambito globale. Ad esempio, si supponga che il monitoraggio CDR sia abilitato a livello di ambito globale, ma disabilitato a livello di ambito di sito (per il sito di Redmond). Le informazioni sulle registrazioni dettagli chiamata non verranno quindi archiviate per gli utenti del sito di Redmond, ma verranno archiviate per gli utenti di altri siti, ovvero utenti gestiti dalle impostazioni globali invece che dalle impostazioni de sito di Redmond.</span><span class="sxs-lookup"><span data-stu-id="07e1c-p113">Keep in mind that settings configured at the site scope take precedence over settings configured at the global scope. For example, suppose CDR monitoring is enabled at the global scope, but disabled at the site scope (for the Redmond site). That means that call detail recording information will not be archived for users in the Redmond site. However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording information archived.</span></span>

<span data-ttu-id="07e1c-162">Nuove impostazioni di configurazione QoE possono essere create a livello di ambito di sito utilizzando un comando simile a questo:</span><span class="sxs-lookup"><span data-stu-id="07e1c-162">New QoE configuration settings can be created at the site scope by using a command like this one:</span></span>

    New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15

<span data-ttu-id="07e1c-163">Per ulteriori informazioni, digitare i comandi seguenti dall'interno di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="07e1c-163">For more information, type the following commands from within the Lync Server Management Shell:</span></span>

    Get-Help New-CsCdrConfiguration | more
    Get-Help Set-CsCdrConfiguration | more
    Get-Help New-CsQoEConfiguration | more
    Get-Help Set-CsQoEConfiguration | more

</div>

<span> </span>

</div>

</div>

</div>

