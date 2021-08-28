---
title: Pianificare Microsoft Teams Rooms gestione con Monitor di Azure
ms.author: dstrome
author: dstrome
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
description: Questo articolo illustra considerazioni sulla pianificazione per l'uso di Monitoraggio di Azure per amministrare Microsoft Teams Rooms dispositivi nell'Skype for Business o Teams distribuzione.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2808d424d79d8d2b60af0573678ee18d0a52bdeb
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619362"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a>Pianificare Microsoft Teams Rooms gestione con Monitor di Azure
 
 Questo articolo illustra considerazioni sulla pianificazione per l'uso di Monitoraggio di Azure per amministrare Microsoft Teams Rooms dispositivi nell'implementazione Microsoft Teams o Skype for Business di rete.
  
[Azure Monitor](/azure/azure-monitor/overview) è una raccolta di servizi di gestione progettati nel cloud fin dall'inizio. Invece di distribuire e gestire le risorse locali, i componenti di Monitoraggio di Azure sono ospitati interamente in Azure. La configurazione è minima e puoi essere operativo letteralmente in pochi minuti. Con alcune operazioni di personalizzazione, può essere di aiuto nella gestione dei sistemi di conferenza Microsoft Teams Rooms, fornendo notifiche in tempo reale dell'integrità del sistema o degli errori per i singoli sistemi di sala e può essere potenzialmente scalato fino alla gestione di migliaia di Microsoft Teams Rooms sale riunioni.
  
Questo articolo illustra i requisiti, la progettazione/architettura e le procedure consigliate per l'implementazione necessarie per implementare la gestione basata su Monitoraggio di Azure dei dispositivi per conferenze di Microsoft Teams Rooms e fornisce collegamenti ad articoli dettagliati sull'implementazione di Monitoraggio di Azure per Microsoft Teams Rooms e informazioni di riferimento critiche per il monitoraggio continuo delle sale Microsoft Teams Rooms. 
  
## <a name="functional-overview"></a>Panoramica funzionale

![Diagramma della gestione Microsoft Teams Rooms con Monitor di Azure](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
L Microsoft Teams Rooms app nel dispositivo console scrive gli eventi nel Windows eventi. Un agente di monitoraggio Microsoft, una volta installato, passa le informazioni al servizio Monitoraggio di Azure. 
  
Dopo aver configurato correttamente, Log Analytics analizza il payload JSON incorporato nelle descrizioni degli eventi per descrivere il funzionamento di ogni sistema di Microsoft Teams Rooms e gli errori rilevati. 
  
Un amministratore che usa Monitor di Azure può ricevere notifiche di sistemi Microsoft Teams Rooms offline o in cui si verificano problemi di app, connettività o hardware, oltre a sapere se è necessario riavviare un sistema. Ogni stato del sistema viene aggiornato di frequente, quindi queste notifiche sono vicine agli aggiornamenti in tempo reale.
  
## <a name="azure-monitor-requirements"></a>Requisiti di Monitoraggio di Azure

Per usare la caratteristica Log Analytics, è necessario avere una sottoscrizione di Azure valida per Azure Monitor. Vedere [Introduzione a un'area di lavoro di Log Analytics](/azure/azure-monitor/learn/quick-create-workspace) per creare una sottoscrizione per l'organizzazione.
  
Se necessario, è consigliabile acquisire familiarità con l'uso di Progettazione visualizzazioni di Log Analytics. Per [informazioni dettagliate, vedere Visualizzazioni in Log Analytics.](/azure/azure-monitor/platform/view-designer)
  
### <a name="related-tasks"></a>Attività correlate

1. Dopo aver sottoscritto Azure Monitor Log Analytics, creare campi personalizzati (come descritto [in](azure-monitor-deploy.md#Custom_fields)Mappa campi personalizzati) necessari per analizzare le informazioni che verranno inviate da Microsoft Teams Rooms console. Questo include informazioni sullo schema JSON documentato in [Informazioni sulle voci del log.](azure-monitor-manage.md#understand-the-log-entries)
    
2. Sviluppare una Microsoft Teams Rooms di gestione dei log in Log Analytics. È possibile [creare un dashboard Microsoft Teams Rooms manualmente](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually).
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a>Requisiti Microsoft Teams Rooms Console

Ogni console Microsoft Teams Rooms è un'app in esecuzione in un dispositivo Surface Pro in modalità tutto schermo (in genere è configurata per essere l'unica app che può essere eseguita nel dispositivo). Come per qualsiasi app Windows, l'app Microsoft Teams Rooms scrive eventi come errori di avvio e hardware nel Windows eventi. L'aggiunta di un agente di Microsoft Monitor nel dispositivo Microsoft Teams Rooms consente di raccogliere questi eventi. Per informazioni [dettagliate, Connessione Windows sul servizio Log Analytics in Azure.](/azure/azure-monitor/platform/agent-windows)
  
## <a name="ongoing-management"></a>Gestione continua

Durante l'uso di Monitoraggio di Azure per gestire i dispositivi Microsoft Teams Rooms, è necessario comprendere le informazioni contenute nei log eventi usati da Monitoraggio di Azure. Per [informazioni dettagliate su questi](azure-monitor-manage.md#understand-the-log-entries) messaggi di integrità, vedere Informazioni sulle voci del log.
  
### <a name="related-tasks"></a>Attività correlate

- Comprendere gli avvisi generati da Microsoft Teams Rooms e come risolverli (vedere la sezione intitolato [Comprendere le voci del log)](azure-monitor-manage.md#understand-the-log-entries)
    
## <a name="see-also"></a>Vedere anche

[Distribuire Microsoft Teams Rooms gestione dei dati con Monitor di Azure](azure-monitor-deploy.md)
  
[Gestire Microsoft Teams Rooms dispositivi con Monitor di Azure](azure-monitor-manage.md)
