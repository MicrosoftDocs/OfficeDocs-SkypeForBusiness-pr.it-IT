---
title: Distribuire il monitoraggio Microsoft Teams Rooms con Monitoraggio di Azure
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: Questo articolo illustra come distribuire il monitoraggio di Microsoft Teams Rooms in modo integrato e end-to-end usando Monitoraggio di Azure.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5dbea45008024762f30d9555f4762c4377d2ed1f
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606415"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-monitoring-with-no-loc-textazure-monitor"></a>Distribuire il :::no-loc text="Microsoft Teams Rooms"::: monitoraggio con :::no-loc text="Azure Monitor":::

In questo articolo viene illustrato come configurare e distribuire il monitoraggio integrato end-to-end dei :::no-loc text="Microsoft Teams Rooms"::: dispositivi tramite :::no-loc text="Azure Monitor":::.

[!INCLUDE [teams-pro-license-requirement](../includes/teams-pro-license-requirement.md)]

È possibile configurare :::no-loc text="Log Analytics"::: all'interno :::no-loc text="Azure Monitor"::: di per fornire telemetria di base e avvisi che aiuteranno a gestire :::no-loc text="Microsoft Teams Rooms":::. Quando la soluzione di gestione matura, si potrebbe decidere di distribuire ulteriori funzionalità di gestione e dati per creare una visualizzazione più dettagliata della disponibilità e delle prestazioni del dispositivo.

Seguendo questa guida, è possibile usare un dashboard come l'esempio seguente per ottenere report dettagliati sullo stato della disponibilità dei dispositivi, dell'integrità di applicazioni e hardware e :::no-loc text="Microsoft Teams Rooms"::: della distribuzione delle versioni di applicazioni e sistemi operativi.

![Screenshot della visualizzazione Analisi log di esempio per Microsoft Teams Rooms.](../media/Deploy-Azure-Monitor-1.png "Esempio di visualizzazione Analisi log per Microsoft Teams Rooms")

In generale, è necessario eseguire le attività seguenti:


1. [Convalidare la :::no-loc text="Log Analytics"::: configurazione](azure-monitor-deploy.md#validate_LogAnalytics)
2. [Configurare i dispositivi di test per :::no-loc text="Log Analytics"::: la configurazione della gestione](azure-monitor-deploy.md#configure_test_devices)
3. [Mappare campi personalizzati](azure-monitor-deploy.md#Custom_fields)
4. [Definire le :::no-loc text="Microsoft Teams Rooms"::: visualizzazioni in :::no-loc text="Log Analytics":::](azure-monitor-deploy.md#Define_Views)
5. [Definire gli avvisi](azure-monitor-deploy.md#Alerts)
6. [Configurare tutti i dispositivi per il monitoraggio](azure-monitor-deploy.md#configure_all_devices)
7. [Configurare soluzioni aggiuntive :::no-loc text="Azure Monitor":::](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> Anche se con una configurazione minima, :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: è possibile monitorare un computer che esegue un :::no-loc text="Windows"::: sistema operativo, ci sono ancora alcuni :::no-loc text="Microsoft Teams Rooms":::passaggi specifici che è necessario eseguire prima di avviare la distribuzione di agenti a tutti i :::no-loc text="Microsoft Teams Rooms"::: dispositivi.
> Pertanto, è consigliabile eseguire tutti i passaggi di configurazione nell'ordine corretto per un'installazione e una configurazione controllate. La qualità del risultato finale dipende molto dalla qualità della configurazione iniziale.

## <a name="validate-no-loc-textlog-analytics-configuration"></a>Convalidare la :::no-loc text="Log Analytics"::: configurazione
<a name="validate_LogAnalytics"> </a>

È necessario avere un'area :::no-loc text="Log Analytics"::: di lavoro per iniziare a raccogliere i log da :::no-loc text="Microsoft Teams Rooms":::. Un'area di lavoro è un ambiente univoco :::no-loc text="Log Analytics"::: con un proprio archivio dati, origini dati e soluzioni. Se si dispone già di un'area di lavoro esistente :::no-loc text="Log Analytics"::: , è possibile usarla per monitorare la :::no-loc text="Microsoft Teams Rooms"::: distribuzione oppure, in alternativa, creare un'area di lavoro dedicata specifica :::no-loc text="Log Analytics"::: per le proprie :::no-loc text="Microsoft Teams Rooms"::: esigenze di monitoraggio.

Se è necessario creare una nuova :::no-loc text="Log Analytics"::: area di lavoro, seguire le istruzioni nell'articolo [Creare un'area :::no-loc text="Log Analytics"::: di lavoro nel :::no-loc text="Azure"::: portale](/azure/azure-monitor/learn/quick-create-workspace)

> [!NOTE]
> Per usarlo :::no-loc text="Log Analytics"::: con :::no-loc text="Azure Monitor":::, è necessario avere un abbonamento attivo :::no-loc text="Azure"::: . Se non si ha un :::no-loc text="Azure"::: abbonamento, è possibile creare [un abbonamento di prova gratuito](https://azure.microsoft.com/free) come punto di partenza.

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a>Configurare :::no-loc text="Log Analytics"::: per la raccolta :::no-loc text="Microsoft Teams Rooms"::: dei registri eventi

:::no-loc text="Log Analytics"::: raccoglie solo gli eventi dai :::no-loc text="Windows"::: registri eventi specificati nelle impostazioni. Per ogni log vengono raccolti solo gli eventi con i livelli di gravità selezionati.

È necessario configurare :::no-loc text="Log Analytics"::: per raccogliere i log necessari per monitorare :::no-loc text="Microsoft Teams Rooms"::: lo stato del dispositivo e dell'applicazione. :::no-loc text="Microsoft Teams Rooms"::: usare il **:::no-loc text="Skype Room System":::** registro eventi.

Per configurare :::no-loc text="Log Analytics"::: per la raccolta degli :::no-loc text="Microsoft Teams Rooms"::: eventi, vedere [:::no-loc text="Windows"::: origini dati del registro eventi in :::no-loc text="Azure Monitor":::](/azure/azure-monitor/platform/data-sources-windows-events)

![Screenshot delle impostazioni del registro eventi.](../media/Deploy-Azure-Monitor-2.png "Impostazioni del registro eventi")

> [!IMPORTANT]
> Configurare :::no-loc text="Windows"::: le impostazioni del registro eventi e immettere **:::no-loc text="Skype Room System":::** come nome del registro eventi, quindi selezionare le caselle di controllo **Errore**, **Avviso** e **Informazioni** .

## <a name="configure-test-devices-for-azure-monitoring"></a>Configurare i dispositivi di test per Monitoraggio di Azure
<a name="configure_test_devices"> </a>

È necessario prepararsi :::no-loc text="Log Analytics"::: per essere in grado di monitorare :::no-loc text="Microsoft Teams Rooms":::gli eventi correlati. Per iniziare, è necessario distribuire :::no-loc text="Microsoft Monitoring"::: gli agenti in uno o due :::no-loc text="Microsoft Teams Rooms"::: dispositivi a cui si ha accesso fisico e ottenere tali dispositivi di test per generare alcuni dati ed eseguirne il push nell'area :::no-loc text="Log Analytics"::: di lavoro.

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a>Installare :::no-loc text="Microsoft Monitoring"::: agenti per testare i dispositivi

Distribuire l'agente :::no-loc text="Microsoft Monitoring"::: nei dispositivi di test seguendo le istruzioni fornite in [Connettere :::no-loc text="Windows"::: i computer al :::no-loc text="Log Analytics"::: servizio in :::no-loc text="Azure":::](/azure/azure-monitor/platform/agent-windows). Questo articolo fornisce informazioni dettagliate sui passaggi per la distribuzione dell'agente :::no-loc text="Microsoft Monitoring"::: per :::no-loc text="Windows":::, istruzioni per ottenere l'ID :::no-loc text="Log Analytics"::: ***area di lavoro** _ e _ *_primary key_** per connettere :::no-loc text="Microsoft Teams Rooms"::: i dispositivi alla :::no-loc text="Azure Monitor"::: distribuzione e i passaggi per verificare la connettività dell'agente all'istanza :::no-loc text="Log Analytics"::: .

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a>Generare eventi di esempio :::no-loc text="Microsoft Teams Rooms":::

Dopo la distribuzione dell'agente :::no-loc text="Microsoft Monitoring"::: nei dispositivi di test, verificare che i dati necessari del registro eventi siano raccolti da :::no-loc text="Azure Monitor":::.

> [!NOTE]
> Riavvia il dispositivo dopo l'installazione dell'agente :::no-loc text="Microsoft Monitoring"::: e assicurati che :::no-loc text="Microsoft Teams Rooms"::: l'app Riunione venga avviata, in modo che possa generare nuovi eventi nel registro eventi.

1.  Accedi al [:::no-loc text="Microsoft Azure"::: portale](https://portal.azure.com) , vai a :::no-loc text="Log Analytics"::: e seleziona l'area di lavoro.

2.  Elencare gli eventi di heartbeat generati da un :::no-loc text="Microsoft Teams Rooms"::: dispositivo:
    1.  Selezionare l'area di lavoro e passare a **Log** e usare una query per recuperare i record heartbeat che avranno i campi personalizzati per :::no-loc text="Microsoft Teams Rooms":::.
    2.  Query di esempio: `Event | where Source == "SRS-App" and EventID == 2000`

3.  Assicurarsi che la query restituisca i record di log che includono gli eventi generati dall'app :::no-loc text="Microsoft Teams Rooms"::: riunioni.

4.  Generare un problema hardware e verificare che gli eventi necessari siano registrati in :::no-loc text="Azure Log Analytics":::.
    1.  Scollega uno dei dispositivi periferici nel sistema di test :::no-loc text="Microsoft Teams Rooms"::: . Potrebbe trattarsi della fotocamera, dell'altoparlante, del microfono o dello schermo della sala anteriore
    2.  Attendere 10 minuti perché il registro eventi venga popolato in :::no-loc text="Azure Log Analytics":::.
    3.  Usare una query per elencare gli eventi di errore hardware: `Event | where Source == "SRS-App" and EventID == 3001`

5.  Generare un problema dell'applicazione e verificare che gli eventi necessari vengano registrati.
    1.  Modificare la :::no-loc text="Microsoft Teams Rooms"::: configurazione dell'account e digitare una coppia Email/password errata.
    2.  Attendere 10 minuti perché il registro eventi venga popolato in :::no-loc text="Azure Log Analytics":::.
    3.  Usare una query per elencare gli eventi di errore dell'applicazione: `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`

> [!IMPORTANT]
> Questi registri eventi di esempio sono necessari prima di poter configurare campi personalizzati. Non procedere con il passaggio successivo finché non vengono raccolti i registri eventi necessari.

## <a name="map-custom-fields"></a>Mappare campi personalizzati
<a name="Custom_fields"> </a>

I campi personalizzati consentono di estrarre dati specifici dai registri eventi. È necessario definire campi personalizzati che verranno usati in seguito con i riquadri, le visualizzazioni del dashboard e gli avvisi. Vedere [Campi personalizzati in :::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/custom-fields) e acquisire familiarità con i concetti prima di iniziare a creare i campi personalizzati.

Per estrarre i campi personalizzati dai registri eventi acquisiti, seguire questa procedura:

1.  Accedi al [:::no-loc text="Microsoft Azure"::: portale](https://portal.azure.com) , vai a :::no-loc text="Log Analytics"::: e seleziona l'area di lavoro.

2. Elencare gli eventi generati da un :::no-loc text="Microsoft Teams Rooms"::: dispositivo:
   1.  Passare a **Log** e usare una query per recuperare i record che avranno il campo personalizzato.
   2.  Query di esempio: `Event | where Source == "SRS-App" and EventID == 2000`

3. Selezionare uno dei record, selezionare il pulsante a sinistra e avviare la procedura guidata di estrazione campi.
4. Evidenzia i dati che vuoi estrarre da RenderedDescription e fornisci un Titolo campo. I nomi dei campi da usare sono disponibili nella tabella 1.
5. Usare i mapping mostrati nella *tabella 1*. :::no-loc text="Log Analytics"::: aggiungerà automaticamente la **\_stringa CF** quando si definisce il nuovo campo.

> [!IMPORTANT]
> Tenere presente che tutti i campi e JSON fanno distinzione tra maiuscole e :::no-loc text="Log Analytics"::: minuscole.
> 
> Prestare attenzione alle query necessarie per ogni campo personalizzato nella tabella seguente. È necessario usare le query corrette per :::no-loc text="Log Analytics"::: estrarre correttamente i valori dei campi personalizzati.
> 
**Tabella 1**

| **JSON**                   | **:::no-loc text="Log Analytics"::: campo personalizzato** | **ID evento** | **Query da usare con l'estrazione**                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| Descrizione                      | SRSEventDescription         | **2000**     | Evento \| in cui Source == "SRS-App" e EventID == 2000 |
| ResourceState                    | SRSResourceState            | **2000**     | Evento \| in cui Source == "SRS-App" e EventID == 2000 |
| Nomeoperazione                    | SRSOperationName            | **2000**     | Evento \| in cui Source == "SRS-App" e EventID == 2000 |
| Operationresult                  | SRSOperationResult          | **2000**     | Evento \| in cui Source == "SRS-App" e EventID == 2000 |
| OS                               | SRSOSVersion                | **2000**     | Evento \| in cui Source == "SRS-App" e EventID == 2000 |
| OSVersion                        | SRSOSLongVersion            | **2000**     | Evento \| in cui Source == "SRS-App" e EventID == 2000 |
| Alias                            | SRSAlias                    | **2000**     | Evento \| in cui Source == "SRS-App" e EventID == 2000 |
| Displayname                      | SRSDisplayName              | **2000**     | Evento \| in cui Source == "SRS-App" e EventID == 2000 |
| AppVersion                       | SRSAppVersion               | **2000**     | Evento \| in cui Source == "SRS-App" e EventID == 2000 |
| IPv4Address                      | SRSIPv4Address              | **2000**     | Evento \| in cui Source == "SRS-App" e EventID == 2000 |
| IPv6Address                      | SRSIPv6Address              | **2000**     | Evento \| in cui Source == "SRS-App" e EventID == 2000 |
| Stato microfono conferenza     | SRSConfMicrophoneStatus     | **3001**     | Evento \| dove Source == "SRS-App" e EventID == 3001 |
| Stato relatore conferenza        | SRSConfSpeakerStatus        | **3001**     | Evento \| dove Source == "SRS-App" e EventID == 3001 |
| Stato altoparlante predefinito           | SRSDefaultSpeakerStatus     | **3001**     | Evento \| dove Source == "SRS-App" e EventID == 3001 |
| Stato della fotocamera                    | SRSCameraStatus             | **3001**     | Evento \| dove Source == "SRS-App" e EventID == 3001 |
| Stato visualizzazione davanti alla sala     | SRSFORDStatus               | **3001**     | Evento \| dove Source == "SRS-App" e EventID == 3001 |
| Stato del sensore di movimento             | SRSMotionSensorStatus       | **3001**     | Evento \| dove Source == "SRS-App" e EventID == 3001 |
| Stato di inserimento HDMI               | SRSHDMIIngestStatus         | **3001**     | Evento \| dove Source == "SRS-App" e EventID == 3001 |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a>Definire le :::no-loc text="Microsoft Teams Rooms"::: visualizzazioni in :::no-loc text="Log Analytics":::
<a name="Define_Views"> </a>

Dopo aver raccolto i dati e aver mappato i campi personalizzati, è possibile usare Progettazione visualizzazioni per sviluppare un dashboard contenente vari riquadri per monitorare :::no-loc text="Microsoft Teams Rooms"::: gli eventi. Usare Progettazione visualizzazioni per creare i riquadri seguenti. Per altre informazioni, vedere [Creare visualizzazioni personalizzate usando Progettazione visualizzazioni in :::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/view-designer)

> [!NOTE]
> I passaggi precedenti di questa guida dovrebbero essere stati completati per il corretto funzionamento dei riquadri del dashboard.
>
> [!IMPORTANT]
> [View Designer in Azure Monitor verrà ritirato il 31 agosto 2023](https://azure.microsoft.com/updates/view-designer-in-azure-monitor-is-retiring-on-31-august-2023/) e le funzionalità di creazione e clone sono state disabilitate il 30 novembre 2020. In alternativa, è possibile usare le cartelle di lavoro. Per altre informazioni sulla guida alla transizione alle cartelle di lavoro di Progettazione visualizzazioni, vedere [Guida introduttiva con i modelli di Progettazione visualizzazioni preimpostati](/azure/azure-monitor/visualize/view-designer-conversion-tasks#quickstart-with-preset-view-designer-templates).

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a>Creare manualmente un dashboard di Microsoft Teams Rooms

In alternativa, è possibile creare un dashboard personalizzato e aggiungere solo i riquadri da monitorare.

#### <a name="configure-the-overview-tile"></a>Configurare il riquadro Panoramica

1.  Aprire **Progettazione visualizzazioni**.
2.  Seleziona **Riquadro Panoramica**, quindi due **numeri** nella raccolta.
3.  Assegna un nome al riquadro **:::no-loc text="Microsoft Teams Rooms":::**.
4.  Definire il **primo riquadro**:<br>
    **Leggenda:** Dispositivi che hanno inviato un heartbeat almeno una volta nell'ultimo mese<br>
    **Query:** ```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```
5.  Definire il **secondo riquadro**:<br>
    **Leggenda:** Dispositivi attivi che hanno inviato un heartbeat nell'ultima ora<br>
    **Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```
6.  Selezionare **Applica**.

### <a name="create-a-tile-that-displays-active-devices"></a>Creare un riquadro che visualizza i dispositivi attivi

1.  Seleziona **Visualizza dashboard** per iniziare ad aggiungere i riquadri.
2.  Selezionare **Numero & elenco** nella raccolta
3.  Definire le proprietà **Generale** :<br>
    **Titolo del gruppo:** Stato battito cardiaco<br>
    **Nuovo gruppo:** Selezionato
4.  Definire le proprietà **tile** :<br>
    **Leggenda:** Dispositivi attivi (heartbeat inviato negli ultimi 20 minuti)<br>
    **Query di riquadro:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```
5.  Definire le proprietà **di List** :<br>
    **Query elenco:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
6.  Definire **i titoli delle colonne**:<br>
    **Nome:** Nome computer<br>
    **Valore:** Ultimo battito cardiaco
7.  Definire **query di spostamento**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Selezionare **Applica** e quindi **Chiudi**.

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a>Creare un riquadro che visualizza i dispositivi con problemi di connettività

1.  Seleziona **Numero & elenco** dalla raccolta e quindi aggiungi un nuovo riquadro.
2.  Definire le proprietà **Generale** :<br>
    **Titolo del gruppo:** Lascia vuoto<br>
    **Nuovo gruppo:** Non selezionato
3.  Definire le proprietà **tile** :<br>
    **Leggenda:** Dispositivi inattivi (nessun messaggio di heartbeat inviato negli ultimi 20 minuti)<br>
    **Query di riquadro:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```
4.  Definire le proprietà **di List** :<br>
    **Query elenco:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```
5.  Definire **i titoli delle colonne**:<br>
    **Nome:** Nome computer<br>
    **Valore:** Ultimo battito cardiaco
6.  Definisci **query di spostamento**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Selezionare **Applica** e quindi **Chiudi**.

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a>Creare un riquadro che visualizza i dispositivi con un errore hardware

1.  Seleziona **Numero & elenco** dalla raccolta e quindi aggiungi un nuovo riquadro.
2.  Definire le proprietà **Generale** :<br>
    **Titolo del gruppo:** Stato hardware<br>
    **Nuovo gruppo:** Selezionato
3.  Definire le proprietà **tile** :<br>
    **Leggenda:** Dispositivi che hanno riscontrato un errore hardware nell'ultima ora<br>
    **Query di riquadro:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Definire le proprietà **di List** :<br>
    **Query elenco:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definire **i titoli delle colonne**:<br>
    **Nome:** Nome computer<br>
    **Valore:** Ultimo errore
6.  Definisci **query di spostamento**:<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Selezionare **Applica** e quindi **Chiudi**.

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a>Creare un riquadro che visualizza le :::no-loc text="Microsoft Teams Rooms"::: versioni del sistema operativo

1.  Seleziona **Ciambella & elenco** dalla raccolta e quindi aggiungi un nuovo riquadro.
2.  Definire le proprietà **Generale** :<br>
    **Titolo del gruppo:** Dettagli del sistema operativo<br>
    **Nuovo gruppo:** Selezionato
3.  Definire le proprietà **header** :<br>
    **Titolo:** Versioni del sistema operativo<br>
    **Sottotitolo:** Dispositivi che eseguono versioni del sistema operativo specifiche
4.  Definire le proprietà **donut** :<br>
    **Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```<br>
    **Testo centrato:** Dispositivi<br>
    **Operazione:** Somma
5.  Definire le proprietà **di List** .<br>
    **Query elenco:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```<br>
    **Nascondi grafico:** Selezionato<br>
    **Abilitare i grafici sparkline:** Non selezionato
6.  Definire **i titoli delle colonne**.<br>
    **Nome:** Nome computer<br>
    **Valore:** Lascia vuoto
7.  Definire **query di spostamento**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Selezionare **Applica** e quindi **Chiudi**.

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a>Creare un riquadro che visualizza le :::no-loc text="Microsoft Teams Rooms"::: versioni dell'applicazione

1.  Seleziona **Ciambella & elenco** dalla raccolta e quindi aggiungi un nuovo riquadro.
2.  Definire le proprietà **Generale** :<br>
    **Titolo del gruppo:** :::no-loc text="Microsoft Teams Rooms"::: dettagli applicazione<br>
    **Nuovo gruppo:** Selezionato
3.  Definire le proprietà **header** :<br>
    **Titolo:** Versioni delle applicazioni<br>
    **Sottotitolo:** Dispositivi che eseguono versioni specifiche dell'applicazione
4.  Definire le proprietà **donut** :<br>
    **Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```<br>
    **Testo centrato:** Dispositivi<br>
    **Operazione:** Somma
5.  Definire le proprietà **di List** .<br>
    **Query elenco:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```<br>
    **Nascondi grafico:** Selezionato<br>
    **Abilitare i grafici sparkline:** Non selezionato
6.  Definire **i titoli delle colonne**.<br>
    **Nome:** Nome computer<br>
    **Valore:** Lascia vuoto
7.  Definire **query di spostamento**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  Selezionare **Applica** e quindi **Chiudi**.

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a>Creare un riquadro che visualizza i dispositivi con un errore dell'applicazione

1.  Seleziona **Numero & elenco** dalla raccolta e quindi aggiungi un nuovo riquadro.
2.  Definire le proprietà **Generale** .<br>
    **Titolo del gruppo:** Lascia vuoto<br>
    **Nuovo gruppo:** Non selezionato
3.  Definire le proprietà **Tile** .<br>
    **Leggenda:** Dispositivi che hanno riscontrato un errore dell'applicazione nell'ultima ora<br>
    **Query di riquadro:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```
4.  Definire le proprietà **di List** .<br>
    **Query elenco:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```
5.  Definire **i titoli delle colonne**.<br>
    **Nome:** Nome computer<br>
    **Valore:** Ultimo errore
6.  Definire **query di spostamento**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  Selezionare **Applica** e quindi **Chiudi**.

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a>Creare un riquadro che visualizza i dispositivi riavviati

1.  Seleziona **Numero & elenco** dalla raccolta e quindi aggiungi un nuovo riquadro.
2.  Definire le proprietà **Generale** .<br>
    **Titolo del gruppo:** Lascia vuoto<br>
    **Nuovo gruppo:** Non selezionato
3.  Definire le proprietà **Tile** .<br>
    **Leggenda:** Dispositivi in cui l'applicazione è stata riavviata nelle ultime 24 ore e numero di riavvii<br>
    **Query di riquadro:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```
4.  Definire le proprietà **di List** .<br>
    **Query elenco:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```
5.  Definire **i titoli delle colonne**.<br>
    **Nome:** Nome computer<br>
    **Valore:** Numero di riavvii
6.  Definire **query di spostamento**.<br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  Selezionare **Applica** e quindi **Chiudi**.
8.  Seleziona **Salva** per salvare il dashboard.

La creazione delle visualizzazioni è stata completata.

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a>Configurare gli avvisi in :::no-loc text="Azure Monitor":::
<a name="Alerts"> </a>

:::no-loc text="Azure Monitor"::: possono generare avvisi per informare gli amministratori, quando una :::no-loc text="Microsoft Teams Rooms"::: console rileva un problema.

:::no-loc text="Azure Monitor"::: include un meccanismo di avviso predefinito che viene eseguito tramite ricerche di log pianificate a intervalli regolari. Se i risultati della ricerca nel log corrispondono a determinati criteri, viene creato un record di avviso.

La regola può quindi eseguire automaticamente una o più azioni per notificare in modo proattivo l'avviso o richiamare un altro processo. Le opzioni possibili con gli avvisi sono:
-   Invio di un messaggio di posta elettronica
-   Richiamare un processo esterno tramite una richiesta HTTP POST
-   Avvio di un runbook in :::no-loc text="Azure Automation"::: servizio

Per altre informazioni sugli avvisi [in :::no-loc text="Azure Monitor":::](/azure/azure-monitor/platform/alerts-unified-log) , vedere Accedere agli avvisi in :::no-loc text="Azure Monitor":::.

> [!NOTE]
> Gli esempi seguenti inviano avvisi tramite posta elettronica quando un :::no-loc text="Microsoft Teams Rooms"::: dispositivo genera un errore hardware o di applicazione.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a>Configurare un avviso di posta elettronica per :::no-loc text="Microsoft Teams Rooms"::: problemi hardware

Configurare una regola di avviso che controlla la presenza di :::no-loc text="Microsoft Teams Rooms"::: dispositivi che hanno riscontrato problemi hardware nell'ultima ora.
1.  Accedi al [:::no-loc text="Microsoft Azure"::: portale](https://portal.azure.com) , vai a :::no-loc text="Log Analytics"::: e seleziona l'area di lavoro.

2. Passare all'area :::no-loc text="Log Analytics"::: di lavoro e selezionare **Avvisi** e quindi selezionare **Nuova regola di avviso**

3. Selezionare **Aggiungi condizione** e quindi **Ricerca log personalizzata**

4.  Immettere la query seguente nella casella di testo Query di ricerca.<br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  Configurare le impostazioni della logica di avviso:<br>
    **In base a:** Numero di risultati<br>
    **Condizione:** Maggiore<br>
    **Soglia:** 0<br>

6. Configurare le impostazioni di valutazione e selezionare **Fine**: <br>
    **Periodo (in minuti):** 60<br>
    **Frequenza (in minuti):** 60<br>

7. Configurare i gruppi di azioni:
    1.  Seleziona **Crea nuovo**
    2.  Specificare i nomi appropriati per i campi *Nome gruppo di* azioni e *Nome breve* .
    3.  Specificare un *Nome azione* univoco e selezionare **Email/SMS/Push/Voce**, quindi selezionare **Modifica dettagli**.
    4.  Selezionare la casella **di controllo Email** e fornire l'indirizzo di posta elettronica della persona o del gruppo che riceverà gli avvisi.
    5.  È anche possibile fornire il numero di telefono per ricevere una notifica tramite SMS, una chiamata vocale o entrambi.
    6. Selezionare **OK**.

8. **Personalizzare le azioni** se si vuole ignorare la riga dell'oggetto dei messaggi di avviso.

9. Specificare il nome e la descrizione di una regola.<br>
    **Nome regola:** :::no-loc text="Microsoft Teams Rooms"::: Avviso di errore hardware<br>
    **Descrizione:** Elenco dei dispositivi che hanno riscontrato un problema hardware nell'ultima ora<br>

10. Selezionare la gravità prevista e verificare che la regola sia abilitata.

11. Selezionare **Crea regola di avviso**.

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a>Configurare un avviso di posta elettronica per :::no-loc text="Microsoft Teams Rooms"::: i problemi dell'applicazione

Ripetere la stessa procedura, ma usare la query seguente per elencare i dispositivi che hanno riscontrato problemi di applicazione nell'ultima ora.

 ```
 Event
 | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
 | summarize arg_max(TimeGenerated, *) by Computer
 | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
 | sort by TimeGenerated desc
 ```

La definizione degli avvisi è stata completata. È possibile definire altri avvisi usando gli esempi precedenti.

Quando viene generato un avviso, riceverai un messaggio e-mail in cui sono elencati i dispositivi che hanno riscontrato un problema nell'ultima ora.

! [Messaggio di avviso di esempio :::no-loc text="Azure Monitor"::: ](.. /media/Deploy-Azure-Monitor-6.png "Messaggio e-mail di avviso di esempio :::no-loc text="Azure Monitor"::: ")

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a>Configura tutti i dispositivi per :::no-loc text="Azure Monitoring":::
<a name="configure_all_devices"> </a> Dopo aver configurato i dashboard e gli avvisi, è possibile configurare e configurare :::no-loc text="Microsoft Monitoring"::: l'agente in tutti i :::no-loc text="Microsoft Teams Rooms"::: dispositivi per completare la distribuzione di monitoraggio.

Anche se è possibile installare e configurare manualmente l'agente :::no-loc text="Microsoft Monitoring"::: in ogni dispositivo, è consigliabile sfruttare i metodi e gli strumenti di distribuzione del software esistenti.

Se si creano i :::no-loc text="Microsoft Teams Rooms"::: dispositivi per la prima volta, è consigliabile includere i passaggi di configurazione e configurazione dell'agente nell'ambito :::no-loc text="Microsoft Monitoring"::: del processo di compilazione. Per altre informazioni, vedere [Installare l'agente tramite la riga di comando](/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a>Distribuzione dell'agente :::no-loc text="Microsoft Monitoring"::: tramite un oggetto Criteri di gruppo (GPO)

Se i :::no-loc text="Microsoft Teams Rooms"::: dispositivi sono già stati distribuiti prima di implementare :::no-loc text="Azure Monitoring":::, è possibile usare lo script fornito per configurare gli agenti tramite :::no-loc text="Active Directory"::: oggetti Criteri di gruppo.

1.  Creare un percorso di rete condiviso e concedere l'accesso in lettura al gruppo **Computer di dominio** .

2.  Scarica la versione a 64 bit dell'agente :::no-loc text="Microsoft Monitoring"::: per :::no-loc text="Windows"::: da <https://go.microsoft.com/fwlink/?LinkID=517476>

3.  Estrarre il contenuto del pacchetto di installazione nella condivisione di rete.
    1.  Aprire una finestra del prompt dei comandi e quindi eseguire **MMASetup-AMD64.exe /c**
    2.  Specificare la condivisione appena creata ed estrarre il contenuto.

4.  Creare un nuovo oggetto Criteri di gruppo e assegnarlo all'unità organizzativa in cui :::no-loc text="Microsoft Teams Rooms"::: si trovano gli account del computer.

5.  Configurare i criteri di esecuzione di PowerShell:
    1.  Modificare l'oggetto Criteri di gruppo appena creato e passare a Componenti \\ dei modelli \\ :::no-loc text="Windows"::: amministrativi criteri di \\ configurazione \\ computer :::no-loc text="Windows PowerShell":::
    2.  Abilita **l'opzione Attiva esecuzione script** e imposta **Criteri di esecuzione** su **Consenti script locali**.

6.  Configurare lo script di avvio:
    1.  Copiare lo script seguente e salvarlo come Install-MMAgent.ps1.
    2.  Modificare i parametri WorkspaceId, WorkspaceKey e SetupPath in modo che corrispondano alla configurazione.
    3.  Modificare lo stesso Criteri di gruppo oggetto e passare a Impostazioni \\ script dei criteri di configurazione \\ \\ :::no-loc text="Windows"::: computer (avvio/arresto)
    4.  Fare doppio clic per selezionare **Avvio** e quindi Selezionare **Script di PowerShell**.
    5.  Selezionare **Mostra file** e quindi copiare il **fileInstall-MMAgent.ps1** in tale cartella.
    6.  Seleziona **Aggiungi** e quindi **Sfoglia**.
    7.  Selezionare lo script ps1 appena copiato.

7.  :::no-loc text="Microsoft Teams Rooms"::: installare e configurare l'agente :::no-loc text="Microsoft Monitoring"::: al secondo riavvio.

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
> È possibile fare riferimento all'articolo [Gestione e gestione dell'agente :::no-loc text="Log Analytics":::](/azure/azure-monitor/platform/agent-manage) quando è necessario riconfigurare un agente, spostarlo in un'area di lavoro diversa o modificare le impostazioni del proxy dopo l'installazione iniziale.

## <a name="additional-solutions"></a>Soluzioni aggiuntive
<a name="Solutions"> </a>

:::no-loc text="Azure Monitor"::: offre soluzioni di gestione predefinite tramite la [relativa raccolta soluzioni](/azure/azure-monitor/insights/solutions) per aiutarti ulteriormente a monitorare l'ambiente. È consigliabile aggiungere le soluzioni [Gestione avvisi](/azure/azure-monitor/platform/alert-management-solution) e [:::no-loc text="Azure Log Analytics"::: Integrità agente](/azure/azure-monitor/insights/solution-agenthealth) anche all'area di lavoro.

> [!NOTE]
> La soluzione Agent Health consente di identificare gli agenti obsoleti o interrotti :::no-loc text="Microsoft Monitoring"::: all'interno dell'ambiente e la soluzione Gestione avvisi fornisce dettagli sugli avvisi generati in un determinato periodo di tempo.

## <a name="see-also"></a>Vedere anche

[Pianificare :::no-loc text="Microsoft Teams Rooms"::: la gestione con :::no-loc text="Azure Monitor":::](azure-monitor-plan.md)

[Gestire i :::no-loc text="Microsoft Teams Rooms"::: dispositivi con :::no-loc text="Azure Monitor":::](azure-monitor-manage.md)
