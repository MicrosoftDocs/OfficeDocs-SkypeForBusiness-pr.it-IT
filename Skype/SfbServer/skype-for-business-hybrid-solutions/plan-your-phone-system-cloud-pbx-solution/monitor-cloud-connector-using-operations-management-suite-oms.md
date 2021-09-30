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
description: Leggere questo argomento per informazioni su come monitorare la distribuzione di Cloud Connector versione 2.1 e successive tramite Microsoft Operations Management Suite (OMS).
ms.openlocfilehash: cf8a79b9b504b5a98592a169d3a507eb938353b9
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012310"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a>Monitorare Cloud Connector mediante Operations Management Suite (OMS)

> [!Important]
> Cloud Connector Edition andrà in pensione il 31 luglio 2021 insieme a Skype for Business Online. Dopo l'aggiornamento dell'organizzazione a Teams, informazioni su come connettere la rete di telefonia locale a Teams tramite [Routing diretto](/MicrosoftTeams/direct-routing-landing-page).

Leggere questo argomento per informazioni su come monitorare la distribuzione di Cloud Connector versione 2.1 e successive tramite Microsoft Operations Management Suite (OMS).

È ora possibile monitorare la distribuzione di Cloud Connector versione 2.1 e successive utilizzando Operations Management Suite (OMS), una soluzione di gestione IT cloud Microsoft. OMS Log Analytics consente di monitorare e analizzare la disponibilità e le prestazioni delle risorse, incluse le macchine fisiche e virtuali. Per ulteriori informazioni su OMS e Log Analytics, vedere [What is Operations Management Suite (OMS)?](/azure/operations-management-suite/operations-management-suite-overview)

In questa sezione sono contenute le seguenti sezioni:

- Prerequisiti

- Configurare Cloud Connector per l'utilizzo di OMS

- Configurare OMS

- Analizzare gli avvisi nel repository di Log Analytics

- Set di monitoraggio consigliato

## <a name="prerequisites"></a>Prerequisiti

Prima di poter utilizzare OMS per monitorare la distribuzione di Cloud Connector, è necessario quanto segue:

- **Un account Azure e un'area di lavoro OMS.** Se non si dispone già di un account Azure, sarà necessario crearne uno per usare OMS Log Analytics. Per informazioni su come creare un account Azure e configurare un'area di lavoro OMS, vedere Introduzione a un'area di [lavoro di Log Analytics.](/azure/log-analytics/log-analytics-get-started)

- **Cloud Connector versione 2.1 o successiva**

- **Log Analytics new log search** is required for Cloud Connector monitoring. Per ulteriori informazioni, vedere [Upgrade your Azure Log Analytics workspace to new log search.](/azure/log-analytics/log-analytics-log-search-upgrade)

## <a name="configure-cloud-connector-to-use-oms"></a>Configurare Cloud Connector per l'utilizzo di OMS

Sarà necessario configurare l'ambiente locale del connettore cloud per l'utilizzo di OMS. A tale scopo, sono necessari l'ID e la chiave dell'area di lavoro di OMS, che è possibile trovare utilizzando il portale OMS come segue: Impostazioni -- Origini connesse \> -- \> Windows Server:

![Screenshot per Cloud Connector OMS.](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

La modalità di configurazione di Cloud Connector per l'utilizzo di OMS dipende dallo scenario in uso:

- Se si sta installando una nuova appliance Cloud Connector o si desidera **ridistribuire un'appliance,** eseguire la procedura seguente prima di eseguire Install-CcAppliance:

    1. Nella sezione CloudConnector.ini file [Common] impostare il parametro OMSEnabled su True.

        Ogni volta che Cloud Connector viene distribuito o aggiornato, tenterà di installare automaticamente l'agente OMS nelle macchine virtuali. Abilita questa funzionalità in modo che l'agente OMS possa superare l'aggiornamento automatico del connettore cloud.

    2. Per configurare l'ID e la chiave OMS, eseguire Set-CcCredential -AccountType OMSWorkspace. 

- **Se si sta installando un agente OMS in un'appliance cloud connector** esistente, attenersi alla seguente procedura:

    1. Nella sezione CloudConnector.ini file [Common] imposta OMSEnabled=true. 

    2. Eseguire Import-CcConfiguration. 

    3. Eseguire Install-CcOMSAgent. 

        > [!NOTE]
        > Se la credenziale OMSWorkspace non è mai stata impostata, viene richiesto di immettere le credenziali quando si esegue install-CcOMSAgent. 

- **Se si desidera aggiornare l'ID o la chiave dell'area di lavoro OMS in un dispositivo Cloud Connector in cui è già installato un agente OMS:**

    1. Per configurare l'ID e la chiave OMS, eseguire Set-CcCredential -AccountType OMSWorkspace. 

    2. Per applicare gli aggiornamenti, eseguire Install-CcOMSAgent. 

- **Per tutti gli scenari, verificare che gli agenti siano connessi come segue:**

    Nel portale OMS passare a Impostazioni - \> Origini connesse - Windows \> server. Verrà visualizzato un elenco di computer connessi. 

## <a name="configure-oms"></a>Configurare OMS

Successivamente, sarà necessario specificare la configurazione di OMS utilizzando il portale OMS. In particolare, sarà necessario:

- Specificare informazioni sui registri eventi e sui contatori delle prestazioni.

- Creazione avvisi 

### <a name="specify-information-about-event-logs-and-performance-counters"></a>Specificare informazioni sui registri eventi e sui contatori delle prestazioni

Nel portale OMS è necessario specificare le informazioni sui registri eventi e sui contatori delle prestazioni come indicato di seguito:

1. Passare a Impostazioni- \> Dati- Windows registri eventi e aggiungere i registri eventi \> per: 

   - Lync Server

   - Applicazione

     > [!NOTE]
     > È necessario immettere manualmente Lync Server nella casella di testo. Non viene visualizzato come opzione nell'elenco a discesa. 

     Per ulteriori informazioni, vedere Windows [di dati del registro eventi in Log Analytics](/azure/log-analytics/log-analytics-data-sources-windows-events)

2. Passare a Impostazioni- Contatori delle prestazioni Windows dati e \> \> aggiungere contatori delle prestazioni per: 

   - **Contatori a livello del sistema operativo**. È possibile aggiungere contatori a livello del sistema operativo, ad esempio l'utilizzo del processore, l'utilizzo della memoria, l'utilizzo della rete, oppure è possibile utilizzare soluzioni esistenti come Capacità e prestazioni, Network Performance Monitor senza aggiungere contatori in modo esplicito. Indipendentemente da come si decide di monitorarli, Microsoft consiglia di monitorare questi contatori del sistema operativo.

   - **Skype for Business contatori .** Esistono numerosi contatori forniti da Skype for Business. È possibile trovare questi contatori accedendo a qualsiasi Mediation Server e aprendo Performance Monitor. Questi contatori iniziano con "LS:". Microsoft consiglia di iniziare almeno con i contatori di capacità seguenti e di aggiungere altri contatori di interesse:

     Totale chiamate attive:

       - LS:MediationServer - Chiamate in ingresso (_Total) \- correnti 

       - LS:MediationServer - Chiamate in uscita (_Total) \- correnti 

     Totale chiamate di bypass multimediale attive:

       - LS:MediationServer - Chiamate in ingresso (_Total) \- Chiamate di bypass multimediale attivo 

       - LS:MediationServer - Chiamate in uscita (_Total) \- Chiamate di bypass multimediale attivo 

     > [!NOTE]
     > È necessario immettere manualmente i contatori delle prestazioni nella casella di testo. Non vengono visualizzate come opzioni nell'elenco a discesa. 

     Per altre informazioni, vedi origini [dati Windows e Linux in Log Analytics](/azure/log-analytics/log-analytics-data-sources-performance-counters)

### <a name="create-alerts"></a>Creare avvisi

In OMS sono disponibili due tipi di avvisi: numero di avvisi dei risultati e avvisi di misurazione metrica. Per ulteriori informazioni sulla creazione di avvisi, vedere [Utilizzo delle regole di avviso in Log Analytics.](/azure/log-analytics/log-analytics-alerts-creating)

Quando si creano avvisi, è consigliabile tenere in considerazione quanto segue:

- Assicurati che l'avviso sia un avviso Numero di risultati, che è la selezione predefinita. 

- Le query demo richiedono che "Numero di risultati" sia impostato su "Maggiore di 0". 

- È consigliabile impostare sia l'intervallo di tempo che la frequenza degli avvisi su 5 minuti. 

- È consigliabile non abilitare "Elimina avvisi" per gli avvisi demo. 

- Per gli scenari di avviso tipici, Microsoft consiglia di creare una coppia di avvisi: un avviso di errore e un avviso di reimpostazione. Per l'avviso di errore, selezionare livello di gravità Critico; per l'avviso di reimpostazione, selezionare livello di gravità Informativo.

Nelle sezioni seguenti viene descritto come creare avvisi di esempio.

 **Creare una coppia di avvisi: "RTCMEDSRV NON è in esecuzione in Mediation Server" e "RTCMEDSRV è di nuovo in esecuzione in Mediation Server"**

Per creare questa coppia di avvisi:

- La query per l'avviso di errore è:

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    La query utilizza il filtro computer *in cui Computer contiene "MediationServer".* Il filtro seleziona solo il computer il cui nome contiene la stringa "MediationServer".

     È necessario sostituire il filtro con il proprio filtro del computer o semplicemente rimuoverlo. È possibile creare filtri stringa complessi senza espressioni regolari. È inoltre possibile scegliere di utilizzare espressioni regolari. È inoltre possibile creare un gruppo di computer salvando una query di ricerca e utilizzando tale gruppo come filtro computer nella query di avviso. Per ulteriori informazioni, vedere [Gruppi di computer in Log Analytics log searches](/azure/log-analytics/log-analytics-computer-groups).

    Per ogni computer, la query di errore otterrà l'ultimo registro eventi sia per l'avvio del servizio RTCMEDSRV che per l'arresto del servizio. Restituirà un registro se l'ultimo evento è l'evento di arresto del servizio. non restituirà nulla se l'ultimo evento è l'evento di avvio del servizio. In breve, la query restituirebbe un elenco di server il cui RTCMEDSRV viene arrestato nell'intervallo di tempo. 

- La query per l'avviso di reimpostazione è:

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    La query di reimpostazione esegue esattamente l'opposto della query di errore. Per ogni computer, restituirà uno se l'ultimo evento è l'evento di avvio del servizio. non restituirà nulla se l'ultimo evento è l'evento di arresto del servizio.

**Creare una coppia di avvisi: "Troppe chiamate simultanee in Mediation Server" e "Le chiamate simultanee tornano al normale carico"**

Per creare questo avviso:

- La query per l'avviso di errore è:

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    Per ogni computer, la query otterrà gli ultimi contatori per le chiamate in ingresso e in uscita e sommerà questi due valori. Restituirà un registro se il valore della somma supera 500; non restituirà nulla se non lo fa. In breve, la query restituirebbe un elenco di server le cui chiamate simultanee sono troppe nell'intervallo di tempo.

- La query per l'avviso di reimpostazione è:

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    La query di reimpostazione esegue esattamente l'opposto della query di errore. Per ogni computer, la query otterrà gli ultimi contatori per le chiamate in ingresso e in uscita e sommerà questi due valori. Restituirà un registro se il valore della somma è minore di 500; non restituirà nulla in caso contrario.

**Creare un avviso: avviso "Utilizzo CPU \> 90 o RTCMEDIARELAY arrestato nei server"**

Per creare questo avviso, la query è:

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

La query otterrà tutti i contatori di utilizzo del processore e l'evento di arresto del servizio da tutti i computer e restituirà un registro se l'utilizzo del processore supera il 90% o se il servizio viene mai arrestato. 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a>Analizzare gli avvisi nel repository di Log Analytics

Per analizzare gli avvisi nel repository, utilizzare la soluzione Gestione avvisi. Per ulteriori informazioni, vedere [Soluzione di gestione degli avvisi in Operations Management Suite (OMS)](/azure/log-analytics/log-analytics-solution-alert-management)

## <a name="recommended-minimal-monitoring-set"></a>Set di monitoraggio minimo consigliato

Per identificare i problemi relativi ai registri eventi e ai contatori delle prestazioni: 

- **Registri eventi.** Per qualsiasi problema, dovrebbe esserci una coppia di eventi, con un set di eventi per indicare che qualcosa non va, mentre l'altro indica che tutto è a posto. Per un determinato periodo di tempo, è l'ultimo evento registrato che indicherà se un elemento è in errore per tale periodo di tempo.

- **Contatori delle prestazioni.** Deve essere presente una soglia per i contatori monitorati.

Nella tabella seguente sono elencati i servizi consigliati da Microsoft per il monitoraggio elencando gli ID evento di arresto e avvio:

|Nome servizio  <br/> |Ruolo del server di destinazione  <br/> |ID evento di arresto  <br/> |ID evento di avvio  <br/> |
|:-----|:-----|:-----|:-----|
|RTCMEDSRV  <br/> |Mediation Server  <br/> |25003  <br/> |25002  <br/> |
|RTCSRV  <br/> |Edge Server  <br/> |12289  <br/> |12288  <br/> |
|RTCMRAUTH  <br/> |Edge Server  <br/> |19003  <br/> |19002  <br/> |
|RTCMEDIARELAY  <br/> |Edge Server  <br/> |22003  <br/> |22002  <br/> |

Nella tabella seguente sono elencati i problemi di rete consigliati da Microsoft per il monitoraggio:


| Nome monitor  <br/>                                        | Ruolo del server di destinazione  <br/> | Espressione ID evento operazione riuscita  <br/> | Espressione ID evento errore  <br/> | Esempio di errore  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| Errore di connettività da Mediation Server a gateway  <br/>    | Mediation Server  <br/>   | 25062                              |                                  | 25002  <br/>           |
| Errore di completamento delle chiamate da Mediation Server a gateway  <br/> | Mediation Server  <br/>   | 25064                              |                                  | 25002  <br/>           |
| Problemi critici di rete  <br/>                           | Edge Server  <br/>        | 14353                              |                                  | 12288  <br/>           |

Di seguito sono elencati i contatori della capacità delle chiamate che devono essere monitorati. Questi numeri devono essere inferiori a 500 per l'edizione standard del connettore cloud; meno di 50 per l'edizione minima del connettore cloud.

- LS:MediationServer - Chiamate in ingresso (_Total) \- correnti 

- LS:MediationServer - Chiamate in uscita (_Total) \- correnti 

- LS:MediationServer - Chiamate in ingresso (_Total) \- Chiamate di bypass multimediale attivo

- LS:MediationServer - Chiamate in uscita (_Total) \- Chiamate di bypass multimediale attivo

## <a name="see-also"></a>Vedere anche

Per ulteriori informazioni sull'utilizzo di OMS, vedere:

- [Trovare i dati usando le ricerche nei log in Log Analytics](/azure/log-analytics/log-analytics-log-searches)

- [Informazioni sugli avvisi in Log Analytics](/azure/log-analytics/log-analytics-alerts)

- [Connessione Windows computer al servizio Log Analytics in Azure](/azure/log-analytics/log-analytics-windows-agents)