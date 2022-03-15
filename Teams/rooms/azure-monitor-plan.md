---
title: Pianificare Microsoft Teams Rooms monitoraggio con Monitoraggio di Azure
ms.author: czawideh
author: cazawideh
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection:
- M365-collaboration
description: Questo articolo illustra considerazioni sulla pianificazione per l'uso di Monitoraggio di Azure per monitorare Microsoft Teams Rooms'implementazione Skype for Business o Teams di rete.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 510f249ea4aef78b898294db0a2c3fbeef8fc283
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2022
ms.locfileid: "63504123"
---
# <a name="plan-microsoft-teams-rooms-monitoring-with-azure-monitor"></a>Pianificare Microsoft Teams Rooms monitoraggio con Monitoraggio di Azure
 
 Questo articolo illustra considerazioni sulla pianificazione per l'uso di Monitoraggio di Azure per amministrare Microsoft Teams Rooms dispositivi nell'implementazione Microsoft Teams o Skype for Business rete.

> [!NOTE]
> È anche possibile [configurare il monitoraggio dell'integrità delle](../alerts/device-health-status.md) Teams Rooms tramite Teams di amministrazione.

[Azure Monitor](/azure/azure-monitor/overview) è una raccolta di servizi di monitoraggio progettati nel cloud fin dall'inizio. Invece di distribuire e gestire le risorse locali, i componenti di Monitoraggio di Azure sono ospitati interamente in Azure. La configurazione è minima e puoi essere operativo in pochi minuti. Con alcune operazioni di personalizzazione, può essere di aiuto per il monitoraggio dei Microsoft Teams Rooms, fornendo notifiche di integrità del sistema o errori per i singoli sistemi di sala e può essere scalato fino alla gestione di migliaia di Microsoft Teams Rooms.
  
Questo articolo illustra i requisiti, la progettazione/architettura e le procedure consigliate per l'implementazione necessarie per implementare il monitoraggio basato su Monitoraggio di Azure Microsoft Teams Rooms. Fornisce anche collegamenti ad articoli dettagliati sull'implementazione di Monitoraggio di Azure Microsoft Teams Rooms informazioni di riferimento critiche per il monitoraggio continuo Microsoft Teams Rooms chat room.
  
## <a name="functional-overview"></a>Panoramica funzionale

![Diagramma della gestione Microsoft Teams Rooms con Monitor di Azure.](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
L Microsoft Teams Rooms app scrive gli eventi nel Windows eventi. Un agente di monitoraggio Microsoft, una volta installato, passa le informazioni al servizio Monitoraggio di Azure.
  
Dopo aver configurato correttamente, Log Analytics analizza il payload JSON incorporato nelle descrizioni degli eventi per descrivere il funzionamento Microsoft Teams Rooms e gli errori rilevati.
  
Un amministratore che usa Monitor di Azure può ricevere notifiche di Microsoft Teams Rooms offline o in cui si verificano problemi di app, connettività o hardware, oltre a sapere se è necessario riavviare un sistema. Ogni stato del sistema viene aggiornato di frequente, quindi queste notifiche sono vicine agli aggiornamenti in tempo reale.
  
## <a name="azure-monitor-requirements"></a>Requisiti di Monitoraggio di Azure

Per usare le funzionalità di Log Analytics, è necessario avere una sottoscrizione di Azure valida per Azure Monitor. Vedere [Introduzione a un'area di lavoro di Log Analytics](/azure/azure-monitor/learn/quick-create-workspace) per creare una sottoscrizione per l'organizzazione.
  
È consigliabile acquisire familiarità con l'uso di Progettazione visualizzazioni di Log Analytics. Per [informazioni dettagliate, vedere Visualizzazioni in Log Analytics](/azure/azure-monitor/platform/view-designer) .
  
### <a name="related-tasks"></a>Attività correlate

1. Dopo aver sottoscritto Azure Monitor Log Analytics, creare campi personalizzati (come [descritto in Mappa](azure-monitor-deploy.md#Custom_fields) campi personalizzati) necessari per analizzare le informazioni che verranno inviate da Microsoft Teams Rooms. Questo include informazioni sullo schema JSON documentato in [Informazioni sulle voci del log](azure-monitor-manage.md#understand-the-log-entries).
    
2. Sviluppare una Microsoft Teams Rooms gestione dei dati in Log Analytics. È possibile [creare un dashboard Microsoft Teams Rooms manualmente](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually).
    
## <a name="individual-microsoft-teams-rooms-requirements"></a>Requisiti Microsoft Teams Rooms individuali

Microsoft Teams Rooms è un'app in esecuzione in un dispositivo di elaborazione in modalità tutto schermo. Come per qualsiasi app Windows, l'app Microsoft Teams Rooms scrive eventi come errori di avvio e hardware nel Windows eventi. L'aggiunta di un agente di Microsoft Monitor Microsoft Teams Rooms la raccolta di questi eventi. Per informazioni [dettagliate, Connessione Windows computer al servizio Log Analytics in Azure](/azure/azure-monitor/platform/agent-windows).
  
## <a name="ongoing-management"></a>Gestione continua

Durante l'uso di Monitoraggio di Azure per monitorare Microsoft Teams Rooms, è necessario comprendere le informazioni contenute nei log eventi usati da Monitoraggio di Azure. Per [informazioni dettagliate su questi messaggi di integrità,](azure-monitor-manage.md#understand-the-log-entries) vedere Informazioni sulle voci del log.
  
### <a name="related-tasks"></a>Attività correlate

- Comprendere gli avvisi generati da Microsoft Teams Rooms e come risolverli (vedere la sezione intitolato [Comprendere le voci del log](azure-monitor-manage.md#understand-the-log-entries))
    
## <a name="see-also"></a>Vedere anche

[Distribuire Microsoft Teams Rooms gestione dei dati con Monitor di Azure](azure-monitor-deploy.md)
  
[Gestire Microsoft Teams Rooms dispositivi con Monitor di Azure](azure-monitor-manage.md)
