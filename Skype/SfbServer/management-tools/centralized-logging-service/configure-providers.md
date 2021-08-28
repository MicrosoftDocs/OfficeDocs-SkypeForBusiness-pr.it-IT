---
title: Configurare i provider per il servizio di registrazione centralizzata in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: 'Riepilogo: informazioni su come configurare i provider di scenari per il servizio di registrazione centralizzata in Skype for Business Server 2015.'
ms.openlocfilehash: ef1c728615d34e074ea041e261b4fc5b220e1fdd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58616542"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a>Configurare i provider per il servizio di registrazione centralizzata in Skype for Business Server 2015
 
**Riepilogo:** Informazioni su come configurare i provider di scenari per il servizio di registrazione centralizzata in Skype for Business Server 2015.
  
I concetti e la configurazione dei provider nel servizio di registrazione centralizzata sono tra i più importanti da comprendere. I provider vengono mappati direttamente Skype for Business Server componenti del ruolo del server nel modello Skype for Business Server di traccia. Il provider definisce i componenti di un Skype for Business Server 2015 che verrà tracciato, il tipo di messaggi (ad esempio, irreversibile, errore o avviso) da raccogliere e i flag (ad esempio, TF_Connection o TF_Diag). I provider sono i componenti tracciabili in ogni Skype for Business Server del server. Tramite i provider vengono definiti il livello e il tipo di traccia per i componenti (ad esempio, S4, SIPStack, messaggistica istantanea e presenza). Il provider definito viene utilizzato in uno scenario per raggruppare tutti i provider per una determinata raccolta logica riferita a una condizione problematica specifica.
  
Per eseguire le funzioni del servizio di registrazione centralizzata utilizzando Skype for Business Server Management Shell, è necessario essere membri dei gruppi di sicurezza RBAC (Role-Based Access Control) CsAdministrator o CsServerAdministrator oppure di un ruolo RBAC personalizzato contenente uno di questi due gruppi. Per restituire un elenco di tutti i ruoli RBAC (Role-Based Access Control) a cui è stato assegnato questo cmdlet , inclusi gli eventuali ruoli RBAC personalizzati creati dall'utente, eseguire il comando seguente da Skype for Business Server Management Shell o dal prompt di Windows PowerShell:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Ad esempio:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

Nella parte restante di questo argomento viene illustrato come definire provider, modificare un provider e cosa contiene una definizione di provider per ottimizzare la risoluzione dei problemi. Esistono due modi per emettere comandi del servizio di registrazione centralizzata. È possibile utilizzare il CLSController.exe che si trova, per impostazione predefinita, nella directory C:\Programmi\File comuni\Skype for Business Server 2015\CLSAgent. In caso contrario, è possibile utilizzare Skype for Business Server Management Shell per emettere Windows PowerShell comandi. Utilizzando Windows PowerShell, è possibile definire nuovi provider da utilizzare nelle sessioni di registrazione e avere il controllo completo sulla loro creazione, su cosa raccolgono e a quale livello raccolgono i dati.
  
> [!IMPORTANT]
> Come già accennato, i provider sono uno strumento dalle grandi potenzialità. Gli scenari, tuttavia, sono ancora più efficaci perché incorporano tutte le informazioni necessarie per impostare ed eseguire la traccia sui componenti rappresentati dai provider. Dato che gli scenari sono in effetti una raccolta di provider, possono essere paragonati all'esecuzione di un file batch contenente centinaia di comandi per raccogliere grandi quantità di informazioni anziché eseguire centinaia di comandi, uno alla volta, dalla riga di comando. 
  
Invece di richiedere un'approfondita ricerca nei dettagli dei provider, il servizio di registrazione centralizzata offre una serie di scenari già definiti. Gli scenari forniti riguardano la maggior parte dei possibili problemi che si verificano. In rari casi, potrebbe essere necessario creare e definire provider e assegnarli agli scenari. È consigliabile acquisire familiarità con ognuno degli scenari forniti prima di analizzare la necessità di creare nuovi provider e scenari. Anche se le informazioni sulla creazione di provider sono disponibili qui per acquisire familiarità con il modo in cui gli scenari usano gli elementi del provider per raccogliere informazioni di traccia, al momento non vengono forniti dettagli sui provider stessi. 
  
Introdotto in [Centralized Logging Service in Skype for Business 2015,](centralized-logging-service.md)gli elementi chiave della definizione di un provider da utilizzare in uno scenario sono:
  
- **Provider** Se si ha familiarità con OCSLogger, i provider sono i componenti che si sceglie di indicare a OCSLogger da quale motore di traccia raccogliere i log. I provider sono gli stessi componenti, e in molti casi ne condividono anche il nome, dei componenti in OCSLogger. Se non si ha familiarità con OCSLogger, i provider sono componenti specifici del ruolo del server da cui il servizio di registrazione centralizzata può raccogliere i registri. Nel caso del servizio di registrazione centralizzata, CLSAgent è la parte architetturale del servizio di registrazione centralizzata che esegue la traccia dei componenti definiti nella configurazione dei provider.
    
- **Livelli di registrazione** OCSLogger ha fornito la possibilità di scegliere un numero di livelli di dettaglio per i dati raccolti. Questa funzionalità è parte integrante del servizio di registrazione centralizzata e degli scenari ed è definita dal **parametro Type.** È possibile scegliere una delle seguenti opzioni:
    
  - **All** Raccoglie nel registro per il provider definito i messaggi di traccia di tipo irreversibile, errore, avviso, dettagliato e debug.
    
  - **Fatale** Raccoglie solo i messaggi di traccia definiti come "Fatale".
    
  - **Errore** Raccoglie solo i messaggi di traccia definiti come "Errore" o "Fatale".
    
  - **Avviso** Raccoglie solo i messaggi di traccia di tipo "Avviso", "Errore" e "Irreversibile".
    
  - **Info** Raccoglie solo i messaggi di traccia che indicano un messaggio informativo per il provider definito, oltre ai messaggi di errore irreversibile, di errore e di avviso.
    
  - **Verbose** Raccoglie tutti i messaggi di traccia di tipo irreversibile, errore, avviso e dettagliato per il provider definito.
    
  - **Il** debug è essenzialmente un equivalente di 'All': raccoglie tracce di tipo Fatal, Error, Warning, Info, Verbose e Debug per il provider definito.
    
- **Flag** OCSLogger ha fornito la possibilità di scegliere i flag per ogni provider che ha definito il tipo di informazioni che è possibile recuperare dai file di traccia. È possibile scegliere tra i flag seguenti, in base al provider:
    
  - **TF_Connection** Fornisce voci di registro correlate alla connessione. Questi log includono informazioni sulle connessioni stabilite con e da un particolare componente. Potrebbero essere anche incluse informazioni significative a livello di rete, ovvero per componenti non correlati al concetto di connessione.
    
  - **TF_Security** Fornisce tutti gli eventi/voci di registro relativi alla sicurezza. Per SipStack, ad esempio, si tratta degli eventi di sicurezza come errori di convalida del dominio ed errori di autenticazione/autorizzazione dei client.
    
  - **TF_Diag** Fornisce eventi di diagnostica che è possibile utilizzare per diagnosticare o risolvere i problemi del componente. Per SipStack, ad esempio, si tratta di errori dei certificati oppure di avvisi/errori DNS.
    
  - **TF_Protocol** Fornisce messaggi di protocollo quali i messaggi SIP e Community Codec Pack.
    
  - **TF_Component** Abilita la registrazione dei componenti specificati come parte dei provider.
    
  - **All** Imposta tutti i flag disponibili disponibili per il provider.
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>Per esaminare le informazioni sui provider di scenari esistenti del servizio di registrazione centralizzata

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic **su Skype for Business Server Management Shell.**
    
2. Per esaminare la configurazione dei provider esistenti, digitare il comando seguente:
    
   ```PowerShell
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    Per visualizzare informazioni sull'operatore conferenza globale, ad esempio, digitare:
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA"
   ```

    Il comando visualizza un elenco dei provider con i flag, le impostazioni e i componenti associati. Se le informazioni visualizzate non sono sufficienti o se l'elenco è troppo lungo per il formato di elenco Windows PowerShell predefinito, è possibile visualizzare ulteriori informazioni definendo un metodo di output diverso. A tale scopo, digitare:
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    Nell'output di questo comando, le informazioni su ogni provider sono visualizzate su cinque righe separate che includono nome del provider, tipo di registrazione, livello di registrazione, flag, GUID e ruolo. 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>Per definire un nuovo provider di scenari del servizio di registrazione centralizzata

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic **su Skype for Business Server Management Shell.**
    
2. Un provider di scenari è costituito dal componente da tracciare, i flag da utilizzare e il livello di dettaglio per la raccolta dei dati. Per definire questi elementi, digitare:
    
   ```PowerShell
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    La definizione di un provider di traccia per specificare quali dati raccogliere e con quale livello di dettaglio dal provider Lyss, ad esempio, è simile alla seguente:
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

-Level raccoglie messaggi irreversibili, di errore, di avviso e di informazioni. I flag utilizzati sono tutti definiti per il provider Lyss e includono TF_Connection, TF_Diag e TF_Protocol.Dopo aver definito la variabile $LyssProvider, è possibile utilizzarla con il cmdlet **New-CsClsScenario** per raccogliere le tracce dal provider Lyss. Per completare la creazione e l'assegnazione del provider a un nuovo scenario, digitare:

```PowerShell
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

Dove $LyssProvider è la variabile che contiene lo scenario definito creato con **New-CsClsProvider**.
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>Per modificare un provider di scenari del servizio di registrazione centralizzata esistente

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic **su Skype for Business Server Management Shell.**
    
2. Per aggiornare o modificare la configurazione di un provider esistente, digitare:
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    Aggiornare quindi lo scenario per assegnare il provider digitando il comando seguente:
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

Il risultato finale del comando è l'aggiornamento dei flag per lo scenario site:Redmond/RedmondLyssInfo e l'assegnazione del livello per il provider. Per visualizzare il nuovo scenario, utilizzare Get-CsClsScenario. Per informazioni dettagliate, vedere [Get-CsClsScenario](/powershell/module/skype/get-csclsscenario?view=skype-ps).
> [!CAUTION]
> **New-ClsCsProvider** non esegue un controllo per stabilire se i flag sono validi. Assicurarsi di digitare correttamente i flag, ad esempio TF_DIAG o TF_CONNECTION. Se il nome dei flag non è corretto, il provider non potrà restituire le informazioni di log previste.
  
Se si desidera aggiungere ulteriori provider a questo scenario, digitare il comando seguente:

```PowerShell
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

In cui ogni provider definito con la direttiva Add è già stato definito tramite il processo **New-CsClsProvider**.
### <a name="to-remove-a-scenario-provider"></a>Per rimuovere un provider di scenari

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic **su Skype for Business Server Management Shell.**
    
2. I cmdlet indicati consentono di aggiornare i provider esistenti e di crearne di nuovi. Per rimuovere un provider, è necessario utilizzare la direttiva Replace per il parametro Provider in **Set-CsClsScenario**. L'unico modo per rimuovere completamente un provider consiste nel sostituirlo con un provider ridefinito con lo stesso nome e poi utilizzare la direttiva Update. Il provider LyssProvider utilizzato negli esempi precedenti, ad esempio, è definito con il tipo di log WPP, il livello di registrazione Debug e i flag TF_CONNECTION e TF_DIAG. È necessario modificare i flag in "All". per modificare il provider digitare il comando seguente:
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
   ```

   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
   ```

3. Se si desidera rimuovere completamente uno scenario e i provider associati, digitare il comando seguente:
    
   ```PowerShell
   Remove-CsClsScenario -Identity <scope and name of scenario>
   ```

    Ad esempio:
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
   ```

    > [!CAUTION]
    > Il cmdlet **Remove-CsClsScenario** non richiede alcuna conferma. Lo scenario viene eliminato insieme ai provider assegnati. È possibile ricreare lo scenario rieseguendo i comandi utilizzati inizialmente per crearlo. Non esiste una procedura per il ripristino di scenari o provider rimossi.
  
Quando si rimuove uno scenario tramite il cmdlet **Remove-CsClsScenario**, si rimuove completamente lo scenario dall'ambito. Per utilizzare gli scenari creati e i provider che facevano parte dello scenario, creare nuovi provider e assegnarli a un nuovo scenario.
## <a name="see-also"></a>Vedere anche

[Get-CsClsScenario](/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[New-CsClsScenario](/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[Remove-CsClsScenario](/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[Set-CsClsScenario](/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[New-CsClsProvider](/powershell/module/skype/new-csclsprovider?view=skype-ps)