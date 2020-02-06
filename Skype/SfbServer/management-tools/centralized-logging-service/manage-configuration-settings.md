---
title: Gestire le impostazioni di configurazione del servizio di registrazione centralizzato in Skype for Business 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
description: 'Riepilogo: informazioni su come recuperare, aggiornare e creare impostazioni di configurazione per il servizio di registrazione centralizzato in Skype for Business Server 2015.'
ms.openlocfilehash: 95aa05cfcd31acda8e78927d674f3a19dff7ef56
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816585"
---
# <a name="manage-centralized-logging-service-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="89a54-103">Gestire le impostazioni di configurazione del servizio di registrazione centralizzato in Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="89a54-103">Manage Centralized Logging Service configuration settings in Skype for Business Server 2015</span></span>

<span data-ttu-id="89a54-104">**Riepilogo:** Informazioni su come recuperare, aggiornare e creare impostazioni di configurazione per il servizio di registrazione centralizzato in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="89a54-104">**Summary:** Learn how to retrieve, update, and create configuration settings for the Centralized Logging Service in Skype for Business Server 2015.</span></span>

<span data-ttu-id="89a54-105">Il servizio di registrazione centralizzato viene controllato e configurato tramite le impostazioni e i parametri creati e usati dal controller del servizio di registrazione centralizzato (CLSController) per inviare comandi all'agente del servizio di registrazione centralizzato del singolo computer ( CLSAgent).</span><span class="sxs-lookup"><span data-stu-id="89a54-105">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer's Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="89a54-106">L'agente elabora i comandi inviati e (nel caso di un comando Start) usa la configurazione degli scenari, i provider, la durata della traccia e i contrassegni per iniziare a raccogliere i log di traccia in base alle informazioni di configurazione fornite.</span><span class="sxs-lookup"><span data-stu-id="89a54-106">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="89a54-107">Non tutti i cmdlet di Windows PowerShell elencati per il servizio di registrazione centralizzata sono progettati per l'uso con le distribuzioni locali di Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="89a54-107">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Skype for Business Server 2015 on-premises deployments.</span></span> <span data-ttu-id="89a54-108">Anche se potrebbero sembrare utili, i cmdlet seguenti non sono progettati per funzionare con le distribuzioni locali di Skype for Business Server 2015:</span><span class="sxs-lookup"><span data-stu-id="89a54-108">Although they may appear to work, the following cmdlets are not designed to function with Skype for Business Server 2015 on-premises deployments:</span></span>

-  <span data-ttu-id="89a54-109">**Cmdlet CsClsRegion:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps)e [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="89a54-109">**CsClsRegion cmdlets:** [Get-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/get-csclsregion?view=skype-ps) ,[Set-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/set-csclsregion?view=skype-ps), [New-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/new-csclsregion?view=skype-ps), and [Remove-CsClsRegion](https://docs.microsoft.com/powershell/module/skype/remove-csclsregion?view=skype-ps).</span></span>
-  <span data-ttu-id="89a54-110">**Cmdlet CsClsSearchTerm:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) e [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="89a54-110">**CsClsSearchTerm cmdlets:** [Get-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/get-csclssearchterm?view=skype-ps) and [Set-CsClsSearchTerm](https://docs.microsoft.com/powershell/module/skype/set-csclssearchterm?view=skype-ps).</span></span>
-  <span data-ttu-id="89a54-111">**Cmdlet CsClsSecurityGroup:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps), [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps)e [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="89a54-111">**CsClsSecurityGroup cmdlets:** [Get-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/get-csclssecuritygroup?view=skype-ps), [Set-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/set-csclssecuritygroup?view=skype-ps),  [New-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/new-csclssecuritygroup?view=skype-ps), and [Remove-CsClsSecurityGroup](https://docs.microsoft.com/powershell/module/skype/remove-csclssecuritygroup?view=skype-ps).</span></span>

<span data-ttu-id="89a54-112">Le impostazioni definite in questi cmdlet non impediscono o causano alcun comportamento indesiderato, ma sono progettate per l'uso con Microsoft Office 365 e non restituiscono i risultati previsti nelle distribuzioni locali.</span><span class="sxs-lookup"><span data-stu-id="89a54-112">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft Office 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="89a54-113">Questo non significa che non sia possibile usare questi cmdlet in distribuzioni locali, ma il loro uso è un argomento più avanzato che non è incluso in questa documentazione.</span><span class="sxs-lookup"><span data-stu-id="89a54-113">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>

<span data-ttu-id="89a54-114">Il servizio di registrazione centralizzato può essere eseguito in un ambito che include un singolo computer o un pool di computer, in un ambito del sito (ovvero un sito definito, ad esempio il sito Redmond che contiene una raccolta di computer e pool nella distribuzione) o in un ambito globale (ovvero , tutti i computer e i pool della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="89a54-114">The Centralized Logging Service can be run at a scope that includes a single computer or a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="89a54-115">Per configurare l'ambito del servizio di registrazione centralizzato tramite Skype for Business Server Management Shell, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contiene uno di questi due gruppi.</span><span class="sxs-lookup"><span data-stu-id="89a54-115">To configure the Centralized Logging Service scope by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="89a54-116">Per restituire un elenco di tutti i ruoli RBAC a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati manualmente), eseguire il comando seguente da Skype for Business Server Management Shell o dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="89a54-116">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Skype for Business cmdlet>"}
```

<span data-ttu-id="89a54-117">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="89a54-117">For example:</span></span>

```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> <span data-ttu-id="89a54-118">Esistono differenze sostanziali tra i comandi della riga di comando che è possibile eseguire in Windows PowerShell o CLSController.</span><span class="sxs-lookup"><span data-stu-id="89a54-118">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="89a54-119">Windows PowerShell offre un metodo RTF per configurare e definire scenari e per riutilizzare questi scenari in modo significativo per gli scenari di risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="89a54-119">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="89a54-120">Mentre CLSController offre un modo rapido ed efficiente per emettere comandi e ottenere risultati, il set di comandi per CLSController è limitato dai comandi finiti disponibili dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="89a54-120">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="89a54-121">Diversamente dai cmdlet di Windows PowerShell, CLSController non è in grado di definire nuovi scenari, gestire l'ambito a livello di sito o globale e molte altre limitazioni di un set di comandi finito che non può essere configurato in modo dinamico.</span><span class="sxs-lookup"><span data-stu-id="89a54-121">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="89a54-122">Mentre CLSController offre un mezzo per l'esecuzione veloce, Windows PowerShell offre un mezzo per estendere la funzionalità del servizio di registrazione centralizzata oltre ciò che è possibile con CLSController.</span><span class="sxs-lookup"><span data-stu-id="89a54-122">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>

<span data-ttu-id="89a54-123">Un singolo ambito computer può essere definito durante l'esecuzione di un comando [Cerca-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) e [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) usando il parametro-Computers.</span><span class="sxs-lookup"><span data-stu-id="89a54-123">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps), [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps), [Start-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/start-csclslogging?view=skype-ps), [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps), [Sync-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/sync-csclslogging?view=skype-ps) and [Update-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/update-csclslogging?view=skype-ps) command using the -Computers parameter.</span></span> <span data-ttu-id="89a54-124">Il parametro-Computers accetta un elenco delimitato da virgole di nomi di dominio completi (FQDN) per il computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="89a54-124">The -Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

> [!TIP]
> <span data-ttu-id="89a54-125">È anche possibile definire i pool e un elenco di pool separati da virgole per cui si vogliono eseguire i comandi di registrazione.</span><span class="sxs-lookup"><span data-stu-id="89a54-125">You can also define -Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>

<span data-ttu-id="89a54-126">Il sito e gli ambiti globali sono definiti nei cmdlet **nuovo-**, **set-** e **Rimuovi-** servizio di registrazione centralizzato.</span><span class="sxs-lookup"><span data-stu-id="89a54-126">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="89a54-127">Gli esempi seguenti illustrano come impostare un sito e un ambito globale.</span><span class="sxs-lookup"><span data-stu-id="89a54-127">The following examples demonstrate how to set a site and a global scope.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="89a54-128">I comandi visualizzati possono contenere parametri e concetti trattati in altre sezioni.</span><span class="sxs-lookup"><span data-stu-id="89a54-128">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="89a54-129">I comandi di esempio hanno lo scopo di dimostrare l'uso del parametro **-Identity** per definire l'ambito e gli altri parametri sono inclusi per la completezza e per specificare l'ambito.</span><span class="sxs-lookup"><span data-stu-id="89a54-129">The example commands are intended to demonstrate the use of the **-Identity** parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="89a54-130">Per informazioni dettagliate sui cmdlet **Set-CsClsConfiguration** , vedere [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) nella documentazione Operations.</span><span class="sxs-lookup"><span data-stu-id="89a54-130">For details about the **Set-CsClsConfiguration** cmdlets, see [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps) in the Operations documentation.</span></span>

### <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="89a54-131">Per recuperare la configurazione del servizio di registrazione centralizzata corrente</span><span class="sxs-lookup"><span data-stu-id="89a54-131">To retrieve the current Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="89a54-132">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="89a54-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="89a54-133">Digitare quanto segue al prompt della riga di comando:</span><span class="sxs-lookup"><span data-stu-id="89a54-133">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration
   ```

<span data-ttu-id="89a54-134">Usare i cmdlet **New-CsClsConfiguration** e **Set-CsClsConfiguration** per creare una nuova configurazione o aggiornare una configurazione esistente. Quando si esegue **Get-CsClsConfiguration**, vengono visualizzate informazioni simili allo screenshot seguente, in cui la distribuzione ha attualmente la configurazione globale predefinita, ma non sono state definite configurazioni di sito:</span><span class="sxs-lookup"><span data-stu-id="89a54-134">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

![Output di esempio di Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)

### <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="89a54-136">Per recuperare la configurazione del servizio di registrazione centralizzata corrente dall'archivio locale del computer</span><span class="sxs-lookup"><span data-stu-id="89a54-136">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1. <span data-ttu-id="89a54-137">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="89a54-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="89a54-138">Digitare quanto segue al prompt della riga di comando:</span><span class="sxs-lookup"><span data-stu-id="89a54-138">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -LocalStore
   ```

<span data-ttu-id="89a54-139">Quando si usa il primo esempio in cui **Get-CsClsConfiguration** non specifica parametri, il comando fa riferimento all'Central Management store per i dati.</span><span class="sxs-lookup"><span data-stu-id="89a54-139">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="89a54-140">Se specifichi il parametro-LocalStore, il comando fa riferimento al computer LocalStore invece di Central Management store.</span><span class="sxs-lookup"><span data-stu-id="89a54-140">If you specify the parameter -LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>
### <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="89a54-141">Per recuperare un elenco di scenari attualmente definiti</span><span class="sxs-lookup"><span data-stu-id="89a54-141">To retrieve a listing of scenarios currently defined</span></span>

1. <span data-ttu-id="89a54-142">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="89a54-142">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="89a54-143">Digitare quanto segue al prompt della riga di comando:</span><span class="sxs-lookup"><span data-stu-id="89a54-143">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
   ```

    <span data-ttu-id="89a54-144">Ad esempio, per recuperare gli scenari definiti nell'ambito globale:</span><span class="sxs-lookup"><span data-stu-id="89a54-144">For example, to retrieve the scenarios that is defined at the global scope:</span></span>

   ```PowerShell
   Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios
   ```

<span data-ttu-id="89a54-145">Il cmdlet **Get-CsClsConfiguration** Visualizza sempre gli scenari che fanno parte di una determinata configurazione dell'ambito.</span><span class="sxs-lookup"><span data-stu-id="89a54-145">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope's configuration.</span></span> <span data-ttu-id="89a54-146">Nella maggior parte dei casi, tutti gli scenari non vengono visualizzati e vengono troncati.</span><span class="sxs-lookup"><span data-stu-id="89a54-146">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="89a54-147">Il comando usato qui elenca tutti gli scenari e le informazioni parziali sui provider, le impostazioni e i contrassegni usati.</span><span class="sxs-lookup"><span data-stu-id="89a54-147">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>
### <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="89a54-148">Per aggiornare un ambito globale per il servizio di registrazione centralizzato tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="89a54-148">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="89a54-149">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="89a54-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="89a54-150">Digitare quanto segue al prompt della riga di comando:</span><span class="sxs-lookup"><span data-stu-id="89a54-150">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="89a54-151">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="89a54-151">For example:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40
   ```

<span data-ttu-id="89a54-152">Il comando indica a CLSAgent su ogni computer e pool della distribuzione di impostare le dimensioni del valore di rollover nel file di traccia in 40 megabyte.</span><span class="sxs-lookup"><span data-stu-id="89a54-152">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes.</span></span> <span data-ttu-id="89a54-153">I computer e i pool in tutti i siti sono interessati dal comando e impostano il valore di rollover del log di traccia configurato su 40 megabyte.</span><span class="sxs-lookup"><span data-stu-id="89a54-153">Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>
### <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="89a54-154">Per aggiornare un ambito del sito per il servizio di registrazione centralizzato tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="89a54-154">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1. <span data-ttu-id="89a54-155">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="89a54-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="89a54-156">Digitare quanto segue al prompt della riga di comando:</span><span class="sxs-lookup"><span data-stu-id="89a54-156">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes>
   ```

   <span data-ttu-id="89a54-157">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="89a54-157">For example:</span></span>

   ```PowerShell
   Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40
   ```

> [!NOTE]
> <span data-ttu-id="89a54-158">Come indicato nell'esempio, la posizione predefinita dei file di log è%TEMP%\Tracing.</span><span class="sxs-lookup"><span data-stu-id="89a54-158">As noted in the example, the default location of the log files is %TEMP%\Tracing.</span></span> <span data-ttu-id="89a54-159">Tuttavia, poiché in realtà è CLSAgent che sta scrivendo il file e CSLAgent viene eseguito come servizio di rete, la variabile% TEMP% si espande in%WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span><span class="sxs-lookup"><span data-stu-id="89a54-159">However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

<span data-ttu-id="89a54-160">Il comando indica a CLSAgent su ogni computer e pool nel sito Redmond di impostare le dimensioni del valore di rollover nel file di traccia in 40 megabyte.</span><span class="sxs-lookup"><span data-stu-id="89a54-160">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes.</span></span> <span data-ttu-id="89a54-161">I computer e i pool in altri siti non saranno interessati dal comando e continueranno a usare il valore di rollover del log di traccia attualmente configurato per impostazione predefinita (20 megabyte) o durante l'inizio della sessione di registrazione.</span><span class="sxs-lookup"><span data-stu-id="89a54-161">Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>
### <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="89a54-162">Per creare una nuova configurazione del servizio di registrazione centralizzata</span><span class="sxs-lookup"><span data-stu-id="89a54-162">To create a new Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="89a54-163">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="89a54-163">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="89a54-164">Digitare quanto segue al prompt della riga di comando:</span><span class="sxs-lookup"><span data-stu-id="89a54-164">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
   ```

    > [!NOTE]
    > <span data-ttu-id="89a54-165">New-CsClsConfiguration offre l'accesso a un numero elevato di impostazioni di configurazione facoltative.</span><span class="sxs-lookup"><span data-stu-id="89a54-165">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="89a54-166">Per informazioni dettagliate sulle opzioni di configurazione, vedere [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) e [informazioni sulle impostazioni di configurazione del servizio di registrazione centralizzata](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).</span><span class="sxs-lookup"><span data-stu-id="89a54-166">For details about the configuration options, see [Get-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps) and [Understanding Centralized Logging Service Configuration Settings](https://technet.microsoft.com/library/3c34e600-0b91-43dc-b4cc-90b6a70ee12e.aspx).</span></span>

<span data-ttu-id="89a54-167">Ad esempio, per creare una nuova configurazione che definisce una cartella di rete per i file di cache, il periodo di rollover per i file di log e le dimensioni di rollover per i file di log, digitare:</span><span class="sxs-lookup"><span data-stu-id="89a54-167">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>

  ```PowerShell
  New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40
  ```

<span data-ttu-id="89a54-168">È consigliabile pianificare con attenzione la creazione di nuove configurazioni e come definire nuove proprietà per il servizio di registrazione centralizzata.</span><span class="sxs-lookup"><span data-stu-id="89a54-168">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="89a54-169">È necessario prestare attenzione a apportare modifiche e verificare che sia possibile comprendere l'impatto sulla possibilità di registrare correttamente gli scenari di problemi.</span><span class="sxs-lookup"><span data-stu-id="89a54-169">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="89a54-170">È necessario apportare modifiche alla configurazione che rafforzerà la possibilità di gestire i log in una dimensione e un periodo di rollover che consentiranno di risolvere i problemi quando si presenta.</span><span class="sxs-lookup"><span data-stu-id="89a54-170">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>
### <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="89a54-171">Per rimuovere una configurazione del servizio di registrazione centralizzata esistente</span><span class="sxs-lookup"><span data-stu-id="89a54-171">To remove an existing Centralized Logging Service configuration</span></span>

1. <span data-ttu-id="89a54-172">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="89a54-172">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="89a54-173">Digitare quanto segue al prompt della riga di comando:</span><span class="sxs-lookup"><span data-stu-id="89a54-173">Type the following at the command-line prompt:</span></span>

   ```PowerShell
   Remove-CsClsConfiguration -Identity <scope and name>
   ```

<span data-ttu-id="89a54-174">Ad esempio, per rimuovere una configurazione centralizzata del servizio di registrazione creata per aumentare il tempo di rollover del file di log, aumentare le dimensioni del file di log di rollover e impostare la posizione della cache del file di log su una condivisione di rete come segue:</span><span class="sxs-lookup"><span data-stu-id="89a54-174">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>

  ```PowerShell
  Remove-CsClsConfiguration -Identity "site:Redmond"
  ```

> [!NOTE]
> <span data-ttu-id="89a54-175">Questa è la nuova configurazione creata nella procedura "per creare una nuova configurazione del servizio di registrazione centralizzata".</span><span class="sxs-lookup"><span data-stu-id="89a54-175">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

<span data-ttu-id="89a54-176">Se si sceglie di rimuovere una configurazione a livello di sito, il sito utilizzerà le impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="89a54-176">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>
## <a name="see-also"></a><span data-ttu-id="89a54-177">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89a54-177">See also</span></span>

[<span data-ttu-id="89a54-178">Configurare i provider per il servizio di registrazione centralizzato in Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="89a54-178">Configure providers for Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-providers.md)

[<span data-ttu-id="89a54-179">Configurare gli scenari per il servizio di registrazione centralizzato in Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="89a54-179">Configure scenarios for the Centralized Logging Service in Skype for Business Server 2015</span></span>](configure-scenarios.md)

[<span data-ttu-id="89a54-180">Servizio di registrazione centralizzato in Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="89a54-180">Centralized Logging Service in Skype for Business 2015</span></span>](centralized-logging-service.md)

[<span data-ttu-id="89a54-181">Set-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="89a54-181">Set-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="89a54-182">Get-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="89a54-182">Get-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="89a54-183">New-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="89a54-183">New-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csclsconfiguration?view=skype-ps)

[<span data-ttu-id="89a54-184">Remove-CsClsConfiguration</span><span class="sxs-lookup"><span data-stu-id="89a54-184">Remove-CsClsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csclsconfiguration?view=skype-ps)
