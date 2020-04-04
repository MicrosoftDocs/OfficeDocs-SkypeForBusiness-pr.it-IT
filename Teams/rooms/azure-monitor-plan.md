---
title: Pianificare la gestione di Microsoft teams Rooms con Azure monitor
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
description: In questo articolo vengono illustrate le considerazioni sulla pianificazione per l'uso di Azure monitor per amministrare i dispositivi Microsoft teams rooms nell'implementazione di Skype for business o teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 16a962d7414407cf5f2f5734b7a2f39a56f7d281
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137606"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a>Pianificare la gestione di Microsoft teams Rooms con Azure monitor
 
 In questo articolo vengono illustrate le considerazioni sulla pianificazione per l'uso di Azure monitor per amministrare i dispositivi Microsoft teams rooms nell'implementazione di Microsoft teams o Skype for business.
  
[Azure monitor](https://docs.microsoft.com/azure/azure-monitor/overview) è una raccolta di servizi di gestione progettati nel cloud dall'inizio. Invece di distribuire e gestire risorse locali, i componenti di Azure monitor sono interamente ospitati in Azure. La configurazione è minima e può essere installato e funzionante letteralmente in pochi minuti. Con un certo lavoro di personalizzazione, può aiutare nella gestione dei sistemi di conferenza di Microsoft teams Rooms fornendo le notifiche in tempo reale dell'integrità del sistema o degli errori per i singoli sistemi in camera e può potenzialmente scalare fino a gestire migliaia di sale riunioni di Microsoft teams.
  
In questo articolo vengono illustrate le procedure consigliate per la gestione dei dispositivi di conferenza di Microsoft teams e i relativi requisiti di progettazione/architettura e implementazione, nonché i collegamenti a articoli dettagliati per l'implementazione di Azure monitor per Microsoft teams Rooms e informazioni di riferimento critiche per il monitoraggio continuo delle sale di Microsoft teams. 
  
## <a name="functional-overview"></a>Panoramica funzionale

![diagramma della gestione delle sale di Microsoft teams con Azure monitor](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
L'app Microsoft teams Rooms nel dispositivo console scrive eventi nel relativo log eventi di Windows. Un agente di monitoraggio Microsoft, una volta installato, passa le informazioni al servizio di Azure monitor. 
  
Una volta configurata correttamente, analisi log analizza il payload JSON incorporato nelle descrizioni degli eventi per descrivere il funzionamento di ogni sistema di Microsoft teams Rooms e quali errori vengono rilevati. 
  
Un amministratore che usa Azure monitor può ricevere le notifiche dei sistemi Microsoft teams Rooms offline o che si verificano errori di app, connettività o hardware, oltre a sapere se è necessario riavviare un sistema. Ogni stato del sistema viene aggiornato di frequente, quindi le notifiche sono vicine agli aggiornamenti in tempo reale.
  
## <a name="azure-monitor-requirements"></a>Requisiti di Azure monitor

Per usare la caratteristica analisi log è necessario disporre di un abbonamento Azure valido per monitor Azure. Vedere [Introduzione a un'area di lavoro analisi log](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) per creare un abbonamento per l'organizzazione.
  
È consigliabile familiarizzarsi come necessario per usare la finestra di progettazione della visualizzazione analisi log. Per i dettagli, vedere [visualizzazioni in analisi log](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer) .
  
### <a name="related-tasks"></a>Attività correlate

1. Dopo aver sottoscritto l'analisi log di Azure monitor, creare campi personalizzati (come descritto in [Mappa campi personalizzati](azure-monitor-deploy.md#Custom_fields)) necessari per analizzare le informazioni che verranno inviate dalle console di Microsoft teams rooms. Ciò include la comprensione dello schema JSON documentato in informazioni [sulle voci di log](azure-monitor-manage.md#understand-the-log-entries).
    
2. Sviluppare una visualizzazione di gestione delle sale di Microsoft teams in analisi log. È possibile [creare un dashboard di Microsoft teams Rooms usando il metodo Import](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) o [creare manualmente un dashboard di Microsoft teams Rooms](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually).
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a>Requisiti della console Microsoft teams Rooms individuali

Ogni console Microsoft teams Rooms è un'app in esecuzione su un dispositivo Surface Pro in modalità Kiosk (in genere è configurata per essere l'unica app che può essere eseguita nel dispositivo). Come per qualsiasi app di Windows, l'app Microsoft teams Rooms scrive eventi come errori di avvio e hardware nel registro eventi di Windows. L'aggiunta di un agente di monitoraggio Microsoft nel dispositivo Microsoft teams Rooms consente di raccogliere questi eventi. Per informazioni dettagliate, vedere [connettere i computer Windows al servizio analisi log in Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows) .
  
## <a name="ongoing-management"></a>Gestione continua

Durante l'uso di Azure monitor per gestire i dispositivi Microsoft teams rooms, è necessario conoscere le informazioni contenute nei registri eventi usati da Azure monitor. Per informazioni dettagliate su questi messaggi di integrità, vedere [comprendere le voci del log](azure-monitor-manage.md#understand-the-log-entries) .
  
### <a name="related-tasks"></a>Attività correlate

- Informazioni sugli avvisi generati dalle sale di Microsoft teams e su come risolverli (vedere la sezione [informazioni sulle voci del log](azure-monitor-manage.md#understand-the-log-entries))
    
## <a name="see-also"></a>Vedere anche

[Distribuire Gestione di Microsoft teams Rooms con Azure monitor](azure-monitor-deploy.md)
  
[Gestire i dispositivi Microsoft teams Rooms con Azure monitor](azure-monitor-manage.md)