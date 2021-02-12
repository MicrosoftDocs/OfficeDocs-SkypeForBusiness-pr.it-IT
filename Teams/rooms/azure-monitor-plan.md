---
title: Pianificare la gestione delle sale di Microsoft Teams con Azure Monitor
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection:
- M365-collaboration
description: Questo articolo illustra considerazioni sulla pianificazione per l'uso di Azure Monitor per amministrare i dispositivi Microsoft Teams Room nell'implementazione di Skype for Business o Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 16a962d7414407cf5f2f5734b7a2f39a56f7d281
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137606"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a>Pianificare la gestione delle sale di Microsoft Teams con Azure Monitor
 
 Questo articolo illustra considerazioni sulla pianificazione per l'uso di Azure Monitor per amministrare i dispositivi Microsoft Teams Room nell'implementazione di Microsoft Teams o Skype for Business.
  
[Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview) è una raccolta di servizi di gestione progettati nel cloud fin dall'inizio. Invece di distribuire e gestire le risorse locali, i componenti di Azure Monitor sono interamente ospitati in Azure. La configurazione è minima e puoi essere letteralmente operativo in pochi minuti. Con alcune personalizzazioni, può essere di aiuto nella gestione dei sistemi di conferenza Microsoft Teams Room, fornendo notifiche in tempo reale relative all'integrità del sistema o ai difetti dei singoli sistemi di sala e può essere anche in grado di gestire migliaia di sale riunioni di Microsoft Teams.
  
Questo articolo fornisce una discussione sui requisiti, la progettazione/architettura e le procedure consigliate di implementazione necessarie per implementare la gestione basata su Azure Monitor dei dispositivi per conferenze di Microsoft Teams Room e fornisce collegamenti ad articoli dettagliati sull'implementazione di Monitor Azure per le sale di Microsoft Teams e informazioni di riferimento critico per il monitoraggio continuo delle sale sale di Microsoft Teams. 
  
## <a name="functional-overview"></a>Panoramica funzionale

![Diagramma della gestione delle sale di Microsoft Teams con Azure Monitor](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
L'app Sale di Microsoft Teams nel dispositivo console scrive gli eventi nel relativo registro eventi di Windows. Un agente di monitoraggio Microsoft, una volta installato, passa le informazioni al servizio Azure Monitor. 
  
Una volta configurato correttamente, Log Analytics analizza il payload JSON incorporato nelle descrizioni degli eventi per descrivere il funzionamento di ogni sistema Room di Microsoft Teams e quali errori vengono rilevati. 
  
Un amministratore che usa Azure Monitor può ricevere notifiche di sistemi Microsoft Teams Room in modalità offline o con app, connettività o errori hardware e sapere se un sistema deve essere riavviato. Ogni stato del sistema viene aggiornato di frequente, quindi queste notifiche sono vicine agli aggiornamenti in tempo reale.
  
## <a name="azure-monitor-requirements"></a>Requisiti di Azure Monitor

Per usare la caratteristica Analisi log, è necessario avere una sottoscrizione di Azure valida per Azure Monitor. Vedere [Introduzione all'area di lavoro Analisi log](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) per creare un abbonamento per l'organizzazione.
  
È consigliabile acquisire familiarità con le informazioni necessarie sull'uso di Progettazione visualizzazioni analisi log. Per [informazioni dettagliate, vedere](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer) Visualizzazioni in Analisi log.
  
### <a name="related-tasks"></a>Attività correlate

1. Dopo aver effettuato la sottoscrizione a Analisi log di Azure Monitor, creare campi personalizzati (come descritto [in](azure-monitor-deploy.md#Custom_fields)Mappa campi personalizzati) necessari per analizzare le informazioni che verranno inviate dalle console di Microsoft Teams Rooms. Questo include informazioni sullo schema JSON documentato in [Informazioni sulle voci del log.](azure-monitor-manage.md#understand-the-log-entries)
    
2. Sviluppare una visualizzazione di gestione sale di Microsoft Teams in Log Analytics. È possibile creare [un dashboard Sale di Microsoft Teams usando il metodo di importazione](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) oppure creare manualmente un dashboard Sale di Microsoft [Teams.](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually)
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a>Requisiti della console di Microsoft Teams Room per singoli utenti

Ogni console di Microsoft Teams Rooms è un'app in esecuzione su un dispositivo Surface Pro in modalità chiosco multimediale (normalmente è configurata come l'unica app che può essere eseguita sul dispositivo). Come con qualsiasi app di Windows, l'app Sale di Microsoft Teams scrive eventi come errori di avvio e hardware nel registro eventi di Windows. L'aggiunta di un agente di Microsoft Monitor nel dispositivo Sale di Microsoft Teams consente la raccolta di questi eventi. Per informazioni [dettagliate, vedere Connettere computer Windows](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows) al servizio Analisi log di Azure.
  
## <a name="ongoing-management"></a>Gestione continua

Durante l'uso di Azure Monitor per gestire i dispositivi delle sale di Microsoft Teams, è necessario comprendere le informazioni contenute nei log eventi usati da Azure Monitor. Per [informazioni dettagliate su questi messaggi di integrità,](azure-monitor-manage.md#understand-the-log-entries) vedere Informazioni sulle voci del log.
  
### <a name="related-tasks"></a>Attività correlate

- Comprendere gli avvisi generati dalle sale di Microsoft Teams e come risolverli (vedere la sezione intitolato [Comprendere le voci del log)](azure-monitor-manage.md#understand-the-log-entries)
    
## <a name="see-also"></a>Vedere anche

[Distribuire la gestione delle sale di Microsoft Teams con Azure Monitor](azure-monitor-deploy.md)
  
[Gestire i dispositivi delle sale di Microsoft Teams con Azure Monitor](azure-monitor-manage.md)