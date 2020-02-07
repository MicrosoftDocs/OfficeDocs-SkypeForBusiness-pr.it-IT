---
title: Panoramica della gestione per le sale di Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection:
- M365-collaboration
description: Panoramica della gestione per le sale di Microsoft teams.
ms.openlocfilehash: 3a56a03342ca0edb0da9dc9ed3a4cada77816bc7
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825884"
---
# <a name="management-overview"></a>Panoramica della gestione

È essenziale sviluppare ed eseguire la manutenzione e le operazioni in corso per garantire che i sistemi Microsoft teams Rooms siano disponibili per gli utenti e per offrire un'esperienza utente ottimale. 

## <a name="monitoring"></a>Monitoraggio 

Il monitoraggio dei sistemi Microsoft teams Rooms è costituito da due attività principali:

- Monitoraggio di dispositivi, applicazioni e periferiche
- Monitoraggio qualità e affidabilità (Call Quality Dashboard)

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a>Monitoraggio di dispositivi, applicazioni e periferiche Microsoft teams rooms

Per fare in modo che gli utenti siano in grado di usare le unità di Microsoft teams rooms, le unità devono essere accese, connesse alla rete con l'applicazione Microsoft teams Rooms correttamente configurata e connessa ai dispositivi periferici funzionanti. 

Le informazioni sullo stato dell'applicazione Microsoft teams Rooms e delle periferiche connesse vengono scritte dall'applicazione Microsoft teams Rooms nel registro eventi di Windows e documentate in [comprendere le voci del log](azure-monitor-manage.md#understand-the-log-entries). 

|**Impostazione**|**Permette**|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (DWORD) 1  <br/> |Consente l'avvio delle sale di Microsoft Teams  <br/> |
|Power Management-\> in AC, disattivare lo schermo dopo 10 minuti  <br/> Power Management-\> su AC, non posizionare mai il sistema in modalità Sleep  <br/> |Consente alle sale di Microsoft teams di disattivare i display allegati e di riattivarsi automaticamente  <br/> |
|NET account/maxpwage: illimitato  <br/> O un mezzo equivalente per disabilitare la scadenza della password per l'account locale. La mancata esecuzione di questa operazione causerà l'errore di accesso dell'account Skype che lamenta una password scaduta. Tieni presente che questo ha un impatto su tutti gli account locali nel computer e quindi la mancata impostazione di questa operazione causerà anche l'eventuale scadenza dell'account amministrativo nella casella.  <br/> |Consente all'account Skype di accedere sempre  <br/> |

Il trasferimento di file tramite criteri di gruppo è illustrato in [configurare un elemento del file](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).
  
## <a name="remote-management-using-powershell"></a>Gestione remota tramite PowerShell
<a name="RemotePS"> </a>

È consigliabile usare Microsoft Operations Manager Suite per monitorare i sistemi Microsoft teams rooms. Per informazioni su come configurare il monitoraggio e gli avvisi di base, vedere [distribuire Gestione di Microsoft teams Rooms con Azure monitor](azure-monitor-deploy.md). 

Usando queste linee guida, puoi creare un dashboard semplice da usare per identificare eventuali problemi con le unità delle sale di Microsoft teams in tutta la distribuzione. 

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/>Punti decisionali|<ul><li>Verificare che sia possibile usare Operations Management Suite per monitorare la distribuzione di Microsoft teams rooms.</li><li>Decidi la lista di distribuzione di destinazione che userai per gli avvisi tramite posta elettronica.</li></ul>|
|![](../media/audio_conferencing_image9.png)<br/>Passaggi successivi|<ul><li>Definire l'approccio di monitoraggio qualità e affidabilità.</li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a>Monitoraggio qualità e affidabilità (Call Quality Dashboard)

Ti consigliamo di implementare procedure di monitoraggio della qualità e affidabilità operative in corso come parte della tua distribuzione per monitorare l'andamento della qualità e dell'affidabilità delle chiamate e delle riunioni, identificando le aree di interesse e lavorando verso una risoluzione. 

Quando si caricano le informazioni sull'edificio in Call Quality dashboard, è possibile esaminare le tendenze per la qualità delle chiamate e l'affidabilità in base a un livello per edificio, che consente di confrontare facilmente gli edifici e di attirare l'attenzione su problemi specifici.

Ti consigliamo di rivedere e seguire la [Guida alla revisione della qualità dell'esperienza](https://aka.ms/qerguide) per identificare le tendenze di qualità e affidabilità e creare un piano di azione per risolverli. 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a>Aggiornamento del sistema operativo Microsoft teams Rooms e dell'applicazione Microsoft teams rooms

È consigliabile aggiornare l'applicazione Microsoft teams Rooms OS e Microsoft teams Rooms per trarre vantaggio da aggiornamenti e miglioramenti del prodotto. Per informazioni dettagliate, vedere [gestire le sale di Microsoft teams](rooms-operations.md#software-updates). 

## <a name="windows-updates"></a>Aggiornamenti di Windows

Microsoft teams Rooms viene eseguito in Windows 10 Enterprise o Windows 10 Enterprise (contratto multilicenza) e riceve gli stessi aggiornamenti di Windows e le build del sistema operativo come desktop standard. Per informazioni dettagliate, vedere [gestire gli aggiornamenti di Windows](updates.md) .


## <a name="troubleshooting"></a>Risoluzione dei problemi

È consigliabile configurare l'avviso di Operations Management Suite come descritto nella sezione precedente, in modo che il team operativo e l'helpdesk vengano avvisati in caso di problemi con le sale di Microsoft teams. Le opzioni disponibili per la gestione remota di PowerShell sono descritte in [gestione remota tramite PowerShell](rooms-operations.md#remote-management-using-powershell). Nel caso in cui un dispositivo periferico sia disconnesso, potrebbe essere necessario affidarsi a "Smart Hand" locali o supporto IT per analizzare e riconnettere i dispositivi. 

Per altre informazioni sulla risoluzione dei problemi e sulla modalità amministratore, vedere [modalità amministratore e gestione dispositivi](rooms-operations.md#admin-mode-and-device-management). 


## <a name="see-also"></a>Vedere anche

[Guida di Microsoft teams rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Pianificare le sale di Microsoft Teams](rooms-plan.md)

[Distribuire le sale di Microsoft Teams](rooms-deploy.md)

[Configurare una console Microsoft teams rooms](console.md)

[Gestire le impostazioni della console Microsoft teams rooms in remoto con un file di configurazione XML](xml-config-file.md)
