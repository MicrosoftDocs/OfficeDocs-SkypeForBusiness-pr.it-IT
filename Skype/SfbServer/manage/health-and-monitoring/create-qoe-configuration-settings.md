---
title: Creare le impostazioni di configurazione di Qualità dell'esperienza in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: 'Riepilogo: informazioni sulle impostazioni QoE (Quality of Experience) in Skype for Business Server.'
ms.openlocfilehash: 8cce0731112166ae232b6273b556d37d693564e3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095350"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="3aefc-103">Creare le impostazioni di configurazione di Qualità dell'esperienza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3aefc-103">Create Quality of Experience configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="3aefc-104">**Riepilogo:** Informazioni sulle impostazioni QoE (Quality of Experience) in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3aefc-104">**Summary:** Learn about Quality of Experience (QoE) settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="3aefc-p101">La metrica QoE registra la qualità delle chiamate audio e video effettuate nell'organizzazione, includendo informazioni quali il numero di pacchetti di rete persi, i rumori di fondo e il livello di "instabilità" (differenze nel ritardo dei pacchetti). Questa metrica viene archiviata in un database separatamente rispetto ad altri dati, ad esempio la registrazione dettagli chiamata, in modo che sia possibile abilitare e disabilitare il servizio QoE in maniera indipendente rispetto ad altre registrazioni di dati.</span><span class="sxs-lookup"><span data-stu-id="3aefc-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>
  
<span data-ttu-id="3aefc-107">Quando si installa Skype for Business Server, viene creata automaticamente una singola raccolta globale di impostazioni di configurazione QoE.</span><span class="sxs-lookup"><span data-stu-id="3aefc-107">When you install Skype for Business Server, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="3aefc-108">Gli amministratori hanno inoltre la possibilità di creare impostazioni personalizzato con ambito sito.</span><span class="sxs-lookup"><span data-stu-id="3aefc-108">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="3aefc-109">Ogni volta che vengono utilizzate tali impostazioni con ambito sito, queste avranno la precedenza rispetto alle impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="3aefc-109">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="3aefc-110">Se si creano impostazioni con ambito sito per il sito Redmond, ad esempio, per gestire i criteri QoE nel sito di Redmond verranno utilizzate tali impostazioni, anziché quelle globali.</span><span class="sxs-lookup"><span data-stu-id="3aefc-110">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage QoE in Redmond.</span></span>
  
<span data-ttu-id="3aefc-111">Le impostazioni di configurazione QoE possono essere create utilizzando il Pannello di controllo di Skype for Business Server o il cmdlet [New-CsQoEConfiguration.](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="3aefc-111">QoE configuration settings can be created by using either Skype for Business Server Control Panel or the [New-CsQoEConfiguration](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="3aefc-112">Se si utilizza il Pannello di controllo di Skype for Business Server per creare nuove impostazioni, saranno disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3aefc-112">If you are using Skype for Business Server Control Panel to create new settings the following options will be available to you:</span></span>
  
|<span data-ttu-id="3aefc-113">**Impostazione dell'interfaccia utente**</span><span class="sxs-lookup"><span data-stu-id="3aefc-113">**UI setting**</span></span>|<span data-ttu-id="3aefc-114">**Parametro di PowerShell**</span><span class="sxs-lookup"><span data-stu-id="3aefc-114">**PowerShell parameter**</span></span>|<span data-ttu-id="3aefc-115">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="3aefc-115">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3aefc-116">Nome</span><span class="sxs-lookup"><span data-stu-id="3aefc-116">Name</span></span>  <br/> |<span data-ttu-id="3aefc-117">Identità</span><span class="sxs-lookup"><span data-stu-id="3aefc-117">Identity</span></span>  <br/> |<span data-ttu-id="3aefc-p104">Identificatore univoco delle impostazioni da creare. Le impostazioni di configurazione QoE possono essere create solo in ambito di sito.</span><span class="sxs-lookup"><span data-stu-id="3aefc-p104">Unique identifier for the settings to be created. QoE configuration settings can only be created at the site scope.</span></span>  <br/> |
|<span data-ttu-id="3aefc-120">Abilita monitoraggio dei dati QoE</span><span class="sxs-lookup"><span data-stu-id="3aefc-120">Enable monitoring of QoE data</span></span>  <br/> |<span data-ttu-id="3aefc-121">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="3aefc-121">EnableQoE</span></span>  <br/> |<span data-ttu-id="3aefc-122">Indica se i record QoE verranno raccolti e salvati nel database di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="3aefc-122">Specifies whether QoE records will be collected and saved to the monitoring database.</span></span>  <br/> |
|<span data-ttu-id="3aefc-123">Abilita eliminazione dei dati QoE</span><span class="sxs-lookup"><span data-stu-id="3aefc-123">Enable purging of QoE data</span></span>  <br/> |<span data-ttu-id="3aefc-124">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="3aefc-124">EnablePurging</span></span>  <br/> |<span data-ttu-id="3aefc-125">Indica se i record verranno cancellati dopo la scadenza specificata nella proprietà **Mantieni dati QoE per durata massima (giorni)**.</span><span class="sxs-lookup"><span data-stu-id="3aefc-125">Specifies whether records will be purged after the duration defined in the **Keep QoE data for a maximum duration (days)** property has elapsed.</span></span> <br/> |
|<span data-ttu-id="3aefc-126">Mantieni dati QoE per durata massima (giorni)</span><span class="sxs-lookup"><span data-stu-id="3aefc-126">Keep QoE data for maximum duration (days)</span></span>  <br/> |<span data-ttu-id="3aefc-127">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="3aefc-127">KeepQoEDataForDays</span></span>  <br/> |<span data-ttu-id="3aefc-p105">Il numero di giorni in cui i dati QoE verranno archiviati prima di essere eliminati dal database. Questo valore viene ignorato se l'eliminazione è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="3aefc-p105">Number of days QoE data will be stored before being purged from the database. This value is ignored if purging is disabled.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="3aefc-130">Il cmdlet New-CsQoEConfiguration include opzioni aggiuntive non disponibili nel Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3aefc-130">The New-CsQoEConfiguration cmdlet includes additional options not available in Skype for Business Server Control Panel.</span></span> <span data-ttu-id="3aefc-131">Per ulteriori informazioni, vedere [l'argomento della Guida New-CsQoEConfiguration.](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="3aefc-131">For more information, see the [New-CsQoEConfiguration](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) help topic.</span></span>
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="3aefc-132">Per creare le impostazioni di configurazione QoE tramite il Pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3aefc-132">To create QoE configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="3aefc-p107">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="3aefc-p107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="3aefc-135">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3aefc-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="3aefc-136">Sulla barra di spostamento sinistra fare clic su **Monitoraggio e archiviazione** e quindi su **Dati QoE**.</span><span class="sxs-lookup"><span data-stu-id="3aefc-136">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="3aefc-137">Nella pagina **Dati QoE** fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="3aefc-137">On the **Quality of Experience Data** page, click **New**.</span></span>
    
5. <span data-ttu-id="3aefc-138">In **Seleziona un sito** fare clic sul sito a cui si desidera applicare i criteri e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3aefc-138">In **Select a Site**, click the site to which the policy is to be applied, and click **OK**.</span></span>
    
6. <span data-ttu-id="3aefc-139">In **Crea nuova impostazione QoE** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3aefc-139">In **New Quality of Experience Setting**, do the following:</span></span>
    
   - <span data-ttu-id="3aefc-140">Selezionare **Abilita monitoraggio dei dati QoE** per attivare il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="3aefc-140">Select **Enable monitoring of QoE data** to turn on monitoring.</span></span>
    
   - <span data-ttu-id="3aefc-141">Selezionare **Abilita eliminazione dei dati QoE** per attivare l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="3aefc-141">Select **Enable purging of QoE data** to turn on purging.</span></span>
    
   - <span data-ttu-id="3aefc-142">In **Mantieni dati QoE per durata massima (giorni)** selezionare il numero massimo di giorni per il mantenimento dei record QoE.</span><span class="sxs-lookup"><span data-stu-id="3aefc-142">In **Keep QoE for maximum duration (days)**, select the maximum number of days that QoE records should be retained.</span></span>
    
7. <span data-ttu-id="3aefc-143">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="3aefc-143">Click **Commit**.</span></span>
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3aefc-144">Creazione di impostazioni di configurazione QoE tramite Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="3aefc-144">Creating QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3aefc-145">È possibile creare impostazioni di configurazione QoE utilizzando Windows PowerShell e il cmdlet New-CsQoEConfiguration QoE.</span><span class="sxs-lookup"><span data-stu-id="3aefc-145">You can create QoE configuration settings by using Windows PowerShell and the New-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="3aefc-146">È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3aefc-146">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3aefc-147">Per informazioni dettagliate sull'Windows PowerShell remoto per connettersi a Skype for Business Server, vedere l'articolo di blog ["Guida introduttiva: Gestione di Microsoft Lync Server 2010 tramite Remote PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="3aefc-147">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="3aefc-148">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3aefc-148">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="3aefc-149">Per creare una nuova raccolta di impostazioni di configurazione QoE</span><span class="sxs-lookup"><span data-stu-id="3aefc-149">To create a new collection of QoE configuration settings</span></span>

 <span data-ttu-id="3aefc-150">Questo comando crea una nuova raccolta di impostazioni di configurazione QoE per il sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="3aefc-150">This command creates a new collection of QoE configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="3aefc-151">Per creare una nuova raccolta di impostazioni di configurazione QoE in cui il monitoraggio QoE è disabilitato</span><span class="sxs-lookup"><span data-stu-id="3aefc-151">To create a new collection of QoE configuration settings where QoE monitoring is disabled</span></span>

 <span data-ttu-id="3aefc-p109">Dal momento che nel comando precedente non sono stati specificati parametri, oltre al parametro Identity obbligatorio, la nuova raccolta di impostazioni di configurazione utilizzerà i valori predefiniti per ogni proprietà. Per creare impostazioni che utilizzano valori di proprietà diversi, includere semplicemente il parametro e il valore di parametro appropriato. Per creare una raccolta di impostazioni di configurazione QoE che consenta la disabilitazione della registrazione QoE per impostazione predefinita, utilizzare un comando come il seguente:</span><span class="sxs-lookup"><span data-stu-id="3aefc-p109">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Quality of Experience configuration settings that, by default, allow disable QoE recording use a command like this:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="3aefc-155">Per specificare più valori di proprietà durante la creazione di una nuova raccolta di impostazioni di configurazione QoE</span><span class="sxs-lookup"><span data-stu-id="3aefc-155">To specify multiple property values when creating a new collection of QoE configuration settings</span></span>

 <span data-ttu-id="3aefc-p110">È possibile specificare più valori di proprietà includendo più parametri. Questo comando, ad esempio, configura le nuove impostazioni per mantenere i dati QoE per 30 giorni ed eliminare i dati obsoleti alle 3.00:</span><span class="sxs-lookup"><span data-stu-id="3aefc-p110">You can multiple property values by including multiple parameters. For example, this command configures the new settings to keep QoE data for 30 days and to purge old data at 3:00 AM:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

<span data-ttu-id="3aefc-158">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [New-CsQoEConfiguration.](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="3aefc-158">For more information, see the help topic for the [New-CsQoEConfiguration](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
