---
title: 'Lync Server 2013: creare impostazioni di configurazione per la qualità delle esperienze'
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
ms.openlocfilehash: a94b7183be9927267796d3e2adaed12b3b71eaf6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501633"
---
# <a name="create-quality-of-experience-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="4a4a8-102">Creare le impostazioni di configurazione per la qualità delle esperienze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a4a8-102">Create Quality of Experience configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a4a8-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="4a4a8-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="4a4a8-p101">La metrica QoE registra la qualità delle chiamate audio e video effettuate nell'organizzazione, includendo informazioni quali il numero di pacchetti di rete persi, i rumori di fondo e il livello di "instabilità" (differenze nel ritardo dei pacchetti). Questa metrica viene archiviata in un database separatamente rispetto ad altri dati, ad esempio la registrazione dettagli chiamata, in modo che sia possibile abilitare e disabilitare il servizio QoE in maniera indipendente rispetto ad altre registrazioni di dati.</span><span class="sxs-lookup"><span data-stu-id="4a4a8-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>

<span data-ttu-id="4a4a8-106">Quando si installa Microsoft Lync Server 2013, viene creata una singola raccolta globale di impostazioni di configurazione QoE.</span><span class="sxs-lookup"><span data-stu-id="4a4a8-106">When you install Microsoft Lync Server 2013, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="4a4a8-107">Gli amministratori hanno inoltre la possibilità di creare impostazioni personalizzato con ambito sito.</span><span class="sxs-lookup"><span data-stu-id="4a4a8-107">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="4a4a8-108">Ogni volta che vengono utilizzate tali impostazioni con ambito sito, queste avranno la precedenza rispetto alle impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="4a4a8-108">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="4a4a8-109">Se si creano impostazioni con ambito sito per il sito Redmond, ad esempio, per gestire i criteri QoE nel sito di Redmond verranno utilizzate tali impostazioni, anziché quelle globali.</span><span class="sxs-lookup"><span data-stu-id="4a4a8-109">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage QoE in Redmond.</span></span>

<span data-ttu-id="4a4a8-110">È possibile creare le impostazioni di configurazione QoE utilizzando il pannello di controllo di Lync Server o il cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="4a4a8-110">QoE configuration settings can be created by using either Lync Server Control Panel or the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet.</span></span> <span data-ttu-id="4a4a8-111">Se si utilizza il pannello di controllo di Lync Server per creare nuove impostazioni, saranno disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4a4a8-111">If you are using Lync Server Control Panel to create new settings the following options will be available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a4a8-112">Impostazione dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="4a4a8-112">UI Setting</span></span></th>
<th><span data-ttu-id="4a4a8-113">Parametro di PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a4a8-113">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="4a4a8-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a4a8-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a4a8-115">Nome</span><span class="sxs-lookup"><span data-stu-id="4a4a8-115">Name</span></span></p></td>
<td><p><span data-ttu-id="4a4a8-116">Identità</span><span class="sxs-lookup"><span data-stu-id="4a4a8-116">Identity</span></span></p></td>
<td><p><span data-ttu-id="4a4a8-p104">Identificatore univoco delle impostazioni da creare. Le impostazioni di configurazione QoE possono essere create solo in ambito di sito.</span><span class="sxs-lookup"><span data-stu-id="4a4a8-p104">Unique identifier for the settings to be created. QoE configuration settings can only be created at the site scope.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a4a8-119">Abilita monitoraggio dei dati QoE</span><span class="sxs-lookup"><span data-stu-id="4a4a8-119">Enable monitoring of QoE data</span></span></p></td>
<td><p><span data-ttu-id="4a4a8-120">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="4a4a8-120">EnableQoE</span></span></p></td>
<td><p><span data-ttu-id="4a4a8-121">Indica se i record QoE verranno raccolti e salvati nel database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="4a4a8-121">Specifies whether QoE records will be collected and saved to the monitoring database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a4a8-122">Abilita eliminazione dei dati QoE</span><span class="sxs-lookup"><span data-stu-id="4a4a8-122">Enable purging of QoE data</span></span></p></td>
<td><p><span data-ttu-id="4a4a8-123">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="4a4a8-123">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="4a4a8-124">Indica se i record verranno cancellati dopo la scadenza specificata nella proprietà <strong>Mantieni dati QoE per durata massima (giorni)</strong>.</span><span class="sxs-lookup"><span data-stu-id="4a4a8-124">Specifies whether records will be purged after the duration defined in the <strong>Keep QoE data for a maximum duration (days)</strong> property has elapsed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a4a8-125">Mantieni dati QoE per durata massima (giorni)</span><span class="sxs-lookup"><span data-stu-id="4a4a8-125">Keep QoE data for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="4a4a8-126">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="4a4a8-126">KeepQoEDataForDays</span></span></p></td>
<td><p><span data-ttu-id="4a4a8-p105">Il numero di giorni in cui i dati QoE verranno archiviati prima di essere eliminati dal database. Questo valore viene ignorato se l'eliminazione è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="4a4a8-p105">Number of days QoE data will be stored before being purged from the database. This value is ignored if purging is disabled.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="4a4a8-129">Il cmdlet New-CsQoEConfiguration include opzioni aggiuntive non disponibili nel pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4a4a8-129">The New-CsQoEConfiguration cmdlet includes additional options not available in Lync Server Control Panel.</span></span> <span data-ttu-id="4a4a8-130">Per ulteriori informazioni, vedere l'argomento relativo alla guida di <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">New-CsQoEConfiguration</A> .</span><span class="sxs-lookup"><span data-stu-id="4a4a8-130">For more information, see the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">New-CsQoEConfiguration</A> help topic.</span></span>



</div>

<div>

## <a name="to-create-qoe-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="4a4a8-131">Per creare le impostazioni di configurazione QoE utilizzando il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="4a4a8-131">To create QoE configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="4a4a8-132">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="4a4a8-132">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="4a4a8-133">Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="4a4a8-133">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="4a4a8-134">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4a4a8-134">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4a4a8-135">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4a4a8-135">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4a4a8-136">Sulla barra di spostamento sinistra fare clic su **Monitoraggio e archiviazione** e quindi su **Dati QoE**.</span><span class="sxs-lookup"><span data-stu-id="4a4a8-136">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="4a4a8-137">Nella pagina **Dati QoE** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="4a4a8-137">On the **Quality of Experience Data** page, click **New**.</span></span>

5.  <span data-ttu-id="4a4a8-138">In **Seleziona un sito** fare clic sul sito a cui si desidera applicare i criteri e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a4a8-138">In **Select a Site**, click the site to which the policy is to be applied, and click **OK**.</span></span>

6.  <span data-ttu-id="4a4a8-139">In **Crea nuova impostazione QoE** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4a4a8-139">In **New Quality of Experience Setting**, do the following:</span></span>
    
      - <span data-ttu-id="4a4a8-140">Selezionare **Abilita monitoraggio dei dati QoE** per attivare il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="4a4a8-140">Select **Enable monitoring of QoE data** to turn on monitoring.</span></span>
    
      - <span data-ttu-id="4a4a8-141">Selezionare **Abilita eliminazione dei dati QoE** per attivare l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="4a4a8-141">Select **Enable purging of QoE data** to turn on purging.</span></span>
    
      - <span data-ttu-id="4a4a8-142">In **Mantieni dati QoE per durata massima (giorni)** selezionare il numero massimo di giorni per il mantenimento dei record QoE.</span><span class="sxs-lookup"><span data-stu-id="4a4a8-142">In **Keep QoE for maximum duration (days)**, select the maximum number of days that QoE records should be retained.</span></span>

7.  <span data-ttu-id="4a4a8-143">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="4a4a8-143">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4a4a8-144">Creazione di impostazioni di configurazione QoE tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a4a8-144">Creating QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4a4a8-145">È possibile creare impostazioni di configurazione QoE utilizzando Windows PowerShell e il cmdlet New-CsQoEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="4a4a8-145">You can create QoE configuration settings by using Windows PowerShell and the New-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="4a4a8-146">È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4a4a8-146">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4a4a8-147">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="4a4a8-147">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="4a4a8-148">Per creare una nuova raccolta di impostazioni di configurazione QoE</span><span class="sxs-lookup"><span data-stu-id="4a4a8-148">To create a new collection of QoE configuration settings</span></span>

  - <span data-ttu-id="4a4a8-149">Questo comando crea una nuova raccolta di impostazioni di configurazione QoE per il sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="4a4a8-149">This command creates a new collection of QoE configuration settings applied to the Redmond site:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="4a4a8-150">Per creare una nuova raccolta di impostazioni di configurazione QoE in cui il monitoraggio QoE è disabilitato</span><span class="sxs-lookup"><span data-stu-id="4a4a8-150">To create a new collection of QoE configuration settings where QoE monitoring is disabled</span></span>

  - <span data-ttu-id="4a4a8-p110">Dal momento che nel comando precedente non sono stati specificati parametri, oltre al parametro Identity obbligatorio, la nuova raccolta di impostazioni di configurazione utilizzerà i valori predefiniti per ogni proprietà. Per creare impostazioni che utilizzano valori di proprietà diversi, includere semplicemente il parametro e il valore di parametro appropriato. Per creare una raccolta di impostazioni di configurazione QoE che consenta la disabilitazione della registrazione QoE per impostazione predefinita, utilizzare un comando come il seguente:</span><span class="sxs-lookup"><span data-stu-id="4a4a8-p110">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Quality of Experience configuration settings that, by default, allow disable QoE recording use a command like this:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="4a4a8-154">Per specificare più valori di proprietà durante la creazione di una nuova raccolta di impostazioni di configurazione QoE</span><span class="sxs-lookup"><span data-stu-id="4a4a8-154">To specify multiple property values when creating a new collection of QoE configuration settings</span></span>

  - <span data-ttu-id="4a4a8-p111">È possibile specificare più valori di proprietà includendo più parametri. Questo comando, ad esempio, configura le nuove impostazioni per mantenere i dati QoE per 30 giorni ed eliminare i dati obsoleti alle 3.00:</span><span class="sxs-lookup"><span data-stu-id="4a4a8-p111">You can multiple property values by including multiple parameters. For example, this command configures the new settings to keep QoE data for 30 days and to purge old data at 3:00 AM:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3

</div>

<span data-ttu-id="4a4a8-157">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="4a4a8-157">For more information, see the help topic for the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

