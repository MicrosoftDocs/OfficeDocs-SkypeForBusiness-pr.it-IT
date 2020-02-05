---
title: Configurare il connettore dei dati di chiamata
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Istruzioni per la configurazione del connettore dei dati di chiamata, che consente di visualizzare la telemetria da Skype for business in locale tramite gli strumenti di Skype for business online.
ms.openlocfilehash: 0354f5a1fd1b4794af29d23e0a0fc1bf49dfebd2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726926"
---
# <a name="configure-call-data-connector"></a>Configurare il connettore dei dati di chiamata

In questo articolo viene descritto come configurare il connettore dei dati di chiamata, ovvero un singolo set di strumenti che consente di visualizzare i dati di qualità delle chiamate di Skype for Business Server utilizzando Skype for business online Call Quality Dashboard (CQD) e gli strumenti di analisi delle chiamate (CA).

Per ulteriori informazioni sui vantaggi e i prerequisiti del connettore dei dati di chiamata, ad esempio i requisiti dei ruoli e la configurazione della connettività ibrida, vedere [Plan Call Data Connector](plan-call-data-connector.md).

## <a name="enable-monitoring"></a>Abilitare il monitoraggio
 
È necessario configurare la raccolta dati di registrazione dati di chiamata (CDR) e la qualità di esperienza (QoE) nel monitoraggio del pool Front End, con i database di LCSCdr e QoEMetrics locali. in caso contrario, i dashboard di analisi chiamata e qualità chiamata non consentiranno di utilizzare i dati. Prima di configurare il connettore dei dati di chiamata, seguire i passaggi descritti in [Deploy Monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) per configurare sia CdR sia QoE, nonché il monitoraggio di base.

> [!IMPORTANT]
> Il connettore dei dati di chiamata non funzionerà se il monitoraggio non è abilitato nel pool Front end.

## <a name="enable-call-data-connector"></a>Attiva connettore dati chiamata

Per configurare e abilitare il connettore dei dati di chiamata, verranno utilizzati i seguenti cmdlet:

| Cmdlet| Descrizione|
| :-----------------|---------------:|
| New-CsCloudCallDataConnection | Cmdlet online che consente di stabilire un agente di raccolta dati online.|
| Get-CsCloudCallDataConnection | Cmdlet online che consente di recuperare un agente di raccolta dati online esistente.|  
| Get-CsCloudCallDataConnector | Cmdlet locale che consente di recuperare le informazioni di connessione create dal cmdlet New-CsCloudCallDataConnection. |
| Set-CsCloudCallDataConnector | Cmdlet locale che consente di salvare una copia locale delle informazioni di connessione create dal cmdlet New-CsCloudCallDataConnection. |  
| Set-CsCloudCallDataConnectorConfiguration | Cmdlet locale che consente di abilitare o disabilitare il connettore e personalizzare il livello di ambito.|

> [!NOTE]
> Per cancellare la configurazione e ricominciare, utilizzare il cmdlet Remove-csclouddatconnectorconfiguration.

### <a name="configure-your-environment"></a>Configurare l'ambiente 

Per configurare l'ambiente per l'abilitazione di un agente di raccolta dati online, è necessario innanzitutto accedere a PowerShell per Skype for business online come amministratore. Per ulteriori informazioni, vedere [Manage Skype for business online con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Esistono due metodi per accedere a PowerShell per Skype for business online:

- Dalla shell di gestione di Skype for Business Server 2019 (metodo consigliato)
- Da un'altra sessione di PowerShell

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a>Accedere a PowerShell di Skype for business online da Skype for Business Server Management Shell (metodo consigliato)

1. Se si Abilita il connettore per la prima volta, eseguire il comando riportato di seguito:

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. Se viene visualizzato un errore che la connessione esiste già, significa che la connessione dati di chiamata esiste già per il tenant. In questo caso, eseguire il comando: 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a>Accedere a PowerShell di Skype for business online da un'altra sessione di PowerShell (metodo facoltativo)

1.  Se si Abilita il connettore per la prima volta, eseguire il comando riportato di seguito: 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  Se viene visualizzato un errore che la connessione esiste già, significa che la connessione dati di chiamata esiste già per il tenant. In questo caso, eseguire il comando: 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

L'output dei comandi precedenti contiene un valore di token, che sarà necessario quando si configura l'ambiente locale, come indicato di seguito:

In Skype for Business Server Management Shell, specificare il seguente comando:

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>Configurare l'ambito

È possibile abilitare il connettore dati chiamata per un sito specifico o per l'intera distribuzione di Skype for Business Server utilizzando il cmdlet Set-CsCloudCallDataConnectorConfiguration da Skype for Business Server Management Shell. Ad esempio, il comando seguente consente di abilitare il connettore dei dati di chiamata nell'ambito globale:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

Oltre alle impostazioni globali, le impostazioni di configurazione del connettore dei dati delle chiamate possono essere assegnate all'ambito del sito. In questo modo viene fornita una maggiore flessibilità di gestione per il monitoraggio. Ad esempio, un amministratore può abilitare l'inoltro del connettore dei dati di chiamata per il sito di Redmond ma disabilitare l'inoltro dei connettori di chiamata per il sito di Dublino, come illustrato nell'esempio seguente:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

Le impostazioni configurate a livello di sito hanno la precedenza su quelle configurate a livello globale. Si supponga, ad esempio, che l'inoltro dei connettori di chiamata sia abilitato nell'ambito globale, ma sia disabilitato nell'ambito del sito (per il sito Redmond). Questo significa che la registrazione dettagli chiamata e le informazioni QoE non verranno inoltrate per gli utenti nel sito Redmond. Tuttavia, gli utenti in altri siti (ovvero gli utenti gestiti dalle impostazioni globali invece delle impostazioni del sito Redmond) avranno la registrazione dettagli chiamata e le informazioni QoE inoltrate.

Nella tabella seguente vengono illustrati i valori delle impostazioni di utilizzo più comunemente utilizzate dal connettore dati chiamata:  

|Proprietà|Descrizione|Valore predefinito|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |Indica se il connettore dati chiamata è abilitato. Se impostato su true, i record di monitoraggio verranno inoltrati al monitoraggio online.  <br/> |$False  <br/> |
| Identità | Determina il livello di ambito per il comando: globale o sito.   | globale  |

## <a name="disable-call-data-connector"></a>Disattiva connettore dati chiamata

La disattivazione del connettore dei dati delle chiamate non dissocia l'archivio di monitoraggio dal pool Front End, né Disinstalla o influisce in altro modo sul database di monitoraggio back-end. Quando si disattiva il connettore dei dati di chiamata, si interrompe Skype for Business Server dal caricamento dei dati delle chiamate nel cloud. 

Si disattiva il connettore dei dati di chiamata utilizzando il cmdlet Set-CsCloudCallDataConnectorConfiguration dall'interno di Skype for Business Server Management Shell. Ad esempio, il comando seguente disattiva il connettore dei dati delle chiamate nell'ambito globale impostando la proprietà EnableCallDataConnector su $False:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

Se si desidera riprendere il caricamento dei dati delle chiamate nel cloud, impostare la proprietà EnableCallDataConnector su $True, come illustrato nell'esempio seguente:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>Visualizzare i dati locali tramite il dashboard online

 Dopo aver abilitato il connettore dati chiamata, è possibile visualizzare i dati delle chiamate locali nel dashboard di analisi delle chiamate o nel dashboard qualità chiamata, come descritto in [Use Call Analytics per risolvere i problemi di qualità scadente](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) e [attivare e utilizzare il dashboard qualità chiamata per Microsoft teams e Skype for business online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).

## <a name="for-more-information"></a>Ulteriori informazioni

Per ulteriori informazioni sui cmdlet, è possibile utilizzare il comando Get-Help da Skype for Business Server Management Shell. Ad esempio:

Get-Help Get-CsCloudCallDataConnector | più

Get-Help Set-CsCloudCallDataConnector | più

Get-Help Set-CsCloudCallDataConnectorConfiguration | più
