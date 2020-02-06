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
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: Leggere questo argomento per informazioni su come monitorare il Cloud Connector versione 2,1 e successiva usando Microsoft Operations Management Suite (OMS).
ms.openlocfilehash: 1dcac3519624cef898622f915b08b24363453b84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799626"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>Monitorare Cloud Connector mediante Operations Management Suite (OMS)

Leggere questo argomento per informazioni su come monitorare il Cloud Connector versione 2,1 e successiva usando Microsoft Operations Management Suite (OMS).

Ora è possibile monitorare il Cloud Connector versione 2,1 e la distribuzione successiva tramite Operations Management Suite (OMS), una soluzione di gestione IT cloud Microsoft. Analisi del log OMS consente di monitorare e analizzare la disponibilità e le prestazioni delle risorse, incluse le macchine fisiche e virtuali. Per altre informazioni su OMS e analisi dei log, vedere [cos'è Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview).

Questo argomento contiene le sezioni seguenti:

- Prerequisiti

- Configurare il connettore Cloud per l'uso di OMS

- Configurare OMS

- Analizzare gli avvisi nel repository di analisi del log

- Set di monitoraggio consigliato

## <a name="prerequisites"></a>Prerequisiti

Prima di poter usare OMS per monitorare la distribuzione di Cloud Connector, è necessario eseguire le operazioni seguenti:

- **Un account Azure e un'area di lavoro OMS.** Se non si dispone già di un account Azure, sarà necessario crearne uno per usare analisi del log OMS. Per informazioni su come creare un account Azure e configurare un'area di lavoro OMS, vedere [Introduzione a un'area di lavoro analisi log](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).

- **Cloud Connector versione 2,1 o successiva**

- **Log Analytics la ricerca di nuovi log** è necessaria per il monitoraggio del connettore Cloud. Per altre informazioni, vedere [aggiornare l'area di lavoro analisi log di Azure a nuova ricerca nel log](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).

## <a name="configure-cloud-connector-to-use-oms"></a>Configurare il connettore Cloud per l'uso di OMS

Per usare OMS è necessario configurare l'ambiente locale del connettore Cloud. A tale scopo, è necessario l'ID e la chiave dell'area di lavoro OMS, che è possibile trovare usando il portale OMS come segue: impostazioni\>--origini connesse\> --server Windows:

![Screenshot per l'OMS per il connettore Cloud](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

La modalità di configurazione del connettore Cloud per l'uso di OMS dipende dallo scenario:

- **Se si sta installando un nuovo accessorio Cloud Connector o si vuole ridistribuire un accessorio**, seguire questa procedura prima di eseguire Install-CcAppliance:

1. Nella sezione file CloudConnector. ini [Common] imposta il parametro OMSEnabled su true.

    Ogni volta che il connettore Cloud viene distribuito o aggiornato, tenterà di installare automaticamente l'agente OMS nella VM. Abilita questa funzionalità in modo che l'agente OMS possa sopravvivere all'aggiornamento automatico di Cloud Connector.

2. Per configurare l'ID e la chiave OMS, eseguire set-CcCredential-AccountType OMSWorkspace. 

- **Se si sta installando un agente OMS in un dispositivo Cloud Connector esistente**, seguire questa procedura:

1. Nella sezione file CloudConnector. ini [Common] imposta OMSEnabled = true. 

2. Eseguire Import-CcConfiguration. 

3. Eseguire Install-CcOMSAgent. 

    > [!NOTE]
    > Se la credenziale OMSWorkspace non è mai stata impostata, vengono richieste le credenziali quando si esegue Install-CcOMSAgent. 

- **Se si vuole aggiornare l'ID o la chiave dell'area di lavoro OMS in un appliance di connessione cloud che ha già installato un agente OMS:**

1. Per configurare l'ID e la chiave OMS, eseguire set-CcCredential-AccountType OMSWorkspace. 

2. Per applicare gli aggiornamenti, eseguire Install-CcOMSAgent. 

- **Per tutti gli scenari, verificare che gli agenti siano connessi come segue:**

    Nel portale OMS, passa a impostazioni-\> origini connesse-\> server Windows. Verrà visualizzato un elenco di computer connessi. 

## <a name="configure-oms"></a>Configurare OMS

Sarà quindi necessario specificare la configurazione OMS usando il portale OMS. In particolare, è necessario:

- Specificare informazioni sui registri eventi e sui contatori delle prestazioni.

- Creare avvisi. 

### <a name="specify-information-about-event-logs-and-performance-counters"></a>Specificare informazioni sui registri eventi e sui contatori delle prestazioni

Nel portale OMS è necessario specificare le informazioni sui registri eventi e sui contatori delle prestazioni, come indicato di seguito:

1. Accedere a impostazioni-\>dati-\>registri eventi di Windows e aggiungere i registri eventi per: 

   - Lync Server

   - Applicazione

     > [!NOTE]
     > È necessario immettere manualmente Lync Server nella casella di testo. Non viene visualizzata come opzione nell'elenco a discesa. 

     Per altre informazioni, vedere [origini dati del log eventi di Windows in analisi log](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)

2. Accedere a impostazioni-\>dati-\> contatori delle prestazioni di Windows e aggiungere contatori delle prestazioni per: 

   - **Contatori del livello di sistema operativo**. È possibile aggiungere contatori del livello di sistema operativo, ad esempio uso del processore, utilizzo della memoria, utilizzo della rete oppure usare soluzioni esistenti come capacità e prestazioni, Network Performance Monitor senza aggiungere contatori in modo esplicito. Indipendentemente dal modo in cui si decide di monitorarli, Microsoft consiglia di monitorare questi contatori del sistema operativo.

   - **Contatori Skype for business**. Ci sono numerosi contatori forniti da Skype for business. È possibile trovare questi contatori accedendo a qualsiasi Mediation Server e aprendo performance monitor. Questi contatori iniziano con "LS:". Microsoft consiglia di iniziare con i contatori di capacità seguenti al minimo e di aggiungerne altri interessanti:

     Totale chiamate attive:

   - LS: MediationServer-chiamate in ingresso (_Total)\- Current 

   - LS: MediationServer-chiamate in uscita (_Total)\- Current 

     Totale chiamate di bypass multimediali attivi:

   - LS: MediationServer-chiamata in ingresso (_Total)\- chiamate di bypass multimediali attive 

   - LS: MediationServer-chiamate in uscita (_Total)\- chiamate di bypass multimediali attive 

     > [!NOTE]
     > È necessario immettere manualmente i contatori delle prestazioni nella casella di testo. Non vengono visualizzate come opzioni nell'elenco a discesa. 

     Per altre informazioni, Vedi [origini dati delle prestazioni di Windows e Linux in analisi log](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)

### <a name="create-alerts"></a>Creare avvisi

In OMS sono disponibili due tipi di avvisi: numero di avvisi sui risultati e di avvisi di misura metrica. Per altre informazioni sulla creazione di avvisi, vedere [uso delle regole di avviso in analisi log](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).

Quando si creano avvisi, tenere presente quanto segue:

- Verificare che l'avviso sia un avviso di tipo numero di risultati, ovvero la selezione predefinita. 

- Le query demo richiedono che "numero di risultati" sia impostato su "maggiore di 0". 

- È consigliabile impostare la frequenza della finestra temporale e quella degli avvisi su 5 minuti. 

- È consigliabile non abilitare "Elimina avvisi" per gli avvisi demo. 

- Per gli scenari di avviso tipici, Microsoft consiglia di creare una coppia di avvisi: un avviso di errore e un avviso di reimpostazione. Per l'avviso di errore selezionare livello di gravità critico; per l'avviso Reimposta selezionare livello di gravità informativo.

Nelle sezioni seguenti viene descritto come creare avvisi di esempio.

 **Creare una coppia di avvisi: "RTCMEDSRV non è in uso in Mediation Servers" e "RTCMEDSRV è di nuovo in uso in Mediation Servers"**

Per creare questa coppia di avvisi:

- La query per l'avviso di errore è:

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    La query usa il filtro computer in *cui il computer contiene "MediationServer"* . Il filtro seleziona solo il computer il cui nome contiene la stringa "MediationServer".

     Sostituire il filtro con il filtro del computer o semplicemente rimuoverlo. Puoi creare filtri di stringhe complessi senza espressioni regolari. Per altre informazioni, Vedi [operatori di stringhe](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators). Puoi anche scegliere di usare le espressioni regolari. Inoltre, è possibile creare un gruppo di computer salvando una query di ricerca e usando il gruppo come filtro del computer nella query di avviso. Per altre informazioni, vedere [gruppi di computer in ricerche nel log di analisi log](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).

    Per ogni computer, la query di errore otterrà l'ultimo log eventi sia per l'avvio del servizio RTCMEDSRV che per l'arresto del servizio. Verrà restituito un log se l'ultimo evento è l'evento di interruzione del servizio; restituirà Nothing se l'ultimo evento è l'evento Start del servizio. In breve, la query restituisce un elenco di server il cui RTCMEDSRV viene interrotto nella finestra temporale. 

- La query per l'avviso di reimpostazione è:

  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    La query di reimpostazione fa esattamente la cosa opposta della query di errore. Per ogni computer, ne restituirà uno se l'ultimo evento è l'evento Start del servizio; restituirà Nothing se l'ultimo evento è l'evento di interruzione del servizio.

  **Creare una coppia di avvisi: "troppe chiamate simultanee in Mediation Server" e "chiamate simultanee ricadono al carico normale"**

Per creare questo avviso:

- La query per l'avviso di errore è:

  ```
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    Per ogni computer, la query otterrà gli ultimi contatori per la chiamata in ingresso e la chiamata in uscita e somma questi due valori. Verrà restituito un log se il valore somma supera 500; non restituirà nulla se non lo fa. In breve, la query restituisce un elenco di server le cui chiamate simultanee sono troppe nella finestra temporale.

- La query per l'avviso di reimpostazione è:

  ```
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    La query di reimpostazione fa esattamente la cosa opposta della query di errore. Per ogni computer, la query otterrà gli ultimi contatori per la chiamata in ingresso e la chiamata in uscita e somma questi due valori. Verrà restituito un log se il valore somma è minore di 500; non restituirà altro.

  **Creare un avviso: avviso "utilizzo \> della CPU 90 o RTCMEDIARELAY interrotto nei server"**

Per creare questo avviso, la query è:

```
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

La query otterrà tutti i contatori di utilizzo del processore e l'evento di arresto del servizio da tutti i computer e restituirà un log se l'utilizzo del processore supera 90% o il servizio è sempre interrotto. 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>Analizzare gli avvisi nel repository di analisi del log

Per analizzare gli avvisi nel repository, usare la soluzione di gestione degli avvisi. Per altre informazioni, vedere [soluzione di gestione degli avvisi in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)

## <a name="recommended-minimal-monitoring-set"></a>Set di monitoraggio minimo consigliato

Per identificare i problemi relativi ai registri eventi e ai contatori delle prestazioni: 

- **Registri eventi.** Per qualsiasi problema, deve essere presente una coppia di eventi, con un set di eventi per indicare che qualcosa non funziona, mentre l'altro indica che è tutto bene. Per un determinato periodo di tempo, è l'ultimo evento registrato che indicherà se qualcosa non funziona per quel periodo di tempo.

- **Contatori delle prestazioni.** Deve essere presente una soglia per i contatori monitorati.

La tabella seguente elenca i servizi consigliati da Microsoft per il monitoraggio elencando gli ID evento Stop e Start:

|Nome servizio  <br/> |Ruolo del server di destinazione  <br/> |Interrompi ID evento  <br/> |Inizio ID evento  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |Mediation Server  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |Edge Server  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |Edge Server  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |Edge Server  <br/> |22003  <br/> |22002  <br/> |

Nella tabella seguente sono elencati i problemi di rete consigliati da Microsoft per il monitoraggio:


| Nome del monitor  <br/>                                        | Ruolo del server di destinazione  <br/> | Espressione ID evento successo  <br/> | Espressione ID evento errore  <br/> | Esempio di errore  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| Errore di connettività del gateway Mediation Server  <br/>    | Mediation Server  <br/>   | 25062                              |                                  | 25002  <br/>           |
| Errore di completamento chiamata di Mediation Server a gateway  <br/> | Mediation Server  <br/>   | 25064                              |                                  | 25002  <br/>           |
| Problemi di rete critici  <br/>                           | Edge Server  <br/>        | 14353                              |                                  | 12288  <br/>           |

Di seguito sono elencati i contatori delle capacità delle chiamate da monitorare. Questi numeri devono essere inferiori a 500 per Cloud Connector Standard Edition; minore di 50 per il Cloud Connector Minimum Edition.

- LS: MediationServer-chiamate in ingresso (_Total)\- Current 

- LS: MediationServer-chiamate in uscita (_Total)\- Current 

- LS: MediationServer-chiamata in ingresso (_Total)\- chiamate di bypass multimediali attive

- LS: MediationServer-chiamate in uscita (_Total)\- chiamate di bypass multimediali attive

## <a name="see-also"></a>Vedere anche

Per altre informazioni sull'uso di OMS, vedere quanto segue:

- [Trovare i dati con ricerche log in analisi log](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [Informazioni di riferimento sul linguaggio di analisi del log di Azure](https://docs.loganalytics.io/docs/Language-Reference)

- [Informazioni sugli avvisi in analisi log](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [Connettere i computer Windows al servizio analisi log in Azure](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


