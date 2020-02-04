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
ms.openlocfilehash: 2428bd11e656d0f1b6295e63ca6106fa7edcbb15
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734855"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-providers-for-centralized-logging-service-in-lync-server-2013"></a>Configurazione dei provider per il servizio di registrazione centralizzato in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-03-19_

I concetti e la configurazione dei *provider* in un servizio di registrazione centralizzato è uno dei più importanti da afferrare. I *provider* sono mappati direttamente ai componenti del ruolo di Lync Server Server nel modello di traccia di Lync Server. Il provider definisce i componenti di un Lync Server 2013 che verranno analizzati, il tipo di messaggi (ad esempio, fatale, Error o Warning) da raccogliere e i contrassegni (ad esempio, TF\_Connection o TF\_diag). I provider sono i componenti rintracciabili in ogni ruolo di server Lync Server. Usando i provider, Definisci il livello e il tipo di traccia sui componenti (ad esempio, S4, SIPStack, IM e Presence). Il provider definito viene usato in uno scenario per raggruppare tutti i provider per una determinata raccolta logica che affrontano una specifica condizione di problema.

Per eseguire le funzioni del servizio di registrazione centralizzato tramite Lync Server Management Shell, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contiene una delle opzioni questi due gruppi. Per restituire un elenco di tutti i ruoli di controllo di accesso basati sul ruolo a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati manualmente), eseguire il comando seguente da Lync Server Management Shell o dal prompt di Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Ad esempio:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

Il resto di questo argomento illustra come definire i provider, modificare un provider e il contenuto di una definizione di provider per ottimizzare la risoluzione dei problemi. Esistono due modi per emettere comandi di servizio di registrazione centralizzati. Per impostazione predefinita, è possibile usare CLSController. exe nella directory C\\: programmi\\comuni di\\Microsoft Lync Server 2013\\CLSAgent. In alternativa, puoi usare Lync Server Management Shell per emettere comandi di Windows PowerShell. La distinzione importante è che quando si usa CLSController. exe alla riga di comando è disponibile una selezione limitata di scenari in cui i provider sono già definiti e non sono modificabili, ma è possibile definire il livello di log. Usando Windows PowerShell puoi definire nuovi provider da usare nelle sessioni di registrazione e avere il controllo completo sulla creazione, su cosa raccolgono e su quale livello raccolgono i dati.

<div class="">


> [!IMPORTANT]  
> Come accennato, i provider sono molto potenti. Tuttavia, gli scenari sono più potenti perché contengono l'incorporamento di tutte le informazioni necessarie per impostare ed eseguire la traccia sui componenti rappresentati dai provider. Con gli scenari che sono una raccolta di provider, questa operazione potrebbe essere confrontata con l'esecuzione di un file batch contenente centinaia di comandi per raccogliere molte informazioni rispetto al rilascio di centinaia di comandi, uno alla volta, nella riga di comando.<BR>Invece di richiedere di approfondire i dettagli dei provider, il servizio di registrazione centralizzato offre numerosi scenari già definiti per l'utente. Gli scenari forniti coprono la stragrande maggioranza dei possibili problemi che incontrerai. In rari casi potrebbe essere necessario creare e definire provider e assegnarli agli scenari. Ti consigliamo vivamente di acquisire familiarità con ognuno degli scenari forniti prima di esaminare la necessità di creare nuovi provider e scenari. Mentre le informazioni sulla creazione di provider si trovano qui per familiarizzare con il modo in cui gli scenari usano gli elementi del provider per raccogliere informazioni di traccia, in questo momento non vengono forniti dettagli sui provider stessi.



</div>

Introdotti in [Panoramica del servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), gli elementi chiave della definizione di un provider per l'uso in uno scenario sono i seguenti:

  - **Providers**   se si ha familiarità con OCSLogger, i provider sono i componenti scelti per indicare a OCSLogger da quale motore di analisi deve raccogliere i log. I provider sono gli stessi componenti e in molti casi hanno lo stesso nome dei componenti in OCSLogger. Se non si ha familiarità con OCSLogger, i provider sono componenti specifici del ruolo del server a cui il servizio di registrazione centralizzata può raccogliere i log. Nel caso del servizio di registrazione centralizzato, CLSAgent è la parte dell'architettura del servizio di registrazione centralizzata che sta eseguendo la traccia dei componenti definiti nella configurazione di provider.

  - **Livelli di registrazione**   OCSLogger fornito l'opzione per scegliere un numero di livelli di dettaglio per i dati raccolti. Questa caratteristica è parte integrante del servizio di registrazione centralizzato e degli scenari e viene definita dal parametro **Type** . È possibile scegliere una delle opzioni seguenti:
    
      - **Tutti**   raccoglie i messaggi di traccia di tipo Fatal, Error, Warning e info nel log per il provider definito.
    
      - **Fatal**   raccoglie solo i messaggi di traccia che indicano un errore per il provider definito.
    
      - **Errore**   raccoglie solo i messaggi di traccia che indicano un errore per il provider definito, oltre a messaggi irreversibili.
    
      - **Avviso**   raccoglie solo i messaggi di traccia che indicano un avviso per il provider definito, oltre a messaggi fatali e di errore.
    
      - **Informazioni**   raccoglie solo i messaggi di traccia che indicano un messaggio informativo per il provider definito, oltre a messaggi fatali, di errore e di avviso.
    
      - **Verbose**   raccoglie tutti i messaggi di traccia di tipo Fatal, Error, Warning e info per il provider definito.

  - **Flags**   OCSLogger ha fornito l'opzione per scegliere contrassegni per ogni provider che ha definito il tipo di informazioni che è possibile recuperare dai file di traccia. È possibile scegliere i contrassegni seguenti in base al provider:
    
      - **La\_connessione**   TF include voci di log correlate alla connessione. Questi registri includono informazioni sulle connessioni stabilite da e verso un particolare componente. Può anche includere informazioni significative a livello di rete, ovvero per i componenti senza il concetto di connessione.
    
      - **TF\_Security**   offre tutti gli eventi/voci di log correlate alla sicurezza. Ad esempio, per SipStack, si tratta di eventi di sicurezza come l'errore di convalida del dominio e gli errori di autenticazione client/autorizzazione.
    
      - **TF\_diag**   offre eventi di diagnostica che è possibile usare per diagnosticare o risolvere i problemi del componente. Ad esempio, per SipStack, si tratta di errori di certificato o di avvisi e messaggi DNS.
    
      - **Il\_protocollo**   TF fornisce messaggi di protocollo, ad esempio messaggi SIP e combinati di codec community.
    
      - **Il\_componente**   TF Abilita la registrazione dei componenti specificati come parte dei provider.
    
      - **Tutto**   imposta tutti i contrassegni disponibili per il provider.

<div>

## <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>Per esaminare le informazioni sui provider di scenari di servizi di registrazione centralizzati esistenti

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Per esaminare la configurazione dei provider esistenti, digitare quanto segue:
    
        Get-CsClsScenario -Identity <scope and scenario name> 
    
    Ad esempio, per esaminare le informazioni sull'operatore di conferenza globale, digitare:
    
        Get-CsClsScenario -Identity "global/CAA"
    
    Il comando Visualizza un elenco di provider con i contrassegni, le impostazioni e i componenti associati. Se le informazioni visualizzate non sono sufficienti o l'elenco è troppo lungo per il formato predefinito dell'elenco di Windows PowerShell, è possibile visualizzare altre informazioni definendo un metodo di output diverso. A tale scopo, digitare:
    
        Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
    
    L'output di questo comando Visualizza ogni provider visualizzato in un formato a cinque righe con il nome del provider, il tipo di registrazione, il livello di registrazione, i contrassegni, il GUID e il ruolo, ognuno in una riga distinta.

</div>

<div>

## <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>Per definire un nuovo provider di scenari del servizio di registrazione centralizzato

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Un provider di scenari è costituito da un componente da tracciare, da contrassegni da usare e da un livello di dettaglio da raccogliere. Per eseguire questa operazione, digitare:
    
        $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
    
    Ad esempio, la definizione di un provider di traccia che definisce cosa raccogliere e il livello di dettaglio del provider Lyss ha l'aspetto seguente:
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"

La raccolta-livello raccoglie messaggi fatali, di errore, di avviso e di informazioni. I contrassegni usati sono tutti quelli definiti per il provider Lyss e includono la connessione\_TF, TF\_diag e TF\_Protocol.

Dopo aver definito la variabile $LyssProvider, è possibile usarla con il cmdlet **New-CsClsScenario** per raccogliere le tracce dal provider Lyss. Per completare la creazione e l'assegnazione del provider in un nuovo scenario, digitare:

    New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

Dove $LyssProvider è la variabile che contiene lo scenario definito creato con **New-CsClsProvider**.

</div>

<div>

## <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>Per modificare un provider di scenario del servizio di registrazione centralizzato esistente

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Per aggiornare o modificare la configurazione di un provider esistente, digitare:
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
    
    È quindi possibile aggiornare lo scenario per assegnare il provider digitando quanto segue:
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider

Il risultato finale del comando è che il sito scenario: Redmond/RedmondLyssInfo avrà aggiornato i contrassegni e il livello per il provider assegnato. Puoi visualizzare il nuovo scenario usando Get-CsClsScenario. Per informazioni dettagliate, vedere [Get-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario).

<div class="">


> [!WARNING]  
> <STRONG>New-ClsCsProvider</STRONG> non controlla per determinare se i contrassegni sono validi. Verificare che l'ortografia dei contrassegni (ad esempio TF_DIAG o TF_CONNECTION) sia stata digitata correttamente. Se i contrassegni non vengono digitati correttamente, il provider non potrà restituire le informazioni di log previste.



</div>

Se si vogliono aggiungere altri provider a questo scenario, digitare quanto segue:

    Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}

Dove ogni provider definito con la direttiva add è già stato definito tramite il processo **New-CsClsProvider** .

</div>

<div>

## <a name="to-remove-a-scenario-provider"></a>Per rimuovere un provider di scenari

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  I cmdlet forniti consentono di aggiornare i provider esistenti e di creare nuovi provider. Per rimuovere un provider, è necessario usare la direttiva Replace per il parametro provider per **impostare-CsClsScenario**. L'unico modo per rimuovere completamente un provider è sostituirlo con un provider ridefinito con lo stesso nome e usare la direttiva Update. Ad esempio, il nostro provider LyssProvider è definito con WPP come tipo di log, Level set to debug e set di contrassegni\_sono connessione TF\_e TF diag. È necessario modificare i contrassegni in "tutti". Per cambiare il provider, digitare quanto segue:
    
        $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"

     &nbsp;
    
        Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}

3.  Se si vuole rimuovere completamente uno scenario e i provider a esso associati, digitare quanto segue:
    
        Remove-CsClsScenario -Identity <scope and name of scenario>
    
    Ad esempio:
    
        Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
    
    <div class="">
    

    > [!WARNING]  
    > Il cmdlet <STRONG>Remove-CsClsScenario</STRONG> non chiede conferma. Lo scenario viene eliminato, insieme ai provider assegnati. Puoi ricreare lo scenario eseguendo nuovamente i comandi usati per crearlo inizialmente. Non esiste una procedura per recuperare gli scenari o i provider rimossi.

    
    </div>

Quando si rimuove uno scenario usando il cmdlet **Remove-CsClsScenario** , si rimuove completamente lo scenario dall'ambito. Per usare gli scenari creati e i provider che facevano parte dello scenario, è possibile creare nuovi provider e assegnarli a un nuovo scenario.

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

