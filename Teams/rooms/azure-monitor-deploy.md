---
title: Distribuire la gestione delle sale di Microsoft Teams con Azure Monitor
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: Questo articolo illustra come distribuire la gestione dei dispositivi di Microsoft Teams Room in modo integrato e completo con Azure Monitor.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b05c490c157c9f6530ca79ecdd8df19f15d94c68
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662101"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-management-with-no-loc-textazure-monitor"></a>Gestione :::no-loc text="Microsoft Teams Rooms"::: della distribuzione con :::no-loc text="Azure Monitor":::

Questo articolo illustra come configurare e distribuire la gestione integrata end-to-end dei dispositivi :::no-loc text="Microsoft Teams Rooms"::: tramite :::no-loc text="Azure Monitor"::: .

È possibile configurarlo all'interno per fornire telemetria e avvisi di base :::no-loc text="Log Analytics"::: che consentono di gestire i dispositivi delle sale :::no-loc text="Azure Monitor"::: :::no-loc text="Microsoft Teams Rooms"::: riunioni. Quando la soluzione di gestione è stata creata, è possibile decidere di distribuire altre funzionalità di gestione e dati per creare una visualizzazione più dettagliata della disponibilità e delle prestazioni dei dispositivi.

Seguendo questa guida, è possibile usare un dashboard come l'esempio seguente per ottenere report di stato dettagliati sulla disponibilità dei dispositivi, l'integrità di applicazioni e hardware e la distribuzione delle versioni di applicazioni :::no-loc text="Microsoft Teams Rooms"::: e sistemi operativi.

![Screenshot della visualizzazione Analisi log di esempio per sale di Microsoft Teams](../media/Deploy-Azure-Monitor-1.png "Esempio di visualizzazione Analisi log per sale di Microsoft Teams")

In alto, è necessario eseguire le attività seguenti:


1. [Convalida :::no-loc text="Log Analytics"::: configurazione](azure-monitor-deploy.md#validate_LogAnalytics)
2. [Configurare i dispositivi di test per la :::no-loc text="Log Analytics"::: configurazione della gestione](azure-monitor-deploy.md#configure_test_devices)
3. [Mappare i campi personalizzati](azure-monitor-deploy.md#Custom_fields)
4. [Definire le :::no-loc text="Microsoft Teams Rooms"::: visualizzazioni in :::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [Definire gli avvisi](azure-monitor-deploy.md#Alerts)
6. [Configurare tutti i dispositivi per il monitoraggio](azure-monitor-deploy.md#configure_all_devices)
7. [Configurare altre :::no-loc text="Azure Monitor"::: soluzioni](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> Anche se con una configurazione minima, è possibile monitorare un computer che esegue un sistema operativo, tuttavia è comunque necessario eseguire alcuni passaggi specifici prima di iniziare la distribuzione di agenti in :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: tutti i :::no-loc text="Windows"::: :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Microsoft Teams Rooms"::: dispositivi.
> Pertanto, è consigliabile eseguire tutti i passaggi di configurazione nell'ordine corretto per una configurazione e una configurazione controllate. La qualità del risultato finale dipende molto dalla qualità della configurazione iniziale.

## <a name="validate-no-loc-textlog-analytics-configuration"></a>Convalida :::no-loc text="Log Analytics"::: configurazione
<a name="validate_LogAnalytics"> </a>

È necessario avere :::no-loc text="Log Analytics"::: un'area di lavoro per iniziare a raccogliere i log dai :::no-loc text="Microsoft Teams Rooms"::: dispositivi. Un'area di lavoro :::no-loc text="Log Analytics"::: è un ambiente univoco con un archivio dati, origini dati e soluzioni propri. Se si ha già un'area di lavoro esistente, è possibile usarla per monitorare la distribuzione oppure, in alternativa, creare un'area di lavoro dedicata specifica per le proprie :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: esigenze di :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: monitoraggio.

Se è necessario creare una nuova area di lavoro, seguire le istruzioni :::no-loc text="Log Analytics"::: nell'articolo [Creare un'area di lavoro nel :::no-loc text="Log Analytics"::: :::no-loc text="Azure"::: portale](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)

> [!NOTE]
> Per usare :::no-loc text="Log Analytics"::: con , è necessario avere un abbonamento :::no-loc text="Azure Monitor"::: :::no-loc text="Azure"::: attivo. Se non si ha un abbonamento, è possibile creare un abbonamento di valutazione :::no-loc text="Azure"::: [gratuito](https://azure.microsoft.com/free) come punto di partenza.

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>Configurazione per :::no-loc text="Log Analytics"::: la raccolta dei log :::no-loc text="Microsoft Teams Rooms"::: eventi

:::no-loc text="Log Analytics"::: raccoglie solo gli eventi :::no-loc text="Windows"::: dai log eventi specificati nelle impostazioni. Per ogni log vengono raccolti solo gli eventi con i livelli di gravità selezionati.

È necessario configurarlo per raccogliere i log necessari per monitorare lo stato dei :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: dispositivi e delle applicazioni. :::no-loc text="Microsoft Teams Rooms"::: usano il **:::no-loc text="Skype Room System":::** registro eventi.

Per la configurazione :::no-loc text="Log Analytics"::: per la raccolta degli :::no-loc text="Microsoft Teams Rooms"::: eventi, vedere le origini dati [ :::no-loc text="Windows"::: del log eventi in :::no-loc text="Azure Monitor"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)

![Screenshot delle impostazioni del registro eventi](../media/Deploy-Azure-Monitor-2.png "Impostazioni del registro eventi")

> [!IMPORTANT]
> Configurare le impostazioni del registro eventi e immetterlo come nome del log eventi, quindi selezionare le caselle di controllo :::no-loc text="Windows"::: **:::no-loc text="Skype Room System":::** Errore, Avviso **e** Informazioni.  

## <a name="configure-test-devices-for-azure-monitoring"></a>Configurare i dispositivi di test per il monitoraggio di Azure
<a name="configure_test_devices"> </a>

È necessario prepararsi :::no-loc text="Log Analytics"::: per il monitoraggio degli eventi :::no-loc text="Microsoft Teams Rooms"::: correlati. Per iniziare, è necessario distribuire gli agenti in uno o due dispositivi a cui si ha accesso fisico e fare in modo che questi dispositivi di test generino alcuni dati e la inserisca :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: nell'area :::no-loc text="Log Analytics"::: di lavoro.

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>Installare :::no-loc text="Microsoft Monitoring"::: agenti per testare i dispositivi

Distribuire :::no-loc text="Microsoft Monitoring"::: l'agente ai dispositivi di test usando le istruzioni fornite in Connetti computer al servizio [ :::no-loc text="Windows"::: :::no-loc text="Log Analytics"::: in :::no-loc text="Azure"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows). Questo articolo fornisce informazioni dettagliate sui passaggi per la distribuzione dell'agente per, le istruzioni per ottenere l'ID area di lavoro e la chiave primaria per collegare i dispositivi alla distribuzione e i passaggi per verificare la connettività dell'agente :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Windows"::: all'istanza. :::no-loc text="Log Analytics":::  * ** _**_ :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics":::

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>Generare eventi di :::no-loc text="Microsoft Teams Rooms"::: esempio

Dopo la :::no-loc text="Microsoft Monitoring"::: distribuzione dell'agente nei dispositivi di test, verificare che i dati del log eventi necessari siano raccolti da :::no-loc text="Azure Monitor"::: .

> [!NOTE]
> Riavviare il dispositivo dopo l'installazione dell'agente e assicurarsi che l'app Riunione sia avviata, in modo che possa generare nuovi eventi nel registro :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: eventi.

1.  Accedere al portale e [ :::no-loc text="Microsoft Azure"::: passare](https://portal.azure.com) all'area di :::no-loc text="Log Analytics"::: lavoro e selezionarla.

2.  Elencare gli eventi heartbeat generati da un :::no-loc text="Microsoft Teams Rooms"::: dispositivo:
    1.  Selezionare l'area di lavoro e passare a _ *Log** e usare una query per recuperare i record heartbeat che avranno i campi personalizzati :::no-loc text="Microsoft Teams Rooms"::: per.
    2.  Query di esempio: `Event | where Source == "SRS-App" and EventID == 2000`

3.  Assicurarsi che la query restituisca record di log che includono eventi generati :::no-loc text="Microsoft Teams Rooms"::: dall'app riunioni.

4.  Generare un problema hardware e verificare che gli eventi necessari siano :::no-loc text="Azure Log Analytics"::: registrati.
    1.  Scollegare uno dei dispositivi periferici nel sistema di :::no-loc text="Microsoft Teams Rooms"::: prova. Può trattarsi della fotocamera, del vivavoce, del microfono o dello schermo della sala anteriore
    2.  Attendere 10 minuti per il popolamento del log eventi in :::no-loc text="Azure Log Analytics"::: .
    3.  Usare una query per elencare gli eventi di errore hardware: `Event | where Source == "SRS-App" and EventID == 3001`

5.  Generare un problema relativo all'applicazione e verificare che gli eventi necessari siano registrati.
    1.  Modificare :::no-loc text="Microsoft Teams Rooms"::: la configurazione dell'applicazione e digitare una coppia indirizzo/password SIP (Session Initiation Protocol) non corretta.
    2.  Attendere 10 minuti per il popolamento del log eventi in :::no-loc text="Azure Log Analytics"::: .
    3.  Usare una query per elencare gli eventi di errore dell'applicazione: `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Questi log eventi di esempio sono necessari per la configurazione dei campi personalizzati. Non proseguire con il passaggio successivo finché non sono stati raccolti i log eventi necessari.

## <a name="map-custom-fields"></a>Mappare i campi personalizzati
<a name="Custom_fields"> </a>

I campi personalizzati vengono utilizzati per estrarre dati specifici dai log eventi. È necessario definire i campi personalizzati che verranno usati in seguito con i riquadri, le visualizzazioni dashboard e gli avvisi. Visualizzare [i :::no-loc text="Log Analytics"::: campi personalizzati e](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) acquisire familiarità con i concetti prima di iniziare a creare i campi personalizzati.

Per estrarre i campi personalizzati dai log eventi acquisiti, seguire questa procedura:

1.  Accedere al portale e [ :::no-loc text="Microsoft Azure"::: passare](https://portal.azure.com) all'area di :::no-loc text="Log Analytics"::: lavoro e selezionarla.

2. Elencare gli eventi generati da un :::no-loc text="Microsoft Teams Rooms"::: dispositivo:
   1.  Passare ai **log** e usare una query per recuperare i record che avranno il campo personalizzato.
   2.  Query di esempio: `Event | where Source == "SRS-App" and EventID == 2000`

3. Selezionare uno dei record, selezionare il pulsante a sinistra e avviare l'estrazione guidata dei campi.
4. Evidenziare i dati da estrarre da RenderedDescription e specificare un titolo di campo. I nomi dei campi da usare sono specificati nella tabella 1.
5. Usare i mapping mostrati nella *tabella 1.* :::no-loc text="Log Analytics":::aggiunge automaticamente la **\_ stringa CF** quando si definisce il nuovo campo.

> [!IMPORTANT]
> Tenere presente che per tutti JSON e :::no-loc text="Log Analytics"::: i campi viene fatto distinzione tra maiuscole e minuscole.
> 
> Prestare attenzione alle query necessarie per ogni campo personalizzato nella tabella seguente. È necessario usare le query corrette per estrarre :::no-loc text="Log Analytics"::: correttamente i valori dei campi personalizzati.
> 
**Tabella 1**

| **JSON**                   | **:::no-loc text="Log Analytics"::: campo personalizzato** | **ID evento** | **Query da usare con l'estrazione**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| Descrizione                      | SRSEventDescription         | **2000**     | Evento \| in cui Source == "SRS-App" e EventID == 2000 |
| ResourceState                    | SRSResourceState            | **2000**     | Evento \| in cui Source == "SRS-App" e EventID == 2000 |
| OperationName                    | SRSOperationName            | **2000**     | Evento \| in cui Source == "SRS-App" e EventID == 2000 |
| OperationResult                  | SRSOperationResult          | **2000**     | Evento \| in cui Source == "SRS-App" e EventID == 2000 |
| OS                               | SRSOSVersion                | **2000**     | Evento \| in cui Source == "SRS-App" e EventID == 2000 |
| OSVersion                        | SRSOSLongVersion            | **2000**     | Evento \| in cui Source == "SRS-App" e EventID == 2000 |
| Alias                            | SRSAlias                    | **2000**     | Evento \| in cui Source == "SRS-App" e EventID == 2000 |
| DisplayName                      | SRSDisplayName              | **2000**     | Evento \| in cui Source == "SRS-App" e EventID == 2000 |
| AppVersion                       | SRSAppVersion               | **2000**     | Evento \| in cui Source == "SRS-App" e EventID == 2000 |
| IPv4Address                      | SRSIPv4Address              | **2000**     | Evento \| in cui Source == "SRS-App" e EventID == 2000 |
| IPv6Address                      | SRSIPv6Address              | **2000**     | Evento \| in cui Source == "SRS-App" e EventID == 2000 |
| Stato microfono conferenza     | SRSConfMicrophoneStatus     | **3001**     | Evento \| in cui Source == "SRS-App" e EventID == 3001 |
| Stato relatore conferenza        | SRSConfSpeakerStatus        | **3001**     | Evento \| in cui Source == "SRS-App" e EventID == 3001 |
| Stato altoparlante predefinito           | SRSDefaultSpeakerStatus     | **3001**     | Evento \| in cui Source == "SRS-App" e EventID == 3001 |
| Stato videocamera                    | SRSCameraStatus             | **3001**     | Evento \| in cui Source == "SRS-App" e EventID == 3001 |
| Front of Room Display status     | SRSFORDStatus               | **3001**     | Evento \| in cui Source == "SRS-App" e EventID == 3001 |
| Stato sensore movimento             | SRSMotionSensorStatus       | **3001**     | Evento \| in cui Source == "SRS-App" e EventID == 3001 |
| Stato di inserimento HDMI               | SRSHDMIIngestStatus         | **3001**     | Evento \| in cui Source == "SRS-App" e EventID == 3001 |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>Definire le :::no-loc text="Microsoft Teams Rooms"::: visualizzazioni in :::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

Dopo la raccolta dei dati e il mapping dei campi personalizzati, è possibile usare Progettazione visualizzazioni per sviluppare un dashboard contenente vari riquadri per il monitoraggio degli :::no-loc text="Microsoft Teams Rooms"::: eventi. Usare Progettazione visualizzazioni per creare i riquadri seguenti. Per altre informazioni, vedere [Creare visualizzazioni :::no-loc text="Log Analytics"::: personalizzate usando Progettazione visualizzazioni in](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> I passaggi precedenti di questa guida dovrebbero essere stati completati perché i riquadri dei dashboard funzionino correttamente.

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a>Creare un dashboard Sale di Microsoft Teams con il metodo di importazione

È possibile importare :::no-loc text="Microsoft Teams Rooms"::: una dashboard e iniziare a monitorare rapidamente i dispositivi. Eseguire la procedura seguente per importare il dashboard:

1.  Ottenere il file [SkypeRoomSystems_v2.omsview](https://go.microsoft.com/fwlink/?linkid=835675) dashboard.
2.  Accedere al portale e [ :::no-loc text="Microsoft Azure"::: passare](https://portal.azure.com) all'area di :::no-loc text="Log Analytics"::: lavoro e selezionarla.
3.  Aprire **Progettazione visualizzazioni.**
4.  Selezionare **Importa,** quindi selezionare il file **SkypeRoomSystems_v2.omsview.**
5.  Selezionare **Salva**.

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Creare manualmente un dashboard Sale di Microsoft Teams

In alternativa, è possibile creare un dashboard personalizzato e aggiungere solo i riquadri da monitorare.

#### <a name="configure-the-overview-tile"></a>Configurare il riquadro Panoramica

1.  Aprire **Progettazione visualizzazioni.**
2.  Selezionare **Riquadro panoramica** e quindi selezionare Due **numeri** nella raccolta.
3.  Assegnare un nome al **:::no-loc text="Microsoft Teams Rooms":::** riquadro.
4.  Definire il **primo riquadro:**<br>
    **Legenda:** Dispositivi che hanno inviato un heartbeat almeno una volta nell'ultimo mese<br>
    **Query:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Definire il **secondo riquadro:**<br>
    **Legenda:** Dispositivi attivi che hanno inviato un heartbeat nell'ultima ora<br>
    **Query:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Selezionare **Applica.**

### <a name="create-a-tile-that-displays-active-devices"></a>Creare un riquadro che mostra i dispositivi attivi

1.  Seleziona **Visualizza dashboard** per iniziare ad aggiungere i riquadri.
2.  Selezionare **Elenco & numerato** nella raccolta
3.  Definire le **proprietà** Generali:<br>
    **Titolo gruppo:** Stato Heartbeat<br>
    **Nuovo gruppo:** Selezionato
4.  Definire le **proprietà del** riquadro:<br>
    **Legenda:** Dispositivi attivi (heartbeat inviato negli ultimi 20 minuti)<br>
    **Query affiancata:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Definire le **proprietà dell'elenco:**<br>
    **Query elenco:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Definire **i titoli di colonna:**<br>
    **Nome:** Nome computer<br>
    **Valore:** Last Heartbeat
7.  Definire **una query di spostamento.**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Selezionare **Applica** e quindi **Chiudi.**

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Creare un riquadro che mostra i dispositivi con problemi di connettività

1.  Selezionare **Elenco &** numero nella raccolta e quindi aggiungere un nuovo riquadro.
2.  Definire le **proprietà** Generali:<br>
    **Titolo gruppo:** Lasciare vuoto<br>
    **Nuovo gruppo:** Non selezionato
3.  Definire le **proprietà del** riquadro:<br>
    **Legenda:** Dispositivi inattivi (nessun messaggio heartbeat inviato negli ultimi 20 minuti)<br>
    **Query affiancata:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Definire le **proprietà dell'elenco:**<br>
    **Query elenco:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Definire **i titoli di colonna:**<br>
    **Nome:** Nome computer<br>
    **Valore:** Last Heartbeat
6.  Definisci **query di spostamento:**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Selezionare **Applica** e quindi **Chiudi.**

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Creare un riquadro che visualizza i dispositivi con un errore hardware

1.  Selezionare **Elenco &** numero nella raccolta e quindi aggiungere un nuovo riquadro.
2.  Definire le **proprietà** Generali:<br>
    **Titolo gruppo:** Stato hardware<br>
    **Nuovo gruppo:** Selezionato
3.  Definire le **proprietà del** riquadro:<br>
    **Legenda:** Dispositivi che hanno riscontrato un errore hardware nell'ultima ora<br>
    **Query affiancata:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Definire le **proprietà dell'elenco:**<br>
    **Query elenco:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definire **i titoli di colonna:**<br>
    **Nome:** Nome computer<br>
    **Valore:** Ultimo errore
6.  Definisci **query di spostamento:**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Selezionare **Applica** e quindi **Chiudi.**

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>Creare un riquadro che mostra le :::no-loc text="Microsoft Teams Rooms"::: versioni del sistema operativo

1.  Seleziona **Donut & list** from the gallery, and then add a new tile.
2.  Definire le **proprietà** Generali:<br>
    **Titolo gruppo:** Dettagli del sistema operativo<br>
    **Nuovo gruppo:** Selezionato
3.  Definire le **proprietà dell'intestazione:**<br>
    **Titolo:** Versioni del sistema operativo<br>
    **Sottotitolo:** Dispositivi che eseguono versioni specifiche del sistema operativo
4.  Definire le **proprietà della donut:**<br>
    **Query:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **Centra il testo:** Dispositivi<br>
    **Operazione:** Somma
5.  Definire le **proprietà dell'elenco.**<br>
    **Query elenco:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **Nascondi grafico:** Selezionato<br>
    **Abilitare i grafici sparkline:** Non selezionato
6.  Definire **i titoli delle colonne.**<br>
    **Nome:** Nome computer<br>
    **Valore:** Lasciare vuoto
7.  Definire **una query di spostamento.**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Selezionare **Applica** e quindi **Chiudi.**

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>Creare un riquadro che visualizza le versioni :::no-loc text="Microsoft Teams Rooms"::: delle applicazioni

1.  Seleziona **Donut & list** from the gallery, and then add a new tile.
2.  Definire le **proprietà** Generali:<br>
    **Titolo gruppo:** :::no-loc text="Microsoft Teams Rooms"::: dettagli dell'applicazione<br>
    **Nuovo gruppo:** Selezionato
3.  Definire le **proprietà dell'intestazione:**<br>
    **Titolo:** Versioni delle applicazioni<br>
    **Sottotitolo:** Dispositivi che eseguono versioni specifiche delle applicazioni
4.  Definire le **proprietà della donut:**<br>
    **Query:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **Centra il testo:** Dispositivi<br>
    **Operazione:** Somma
5.  Definire le **proprietà dell'elenco.**<br>
    **Query elenco:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **Nascondi grafico:** Selezionato<br>
    **Abilitare i grafici sparkline:** Non selezionato
6.  Definire **i titoli delle colonne.**<br>
    **Nome:** Nome computer<br>
    **Valore:** Lasciare vuoto
7.  Definire **una query di spostamento.**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Selezionare **Applica** e quindi **Chiudi.**

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Creare un riquadro che visualizza i dispositivi con un errore di applicazione

1.  Selezionare **Elenco &** numero nella raccolta e quindi aggiungere un nuovo riquadro.
2.  Definire le **proprietà** Generale.<br>
    **Titolo gruppo:** Lasciare vuoto<br>
    **Nuovo gruppo:** Non selezionato
3.  Definire le **proprietà del** riquadro.<br>
    **Legenda:** Dispositivi in cui si è verificato un errore nell'ultima ora<br>
    **Query affiancata:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Definire le **proprietà dell'elenco.**<br>
    **Query elenco:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definire **i titoli delle colonne.**<br>
    **Nome:** Nome computer<br>
    **Valore:** Ultimo errore
6.  Definire **una query di spostamento.**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Selezionare **Applica** e quindi **Chiudi.**

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Crea un riquadro che mostra i dispositivi che sono stati riavviati

1.  Selezionare **Elenco &** numero nella raccolta e quindi aggiungere un nuovo riquadro.
2.  Definire le **proprietà** Generale.<br>
    **Titolo gruppo:** Lasciare vuoto<br>
    **Nuovo gruppo:** Non selezionato
3.  Definire le **proprietà del** riquadro.<br>
    **Legenda:** Dispositivi in cui l'applicazione è stata riavviata nelle ultime 24 ore e numero di riavvii<br>
    **Query affiancata:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Definire le **proprietà dell'elenco.**<br>
    **Query elenco:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Definire **i titoli delle colonne.**<br>
    **Nome:** Nome computer<br>
    **Valore:** Numero di riavvii
6.  Definire **una query di spostamento.**<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Selezionare **Applica** e quindi **Chiudi.**
8.  Selezionare **Salva** per salvare il dashboard.

La creazione delle visualizzazioni è stata completata.

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>Configura avvisi in :::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor"::: può generare avvisi per avvisare gli amministratori quando si verifica :::no-loc text="Microsoft Teams Rooms"::: un problema con una console.

:::no-loc text="Azure Monitor"::: include un meccanismo di avviso incorporato che viene eseguito attraverso ricerche nel log pianificate a intervalli regolari. Se i risultati della ricerca nel log corrispondono ad alcuni criteri specifici, viene creato un record di avviso.

La regola può quindi eseguire automaticamente una o più azioni per inviare in modo proattivo una notifica dell'avviso o richiamare un altro processo. Le possibili opzioni per gli avvisi sono:
-   Invio di un messaggio di posta elettronica
-   Richiamo di un processo esterno tramite una richiesta HTTP POST
-   Avvio di un runbook nel :::no-loc text="Azure Automation"::: servizio

Per [altre :::no-loc text="Azure Monitor"::: informazioni sugli avvisi,](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) vedere Accedere agli avvisi in :::no-loc text="Azure Monitor"::: .

> [!NOTE]
> Gli esempi seguenti inviano avvisi tramite posta elettronica quando :::no-loc text="Microsoft Teams Rooms"::: un dispositivo genera un errore hardware o di un'applicazione.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>Configurare un avviso tramite posta elettronica per problemi :::no-loc text="Microsoft Teams Rooms"::: hardware

Configurare una regola di avviso per il controllo della presenza di dispositivi che hanno riscontrato problemi :::no-loc text="Microsoft Teams Rooms"::: hardware nell'ultima ora.
1.  Accedere al portale e [ :::no-loc text="Microsoft Azure"::: passare](https://portal.azure.com) all'area di :::no-loc text="Log Analytics"::: lavoro e selezionarla.

2. Passare :::no-loc text="Log Analytics"::: all'area di lavoro e selezionare **Avvisi** e quindi selezionare Nuova regola **di avviso**

3. Selezionare **Aggiungi condizione** e quindi Ricerca log **personalizzata**

4.  Immettere la query seguente nella casella di testo della query di ricerca.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  Configurare le impostazioni della logica di avviso:<br>
    **In base a:** Numero di risultati<br>
    **Condizione:** Maggiore di<br>
    **Soglia:** 0<br>

6. Configurare le impostazioni di valutazione e selezionare **Fatto:** <br>
    **Periodo (in minuti):** 60<br>
    **Frequenza (in minuti):** 60<br>

7. Configurare gruppi di azioni:
    1.  Selezionare **Crea nuovo**
    2.  Specificare nomi adatti per i *campi Nome gruppo di* azioni e Nome *breve.*
    3.  Specificare un nome *di azione univoco* e **selezionare E-mail/SMS/Push/Voice,** quindi **selezionare Modifica dettagli.**
    4.  Selezionare la **casella di** controllo Posta elettronica e specificare l'indirizzo di posta elettronica della persona o del gruppo che riceverà gli avvisi.
    5.  Puoi anche fornire il tuo numero di telefono per ricevere una notifica tramite SMS, una chiamata vocale o entrambi.
    6. Scegliere **OK.**

8. **Personalizzare le azioni** se si desidera ignorare la riga dell'oggetto dei messaggi di avviso.

9. Specificare il nome e la descrizione di una regola.<br>
    **Nome regola:** :::no-loc text="Microsoft Teams Rooms"::: Avviso di errore hardware<br>
    **Descrizione:** Elenco dei dispositivi che hanno riscontrato un problema hardware nell'ultima ora<br>

10. Selezionare il livello di gravità previsto e assicurarsi che la regola sia abilitata.

11. Selezionare **Crea regola di avviso.**

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a>Configurare un avviso tramite posta elettronica per i :::no-loc text="Microsoft Teams Rooms"::: problemi dell'applicazione

Ripetere la stessa procedura, ma usare la query seguente per elencare i dispositivi che hanno riscontrato problemi di applicazione nell'ultima ora.

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

La definizione degli avvisi è stata completata. È possibile definire altri avvisi usando gli esempi precedenti.

Quando viene generato un avviso, si ottiene un messaggio di posta elettronica che elenca i dispositivi che hanno rilevato un problema nell'ultima ora.

! [Messaggio :::no-loc text="Azure Monitor"::: e-mail di avviso di esempio](.. /media/Deploy-Azure-Monitor-6.png "Messaggio :::no-loc text="Azure Monitor"::: e-mail di avviso di esempio")

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>Configura tutti i dispositivi per :::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"></a> Dopo aver configurato i dashboard e gli avvisi, è possibile configurare l'agente in tutti i dispositivi per :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: completare la distribuzione di monitoraggio.

Anche se è possibile installare e configurare manualmente l'agente in ogni dispositivo, è consigliabile usare i metodi e :::no-loc text="Microsoft Monitoring"::: gli strumenti di distribuzione del software esistenti.

Se si stanno creando i dispositivi per la prima volta, è consigliabile includere i passaggi di configurazione e configurazione dell'agente come parte del :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Microsoft Monitoring"::: processo di build. Per altre informazioni, vedere [Installare l'agente dalla riga di comando.](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line)

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>Distribuzione :::no-loc text="Microsoft Monitoring"::: dell'agente tramite un oggetto Criteri di gruppo

Se i dispositivi sono già stati distribuiti prima dell'implementazione, è possibile usare lo script fornito per configurare e configurare gli agenti :::no-loc text="Microsoft Teams Rooms"::: usando oggetti Criteri di :::no-loc text="Azure Monitoring"::: :::no-loc text="Active Directory"::: gruppo.

1.  Creare un percorso di rete condiviso e concedere l'accesso in lettura al **gruppo Domain Computers.**

2.  Scarica la versione a 64 bit :::no-loc text="Microsoft Monitoring"::: dell'agente :::no-loc text="Windows"::: da <https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Estrarre il contenuto del pacchetto di configurazione nella condivisione di rete.
    1.  Aprire una finestra del prompt dei comandi e quindi eseguire **MMASetup-AMD64.exe /c**
    2.  Specificare la condivisione appena creata ed estrarre il contenuto.

4.  Creare un nuovo oggetto Criteri di gruppo e assegnarlo all'unità organizzativa in cui si trovano :::no-loc text="Microsoft Teams Rooms"::: gli account computer.

5.  Configurare i criteri di esecuzione di PowerShell:
    1.  Modificare l'oggetto Criteri di gruppo appena creato e passare ai componenti dei modelli amministrativi di \\ Criteri \\ di configurazione \\ :::no-loc text="Windows"::: computer \\:::no-loc text="Windows PowerShell":::
    2.  Abilitare **l'attivazione dell'esecuzione di script** e impostare **i criteri di** esecuzione in modo da consentire gli script **locali.**

6.  Configurare lo script di avvio:
    1.  Copiare lo script seguente e salvarlo come Install-MMAgent.ps1.
    2.  Modificare i parametri WorkspaceId, WorkspaceKey e SetupPath in base alla configurazione.
    3.  Modificare lo stesso oggetto Criteri di gruppo e passare agli script delle impostazioni dei criteri di configurazione del computer \\ \\ :::no-loc text="Windows"::: \\ (avvio/arresto)
    4.  Fare doppio clic per selezionare **Avvio,** quindi selezionare **Script di PowerShell.**
    5.  Selezionare **Mostra file** e quindi copiareInstall-MMAgent.ps1file nella cartella. 
    6.  Selezionare **Aggiungi,** quindi **Sfoglia.**
    7.  Selezionare lo script ps1 appena copiato.

7.  :::no-loc text="Microsoft Teams Rooms"::: dispositivi dovrebbero installare e configurare :::no-loc text="Microsoft Monitoring"::: l'agente con il secondo riavvio.

```PowerShell
# Install-MMAgent.ps1
<#
Date:        04/20/2018
Script:      Install-MMAgent.ps1
Version:     1.0
#>

# Set the parameters
$WorkspaceId = "<your workspace id>"
$WorkspaceKey = "<your workspace key>"
$SetupPath = "\\Server\Share"

$SetupParameters = "/qn NOAPM=1 ADD_OPINSIGHTS_WORKSPACE=1 OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE=0 OPINSIGHTS_WORKSPACE_ID=$WorkspaceId OPINSIGHTS_WORKSPACE_KEY=$WorkspaceKey AcceptEndUserLicenseAgreement=1"

# $SetupParameters = $SetupParameters + " OPINSIGHTS_PROXY_URL=<Proxy server URL> OPINSIGHTS_PROXY_USERNAME=<Proxy server username> OPINSIGHTS_PROXY_PASSWORD=<Proxy server password>"

# Start PowerShell logging
Start-Transcript -Path C:\Temp\MMA-Install.Log

# Check if the Microsoft Monitoring Agent is installed
$mma = New-Object -ComObject 'AgentConfigManager.MgmtSvcCfg'

# Check if the Microsoft Monitoring agent is installed
if (!$mma)
{
    #Install agent
    Start-Process -FilePath "$SetupPath\Setup.exe" -ArgumentList $SetupParameters -ErrorAction Stop -Wait
}

# Check if the agent has a valid configuration
$CheckMMA = $mma.GetCloudWorkspace($WorkspaceId).AgentId
if (!$CheckMMA)
{
    # Apply new configuration
    $mma.AddCloudWorkspace($WorkspaceId, $WorkspaceKey)
    $mma.ReloadConfiguration()
}

Stop-Transcript
```

> [!NOTE]
> È possibile vedere [ :::no-loc text="Log Analytics"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) l'articolo Gestione e gestione dell'agente quando è necessario riconfigurare un agente, spostarlo in un'area di lavoro diversa o modificare le impostazioni del proxy dopo l'installazione iniziale.

## <a name="additional-solutions"></a>Altre soluzioni
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor"::: fornisce soluzioni di gestione incorporate tramite la [raccolta](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) soluzioni per monitorare ulteriormente l'ambiente. È consigliabile aggiungere soluzioni di gestione degli [avvisi](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution) e integrità [ :::no-loc text="Azure Log Analytics"::: dell'agente](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth) anche all'area di lavoro.

> [!NOTE]
> La soluzione Integrità agente consente di identificare gli agenti obsoleti o interrotti all'interno dell'ambiente e la soluzione gestione degli avvisi fornisce dettagli sugli avvisi generati in un :::no-loc text="Microsoft Monitoring"::: determinato periodo.

## <a name="see-also"></a>Vedere anche

[Pianificare :::no-loc text="Microsoft Teams Rooms"::: la gestione con :::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[Gestisci :::no-loc text="Microsoft Teams Rooms"::: dispositivi con :::no-loc text="Azure Monitor":::](azure-monitor-manage.md)
