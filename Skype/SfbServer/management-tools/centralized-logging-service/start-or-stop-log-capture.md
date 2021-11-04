---
title: Avviare o arrestare l'acquisizione del registro CLS Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
description: 'Riepilogo: informazioni su come avviare o arrestare una sessione di acquisizione dei registri del servizio di registrazione centralizzata in Skype for Business Server 2015.'
ms.openlocfilehash: 051ea00f65e6bdcce563c9f4e9d3c0f634e8c09b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774612"
---
# <a name="start-or-stop-cls-log-capture-in-skype-for-business-server-2015"></a>Avviare o arrestare l'acquisizione del registro CLS Skype for Business Server 2015
 
**Riepilogo:** Informazioni su come avviare o arrestare una sessione di acquisizione dei registri del servizio di registrazione centralizzata in Skype for Business Server 2015.
  
Per acquisire i registri di traccia utilizzando il servizio di registrazione centralizzata, è necessario eseguire un comando per avviare la registrazione in uno o più computer e pool. Vengono inoltre emersi parametri che definiscono i computer o i pool, gli scenari da eseguire (ad esempio, AlwaysOn, un altro scenario predefinito o uno scenario creato), i componenti di Skype for Business Server (ad esempio, S4, SipStack) da tracciare.
  
Per acquisire le informazioni giuste è necessario assicurarsi di usare lo scenario corretto per la raccolta di informazioni pertinenti al problema. Nel servizio di registrazione centralizzata, uno scenario è il concetto di attivazione della registrazione in base a una raccolta di componenti server, livelli di registrazione e flag, che è molto più efficiente e utile rispetto alla necessità di definire questi elementi in base al server. Si definisce e specifica uno scenario da eseguire, e questo viene eseguito in modo coerente in tutti i server e i pool nell'ambito dell'infrastruttura.
  
Lo scenario predefinito è denominato **AlwaysOn**. Lo scopo di AlwaysOn, come indicato dal nome, è l'esecuzione costante dello scenario. Lo scenario AlwaysOn raccoglie informazioni a livello Info su molti dei più comuni componenti server. Tenere presente che questo livello di registrazione include, in aggiunta ai messaggi di informazioni, i messaggi di tipo Fatal, Error e Warning, ovvero relativi ad avvisi, errori ed errori irreversibili. AlwaysOn raccoglie informazioni prima, durante e dopo il verificarsi di un problema. Questo comportamento è radicalmente diverso rispetto a quello degli strumenti di registrazione precedenti, ad esempio OCSLogger. L'esecuzione di OCSLogger avveniva quando il problema si era già verificato, rendendone più difficoltosa la risoluzione poiché i dati raccolti erano di tipo reattivo e non proattivo. Se AlwaysOn non contiene le informazioni cercate per individuare il componente che causa il problema e indicare le azioni per la risoluzione (evento improbabile, data l'estensione e il livello di dettaglio dei provider in AlwaysOn), indicherà un livello di informazioni ragionevole per determinare le altre operazioni da eseguire, ad esempio creare un nuovo scenario, raccogliere altre informazioni, eseguire una ricerca diversa per raccogliere dettagli più specifici e così via.
  
Il servizio di registrazione centralizzata offre due modi per emettere comandi. Diversi argomenti sono stati incentrati sull'utilizzo di Windows PowerShell tramite Skype for Business Server Management Shell. La possibilità di utilizzare una serie di configurazioni e comandi complessi favorisce Windows PowerShell per l'utilizzo del servizio di registrazione centralizzata. Poiché Windows PowerShell tramite Skype for Business Server Management Shell è quasi onnipresente per tutte le funzioni in Skype for Business Server, vengono illustrati solo i Windows PowerShell comandi. 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>Per eseguire Start-CsClsLogging con Windows PowerShell comandi di base

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell.**
    
2. Avviare uno scenario di registrazione con il servizio di registrazione centralizzato digitando quanto segue:
    
   ```PowerShell
   Start-CsClsLogging -Scenario <name of scenario>
   ```

    Ad esempio, per avviare lo scenario **AlwaysOn** digitare:
    
   ```PowerShell
   Start-CsClsLogging -Scenario AlwaysOn
   ```

    > [!NOTE]
    > Lo scenario AlwaysOn non ha una durata predefinita. Verrà eseguito finché non lo si interrompe esplicitamente con il cmdlet **Stop-CsClsLogging**. Per informazioni dettagliate, vedere [Stop-CsClsLogging](/powershell/module/skype/stop-csclslogging?view=skype-ps). Per tutti gli altri scenari, la durata predefinita è 4 ore. 
  
3. Premere INVIO per eseguire il comando. 
    
    > [!NOTE]
    > Per l'esecuzione dei comandi e la comunicazione dello stato dai computer della distribuzione possono essere necessari da 30 a 60 secondi. 
  
     ![Esecuzione di Start-CsClsLogging.](../../media/Ops_CLS_Show_and_Start_ClsLogging.jpg)
  
4. Per avviare un altro scenario, usare il cmdlet **Start-CsClsLogging** con il nome dello scenario aggiuntivo da eseguire (ad esempio lo scenario **Authentication**) come segue:
    
   ```PowerShell
   Start-CsClsLogging -Scenario Authentication
   ```

    > [!IMPORTANT]
    > È possibile eseguire un totale di due scenari su qualsiasi computer in qualsiasi momento. Se l'ambito del comando è globale, lo o gli scenari verranno eseguiti da tutti i computer della distribuzione. Per avviare un terzo scenario è necessario interrompere la registrazione nel computer, pool, sito o ambito globale in cui si vuole eseguire il nuovo scenario. Se è stato avviato un ambito globale, è possibile interrompere la registrazione per uno o per entrambi gli scenari in uno o più computer e pool. 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>Per eseguire Start-CsClsLogging con Windows PowerShell comandi avanzati

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell.**
    
2. Sono disponibili ulteriori parametri per la gestione dei comandi di registrazione. È possibile utilizzare -Duration per modificare il periodo di tempo per l'esecuzione dello scenario. È inoltre possibile definire -Computers, un elenco di nomi di dominio completi (FQDN) dei computer separati da una virgola oppure -Pools, un elenco separato da virgole di FQDN per i pool su cui si desidera eseguire l'accesso.
    
    Si avvia una sessione di registrazione per lo scenario UserReplicator nel pool "pool01.contoso.net". La durata della sessione di registrazione deve essere di 8 ore. A questo scopo, digitare:
    
   ```PowerShell
   Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
   ```

    L'esecuzione corretta dello scenario restituisce un risultato simile al seguente:
    
     ![Esecuzione di Start-CsClsLogging.](../../media/Ops_CsClsLogging_UserReplicator_Exp.jpg)
  
Si noti che in questo esempio gli scenari AlwaysOn e UserReplicator sono entrambi in esecuzione. 
    
## <a name="stop-the-centralized-logging-service-log-capture"></a>Arrestare l'acquisizione del registro del servizio di registrazione centralizzato
<a name="stop"> </a>

Il cmdlet Stop-CsClsLogging consente di interrompere una sessione di registrazione in esecuzione. In genere, non esistono molte situazioni in cui è necessario arrestare una sessione di registrazione. Ad esempio, è possibile eseguire ricerche nei log e modificare configurazioni senza bisogno di interrompere la registrazione. Se sono in esecuzione due scenari, ad esempio AlwaysOn e UserReplicator, ed è necessario raccogliere informazioni relative all'autenticazione, per poter avviare lo scenario Authentication sarà necessario interrompere uno dei due scenari, a livello globale, di pool o di sito. Per informazioni dettagliate, vedere [Stop-CsClsLogging](/powershell/module/skype/stop-csclslogging?view=skype-ps).
  
> [!NOTE]
> Quando si determinano gli scenari che è possibile eseguire in una determinata distribuzione, pool o computer, è necessario ricordare che si è limitati all'esecuzione di due scenari **per computer:** AlwaysOn e uno scenario personalizzato. Se si stanno registrando le attività in un pool, è consigliabile trattare il pool come una singola entità. Nella maggior parte dei casi l'esecuzione di scenari diversi in ogni computer di un pool non ha senso. È invece opportuno esaminare il problema su cui si stanno raccogliendo dati e stabilire quale scenario abbia più senso in un determinato computer nella distribuzione complessiva. Ad esempio, se si considera lo scenario UserReplicator, l'esecuzione di UserReplicator in un server perimetrale o in un pool di server perimetrali non avrebbe molto valore. 
  
Una volta compresi il problema e l'ambito dell'impatto, andranno effettuate scelte attente sugli scenari da eseguire e sui computer e pool ai quali applicarli. Mentre lo scenario AlwaysOn è adatto all'applicazione su vasta scala, in quanto raccoglie informazioni su un'ampia gamma di provider, gli scenari specifici risultano utili solo se applicati a specifici computer o pool. È inoltre necessaria attenzione quando si avvia una sessione di registrazione scelta a caso senza prima comprendere il valore di un dato scenario. Se si utilizza lo scenario sbagliato, oppure si sceglie uno scenario appropriato per l'attività, ma lo si applica all'ambito sbagliato (a livello globale, di sito, di pool o di computer), si possono ottenere dati dubbi e non molto utili, come se non si fosse eseguito affatto lo scenario.
  
Per controllare le funzioni del servizio di registrazione centralizzata utilizzando Skype for Business Server Management Shell, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator basati sui ruoli o un ruolo RBAC personalizzato contenente uno di questi due gruppi. Per restituire un elenco di tutti i ruoli RBAC a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati dall'utente), eseguire il comando seguente da Skype for Business Server Management Shell o dal prompt di Windows PowerShell:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Ad esempio:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Potrebbe quindi chiedersi: Ora che è stata abilitata la registrazione, dove vengono conservati i log? Poiché è possibile accedere alle informazioni archiviate nei registri utilizzando le query della shell di gestione inviate agli agenti CLS ed è possibile inviare i risultati in diversi formati di file possibili, in cui in ogni server un agente CLS mantiene i propri record non è effettivamente importante sapere.  I file di registro possono essere salvati in un percorso specificato e letti e analizzati utilizzando diversi strumenti, tra cuiSnooper.exee qualsiasi strumento **in** grado di leggere un file di testo, ad esempio **Notepad.exe**. Snooper.exe fa parte degli strumenti di debug Skype for Business Server 2015 ed è disponibile come [download Web.](https://go.microsoft.com/fwlink/p/?LinkId=285257)

### <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>Per arrestare una sessione del servizio di registrazione centralizzata attualmente in esecuzione

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell.**
    
2. Eseguire una query sul servizio di registrazione centralizzata per individuare gli scenari attualmente in esecuzione digitando quanto segue:
    
   ```PowerShell
   Show-CsClsLogging
   ```

   ![Windows PowerShell console dopo aver chiamato Show-CsCl.](../../media/Ops_Show_Stop_CsClsLogging.jpg)
  
   Il risultato di Show-CsClsLogging è un riepilogo degli scenari in esecuzione e dei relativi ambiti di esecuzione. Per informazioni dettagliate, vedere [Show-CsClsLogging](/powershell/module/skype/show-csclslogging?view=skype-ps).
    
3. Per interrompere una sessione di registrazione in esecuzione con uno scenario specifico, digitare:
    
   ```PowerShell
   Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
   ```
   Ad esempio:
    
   ```PowerShell
   Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
   ```

   Questo comando interromperà la registrazione con lo scenario UserReplicatior in pool01.contoso.net.
    
    > [!NOTE]
    > I log creati nel corso di questa sessione di registrazione utilizzando lo scenario UserReplicator non vengono eliminati. La registrazione resta disponibile per l'esecuzione di ricerche mediante il comando Search-CsClsLogging. Per informazioni dettagliate, vedere [Search-CsClsLogging](/powershell/module/skype/search-csclslogging?view=skype-ps). 
  
Il cmdlet Stop-CsClsLogging funge da comando complementare a Start-CsClsLogging e interrompe la sessione di registrazione, definita dagli scenari, conservando i log creati. È possibile eseguire un totale di due scenari su un dato computer in qualsiasi momento. L'interruzione di uno scenario per raccogliere informazioni utilizzando uno scenario diverso è un'attività comune, utile nella maggior parte delle procedure di risoluzione dei problemi relativi ai carichi di lavoro.
## <a name="see-also"></a>Vedere anche
<a name="stop"> </a>

[Servizio di registrazione centralizzato in Skype for Business 2015](centralized-logging-service.md)