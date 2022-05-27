---
title: Monitorare Cloud Connector mediante Operations Management Suite (OMS)
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: Leggere questo argomento per informazioni su come monitorare la distribuzione di Cloud Connector versione 2.1 e successiva usando Microsoft Operations Management Suite (OMS).
ms.openlocfilehash: c10eac34e065ab76cb570a21752838c308b6afd8
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676508"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>Monitorare Cloud Connector mediante Operations Management Suite (OMS)

> [!Important]
> Cloud Connector Edition ritirerà il 31 luglio 2021 insieme a Skype for Business Online. Dopo l'aggiornamento dell'organizzazione a Teams, informazioni su come connettere la rete telefonica locale a Teams tramite [routing diretto](/MicrosoftTeams/direct-routing-landing-page).

Leggere questo argomento per informazioni su come monitorare la distribuzione di Cloud Connector versione 2.1 e successiva usando Microsoft Operations Management Suite (OMS).

È ora possibile monitorare la distribuzione di Cloud Connector versione 2.1 e successiva usando Operations Management Suite (OMS), una soluzione di gestione IT cloud Microsoft. Oms Log Analytics consente di monitorare e analizzare la disponibilità e le prestazioni delle risorse, incluse le macchine fisiche e virtuali. Per altre informazioni su OMS e Log Analytics, vedere [Che cos'è Operations Management Suite (OMS)?](/azure/operations-management-suite/operations-management-suite-overview)

In questa sezione sono contenute le seguenti sezioni:

- Prerequisiti

- Configurare Cloud Connector per l'uso di OMS

- Configurare OMS

- Analizzare gli avvisi nel repository di Log Analytics

- Set di monitoraggio consigliato

## <a name="prerequisites"></a>Prerequisiti

Prima di poter usare OMS per monitorare la distribuzione di Cloud Connector, è necessario quanto segue:

- **Un account Azure e un'area di lavoro OMS.** Se non si dispone già di un account Azure, è necessario crearne uno per usare Log Analytics di OMS. Per informazioni su come creare un account Azure e configurare un'area di lavoro OMS, vedere [Attività iniziali con un'area di lavoro Log Analytics](/azure/log-analytics/log-analytics-get-started).

- **Cloud Connector versione 2.1 o successiva**

- **È necessaria una nuova ricerca log di Log Analytics** per il monitoraggio del connettore cloud. Per altre informazioni, vedere [Aggiornare l'area di lavoro di Azure Log Analytics a una nuova ricerca log](/azure/log-analytics/log-analytics-log-search-upgrade).

## <a name="configure-cloud-connector-to-use-oms"></a>Configurare Cloud Connector per l'uso di OMS

È necessario configurare l'ambiente locale di Cloud Connector per l'uso di OMS. A tale scopo, sono necessari l'ID e la chiave dell'area di lavoro OMS, che è possibile trovare usando il portale di OMS come segue: Impostazioni --\>Origini connesse --\> Windows Server:

![Screenshot per Cloud Connector OMS.](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

La configurazione di Cloud Connector per l'uso di OMS dipende dal proprio scenario:

- **Se si installa una nuova appliance Cloud Connector o si vuole ridistribuirla**, seguire questa procedura prima di eseguire Install-CcAppliance:

  1. Nella sezione CloudConnector.ini file [Common] impostare il parametro OMSEnabled su True.

     Ogni volta che Cloud Connector viene distribuito o aggiornato, tenterà di installare automaticamente l'agente OMS nelle macchine virtuali. Abilitare questa funzionalità in modo che l'agente OMS possa sopravvivere all'aggiornamento automatico di Cloud Connector.

  2. Per configurare l'ID e la chiave OMS, eseguire Set-CcCredential -AccountType OMSWorkspace.

- **Se si installa un agente OMS in un'appliance Cloud Connector esistente**, seguire questa procedura:

  1. Nella sezione CloudConnector.ini file [Common] impostare OMSEnabled=true.

  2. Eseguire Import-CcConfiguration.

  3. Eseguire Install-CcOMSAgent.

     > [!NOTE]
     > Se le credenziali di OMSWorkspace non sono mai state impostate, vengono richieste le credenziali quando si esegue install-CcOMSAgent.

- **Se si vuole aggiornare l'ID o la chiave dell'area di lavoro OMS in un'appliance Cloud Connector che ha già installato un agente OMS:**

  1. Per configurare l'ID e la chiave OMS, eseguire Set-CcCredential -AccountType OMSWorkspace.

  2. Per applicare gli aggiornamenti, eseguire Install-CcOMSAgent.

- **Per tutti gli scenari, verificare che gli agenti siano connessi come indicato di seguito:**

    Nel portale di OMS passare a Impostazioni -\> Origini connesse -\> server Windows. Verrà visualizzato un elenco di computer connessi.

## <a name="configure-oms"></a>Configurare OMS

Successivamente, sarà necessario specificare la configurazione di OMS usando il portale di OMS. In particolare, sarà necessario:

- Specificare informazioni sui log eventi e sui contatori delle prestazioni.

- Creazione avvisi

### <a name="specify-information-about-event-logs-and-performance-counters"></a>Specificare informazioni sui log eventi e sui contatori delle prestazioni

Nel portale di OMS è necessario specificare le informazioni sui log eventi e sui contatori delle prestazioni come indicato di seguito:

1. Passare a Impostazioni-Data-Windows\>\> Registri eventi e aggiungere i log eventi per:

   - Lync Server

   - Applicazione

     > [!NOTE]
     > È necessario immettere manualmente Lync Server nella casella di testo. Non viene visualizzata come opzione nell'elenco a discesa.

     Per altre informazioni, vedere [Windows origini dati del log eventi in Log Analytics](/azure/log-analytics/log-analytics-data-sources-windows-events)

2. Passare a Impostazioni-Data\>-\> contatori delle prestazioni Windows e aggiungere contatori delle prestazioni per:

   - **Contatori a livello di sistema operativo**. È possibile aggiungere contatori a livello di sistema operativo, ad esempio l'utilizzo del processore, l'utilizzo della memoria, l'utilizzo della rete oppure è possibile usare soluzioni esistenti come Capacità e prestazioni, Rete Monitor prestazioni senza aggiungere contatori in modo esplicito. Indipendentemente dal modo in cui si decide di monitorarli, Microsoft consiglia di monitorare questi contatori del sistema operativo.

   - **Skype for Business contatori**. Sono disponibili numerosi contatori forniti da Skype for Business. È possibile trovare questi contatori accedendo a qualsiasi Mediation Server e aprendo il Monitor prestazioni. Questi contatori iniziano con "LS:". Microsoft consiglia di iniziare con i contatori di capacità seguenti come minimo e di aggiungerne altri di interesse:

     Totale chiamate attive:

     - LS:MediationServer - Chiamate in ingresso (_Total)\- correnti

     - LS:MediationServer - Chiamate in uscita (_Total)\- correnti

     Totale chiamate di bypass multimediale attivo:

     - LS:MediationServer - Chiamate in ingresso (_Total)\- Chiamate di bypass multimediale attivo

     - LS:MediationServer - Chiamate in uscita (_Total)\- Chiamate di bypass multimediale attivo

     > [!NOTE]
     > È necessario immettere manualmente i contatori delle prestazioni nella casella di testo. Non vengono visualizzate come opzioni nell'elenco a discesa.

     Per altre informazioni, vedere [origini dati sulle prestazioni di Windows e Linux in Log Analytics](/azure/log-analytics/log-analytics-data-sources-performance-counters)

### <a name="create-alerts"></a>Creare avvisi

Esistono due tipi di avvisi in OMS: numero di avvisi di risultati e avvisi di misurazione delle metriche. Per altre informazioni sulla creazione di avvisi, vedere [Uso delle regole di avviso in Log Analytics](/azure/log-analytics/log-analytics-alerts-creating).

Quando si creano avvisi, è consigliabile considerare quanto segue:

- Assicurarsi che l'avviso sia un avviso numero di risultati, ovvero la selezione predefinita.

- Le query demo richiedono che "Numero di risultati" sia impostato su "Maggiore di 0".

- È consigliabile impostare sia Intervallo di tempo che Frequenza avviso su 5 minuti.

- È consigliabile non abilitare "Elimina avvisi" per gli avvisi demo.

- Per gli scenari di avviso tipici, Microsoft consiglia di creare una coppia di avvisi: un avviso di errore e un avviso di reimpostazione. Per l'avviso di errore, selezionare livello di gravità Critico; per l'avviso di reimpostazione selezionare livello di gravità Informational .

Le sezioni seguenti descrivono come creare avvisi di esempio.

#### <a name="create-an-alert-pair-rtcmedsrv-is-not-running-in-mediation-servers-and-rtcmedsrv-is-back-in-running-in-mediation-servers"></a>Creare una coppia di avvisi: "RTCMEDSRV NON è in esecuzione nei mediation server" e "RTCMEDSRV è di nuovo in esecuzione nei mediation server"

Per creare questa coppia di avvisi:

- La query per l'avviso di errore è:

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    La query usa il filtro computer  *in cui Computer contiene "MediationServer"*  . Il filtro seleziona solo il computer il cui nome contiene la stringa "MediationServer".

     Sostituire il filtro con il proprio filtro computer o semplicemente rimuoverlo. È possibile creare filtri stringa complessi senza espressioni regolari. È anche possibile scegliere di usare espressioni regolari. Inoltre, è possibile creare un gruppo di computer salvando una query di ricerca e usando tale gruppo come filtro del computer nella query di avviso. Per altre informazioni, vedere [Gruppi di computer nelle ricerche nei log di Log Analytics](/azure/log-analytics/log-analytics-computer-groups).

    Per ogni computer, la query di errore otterrà l'ultimo registro eventi sia per l'avvio del servizio RTCMEDSRV che per l'arresto del servizio. Restituirà un log se l'ultimo evento è l'evento di arresto del servizio; non restituirà nulla se l'ultimo evento è l'evento di avvio del servizio. In breve, la query restituirà un elenco di server il cui RTCMEDSRV viene arrestato nell'intervallo di tempo.

- La query per l'avviso di reimpostazione è:

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    La query di reimpostazione esegue esattamente l'operazione opposta della query di errore. Per ogni computer, ne restituirà uno se l'ultimo evento è l'evento di avvio del servizio; non restituirà nulla se l'ultimo evento è l'evento di arresto del servizio.

#### <a name="create-an-alert-pair--too-many-concurrent-calls-in-mediation-servers-and-concurrent-calls-fall-back-to-normal-load"></a>Creare una coppia di avvisi: "Troppe chiamate simultanee in Mediation Server" e "Le chiamate simultanee tornano al carico normale"

Per creare questo avviso:

- La query per l'avviso di errore è:

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    Per ogni computer, la query otterrà gli ultimi contatori per la chiamata in ingresso e in uscita e somma i due valori. Restituirà un log se il valore della somma supera 500; non restituirà nulla se non lo fa. In breve, la query restituirà un elenco di server le cui chiamate simultanee sono troppe nell'intervallo di tempo.

- La query per l'avviso di reimpostazione è:

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    La query di reimpostazione esegue esattamente l'operazione opposta della query di errore. Per ogni computer, la query otterrà gli ultimi contatori per la chiamata in ingresso e in uscita e somma i due valori. Restituirà un log se il valore della somma è minore di 500; altrimenti non restituirà nulla.

#### <a name="create-an-alert-cpu-usage--90-or-rtcmediarelay-stopped-in-servers-alert"></a>Creare un avviso: avviso "Utilizzo \> CPU 90 o RTCMEDIARELAY arrestato nei server"

Per creare questo avviso, la query è:

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

La query otterrà tutti i contatori di utilizzo del processore e l'evento di arresto del servizio da tutti i computer e restituirà un log se l'utilizzo del processore supera il 90% o il servizio viene mai arrestato.

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>Analizzare gli avvisi nel repository di Log Analytics

Per analizzare gli avvisi nel repository, usare la soluzione Gestione avvisi. Per altre informazioni, vedere [Soluzione gestione avvisi in Operations Management Suite (OMS)](/azure/log-analytics/log-analytics-solution-alert-management)

## <a name="recommended-minimal-monitoring-set"></a>Set di monitoraggio minimo consigliato

Per identificare i problemi relativi ai log eventi e ai contatori delle prestazioni:

- **Log eventi.** Per qualsiasi problema, deve essere presente una coppia di eventi, con un set di eventi per indicare che qualcosa non funziona, mentre l'altro indica che tutto è corretto. Per un determinato periodo di tempo, è l'ultimo evento registrato che indicherà se qualcosa non va per quel periodo di tempo.

- **Contatori delle prestazioni.** Deve essere presente una soglia per i contatori monitorati.

Nella tabella seguente sono elencati i servizi che Microsoft consiglia di monitorare elencando gli ID evento di arresto e avvio:

|Nome servizio  <br/> |Ruolo server di destinazione  <br/> |ID evento stop  <br/> |ID evento start  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |Mediation Server  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |Edge Server  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |Edge Server  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |Edge Server  <br/> |22003  <br/> |22002  <br/> |

Nella tabella seguente sono elencati i problemi di rete consigliati da Microsoft per il monitoraggio:


| Nome monitoraggio  <br/>                                        | Ruolo server di destinazione  <br/> | Espressione di ID evento riuscita  <br/> | Espressione ID evento errore  <br/> | Esempio di errore  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| Errore di connettività da Mediation Server a gateway  <br/>    | Mediation Server  <br/>   | 25062                              |                                  | 25002  <br/>           |
| Errore di completamento della chiamata da Mediation Server a gateway  <br/> | Mediation Server  <br/>   | 25064                              |                                  | 25002  <br/>           |
| Problemi di rete critici  <br/>                           | Edge Server  <br/>        | 14353                              |                                  | 12288  <br/>           |

Di seguito sono elencati i contatori della capacità delle chiamate che devono essere monitorati. Questi numeri devono essere inferiori a 500 per l'edizione Standard di Cloud Connector; meno di 50 per l'edizione minima di Cloud Connector.

- LS:MediationServer - Chiamate in ingresso (_Total)\- correnti

- LS:MediationServer - Chiamate in uscita (_Total)\- correnti

- LS:MediationServer - Chiamate in ingresso (_Total)\- Chiamate di bypass multimediale attivo

- LS:MediationServer - Chiamate in uscita (_Total)\- Chiamate di bypass multimediale attivo

## <a name="see-also"></a>Vedere anche

Per altre informazioni sull'uso di OMS, vedere quanto segue:

- [Trovare i dati usando le ricerche nei log in Log Analytics](/azure/log-analytics/log-analytics-log-searches)

- [Informazioni sugli avvisi in Log Analytics](/azure/log-analytics/log-analytics-alerts)

- [Connessione Windows computer al servizio Log Analytics in Azure](/azure/log-analytics/log-analytics-windows-agents)