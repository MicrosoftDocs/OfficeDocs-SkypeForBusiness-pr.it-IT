---
title: Configurare i provider per il servizio di registrazione centralizzato in Skype for Business 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: 'Riepilogo: informazioni su come configurare i provider di scenari per il servizio di registrazione centralizzato in Skype for Business Server 2015.'
ms.openlocfilehash: dcfa16ffa00e81153172570e67020cf287350cd9
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991471"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a>Configurare i provider per il servizio di registrazione centralizzato in Skype for Business 2015
 
**Riepilogo:** Informazioni su come configurare i provider di scenari per il servizio di registrazione centralizzato in Skype for Business Server 2015.
  
I concetti e la configurazione dei provider in un servizio di registrazione centralizzato è uno dei più importanti da afferrare. Theproviders mappa direttamente ai componenti del ruolo del server Skype for Business Server nel modello di traccia di Skype for Business Server. Il provider definisce i componenti di un server Skype for business 2015 che verrà tracciato, il tipo di messaggi (ad esempio, fatale, errore o avviso) da raccogliere e i contrassegni (ad esempio TF_Connection o TF_Diag). I provider sono i componenti rintracciabili in ogni ruolo del server Skype for Business Server. Usando i provider, Definisci il livello e il tipo di traccia sui componenti (ad esempio, S4, SIPStack, IM e Presence). Il provider definito viene usato in uno scenario per raggruppare tutti i provider per una determinata raccolta logica che affrontano una specifica condizione di problema.
  
Per eseguire le funzioni di servizio di registrazione centralizzata con Skype for Business Server Management Shell, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contiene uno di questi due gruppi. Per restituire un elenco di tutti i ruoli di controllo di accesso basati sul ruolo a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati manualmente), eseguire il comando seguente da Skype for Business Server Management Shell o Windows PowerShell prompt
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Ad esempio:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

Il resto di questo argomento illustra come definire i provider, modificare un provider e il contenuto di una definizione di provider per ottimizzare la risoluzione dei problemi. Esistono due modi per emettere comandi di servizio di registrazione centralizzati. Per impostazione predefinita, è possibile usare CLSController. exe nella directory c:\Programmi\File Skype for Business Server 2015 \ CLSAgent. In alternativa, puoi usare Skype for Business Server Management Shell per emettere comandi di Windows PowerShell. Usando Windows PowerShell puoi definire nuovi provider da usare nelle sessioni di registrazione e avere il controllo completo sulla creazione, su cosa raccolgono e su quale livello raccolgono i dati.
  
> [!IMPORTANT]
> Come accennato, i provider sono molto potenti. Tuttavia, gli scenari sono più potenti perché contengono l'incorporamento di tutte le informazioni necessarie per impostare ed eseguire la traccia sui componenti rappresentati dai provider. Con gli scenari che sono una raccolta di provider, questa operazione potrebbe essere confrontata con l'esecuzione di un file batch contenente centinaia di comandi per raccogliere molte informazioni rispetto al rilascio di centinaia di comandi, uno alla volta, nella riga di comando. 
  
Invece di richiedere di approfondire i dettagli dei provider, il servizio di registrazione centralizzato offre numerosi scenari già definiti per l'utente. Gli scenari forniti coprono la stragrande maggioranza dei possibili problemi che incontrerai. In rari casi potrebbe essere necessario creare e definire provider e assegnarli agli scenari. Ti consigliamo vivamente di acquisire familiarità con ognuno degli scenari forniti prima di esaminare la necessità di creare nuovi provider e scenari. Mentre le informazioni sulla creazione di provider si trovano qui per familiarizzare con il modo in cui gli scenari usano gli elementi del provider per raccogliere informazioni di traccia, in questo momento non vengono forniti dettagli sui provider stessi. 
  
Introdotti in [servizi di registrazione centralizzati in Skype for Business 2015](centralized-logging-service.md), gli elementi chiave della definizione di un provider per l'uso in uno scenario sono i seguenti:
  
- **Provider** Se si ha familiarità con OCSLogger, i provider sono i componenti scelti per indicare a OCSLogger da quale motore di analisi deve raccogliere i log. I provider sono gli stessi componenti e in molti casi hanno lo stesso nome dei componenti in OCSLogger. Se non si ha familiarità con OCSLogger, i provider sono componenti specifici del ruolo del server a cui il servizio di registrazione centralizzata può raccogliere i log. Nel caso del servizio di registrazione centralizzato, CLSAgent è la parte dell'architettura del servizio di registrazione centralizzata che sta eseguendo la traccia dei componenti definiti nella configurazione di provider.
    
- **Livelli di registrazione** OCSLogger ha fornito l'opzione per scegliere un numero di livelli di dettaglio per i dati raccolti. Questa caratteristica è parte integrante del servizio di registrazione centralizzato e degli scenari e viene definita dal parametro **Type** . È possibile scegliere una delle opzioni seguenti:
    
  - **Tutti i** Raccoglie i messaggi di traccia di tipo Fatal, Error, Warning, verbose e info di debug nel log per il provider definito.
    
  - **Fatal** Raccoglie solo i messaggi di traccia definiti come "fatali".
    
  - **Errore** Raccoglie solo i messaggi di traccia definiti come "errore" o "fatale".
    
  - **Avviso** Raccoglie solo i messaggi di traccia di tipo "avviso", "errore" e "fatale".
    
  - **Informazioni** Raccoglie solo i messaggi di traccia che indicano un messaggio informativo per il provider definito, oltre a messaggi irreversibili, di errore e di avviso.
    
  - **Verbose** Raccoglie tutti i messaggi di traccia di tipo Fatal, Error, Warning e Verbose per il provider definito.
    
  - Il **debug** è essenzialmente un equivalente di ' all'-raccoglie tracce di tipo fatale, Error, Warning, info, verbose e debug per il provider definito.
    
- **Contrassegni** OCSLogger ha fornito l'opzione per scegliere contrassegni per ogni provider che ha definito il tipo di informazioni che è possibile recuperare dai file di traccia. È possibile scegliere i contrassegni seguenti in base al provider:
    
  - **TF_Connection** Fornisce voci di log correlate alla connessione. Questi registri includono informazioni sulle connessioni stabilite da e verso un particolare componente. Può anche includere informazioni significative a livello di rete, ovvero per i componenti senza il concetto di connessione.
    
  - **TF_Security** Fornisce tutti gli eventi/voci di log correlate alla sicurezza. Ad esempio, per SipStack, si tratta di eventi di sicurezza come l'errore di convalida del dominio e gli errori di autenticazione client/autorizzazione.
    
  - **TF_Diag** Fornisce gli eventi di diagnostica che è possibile usare per diagnosticare o risolvere i problemi del componente. Ad esempio, per SipStack, si tratta di errori di certificato o di avvisi e messaggi DNS.
    
  - **TF_Protocol** Fornisce messaggi di protocollo come i messaggi SIP e i pacchetti di codec community combinati.
    
  - **TF_Component** Abilita la registrazione dei componenti specificati come parte dei provider.
    
  - **Tutti i** Imposta tutti i contrassegni disponibili per il provider.
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>Per esaminare le informazioni sui provider di scenari di servizi di registrazione centralizzati esistenti

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
2. Per esaminare la configurazione dei provider esistenti, digitare quanto segue:
    
   ```PowerShell
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    Ad esempio, per esaminare le informazioni sull'operatore di conferenza globale, digitare:
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA"
   ```

    Il comando Visualizza un elenco di provider con i contrassegni, le impostazioni e i componenti associati. Se le informazioni visualizzate non sono sufficienti o l'elenco è troppo lungo per il formato predefinito dell'elenco di Windows PowerShell, è possibile visualizzare altre informazioni definendo un metodo di output diverso. A tale scopo, digitare:
    
   ```PowerShell
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    L'output di questo comando Visualizza ogni provider visualizzato in un formato a cinque righe con il nome del provider, il tipo di registrazione, il livello di registrazione, i contrassegni, il GUID e il ruolo, ognuno in una riga distinta. 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>Per definire un nuovo provider di scenari del servizio di registrazione centralizzato

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
2. Un provider di scenari è costituito da un componente da tracciare, da contrassegni da usare e da un livello di dettaglio da raccogliere. Per eseguire questa operazione, digitare:
    
   ```PowerShell
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    Ad esempio, la definizione di un provider di traccia che definisce cosa raccogliere e il livello di dettaglio del provider Lyss ha l'aspetto seguente:
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

Il livello raccoglie messaggi fatali, di errore, di avviso e di informazioni. I contrassegni usati sono tutti quelli definiti per il provider Lyss e includono TF_Connection, TF_Diag e TF_Protocol. dopo aver definito la variabile $LyssProvider, è possibile usarla con il cmdlet **New-CsClsScenario** per raccogliere le tracce dal provider Lyss. Per completare la creazione e l'assegnazione del provider in un nuovo scenario, digitare:

```PowerShell
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

Dove $LyssProvider è la variabile che contiene lo scenario definito creato con **New-CsClsProvider**.
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>Per modificare un provider di scenario del servizio di registrazione centralizzato esistente

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
2. Per aggiornare o modificare la configurazione di un provider esistente, digitare:
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    È quindi possibile aggiornare lo scenario per assegnare il provider digitando quanto segue:
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

Il risultato finale del comando è che il sito scenario: Redmond/RedmondLyssInfo avrà aggiornato i contrassegni e il livello per il provider assegnato. Puoi visualizzare il nuovo scenario usando Get-CsClsScenario. Per informazioni dettagliate, vedere [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps).
> [!CAUTION]
> **New-ClsCsProvider** non controlla per determinare se i contrassegni sono validi. Verificare che l'ortografia dei contrassegni (ad esempio TF_DIAG o TF_CONNECTION) sia stata digitata correttamente. Se i contrassegni non vengono digitati correttamente, il provider non potrà restituire le informazioni di log previste.
  
Se si vogliono aggiungere altri provider a questo scenario, digitare quanto segue:

```PowerShell
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

Dove ogni provider definito con la direttiva add è già stato definito tramite il processo **New-CsClsProvider** .
### <a name="to-remove-a-scenario-provider"></a>Per rimuovere un provider di scenari

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
2. I cmdlet forniti consentono di aggiornare i provider esistenti e di creare nuovi provider. Per rimuovere un provider, è necessario usare la direttiva Replace per il parametro provider per **impostare-CsClsScenario**. L'unico modo per rimuovere completamente un provider è sostituirlo con un provider ridefinito con lo stesso nome e usare la direttiva Update. Ad esempio, il nostro provider LyssProvider è definito con WPP come tipo di log, Level set to debug e flags set sono TF_CONNECTION e TF_DIAG. È necessario modificare i contrassegni in "tutti". Per cambiare il provider, digitare quanto segue:
    
   ```PowerShell
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
   ```

   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
   ```

3. Se si vuole rimuovere completamente uno scenario e i provider a esso associati, digitare quanto segue:
    
   ```PowerShell
   Remove-CsClsScenario -Identity <scope and name of scenario>
   ```

    Ad esempio:
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
   ```

    > [!CAUTION]
    > Il cmdlet **Remove-CsClsScenario** non chiede conferma. Lo scenario viene eliminato, insieme ai provider assegnati. Puoi ricreare lo scenario eseguendo nuovamente i comandi usati per crearlo inizialmente. Non esiste una procedura per recuperare gli scenari o i provider rimossi.
  
Quando si rimuove uno scenario usando il cmdlet **Remove-CsClsScenario** , si rimuove completamente lo scenario dall'ambito. Per usare gli scenari creati e i provider che facevano parte dello scenario, è possibile creare nuovi provider e assegnarli a un nuovo scenario.
## <a name="see-also"></a>Vedere anche

[Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[New-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[Remove-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps)
