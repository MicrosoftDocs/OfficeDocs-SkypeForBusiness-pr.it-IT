---
title: Pianificare il monitoraggio Microsoft Teams Rooms con Monitoraggio di Azure
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
- Teams_ITAdmin_Rooms
description: Questo articolo descrive considerazioni sulla pianificazione per l'uso di Monitoraggio di Azure per monitorare Microsoft Teams Rooms nell'implementazione di Skype for Business o Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac3ac3af4e4f162238af0e9bf38c45569302fdfb
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269571"
---
# <a name="plan-microsoft-teams-rooms-monitoring-with-azure-monitor"></a>Pianificare il monitoraggio Microsoft Teams Rooms con Monitoraggio di Azure
 
 Questo articolo descrive considerazioni sulla pianificazione per l'uso di Monitoraggio di Azure per amministrare Microsoft Teams Rooms dispositivi nell'implementazione di Microsoft Teams o Skype for Business.

> [!NOTE]
> È anche possibile [configurare il monitoraggio dell'integrità di Teams Rooms](../alerts/device-health-status.md) usando l'interfaccia di amministrazione di Teams.

[Monitoraggio di Azure](/azure/azure-monitor/overview) è una raccolta di servizi di monitoraggio progettati fin dall'inizio nel cloud. Invece di distribuire e gestire risorse locali, i componenti di Monitoraggio di Azure sono interamente ospitati in Azure. La configurazione è minima e puoi essere operativo in pochi minuti. Con alcuni lavori di personalizzazione, può aiutare a monitorare Microsoft Teams Rooms fornendo notifiche di integrità del sistema o difetti per i singoli sistemi di sala e può aumentare fino a gestire migliaia di Microsoft Teams Rooms.
  
Questo articolo fornisce una discussione sui requisiti, la progettazione/architettura e le procedure consigliate di implementazione necessarie per implementare il monitoraggio basato su Monitoraggio di Azure di Microsoft Teams Rooms. Sono inoltre disponibili collegamenti ad articoli dettagliati sull'implementazione di Monitoraggio di Azure per Microsoft Teams Rooms e informazioni di riferimento critico per il monitoraggio continuo di Microsoft Teams Rooms sale.
  
## <a name="functional-overview"></a>Panoramica funzionale

![diagramma della gestione Microsoft Teams Rooms con Monitoraggio di Azure.](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
L'app Microsoft Teams Rooms scrive gli eventi nel registro eventi di Windows. Un agente di monitoraggio Microsoft, una volta installato, passa le informazioni al servizio Monitoraggio di Azure.
  
Una volta configurato correttamente, Log Analytics analizza il payload JSON incorporato nelle descrizioni degli eventi per descrivere come funziona Microsoft Teams Rooms e quali errori vengono rilevati.
  
Un amministratore che usa Monitoraggio di Azure può ricevere notifiche di Microsoft Teams Rooms che sono offline o che stanno riscontrando errori di app, connettività o hardware, oltre a sapere se è necessario riavviare un sistema. Ogni stato del sistema viene aggiornato di frequente, quindi queste notifiche si avvicinano agli aggiornamenti in tempo reale.
  
## <a name="azure-monitor-requirements"></a>Requisiti di Monitoraggio di Azure

Per usare le funzionalità di Log Analytics, è necessario avere una sottoscrizione di Azure valida per Monitoraggio di Azure. Vedere [Introduzione a un'area di lavoro Log Analytics](/azure/azure-monitor/learn/quick-create-workspace) per creare un abbonamento per l'organizzazione.
  
È consigliabile acquisire familiarità con l'uso di Log Analytics View Designer. Per informazioni dettagliate, vedere [Visualizzazioni in Log Analytics](/azure/azure-monitor/platform/view-designer) .
  
### <a name="related-tasks"></a>Attività correlate

1. Dopo aver sottoscritto Azure Monitor Log Analytics, creare campi personalizzati (come descritto in [Mappa campi personalizzati](azure-monitor-deploy.md#Custom_fields)) necessari per analizzare le informazioni che verranno inviate da Microsoft Teams Rooms. È inclusa la comprensione dello schema JSON documentato in [Informazioni sulle voci del log](azure-monitor-manage.md#understand-the-log-entries).
    
2. Sviluppare una visualizzazione di gestione Microsoft Teams Rooms in Log Analytics. È possibile [creare manualmente un dashboard di Microsoft Teams Rooms](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually).
    
## <a name="individual-microsoft-teams-rooms-requirements"></a>Requisiti individuali Microsoft Teams Rooms

Microsoft Teams Rooms è un'app in esecuzione su un dispositivo di calcolo in modalità tutto schermo. Come per qualsiasi app di Windows, l'app Microsoft Teams Rooms scrive eventi come l'avvio e gli errori hardware nel registro eventi di Windows. L'aggiunta di un agente di Microsoft Monitor in Microsoft Teams Rooms consente la raccolta di questi eventi. Per informazioni dettagliate [, vedere Connettere computer Windows al servizio Log Analytics in Azure](/azure/azure-monitor/platform/agent-windows) .
  
## <a name="ongoing-management"></a>Gestione continua

Durante l'uso di Monitoraggio di Azure per monitorare la Microsoft Teams Rooms, è necessario comprendere le informazioni contenute nei log eventi usati da Monitoraggio di Azure. Per informazioni dettagliate su questi messaggi di integrità, vedere [Informazioni sulle voci del log](azure-monitor-manage.md#understand-the-log-entries) .
  
### <a name="related-tasks"></a>Attività correlate

- Comprendere gli avvisi generati da Microsoft Teams Rooms e come risolverli (vedere la sezione [informazioni sulle voci del log](azure-monitor-manage.md#understand-the-log-entries))
    
## <a name="see-also"></a>Vedere anche

[Distribuire Microsoft Teams Rooms gestione con Monitoraggio di Azure](azure-monitor-deploy.md)
  
[Gestire Microsoft Teams Rooms dispositivi con Monitoraggio di Azure](azure-monitor-manage.md)
