---
title: Avviare o arrestare l'acquisizione dei log CSL in Skype for Business 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
description: 'Riepilogo: informazioni su come avviare o arrestare una sessione di acquisizione del log del servizio di registrazione centralizzata in Skype for Business Server 2015.'
ms.openlocfilehash: 4d8c40c2fdb648497997fbd4a69dc49af4685b43
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816565"
---
# <a name="start-or-stop-cls-log-capture-in-skype-for-business-server-2015"></a>Avviare o arrestare l'acquisizione dei log CSL in Skype for Business 2015
 
**Riepilogo:** Informazioni su come avviare o arrestare una sessione di acquisizione del log del servizio di registrazione centralizzata in Skype for Business Server 2015.
  
Per acquisire i registri di traccia usando il servizio di registrazione centralizzato, viene emesso un comando per iniziare la registrazione in uno o più computer e pool. Puoi anche emettere parametri che definiscono i computer o i pool, quali scenari eseguire, ad esempio AlwaysOn, un altro scenario predefinito o uno scenario che hai creato, i componenti di Skype for Business Server (ad esempio, S4, SipStack) da rintracciare.
  
Per acquisire le informazioni appropriate, è necessario assicurarsi di usare lo scenario giusto per raccogliere informazioni rilevanti per il problema. Nel servizio di registrazione centralizzato, uno scenario è il concetto di attivazione della registrazione basato su una raccolta di componenti server, livelli di registrazione e contrassegni, che è molto più efficiente e utile che definire questi elementi in base al server. Puoi definire e specificare uno scenario da eseguire e lo scenario viene eseguito in modo coerente in tutti i server e i pool nell'ambito dell'infrastruttura.
  
Lo scenario predefinito è denominato **AlwaysOn**. Lo scopo previsto per AlwaysOn è l'esecuzione costante dello scenario, come implica il nome dello scenario. Lo scenario AlwaysOn raccoglie informazioni a livello di informazioni (si noti che il livello di registrazione info include fatale, Error e Warning oltre ai messaggi info) per molti dei componenti server più comuni. AlwaysOn raccoglie le informazioni prima, durante e dopo che si verifica un problema. Ciò si differenzia in modo significativo dal comportamento tipico degli strumenti di registrazione precedenti, ad esempio OCSLogger. Hai eseguito OCSLogger dopo che il problema era già avvenuto, rendendo più difficile la risoluzione dei problemi perché i dati che hai sono reattivi e non proattivi. Se AlwaysOn non contiene le informazioni che si stanno cercando per fare riferimento al componente problema e indicare una linea di azione per risolverlo (che non è probabilmente dato l'ampiezza e la profondità dei provider in AlwaysOn), indicherà un livello di informazioni ragionevole conferma per determinare altre informazioni utili, ad esempio la creazione di un nuovo scenario, la raccolta di altri dati, l'esecuzione di una ricerca diversa per raccogliere dettagli più mirati e così via.
  
Il servizio di registrazione centralizzato offre due modi per emettere comandi. Un certo numero di argomenti è stato focalizzato sull'uso di Windows PowerShell tramite Skype for Business Server Management Shell. La possibilità di usare una serie di configurazioni e comandi complessi favorisce Windows PowerShell per l'uso del servizio di registrazione centralizzato. Dato che Windows PowerShell tramite Skype for Business Server Management Shell è quasi onnipresente per tutte le funzioni in Skype for Business Server, vengono discussi solo i comandi di Windows PowerShell. 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>Per eseguire Start-CsClsLogging con Windows PowerShell usando i comandi di base

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
2. Avviare uno scenario di registrazione con il servizio di registrazione centralizzato digitando quanto segue:
    
   ```PowerShell
   Start-CsClsLogging -Scenario <name of scenario>
   ```

    Ad esempio, per avviare lo scenario **AlwaysOn** , digitare:
    
   ```PowerShell
   Start-CsClsLogging -Scenario AlwaysOn
   ```

    > [!NOTE]
    > Lo scenario AlwaysOn non ha durata predefinita. Questo scenario verrà eseguito fino a quando non lo Interrompi esplicitamente con il cmdlet **Stop-CsClsLogging** . Per informazioni dettagliate, vedere [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps). Per tutti gli altri scenari, la durata predefinita è di 4 ore. 
  
3. Premere INVIO per eseguire il comando. 
    
    > [!NOTE]
    > Potrebbe essere necessario un breve lasso di tempo (da 30 a 60 secondi) per i comandi da eseguire e per ricevere lo stato di nuovo dai computer della distribuzione. 
  
     ![Esecuzione di Start-CsClsLogging.](../../media/Ops_CLS_Show_and_Start_ClsLogging.jpg)
  
4. Per avviare un altro scenario, usare il cmdlet **Start-CsClsLogging** con il nome dello scenario aggiuntivo da eseguire come indicato di seguito, ad esempio l' **autenticazione**dello scenario:
    
   ```PowerShell
   Start-CsClsLogging -Scenario Authentication
   ```

    > [!IMPORTANT]
    > È possibile avere un totale di due scenari in esecuzione in qualsiasi computer specifico in qualsiasi momento. Se il comando è globale nell'ambito, tutti i computer della distribuzione eseguiranno lo scenario o gli scenari. Per avviare un terzo scenario, è necessario interrompere la registrazione nel computer, nel pool, nel sito o nell'ambito globale in cui si vuole eseguire il nuovo scenario. Se è stato avviato un ambito globale, è possibile interrompere la registrazione per uno o entrambi gli scenari in uno o più computer e pool. 
  
### <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>Per eseguire Start-CsClsLogging con Windows PowerShell tramite comandi avanzati

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
2. Sono disponibili parametri aggiuntivi per gestire i comandi di registrazione. È possibile usare la durata per regolare il periodo di tempo per l'esecuzione dello scenario. È anche possibile definire-computer, un elenco di nomi di dominio completi di computer (FQDN) separati da una virgola o da-pools, un elenco delimitato da virgole di FQDN per i pool di cui si vuole eseguire l'accesso.
    
    Si avvia una sessione di registrazione per lo scenario UserReplicator nel pool "pool01.contoso.net". Puoi anche definire la durata della sessione di registrazione a 8 ore. A tale scopo, digitare:
    
   ```PowerShell
   Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
   ```

    L'esecuzione corretta di questo scenario restituisce un risultato simile al seguente:
    
     ![Esecuzione di Start-CsClsLogging.](../../media/Ops_CsClsLogging_UserReplicator_Exp.jpg)
  
Tieni presente che in questo esempio viene eseguito lo scenario AlwaysOn e lo scenario UserReplicator è in corso. 
    
## <a name="stop-the-centralized-logging-service-log-capture"></a>Arrestare l'acquisizione del log del servizio di registrazione centralizzata
<a name="stop"> </a>

È possibile interrompere una sessione di registrazione corrente con il cmdlet Stop-CsClsLogging. In genere, non ci sono molte situazioni in cui è necessario interrompere una sessione di registrazione. Ad esempio, è possibile cercare registri e modificare le configurazioni senza prima di tutto necessario interrompere la registrazione. Se sono in uso due scenari, ad esempio AlwaysOn e UserReplicator, ed è necessario raccogliere informazioni correlate all'autenticazione, è necessario interrompere uno degli altri scenari (in un ambito globale, di un sito, di un pool o un computer) prima di iniziare a eseguire Scenario di autenticazione. Per informazioni dettagliate, vedere [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/stop-csclslogging?view=skype-ps).
  
> [!NOTE]
> Per determinare gli scenari che è possibile eseguire in una distribuzione, un pool o un computer specifico, è necessario tenere presente che si è limitati a eseguire due scenari **per computer**: AlwaysOn e uno scenario personalizzato. Se si esegue la registrazione di attività in un pool, è consigliabile trattare un pool come singola entità. Nella maggior parte dei casi, non avrebbe senso eseguire scenari diversi in ogni computer in un pool. È consigliabile esaminare il problema di cui si stanno raccogliendo i dati e pensare allo scenario più appropriato in un dato computer nella distribuzione complessiva. Se, ad esempio, consideriamo lo scenario UserReplicator, il valore dell'uso di UserReplicator in un server perimetrale o in un pool di Edge sarà molto scarso. 
  
Dopo aver compreso il problema e l'ambito dell'impatto, è consigliabile scegliere quali scenari eseguire in quali computer e pool. Anche se lo scenario AlwaysOn ha un significato per un'applicazione di ambito esteso, poiché raccoglie informazioni su un'ampia gamma di provider, gli scenari specifici hanno solo valore dell'applicazione in computer o pool specifici. È inoltre necessario prestare attenzione quando si avvia una sessione di registrazione in modo casuale senza prima capire il valore di uno scenario specifico. Se si usa lo scenario errato oppure se si usa uno scenario appropriato per l'attività e si applica lo scenario nell'ambito errato (globale, sito, pool o computer), è possibile ottenere dati discutibili che non sono molto utili, come se non fosse stato eseguito affatto lo scenario.
  
Per controllare le funzioni del servizio di registrazione centralizzato usando Skype for Business Server Management Shell, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contiene uno di questi due gruppi. Per restituire un elenco di tutti i ruoli RBAC a cui è stato assegnato questo cmdlet (inclusi eventuali ruoli RBAC personalizzati creati manualmente), eseguire il comando seguente da Skype for Business Server Management Shell o dal prompt di Windows PowerShell:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

Ad esempio:
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

> [!NOTE]
> Quindi potresti chiederti: ora che hai abilitato la registrazione, dove sono conservati i log? Dato che si accede alle informazioni archiviate nei registri tramite le query di Management Shell inviate agli agenti CLS ed è possibile eseguire l'output dei risultati in diversi formati di file, in cui in ogni server un agente CLS mantiene i propri record non è effettivamente importante saperlo.  I file di log possono essere salvati in una posizione specificata e letta e analizzata usando una varietà di strumenti, tra cui **Snooper. exe** e qualsiasi strumento in grado di leggere un file di testo, ad esempio **notepad. exe**. Snooper. exe fa parte degli strumenti di debug di Skype for Business Server 2015 ed è disponibile come [download Web](https://go.microsoft.com/fwlink/p/?LinkId=285257).

### <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>Per interrompere una sessione di servizio di registrazione centralizzata attualmente in uso

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
2. Eseguire una query sul servizio di registrazione centralizzata per individuare gli scenari in esecuzione digitando quanto segue:
    
   ```PowerShell
   Show-CsClsLogging
   ```

   ![Console di Windows PowerShell dopo la chiamata a Show-CsCl](../../media/Ops_Show_Stop_CsClsLogging.jpg)
  
   Il risultato di Show-CsClsLogging è un riepilogo degli scenari in uso e l'ambito in cui sono in uso. Per informazioni dettagliate, vedere [Mostra-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/show-csclslogging?view=skype-ps).
    
3. Per interrompere una sessione di registrazione attualmente in uso con uno scenario specifico, digitare:
    
   ```PowerShell
   Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
   ```
   Ad esempio:
    
   ```PowerShell
   Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
   ```

   Questo comando interrompe la registrazione con lo scenario UserReplicatior in pool01.contoso.net.
    
    > [!NOTE]
    > I log creati durante questa sessione di registrazione usando lo scenario UserReplicator non vengono eliminati. La registrazione è ancora disponibile per l'esecuzione delle ricerche sull'uso del comando Cerca-CsClsLogging. Per informazioni dettagliate, vedere [Ricerca-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/search-csclslogging?view=skype-ps). 
  
Agendo come comando complementare per Start-CsClsLogging, il cmdlet Stop-CsClsLogging termina la sessione di registrazione, definita da scenari, e mantiene i registri creati dalla sessione di registrazione. È possibile eseguire due scenari in un computer specifico in qualsiasi momento. Il metodo di interruzione di uno scenario per raccogliere informazioni con un altro scenario è un'attività comune che è possibile eseguire durante la maggior parte dei problemi di lavoro.
## <a name="see-also"></a>Vedere anche
<a name="stop"> </a>

[Servizio di registrazione centralizzato in Skype for Business 2015](centralized-logging-service.md)
