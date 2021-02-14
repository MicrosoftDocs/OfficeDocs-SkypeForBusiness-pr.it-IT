---
title: Gestire l'eliminazione dei dati archiviati in Skype for Business Server
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
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: "Riepilogo: informazioni su come gestire l'eliminazione dei dati archiviati per Skype for Business Server."
ms.openlocfilehash: aecc78f84b3cd4b745a96e534535c98c1739c156
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828536"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a><span data-ttu-id="c9520-103">Gestire l'eliminazione dei dati archiviati in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c9520-103">Manage purging of archived data in Skype for Business Server</span></span>

<span data-ttu-id="c9520-104">**Riepilogo:** Informazioni su come gestire l'eliminazione dei dati archiviati per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c9520-104">**Summary:** Learn how to manage purging of archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="c9520-105">Il database di archiviazione non è destinato alla conservazione a lungo termine e Skype for Business Server non fornisce una soluzione di e-discovery (ricerca) per i dati archiviati, quindi i dati devono essere spostati in un altro spazio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="c9520-105">The Archiving database is not intended for long-term retention, and Skype for Business Server does not provide an e-discovery (search) solution for archived data, so data needs to be moved to other storage.</span></span> <span data-ttu-id="c9520-106">Skype for Business Server offre uno strumento di esportazione delle sessioni che puoi usare per esportare i dati archiviati in trascrizioni disponibili per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="c9520-106">Skype for Business Server provides a session export tool that you can use to export archived data into searchable transcripts.</span></span> <span data-ttu-id="c9520-107">È necessario definire quando eliminare i dati archiviati ed esportati.</span><span class="sxs-lookup"><span data-stu-id="c9520-107">You need to define when to purge archived and exported data.</span></span> 
  
<span data-ttu-id="c9520-108">Per ulteriori informazioni sull'esportazione di dati utilizzando il cmdlet **Export-CsArchivingData,** vedere Esportare i dati archiviati [in Skype for Business Server.](export-archived-data.md)</span><span class="sxs-lookup"><span data-stu-id="c9520-108">For more information about exporting data by using the **Export-CsArchivingData** cmdlet, see [Export archived data in Skype for Business Server](export-archived-data.md).</span></span>
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a><span data-ttu-id="c9520-109">Gestire l'eliminazione dei dati tramite il Pannello di controllo</span><span class="sxs-lookup"><span data-stu-id="c9520-109">Manage purging of data by using the Control Panel</span></span>

<span data-ttu-id="c9520-110">Per gestire l'eliminazione dei dati archiviati tramite il Pannello di controllo:</span><span class="sxs-lookup"><span data-stu-id="c9520-110">To manage purging of archived data by using the Control Panel:</span></span>
  
1. <span data-ttu-id="c9520-111">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="c9520-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="c9520-112">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c9520-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="c9520-113">Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Configurazione archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="c9520-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="c9520-114">Fare clic sul nome della configurazione globale, di sito o di pool appropriata nell'elenco delle configurazioni di archiviazione, scegliere **Modifica**, **Mostra dettagli** ed eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9520-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="c9520-115">Per abilitare l'eliminazione, selezionare la casella di controllo **Abilita eliminazione dei dati di archiviazione** ed eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9520-115">To enable purging, select the **Enable purging of archiving data** check box and then do one of the following:</span></span>
    
     - <span data-ttu-id="c9520-116">Per eliminare tutti i record, fare clic su **Elimina dati di archiviazione esportati e archiviati dopo durata massima (giorni)** e quindi specificare il numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="c9520-116">To purge all records, click the **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="c9520-117">Per eliminare solo i dati che sono stati esportati, fare clic su **Elimina solo i dati di archiviazione esportati**.</span><span class="sxs-lookup"><span data-stu-id="c9520-117">To purge only the data that has been exported, click **Purge exported archiving data only**.</span></span>
    
   - <span data-ttu-id="c9520-118">Per disabilitare l'eliminazione, deselezionare la casella di controllo **Abilita eliminazione dei dati di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="c9520-118">To disable purging, clear the **Enable purging of archiving data** check box.</span></span>
    
5. <span data-ttu-id="c9520-119">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="c9520-119">Click **Commit**.</span></span>
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a><span data-ttu-id="c9520-120">Gestire l'eliminazione dei dati tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9520-120">Manage purging of data by using Windows PowerShell</span></span>

<span data-ttu-id="c9520-121">È possibile gestire l'eliminazione dei dati archiviati utilizzando i cmdlet Windows PowerShell seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9520-121">You can manage purging of archived data by using the following Windows PowerShell cmdlets:</span></span>
  
- <span data-ttu-id="c9520-122">Il cmdlet **Set-CsArchivingConfiguration** con il parametro EnablePurging consente di abilitare o disabilitare l'eliminazione dei dati archiviati.</span><span class="sxs-lookup"><span data-stu-id="c9520-122">**Set-CsArchivingConfiguration** cmdlet with the EnablePurging parameter lets you enable or disable purging of archived data.</span></span>
    
- <span data-ttu-id="c9520-123">**Invoke-CsArchivingDatabasePurge** consente di eliminare manualmente i record dal database di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="c9520-123">**Invoke-CsArchivingDatabasePurge** lets you manually purge records from the Archiving database.</span></span>
    
<span data-ttu-id="c9520-124">Ad esempio, il comando seguente consente l'eliminazione di tutti i dati archiviati.</span><span class="sxs-lookup"><span data-stu-id="c9520-124">For example, the following command enables the purging of all archived data.</span></span> <span data-ttu-id="c9520-125">Dopo l'esecuzione di questo comando, Skype for Business Server elimina tutti i record di archiviazione precedenti al valore specificato per il parametro KeepArchivingDataForDays.</span><span class="sxs-lookup"><span data-stu-id="c9520-125">After this command is run, Skype for Business Server will purge all archiving records older than the value specified for the KeepArchivingDataForDays parameter.</span></span> 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

<span data-ttu-id="c9520-126">Il comando seguente limita l'eliminazione ai record archiviati esportati in un file di dati (utilizzando il cmdlet **Export-CSArchivingData).**</span><span class="sxs-lookup"><span data-stu-id="c9520-126">The following command limits purging to archived records that have been exported to a data file (by using the **Export-CSArchivingData** cmdlet).</span></span> <span data-ttu-id="c9520-127">È inoltre necessario impostare il parametro PurgeExportedArchivesOnly su True ($True):</span><span class="sxs-lookup"><span data-stu-id="c9520-127">You must also set the PurgeExportedArchivesOnly parameter to True ($True):</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

<span data-ttu-id="c9520-128">Dopo l'esecuzione di questo comando, Skype for Business Server elimina solo i record di archiviazione che soddisfano due criteri: 1) sono precedenti al valore specificato per il parametro KeepArchivingDataForDays; e 2) sono stati esportati utilizzando il cmdlet **Export-CsArchivingData.**</span><span class="sxs-lookup"><span data-stu-id="c9520-128">After this command is run, Skype for Business Server will only purge archiving records that meet two criteria: 1) they are older than the value specified for the KeepArchivingDataForDays parameter; and, 2) they have been exported by using the **Export-CsArchivingData** cmdlet.</span></span>
  
<span data-ttu-id="c9520-129">Per disabilitare l'eliminazione automatica dei record di archiviazione, impostare il parametro EnablePurging su False ($False):</span><span class="sxs-lookup"><span data-stu-id="c9520-129">To disable the automated purging of archiving records, set the EnablePurging parameter to False ($False):</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

<span data-ttu-id="c9520-130">Nell'esempio seguente viene utilizzato il cmdlet **Invoke-CsArchivingDatabasePurge** per eliminare tutti i record di più di 24 ore dal database di archiviazione in atl-sql-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c9520-130">The following example uses the **Invoke-CsArchivingDatabasePurge** cmdlet to purge all the records more than 24 hours old from the archiving database on atl-sql-001.contoso.com.</span></span> <span data-ttu-id="c9520-131">Per assicurarsi che tutti i record siano stati eliminati, inclusi quelli che non sono stati esportati, il parametro PurgeExportedArchivesOnly è impostato su False ($False):</span><span class="sxs-lookup"><span data-stu-id="c9520-131">To ensure that all the records are deleted, including records that have not been exported, the PurgeExportedArchivesOnly parameter is set to False ($False):</span></span>
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
