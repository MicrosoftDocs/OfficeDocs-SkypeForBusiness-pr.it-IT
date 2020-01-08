---
title: Configurare il connettore dei dati di chiamata
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Istruzioni per la configurazione del connettore dei dati di chiamata, che consente di visualizzare la telemetria da Skype for business in locale tramite gli strumenti di Skype for business online.
ms.openlocfilehash: 4d472ce49a3059df7286c647b013abe321b9fd15
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "40963044"
---
# <a name="configure-call-data-connector"></a><span data-ttu-id="78b6a-103">Configurare il connettore dei dati di chiamata</span><span class="sxs-lookup"><span data-stu-id="78b6a-103">Configure Call Data Connector</span></span>

<span data-ttu-id="78b6a-104">In questo articolo viene descritto come configurare il connettore dei dati di chiamata, ovvero un singolo set di strumenti che consente di visualizzare i dati di qualità delle chiamate di Skype for Business Server utilizzando Skype for business online Call Quality Dashboard (CQD) e gli strumenti di analisi delle chiamate (CA).</span><span class="sxs-lookup"><span data-stu-id="78b6a-104">This article describes how to configure Call Data Connector--a single toolset that enables viewing Skype for Business Server Call Quality Data using Skype for Business Online Call Quality Dashboard (CQD) and Call Analytics (CA) tools.</span></span>

<span data-ttu-id="78b6a-105">Per ulteriori informazioni sui vantaggi e i prerequisiti del connettore dei dati di chiamata, ad esempio i requisiti dei ruoli e la configurazione della connettività ibrida, vedere [Plan Call Data Connector](plan-call-data-connector.md).</span><span class="sxs-lookup"><span data-stu-id="78b6a-105">For more information about Call Data Connector benefits and pre-requisites, such as role requirements and setting up hybrid connectivity, see [Plan Call Data Connector](plan-call-data-connector.md).</span></span>

## <a name="enable-monitoring"></a><span data-ttu-id="78b6a-106">Abilitare il monitoraggio</span><span class="sxs-lookup"><span data-stu-id="78b6a-106">Enable Monitoring</span></span>
 
<span data-ttu-id="78b6a-107">È necessario configurare la raccolta dati di registrazione dati di chiamata (CDR) e la qualità di esperienza (QoE) nel monitoraggio del pool Front End, con i database di LCSCdr e QoEMetrics locali. in caso contrario, i dashboard di analisi chiamata e qualità chiamata non consentiranno di utilizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="78b6a-107">You must configure Call Data Recording (CDR) and Quality of Experience (QoE) data collection in your front end pool Monitoring,with local LCSCdr and QoEMetrics databases; otherwise, the Call Analytics and Call Quality Dashboards won’t get data to work with.</span></span> <span data-ttu-id="78b6a-108">Prima di configurare il connettore dei dati di chiamata, seguire i passaggi descritti in [Deploy Monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) per configurare sia CdR sia QoE, nonché il monitoraggio di base.</span><span class="sxs-lookup"><span data-stu-id="78b6a-108">Before you Configure Call Data Connector, follow the steps provided in [Deploy monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) to configure both CDR and QoE as well as basic Monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="78b6a-109">Il connettore dei dati di chiamata non funzionerà se il monitoraggio non è abilitato nel pool Front end.</span><span class="sxs-lookup"><span data-stu-id="78b6a-109">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

## <a name="enable-call-data-connector"></a><span data-ttu-id="78b6a-110">Attiva connettore dati chiamata</span><span class="sxs-lookup"><span data-stu-id="78b6a-110">Enable Call Data Connector</span></span>

<span data-ttu-id="78b6a-111">Per configurare e abilitare il connettore dei dati di chiamata, verranno utilizzati i seguenti cmdlet:</span><span class="sxs-lookup"><span data-stu-id="78b6a-111">To configure and enable Call Data Connector, you will use the following cmdlets:</span></span>

| <span data-ttu-id="78b6a-112">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="78b6a-112">Cmdlet</span></span>| <span data-ttu-id="78b6a-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="78b6a-113">Description</span></span>|
| :-----------------|---------------:|
| <span data-ttu-id="78b6a-114">New-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="78b6a-114">New-CsCloudCallDataConnection</span></span> | <span data-ttu-id="78b6a-115">Cmdlet online che consente di stabilire un agente di raccolta dati online.</span><span class="sxs-lookup"><span data-stu-id="78b6a-115">An online cmdlet that establishes an online data collector.</span></span>|
| <span data-ttu-id="78b6a-116">Get-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="78b6a-116">Get-CsCloudCallDataConnection</span></span> | <span data-ttu-id="78b6a-117">Cmdlet online che consente di recuperare un agente di raccolta dati online esistente.</span><span class="sxs-lookup"><span data-stu-id="78b6a-117">An online cmdlet that retrieves an existing online data collector.</span></span>|  
| <span data-ttu-id="78b6a-118">Get-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="78b6a-118">Get-CsCloudCallDataConnector</span></span> | <span data-ttu-id="78b6a-119">Cmdlet locale che consente di recuperare le informazioni di connessione create dal cmdlet New-CsCloudCallDataConnection.</span><span class="sxs-lookup"><span data-stu-id="78b6a-119">An on-premises cmdlet that retrieves the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |
| <span data-ttu-id="78b6a-120">Set-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="78b6a-120">Set-CsCloudCallDataConnector</span></span> | <span data-ttu-id="78b6a-121">Cmdlet locale che consente di salvare una copia locale delle informazioni di connessione create dal cmdlet New-CsCloudCallDataConnection.</span><span class="sxs-lookup"><span data-stu-id="78b6a-121">An on-premises cmdlet that saves an on-premises copy of the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |  
| <span data-ttu-id="78b6a-122">Set-CsCloudCallDataConnectorConfiguration</span><span class="sxs-lookup"><span data-stu-id="78b6a-122">Set-CsCloudCallDataConnectorConfiguration</span></span> | <span data-ttu-id="78b6a-123">Cmdlet locale che consente di abilitare o disabilitare il connettore e personalizzare il livello di ambito.</span><span class="sxs-lookup"><span data-stu-id="78b6a-123">An on-premises cmdlet that allows you to enable or disable the connector and customize the scope level.</span></span>|

> [!NOTE]
> <span data-ttu-id="78b6a-124">Per cancellare la configurazione e ricominciare, utilizzare il cmdlet Remove-csclouddatconnectorconfiguration.</span><span class="sxs-lookup"><span data-stu-id="78b6a-124">To erase your configuration and start over, please use the Remove-csclouddatconnectorconfiguration cmdlet.</span></span>

### <a name="configure-your-environment"></a><span data-ttu-id="78b6a-125">Configurare l'ambiente</span><span class="sxs-lookup"><span data-stu-id="78b6a-125">Configure your environment</span></span> 

<span data-ttu-id="78b6a-126">Per configurare l'ambiente per l'abilitazione di un agente di raccolta dati online, è necessario innanzitutto accedere a PowerShell per Skype for business online come amministratore.</span><span class="sxs-lookup"><span data-stu-id="78b6a-126">To configure your environment to enable an online data collector, you must first log in to Skype for Business Online PowerShell as an administrator.</span></span> <span data-ttu-id="78b6a-127">Per ulteriori informazioni, vedere [Manage Skype for business online con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="78b6a-127">For more information, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="78b6a-128">Esistono due metodi per accedere a PowerShell per Skype for business online:</span><span class="sxs-lookup"><span data-stu-id="78b6a-128">There are two methods for logging in to Skype for Business Online PowerShell:</span></span>

- <span data-ttu-id="78b6a-129">Dalla shell di gestione di Skype for Business Server 2019 (metodo consigliato)</span><span class="sxs-lookup"><span data-stu-id="78b6a-129">From the Skype for Business Server 2019 management shell (recommended method)</span></span>
- <span data-ttu-id="78b6a-130">Da un'altra sessione di PowerShell</span><span class="sxs-lookup"><span data-stu-id="78b6a-130">From another PowerShell session</span></span>

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a><span data-ttu-id="78b6a-131">Accedere a PowerShell di Skype for business online da Skype for Business Server Management Shell (metodo consigliato)</span><span class="sxs-lookup"><span data-stu-id="78b6a-131">Log in to Skype for Business Online PowerShell from the Skype for Business Server management shell (recommended method)</span></span>

1. <span data-ttu-id="78b6a-132">Se si Abilita il connettore per la prima volta, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="78b6a-132">If enabling the connector for the first time, run the following command:</span></span>

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. <span data-ttu-id="78b6a-133">Se viene visualizzato un errore che la connessione esiste già, significa che la connessione dati di chiamata esiste già per il tenant.</span><span class="sxs-lookup"><span data-stu-id="78b6a-133">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="78b6a-134">In questo caso, eseguire il comando:</span><span class="sxs-lookup"><span data-stu-id="78b6a-134">In this case, run the command:</span></span> 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a><span data-ttu-id="78b6a-135">Accedere a PowerShell di Skype for business online da un'altra sessione di PowerShell (metodo facoltativo)</span><span class="sxs-lookup"><span data-stu-id="78b6a-135">Log in to Skype for Business Online PowerShell from another PowerShell session (optional method)</span></span>

1.  <span data-ttu-id="78b6a-136">Se si Abilita il connettore per la prima volta, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="78b6a-136">If enabling the connector for the first time, run the following command:</span></span> 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  <span data-ttu-id="78b6a-137">Se viene visualizzato un errore che la connessione esiste già, significa che la connessione dati di chiamata esiste già per il tenant.</span><span class="sxs-lookup"><span data-stu-id="78b6a-137">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="78b6a-138">In questo caso, eseguire il comando:</span><span class="sxs-lookup"><span data-stu-id="78b6a-138">In this case, run the command:</span></span> 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

<span data-ttu-id="78b6a-139">L'output dei comandi precedenti contiene un valore di token, che sarà necessario quando si configura l'ambiente locale, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="78b6a-139">The output of the above commands contains a token value, which you will need when configuring your on-premises environment as follows:</span></span>

<span data-ttu-id="78b6a-140">In Skype for Business Server Management Shell, specificare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="78b6a-140">From within the Skype for Business Server management shell, specify the following command:</span></span>

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a><span data-ttu-id="78b6a-141">Configurare l'ambito</span><span class="sxs-lookup"><span data-stu-id="78b6a-141">Configure the scope</span></span>

<span data-ttu-id="78b6a-142">È possibile abilitare il connettore dati chiamata per un sito specifico o per l'intera distribuzione di Skype for Business Server utilizzando il cmdlet Set-CsCloudCallDataConnectorConfiguration da Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="78b6a-142">You can enable Call Data Connector for a particular site or for your entire Skype for Business Server deployment by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="78b6a-143">Ad esempio, il comando seguente consente di abilitare il connettore dei dati di chiamata nell'ambito globale:</span><span class="sxs-lookup"><span data-stu-id="78b6a-143">For example, the following command enables Call Data Connector at the global scope:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

<span data-ttu-id="78b6a-144">Oltre alle impostazioni globali, le impostazioni di configurazione del connettore dei dati delle chiamate possono essere assegnate all'ambito del sito.</span><span class="sxs-lookup"><span data-stu-id="78b6a-144">In addition to the global settings, Call Data Connector configuration settings can be assigned to the site scope.</span></span> <span data-ttu-id="78b6a-145">In questo modo viene fornita una maggiore flessibilità di gestione per il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="78b6a-145">This provides additional management flexibility when it comes to monitoring.</span></span> <span data-ttu-id="78b6a-146">Ad esempio, un amministratore può abilitare l'inoltro del connettore dei dati di chiamata per il sito di Redmond ma disabilitare l'inoltro dei connettori di chiamata per il sito di Dublino, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="78b6a-146">For example, an administrator can enable Call Data Connector forwarding for the Redmond site but disable Call Data Connector forwarding for the Dublin site, as shown in the following example:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

<span data-ttu-id="78b6a-147">Le impostazioni configurate a livello di sito hanno la precedenza su quelle configurate a livello globale.</span><span class="sxs-lookup"><span data-stu-id="78b6a-147">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="78b6a-148">Si supponga, ad esempio, che l'inoltro dei connettori di chiamata sia abilitato nell'ambito globale, ma sia disabilitato nell'ambito del sito (per il sito Redmond).</span><span class="sxs-lookup"><span data-stu-id="78b6a-148">For example, suppose Call Data Connector forwarding is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="78b6a-149">Questo significa che la registrazione dettagli chiamata e le informazioni QoE non verranno inoltrate per gli utenti nel sito Redmond.</span><span class="sxs-lookup"><span data-stu-id="78b6a-149">That means that call detail recording and QoE information will not be forwarded for users in the Redmond site.</span></span> <span data-ttu-id="78b6a-150">Tuttavia, gli utenti in altri siti (ovvero gli utenti gestiti dalle impostazioni globali invece delle impostazioni del sito Redmond) avranno la registrazione dettagli chiamata e le informazioni QoE inoltrate.</span><span class="sxs-lookup"><span data-stu-id="78b6a-150">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording and QoE information forwarded.</span></span>

<span data-ttu-id="78b6a-151">Nella tabella seguente vengono illustrati i valori delle impostazioni di utilizzo più comunemente utilizzate dal connettore dati chiamata:</span><span class="sxs-lookup"><span data-stu-id="78b6a-151">Values for the most commonly used settings used by Call Data Connector are shown in the following table:</span></span>  

|<span data-ttu-id="78b6a-152">Proprietà</span><span class="sxs-lookup"><span data-stu-id="78b6a-152">Property</span></span>|<span data-ttu-id="78b6a-153">Descrizione</span><span class="sxs-lookup"><span data-stu-id="78b6a-153">Description</span></span>|<span data-ttu-id="78b6a-154">Valore predefinito</span><span class="sxs-lookup"><span data-stu-id="78b6a-154">Default value</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="78b6a-155">EnableCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="78b6a-155">EnableCallDataConnector</span></span>  <br/> |<span data-ttu-id="78b6a-156">Indica se il connettore dati chiamata è abilitato.</span><span class="sxs-lookup"><span data-stu-id="78b6a-156">Indicates whether Call Data Connector is enabled.</span></span> <span data-ttu-id="78b6a-157">Se impostato su true, i record di monitoraggio verranno inoltrati al monitoraggio online.</span><span class="sxs-lookup"><span data-stu-id="78b6a-157">If True, monitoring records will be forwarded to online monitoring.</span></span>  <br/> |<span data-ttu-id="78b6a-158">$False</span><span class="sxs-lookup"><span data-stu-id="78b6a-158">$False</span></span>  <br/> |
| <span data-ttu-id="78b6a-159">Identità</span><span class="sxs-lookup"><span data-stu-id="78b6a-159">Identity</span></span> | <span data-ttu-id="78b6a-160">Determina il livello di ambito per il comando: globale o sito.</span><span class="sxs-lookup"><span data-stu-id="78b6a-160">Determines the scope level for the command: global or site.</span></span>   | <span data-ttu-id="78b6a-161">globale</span><span class="sxs-lookup"><span data-stu-id="78b6a-161">global</span></span>  |

## <a name="disable-call-data-connector"></a><span data-ttu-id="78b6a-162">Disattiva connettore dati chiamata</span><span class="sxs-lookup"><span data-stu-id="78b6a-162">Disable Call Data Connector</span></span>

<span data-ttu-id="78b6a-163">La disattivazione del connettore dei dati delle chiamate non dissocia l'archivio di monitoraggio dal pool Front End, né Disinstalla o influisce in altro modo sul database di monitoraggio back-end.</span><span class="sxs-lookup"><span data-stu-id="78b6a-163">Disabling Call Data Connector does not disassociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="78b6a-164">Quando si disattiva il connettore dei dati di chiamata, si interrompe Skype for Business Server dal caricamento dei dati delle chiamate nel cloud.</span><span class="sxs-lookup"><span data-stu-id="78b6a-164">When you disable Call Data Connector, you stop Skype for Business Server from uploading call data to the cloud.</span></span> 

<span data-ttu-id="78b6a-165">Si disattiva il connettore dei dati di chiamata utilizzando il cmdlet Set-CsCloudCallDataConnectorConfiguration dall'interno di Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="78b6a-165">You disable Call Data Connector by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="78b6a-166">Ad esempio, il comando seguente disattiva il connettore dei dati delle chiamate nell'ambito globale impostando la proprietà EnableCallDataConnector su $False:</span><span class="sxs-lookup"><span data-stu-id="78b6a-166">For example, the following command disables Call Data Connector at the global scope by setting the EnableCallDataConnector property to $False:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

<span data-ttu-id="78b6a-167">Se si desidera riprendere il caricamento dei dati delle chiamate nel cloud, impostare la proprietà EnableCallDataConnector su $True, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="78b6a-167">If you want to resume uploading call data to the cloud, set the EnableCallDataConnector property back to $True, as shown in the following example:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a><span data-ttu-id="78b6a-168">Visualizzare i dati locali tramite il dashboard online</span><span class="sxs-lookup"><span data-stu-id="78b6a-168">View on-premises data through the online dashboard</span></span>

 <span data-ttu-id="78b6a-169">Dopo aver abilitato il connettore dati chiamata, è possibile visualizzare i dati delle chiamate locali nel dashboard di analisi delle chiamate o nel dashboard qualità chiamata, come descritto in [Use Call Analytics per risolvere i problemi di qualità scadente](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) e [attivare e utilizzare il dashboard qualità chiamata per Microsoft teams e Skype for business online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).</span><span class="sxs-lookup"><span data-stu-id="78b6a-169">After Call Data Connector is enabled, you can view your on-premises call data on the Call Analytics dashboard or Call Quality Dashboard as described in  [Use Call Analytics to troubleshoot poor quality](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) and [Turn on and use Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="78b6a-170">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="78b6a-170">For more information</span></span>

<span data-ttu-id="78b6a-171">Per ulteriori informazioni sui cmdlet, è possibile utilizzare il comando Get-Help da Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="78b6a-171">For more information on the cmdlets, you can use the Get-Help command from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="78b6a-172">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="78b6a-172">For example:</span></span>

<span data-ttu-id="78b6a-173">Get-Help Get-CsCloudCallDataConnector | più</span><span class="sxs-lookup"><span data-stu-id="78b6a-173">Get-Help Get-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="78b6a-174">Get-Help Set-CsCloudCallDataConnector | più</span><span class="sxs-lookup"><span data-stu-id="78b6a-174">Get-Help Set-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="78b6a-175">Get-Help Set-CsCloudCallDataConnectorConfiguration | più</span><span class="sxs-lookup"><span data-stu-id="78b6a-175">Get-Help Set-CsCloudCallDataConnectorConfiguration | more</span></span>
