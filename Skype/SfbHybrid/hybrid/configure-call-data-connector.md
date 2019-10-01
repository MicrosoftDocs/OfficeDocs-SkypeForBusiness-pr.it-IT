---
title: Configurare il connettore dati chiamata
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Istruzioni per la configurazione della chiamata Data Connector, che consente la visualizzazione di telemetria da Skype for business in locale con gli strumenti di Skype for business online.
ms.openlocfilehash: 48af644523e9872107c814aa330d2af2d9a4272f
ms.sourcegitcommit: 1f84b0edc4e418259b9f6392370e2cc4dc70df82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2019
ms.locfileid: "37328375"
---
# <a name="configure-call-data-connector"></a><span data-ttu-id="b487d-103">Configurare il connettore dati chiamata</span><span class="sxs-lookup"><span data-stu-id="b487d-103">Configure Call Data Connector</span></span>

<span data-ttu-id="b487d-104">Questo articolo descrive come configurare il connettore dati chiamata, un singolo set di strumenti che consente di visualizzare i dati di qualità delle chiamate di Skype for Business Server usando Skype for business online Call Quality Dashboard (Call Quality Dashboard) e strumenti di analisi delle chiamate (CA).</span><span class="sxs-lookup"><span data-stu-id="b487d-104">This article describes how to configure Call Data Connector--a single toolset that enables viewing Skype for Business Server Call Quality Data using Skype for Business Online Call Quality Dashboard (CQD) and Call Analytics (CA) tools.</span></span>

<span data-ttu-id="b487d-105">Per altre informazioni sui vantaggi e i prerequisiti per i connettori dei dati delle chiamate, ad esempio i requisiti dei ruoli e la configurazione della connettività ibrida, Vedi [Data Connector chiamata piano](plan-call-data-connector.md).</span><span class="sxs-lookup"><span data-stu-id="b487d-105">For more information about Call Data Connector benefits and pre-requisites, such as role requirements and setting up hybrid connectivity, see [Plan Call Data Connector](plan-call-data-connector.md).</span></span>

## <a name="enable-monitoring"></a><span data-ttu-id="b487d-106">Abilitare il monitoraggio</span><span class="sxs-lookup"><span data-stu-id="b487d-106">Enable Monitoring</span></span>
 
<span data-ttu-id="b487d-107">È necessario configurare la raccolta dati chiamate CDR (Call Data Recording) e QoE (Quality of Experience) nel monitoraggio del pool Front-End, con i database LCSCdr e QoEMetrics locali; in caso contrario, i dashboard di analisi delle chiamate e di qualità delle chiamate non consentiranno di usare i dati.</span><span class="sxs-lookup"><span data-stu-id="b487d-107">You must configure Call Data Recording (CDR) and Quality of Experience (QoE) data collection in your front end pool Monitoring,with local LCSCdr and QoEMetrics databases; otherwise, the Call Analytics and Call Quality Dashboards won’t get data to work with.</span></span> <span data-ttu-id="b487d-108">Prima di configurare il connettore dati chiamata, seguire i passaggi descritti in [distribuire il monitoraggio in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) per configurare CDR e QoE, nonché il monitoraggio di base.</span><span class="sxs-lookup"><span data-stu-id="b487d-108">Before you Configure Call Data Connector, follow the steps provided in [Deploy monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) to configure both CDR and QoE as well as basic Monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b487d-109">Il connettore dati chiamata non funzionerà se il monitoraggio non è abilitato nel pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="b487d-109">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

## <a name="enable-call-data-connector"></a><span data-ttu-id="b487d-110">Attiva connettore dati chiamata</span><span class="sxs-lookup"><span data-stu-id="b487d-110">Enable Call Data Connector</span></span>

<span data-ttu-id="b487d-111">Per configurare e abilitare il connettore dati chiamata, si utilizzeranno i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="b487d-111">To configure and enable Call Data Connector, you will use the following cmdlets:</span></span>

| <span data-ttu-id="b487d-112">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b487d-112">Cmdlet</span></span>| <span data-ttu-id="b487d-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b487d-113">Description</span></span>|
| :-----------------|---------------:|
| <span data-ttu-id="b487d-114">New-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="b487d-114">New-CsCloudCallDataConnection</span></span> | <span data-ttu-id="b487d-115">Un cmdlet online che stabilisce un agente di raccolta dati online.</span><span class="sxs-lookup"><span data-stu-id="b487d-115">An online cmdlet that establishes an online data collector.</span></span>|
| <span data-ttu-id="b487d-116">Get-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="b487d-116">Get-CsCloudCallDataConnection</span></span> | <span data-ttu-id="b487d-117">Un cmdlet online che recupera un agente di raccolta dati online esistente.</span><span class="sxs-lookup"><span data-stu-id="b487d-117">An online cmdlet that retrieves an existing online data collector.</span></span>|  
| <span data-ttu-id="b487d-118">Get-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="b487d-118">Get-CsCloudCallDataConnector</span></span> | <span data-ttu-id="b487d-119">Cmdlet locale che recupera le informazioni di connessione create dal cmdlet New-CsCloudCallDataConnection.</span><span class="sxs-lookup"><span data-stu-id="b487d-119">An on-premises cmdlet that retrieves the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |
| <span data-ttu-id="b487d-120">Set-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="b487d-120">Set-CsCloudCallDataConnector</span></span> | <span data-ttu-id="b487d-121">Cmdlet locale che salva una copia locale delle informazioni di connessione create dal cmdlet New-CsCloudCallDataConnection.</span><span class="sxs-lookup"><span data-stu-id="b487d-121">An on-premises cmdlet that saves an on-premises copy of the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |  
| <span data-ttu-id="b487d-122">Set-CsCloudCallDataConnectorConfiguration</span><span class="sxs-lookup"><span data-stu-id="b487d-122">Set-CsCloudCallDataConnectorConfiguration</span></span> | <span data-ttu-id="b487d-123">Cmdlet locale che consente di abilitare o disabilitare il connettore e personalizzare il livello di ambito.</span><span class="sxs-lookup"><span data-stu-id="b487d-123">An on-premises cmdlet that allows you to enable or disable the connector and customize the scope level.</span></span>|

> [!NOTE]
> <span data-ttu-id="b487d-124">Per cancellare la configurazione e ricominciare, usare il cmdlet Remove-csclouddatconnectorconfiguration.</span><span class="sxs-lookup"><span data-stu-id="b487d-124">To erase your configuration and start over, please use the Remove-csclouddatconnectorconfiguration cmdlet.</span></span>

### <a name="configure-your-environment"></a><span data-ttu-id="b487d-125">Configurare l'ambiente</span><span class="sxs-lookup"><span data-stu-id="b487d-125">Configure your environment</span></span> 

<span data-ttu-id="b487d-126">Per configurare l'ambiente per l'abilitazione di un agente di raccolta dati online, è necessario prima di tutto accedere a Skype for Business Online PowerShell come amministratore.</span><span class="sxs-lookup"><span data-stu-id="b487d-126">To configure your environment to enable an online data collector, you must first log in to Skype for Business Online PowerShell as an administrator.</span></span> <span data-ttu-id="b487d-127">Per altre informazioni, vedere [gestire Skype for business online con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="b487d-127">For more information, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="b487d-128">Esistono due metodi per accedere a PowerShell per Skype for business online:</span><span class="sxs-lookup"><span data-stu-id="b487d-128">There are two methods for logging in to Skype for Business Online PowerShell:</span></span>

- <span data-ttu-id="b487d-129">Da Skype for Business Server 2019 Management Shell (metodo consigliato)</span><span class="sxs-lookup"><span data-stu-id="b487d-129">From the Skype for Business Server 2019 management shell (recommended method)</span></span>
- <span data-ttu-id="b487d-130">Da un'altra sessione di PowerShell</span><span class="sxs-lookup"><span data-stu-id="b487d-130">From another PowerShell session</span></span>

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a><span data-ttu-id="b487d-131">Accedere a PowerShell per Skype for business online da Skype for Business Server Management Shell (metodo consigliato)</span><span class="sxs-lookup"><span data-stu-id="b487d-131">Log in to Skype for Business Online PowerShell from the Skype for Business Server management shell (recommended method)</span></span>

1. <span data-ttu-id="b487d-132">Se si Abilita il connettore per la prima volta, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="b487d-132">If enabling the connector for the first time, run the following command:</span></span>

   ```
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. <span data-ttu-id="b487d-133">Se viene visualizzato un messaggio di errore che la connessione esiste già, significa che la connessione dati della chiamata esiste già per il tenant.</span><span class="sxs-lookup"><span data-stu-id="b487d-133">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="b487d-134">In questo caso, Esegui il comando:</span><span class="sxs-lookup"><span data-stu-id="b487d-134">In this case, run the command:</span></span> 

   ```
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a><span data-ttu-id="b487d-135">Accedere a PowerShell per Skype for business online da un'altra sessione di PowerShell (metodo facoltativo)</span><span class="sxs-lookup"><span data-stu-id="b487d-135">Log in to Skype for Business Online PowerShell from another PowerShell session (optional method)</span></span>

1.  <span data-ttu-id="b487d-136">Se si Abilita il connettore per la prima volta, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="b487d-136">If enabling the connector for the first time, run the following command:</span></span> 

    ``` 
    New-CsCloudCallDataConnection 
    ```

2.  <span data-ttu-id="b487d-137">Se viene visualizzato un messaggio di errore che la connessione esiste già, significa che la connessione dati della chiamata esiste già per il tenant.</span><span class="sxs-lookup"><span data-stu-id="b487d-137">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="b487d-138">In questo caso, Esegui il comando:</span><span class="sxs-lookup"><span data-stu-id="b487d-138">In this case, run the command:</span></span> 

    ```
    Get-CsCloudCallDataConnection  
    ```

<span data-ttu-id="b487d-139">L'output dei comandi descritti sopra contiene un valore di token, che sarà necessario quando configuri l'ambiente locale come segue:</span><span class="sxs-lookup"><span data-stu-id="b487d-139">The output of the above commands contains a token value, which you will need when configuring your on-premises environment as follows:</span></span>

<span data-ttu-id="b487d-140">In Skype for Business Server Management Shell, specificare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="b487d-140">From within the Skype for Business Server management shell, specify the following command:</span></span>

```
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a><span data-ttu-id="b487d-141">Configurare l'ambito</span><span class="sxs-lookup"><span data-stu-id="b487d-141">Configure the scope</span></span>

<span data-ttu-id="b487d-142">Puoi abilitare il connettore dati chiamata per un determinato sito o per l'intera distribuzione di Skype for Business Server usando il cmdlet Set-CsCloudCallDataConnectorConfiguration da Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b487d-142">You can enable Call Data Connector for a particular site or for your entire Skype for Business Server deployment by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="b487d-143">Ad esempio, il comando seguente abilita il connettore data chiamata nell'ambito globale:</span><span class="sxs-lookup"><span data-stu-id="b487d-143">For example, the following command enables Call Data Connector at the global scope:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

<span data-ttu-id="b487d-144">Oltre alle impostazioni globali, è possibile assegnare le impostazioni di configurazione dei connettori dati all'ambito del sito.</span><span class="sxs-lookup"><span data-stu-id="b487d-144">In addition to the global settings, Call Data Connector configuration settings can be assigned to the site scope.</span></span> <span data-ttu-id="b487d-145">In questo caso è disponibile un'ulteriore flessibilità di gestione per il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="b487d-145">This provides additional management flexibility when it comes to monitoring.</span></span> <span data-ttu-id="b487d-146">Ad esempio, un amministratore può abilitare l'inoltro del connettore dei dati delle chiamate per il sito Redmond, ma disabilitare l'inoltro del connettore dei dati delle chiamate per il sito di Dublino, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="b487d-146">For example, an administrator can enable Call Data Connector forwarding for the Redmond site but disable Call Data Connector forwarding for the Dublin site, as shown in the following example:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

<span data-ttu-id="b487d-147">Le impostazioni configurate nell'ambito del sito hanno la precedenza sulle impostazioni configurate nell'ambito globale.</span><span class="sxs-lookup"><span data-stu-id="b487d-147">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="b487d-148">Supponiamo, ad esempio, che l'inoltro di Data Connector di chiamata sia abilitato nell'ambito globale, ma disabilitato nell'ambito del sito (per il sito Redmond).</span><span class="sxs-lookup"><span data-stu-id="b487d-148">For example, suppose Call Data Connector forwarding is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="b487d-149">Ciò significa che la registrazione dei dettagli delle chiamate e le informazioni QoE non verranno inoltrate per gli utenti nel sito Redmond.</span><span class="sxs-lookup"><span data-stu-id="b487d-149">That means that call detail recording and QoE information will not be forwarded for users in the Redmond site.</span></span> <span data-ttu-id="b487d-150">Tuttavia, gli utenti di altri siti, ovvero gli utenti gestiti dalle impostazioni globali anziché dalle impostazioni del sito Redmond, avranno inoltrato le informazioni relative alla registrazione dei dettagli delle chiamate e agli QoE.</span><span class="sxs-lookup"><span data-stu-id="b487d-150">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording and QoE information forwarded.</span></span>

<span data-ttu-id="b487d-151">Nella tabella seguente sono illustrati i valori delle impostazioni di uso più comune usate da connettore dati chiamata:</span><span class="sxs-lookup"><span data-stu-id="b487d-151">Values for the most commonly used settings used by Call Data Connector are shown in the following table:</span></span>  

|<span data-ttu-id="b487d-152">Proprietà</span><span class="sxs-lookup"><span data-stu-id="b487d-152">Property</span></span>|<span data-ttu-id="b487d-153">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b487d-153">Description</span></span>|<span data-ttu-id="b487d-154">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="b487d-154">Default value</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b487d-155">EnableCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="b487d-155">EnableCallDataConnector</span></span>  <br/> |<span data-ttu-id="b487d-156">Indica se il connettore dati della chiamata è abilitato.</span><span class="sxs-lookup"><span data-stu-id="b487d-156">Indicates whether Call Data Connector is enabled.</span></span> <span data-ttu-id="b487d-157">Se true, il monitoraggio dei record verrà inoltrato al monitoraggio online.</span><span class="sxs-lookup"><span data-stu-id="b487d-157">If True, monitoring records will be forwarded to online monitoring.</span></span>  <br/> |<span data-ttu-id="b487d-158">$False</span><span class="sxs-lookup"><span data-stu-id="b487d-158">$False</span></span>  <br/> |
| <span data-ttu-id="b487d-159">Identity</span><span class="sxs-lookup"><span data-stu-id="b487d-159">Identity</span></span> | <span data-ttu-id="b487d-160">Determina il livello di ambito per il comando: globale o sito.</span><span class="sxs-lookup"><span data-stu-id="b487d-160">Determines the scope level for the command: global or site.</span></span>   | <span data-ttu-id="b487d-161">globale</span><span class="sxs-lookup"><span data-stu-id="b487d-161">global</span></span>  |

## <a name="disable-call-data-connector"></a><span data-ttu-id="b487d-162">Disattiva connettore dati chiamata</span><span class="sxs-lookup"><span data-stu-id="b487d-162">Disable Call Data Connector</span></span>

<span data-ttu-id="b487d-163">La disabilitazione del connettore dati chiamata non dissocia l'archivio di monitoraggio dal pool Front-End, né Disinstalla o influisce in altro modo sul database di monitoraggio del backend.</span><span class="sxs-lookup"><span data-stu-id="b487d-163">Disabling Call Data Connector does not disassociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="b487d-164">Quando si disattiva chiamata Data Connector, viene impedito a Skype for Business Server di caricare i dati delle chiamate nel cloud.</span><span class="sxs-lookup"><span data-stu-id="b487d-164">When you disable Call Data Connector, you stop Skype for Business Server from uploading call data to the cloud.</span></span> 

<span data-ttu-id="b487d-165">Puoi disabilitare il connettore dati chiamata usando il cmdlet Set-CsCloudCallDataConnectorConfiguration dall'interno di Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b487d-165">You disable Call Data Connector by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="b487d-166">Ad esempio, il comando seguente disabilita la chiamata Data Connector nell'ambito globale impostando la proprietà EnableCallDataConnector su $False:</span><span class="sxs-lookup"><span data-stu-id="b487d-166">For example, the following command disables Call Data Connector at the global scope by setting the EnableCallDataConnector property to $False:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

<span data-ttu-id="b487d-167">Se si vuole riprendere a caricare i dati delle chiamate nel cloud, impostare la proprietà EnableCallDataConnector su $True, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="b487d-167">If you want to resume uploading call data to the cloud, set the EnableCallDataConnector property back to $True, as shown in the following example:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a><span data-ttu-id="b487d-168">Visualizzare i dati locali tramite il dashboard online</span><span class="sxs-lookup"><span data-stu-id="b487d-168">View on-premises data through the online dashboard</span></span>

 <span data-ttu-id="b487d-169">Dopo aver abilitato il connettore dati chiamata, è possibile visualizzare i dati delle chiamate locali nel dashboard di analisi delle chiamate o nel dashboard qualità chiamata, come descritto in [usare la chiamata analitica per risolvere i problemi di qualità scadente](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) e [attivare e usare il dashboard qualità chiamata per Microsoft teams e Skype for business online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).</span><span class="sxs-lookup"><span data-stu-id="b487d-169">After Call Data Connector is enabled, you can view your on-premises call data on the Call Analytics dashboard or Call Quality Dashboard as described in  [Use Call Analytics to troubleshoot poor quality](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) and [Turn on and use Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="b487d-170">Per altre informazioni</span><span class="sxs-lookup"><span data-stu-id="b487d-170">For more information</span></span>

<span data-ttu-id="b487d-171">Per altre informazioni sui cmdlet, è possibile usare il comando Get-Help da Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b487d-171">For more information on the cmdlets, you can use the Get-Help command from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="b487d-172">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b487d-172">For example:</span></span>

<span data-ttu-id="b487d-173">Get-Help Get-CsCloudCallDataConnector | più</span><span class="sxs-lookup"><span data-stu-id="b487d-173">Get-Help Get-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="b487d-174">Get-Help Set-CsCloudCallDataConnector | più</span><span class="sxs-lookup"><span data-stu-id="b487d-174">Get-Help Set-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="b487d-175">Get-Help Set-CsCloudCallDataConnectorConfiguration | più</span><span class="sxs-lookup"><span data-stu-id="b487d-175">Get-Help Set-CsCloudCallDataConnectorConfiguration | more</span></span>
