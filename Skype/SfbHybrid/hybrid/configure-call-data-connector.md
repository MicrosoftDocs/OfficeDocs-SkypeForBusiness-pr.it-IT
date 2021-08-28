---
title: Configurare connettore dati chiamate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection: ''
description: Istruzioni per la configurazione del connettore dati di chiamata, che consente di visualizzare la telemetria Skype for Business locale usando gli strumenti Skype for Business Online.
ms.openlocfilehash: 0e064e26ce7b8bfb97793666808b0b8a88ab2efc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58581150"
---
# <a name="configure-call-data-connector"></a>Configurare connettore dati chiamate

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


In questo articolo viene descritto come configurare Call Data Connector, un singolo set di strumenti che consente la visualizzazione dei dati sulla qualità delle chiamate di Skype for Business Server tramite gli strumenti CQD (Call Quality Dashboard) e Call Analytics (CA) di Skype for Business Online.

Per ulteriori informazioni sui vantaggi e i prerequisiti del connettore di dati di chiamata, ad esempio i requisiti dei ruoli e la configurazione della connettività ibrida, vedere [Plan Call Data Connector.](plan-call-data-connector.md)

## <a name="enable-monitoring"></a>Abilita monitoraggio
 
È necessario configurare la registrazione dei dati delle chiamate (CDR) e la raccolta dei dati QoE (Quality of Experience) nel monitoraggio del pool front-end, con database LCSCdr e QoEMetrics locali; in caso contrario, i dashboard di analisi delle chiamate e qualità delle chiamate non ottengono dati da utilizzare. Prima di configurare Il connettore dati di chiamata, seguire i passaggi descritti in Distribuire il monitoraggio [in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) per configurare sia la registrazione chiamata che QoE, nonché il monitoraggio di base.

> [!IMPORTANT]
> Call Data Connector non funzionerà se il monitoraggio non è abilitato nel pool front-end.

## <a name="enable-call-data-connector"></a>Abilita connettore dati chiamata

Per configurare e abilitare Call Data Connector, si utilizzeranno i cmdlet seguenti:

| Cmdlet| Descrizione|
| :-----------------|---------------:|
| New-CsCloudCallDataConnection | Cmdlet online che stabilisce un agente di raccolta dati online.|
| Get-CsCloudCallDataConnection | Cmdlet online che recupera un agente di raccolta dati online esistente.|  
| Get-CsCloudCallDataConnector | Cmdlet locale che recupera le informazioni di connessione create dal cmdlet New-CsCloudCallDataConnection locale. |
| Set-CsCloudCallDataConnector | Cmdlet locale che salva una copia locale delle informazioni di connessione create dal cmdlet New-CsCloudCallDataConnection locale. |  
| Set-CsCloudCallDataConnectorConfiguration | Cmdlet locale che consente di abilitare o disabilitare il connettore e personalizzare il livello di ambito.|

> [!NOTE]
> Per cancellare la configurazione e ricominciare, utilizzare il cmdlet Remove-csclouddatconnectorconfiguration.

### <a name="configure-your-environment"></a>Configurare l'ambiente 

Per configurare l'ambiente in modo da abilitare un agente di raccolta dati online, è innanzitutto necessario accedere a Skype for Business PowerShell online come amministratore. Per ulteriori informazioni, vedere [Manage Skype for Business Online with Office 365 PowerShell.](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

Esistono due metodi per accedere a Skype for Business PowerShell online:

- Da Skype for Business Server 2019 Management Shell (metodo consigliato)
- Da un'altra sessione di PowerShell

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a>Accedere a Skype for Business PowerShell online da Skype for Business Server Management Shell (metodo consigliato)

1. Se si abilita il connettore per la prima volta, eseguire il comando seguente:

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. Se viene visualizzato un errore che indica che la connessione esiste già, significa che la connessione dati di chiamata esiste già per il tenant. In questo caso, eseguire il comando: 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a>Accedere a powershell Skype for Business Online da un'altra sessione di PowerShell (metodo facoltativo)

1.  Se si abilita il connettore per la prima volta, eseguire il comando seguente: 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  Se viene visualizzato un errore che indica che la connessione esiste già, significa che la connessione dati di chiamata esiste già per il tenant. In questo caso, eseguire il comando: 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

L'output dei comandi precedenti contiene un valore token, necessario per la configurazione dell'ambiente locale nel modo seguente:

All'interno di Skype for Business Server management shell, specificare il comando seguente:

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>Configurare l'ambito

È possibile abilitare Call Data Connector per un sito specifico o per l'intera distribuzione di Skype for Business Server utilizzando il cmdlet Set-CsCloudCallDataConnectorConfiguration dall'interno di Skype for Business Server Management Shell. Ad esempio, il comando seguente abilita Call Data Connector nell'ambito globale:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

Oltre alle impostazioni globali, le impostazioni di configurazione del connettore dati di chiamata possono essere assegnate all'ambito del sito. In questo modo si garantisce una maggiore flessibilità di gestione per quanto riguarda il monitoraggio. Ad esempio, un amministratore può abilitare l'inoltro del connettore di dati di chiamata per il sito Redmond, ma disabilitare l'inoltro del connettore di dati di chiamata per il sito Dublino, come illustrato nell'esempio seguente:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

Le impostazioni configurate a livello di sito hanno la precedenza su quelle configurate a livello globale. Si supponga ad esempio che l'inoltro del connettore di dati di chiamata sia abilitato nell'ambito globale, ma disabilitato nell'ambito del sito (per il sito Redmond). Ciò significa che la registrazione dettagli chiamata e le informazioni QoE non verranno inoltrate per gli utenti nel sito Redmond. Tuttavia, gli utenti di altri siti (ovvero gli utenti gestiti dalle impostazioni globali anziché dalle impostazioni del sito Redmond) riceveranno la registrazione dettagli chiamata e le informazioni QoE inoltrate.

Nella tabella seguente sono riportati i valori per le impostazioni utilizzate più di frequente dal connettore dati di chiamata:  

|Proprietà|Descrizione|Valore predefinito|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |Indica se Call Data Connector è abilitato. Se True, i record di monitoraggio verranno inoltrati al monitoraggio online.  <br/> |$False  <br/> |
| Identità | Determina il livello di ambito per il comando: globale o sito.   | global  |

## <a name="disable-call-data-connector"></a>Disabilita connettore dati chiamata

La disabilitazione di Call Data Connector non disassocia l'archivio di monitoraggio dal pool Front End, né disinstalla o in altro modo influisce sul database di monitoraggio back-end. Quando si disabilita Call Data Connector, si interrompe Skype for Business Server di caricare i dati delle chiamate nel cloud. 

È possibile disabilitare Call Data Connector utilizzando il cmdlet Set-CsCloudCallDataConnectorConfiguration dall'Skype for Business Server Management Shell. Ad esempio, il comando seguente disabilita Call Data Connector nell'ambito globale impostando la proprietà EnableCallDataConnector su $False:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

Se si desidera riprendere il caricamento dei dati delle chiamate nel cloud, impostare nuovamente la proprietà EnableCallDataConnector su $True, come illustrato nell'esempio seguente:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>Visualizzare i dati locali tramite il dashboard online

 Dopo aver abilitato Call Data Connector, è possibile visualizzare i dati delle chiamate locali nel dashboard di Call Analytics o call quality dashboard, come descritto in [Use Call Analytics to troubleshoot poor quality](/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) e Turn on and use Call Quality Dashboard for Microsoft Teams and Skype for Business [Online.](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)

## <a name="for-more-information"></a>Ulteriori informazioni

Per ulteriori informazioni sui cmdlet, è possibile utilizzare il comando Get-Help da Skype for Business Server Management Shell. Ad esempio:

Get-Help Get-CsCloudCallDataConnector | altro

Get-Help Set-CsCloudCallDataConnector | altro

Get-Help Set-CsCloudCallDataConnectorConfiguration | altro