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
description: Leggere questo argomento per informazioni su come monitorare il Cloud Connector versione 2,1 e versioni successive tramite Microsoft Operations Management Suite (OMS).
ms.openlocfilehash: eca2f56bf564e376717a42bd8d297710905f8dc6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359092"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>Monitorare Cloud Connector mediante Operations Management Suite (OMS)

> [!Important]
> Cloud Connector Edition si ritirerà il 31 luglio 2021 insieme a Skype for business online. Dopo che l'organizzazione ha eseguito l'aggiornamento ai team, informazioni su come connettere la rete di telefonia locale ai team che utilizzano il [routing diretto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).

Leggere questo argomento per informazioni su come monitorare il Cloud Connector versione 2,1 e versioni successive tramite Microsoft Operations Management Suite (OMS).

È ora possibile monitorare il Cloud Connector versione 2,1 e successive tramite Operations Management Suite (OMS), una soluzione di gestione IT di Microsoft Cloud. L'analisi dei log OMS consente di monitorare e analizzare la disponibilità e le prestazioni delle risorse, incluse le macchine fisiche e virtuali. Per ulteriori informazioni su OMS e analisi dei log, vedere [che cos'è Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)

In questa sezione sono contenute le seguenti sezioni:

- Prerequisiti

- Configurare il connettore Cloud per l'utilizzo di OMS

- Configurare OMS

- Analizzare gli avvisi nel repository di analisi dei log

- Set di monitoraggio consigliato

## <a name="prerequisites"></a>Prerequisiti

Prima di poter utilizzare OMS per monitorare la distribuzione dei connettori cloud, è necessario eseguire le operazioni seguenti:

- **Un account di Azure e un'area di lavoro OMS.** Se non si dispone già di un account di Azure, sarà necessario crearne uno per utilizzare analisi del registro OMS. Per informazioni su come creare un account di Azure e configurare un'area di lavoro OMS, vedere [Introduzione a un'area di lavoro di analisi dei log](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).

- **Cloud Connector versione 2,1 o successiva**

- **Log Analytics il nuovo log Search** è necessario per il monitoraggio dei connettori cloud. Per ulteriori informazioni, vedere [upgrade your Azure log Analytics Workspace to New Log Search](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).

## <a name="configure-cloud-connector-to-use-oms"></a>Configurare il connettore Cloud per l'utilizzo di OMS

È necessario configurare l'ambiente locale del connettore Cloud per l'utilizzo di OMS. A tale scopo, è necessario l'ID e la chiave dell'area di lavoro OMS, che è possibile trovare utilizzando il portale OMS come segue: impostazioni-- \> origini connesse-- \> server Windows:

![Screenshot per il connettore Cloud OMS](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

La modalità di configurazione del connettore Cloud per l'utilizzo di OMS dipende dallo scenario:

- **Se si sta installando un nuovo accessorio Cloud Connector o si desidera ridistribuire un dispositivo**, attenersi alla seguente procedura prima di eseguire Install-CcAppliance:

    1. Nella sezione file CloudConnector.ini [Common] impostare il parametro OMSEnabled su true.

        Ogni volta che il connettore Cloud viene distribuito o aggiornato, tenterà di installare l'agente OMS automaticamente sulle macchine virtuali. Abilitare questa funzionalità in modo che l'agente OMS possa sopravvivere all'aggiornamento automatico del connettore Cloud.

    2. Per configurare l'ID OMS e la chiave, eseguire set-CcCredential-AccountType OMSWorkspace. 

- **Se si sta installando un agente OMS su un dispositivo di connessione cloud esistente**, procedere come segue:

    1. Nella sezione file CloudConnector.ini [Common] impostare OMSEnabled = true. 

    2. Eseguire Import-CcConfiguration. 

    3. Eseguire Install-CcOMSAgent. 

        > [!NOTE]
        > Se non è mai stata impostata la credenziale OMSWorkspace, viene richiesto di utilizzare le credenziali quando si esegue Install-CcOMSAgent. 

- **Se si desidera aggiornare l'ID dell'area di lavoro OMS o la chiave in un dispositivo di connessione cloud che ha già installato un agente OMS:**

    1. Per configurare l'ID OMS e la chiave, eseguire set-CcCredential-AccountType OMSWorkspace. 

    2. Per applicare gli aggiornamenti, eseguire Install-CcOMSAgent. 

- **Per tutti gli scenari, verificare che gli agenti siano connessi come indicato di seguito:**

    Nel portale OMS accedere a origini connesse alle impostazioni \> - \> server Windows. Verrà visualizzato un elenco di computer connessi. 

## <a name="configure-oms"></a>Configurare OMS

Successivamente, è necessario specificare la configurazione OMS tramite il portale OMS. In particolare, sarà necessario:

- Specificare informazioni sui registri eventi e sui contatori delle prestazioni.

- Creazione avvisi 

### <a name="specify-information-about-event-logs-and-performance-counters"></a>Specificare informazioni sui registri eventi e sui contatori delle prestazioni

Nel portale OMS, è necessario specificare le informazioni sui registri eventi e sui contatori delle prestazioni, come indicato di seguito:

1. Passare a impostazioni- \> dati- \> registri eventi di Windows e aggiungere registri eventi per: 

   - Lync Server

   - Applicazione

     > [!NOTE]
     > È necessario immettere manualmente Lync Server nella casella di testo. Non viene visualizzata come opzione nell'elenco a discesa. 

     Per ulteriori informazioni, vedere [origini dati del registro eventi di Windows nell'analisi dei log](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)

2. Andare a Settings- \> data- \> Windows Performance Counters e aggiungere contatori delle prestazioni per: 

   - **Contatori del livello del sistema operativo**. È possibile aggiungere contatori a livello di sistema operativo, ad esempio l'utilizzo del processore, l'utilizzo della memoria, l'utilizzo della rete oppure è possibile utilizzare soluzioni esistenti quali capacità e prestazioni, Network Performance Monitor senza aggiungere contatori in modo esplicito. Indipendentemente dal modo in cui si decide di monitorarli, Microsoft consiglia di monitorare questi contatori del sistema operativo.

   - **Contatori Skype for business**. Sono disponibili numerosi contatori forniti da Skype for business. È possibile trovare questi contatori accedendo a qualsiasi Mediation Server e aprendo il monitoraggio delle prestazioni. Questi contatori iniziano con "LS:". Microsoft consiglia di iniziare con i contatori di capacità seguenti almeno e aggiungere altri che sono di interesse:

     Totale chiamate attive:

       - LS: MediationServer-chiamate in entrata (_Total) \- correnti 

       - LS: MediationServer-chiamate in uscita (_Total) \- correnti 

     Totale chiamate di bypass multimediale attivo:

       - LS: MediationServer-chiamate in entrata (_Total) \- chiamate di bypass multimediale attive 

       - LS: MediationServer-chiamate in uscita (_Total) le \- chiamate di bypass multimediale attivo 

     > [!NOTE]
     > È necessario immettere manualmente i contatori delle prestazioni nella casella di testo. Non vengono visualizzate come opzioni nell'elenco a discesa. 

     Per ulteriori informazioni, vedere [Windows and Linux Performance Data Sources in log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)

### <a name="create-alerts"></a>Creare avvisi

Sono disponibili due tipi di avvisi in OMS: numero di avvisi sui risultati e avvisi di misura metrica. Per ulteriori informazioni sulla creazione di avvisi, vedere [utilizzo delle regole di avviso nell'analisi dei log](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).

Quando si creano avvisi, tenere presente quanto segue:

- Verificare che l'avviso sia un avviso di numero di risultati, che è la selezione predefinita. 

- Le query demo richiedono che il "numero di risultati" sia impostato su "maggiore di 0". 

- Si consiglia di impostare la frequenza delle finestre temporali e degli avvisi su 5 minuti. 

- Si consiglia di non abilitare "Ometti avvisi" per gli avvisi demo. 

- Per gli scenari di avviso tipici, Microsoft consiglia di creare una coppia di avvisi: un avviso di errore e un avviso di reimpostazione. Per l'avviso di errore, selezionare livello di gravità critico. per l'avviso Reimposta, selezionare livello di gravità informativo.

Nelle sezioni seguenti viene descritto come creare avvisi di esempio.

 **Creare una coppia di avvisi: "RTCMEDSRV non è in esecuzione in Mediation Server" e "RTCMEDSRV è tornato in esecuzione in Mediation Server"**

Per creare questa coppia di avvisi:

- La query per l'avviso di errore è la seguente:

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    La query utilizza il filtro computer in  *cui il computer contiene "MediationServer"*  . Il filtro seleziona solo il computer il cui nome contiene la stringa "MediationServer".

     È necessario sostituire il filtro con il proprio filtro del computer o semplicemente rimuoverlo. È possibile creare filtri stringa complessi senza espressioni regolari. Per ulteriori informazioni, vedere [String Operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators). È anche possibile scegliere di utilizzare le espressioni regolari. Inoltre, è possibile creare un gruppo di computer salvando una query di ricerca e usando quel gruppo come filtro del computer nella query di avviso. Per ulteriori informazioni, vedere [gruppi di computer nelle ricerche dei log di analisi](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups)log.

    Per ogni computer, la query di errore otterrà l'ultimo registro eventi sia per l'avvio del servizio di RTCMEDSRV che per l'arresto del servizio. Restituirà un log se l'ultimo evento è l'evento di arresto del servizio; restituirà Nothing se l'ultimo evento è l'evento di avvio del servizio. In breve, la query restituisce un elenco di server la cui RTCMEDSRV viene interrotta nella finestra temporale. 

- La query per l'avviso di reimpostazione è:

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    La query di reimpostazione fa esattamente l'operazione opposta alla query di errore. Per ogni computer, ne restituirà uno se l'ultimo evento è l'evento di avvio del servizio. restituirà Nothing se l'ultimo evento è l'evento di arresto del servizio.

**Creare una coppia di avvisi: "troppe chiamate simultanee in Mediation Server" e "le chiamate simultanee ricadono sul carico normale"**

Per creare questo avviso:

- La query per l'avviso di errore è la seguente:

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    Per ogni computer, la query otterrà gli ultimi contatori per le chiamate in ingresso e in uscita e somma i due valori. Restituirà un log se il valore della somma è superiore a 500; non restituirà alcun valore se non lo è. In breve, la query restituisce un elenco di server le cui chiamate simultanee sono troppe nella finestra temporale.

- La query per l'avviso di reimpostazione è:

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    La query di reimpostazione fa esattamente l'operazione opposta alla query di errore. Per ogni computer, la query otterrà gli ultimi contatori per le chiamate in ingresso e in uscita e somma i due valori. Se il valore della somma è inferiore a 500, verrà restituito un log. in caso contrario, non restituirà alcun valore.

**Creare un avviso: "avviso di utilizzo della CPU \> 90 o RTCMEDIARELAY interrotto nei server"**

Per creare questo avviso, la query è:

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

La query otterrà tutti i contatori di utilizzo del processore e l'evento di arresto del servizio da tutti i computer e restituirà un log se l'utilizzo del processore supera il 90% o il servizio non viene mai interrotto. 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>Analizzare gli avvisi nel repository di analisi dei log

Per analizzare gli avvisi nell'archivio, utilizzare la soluzione di gestione avvisi. Per ulteriori informazioni, vedere [Alert Management Solution in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)

## <a name="recommended-minimal-monitoring-set"></a>Set di monitoraggio minimo consigliato

Per identificare i problemi relativi ai registri eventi e ai contatori delle prestazioni: 

- **Registri eventi.** Per qualsiasi problema, deve essere presente una coppia di eventi, con un insieme di eventi per indicare che qualcosa non va, mentre l'altro indica che è tutto a posto. Per un determinato periodo di tempo, è l'ultimo evento registrato che indicherà se qualcosa non funziona per il periodo di tempo specificato.

- **Contatori delle prestazioni.** Deve essere presente una soglia per i contatori monitorati.

Nella tabella seguente sono elencati i servizi che Microsoft consiglia di monitorare elencando gli ID evento Stop e Start:

|Nome del servizio  <br/> |Ruolo del server di destinazione  <br/> |Interrompere l'ID evento  <br/> |ID evento di avvio  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |Mediation Server  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |Edge Server  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |Edge Server  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |Edge Server  <br/> |22003  <br/> |22002  <br/> |

Nella tabella seguente sono elencati i problemi di rete che Microsoft consiglia di monitorare:


| Nome del monitoraggio  <br/>                                        | Ruolo del server di destinazione  <br/> | Espressione dell'ID evento di esito positivo  <br/> | Espressione dell'ID evento di errore  <br/> | Esempio di errore  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| Mediation Server all'errore di connettività del gateway  <br/>    | Mediation Server  <br/>   | 25062                              |                                  | 25002  <br/>           |
| Errore di completamento delle chiamate del gateway Mediation Server  <br/> | Mediation Server  <br/>   | 25064                              |                                  | 25002  <br/>           |
| Problemi di rete critici  <br/>                           | Edge Server  <br/>        | 14353                              |                                  | 12288  <br/>           |

Di seguito sono elencati i contatori delle capacità di chiamata che devono essere monitorati. Questi numeri devono essere inferiori a 500 per Cloud Connector Standard Edition; meno di 50 per l'edizione minima del connettore Cloud.

- LS: MediationServer-chiamate in entrata (_Total) \- correnti 

- LS: MediationServer-chiamate in uscita (_Total) \- correnti 

- LS: MediationServer-chiamate in entrata (_Total) \- chiamate di bypass multimediale attive

- LS: MediationServer-chiamate in uscita (_Total) le \- chiamate di bypass multimediale attivo

## <a name="see-also"></a>Vedere anche

Per ulteriori informazioni sull'utilizzo di OMS, vedere gli argomenti seguenti:

- [Trovare i dati utilizzando le ricerche log nell'analisi dei log](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [Informazioni di riferimento sul linguaggio del registro di Azure](https://docs.loganalytics.io/docs/Language-Reference)

- [Informazioni sugli avvisi nell'analisi del log](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [Connettere i computer Windows al servizio di analisi dei log in Azure](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


