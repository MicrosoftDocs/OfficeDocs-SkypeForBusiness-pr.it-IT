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
description: Istruzioni per la configurazione di Call Data Connector, che consente di visualizzare i dati di telemetria da Skype for Business locale usando Skype for Business strumenti online.
ms.openlocfilehash: 0d92d31798cd4b3fb5a1b4c555ff0ff00c2bdf31
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2022
ms.locfileid: "67156934"
---
# <a name="configure-call-data-connector"></a>Configurare connettore dati chiamate

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


Questo articolo descrive come configurare Call Data Connector, un singolo set di strumenti che consente di visualizzare Skype for Business Server dati di qualità delle chiamate usando gli strumenti Microsoft Call Quality Dashboard (CQD) e Call Analytics (CA).

Per altre informazioni sui vantaggi e sui prerequisiti di Call Data Connector, ad esempio i requisiti del ruolo e la configurazione della connettività ibrida, vedere [Plan Call Data Connector](plan-call-data-connector.md).

## <a name="enable-monitoring"></a>Abilitare il monitoraggio
 
È necessario configurare la registrazione dei dati di chiamata (CDR) e la raccolta di dati QoE (Quality of Experience) nel monitoraggio del pool front-end con i database LCSCdr e QoEMetrics locali; in caso contrario, i dashboard di Analisi delle chiamate e Qualità delle chiamate non ottengono dati da usare. Prima di configurare Call Data Connector, seguire i passaggi descritti in [Distribuire il monitoraggio in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) per configurare sia la cdr che la QoE, nonché il monitoraggio di base.

> [!IMPORTANT]
> Il connettore dati di chiamata non funzionerà se il monitoraggio non è abilitato nel pool front-end.

## <a name="enable-call-data-connector"></a>Abilitare Call Data Connector

Per configurare e abilitare Call Data Connector, si useranno i cmdlet seguenti:

| Cmdlet| Descrizione|
| :-----------------|---------------:|
| New-CsCloudCallDataConnection | Cmdlet online che stabilisce un agente di raccolta dati online.|
| Get-CsCloudCallDataConnection | Cmdlet online che recupera un agente di raccolta dati online esistente.|  
| Get-CsCloudCallDataConnector | Cmdlet locale che recupera le informazioni di connessione create dal cmdlet New-CsCloudCallDataConnection. |
| Set-CsCloudCallDataConnector | Cmdlet locale che salva una copia locale delle informazioni di connessione create dal cmdlet New-CsCloudCallDataConnection. |  
| Set-CsCloudCallDataConnectorConfiguration | Cmdlet locale che consente di abilitare o disabilitare il connettore e personalizzare il livello di ambito.|

> [!NOTE]
> Per cancellare la configurazione e ricominciare, usare il cmdlet Remove-csclouddatconnectorconfiguration.

### <a name="configure-your-environment"></a>Configurare l'ambiente 

Per configurare l'ambiente per abilitare un agente di raccolta dati online, è innanzitutto necessario accedere al modulo PowerShell di Microsoft Teams come amministratore. Per altre informazioni, vedere [Panoramica di PowerShell di Microsoft Teams](/microsoftteams/teams-powershell-overview).

Esistono due metodi per accedere al modulo PowerShell di Microsoft Teams:

- Dalla shell di gestione Skype for Business Server 2019 (metodo consigliato)
- Da un'altra sessione di PowerShell

#### <a name="log-in-to-microsoft-teams-powershell-module-from-the-skype-for-business-server-management-shell-recommended-method"></a>Accedere al modulo PowerShell di Microsoft Teams dalla shell di gestione Skype for Business Server (metodo consigliato)

1. Se si abilita il connettore per la prima volta, eseguire il comando seguente:

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. Se viene visualizzato un errore che indica che la connessione esiste già, significa che la connessione dati di chiamata esiste già per il tenant. In questo caso, eseguire il comando : 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-microsoft-teams-powershell-module-from-another-powershell-session-optional-method"></a>Accedere al modulo PowerShell di Microsoft Teams da un'altra sessione di PowerShell (metodo facoltativo)

1.  Se si abilita il connettore per la prima volta, eseguire il comando seguente: 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  Se viene visualizzato un errore che indica che la connessione esiste già, significa che la connessione dati di chiamata esiste già per il tenant. In questo caso, eseguire il comando : 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

L'output dei comandi precedenti contiene un valore di token, necessario quando si configura l'ambiente locale come indicato di seguito:

Dall'interno della shell di gestione Skype for Business Server specificare il comando seguente:

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>Configurare l'ambito

È possibile abilitare Call Data Connector per un sito specifico o per l'intera distribuzione Skype for Business Server usando il cmdlet Set-CsCloudCallDataConnectorConfiguration dall'interno della shell di gestione Skype for Business Server. Ad esempio, il comando seguente abilita Call Data Connector nell'ambito globale:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

Oltre alle impostazioni globali, le impostazioni di configurazione di Call Data Connector possono essere assegnate all'ambito del sito. Ciò offre ulteriore flessibilità di gestione quando si tratta di monitoraggio. Ad esempio, un amministratore può abilitare l'inoltro del connettore di dati di chiamata per il sito Redmond, ma disabilitare l'inoltro del connettore di dati di chiamata per il sito Dublino, come illustrato nell'esempio seguente:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

Le impostazioni configurate a livello di sito hanno la precedenza su quelle configurate a livello globale. Si supponga, ad esempio, che l'inoltro di Call Data Connector sia abilitato nell'ambito globale, ma disabilitato nell'ambito del sito (per il sito Redmond). Ciò significa che la registrazione dei dettagli della chiamata e le informazioni QoE non verranno inoltrate per gli utenti nel sito Redmond. Tuttavia, gli utenti di altri siti (ovvero gli utenti gestiti dalle impostazioni globali anziché dalle impostazioni del sito Redmond) avranno la registrazione dei dettagli della chiamata e le informazioni QoE inoltrate.

I valori per le impostazioni usate più di frequente dal connettore di dati di chiamata sono visualizzati nella tabella seguente:  

|Proprietà|Descrizione|Valore predefinito|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |Indica se Call Data Connector è abilitato. Se True, i record di monitoraggio verranno inoltrati al monitoraggio online.  <br/> |$False  <br/> |
| Identità | Determina il livello di ambito per il comando: globale o sito.   | globale  |

## <a name="disable-call-data-connector"></a>Disabilitare Call Data Connector

La disabilitazione di Call Data Connector non dissocia l'archivio di monitoraggio dal pool Front End, né disinstalla o influisce in altro modo sul database di monitoraggio back-end. Quando si disabilita Call Data Connector, si arresta Skype for Business Server dal caricamento dei dati delle chiamate nel cloud. 

È possibile disabilitare Call Data Connector usando il cmdlet Set-CsCloudCallDataConnectorConfiguration dall'interno della shell di gestione Skype for Business Server. Ad esempio, il comando seguente disabilita il connettore di dati di chiamata nell'ambito globale impostando la proprietà EnableCallDataConnector su $False:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

Per riprendere il caricamento dei dati delle chiamate nel cloud, impostare nuovamente la proprietà EnableCallDataConnector su $True, come illustrato nell'esempio seguente:

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>Visualizzare i dati locali tramite il dashboard online

 Dopo l'abilitazione di Call Data Connector, è possibile visualizzare i dati delle chiamate locali nel dashboard di Analisi delle chiamate o nel dashboard qualità delle chiamate, come descritto in [Usare Analisi chiamate per risolvere i problemi di qualità scadente](/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) e [Attivare e usare Il dashboard qualità delle chiamate per Microsoft Teams e Skype for Business Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).

## <a name="for-more-information"></a>Ulteriori informazioni

Per altre informazioni sui cmdlet, è possibile usare il comando Get-Help da Skype for Business Server Management Shell. Ad esempio:

Get-Help Get-CsCloudCallDataConnector | più

Get-Help Set-CsCloudCallDataConnector | più

Get-Help Set-CsCloudCallDataConnectorConfiguration | più
