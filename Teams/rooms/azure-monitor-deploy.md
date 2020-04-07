---
title: Distribuire Gestione di Microsoft teams Rooms con Azure monitor
ms.author: v-lanac
author: lanachin
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
description: Questo articolo illustra come distribuire la gestione dei dispositivi Microsoft teams rooms in modo integrato e completo con Azure monitor.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0e0e810bb2932918947a011a9d2091858d0819eb
ms.sourcegitcommit: 0fdc60840f45ff5b0a39a8ec4a21138f6cab49c9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/07/2020
ms.locfileid: "43160090"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-management-with-no-loc-textazure-monitor"></a>Distribuire :::no-loc text="Microsoft Teams Rooms"::: la gestione con:::no-loc text="Azure Monitor":::

Questo articolo illustra come configurare e distribuire la gestione integrata e end-to-end dei :::no-loc text="Microsoft Teams Rooms"::: dispositivi tramite. :::no-loc text="Azure Monitor":::

Puoi configurare :::no-loc text="Log Analytics"::: l'interno :::no-loc text="Azure Monitor"::: per fornire la telemetria di base e gli avvisi che :::no-loc text="Microsoft Teams Rooms"::: ti aiuteranno a gestire i dispositivi della sala riunioni. Man mano che la soluzione di gestione è matura, è possibile decidere di distribuire altre funzionalità di gestione e dati per creare una visualizzazione più dettagliata della disponibilità e delle prestazioni dei dispositivi.

Seguendo questa guida, è possibile usare un dashboard come l'esempio seguente per ottenere report di stato dettagliati per la disponibilità dei dispositivi, l'integrità dell' :::no-loc text="Microsoft Teams Rooms"::: applicazione e dell'hardware e la distribuzione delle versioni delle applicazioni e del sistema operativo.

![Screenshot della visualizzazione analisi log di esempio per Microsoft teams rooms](../media/Deploy-Azure-Monitor-1.png "Visualizzazione analisi log di esempio per Microsoft teams rooms")

A livello elevato, è necessario eseguire le attività seguenti:


1. [Convalidare :::no-loc text="Log Analytics"::: la configurazione](azure-monitor-deploy.md#validate_LogAnalytics)
2. [Configurare i dispositivi di :::no-loc text="Log Analytics"::: test per la configurazione della gestione](azure-monitor-deploy.md#configure_test_devices)
3. [Mappare i campi personalizzati](azure-monitor-deploy.md#Custom_fields)
4. [Definire le :::no-loc text="Microsoft Teams Rooms"::: visualizzazioni in:::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [Definire gli avvisi](azure-monitor-deploy.md#Alerts)
6. [Configurare tutti i dispositivi per il monitoraggio](azure-monitor-deploy.md#configure_all_devices)
7. [Configurare soluzioni :::no-loc text="Azure Monitor"::: aggiuntive](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> Anche se con una configurazione :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: minima, è possibile monitorare un :::no-loc text="Windows"::: computer che esegue un sistema operativo, :::no-loc text="Microsoft Teams Rooms":::ma è necessario eseguire alcuni passaggi specifici prima di iniziare la distribuzione di agenti in :::no-loc text="Microsoft Teams Rooms"::: tutti i dispositivi.
> Per questo motivo, ti consigliamo vivamente di eseguire tutti i passaggi di configurazione nell'ordine corretto per una configurazione e un'impostazione controllate. La qualità del risultato finale dipende molto dalla qualità della configurazione iniziale.

## <a name="validate-no-loc-textlog-analytics-configuration"></a>Convalidare :::no-loc text="Log Analytics"::: la configurazione
<a name="validate_LogAnalytics"> </a>

Per iniziare a raccogliere i :::no-loc text="Log Analytics"::: log dai :::no-loc text="Microsoft Teams Rooms"::: dispositivi, è necessario disporre di un'area di lavoro. Un'area di lavoro è :::no-loc text="Log Analytics"::: un ambiente univoco con il proprio archivio dati, origini dati e soluzioni. Se si dispone già di un' :::no-loc text="Log Analytics"::: area di lavoro esistente, è possibile usarla :::no-loc text="Microsoft Teams Rooms"::: per monitorare la distribuzione o, in alternativa, per :::no-loc text="Log Analytics"::: creare un'area di :::no-loc text="Microsoft Teams Rooms"::: lavoro dedicata specifica delle esigenze di monitoraggio.

Se è necessario creare una nuova :::no-loc text="Log Analytics"::: area di lavoro, seguire le istruzioni dell'articolo [creare un' :::no-loc text="Log Analytics"::: area di lavoro :::no-loc text="Azure"::: nel portale](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)

> [!NOTE]
> Per :::no-loc text="Log Analytics"::: usarlo :::no-loc text="Azure Monitor":::, è necessario avere un abbonamento attivo :::no-loc text="Azure"::: . Se non si dispone di :::no-loc text="Azure"::: un abbonamento, è possibile creare [un abbonamento di valutazione gratuito](https://azure.microsoft.com/free) come punto di partenza.

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>Configurare :::no-loc text="Log Analytics"::: per raccogliere :::no-loc text="Microsoft Teams Rooms"::: i log eventi

:::no-loc text="Log Analytics":::raccoglie solo gli eventi dai registri :::no-loc text="Windows"::: eventi specificati nelle impostazioni. Per ogni log, vengono raccolti solo gli eventi con i severi selezionati.

È necessario configurare :::no-loc text="Log Analytics"::: per raccogliere i log necessari per monitorare :::no-loc text="Microsoft Teams Rooms"::: lo stato del dispositivo e dell'applicazione. :::no-loc text="Microsoft Teams Rooms":::i dispositivi usano **:::no-loc text="Skype Room System":::** il log eventi.

Per configurare :::no-loc text="Log Analytics"::: la raccolta degli :::no-loc text="Microsoft Teams Rooms"::: eventi, vedere [ :::no-loc text="Windows"::: origini dati del log eventi :::no-loc text="Azure Monitor"::: in](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)

![Screenshot delle impostazioni del log eventi](../media/Deploy-Azure-Monitor-2.png "Impostazioni del log eventi")

> [!IMPORTANT]
> Configurare :::no-loc text="Windows"::: le impostazioni del log eventi **:::no-loc text="Skype Room System":::** e immettere il nome del log eventi e quindi selezionare le caselle di controllo **errore**, **avviso**e **informazioni** .

## <a name="configure-test-devices-for-azure-monitoring"></a>Configurare i dispositivi di test per il monitoraggio di Azure
<a name="configure_test_devices"> </a>

È necessario prepararsi :::no-loc text="Log Analytics"::: per poter monitorare :::no-loc text="Microsoft Teams Rooms":::gli eventi correlati. Per iniziare, è necessario distribuire :::no-loc text="Microsoft Monitoring"::: gli agenti in uno o due :::no-loc text="Microsoft Teams Rooms"::: dispositivi a cui si ha accesso fisico e ottenere quei dispositivi di test che generano alcuni dati e lo spingono all' :::no-loc text="Log Analytics"::: area di lavoro.

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>Installare :::no-loc text="Microsoft Monitoring"::: gli agenti per testare i dispositivi

Distribuire l' :::no-loc text="Microsoft Monitoring"::: agente nei dispositivi di test usando le istruzioni fornite in [connettere :::no-loc text="Windows"::: i computer al :::no-loc text="Log Analytics"::: servizio :::no-loc text="Azure"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows). In questo articolo vengono fornite informazioni dettagliate sui passaggi per :::no-loc text="Microsoft Monitoring"::: la distribuzione :::no-loc text="Windows":::dell'agente, le istruzioni :::no-loc text="Log Analytics"::: per ottenere l' ***ID area di lavoro*** e la ***chiave primaria*** per ottenere :::no-loc text="Microsoft Teams Rooms"::: i dispositivi connessi alla :::no-loc text="Azure Monitor"::: distribuzione e i passaggi :::no-loc text="Log Analytics"::: per verificare la connettività dell'agente all'istanza.

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>Generare eventi :::no-loc text="Microsoft Teams Rooms"::: di esempio

Dopo che :::no-loc text="Microsoft Monitoring"::: l'agente è stato distribuito sui dispositivi di test, verificare che i dati del log eventi necessari :::no-loc text="Azure Monitor":::vengano raccolti da.

> [!NOTE]
> Riavviare il dispositivo dopo l'installazione dell' :::no-loc text="Microsoft Monitoring"::: agente e verificare che :::no-loc text="Microsoft Teams Rooms"::: l'app riunione venga avviata, in modo che possa generare nuovi eventi nel log eventi.

1.  Accedere al [ :::no-loc text="Microsoft Azure"::: portale](https://portal.azure.com) e :::no-loc text="Log Analytics"::: selezionare l'area di lavoro.

2.  Elencare gli eventi heartbeat generati da :::no-loc text="Microsoft Teams Rooms"::: un dispositivo:
    1.  Selezionare l'area di lavoro e accedere ai **registri** e usare una query per recuperare i record heartbeat con i campi personalizzati :::no-loc text="Microsoft Teams Rooms":::.
    2.  Query di esempio:`Event | where Source == "SRS-App" and EventID == 2000`

3.  Verificare che la query restituisca i record di log che includono gli eventi :::no-loc text="Microsoft Teams Rooms"::: generati dall'app riunioni.

4.  Generare un problema hardware e verificare che gli eventi necessari siano connessi :::no-loc text="Azure Log Analytics":::.
    1.  Scollegare uno dei dispositivi periferici nel sistema di test :::no-loc text="Microsoft Teams Rooms"::: . Potrebbe essere la fotocamera, il vivavoce, il microfono o la visualizzazione della sala anteriore
    2.  Attendere 10 minuti per il popolamento del log eventi :::no-loc text="Azure Log Analytics":::.
    3.  Usare una query per elencare gli eventi di errore hardware:`Event | where Source == "SRS-App" and EventID == 3001`

5.  Generare un problema di applicazione e verificare che gli eventi necessari vengano registrati.
    1.  Modificare :::no-loc text="Microsoft Teams Rooms"::: la configurazione dell'applicazione e digitare un indirizzo SIP (Session Initiation Protocol) non corretto o una coppia di password.
    2.  Attendere 10 minuti per il popolamento del log eventi :::no-loc text="Azure Log Analytics":::.
    3.  Usare una query per elencare gli eventi di errore dell'applicazione:`Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Questi registri eventi di esempio sono necessari prima che i campi personalizzati possano essere configurati. Non procedere al passaggio successivo finché non vengono raccolti i registri eventi necessari.

## <a name="map-custom-fields"></a>Mappare i campi personalizzati
<a name="Custom_fields"> </a>

Si usano campi personalizzati per estrarre dati specifici dai registri eventi. È necessario definire i campi personalizzati che verranno usati in seguito con i riquadri, le visualizzazioni dashboard e gli avvisi. Vedere i [campi personalizzati :::no-loc text="Log Analytics"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) e acquisire familiarità con i concetti prima di iniziare a creare i campi personalizzati.

Per estrarre i campi personalizzati dai registri eventi acquisiti, eseguire le operazioni seguenti:

1.  Accedere al [ :::no-loc text="Microsoft Azure"::: portale](https://portal.azure.com) e :::no-loc text="Log Analytics"::: selezionare l'area di lavoro.

2. Elencare gli eventi generati da :::no-loc text="Microsoft Teams Rooms"::: un dispositivo:
   1.  Accedere a **log** e usare una query per recuperare i record che avranno il campo personalizzato.
   2.  Query di esempio:`Event | where Source == "SRS-App" and EventID == 2000`

3. Selezionare uno dei record, selezionare il pulsante a sinistra e avviare l'estrazione guidata campi.
4. Evidenziare i dati che si desidera estrarre da RenderedDescription e specificare un titolo di campo. I nomi dei campi da usare sono forniti nella tabella 1.

   ![Definizione di campo personalizzato](../media/Deploy-Azure-Monitor-4.png "Definizione di campo personalizzato")

5. Usare i mapping visualizzati nella *tabella 1*. :::no-loc text="Log Analytics":::verrà accodata automaticamente ** \_** la stringa CF quando si definisce il nuovo campo.

> [!IMPORTANT]
> Ricorda che tutti i campi :::no-loc text="Log Analytics"::: e i JSON sono con distinzione tra maiuscole e minuscole.
> 
> Prestare attenzione alle query necessarie per ogni campo personalizzato nella tabella seguente. È necessario usare le query corrette per :::no-loc text="Log Analytics"::: estrarre correttamente i valori dei campi personalizzati.
> 
 ![Definizione di campo personalizzato](../media/Deploy-Azure-Monitor-5.png "Definizione di campo personalizzato")

**Tabella 1**

| **Campo JSON**                   | **:::no-loc text="Log Analytics":::campo personalizzato** | **ID evento** | **Query da usare con l'estrazione**                   |
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


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>Definire le :::no-loc text="Microsoft Teams Rooms"::: visualizzazioni in:::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

Dopo la raccolta dei dati e i campi personalizzati, è possibile usare la finestra di progettazione di visualizzazione per sviluppare un dashboard contenente :::no-loc text="Microsoft Teams Rooms"::: diversi riquadri per monitorare gli eventi. Usare la finestra di progettazione di visualizzazione per creare i riquadri seguenti. Per altre informazioni, vedere [creare visualizzazioni personalizzate tramite la finestra di progettazione :::no-loc text="Log Analytics"::: di visualizzazione in](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> I passaggi precedenti di questa guida devono essere stati completati per il corretto funzionamento dei riquadri del dashboard.

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a>Creare un dashboard di Microsoft teams Rooms usando il metodo Import

È possibile importare un :::no-loc text="Microsoft Teams Rooms"::: dashboard e avviare il monitoraggio rapido dei dispositivi. Eseguire la procedura seguente per importare il Dashboard:

1.  Ottenere il file del dashboard [SkypeRoomSystems_v2. omsview](https://go.microsoft.com/fwlink/?linkid=835675) .
2.  Accedere al [ :::no-loc text="Microsoft Azure"::: portale](https://portal.azure.com) e :::no-loc text="Log Analytics"::: selezionare l'area di lavoro.
3.  Aprire **Progettazione visualizzazioni**.
4.  Selezionare **Importa**e quindi selezionare il file **SkypeRoomSystems_v2. omsview** .
5.  Selezionare **Salva**.

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Creare manualmente un dashboard di Microsoft teams rooms

In alternativa, è possibile creare un dashboard personalizzato e aggiungere solo i riquadri che si desidera monitorare.

#### <a name="configure-the-overview-tile"></a>Configurare il riquadro Panoramica

1.  Aprire **Progettazione visualizzazioni**.
2.  Selezionare **riquadro Panoramica**e quindi selezionare **due numeri** dalla raccolta.
3.  Assegnare un nome **:::no-loc text="Microsoft Teams Rooms":::** al riquadro.
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

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>Creare un riquadro che visualizza :::no-loc text="Microsoft Teams Rooms"::: le versioni del sistema operativo

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

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>Creare un riquadro che visualizza :::no-loc text="Microsoft Teams Rooms"::: le versioni delle applicazioni

1.  Selezionare **elenco & ciambella** nella raccolta e quindi aggiungere un nuovo riquadro.
2.  Definire le proprietà **generali** :<br>
    **Titolo del gruppo:** :::no-loc text="Microsoft Teams Rooms"::: dettagli applicazione<br>
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

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>Configurare gli avvisi in:::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor":::può generare avvisi per avvisare gli amministratori quando una :::no-loc text="Microsoft Teams Rooms"::: console incontra un problema.

:::no-loc text="Azure Monitor":::include un meccanismo di avviso incorporato che viene eseguito tramite ricerche di log pianificate a intervalli regolari. Se i risultati della ricerca del log corrispondono a determinati criteri specifici, viene creato un record di avviso.

La regola può quindi eseguire automaticamente una o più azioni per avvisare in modo proattivo l'avviso o richiamare un altro processo. Le opzioni possibili con gli avvisi sono:
-   Invio di un messaggio di posta elettronica
-   Richiamo di un processo esterno tramite una richiesta POST HTTP
-   Avvio di un Runbook :::no-loc text="Azure Automation"::: in servizio

Per ulteriori informazioni sugli avvisi in :::no-loc text="Azure Monitor":::, vedere registrare gli [avvisi :::no-loc text="Azure Monitor"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) .

> [!NOTE]
> Gli esempi seguenti inviano avvisi tramite posta :::no-loc text="Microsoft Teams Rooms"::: elettronica quando un dispositivo genera un errore hardware o dell'applicazione.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>Configurare un avviso di posta :::no-loc text="Microsoft Teams Rooms"::: elettronica per problemi hardware

Configurare una regola di avviso che controlli :::no-loc text="Microsoft Teams Rooms"::: i dispositivi che hanno riscontrato problemi hardware nell'ultima ora.
1.  Accedere al [ :::no-loc text="Microsoft Azure"::: portale](https://portal.azure.com) e :::no-loc text="Log Analytics"::: selezionare l'area di lavoro.

2. Passare all' :::no-loc text="Log Analytics"::: area di lavoro e selezionare **avvisi** e quindi selezionare **nuova regola di avviso**

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
    4.  Selezionare la casella di controllo **posta elettronica** e specificare l'indirizzo di posta elettronica della persona o del gruppo che riceverà gli avvisi.
    5.  È anche possibile specificare il numero di telefono per ricevere una notifica tramite SMS, una chiamata vocale o entrambi.
    6. Selezionare **OK**.

8. **Personalizzare le azioni** se si vuole ignorare la riga dell'oggetto dei messaggi di posta elettronica di avviso.

9. Specificare un nome e una descrizione della regola.<br>
    **Nome regola:** :::no-loc text="Microsoft Teams Rooms"::: avviso di errore hardware<br>
    **Descrizione:** Elenco dei dispositivi che hanno rilevato un problema hardware nell'ultima ora<br>

10. Selezionare la gravità desiderata e verificare che la regola sia abilitata.

11. Selezionare **Crea regola di avviso**.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a>Configurare un avviso di posta :::no-loc text="Microsoft Teams Rooms"::: elettronica per problemi di applicazione

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

! [Esempio :::no-loc text="Azure Monitor"::: di messaggio di posta elettronica Alert] (.. /media/Deploy-Azure-Monitor-6.png "messaggio :::no-loc text="Azure Monitor"::: di avviso di esempio")

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>Configurare tutti i dispositivi per:::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"> </a> Una volta configurati i dashboard e gli avvisi, è possibile impostare e :::no-loc text="Microsoft Monitoring"::: configurare Agent in :::no-loc text="Microsoft Teams Rooms"::: tutti i dispositivi per completare la distribuzione del monitoraggio.

Anche se è possibile installare e configurare :::no-loc text="Microsoft Monitoring"::: l'agente manualmente su ogni dispositivo, è consigliabile sfruttare gli strumenti e i metodi di distribuzione del software esistenti.

Se si stanno costruendo i :::no-loc text="Microsoft Teams Rooms"::: dispositivi per la prima volta, è possibile includere la procedura di :::no-loc text="Microsoft Monitoring"::: installazione e configurazione dell'agente come parte del processo di compilazione. Per altre informazioni, vedere [installare l'agente tramite la riga di comando](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>Distribuzione :::no-loc text="Microsoft Monitoring"::: di un agente tramite un oggetto Criteri di gruppo

Se i :::no-loc text="Microsoft Teams Rooms"::: dispositivi sono già stati distribuiti prima di :::no-loc text="Azure Monitoring":::implementarli, è possibile usare lo script specificato per configurare gli agenti e configurarli tramite gli oggetti Criteri di :::no-loc text="Active Directory"::: gruppo.

1.  Creare un percorso di rete condiviso e concedere l'accesso in lettura al gruppo **Domain Computers** .

2.  Scaricare la versione a 64 bit dell' :::no-loc text="Microsoft Monitoring"::: agente da :::no-loc text="Windows":::<https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Estrarre il contenuto del pacchetto di installazione nella condivisione di rete.
    1.  Aprire una finestra del prompt dei comandi e quindi eseguire **MMASetup-amd64. exe/c**
    2.  Specifica la condivisione appena creata ed Estrai il contenuto.

4.  Creare un nuovo oggetto Criteri di gruppo e assegnarlo all'unità organizzativa in :::no-loc text="Microsoft Teams Rooms"::: cui si trovano gli account del computer.

5.  Configurare i criteri di esecuzione di PowerShell:
    1.  Modificare l'oggetto Criteri di gruppo appena creato e passare a componenti \\ \\ :::no-loc text="Windows"::: \\ dei \\ modelli amministrativi di criteri di configurazione del computer:::no-loc text="Windows PowerShell":::
    2.  Abilitare l' **esecuzione attiva dello script** e impostare i **criteri di esecuzione** per consentire gli **script locali**.

6.  Configurare lo script di avvio:
    1.  Copiare lo script seguente e salvarlo come Install-MMAgent. ps1.
    2.  Modificare i parametri WorkspaceId, WorkspaceKey e SetupPath in base alla configurazione.
    3.  Modificare lo stesso oggetto Criteri di gruppo e passare a script \\ di \\ :::no-loc text="Windows"::: impostazioni \\ dei criteri di configurazione del computer (avvio/arresto)
    4.  Fare doppio clic per selezionare **avvio**e quindi selezionare **script di PowerShell**.
    5.  Selezionare **Mostra file**e quindi copiare il file **Install-mmagent. ps1** in tale cartella.
    6.  Selezionare **Aggiungi**e quindi **Sfoglia**.
    7.  Selezionare lo script ps1 appena copiato.

7.  :::no-loc text="Microsoft Teams Rooms":::i dispositivi devono installare e configurare :::no-loc text="Microsoft Monitoring"::: l'agente con il secondo riavvio.

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
> È possibile fare riferimento all'articolo [gestione e manutenzione dell' :::no-loc text="Log Analytics"::: agente](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) quando è necessario riconfigurare un agente, spostarlo in un'area di lavoro diversa o modificare le impostazioni del proxy dopo l'installazione iniziale.

## <a name="additional-solutions"></a>Soluzioni aggiuntive
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor":::fornisce soluzioni di gestione predefinite tramite la [raccolta](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) soluzioni per consentire di monitorare ulteriormente l'ambiente. Ti consigliamo vivamente di aggiungere soluzioni per la [gestione degli avvisi](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution) e [ :::no-loc text="Azure Log Analytics"::: l'integrità degli agenti](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth) anche all'area di lavoro.

> [!NOTE]
> La soluzione per l'integrità dell'agente può aiutare a identificare gli agenti :::no-loc text="Microsoft Monitoring"::: obsoleti o interrotti all'interno dell'ambiente e la soluzione di gestione degli avvisi fornisce informazioni dettagliate sugli avvisi generati entro un determinato periodo.

## <a name="see-also"></a>Vedere anche

[Pianificare :::no-loc text="Microsoft Teams Rooms"::: la gestione con:::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[Gestire :::no-loc text="Microsoft Teams Rooms"::: i dispositivi con:::no-loc text="Azure Monitor":::](azure-monitor-manage.md)
