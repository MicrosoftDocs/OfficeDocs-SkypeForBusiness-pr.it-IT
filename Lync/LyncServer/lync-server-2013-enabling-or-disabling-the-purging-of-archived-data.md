---
title: "Lync Server 2013: Abilitazione o disabilitazione dell'eliminazione dei dati archiviati"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling the purging of archived data
ms:assetid: 28cef09f-0970-4fc3-8315-f26689e3e187
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520968(v=OCS.15)
ms:contentKeyID: 48183678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e62ff615b4e2fcf5ec10f470993f985db0363a4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049158"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-the-purging-of-archived-data-in-lync-server-2013"></a><span data-ttu-id="3b735-102">Abilitazione o disabilitazione dell'eliminazione dei dati archiviati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b735-102">Enabling or disabling the purging of archived data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b735-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="3b735-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="3b735-104">Nel pannello di controllo di Lync Server 2013, è possibile utilizzare le configurazioni di archiviazione per abilitare e disabilitare l'eliminazione e configurare la modalità di implementazione dell'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="3b735-104">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable purging and configure how purging is implemented.</span></span> <span data-ttu-id="3b735-105">Sono incluse le configurazioni di archiviazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="3b735-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="3b735-106">Una configurazione globale creata per impostazione predefinita quando si distribuisce Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3b735-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="3b735-107">Configurazioni facoltative a livello di sito e di pool che possono essere create e utilizzate per specificare come deve essere implementata l'archiviazione per siti o pool specifici.</span><span class="sxs-lookup"><span data-stu-id="3b735-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="3b735-108">Le configurazioni di archiviazione vengono definite inizialmente al momento della distribuzione dell'archiviazione, ma è possibile modificarle, aggiungerle ed eliminarle dopo la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3b735-108">You initially set up Archiving configurations when you deploy Archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="3b735-109">Per informazioni dettagliate sulla modalità di implementazione delle configurazioni di archiviazione, incluse le opzioni che è possibile specificare e la gerarchia delle configurazioni di archiviazione, vedere [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, alla distribuzione o alla documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="3b735-109">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3b735-110">Per utilizzare l'archiviazione per gli utenti ospitati in Lync Server 2013, è necessario configurare i criteri di archiviazione per specificare se abilitare l'archiviazione per le comunicazioni interne, per le comunicazioni esterne o per entrambi.</span><span class="sxs-lookup"><span data-stu-id="3b735-110">To use archiving for users who are homed on Lync Server 2013 you must configure Archiving policies to specify whether to enable archiving for internal communications, for external communications, or for both.</span></span> <span data-ttu-id="3b735-111">Per impostazione predefinita, l'archiviazione non è abilitata né per le comunicazioni interne né per quelle esterne.</span><span class="sxs-lookup"><span data-stu-id="3b735-111">By default, archiving is not enabled for either internal or external communications.</span></span> <span data-ttu-id="3b735-112">Prima di abilitare Archiviazione nei criteri, è necessario specificare le configurazioni di archiviazione appropriate per la distribuzione corrente e, facoltativamente, per siti e pool specifici, come descritto in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="3b735-112">Prior to enabling Archiving in any policies, you should specify the appropriate Archiving configurations for your deployment and, optionally, for specific sites and pools, as described in this section.</span></span> <span data-ttu-id="3b735-113">Per informazioni dettagliate sull'abilitazione dell'archiviazione, vedere <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configurazione e assegnazione dei criteri di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3b735-113">For details about enabling Archiving, see <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuring and assigning Archiving policies in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="3b735-114">Se si decide dopo la distribuzione dell'archiviazione che si desidera utilizzare l'integrazione di Microsoft Exchange per archiviare i dati di archiviazione e i file nei server Exchange 2013 e tutti gli utenti sono ospitati nei server Exchange 2013, è necessario rimuovere la configurazione del database di SQL Server. dalla topologia.</span><span class="sxs-lookup"><span data-stu-id="3b735-114">If you decide after you deploy Archiving that you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers and all your users are homed on your Exchange 2013 servers, you should remove the SQL Server database configuration from your topology.</span></span> <span data-ttu-id="3b735-115">Per eseguire questa operazione, è necessario utilizzare Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="3b735-115">You must use Topology Builder to do this.</span></span> <span data-ttu-id="3b735-116">Per ulteriori informazioni, vedere <A href="lync-server-2013-changing-archiving-database-options.md">modifica delle opzioni del database di archiviazione in Lync Server 2013</A> nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="3b735-116">For details, see <A href="lync-server-2013-changing-archiving-database-options.md">Changing Archiving database options in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-purging-for-archiving"></a><span data-ttu-id="3b735-117">Per abilitare o disabilitare l'eliminazione per l'archiviazione</span><span class="sxs-lookup"><span data-stu-id="3b735-117">To enable or disable purging for archiving</span></span>

1.  <span data-ttu-id="3b735-118">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="3b735-118">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3b735-119">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3b735-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3b735-120">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3b735-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3b735-121">Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Configurazione archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="3b735-121">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="3b735-122">Fare clic sul nome della configurazione globale, di sito o di pool appropriata nell'elenco delle configurazioni di archiviazione, scegliere **Modifica**, **Mostra dettagli** ed eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3b735-122">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
      - <span data-ttu-id="3b735-123">Per abilitare l'eliminazione, selezionare la casella di controllo **Abilita eliminazione dei dati di archiviazione** ed eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3b735-123">To enable purging, select the **Enable purging of archiving data** check box and then do one of the following:</span></span>
        
          - <span data-ttu-id="3b735-124">Per eliminare tutti i record, fare clic su **Elimina dati di archiviazione esportati e archiviati dopo durata massima (giorni)** e quindi specificare il numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="3b735-124">To purge all records, click the **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="3b735-125">Per eliminare solo i dati che sono stati esportati, fare clic su **Elimina solo i dati di archiviazione esportati**.</span><span class="sxs-lookup"><span data-stu-id="3b735-125">To purge only the data that has been exported, click **Purge exported archiving data only**.</span></span>
    
      - <span data-ttu-id="3b735-126">Per disabilitare l'eliminazione, deselezionare la casella di controllo **Abilita eliminazione dei dati di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="3b735-126">To disable purging, clear the **Enable purging of archiving data** check box.</span></span>

5.  <span data-ttu-id="3b735-127">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="3b735-127">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-the-purging-of-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3b735-128">Abilitazione o disabilitazione dell'eliminazione dei dati di archiviazione mediante i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3b735-128">Enabling or Disabling the Purging of Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3b735-129">L'abilitazione e la disabilitazione dell'eliminazione automatica dei dati di archiviazione possono essere gestite tramite Windows PowerShell e il cmdlet **Set-CsArchivingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="3b735-129">Enabling and disabling the automated purging of archiving data can be managed by using Windows PowerShell and the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="3b735-130">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3b735-130">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3b735-131">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="3b735-131">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-the-purging-of-all-archiving-data"></a><span data-ttu-id="3b735-132">Per abilitare l'eliminazione di tutti i dati di archiviazione</span><span class="sxs-lookup"><span data-stu-id="3b735-132">To enable the purging of all archiving data</span></span>

  - <span data-ttu-id="3b735-133">Per abilitare l'eliminazione di tutti i dati di archiviazione, impostare la proprietà **EnablePurging** su true ($True).</span><span class="sxs-lookup"><span data-stu-id="3b735-133">To enable the purging of all archiving data set the **EnablePurging** property to true ($True).</span></span> <span data-ttu-id="3b735-134">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3b735-134">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
    
    <span data-ttu-id="3b735-135">Dopo l'esecuzione di questo comando, tutti i giorni Lync Server eliminerà tutti i record di archiviazione precedenti al valore specificato per la proprietà **KeepArchivingDataForDays** .</span><span class="sxs-lookup"><span data-stu-id="3b735-135">After this command is run, then every day Lync Server will purge all archiving records older than the value specified for the **KeepArchivingDataForDays** property.</span></span>

</div>

<div>

## <a name="to-enable-the-purging-only-of-exported-archiving-data"></a><span data-ttu-id="3b735-136">Per abilitare l'eliminazione solo dei dati di archiviazione esportati</span><span class="sxs-lookup"><span data-stu-id="3b735-136">To enable the purging only of exported archiving data</span></span>

  - <span data-ttu-id="3b735-137">Per limitare l'eliminazione ai record di archiviazione che sono stati esportati in un file di dati (utilizzando il cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) ), è inoltre necessario impostare la proprietà PurgeExportedArchivesOnly su True ($true).</span><span class="sxs-lookup"><span data-stu-id="3b735-137">To limit purging to archiving records that have been exported to a data file (by using the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet) you must also set the PurgeExportedArchivesOnly property to True ($True).</span></span> <span data-ttu-id="3b735-138">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3b735-138">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
    
    <span data-ttu-id="3b735-139">Dopo l'esecuzione di questo comando, Lync Server eliminerà solo i record di archiviazione che soddisfano i due criteri: 1) sono precedenti al valore specificato per la proprietà **KeepArchivingDataForDays** . e 2) sono stati esportati utilizzando il cmdlet **Export-CsArchivingData** .</span><span class="sxs-lookup"><span data-stu-id="3b735-139">After this command is run, Lync Server will only purge archiving records that meet two criteria: 1) they are older than the value specified for the **KeepArchivingDataForDays** property; and, 2) they have been exported by using the **Export-CsArchivingData** cmdlet.</span></span>

</div>

<div>

## <a name="to-disable-the-purging-of-all-archiving-data"></a><span data-ttu-id="3b735-140">Per disabilitare l'eliminazione di tutti i dati di archiviazione</span><span class="sxs-lookup"><span data-stu-id="3b735-140">To disable the purging of all archiving data</span></span>

  - <span data-ttu-id="3b735-141">Per disabilitare l'eliminazione automatica dei record di archiviazione, impostare la proprietà **EnablePurging** su False ($False).</span><span class="sxs-lookup"><span data-stu-id="3b735-141">To disable the automated purging of archiving records, set the **EnablePurging** property to False ($False).</span></span> <span data-ttu-id="3b735-142">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3b735-142">For example:</span></span>
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False

</div>

<span data-ttu-id="3b735-143">Per ulteriori informazioni, incluse le opzioni aggiuntive per l'eliminazione dei dati di archiviazione, vedere l'argomento della Guida relativo al cmdlet [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="3b735-143">For more information, including additional options for purging archiving data, see the help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3b735-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b735-144">See Also</span></span>


[<span data-ttu-id="3b735-145">Funzionamento dell'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b735-145">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="3b735-146">Configurazione e assegnazione dei criteri di archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b735-146">Configuring and assigning Archiving policies in Lync Server 2013</span></span>](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
[<span data-ttu-id="3b735-147">Gestione delle opzioni di configurazione dell'archiviazione in Lync Server 2013 per l'organizzazione, i siti e i pool</span><span class="sxs-lookup"><span data-stu-id="3b735-147">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

