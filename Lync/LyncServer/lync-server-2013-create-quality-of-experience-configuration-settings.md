---
title: 'Lync Server 2013: creare impostazioni di configurazione della qualità delle esperienze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Quality of Experience configuration settings
ms:assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521006(v=OCS.15)
ms:contentKeyID: 48184357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f651da026dcf73253eaccada14332a7f2f5c1f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-quality-of-experience-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="4c3c9-102">Creare impostazioni di configurazione della qualità delle esperienze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c3c9-102">Create Quality of Experience configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c3c9-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="4c3c9-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="4c3c9-104">Le metriche sulla qualità delle esperienze (QoE) tengono traccia della qualità delle chiamate audio e video effettuate nell'organizzazione, tra cui il numero di pacchetti di rete persi, il rumore di fondo e la quantità di "jitter" (differenze nel ritardo del pacchetto).</span><span class="sxs-lookup"><span data-stu-id="4c3c9-104">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay).</span></span> <span data-ttu-id="4c3c9-105">Queste metriche sono archiviate in un database, oltre ad altri dati, ad esempio i record dettagli chiamata, che consentono di abilitare e disabilitare QoE indipendentemente da altre registrazioni di dati.</span><span class="sxs-lookup"><span data-stu-id="4c3c9-105">These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>

<span data-ttu-id="4c3c9-106">Quando si installa Microsoft Lync Server 2013, viene creata una singola raccolta globale di impostazioni di configurazione QoE.</span><span class="sxs-lookup"><span data-stu-id="4c3c9-106">When you install Microsoft Lync Server 2013, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="4c3c9-107">Gli amministratori hanno anche la possibilità di creare impostazioni personalizzate nell'ambito del sito.</span><span class="sxs-lookup"><span data-stu-id="4c3c9-107">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="4c3c9-108">Ogni volta che vengono usate queste impostazioni con ambito sito, hanno la precedenza sulle impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="4c3c9-108">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="4c3c9-109">Ad esempio, se crei impostazioni con ambito sito per il sito Redmond, le impostazioni (invece delle impostazioni globali) verranno usate per gestire i QoE in Redmond.</span><span class="sxs-lookup"><span data-stu-id="4c3c9-109">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage QoE in Redmond.</span></span>

<span data-ttu-id="4c3c9-110">Le impostazioni di configurazione QoE possono essere create usando il pannello di controllo di Lync Server o il cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="4c3c9-110">QoE configuration settings can be created by using either Lync Server Control Panel or the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet.</span></span> <span data-ttu-id="4c3c9-111">Se si usa il pannello di controllo di Lync Server per creare nuove impostazioni, saranno disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4c3c9-111">If you are using Lync Server Control Panel to create new settings the following options will be available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c3c9-112">Impostazione dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="4c3c9-112">UI Setting</span></span></th>
<th><span data-ttu-id="4c3c9-113">Parametro di PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c3c9-113">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="4c3c9-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4c3c9-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c3c9-115">Nome</span><span class="sxs-lookup"><span data-stu-id="4c3c9-115">Name</span></span></p></td>
<td><p><span data-ttu-id="4c3c9-116">Identity</span><span class="sxs-lookup"><span data-stu-id="4c3c9-116">Identity</span></span></p></td>
<td><p><span data-ttu-id="4c3c9-117">Identificatore univoco per le impostazioni da creare.</span><span class="sxs-lookup"><span data-stu-id="4c3c9-117">Unique identifier for the settings to be created.</span></span> <span data-ttu-id="4c3c9-118">Le impostazioni di configurazione QoE possono essere create solo nell'ambito del sito.</span><span class="sxs-lookup"><span data-stu-id="4c3c9-118">QoE configuration settings can only be created at the site scope.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c3c9-119">Abilitare il monitoraggio dei dati QoE</span><span class="sxs-lookup"><span data-stu-id="4c3c9-119">Enable monitoring of QoE data</span></span></p></td>
<td><p><span data-ttu-id="4c3c9-120">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="4c3c9-120">EnableQoE</span></span></p></td>
<td><p><span data-ttu-id="4c3c9-121">Specifica se i record QoE verranno raccolti e salvati nel database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="4c3c9-121">Specifies whether QoE records will be collected and saved to the monitoring database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c3c9-122">Abilitare l'eliminazione dei dati QoE</span><span class="sxs-lookup"><span data-stu-id="4c3c9-122">Enable purging of QoE data</span></span></p></td>
<td><p><span data-ttu-id="4c3c9-123">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="4c3c9-123">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="4c3c9-124">Specifica se i record verranno eliminati dopo che è trascorso il periodo definito nella proprietà <strong>Mantieni i dati QoE per una durata massima (giorni)</strong> .</span><span class="sxs-lookup"><span data-stu-id="4c3c9-124">Specifies whether records will be purged after the duration defined in the <strong>Keep QoE data for a maximum duration (days)</strong> property has elapsed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c3c9-125">Mantieni i dati QoE per la durata massima (giorni)</span><span class="sxs-lookup"><span data-stu-id="4c3c9-125">Keep QoE data for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="4c3c9-126">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="4c3c9-126">KeepQoEDataForDays</span></span></p></td>
<td><p><span data-ttu-id="4c3c9-127">Numero di giorni i dati QoE verranno archiviati prima di essere eliminati dal database.</span><span class="sxs-lookup"><span data-stu-id="4c3c9-127">Number of days QoE data will be stored before being purged from the database.</span></span> <span data-ttu-id="4c3c9-128">Questo valore viene ignorato se l'eliminazione è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="4c3c9-128">This value is ignored if purging is disabled.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="4c3c9-129">Il cmdlet New-CsQoEConfiguration include opzioni aggiuntive non disponibili nel pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4c3c9-129">The New-CsQoEConfiguration cmdlet includes additional options not available in Lync Server Control Panel.</span></span> <span data-ttu-id="4c3c9-130">Per altre informazioni, vedere l'argomento della Guida <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">New-CsQoEConfiguration</A> .</span><span class="sxs-lookup"><span data-stu-id="4c3c9-130">For more information, see the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">New-CsQoEConfiguration</A> help topic.</span></span>



</div>

<div>

## <a name="to-create-qoe-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="4c3c9-131">Per creare impostazioni di configurazione QoE tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="4c3c9-131">To create QoE configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="4c3c9-132">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="4c3c9-132">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="4c3c9-133">Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="4c3c9-133">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="4c3c9-134">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4c3c9-134">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4c3c9-135">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4c3c9-135">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4c3c9-136">Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **qualità dei dati dell'esperienza**.</span><span class="sxs-lookup"><span data-stu-id="4c3c9-136">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="4c3c9-137">Nella pagina **qualità di dati esperienza** fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="4c3c9-137">On the **Quality of Experience Data** page, click **New**.</span></span>

5.  <span data-ttu-id="4c3c9-138">In **Seleziona un sito**fare clic sul sito a cui applicare il criterio e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c3c9-138">In **Select a Site**, click the site to which the policy is to be applied, and click **OK**.</span></span>

6.  <span data-ttu-id="4c3c9-139">Nell' **impostazione nuova qualità dell'esperienza**, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4c3c9-139">In **New Quality of Experience Setting**, do the following:</span></span>
    
      - <span data-ttu-id="4c3c9-140">Selezionare **Abilita il monitoraggio dei dati QoE** per attivare il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="4c3c9-140">Select **Enable monitoring of QoE data** to turn on monitoring.</span></span>
    
      - <span data-ttu-id="4c3c9-141">Selezionare **Abilita l'eliminazione dei dati QoE** per attivare l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="4c3c9-141">Select **Enable purging of QoE data** to turn on purging.</span></span>
    
      - <span data-ttu-id="4c3c9-142">In **Mantieni QoE per la durata massima (giorni)** selezionare il numero massimo di giorni in cui devono essere conservati i record QoE.</span><span class="sxs-lookup"><span data-stu-id="4c3c9-142">In **Keep QoE for maximum duration (days)**, select the maximum number of days that QoE records should be retained.</span></span>

7.  <span data-ttu-id="4c3c9-143">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="4c3c9-143">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4c3c9-144">Creazione di impostazioni di configurazione QoE con i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c3c9-144">Creating QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4c3c9-145">Puoi creare impostazioni di configurazione QoE usando Windows PowerShell e il cmdlet New-CsQoEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="4c3c9-145">You can create QoE configuration settings by using Windows PowerShell and the New-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="4c3c9-146">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c3c9-146">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4c3c9-147">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="4c3c9-147">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="4c3c9-148">Per creare una nuova raccolta di impostazioni di configurazione QoE</span><span class="sxs-lookup"><span data-stu-id="4c3c9-148">To create a new collection of QoE configuration settings</span></span>

  - <span data-ttu-id="4c3c9-149">Questo comando crea una nuova raccolta di impostazioni di configurazione QoE applicate al sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="4c3c9-149">This command creates a new collection of QoE configuration settings applied to the Redmond site:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="4c3c9-150">Per creare una nuova raccolta di impostazioni di configurazione QoE in cui il monitoraggio QoE è disabilitato</span><span class="sxs-lookup"><span data-stu-id="4c3c9-150">To create a new collection of QoE configuration settings where QoE monitoring is disabled</span></span>

  - <span data-ttu-id="4c3c9-151">Poiché non sono stati specificati parametri (ad eccezione del parametro di identità obbligatorio) nel comando precedente, la nuova raccolta di impostazioni di configurazione utilizzerà i valori predefiniti per tutte le relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="4c3c9-151">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> <span data-ttu-id="4c3c9-152">Per creare impostazioni che usano valori di proprietà diversi, includere semplicemente il parametro e il valore del parametro appropriati.</span><span class="sxs-lookup"><span data-stu-id="4c3c9-152">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="4c3c9-153">Ad esempio, per creare una raccolta di impostazioni di configurazione della qualità delle esperienze che, per impostazione predefinita, consentono di disabilitare la registrazione QoE usare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="4c3c9-153">For example, to create a collection of Quality of Experience configuration settings that, by default, allow disable QoE recording use a command like this:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="4c3c9-154">Per specificare più valori di proprietà quando si crea una nuova raccolta di impostazioni di configurazione QoE</span><span class="sxs-lookup"><span data-stu-id="4c3c9-154">To specify multiple property values when creating a new collection of QoE configuration settings</span></span>

  - <span data-ttu-id="4c3c9-155">Puoi includere più valori di proprietà includendo più parametri.</span><span class="sxs-lookup"><span data-stu-id="4c3c9-155">You can multiple property values by including multiple parameters.</span></span> <span data-ttu-id="4c3c9-156">Ad esempio, questo comando Configura le nuove impostazioni per conservare i dati QoE per 30 giorni e per eliminare i vecchi dati in 3:00 AM:</span><span class="sxs-lookup"><span data-stu-id="4c3c9-156">For example, this command configures the new settings to keep QoE data for 30 days and to purge old data at 3:00 AM:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3

</div>

<span data-ttu-id="4c3c9-157">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="4c3c9-157">For more information, see the help topic for the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

