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
# <a name="configure-call-data-connector"></a>Configurare il connettore dati chiamata

Questo articolo descrive come configurare il connettore dati chiamata, un singolo set di strumenti che consente di visualizzare i dati di qualità delle chiamate di Skype for Business Server usando Skype for business online Call Quality Dashboard (Call Quality Dashboard) e strumenti di analisi delle chiamate (CA).

Per altre informazioni sui vantaggi e i prerequisiti per i connettori dei dati delle chiamate, ad esempio i requisiti dei ruoli e la configurazione della connettività ibrida, Vedi [Data Connector chiamata piano](plan-call-data-connector.md).

## <a name="enable-monitoring"></a>Abilitare il monitoraggio
 
È necessario configurare la raccolta dati chiamate CDR (Call Data Recording) e QoE (Quality of Experience) nel monitoraggio del pool Front-End, con i database LCSCdr e QoEMetrics locali; in caso contrario, i dashboard di analisi delle chiamate e di qualità delle chiamate non consentiranno di usare i dati. Prima di configurare il connettore dati chiamata, seguire i passaggi descritti in [distribuire il monitoraggio in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) per configurare CDR e QoE, nonché il monitoraggio di base.

> [!IMPORTANT]
> Il connettore dati chiamata non funzionerà se il monitoraggio non è abilitato nel pool Front-end.

## <a name="enable-call-data-connector"></a>Attiva connettore dati chiamata

Per configurare e abilitare il connettore dati chiamata, si utilizzeranno i cmdlet seguenti:

| Cmdlet| Descrizione|
| :-----------------|---------------:|
| New-CsCloudCallDataConnection | Un cmdlet online che stabilisce un agente di raccolta dati online.|
| Get-CsCloudCallDataConnection | Un cmdlet online che recupera un agente di raccolta dati online esistente.|  
| Get-CsCloudCallDataConnector | Cmdlet locale che recupera le informazioni di connessione create dal cmdlet New-CsCloudCallDataConnection. |
| Set-CsCloudCallDataConnector | Cmdlet locale che salva una copia locale delle informazioni di connessione create dal cmdlet New-CsCloudCallDataConnection. |  
| Set-CsCloudCallDataConnectorConfiguration | Cmdlet locale che consente di abilitare o disabilitare il connettore e personalizzare il livello di ambito.|

> [!NOTE]
> Per cancellare la configurazione e ricominciare, usare il cmdlet Remove-csclouddatconnectorconfiguration.

### <a name="configure-your-environment"></a>Configurare l'ambiente 

Per configurare l'ambiente per l'abilitazione di un agente di raccolta dati online, è necessario prima di tutto accedere a Skype for Business Online PowerShell come amministratore. Per altre informazioni, vedere [gestire Skype for business online con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Esistono due metodi per accedere a PowerShell per Skype for business online:

- Da Skype for Business Server 2019 Management Shell (metodo consigliato)
- Da un'altra sessione di PowerShell

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a>Accedere a PowerShell per Skype for business online da Skype for Business Server Management Shell (metodo consigliato)

1. Se si Abilita il connettore per la prima volta, eseguire il comando seguente:

   ```
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. Se viene visualizzato un messaggio di errore che la connessione esiste già, significa che la connessione dati della chiamata esiste già per il tenant. In questo caso, Esegui il comando: 

   ```
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a>Accedere a PowerShell per Skype for business online da un'altra sessione di PowerShell (metodo facoltativo)

1.  Se si Abilita il connettore per la prima volta, eseguire il comando seguente: 

    ``` 
    New-CsCloudCallDataConnection 
    ```

2.  Se viene visualizzato un messaggio di errore che la connessione esiste già, significa che la connessione dati della chiamata esiste già per il tenant. In questo caso, Esegui il comando: 

    ```
    Get-CsCloudCallDataConnection  
    ```

L'output dei comandi descritti sopra contiene un valore di token, che sarà necessario quando configuri l'ambiente locale come segue:

In Skype for Business Server Management Shell, specificare il comando seguente:

```
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>Configurare l'ambito

Puoi abilitare il connettore dati chiamata per un determinato sito o per l'intera distribuzione di Skype for Business Server usando il cmdlet Set-CsCloudCallDataConnectorConfiguration da Skype for Business Server Management Shell. Ad esempio, il comando seguente abilita il connettore data chiamata nell'ambito globale:

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

Oltre alle impostazioni globali, è possibile assegnare le impostazioni di configurazione dei connettori dati all'ambito del sito. In questo caso è disponibile un'ulteriore flessibilità di gestione per il monitoraggio. Ad esempio, un amministratore può abilitare l'inoltro del connettore dei dati delle chiamate per il sito Redmond, ma disabilitare l'inoltro del connettore dei dati delle chiamate per il sito di Dublino, come illustrato nell'esempio seguente:

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

Le impostazioni configurate nell'ambito del sito hanno la precedenza sulle impostazioni configurate nell'ambito globale. Supponiamo, ad esempio, che l'inoltro di Data Connector di chiamata sia abilitato nell'ambito globale, ma disabilitato nell'ambito del sito (per il sito Redmond). Ciò significa che la registrazione dei dettagli delle chiamate e le informazioni QoE non verranno inoltrate per gli utenti nel sito Redmond. Tuttavia, gli utenti di altri siti, ovvero gli utenti gestiti dalle impostazioni globali anziché dalle impostazioni del sito Redmond, avranno inoltrato le informazioni relative alla registrazione dei dettagli delle chiamate e agli QoE.

Nella tabella seguente sono illustrati i valori delle impostazioni di uso più comune usate da connettore dati chiamata:  

|Proprietà|Descrizione|Valore predefinito|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |Indica se il connettore dati della chiamata è abilitato. Se true, il monitoraggio dei record verrà inoltrato al monitoraggio online.  <br/> |$False  <br/> |
| Identity | Determina il livello di ambito per il comando: globale o sito.   | globale  |

## <a name="disable-call-data-connector"></a>Disattiva connettore dati chiamata

La disabilitazione del connettore dati chiamata non dissocia l'archivio di monitoraggio dal pool Front-End, né Disinstalla o influisce in altro modo sul database di monitoraggio del backend. Quando si disattiva chiamata Data Connector, viene impedito a Skype for Business Server di caricare i dati delle chiamate nel cloud. 

Puoi disabilitare il connettore dati chiamata usando il cmdlet Set-CsCloudCallDataConnectorConfiguration dall'interno di Skype for Business Server Management Shell. Ad esempio, il comando seguente disabilita la chiamata Data Connector nell'ambito globale impostando la proprietà EnableCallDataConnector su $False:

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

Se si vuole riprendere a caricare i dati delle chiamate nel cloud, impostare la proprietà EnableCallDataConnector su $True, come illustrato nell'esempio seguente:

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>Visualizzare i dati locali tramite il dashboard online

 Dopo aver abilitato il connettore dati chiamata, è possibile visualizzare i dati delle chiamate locali nel dashboard di analisi delle chiamate o nel dashboard qualità chiamata, come descritto in [usare la chiamata analitica per risolvere i problemi di qualità scadente](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) e [attivare e usare il dashboard qualità chiamata per Microsoft teams e Skype for business online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).

## <a name="for-more-information"></a>Per altre informazioni

Per altre informazioni sui cmdlet, è possibile usare il comando Get-Help da Skype for Business Server Management Shell. Ad esempio:

Get-Help Get-CsCloudCallDataConnector | più

Get-Help Set-CsCloudCallDataConnector | più

Get-Help Set-CsCloudCallDataConnectorConfiguration | più
