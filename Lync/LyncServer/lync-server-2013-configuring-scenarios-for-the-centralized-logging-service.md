---
title: 'Lync Server 2013: configurazione degli scenari per il servizio di registrazione centralizzato'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring scenarios for the Centralized Logging Service
ms:assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688085(v=OCS.15)
ms:contentKeyID: 49733682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a39bcd23516970edf1c4694a8eff1ecb682eda1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041025"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-scenarios-for-the-centralized-logging-service-in-lync-server-2013"></a>Configurazione degli scenari per il servizio di registrazione centralizzato in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-05_

Gli scenari definiscono l'ambito (ovvero globale, sito, pool o computer) e quali provider utilizzare nel servizio di registrazione centralizzato. Attraverso gli scenari si attivano o disattivano le tracce per i provider (ad esempio, S4, SIPStack, messaggistica immediata e presenza). Attraverso la configurazione di uno scenario, è possibile raggruppare tutti i provider per una data raccolta logica relativa a un problema specifico. Se si rileva che è necessario modificare uno scenario per soddisfare la risoluzione dei problemi e le esigenze di registrazione, gli strumenti di debug di Lync Server 2013 forniscono un modulo di Windows PowerShell denominato *ClsController. psm1* che contiene una funzione denominata *Edit-CsClsScenario*. Il modulo consente di modificare le proprietà dello scenario. In questo argomento sono forniti esempi di funzionamento del modulo. Gli strumenti di debug di Lync Server 2013 vengono scaricati dal collegamento seguente:[http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)

<div>


> [!IMPORTANT]  
> Per un determinato ambito (sito, globale, pool o computer), è possibile eseguire un massimo di due scenari alla volta. Per determinare gli scenari attualmente in esecuzione, utilizzare Windows PowerShell e <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">Get-CsClsScenario</A>. Utilizzando Windows PowerShell e <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">Set-CsClsScenario</A>, è possibile modificare in modo dinamico gli scenari in esecuzione. È possibile modificare gli scenari durante una sessione di registrazione, al fine di regolare o rifinire i dati che vengono raccolti, nonché i provider.



</div>

Per eseguire le funzioni del servizio di registrazione centralizzato utilizzando Lync Server Management Shell, è necessario essere membri dei gruppi di sicurezza di CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contenga uno di questi due gruppi. Per restituire un elenco di tutti i ruoli RBAC a cui è stato assegnato questo cmdlet, inclusi i ruoli RBAC personalizzati creati dall'utente, eseguire il comando seguente da Lync Server Management Shell o dal prompt di Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Ad esempio:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

Questo argomento si concentra sulle modalità di definizione di uno scenario, modifica di uno scenario, recupero degli scenari in esecuzione, rimozione di uno scenario e specificazione del contenuto di uno scenario, per l'ottimizzazione della risoluzione dei problemi. Esistono due modi per emettere comandi del servizio di registrazione centralizzata. È possibile\\utilizzare CLSController. exe che si trova, per impostazione predefinita, nella directory C: Program Files\\Common files\\Microsoft Lync Server 2013\\CLSAgent. In alternativa, è possibile utilizzare Lync Server Management Shell per emettere comandi di Windows PowerShell. Quando si utilizza CLSController.exe, nella riga di comando esiste una selezione di scenari disponibili finita. Quando si utilizza Windows PowerShell, è possibile definire nuovi scenari per l'utilizzo nelle sessioni di registrazione.

Come descritto in [Panoramica del servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), gli elementi di uno scenario sono:

  - **Providers**   se si ha familiarità con OCSLogger, i provider sono i componenti scelti per indicare a OCSLogger cosa dovrebbe raccogliere i log dal motore di traccia. I provider sono gli stessi componenti, e in molti casi ne condividono anche il nome, dei componenti in OCSLogger. Se non si ha familiarità con OCSLogger, i provider sono componenti specifici del ruolo del server in cui il servizio di registrazione centralizzato può raccogliere i log. Per informazioni dettagliate sulla configurazione dei provider, vedere [configurazione di provider per il servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md).

  - **Identity**   il parametro – Identity consente di impostare l'ambito e il nome dello scenario. Ad esempio, è possibile impostare un ambito “globale” e identificare lo scenario con “LyssServiceScenario”. Quando si combinano le due cose, si definisce il parametro Identity (ad esempio, “global/LyssServiceScenario”).
    
    Facoltativamente è possibile utilizzare i parametri –Name and –Parent. Il parametro Name identifica lo scenario in maniera univoca. Se si utilizza il parametro Name, è necessario utilizzare anche il parametro Parent per aggiungere lo scenario all'ambito globale o sito.
    
    <div>
    

    > [!IMPORTANT]  
    > Se si utilizzano i parametri Name e Parent, non è possibile utilizzare il parametro <STRONG>–Identity</STRONG>.

    
    </div>

<div>

## <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>Per creare un nuovo scenario con il cmdlet New-CsClsScenario

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Per creare un nuovo scenario per una sessione di registrazione, utilizzare [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider) e definire il nome dello scenario (ovvero, un'identificazione univoca). Scegliere un tipo di formato di registrazione da WPP (ovvero, Windows software trace preprocessor e predefinito), EventLog (ovvero, il formato del registro eventi di Windows) o IISLog (ovvero, il file formato ASCII basato sul formato dei file di registro IIS). Definire quindi il livello (Secondo la definizione dei livelli di registrazione in questo argomento) e i contrassergni (secondo la definizione dei contrassegni in questo argomento).
    
    In questo scenario di esempio, utilizzeremo LyssProvider come provider variabile di esempio.
    
    Per creare uno scenario utilizzando le opzioni definite, digitare:
    
        New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
    
    Ad esempio:
    
        New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
    
    Il formato alternativo, –Name e –Parent:
    
        New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider

</div>

<div>

## <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>Per creare un nuovo scenario con provider multipli con il cmdlet New-CsClsScenario

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Esiste un limite di due scenari per ambito. Non esiste, tuttavia, un limite fisso di provider. In questo esempio, si supponga di aver creato tre provider, e di volerli assegnare tutti a uno scenario che si sta definendo. I nomi variabili dei provider sono LyssProvider, ABServerProvider e SIPStackProvider. Per definire e assegnare più provider a uno scenario, digitare il comando seguente in un prompt dei comandi di Lync Server Management Shell o di Windows PowerShell:
    
        New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
    
    <div>
    

    > [!NOTE]  
    > Come è noto in Windows PowerShell, la convenzione per la creazione di una tabella hash di valori <CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE> utilizzando è nota come <EM>splatting</EM>. Per informazioni dettagliate su splatting in Windows PowerShell, <A href="http://go.microsoft.com/fwlink/p/?linkid=267760">http://go.microsoft.com/fwlink/p/?LinkId=267760</A>vedere.

    
    </div>

</div>

<div>

## <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>Per modificare uno scenario esistente tramite il cmdlet Set-CsClsScenario

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Esiste un limite di due scenari per ambito. È possibile cambiare in qualunque momento lo scenario eseguito, anche quando è in esecuzione una sessione di raccolta di registri. Se si definisce nuovamente lo scenario in esecuzione, la sessione di raccolta smetterà di utilizzare lo scenario rimosso, e inizierà ad utilizzare il nuovo scenario. Tuttavia, le informazioni raccolte con lo scenario rimosso rimarranno nei registri. Per definire un nuovo scenario, eseguire le operazioni seguenti (supponiamo che è stato aggiunto un nome di provider già definito, chiamato “S4Provider”):
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
    
    Ad esempio:
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
    
    Per sostituire un provider, definire un provider singolo o un elenco di provider separati da virgola a sostituzione dell'insieme esistente. Se si desidera sostituire uno dei molti provider, aggiungere i nuovi provider a quelli esistenti, per creare un insieme di provider contenente sia i provider esistenti che quelli nuovi. Per sostituire tutti i provider con un nuovo insieme, digitare:
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
    
    Ad esempio, per sostituire l'insieme esistente di $LyssProvider, $ABServerProvider e $SIPStackProvider con $LyssServiceProvider:
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
    
    Per sostituire soltanto il provider $LyssProvider dall'insieme corrente di $LyssProvider, $ABServerProvider e $SIPStackProvider con $LyssServiceProvider, digitare:
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}

</div>

<div>

## <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>Per rimuovere uno scenario esistente tramite il cmdlet Remove-CsClsScenario

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Per rimuovere uno scenario precedentemente definito, digitare:
    
        Remove-CsClsScenario -Identity <name of scope and scenario>
    
    Ad esempio, per rimuovere lo scenario definito:Redmond/LyssServiceScenario:
    
        Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"

Il cmdlet **Remove-CsClsScenario** rimuove lo scenario specificato, ma le tracce acquisite restano disponibili nei registri per la ricerca.

</div>

<div>

## <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clscontrollerpsm1-module"></a>Per caricare e scaricare il cmdlet Edit-CsClsScenario attraverso il modulo ClsController.psm1

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.
    
    <div>
    

    > [!IMPORTANT]  
    > Il modulo ClsController.psm1 è fornito come download Web separato. Il modulo fa parte degli strumenti di debug di Lync Server 2013. Per impostazione predefinita, gli strumenti di debug sono installati nella cartella C:\Program Files\Lync Server 2013\Debugging Tools.

    
    </div>

2.  Da Windows PowerShell, digitare:
    
        Import-Module "C:\Program Files\Lync Server 2013\Debugging Tools\ClsController.psm1"
    
    <div>
    

    > [!TIP]  
    > Il corretto caricamento del modulo restituisce il messaggio al prompt dei comandi di Windows PowerShell. Per verificare che il modulo sia caricato e che sia disponibile Edit-CsClsScenario, digitare <CODE>Get-Help Edit-CsClsScenario</CODE>. Dovrebbe essere visualizzato un riepilogo di base della sintassi per EditCsClsScenario.

    
    </div>

3.  Per scaricare i moduli, digitare:
    
        Remove-Module ClsController
    
    <div>
    

    > [!TIP]  
    > Lo scaricamento riuscito del modulo restituisce il messaggio al prompt dei comandi di Windows PowerShell. Per verificare che il modulo sia scaricato, digitare <CODE>Get-Help Edit-CsClsScenario</CODE>. Windows PowerShell tenterà di individuare la guida per il cmdlet e avrà esito negativo.

    
    </div>

</div>

<div>

## <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>Per rimuovere un provider esistente da uno scenario attraverso il modulo Edit-ClsController

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Per rimuovere un provider dallo scenario AlwaysOn, digitare:
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
    
    Ad esempio:
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
    
    I parametri ScenarioName e ProviderName sono parametri relativi alla posizione, ovvero devono essere definiti nella posizione della riga di comando attesa. Il nome del parametro non deve essere definito esplicitamente se il nome dello scenario si trova in posizione due e il provider in posizione tre, in relazione al nome del cmdlet in posizione uno. Attraverso queste informazioni, il comando precedente verrebbe digitato come:
    
        Edit-CsClsScenario AlwaysOn ChatServer -Remove
    
    Questo tipo di posizionamento del valore del parametro si applica soltanto ai parametri –Scenario e –Provider. Tutti gli altri parametri devono essere definiti esplicitamente.

</div>

<div>

## <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>Per aggiungere un provider esistente a uno scenario attraverso il modulo Edit-ClsController

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Per aggiungere un provider allo scenario AlwaysOn, digitare:
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
    
    Ad esempio:
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
    
    \-LogLevel può essere di tipo fatale, Error, Warning, info, Verbose, debug o all. : I flag possono corrispondere a qualsiasi flag supportato dal provider, ad esempio TF\_\_diag. –Il valore dei contrassegni, inoltre, può essere ALL
    
    L'esempio precedente può essere digitato anche attraverso la caratteristiche di posizione del cmdlet. Ad esempio, per aggiungere il provider ChatServer allo scenario AlwaysOn, digitare:
    
        Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL

</div>

</div>

<span> </span>

</div>

</div>

</div>

