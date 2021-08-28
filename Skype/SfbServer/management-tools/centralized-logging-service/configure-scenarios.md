---
title: Configurare gli scenari per il servizio di registrazione centralizzata in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: 'Riepilogo: informazioni su come creare, modificare e rimuovere scenari per il servizio di registrazione centralizzata in Skype for Business Server 2015.'
ms.openlocfilehash: b4dea0146cfb80d8f28a102d4cf719a28b7bb188
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619712"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Configurare gli scenari per il servizio di registrazione centralizzata in Skype for Business Server 2015
 
**Riepilogo:** Informazioni su come creare, modificare e rimuovere scenari per il servizio di registrazione centralizzata in Skype for Business Server 2015.
  
Gli scenari definiscono l'ambito (ovvero globale, sito, pool o computer) e i provider da utilizzare nel servizio di registrazione centralizzata. Attraverso gli scenari si attivano o disattivano le tracce per i provider (ad esempio, S4, SIPStack, messaggistica immediata e presenza). Attraverso la configurazione di uno scenario, è possibile raggruppare tutti i provider per una data raccolta logica relativa a un problema specifico. Se si trova che uno scenario deve essere modificato per soddisfare le esigenze di risoluzione dei problemi e registrazione, gli strumenti di debug di Skype for Business Server 2015 forniscono un modulo Windows PowerShell denominato ClsScenarioEdit.psm1 contenente una funzione denominataEdit-CsClsScenario. Il modulo consente di modificare le proprietà dello scenario. In questo argomento sono forniti esempi di funzionamento del modulo. Scaricare gli Skype for Business Server 2015 [Debugging Tools](https://go.microsoft.com/fwlink/p/?LinkId=285257) prima di procedere.
  
> [!IMPORTANT]
> Per un determinato ambito (sito, globale, pool o computer), è possibile eseguire un massimo di due scenari alla volta. Per determinare quali scenari sono attualmente in esecuzione, utilizzare Windows PowerShell [e Get-CsClsScenario](/powershell/module/skype/get-csclsscenario?view=skype-ps). Utilizzando Windows PowerShell e [Set-CsClsScenario](/powershell/module/skype/set-csclsscenario?view=skype-ps), è possibile modificare dinamicamente gli scenari in esecuzione. È possibile modificare gli scenari durante una sessione di registrazione, al fine di regolare o rifinire i dati che vengono raccolti, nonché i provider. 
  
Per eseguire le funzioni del servizio di registrazione centralizzata utilizzando Skype for Business Server Management Shell, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator basati sui ruoli o un ruolo RBAC personalizzato contenente uno di questi due gruppi. Per restituire un elenco di tutti i ruoli RBAC a cui è stato assegnato questo cmdlet, inclusi gli eventuali ruoli RBAC personalizzati creati dall'utente, eseguire il comando seguente da Skype for Business Server Management Shell o dal prompt di Windows PowerShell:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Ad esempio:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

Questo argomento si concentra sulle modalità di definizione di uno scenario, modifica di uno scenario, recupero degli scenari in esecuzione, rimozione di uno scenario e specificazione del contenuto di uno scenario, per l'ottimizzazione della risoluzione dei problemi. È possibile utilizzare Skype for Business Server Management Shell per emettere Windows PowerShell comandi. Quando si utilizza Windows PowerShell, è possibile definire nuovi scenari da utilizzare nelle sessioni di registrazione.
  
Come introdotto in [Centralized Logging Service in Skype for Business 2015,](centralized-logging-service.md)gli elementi di uno scenario sono:
  
- **Provider** Se si ha familiarità con OCSLogger, i provider sono i componenti che si sceglie di indicare a OCSLogger da quale motore di traccia raccogliere i log. I provider sono gli stessi componenti, e in molti casi ne condividono anche il nome, dei componenti in OCSLogger. Se non si ha familiarità con OCSLogger, i provider sono componenti specifici del ruolo del server da cui il servizio di registrazione centralizzata può raccogliere i log. Per informazioni dettagliate sulla configurazione dei provider, vedere [Configure providers for Centralized Logging Service in Skype for Business Server 2015.](configure-providers.md)
    
- **Identity** Il parametro -Identity imposta l'ambito e il nome dello scenario. Ad esempio, è possibile impostare un ambito "globale" e identificare lo scenario con "LyssServiceScenario". Quando si combinano i due elementi, si definisce l'identità (ad esempio, "global/LyssServiceScenario").
    
    Facoltativamente, è possibile utilizzare i parametri -Name e -Parent. Il parametro Name identifica lo scenario in maniera univoca. Se si utilizza il parametro Name, è necessario utilizzare anche il parametro Parent per aggiungere lo scenario all'ambito globale o sito. 
    
    > [!IMPORTANT]
    > Se si utilizzano i parametri Name e Parent, non è possibile utilizzare il **parametro -Identity.**
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>Per creare un nuovo scenario con il cmdlet New-CsClsScenario

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell.**
    
2. Per creare un nuovo scenario per una sessione di registrazione, utilizzare [New-CsClsProvider](/powershell/module/skype/new-csclsprovider?view=skype-ps) e definire il nome dello scenario (ovvero, un'identificazione univoca). Scegliere un tipo di formato di registrazione da WPP (ovvero, Windows software trace preprocessor e predefinito), EventLog (ovvero, il formato del registro eventi di Windows) o IISLog (ovvero, il file formato ASCII basato sul formato dei file di registro IIS). Definire quindi il livello (Secondo la definizione dei livelli di registrazione in questo argomento) e i contrassergni (secondo la definizione dei contrassegni in questo argomento).
    
    In questo scenario di esempio, utilizzeremo LyssProvider come provider variabile di esempio.
    
    Per creare uno scenario utilizzando le opzioni definite, digitare:
    
   ```PowerShell
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    Ad esempio:
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    Formato alternativo con -Name e -Parent:
    
   ```PowerShell
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>Per creare un nuovo scenario con provider multipli con il cmdlet New-CsClsScenario

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell.**
    
2. Esiste un limite di due scenari per ambito. Non esiste, tuttavia, un limite fisso di provider. In questo esempio, si supponga di aver creato tre provider, e di volerli assegnare tutti a uno scenario che si sta definendo. I nomi variabili dei provider sono LyssProvider, ABServerProvider e SIPStackProvider. Per definire e assegnare più provider a uno scenario, digitare quanto segue al prompt dei comandi di Skype for Business Server Management Shell o Windows PowerShell comando:
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > Come è noto in Windows PowerShell, la convenzione per la creazione di una tabella hash di valori tramite è nota `@{<variable>=<value1>, <value2>, <value>…}` comesplatting. Per informazioni dettagliate sulla creazione di Windows PowerShell, vedere [https://go.microsoft.com/fwlink/p/?LinkId=267760](/previous-versions/technet-magazine/gg675931(v=msdn.10)) . 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>Per modificare uno scenario esistente tramite il cmdlet Set-CsClsScenario

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell.**
    
2. Esiste un limite di due scenari per ambito. È possibile cambiare in qualunque momento lo scenario eseguito, anche quando è in esecuzione una sessione di raccolta di registri. Se si definisce nuovamente lo scenario in esecuzione, la sessione di raccolta smetterà di utilizzare lo scenario rimosso, e inizierà ad utilizzare il nuovo scenario. Tuttavia, le informazioni raccolte con lo scenario rimosso rimarranno nei registri. Per definire un nuovo scenario, eseguire le operazioni seguenti, presupponendo l'aggiunta di un provider già definito denominato "S4Provider":
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    Ad esempio:
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    Per sostituire un provider, definire un provider singolo o un elenco di provider separati da virgola a sostituzione dell'insieme esistente. Se si desidera sostituire uno dei molti provider, aggiungere i nuovi provider a quelli esistenti, per creare un insieme di provider contenente sia i provider esistenti che quelli nuovi. Per sostituire tutti i provider con un nuovo insieme, digitare:
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    Ad esempio, per sostituire l'insieme esistente di $LyssProvider, $ABServerProvider e $SIPStackProvider con $LyssServiceProvider:
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    Per sostituire soltanto il provider $LyssProvider dall'insieme corrente di $LyssProvider, $ABServerProvider e $SIPStackProvider con $LyssServiceProvider, digitare:
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>Per rimuovere uno scenario esistente tramite il cmdlet Remove-CsClsScenario

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell.**
    
2. Per rimuovere uno scenario precedentemente definito, digitare:
    
   ```PowerShell
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    Ad esempio, per rimuovere lo scenario definito:Redmond/LyssServiceScenario:
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

Il cmdlet **Remove-CsClsScenario** rimuove lo scenario specificato, ma le tracce acquisite restano disponibili nei registri per la ricerca.
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a>Per caricare e scaricare il cmdlet Edit-CsClsScenario utilizzando il modulo ClsScenarioEdit.psm1

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell.**
    
    > [!IMPORTANT]
    > Il modulo ClsScenarioEdit.psm1 viene fornito come download Web separato. Il modulo fa parte degli strumenti di Skype for Business Server 2015 Debugging. Per impostazione predefinita, gli strumenti di debug vengono installati nella directory C:\Programmi\Skype for Business Server 2015\Debugging Tools. 
  
2. Dal Windows PowerShell, digitare:
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > Il caricamento corretto del modulo torna al prompt Windows PowerShell comando. Per verificare che il modulo sia caricato e che Edit-CsClsScenario disponibile, digitare  `Get-Help Edit-CsClsScenario` . Dovrebbe essere visualizzato un riepilogo di base della sintassi per EditCsClsScenario. 
  
3. Per scaricare i moduli, digitare:
    
   ```PowerShell
   Remove-Module ClsController
   ```

    > [!TIP]
    > Lo scaricamento corretto del modulo torna al prompt dei Windows PowerShell comando. Per verificare che il modulo sia stato scaricato, digitare  `Get-Help Edit-CsClsScenario` . Windows PowerShell tenterà di individuare la Guida per il cmdlet e avrà esito negativo. 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>Per rimuovere un provider esistente da uno scenario attraverso il modulo Edit-ClsController

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell.**
    
2. Dal Windows PowerShell, digitare:
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > Il caricamento corretto del modulo torna al prompt Windows PowerShell comando. Per verificare che il modulo sia caricato e che Edit-CsClsScenario disponibile, digitare  `Get-Help Edit-CsClsScenario` . Dovrebbe essere visualizzato un riepilogo di base della sintassi per EditCsClsScenario. 
  
3. Per rimuovere un provider dallo scenario AlwaysOn, digitare:
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   Ad esempio:
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   I parametri ScenarioName e ProviderName sono parametri relativi alla posizione, ovvero devono essere definiti nella posizione della riga di comando attesa. Il nome del parametro non deve essere definito esplicitamente se il nome dello scenario si trova in posizione due e il provider in posizione tre, in relazione al nome del cmdlet in posizione uno. Attraverso queste informazioni, il comando precedente verrebbe digitato come:
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   Il posizionamento posizionale dei valori dei parametri si applica solo a -Scenario e -Provider. Tutti gli altri parametri devono essere definiti esplicitamente.
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>Per aggiungere un provider esistente a uno scenario attraverso il modulo Edit-ClsController

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell.**
    
2. Per aggiungere un provider allo scenario AlwaysOn, digitare:
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    Ad esempio:
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    -Loglevel può essere di tipo Fatal, Error, Warning, Info, Verbose, Debug o All. -Flags può essere uno qualsiasi dei flag supportati dal provider, ad esempio TF_COMPONENT, TF_DIAG. -Flags può anche essere di valore ALL
    
   L'esempio precedente può essere digitato anche attraverso la caratteristiche di posizione del cmdlet. Ad esempio, per aggiungere il provider ChatServer allo scenario AlwaysOn, digitare:
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```