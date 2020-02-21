---
title: 'Lync Server 2013: configurazione dei provider per il servizio di registrazione centralizzato'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring providers for Centralized Logging Service
ms:assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688082(v=OCS.15)
ms:contentKeyID: 49733678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bc8ad2f5372ee9b434a1236e9d0cbba0f34a5de
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204872"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-providers-for-centralized-logging-service-in-lync-server-2013"></a>Configurazione dei provider per il servizio di registrazione centralizzato in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-03-19_

I concetti e la configurazione dei *provider* nel servizio di registrazione centralizzato è uno dei più importanti da afferrare. I *provider* vengono mappati direttamente ai componenti del ruolo del server Lync Server nel modello di traccia di Lync Server. Il provider definisce i componenti di un Lync Server 2013 che verranno rintracciati, il tipo di messaggi (ad esempio, fatale, errore o avviso) da raccogliere e i flag, ad esempio la connessione TF\_o TF\_diag. I provider sono i componenti tracciabili in ogni ruolo del server Lync Server. Tramite i provider vengono definiti il livello e il tipo di traccia per i componenti (ad esempio, S4, SIPStack, messaggistica istantanea e presenza). Il provider definito viene utilizzato in uno scenario per raggruppare tutti i provider per una determinata raccolta logica riferita a una condizione problematica specifica.

Per eseguire le funzioni del servizio di registrazione centralizzato utilizzando Lync Server Management Shell, è necessario essere membri dei gruppi di sicurezza di CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contenga uno dei questi due gruppi. Per restituire un elenco di tutti i ruoli RBAC (Role-Based Access Control) a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati autonomamente), eseguire il comando seguente da Lync Server Management Shell o dal prompt di Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Ad esempio:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

La parte restante di questo argomento è incentrata su come definire i provider, modificare un provider e la definizione di un provider che contiene per ottimizzare la risoluzione dei problemi. Esistono due modi per emettere comandi del servizio di registrazione centralizzata. È possibile\\utilizzare CLSController. exe che si trova, per impostazione predefinita, nella directory C: Program Files\\Common files\\Microsoft Lync Server 2013\\CLSAgent. In alternativa, è possibile utilizzare Lync Server Management Shell per emettere comandi di Windows PowerShell. La distinzione importante è che quando si utilizza CLSController. exe nella riga di comando è disponibile una selezione limitata di scenari in cui i provider sono già definiti e non sono modificabili, ma è possibile definire il livello di registrazione. Utilizzando Windows PowerShell, è possibile definire nuovi provider per l'utilizzo nelle sessioni di registrazione e avere il controllo completo sulla creazione, su cosa raccolgono e sul livello di raccolta dei dati.

<div class="">


> [!IMPORTANT]  
> Come già accennato, i provider sono uno strumento dalle grandi potenzialità. Gli scenari, tuttavia, sono ancora più efficaci perché incorporano tutte le informazioni necessarie per impostare ed eseguire la traccia sui componenti rappresentati dai provider. Dato che gli scenari sono in effetti una raccolta di provider, possono essere paragonati all'esecuzione di un file batch contenente centinaia di comandi per raccogliere grandi quantità di informazioni anziché eseguire centinaia di comandi, uno alla volta, dalla riga di comando.<BR>Invece di richiedere di approfondire i dettagli dei provider, il servizio di registrazione centralizzato fornisce una serie di scenari già definiti per l'utente. Gli scenari forniti coprono la maggior parte dei possibili problemi che verranno riscontrati. In rari casi, potrebbe essere necessario creare e definire provider e assegnarli a scenari. È consigliabile acquisire familiarità con tutti gli scenari forniti prima di esaminare la necessità di creare nuovi provider e scenari. Anche se le informazioni sulla creazione di provider sono disponibili in questo articolo per familiarizzare con la modalità di utilizzo degli elementi provider per raccogliere informazioni di traccia, i dettagli sui provider stessi non vengono forniti in questo momento.



</div>

Introdotti in [Panoramica del servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), gli elementi principali per la definizione di un provider per l'utilizzo in uno scenario sono:

  - **Providers**   se si ha familiarità con OCSLogger, i provider sono i componenti scelti per indicare a OCSLogger cosa dovrebbe raccogliere i log dal motore di traccia. I provider sono gli stessi componenti, e in molti casi ne condividono anche il nome, dei componenti in OCSLogger. Se non si ha familiarità con OCSLogger, i provider sono componenti specifici del ruolo del server in cui il servizio di registrazione centralizzato può raccogliere i log. Nel caso del servizio di registrazione centralizzato, CLSAgent è la parte architettonica del servizio di registrazione centralizzato che esegue la traccia dei componenti definiti nella configurazione di provider.

  - **Livelli di registrazione**   OCSLogger è stata fornita la possibilità di scegliere un certo numero di livelli di dettaglio per i dati raccolti. Questa funzionalità è parte integrante del servizio di registrazione centralizzato e degli scenari ed è definita dal parametro **Type** . È possibile scegliere una delle seguenti opzioni:
    
      - **Tutti**   i messaggi di traccia di tipo fatale, errore, avviso e informazioni vengono raccolti nel registro per il provider definito.
    
      - **Fatal**   raccoglie solo i messaggi di traccia che indicano un errore per il provider definito.
    
      - **L'errore**   raccoglie solo i messaggi di traccia che indicano un errore per il provider definito, oltre ai messaggi irreversibili.
    
      - **Avviso**   raccoglie solo i messaggi di traccia che indicano un avviso per il provider definito, oltre a messaggi fatali e di errore.
    
      - **Info**   raccoglie solo i messaggi di traccia che indicano un messaggio informativo per il provider definito, oltre a messaggi fatali, di errore e di avviso.
    
      - **Verbose**   raccoglie tutti i messaggi di traccia di tipo fatale, Error, Warning e info per il provider definito.

  - **Flags**   OCSLogger è stata fornita la possibilità di scegliere flag per ogni provider che ha definito il tipo di informazioni che è possibile recuperare dai file di traccia. È possibile scegliere tra i flag seguenti, in base al provider:
    
      - **La\_connessione**   TF fornisce le voci di registro correlate alla connessione. Questi log includono informazioni sulle connessioni stabilite con e da un particolare componente. Potrebbero essere anche incluse informazioni significative a livello di rete, ovvero per componenti non correlati al concetto di connessione.
    
      - **La\_sicurezza**   TF fornisce tutti gli eventi e le voci di registro relative alla sicurezza. Per SipStack, ad esempio, si tratta degli eventi di sicurezza come errori di convalida del dominio ed errori di autenticazione/autorizzazione dei client.
    
      - **TF\_diag**   fornisce gli eventi di diagnostica che è possibile utilizzare per diagnosticare o risolvere i problemi del componente. Per SipStack, ad esempio, si tratta di errori dei certificati oppure di avvisi/errori DNS.
    
      - **TF\_Protocol**   fornisce messaggi di protocollo, ad esempio messaggi SIP e combinati di codec community.
    
      - **Il\_componente**   TF consente di abilitare la registrazione sui componenti specificati come parte dei provider.
    
      - **All**   consente di impostare tutti i flag disponibili per il provider.

<div>

## <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>Per esaminare le informazioni sui provider di scenari del servizio di registrazione centralizzato esistenti

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Per esaminare la configurazione dei provider esistenti, digitare il comando seguente:
    
        Get-CsClsScenario -Identity <scope and scenario name> 
    
    Per visualizzare informazioni sull'operatore conferenza globale, ad esempio, digitare:
    
        Get-CsClsScenario -Identity "global/CAA"
    
    Il comando visualizza un elenco dei provider con i flag, le impostazioni e i componenti associati. Se le informazioni visualizzate non sono sufficienti o se l'elenco è troppo lungo per il formato predefinito dell'elenco di Windows PowerShell, è possibile visualizzare ulteriori informazioni definendo un metodo di output diverso. A tale scopo, digitare:
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    Nell'output di questo comando, le informazioni su ogni provider sono visualizzate su cinque righe separate che includono nome del provider, tipo di registrazione, livello di registrazione, flag, GUID e ruolo.

</div>

<div>

## <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>Per definire un nuovo provider di scenari per il servizio di registrazione centralizzato

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Un provider di scenari è costituito dal componente da tracciare, i flag da utilizzare e il livello di dettaglio per la raccolta dei dati. Per definire questi elementi, digitare:
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    La definizione di un provider di traccia per specificare quali dati raccogliere e con quale livello di dettaglio dal provider Lyss, ad esempio, è simile alla seguente:
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

Il parametro –Level consente di specificare se raccogliere i messaggi relativi a errori irreversibili, errori, avvisi e informazioni. I flag utilizzati sono tutti quelli definiti per il provider Lyss e includono la connessione TF\_, TF\_diag e il protocollo\_TF.

Dopo aver definito la variabile $LyssProvider è possibile utilizzarla con il cmdlet **New-CsClsScenario** per raccogliere le tracce dal provider Lyss. Per completare la creazione e l'assegnazione del provider a un nuovo scenario, digitare:

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

Dove $LyssProvider è la variabile che contiene lo scenario definito creato con **New-CsClsProvider**.

</div>

<div>

## <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>Per modificare un provider di scenari del servizio di registrazione centralizzato esistente

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Per aggiornare o modificare la configurazione di un provider esistente, digitare:
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    Aggiornare quindi lo scenario per assegnare il provider digitando il comando seguente:
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

Il risultato finale del comando è l'aggiornamento dei flag per lo scenario site:Redmond/RedmondLyssInfo e l'assegnazione del livello per il provider. Per visualizzare il nuovo scenario, utilizzare Get-CsClsScenario. Per informazioni dettagliate, vedere [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario).

<div class="">


> [!WARNING]  
> <STRONG>New-ClsCsProvider</STRONG> non esegue un controllo per stabilire se i flag sono validi. Assicurarsi di digitare correttamente i flag, ad esempio TF_DIAG o TF_CONNECTION. Se il nome dei flag non è corretto, il provider non potrà restituire le informazioni di log previste.



</div>

Se si desidera aggiungere ulteriori provider a questo scenario, digitare il comando seguente:

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

In cui ogni provider definito con la direttiva Add è già stato definito tramite il processo **New-CsClsProvider**.

</div>

<div>

## <a name="to-remove-a-scenario-provider"></a>Per rimuovere un provider di scenari

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  I cmdlet indicati consentono di aggiornare i provider esistenti e di crearne di nuovi. Per rimuovere un provider, è necessario utilizzare la direttiva Replace per il parametro Provider in **Set-CsClsScenario**. L'unico modo per rimuovere completamente un provider consiste nel sostituirlo con un provider ridefinito con lo stesso nome e poi utilizzare la direttiva Update. Ad esempio, il provider LyssProvider è definito con WPP come tipo di log, Level set to debug e flags set are TF\_Connection e TF\_diag. Supponendo di dover modificare i flag e impostare "All". per modificare il provider digitare il comando seguente:
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"

     &nbsp;
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}

3.  Se si desidera rimuovere completamente uno scenario e i provider associati, digitare il comando seguente:
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    Ad esempio:
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    
    <div class="">
    

    > [!WARNING]  
    > Il cmdlet <STRONG>Remove-CsClsScenario</STRONG> non richiede alcuna conferma. Lo scenario viene eliminato insieme ai provider assegnati. È possibile ricreare lo scenario rieseguendo i comandi utilizzati inizialmente per crearlo. Non esiste una procedura per il ripristino di scenari o provider rimossi.

    
    </div>

Quando si rimuove uno scenario tramite il cmdlet **Remove-CsClsScenario**, si rimuove completamente lo scenario dall'ambito. Per utilizzare gli scenari creati e i provider che facevano parte dello scenario, creare nuovi provider e assegnarli a un nuovo scenario.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario)  
[New-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/New-CsClsScenario)  
[Remove-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Remove-CsClsScenario)  
[Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario)  
[New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

