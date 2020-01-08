---
title: 'Lync Server 2013: configurazione degli scenari per il servizio di registrazione centralizzata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring scenarios for the Centralized Logging Service
ms:assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688085(v=OCS.15)
ms:contentKeyID: 49733682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abc0be2ac6459c34546de41ee7e2c709e0d0c0f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-scenarios-for-the-centralized-logging-service-in-lync-server-2013"></a>Configurazione di scenari per il servizio di registrazione centralizzato in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-02-05_

Gli scenari definiscono l'ambito (ovvero globale, sito, pool o computer) e i provider da usare nel servizio di registrazione centralizzata. Usando gli scenari, puoi abilitare o disabilitare la traccia sui provider, ad esempio S4, SIPStack, IM e Presence. Configurando uno scenario, è possibile raggruppare tutti i provider per una determinata raccolta logica che affrontano una specifica condizione di problema. Se si scopre che è necessario modificare uno scenario in base alle esigenze di risoluzione dei problemi e alla registrazione, gli strumenti di debug di Lync Server 2013 forniscono un modulo di Windows PowerShell denominato *ClsController. psm1* che contiene una funzione denominata *Edit-CsClsScenario*. Lo scopo del modulo consiste nel modificare le proprietà dello scenario denominato. In questo argomento sono disponibili alcuni esempi di funzionamento di questo modulo. Gli strumenti di debug di Lync Server 2013 vengono scaricati dal collegamento seguente:[http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)

<div>


> [!IMPORTANT]  
> Per un ambito specifico, ovvero sito, globale, pool o computer, è possibile eseguire un massimo di due scenari in qualsiasi momento. Per determinare gli scenari attualmente in uso, usare Windows PowerShell e <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">Get-CsClsScenario</A>. Usando Windows PowerShell e <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">Set-CsClsScenario</A>, è possibile modificare in modo dinamico gli scenari in uso. È possibile modificare gli scenari in corso durante una sessione di registrazione per modificare o affinare i dati che si stanno raccogliendo e da quali provider.



</div>

Per eseguire le funzioni del servizio di registrazione centralizzato tramite Lync Server Management Shell, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contenga uno di questi due gruppi. Per restituire un elenco di tutti i ruoli RBAC a cui è stato assegnato questo cmdlet, inclusi i ruoli RBAC personalizzati creati personalmente, eseguire il comando seguente da Lync Server Management Shell o dal prompt di Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Ad esempio:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

La parte restante di questo argomento illustra come definire uno scenario, modificare uno scenario, recuperare gli scenari in uso, rimuovere uno scenario e specificare lo scenario che contiene per ottimizzare la risoluzione dei problemi. Esistono due modi per emettere comandi di servizio di registrazione centralizzati. Per impostazione predefinita, è possibile usare CLSController. exe nella directory C\\: programmi\\comuni di\\Microsoft Lync Server 2013\\CLSAgent. In alternativa, puoi usare Lync Server Management Shell per emettere comandi di Windows PowerShell. La distinzione importante è che quando si usa CLSController. exe alla riga di comando è disponibile una selezione limitata di scenari. Quando si usa Windows PowerShell, è possibile definire nuovi scenari da usare nelle sessioni di registrazione.

Come è stato introdotto in [Panoramica del servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), gli elementi di uno scenario sono i seguenti:

  - **Providers**   se si ha familiarità con OCSLogger, i provider sono i componenti scelti per indicare a OCSLogger da quale motore di analisi deve raccogliere i log. I provider sono gli stessi componenti e in molti casi hanno lo stesso nome dei componenti in OCSLogger. Se non si ha familiarità con OCSLogger, i provider sono componenti specifici del ruolo del server a cui il servizio di registrazione centralizzata può raccogliere i log. Per informazioni dettagliate sulla configurazione dei provider, vedere [configurazione di provider per il servizio di registrazione centralizzata in Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md).

  - **Identity**   il parametro: Identity imposta l'ambito e il nome dello scenario. Ad esempio, puoi impostare un ambito di "globale" e identificare lo scenario con "LyssServiceScenario". Quando si combinano i due, si definisce l'identità, ad esempio "Global/LyssServiceScenario".
    
    Facoltativamente, è possibile usare i parametri-Name e-Parent. Puoi definire il parametro Name per identificare in modo univoco lo scenario. Se si usa nome, è necessario usare anche l'elemento padre per aggiungere lo scenario a globale o a sito.
    
    <div>
    

    > [!IMPORTANT]  
    > Se si usano i parametri Name e Parent, non è possibile usare il parametro <STRONG>– Identity</STRONG> .

    
    </div>

<div>

## <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>Per creare un nuovo scenario con il cmdlet New-CsClsScenario

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Per creare un nuovo scenario per una sessione di registrazione, USA [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider) e Definisci il nome dello scenario, ovvero il modo in cui verrà identificato in modo univoco. Scegliere un tipo di formato di registrazione da WPP (ovvero il preprocessore di traccia del software Windows ed è il valore predefinito), EventLog (ovvero il formato del log eventi di Windows) o IISLog (ovvero file in formato ASCII basato sul formato del file di log di IIS). Definire quindi il livello (definito in livelli di registrazione in questo argomento) e i contrassegni (come definito in contrassegni in questo argomento).
    
    Per questo scenario di esempio, usiamo LyssProvider come variabile di provider di esempio.
    
    Per creare uno scenario usando le opzioni definite, digitare:
    
        New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
    
    Ad esempio:
    
        New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
    
    Formato alternativo con-nome e-padre:
    
        New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider

</div>

<div>

## <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>Per creare un nuovo scenario con più provider con il cmdlet New-CsClsScenario

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Si è limitati a due scenari per ogni ambito. Tuttavia, non si è limitati a un determinato numero di provider. In questo esempio, supponiamo di avere creato tre provider e di assegnare tutti e tre allo scenario che stai definendo. I nomi delle variabili del provider sono LyssProvider, ABServerProvider e SIPStackProvider. Per definire e assegnare più provider a uno scenario, digitare quanto segue in un prompt dei comandi di Lync Server Management Shell o Windows PowerShell:
    
        New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
    
    <div>
    

    > [!NOTE]  
    > Come è noto in Windows PowerShell, la convenzione per la creazione di una tabella hash di valori <CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE> usando è nota come <EM>splatting</EM>. Per informazioni dettagliate su splatting in Windows PowerShell, <A href="http://go.microsoft.com/fwlink/p/?linkid=267760">http://go.microsoft.com/fwlink/p/?LinkId=267760</A>vedere.

    
    </div>

</div>

<div>

## <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>Per modificare uno scenario esistente con il cmdlet Set-CsClsScenario

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Si è limitati a due scenari per ogni ambito. È possibile modificare gli scenari in esecuzione in qualsiasi momento, anche quando è in corso una sessione di acquisizione di registrazione. Se si ridefiniscono gli scenari in uso, la sessione di registrazione corrente smetterà di usare lo scenario rimosso e quindi inizierà a usare il nuovo scenario. Tuttavia, le informazioni di registrazione acquisite con lo scenario rimosso restano nei registri acquisiti. Per definire un nuovo scenario, eseguire le operazioni seguenti, ad esempio supponendo che l'aggiunta di un provider già definito denominato "S4Provider":
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
    
    Ad esempio:
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
    
    Se si vuole sostituire i provider, definire un singolo provider o un elenco di provider separati da virgole per sostituire il set corrente. Se si vuole sostituire solo uno di molti provider, aggiungere i provider correnti con i nuovi provider per creare un nuovo set di provider che contiene sia i nuovi provider che i provider esistenti. Per sostituire tutti i provider con un nuovo set, digitare quanto segue:
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
    
    Ad esempio, per sostituire il set corrente di $LyssProvider, $ABServerProvider e $SIPStackProvider con $LyssServiceProvider:
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
    
    Per sostituire solo il provider $LyssProvider dal set corrente di $LyssProvider, $ABServerProvider e $SIPStackProvider con $LyssServiceProvider, digitare quanto segue:
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}

</div>

<div>

## <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>Per rimuovere uno scenario esistente con il cmdlet Remove-CsClsScenario

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Se si vuole rimuovere uno scenario definito in precedenza, digitare quanto segue:
    
        Remove-CsClsScenario -Identity <name of scope and scenario>
    
    Ad esempio, per rimuovere il sito scenario definito: Redmond/LyssServiceScenario:
    
        Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"

Il cmdlet **Remove-CsClsScenario** rimuove lo scenario specificato, ma le tracce acquisite sono ancora disponibili nei registri in cui eseguire la ricerca.

</div>

<div>

## <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clscontrollerpsm1-module"></a>Per caricare e scaricare il cmdlet Edit-CsClsScenario usando il modulo ClsController. psm1

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.
    
    <div>
    

    > [!IMPORTANT]  
    > Il modulo ClsController. psm1 viene fornito come download Web separato. Il modulo fa parte degli strumenti di debug di Lync Server 2013. Per impostazione predefinita, gli strumenti di debug sono installati nella directory C:\Program Files\Lync Server 2013 \ Debugging Tools.

    
    </div>

2.  In Windows PowerShell digitare:
    
        Import-Module "C:\Program Files\Lync Server 2013\Debugging Tools\ClsController.psm1"
    
    <div>
    

    > [!TIP]  
    > Il caricamento riuscito del modulo restituisce il prompt dei comandi di Windows PowerShell. Per verificare che il modulo sia caricato e che la modifica-CsClsScenario sia disponibile, <CODE>Get-Help Edit-CsClsScenario</CODE>Digitare. Dovresti vedere la sinossi di base della sintassi per EditCsClsScenario.

    
    </div>

3.  Per scaricare i moduli, digitare:
    
        Remove-Module ClsController
    
    <div>
    

    > [!TIP]  
    > Il riuscito scarico del modulo restituisce il prompt dei comandi di Windows PowerShell. Per verificare che il modulo sia scaricato, digitare <CODE>Get-Help Edit-CsClsScenario</CODE>. Windows PowerShell tenterà di individuare la guida per il cmdlet e non riesce.

    
    </div>

</div>

<div>

## <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>Per rimuovere un provider esistente da uno scenario con il modulo Edit-ClsController

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Per rimuovere un provider dallo scenario AlwaysOn, digitare:
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
    
    Per esempio:
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
    
    I parametri ScenarioName e ProviderName sono posizionali, ovvero devono essere definiti nella posizione prevista nella riga di comando. Il nome del parametro non deve essere definito in modo esplicito se il nome dello scenario è nella posizione due e il provider è nella posizione tre, in relazione al nome del cmdlet come posizione uno. Usando queste informazioni, il comando precedente verrebbe tipizzato come segue:
    
        Edit-CsClsScenario AlwaysOn ChatServer -Remove
    
    La posizione di posizionamento dei valori di parametro si applica solo a-scenario e-provider. Tutti gli altri parametri devono essere definiti in modo esplicito.

</div>

<div>

## <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>Per aggiungere un provider a uno scenario con il modulo Edit-ClsController

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Per aggiungere un provider allo scenario AlwaysOn, digitare:
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
    
    Per esempio:
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
    
    \-LogLevel può essere di tipo Fatal, Error, Warning, info, Verbose, debug o all. : I contrassegni possono essere uno dei contrassegni supportati dal provider, ad esempio\_TF Component,\_TF diag. -Flags può anche essere di valore ALL
    
    L'esempio precedente può anche essere digitato usando la caratteristica posizionali del cmdlet. Ad esempio, per aggiungere il provider ChatServer allo scenario AlwaysOn, digitare:
    
        Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL

</div>

</div>

<span> </span>

</div>

</div>

</div>

