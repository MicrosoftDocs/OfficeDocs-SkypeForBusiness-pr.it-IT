---
title: Distribuire Gestione di Microsoft teams Rooms con Azure monitor
ms.author: v-lanac
author: lanachin
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: Questo articolo illustra come distribuire la gestione dei dispositivi Microsoft teams rooms in modo integrato e completo con Azure monitor.
ms.openlocfilehash: 12936113a951f90bb1a3bed72f71d09f1f72ccd9
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569941"
---
# <a name="deploy-microsoft-teams-rooms-management-with-azure-monitor"></a>Distribuire Gestione di Microsoft teams Rooms con Azure monitor

Questo articolo illustra come configurare e distribuire la gestione integrata e end-to-end dei dispositivi Microsoft teams Rooms usando Azure monitor.

È possibile configurare l'analisi del log in Azure monitor per fornire la telemetria di base e gli avvisi che consentono di gestire i dispositivi della sala riunioni di Microsoft teams rooms. Man mano che la soluzione di gestione è matura, è possibile decidere di distribuire altre funzionalità di gestione e dati per creare una visualizzazione più dettagliata della disponibilità e delle prestazioni dei dispositivi.

Seguendo questa guida, è possibile usare un dashboard come l'esempio seguente per ottenere report di stato dettagliati per la disponibilità dei dispositivi, l'integrità dell'applicazione e dell'hardware e la distribuzione delle versioni dell'applicazione e del sistema operativo Microsoft teams rooms.

![Screenshot della visualizzazione analisi log di esempio per le sale di Microsoft Teams](../media/Deploy-Azure-Monitor-1.png "Visualizzazione analisi log di esempio per Microsoft teams rooms")

A livello elevato, è necessario eseguire le attività seguenti:


1. [Convalida configurazione analisi log](azure-monitor-deploy.md#validate_LogAnalytics)
2. [Configurare i dispositivi di test per la configurazione di gestione analisi log](azure-monitor-deploy.md#configure_test_devices)
3. [Mappare i campi personalizzati](azure-monitor-deploy.md#Custom_fields)
4. [Definire le visualizzazioni delle sale di Microsoft teams in analisi log](azure-monitor-deploy.md#Define_Views)
5. [Definire gli avvisi](azure-monitor-deploy.md#Alerts)
6. [Configurare tutti i dispositivi per il monitoraggio](azure-monitor-deploy.md#configure_all_devices)
7. [Configurare altre soluzioni di Azure monitor](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> Anche se con una configurazione minima, l'analisi dei log di Azure monitor può monitorare un computer che esegue un sistema operativo Windows, ci sono ancora alcune sale di Microsoft teams: passaggi specifici che è necessario eseguire prima di avviare la distribuzione di agenti in tutti i Microsoft Teams Dispositivi rooms.
> Per questo motivo, ti consigliamo vivamente di eseguire tutti i passaggi di configurazione nell'ordine corretto per una configurazione e un'impostazione controllate. La qualità del risultato finale dipende molto dalla qualità della configurazione iniziale.

## <a name="validate-log-analytics-configuration"></a>Convalida configurazione analisi log
<a name="validate_LogAnalytics"> </a>

È necessario disporre di un'area di lavoro analisi log per iniziare a raccogliere i log dai dispositivi Microsoft teams rooms. Un'area di lavoro è un ambiente di analisi del log univoco con il proprio archivio dati, origini dati e soluzioni. Se si dispone già di un'area di lavoro analisi log esistente, è possibile usarla per monitorare la distribuzione di Microsoft teams rooms o, in alternativa, per creare un'area di lavoro di analisi del log dedicata specifica delle esigenze di monitoraggio delle sale di Microsoft teams.

Se è necessario creare una nuova area di lavoro analisi log, seguire le istruzioni dell'articolo [creare un'area di lavoro analisi log in Azure Portal](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)

> [!NOTE]
> Per usare log Analytics con Azure monitor, è necessario avere un abbonamento a Azure attivo. Se non si ha un abbonamento a Azure, è possibile creare [un abbonamento di valutazione gratuito](https://azure.microsoft.com/free) come punto di partenza.

### <a name="configure-log-analytics-to-collect-microsoft-teams-rooms-event-logs"></a>Configurare l'analisi del log per raccogliere i registri eventi di Microsoft teams rooms

Analisi log raccoglie solo gli eventi dai registri eventi di Windows specificati nelle impostazioni. Per ogni log, vengono raccolti solo gli eventi con i severi selezionati.

È necessario configurare log Analytics per raccogliere i log necessari per monitorare lo stato delle applicazioni e del dispositivo Microsoft teams rooms. I dispositivi Microsoft teams Rooms usano il registro eventi di **sistema room Skype** .

Per configurare l'analisi del log per raccogliere gli eventi di Microsoft teams rooms, vedere [origini dati del log eventi di Windows in Azure monitor](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)

![Screenshot delle impostazioni del log eventi](../media/Deploy-Azure-Monitor-2.png "Impostazioni del log eventi")

> [!IMPORTANT]
> Configurare le impostazioni del log eventi di Windows e immettere **Skype room System** come nome del log eventi e quindi selezionare le caselle di controllo **errore**, **avviso**e **informazioni** .

## <a name="configure-test-devices-for-azure-monitoring"></a>Configurare i dispositivi di test per il monitoraggio di Azure
<a name="configure_test_devices"> </a>

Per poter monitorare gli eventi correlati a Microsoft teams, è necessario preparare log Analytics. Per iniziare, è necessario distribuire gli agenti di monitoraggio Microsoft in uno o due dispositivi Microsoft teams Rooms a cui si ha accesso fisico e ottenere questi dispositivi di test per generare alcuni dati e spingerli nell'area di lavoro analisi log.

### <a name="install-microsoft-monitoring-agents-to-test-devices"></a>Installare gli agenti di monitoraggio Microsoft per testare i dispositivi

Distribuire l'agente di monitoraggio Microsoft nei dispositivi di test usando le istruzioni fornite in [connettere i computer Windows al servizio analisi log in Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows). Questo articolo fornisce informazioni dettagliate sui passaggi per la distribuzione di Microsoft Monitoring Agent per Windows, le istruzioni per ottenere l' ***ID del Workspace*** log Analytics e la ***chiave primaria*** per ottenere i dispositivi di Microsoft teams Rooms connessi la distribuzione di Azure monitor e i passaggi per verificare la connettività dell'agente all'istanza di analisi del log.

### <a name="generate-sample-microsoft-teams-rooms-events"></a>Generazione di esempi di eventi di Microsoft teams rooms

Dopo aver distribuito l'agente di monitoraggio Microsoft sui dispositivi di test, verificare che i dati del log eventi necessari vengano raccolti da Azure monitor.

> [!NOTE]
> Riavviare il dispositivo dopo l'installazione dell'agente di monitoraggio Microsoft e verificare che l'app riunione Microsoft teams rooms sia avviata, in modo che possa generare nuovi eventi nel log eventi.

1.  Accedere a [Microsoft Azure Portal](https://portal.azure.com) e accedere a log Analytics e selezionare l'area di lavoro.

2.  Elencare gli eventi heartbeat generati da un dispositivo Microsoft teams Rooms:
    1.  Selezionare l'area di lavoro e accedere ai **registri** e usare una query per recuperare i record heartbeat che avranno i campi personalizzati per le sale di Microsoft teams.
    2.  Query di esempio:`Event | where Source == "SRS-App" and EventID == 2000`

3.  Verificare che la query restituisca i record di log che includono gli eventi generati dall'app riunioni di Microsoft teams rooms.

4.  Generare un problema hardware e verificare che gli eventi necessari vengano registrati in analisi log di Azure.
    1.  Scollegare uno dei dispositivi periferici nel sistema test Microsoft teams rooms. Potrebbe essere la fotocamera, il vivavoce, il microfono o la visualizzazione della sala anteriore
    2.  Attendere 10 minuti prima che il log eventi venga popolato in analisi log di Azure.
    3.  Usare una query per elencare gli eventi di errore hardware:`Event | where Source == "SRS-App" and EventID == 3001`

5.  Generare un problema di applicazione e verificare che gli eventi necessari vengano registrati.
    1.  Modificare la configurazione dell'applicazione Microsoft teams Rooms e digitare un indirizzo SIP (Session Initiation Protocol) non corretto o una coppia di password.
    2.  Attendere 10 minuti prima che il log eventi venga popolato in analisi log di Azure.
    3.  Usare una query per elencare gli eventi di errore dell'applicazione:`Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Questi registri eventi di esempio sono necessari prima che i campi personalizzati possano essere configurati. Non procedere al passaggio successivo finché non vengono raccolti i registri eventi necessari.

## <a name="map-custom-fields"></a>Mappare i campi personalizzati
<a name="Custom_fields"> </a>

Si usano campi personalizzati per estrarre dati specifici dai registri eventi. È necessario definire i campi personalizzati che verranno usati in seguito con i riquadri, le visualizzazioni dashboard e gli avvisi. Vedere [campi personalizzati in analisi log](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) e acquisire familiarità con i concetti prima di iniziare a creare i campi personalizzati.

Per estrarre i campi personalizzati dai registri eventi acquisiti, eseguire le operazioni seguenti:

1.  Accedere a [Microsoft Azure Portal](https://portal.azure.com) e accedere a log Analytics e selezionare l'area di lavoro.

2. Elencare gli eventi generati da un dispositivo Microsoft teams Rooms:
   1.  Accedere a **log** e usare una query per recuperare i record che avranno il campo personalizzato.
   2.  Query di esempio:`Event | where Source == "SRS-App" and EventID == 2000`

3. Selezionare uno dei record, selezionare il pulsante a sinistra e avviare l'estrazione guidata campi.
4. Evidenziare i dati che si desidera estrarre da RenderedDescription e specificare un titolo di campo. I nomi dei campi da usare sono forniti nella tabella 1.

   ![Definizione di campo personalizzato](../media/Deploy-Azure-Monitor-4.png "Definizione di campo personalizzato")

5. Usare i mapping visualizzati nella *tabella 1*. Analisi log aggiungerà automaticamente la ** \_stringa CF** quando si definisce il nuovo campo.

> [!IMPORTANT]
> Tenere presente che tutti i campi di analisi JSON e log sono con distinzione tra maiuscole e minuscole.
> 
> Prestare attenzione alle query necessarie per ogni campo personalizzato nella tabella seguente. Per estrarre correttamente i valori dei campi personalizzati, è necessario usare le query corrette per l'analisi del log.
> 
 ![Definizione di campo personalizzato](../media/Deploy-Azure-Monitor-5.png "Definizione di campo personalizzato")

**Tabella 1**

| **Campo JSON**                   | **Campo personalizzato analisi log** | **ID evento** | **Query da usare con l'estrazione**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| Descrizione                      | SRSEventDescription         | **2000**     | Evento \| where source = = "SRS-app" e EventID = = 2000 |
| ResourceState                    | SRSResourceState            | **2000**     | Evento \| where source = = "SRS-app" e EventID = = 2000 |
| NomeOperazione                    | SRSOperationName            | **2000**     | Evento \| where source = = "SRS-app" e EventID = = 2000 |
| OperationResult                  | SRSOperationResult          | **2000**     | Evento \| where source = = "SRS-app" e EventID = = 2000 |
| OS                               | SRSOSVersion                | **2000**     | Evento \| where source = = "SRS-app" e EventID = = 2000 |
| OSVersion                        | SRSOSLongVersion            | **2000**     | Evento \| where source = = "SRS-app" e EventID = = 2000 |
| Alias                            | SRSAlias                    | **2000**     | Evento \| where source = = "SRS-app" e EventID = = 2000 |
| DisplayName                      | SRSDisplayName              | **2000**     | Evento \| where source = = "SRS-app" e EventID = = 2000 |
| AppVersion                       | SRSAppVersion               | **2000**     | Evento \| where source = = "SRS-app" e EventID = = 2000 |
| Indirizzoipv4                      | SRSIPv4Address              | **2000**     | Evento \| where source = = "SRS-app" e EventID = = 2000 |
| Indirizzoipv6                      | SRSIPv6Address              | **2000**     | Evento \| where source = = "SRS-app" e EventID = = 2000 |
| Stato microfono conferenza     | SRSConfMicrophoneStatus     | **3001**     | Evento \| where source = = "SRS-app" e EventID = = 3001 |
| Stato altoparlante conferenza        | SRSConfSpeakerStatus        | **3001**     | Evento \| where source = = "SRS-app" e EventID = = 3001 |
| Stato altoparlante predefinito           | SRSDefaultSpeakerStatus     | **3001**     | Evento \| where source = = "SRS-app" e EventID = = 3001 |
| Stato fotocamera                    | SRSCameraStatus             | **3001**     | Evento \| where source = = "SRS-app" e EventID = = 3001 |
| Inizio dello stato di visualizzazione della sala     | SRSFORDStatus               | **3001**     | Evento \| where source = = "SRS-app" e EventID = = 3001 |
| Stato sensore movimento             | SRSMotionSensorStatus       | **3001**     | Evento \| where source = = "SRS-app" e EventID = = 3001 |
| Stato di ingestione HDMI               | SRSHDMIIngestStatus         | **3001**     | Evento \| where source = = "SRS-app" e EventID = = 3001 |


## <a name="define-the-microsoft-teams-rooms-views-in-log-analytics"></a>Definire le visualizzazioni delle sale di Microsoft teams in analisi log
<a name="Define_Views"> </a>

Dopo la raccolta dei dati e i campi personalizzati, è possibile usare la finestra di progettazione di visualizzazione per sviluppare un dashboard contenente vari riquadri per monitorare gli eventi di Microsoft teams rooms. Usare la finestra di progettazione di visualizzazione per creare i riquadri seguenti. Per altre informazioni, vedere [creare visualizzazioni personalizzate tramite la finestra di progettazione di visualizzazione in analisi log](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> I passaggi precedenti di questa guida devono essere stati completati per il corretto funzionamento dei riquadri del dashboard.

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a>Creare un dashboard di Microsoft teams Rooms usando il metodo Import

È possibile importare un dashboard di Microsoft teams Rooms e avviare il monitoraggio rapido dei dispositivi. Eseguire la procedura seguente per importare il Dashboard:

1.  Ottenere il file del dashboard di [SkypeRoomSystems_v2. omsview](https://go.microsoft.com/fwlink/?linkid=835675) .
2.  Accedere a [Microsoft Azure Portal](https://portal.azure.com) e accedere a log Analytics e selezionare l'area di lavoro.
3.  Aprire **Progettazione visualizzazioni**.
4.  Selezionare **Importa**e quindi selezionare il file **SkypeRoomSystems_v2. omsview** .
5.  Selezionare **Salva**.

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Creare manualmente un dashboard di Microsoft teams rooms

In alternativa, è possibile creare un dashboard personalizzato e aggiungere solo i riquadri che si desidera monitorare.

#### <a name="configure-the-overview-tile"></a>Configurare il riquadro Panoramica

1.  Aprire **Progettazione visualizzazioni**.
2.  Selezionare **riquadro Panoramica**e quindi selezionare **due numeri** dalla raccolta.
3.  Assegnare un nome al riquadro **Microsoft teams Rooms**.
4.  Definire il **primo riquadro**:<br>
    **Legenda:** Dispositivi che hanno inviato un battito cardiaco almeno una volta nell'ultimo mese<br>
    **Query:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Definire il **secondo riquadro**:<br>
    **Legenda:** Dispositivi attivi che hanno inviato un battito cardiaco nell'ultima ora<br>
    **Query:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Selezionare **applica**.

### <a name="create-a-tile-that-displays-active-devices"></a>Creare un riquadro in cui sono visualizzati i dispositivi attivi

1.  Selezionare **Visualizza dashboard** per iniziare ad aggiungere i riquadri.
2.  Selezionare **numero & elenco** nella raccolta
3.  Definire le proprietà **generali** :<br>
    **Titolo del gruppo:** Stato heartbeat<br>
    **Nuovo gruppo:** Selezionato
4.  Definire le proprietà del **riquadro** :<br>
    **Legenda:** Dispositivi attivi (heartbeat inviato negli ultimi 20 minuti)<br>
    **Query riquadro:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Definire le proprietà dell' **elenco** :<br>
    **Query di elenco:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Definire i **titoli di colonna**:<br>
    **Nome:** Nome computer<br>
    **Valore:** Ultimo heartbeat
7.  Definire la **query di spostamento**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Selezionare **applica**e quindi **Chiudi**.

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Creare un riquadro in cui vengono visualizzati i dispositivi con problemi di connettività

1.  Selezionare **numero & elenco** nella raccolta e quindi aggiungere un nuovo riquadro.
2.  Definire le proprietà **generali** :<br>
    **Titolo del gruppo:** Lascia vuoto<br>
    **Nuovo gruppo:** Non selezionato
3.  Definire le proprietà del **riquadro** :<br>
    **Legenda:** Dispositivi inattivi (nessun messaggio di heartbeat inviato negli ultimi 20 minuti)<br>
    **Query riquadro:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Definire le proprietà dell' **elenco** :<br>
    **Query di elenco:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Definire i **titoli di colonna**:<br>
    **Nome:** Nome computer<br>
    **Valore:** Ultimo heartbeat
6.  Definire la **query di spostamento**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Selezionare **applica**e quindi **Chiudi**.

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Creare un riquadro in cui sono visualizzati dispositivi con un errore hardware

1.  Selezionare **numero & elenco** nella raccolta e quindi aggiungere un nuovo riquadro.
2.  Definire le proprietà **generali** :<br>
    **Titolo del gruppo:** Stato hardware<br>
    **Nuovo gruppo:** Selezionato
3.  Definire le proprietà del **riquadro** :<br>
    **Legenda:** Dispositivi che hanno registrato un errore hardware nell'ultima ora<br>
    **Query riquadro:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Definire le proprietà dell' **elenco** :<br>
    **Query di elenco:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definire i **titoli di colonna**:<br>
    **Nome:** Nome computer<br>
    **Valore:** Ultimo errore
6.  Definire la **query di spostamento**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Selezionare **applica**e quindi **Chiudi**.

### <a name="create-a-tile-that-displays-microsoft-teams-rooms-operating-system-versions"></a>Creare un riquadro in cui sono visualizzate le versioni del sistema operativo Microsoft teams rooms

1.  Selezionare **elenco & ciambella** nella raccolta e quindi aggiungere un nuovo riquadro.
2.  Definire le proprietà **generali** :<br>
    **Titolo del gruppo:** Dettagli del sistema operativo<br>
    **Nuovo gruppo:** Selezionato
3.  Definire le proprietà dell' **intestazione** :<br>
    **Titolo:** Versioni del sistema operativo<br>
    **Sottotitoli:** Dispositivi con versioni specifiche del sistema operativo
4.  Definire le proprietà della **ciambella** :<br>
    **Query:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **Testo centrale:** Dispositivi<br>
    **Operazione:** Somma
5.  Definire le proprietà dell' **elenco** .<br>
    **Query di elenco:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **Nascondi grafico:** Selezionato<br>
    **Abilitare i grafici sparkline:** Non selezionato
6.  Definire i **titoli di colonna**.<br>
    **Nome:** Nome computer<br>
    **Valore:** Lascia vuoto
7.  Definire la **query di spostamento**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Selezionare **applica** e quindi **Chiudi**.

### <a name="create-a-tile-that-displays-microsoft-teams-rooms-application-versions"></a>Creare un riquadro che visualizza le versioni delle applicazioni di Microsoft teams rooms

1.  Selezionare **elenco & ciambella** nella raccolta e quindi aggiungere un nuovo riquadro.
2.  Definire le proprietà **generali** :<br>
    **Titolo del gruppo:** Dettagli dell'applicazione Microsoft teams rooms<br>
    **Nuovo gruppo:** Selezionato
3.  Definire le proprietà dell' **intestazione** :<br>
    **Titolo:** Versioni delle applicazioni<br>
    **Sottotitoli:** Dispositivi che gestiscono versioni specifiche delle applicazioni
4.  Definire le proprietà della **ciambella** :<br>
    **Query:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **Testo centrale:** Dispositivi<br>
    **Operazione:** Somma
5.  Definire le proprietà dell' **elenco** .<br>
    **Query di elenco:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **Nascondi grafico:** Selezionato<br>
    **Abilitare i grafici sparkline:** Non selezionato
6.  Definire i **titoli di colonna**.<br>
    **Nome:** Nome computer<br>
    **Valore:** Lascia vuoto
7.  Definire la **query di spostamento**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Selezionare **applica** e quindi **Chiudi**.

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Creare un riquadro in cui vengono visualizzati i dispositivi con un errore di applicazione

1.  Selezionare **numero & elenco** nella raccolta e quindi aggiungere un nuovo riquadro.
2.  Definire le proprietà **generali** .<br>
    **Titolo del gruppo:** Lascia vuoto<br>
    **Nuovo gruppo:** Non selezionato
3.  Definire le proprietà del **riquadro** .<br>
    **Legenda:** Dispositivi con un errore di applicazione nell'ultima ora<br>
    **Query riquadro:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Definire le proprietà dell' **elenco** .<br>
    **Query di elenco:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definire i **titoli di colonna**.<br>
    **Nome:** Nome computer<br>
    **Valore:** Ultimo errore
6.  Definire la **query di spostamento**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Selezionare **applica** e quindi **Chiudi**.

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Creare un riquadro in cui sono visualizzati i dispositivi riavviati

1.  Selezionare **numero & elenco** nella raccolta e quindi aggiungere un nuovo riquadro.
2.  Definire le proprietà **generali** .<br>
    **Titolo del gruppo:** Lascia vuoto<br>
    **Nuovo gruppo:** Non selezionato
3.  Definire le proprietà del **riquadro** .<br>
    **Legenda:** Dispositivi in cui l'applicazione è stata riavviata nelle ultime 24 ore e numero di riavvii<br>
    **Query riquadro:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Definire le proprietà dell' **elenco** .<br>
    **Query di elenco:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Definire i **titoli di colonna**.<br>
    **Nome:** Nome computer<br>
    **Valore:** Numero di riavvii
6.  Definire la **query di spostamento**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Selezionare **applica** e quindi **Chiudi**.
8.  Selezionare **Salva** per salvare il dashboard.

Ora hai completato la creazione delle visualizzazioni.

## <a name="configure-alerts-in-azure-monitor"></a>Configurare gli avvisi in Azure monitor
<a name="Alerts"> </a>

Azure monitor può generare avvisi per avvisare gli amministratori quando una console di Microsoft teams Rooms incontra un problema.

Azure Monitor include un meccanismo di avviso incorporato che viene eseguito tramite ricerche di log pianificate a intervalli regolari. Se i risultati della ricerca del log corrispondono a determinati criteri specifici, viene creato un record di avviso.

La regola può quindi eseguire automaticamente una o più azioni per avvisare in modo proattivo l'avviso o richiamare un altro processo. Le opzioni possibili con gli avvisi sono:
-   Invio di un messaggio di posta elettronica
-   Richiamo di un processo esterno tramite una richiesta POST HTTP
-   Avvio di un Runbook nel servizio di automazione di Azure

Per altre informazioni sugli avvisi in Azure monitor, vedere [registrare gli avvisi in Azure monitor](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) .

> [!NOTE]
> Gli esempi seguenti inviano avvisi tramite posta elettronica quando un dispositivo Microsoft teams Rooms genera un errore hardware o di un'applicazione.

### <a name="configure-an-email-alert-for-microsoft-teams-rooms-hardware-issues"></a>Configurare un avviso di posta elettronica per problemi hardware di Microsoft teams rooms

Configurare una regola di avviso che controlli i dispositivi Microsoft teams Rooms che hanno riscontrato problemi hardware nell'ultima ora.
1.  Accedere a [Microsoft Azure Portal](https://portal.azure.com) e accedere a log Analytics e selezionare l'area di lavoro.

2. Passare all'area di lavoro analisi log e selezionare **avvisi** e quindi **nuova regola di avviso**

3. Selezionare **Aggiungi condizione** e quindi **Ricerca log personalizzata**

4.  Immettere la query seguente nella casella di testo query di ricerca.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  Configurare le impostazioni della logica di avviso:<br>
    **Basato su:** Numero di risultati<br>
    **Condizione:** Maggiore di<br>
    **Soglia:** 0<br>

6. Configurare le impostazioni di valutazione e selezionare **fine**: <br>
    **Periodo (in minuti):** 60<br>
    **Frequenza (in minuti):** 60<br>

7. Configurare i gruppi di azioni:
    1.  Selezionare **Crea nuovo**
    2.  Specificare nomi appropriati per il *nome del gruppo di azioni* e i campi *nome breve* .
    3.  Specificare un *nome di azione* univoco e selezionare **posta elettronica/SMS/push/Voice**e quindi selezionare **Modifica dettagli**.
    4.  Selezionare la casella di controllo posta elettronica e specificare l'indirizzo di posta elettronica della persona o del gruppo che riceverà gli avvisi.
    5.  È anche possibile specificare il numero di telefono per ricevere una notifica tramite SMS, una chiamata vocale o entrambi.
    6. Selezionare **OK**.

8. **Personalizzare le azioni** se si vuole ignorare la riga dell'oggetto dei messaggi di posta elettronica di avviso.

9. Specificare un nome e una descrizione della regola.<br>
    **Nome regola:** Avviso di errore hardware di Microsoft teams rooms<br>
    **Descrizione:** Elenco dei dispositivi che hanno rilevato un problema hardware nell'ultima ora<br>

10. Selezionare la gravità desiderata e verificare che la regola sia abilitata.

11. Selezionare **Crea regola di avviso**.

### <a name="configure-an-email-alert-for-microsoft-teams-rooms-application-issues"></a>Configurare un avviso di posta elettronica per problemi di applicazione di Microsoft teams rooms

Ripetere la stessa procedura, ma usare la query seguente per elencare i dispositivi che hanno riscontrato problemi di applicazione nell'ultima ora.

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

Ora hai completato la definizione degli avvisi. Puoi definire altri avvisi usando gli esempi descritti sopra.

Quando viene generato un avviso, viene visualizzato un messaggio di posta elettronica che elenca i dispositivi che hanno rilevato un problema entro l'ultima ora.

![Esempio di messaggio di avviso di Azure monitor](../media/Deploy-Azure-Monitor-6.png "Esempio di messaggio di avviso di Azure monitor")

## <a name="configure-all-devices-for-azure-monitoring"></a>Configurare tutti i dispositivi per il monitoraggio di Azure
<a name="configure_all_devices"></a> Una volta configurati i dashboard e gli avvisi, è possibile impostare e configurare Microsoft Monitoring Agent in tutti i dispositivi Microsoft teams Rooms per completare la distribuzione del monitoraggio.

Anche se è possibile installare e configurare manualmente l'agente di monitoraggio Microsoft su ogni dispositivo, è consigliabile sfruttare gli strumenti e i metodi di distribuzione del software esistenti.

Se si stanno costruendo i dispositivi Microsoft teams Rooms per la prima volta, è consigliabile includere i passaggi di configurazione ed esecuzione dell'agente di monitoraggio Microsoft come parte del processo di compilazione. Per altre informazioni, vedere [installare l'agente tramite la riga di comando](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-microsoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>Distribuzione di agente di monitoraggio Microsoft tramite un oggetto Criteri di gruppo

Se sono già stati distribuiti i dispositivi di Microsoft teams Rooms prima di implementare il monitoraggio di Azure, è possibile usare lo script fornito per configurare gli agenti e configurarli usando gli oggetti Criteri di gruppo di Active Directory.

1.  Creare un percorso di rete condiviso e concedere l'accesso in lettura al gruppo **Domain Computers** .

2.  Scaricare la versione a 64 bit dell'agente di monitoraggio Microsoft per Windows da<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Estrarre il contenuto del pacchetto di installazione nella condivisione di rete.
    1.  Aprire una finestra del prompt dei comandi e quindi eseguire **MMASetup-amd64. exe/c**
    2.  Specifica la condivisione appena creata ed Estrai il contenuto.

4.  Creare un nuovo oggetto Criteri di gruppo e assegnarlo all'unità organizzativa in cui si trovano gli account del computer di Microsoft teams rooms.

5.  Configurare i criteri di esecuzione di PowerShell:
    1.  Modificare l'oggetto Criteri di gruppo appena creato e passare a criteri \\ \\ di configurazione del \\ computer modelli \\ amministrativi di Windows Components Windows PowerShell
    2.  Abilitare l' **esecuzione attiva dello script** e impostare i **criteri di esecuzione** per consentire gli **script locali**.

6.  Configurare lo script di avvio:
    1.  Copiare lo script seguente e salvarlo come Install-MMAgent. ps1.
    2.  Modificare i parametri WorkspaceId, WorkspaceKey e SetupPath in base alla configurazione.
    3.  Modificare lo stesso oggetto Criteri di gruppo e passare a criteri \\ \\ di configurazione del \\ computer script delle impostazioni di Windows (avvio/arresto)
    4.  Fare doppio clic per selezionare **avvio**e quindi selezionare **script di PowerShell**.
    5.  Selezionare **Mostra file**e quindi copiare il file **Install-mmagent. ps1** in tale cartella.
    6.  Selezionare **Aggiungi**e quindi **Sfoglia**.
    7.  Selezionare lo script ps1 appena copiato.

7.  I dispositivi Microsoft teams Rooms devono installare e configurare l'agente di monitoraggio Microsoft con il secondo riavvio.

```
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
> È possibile fare riferimento all'articolo [gestione e manutenzione dell'agente analisi log](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) quando è necessario riconfigurare un agente, spostarlo in un'area di lavoro diversa o modificare le impostazioni del proxy dopo l'installazione iniziale.

## <a name="additional-solutions"></a>Soluzioni aggiuntive
<a name="Solutions"> </a>

Azure monitor offre soluzioni di gestione predefinite tramite la [raccolta](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) soluzioni per aiutarti a monitorare ulteriormente l'ambiente. Ti consigliamo vivamente di aggiungere la [gestione degli avvisi](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution) e le soluzioni per [l'integrità dell'agente analisi di Azure log](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth) anche all'area di lavoro.

> [!NOTE]
> La soluzione per l'integrità dell'agente consente di identificare gli agenti di monitoraggio Microsoft obsoleti o interrotti all'interno dell'ambiente e la soluzione di gestione degli avvisi fornisce informazioni dettagliate sulle segnalazioni che sono state generate entro un determinato periodo.

## <a name="see-also"></a>Vedere anche

[Pianificare la gestione di Microsoft teams Rooms con Azure monitor](azure-monitor-plan.md)

[Gestire i dispositivi Microsoft teams Rooms con Azure monitor](azure-monitor-manage.md)
