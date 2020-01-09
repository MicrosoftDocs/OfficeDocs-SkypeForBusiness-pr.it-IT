---
title: Configurare gli scenari per il servizio di registrazione centralizzato in Skype for Business 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: 'Riepilogo: informazioni su come creare, modificare e rimuovere scenari per il servizio di registrazione centralizzato in Skype for Business Server 2015.'
ms.openlocfilehash: 9a6ce9a760255275c3ad265cdd6c58fa964f8e43
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991601"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a>Configurare gli scenari per il servizio di registrazione centralizzato in Skype for Business 2015
 
**Riepilogo:** Informazioni su come creare, modificare e rimuovere scenari per il servizio di registrazione centralizzato in Skype for Business Server 2015.
  
Gli scenari definiscono l'ambito (ovvero globale, sito, pool o computer) e i provider da usare nel servizio di registrazione centralizzata. Usando gli scenari, puoi abilitare o disabilitare la traccia sui provider, ad esempio S4, SIPStack, IM e Presence. Configurando uno scenario, è possibile raggruppare tutti i provider per una determinata raccolta logica che affrontano una specifica condizione di problema. Se si scopre che è necessario modificare uno scenario per soddisfare le esigenze di risoluzione dei problemi e registrazione, gli strumenti di debug di Skype for Business Server 2015 forniscono un modulo di Windows PowerShell denominato ClsScenarioEdit. psm1 che contiene una funzione namedEdit-CsClsScenario. Lo scopo del modulo consiste nel modificare le proprietà dello scenario denominato. In questo argomento sono disponibili alcuni esempi di funzionamento di questo modulo. Scaricare gli [strumenti di debug](https://go.microsoft.com/fwlink/p/?LinkId=285257) di Skype for Business Server 2015 prima di procedere.
  
> [!IMPORTANT]
> Per un ambito specifico, ovvero sito, globale, pool o computer, è possibile eseguire un massimo di due scenari in qualsiasi momento. Per determinare gli scenari attualmente in uso, usare Windows PowerShell e [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps). Usando Windows PowerShell e [Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps), è possibile modificare in modo dinamico gli scenari in uso. È possibile modificare gli scenari in corso durante una sessione di registrazione per modificare o affinare i dati che si stanno raccogliendo e da quali provider. 
  
Per eseguire le funzioni del servizio di registrazione centralizzato usando Skype for Business Server Management Shell, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contiene uno di questi due gruppi. Per restituire un elenco di tutti i ruoli RBAC a cui è stato assegnato questo cmdlet, inclusi i ruoli RBAC personalizzati creati personalmente, eseguire il comando seguente da Skype for Business Server Management Shell o dal prompt di Windows PowerShell:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Ad esempio:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

La parte restante di questo argomento illustra come definire uno scenario, modificare uno scenario, recuperare gli scenari in uso, rimuovere uno scenario e specificare lo scenario che contiene per ottimizzare la risoluzione dei problemi. Puoi usare Skype for Business Server Management Shell per emettere comandi di Windows PowerShell. Quando si usa Windows PowerShell, è possibile definire nuovi scenari da usare nelle sessioni di registrazione.
  
Come è stato introdotto in [servizio di registrazione centralizzato in Skype for Business 2015](centralized-logging-service.md), gli elementi di uno scenario sono i seguenti:
  
- **Provider** Se si ha familiarità con OCSLogger, i provider sono i componenti scelti per indicare a OCSLogger da quale motore di analisi deve raccogliere i log. I provider sono gli stessi componenti e in molti casi hanno lo stesso nome dei componenti in OCSLogger. Se non si ha familiarità con OCSLogger, i provider sono componenti specifici del ruolo del server a cui il servizio di registrazione centralizzata può raccogliere i log. Per informazioni dettagliate sulla configurazione dei provider, vedere [configurare i provider per il servizio di registrazione centralizzato in Skype for Business Server 2015](configure-providers.md).
    
- **Identità** Il parametro-Identity imposta l'ambito e il nome dello scenario. Ad esempio, puoi impostare un ambito di "globale" e identificare lo scenario con "LyssServiceScenario". Quando si combinano i due, si definisce l'identità, ad esempio "Global/LyssServiceScenario".
    
    Facoltativamente, è possibile usare i parametri-Name e-Parent. Puoi definire il parametro Name per identificare in modo univoco lo scenario. Se si usa nome, è necessario usare anche l'elemento padre per aggiungere lo scenario a globale o a sito. 
    
    > [!IMPORTANT]
    > Se si usano i parametri Name e Parent, non è possibile usare il parametro **-Identity** .
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>Per creare un nuovo scenario con il cmdlet New-CsClsScenario

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
2. Per creare un nuovo scenario per una sessione di registrazione, USA [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps) e Definisci il nome dello scenario, ovvero il modo in cui verrà identificato in modo univoco. Scegliere un tipo di formato di registrazione da WPP (ovvero il preprocessore di traccia del software Windows ed è il valore predefinito), EventLog (ovvero il formato del log eventi di Windows) o IISLog (ovvero file in formato ASCII basato sul formato del file di log di IIS). Definire quindi il livello (definito in livelli di registrazione in questo argomento) e i contrassegni (come definito in contrassegni in questo argomento).
    
    Per questo scenario di esempio, usiamo LyssProvider come variabile di provider di esempio.
    
    Per creare uno scenario usando le opzioni definite, digitare:
    
   ```PowerShell
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    Ad esempio:
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    Il formato alternativo using-Name e-Parent:
    
   ```PowerShell
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>Per creare un nuovo scenario con più provider con il cmdlet New-CsClsScenario

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
2. Si è limitati a due scenari per ogni ambito. Tuttavia, non si è limitati a un determinato numero di provider. In questo esempio, supponiamo di avere creato tre provider e di assegnare tutti e tre allo scenario che stai definendo. I nomi delle variabili del provider sono LyssProvider, ABServerProvider e SIPStackProvider. Per definire e assegnare più provider a uno scenario, digitare quanto segue in un prompt dei comandi di Skype for Business Server Management Shell o Windows PowerShell:
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > Come è noto in Windows PowerShell, la convenzione per la creazione di una tabella hash di valori `@{<variable>=<value1>, <value2>, <value>…}` usando è nota assplatting. Per informazioni dettagliate su splatting in Windows PowerShell, [https://go.microsoft.com/fwlink/p/?LinkId=267760](https://go.microsoft.com/fwlink/p/?LinkId=267760)vedere. 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>Per modificare uno scenario esistente con il cmdlet Set-CsClsScenario

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
2. Si è limitati a due scenari per ogni ambito. È possibile modificare gli scenari in esecuzione in qualsiasi momento, anche quando è in corso una sessione di acquisizione di registrazione. Se si ridefiniscono gli scenari in uso, la sessione di registrazione corrente smetterà di usare lo scenario rimosso e quindi inizierà a usare il nuovo scenario. Tuttavia, le informazioni di registrazione acquisite con lo scenario rimosso restano nei registri acquisiti. Per definire un nuovo scenario, eseguire le operazioni seguenti, ad esempio supponendo che l'aggiunta di un provider già definito denominato "S4Provider":
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    Ad esempio:
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    Se si vuole sostituire i provider, definire un singolo provider o un elenco di provider separati da virgole per sostituire il set corrente. Se si vuole sostituire solo uno di molti provider, aggiungere i provider correnti con i nuovi provider per creare un nuovo set di provider che contiene sia i nuovi provider che i provider esistenti. Per sostituire tutti i provider con un nuovo set, digitare quanto segue:
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    Ad esempio, per sostituire il set corrente di $LyssProvider, $ABServerProvider e $SIPStackProvider con $LyssServiceProvider:
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    Per sostituire solo il provider $LyssProvider dal set corrente di $LyssProvider, $ABServerProvider e $SIPStackProvider con $LyssServiceProvider, digitare quanto segue:
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>Per rimuovere uno scenario esistente con il cmdlet Remove-CsClsScenario

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
2. Se si vuole rimuovere uno scenario definito in precedenza, digitare quanto segue:
    
   ```PowerShell
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    Ad esempio, per rimuovere il sito scenario definito: Redmond/LyssServiceScenario:
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

Il cmdlet **Remove-CsClsScenario** rimuove lo scenario specificato, ma le tracce acquisite sono ancora disponibili nei registri in cui eseguire la ricerca.
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a>Per caricare e scaricare il cmdlet Edit-CsClsScenario usando il modulo ClsScenarioEdit. psm1

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
    > [!IMPORTANT]
    > Il modulo ClsScenarioEdit. psm1 viene fornito come download Web separato. Il modulo fa parte degli strumenti di debug di Skype for Business Server 2015. Per impostazione predefinita, gli strumenti di debug sono installati nella directory C:\Program Skype for Business Server 2015 \ Debugging Tools. 
  
2. In Windows PowerShell digitare:
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > Il caricamento riuscito del modulo restituisce il prompt dei comandi di Windows PowerShell. Per verificare che il modulo sia caricato e che la modifica-CsClsScenario sia disponibile, `Get-Help Edit-CsClsScenario`Digitare. Dovresti vedere la sinossi di base della sintassi per EditCsClsScenario. 
  
3. Per scaricare i moduli, digitare:
    
   ```PowerShell
   Remove-Module ClsController
   ```

    > [!TIP]
    > Il riuscito scarico del modulo restituisce il prompt dei comandi di Windows PowerShell. Per verificare che il modulo sia scaricato, digitare `Get-Help Edit-CsClsScenario`. Windows PowerShell tenterà di individuare la guida per il cmdlet e non riesce. 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>Per rimuovere un provider esistente da uno scenario con il modulo Edit-ClsController

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
2. In Windows PowerShell digitare:
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > Il caricamento riuscito del modulo restituisce il prompt dei comandi di Windows PowerShell. Per verificare che il modulo sia caricato e che la modifica-CsClsScenario sia disponibile, `Get-Help Edit-CsClsScenario`Digitare. Dovresti vedere la sinossi di base della sintassi per EditCsClsScenario. 
  
3. Per rimuovere un provider dallo scenario AlwaysOn, digitare:
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   Per esempio:
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   I parametri ScenarioName e ProviderName sono posizionali, ovvero devono essere definiti nella posizione prevista nella riga di comando. Il nome del parametro non deve essere definito in modo esplicito se il nome dello scenario è nella posizione due e il provider è nella posizione tre, in relazione al nome del cmdlet come posizione uno. Usando queste informazioni, il comando precedente verrebbe tipizzato come segue:
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   La posizione di posizionamento dei valori di parametro si applica solo a-scenario e-provider. Tutti gli altri parametri devono essere definiti in modo esplicito.
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>Per aggiungere un provider a uno scenario con il modulo Edit-ClsController

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
2. Per aggiungere un provider allo scenario AlwaysOn, digitare:
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    Per esempio:
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    -LogLevel può essere di tipo Fatal, Error, Warning, info, Verbose, debug o all. -I flag possono essere uno dei contrassegni supportati dal provider, ad esempio TF_COMPONENT, TF_DIAG. -Flags può anche essere di valore ALL
    
   L'esempio precedente può anche essere digitato usando la caratteristica posizionali del cmdlet. Ad esempio, per aggiungere il provider ChatServer allo scenario AlwaysOn, digitare:
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```
