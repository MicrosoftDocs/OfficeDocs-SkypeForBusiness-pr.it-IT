---
title: Gestire i dispositivi delle sale di Microsoft Teams con Azure Monitor
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
ms.assetid: f8109905-3279-475f-a64b-31d37af48bfe
ms.collection:
- M365-collaboration
description: Questo articolo illustra come gestire i dispositivi di Microsoft Teams Room in modo integrato con Azure Monitor.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 16105e77c8e66afa00f089d1337984b7e7d9a502
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662051"
---
# <a name="manage-microsoft-teams-rooms-devices-with-azure-monitor"></a>Gestire i dispositivi delle sale di Microsoft Teams con Azure Monitor

Questo articolo illustra come gestire i dispositivi di Microsoft Teams Room in modo integrato con Azure Monitor.

È possibile configurare Azure Monitor in modo da fornire telemetria di base per gestire i dispositivi delle sale riunioni Skype. Per [informazioni dettagliate, vedere](azure-monitor-plan.md) Pianificare la gestione delle sale di Microsoft Teams con Il monitoraggio di Azure e distribuire la gestione delle sale di Microsoft Teams con Azure [Monitor.](azure-monitor-deploy.md) Quando la soluzione di gestione è stata creata, è possibile usare altre funzionalità di gestione e dati per creare una visualizzazione più dettagliata delle prestazioni dei dispositivi.

## <a name="understand-the-log-entries"></a>Informazioni sulla voce di log

Le descrizioni degli eventi seguenti vengono inserite nel campo di descrizione del registro eventi ogni cinque minuti, quando l'app Sale di Microsoft Teams registra le informazioni corrispondenti nel registro eventi di Windows. L'agente di monitoraggio di Microsoft passa questi record a Log Analytics in Azure Monitor, che li analizza nel dashboard creato nella gestione delle sale di [Microsoft Teams con Azure Monitor.](azure-monitor-deploy.md) Con il dashboard, è possibile esaminare le singole voci del log per determinare i corsi di azione, se necessario.

Gli ID evento 2000 e 3000 indicano che il dispositivo in questione funziona come previsto. Gli ID evento 2001 e 3001 indicano che è stato rilevato un problema. L'ID evento 4000 può richiedere l'intervento del 4000 se visualizzato più spesso del previsto, rispetto a una linea di base impostata o ad altri dispositivi distribuiti nell'organizzazione.

La comprensione di queste descrizioni degli eventi consente di risolvere rapidamente i problemi e costituisce un punto di partenza per ulteriori operazioni di risoluzione dei problemi.

| Livello &nbsp; ID &nbsp; evento|Comportamento &nbsp; dell'evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Descrizione &nbsp; evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> Informazioni | Si tratta di un evento heartbeat integro. Ogni 5 minuti, Microsoft Teams Room verifica che sia connesso a Microsoft Teams o Skype for Business e che sia disponibile connettività di rete ed Exchange. <br> Se tutti e 3 i fattori sono veri, scrive l'ID evento 2000 nel registro eventi ogni 5 minuti finché il dispositivo non è offline o una o più condizioni non vengono più soddisfatte. | {"Description":"Heartbeat is healthy.", "ResourceState":"Healthy", "OperationName":"Heartbeat", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias <span></span> @contoso.com", "DisplayName":"Nome visualizzato", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"IP v6 address"} <br><br> In questo esempio, tutte le condizioni del heartbeat sono state soddisfatte e il dispositivo Microsoft Teams Rooms è stato contrassegnato come integro. In caso di errori, l'app registrerebbe invece l'ID evento 2001. |
| 2001  <br> Errore | Si tratta di un evento di errore dell'app. Ogni 5 minuti, Microsoft Teams Room verifica che sia connesso a Microsoft Teams o Skype for Business con connettività di rete ed Exchange. Se uno o più fattori non sono veri, scrive EventID 2001 nel log eventi ogni 5 minuti finché il dispositivo non è offline o non vengono soddisfatte di nuovo tutte le condizioni.  | {"Descrizione":"Stato rete: integro. Stato di Exchange: Connesso. **Stato accesso: non integro.** ", "ResourceState":"Non integro", "OperationName":"Heartbeat", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"} <br><br>  In questo esempio, Sale di Microsoft Teams ha determinato che la connessione di rete era integra e l'app era connessa a Exchange, ma la parte in grassetto indica che l'app non è connessa. Potrebbe trattarsi di un problema di configurazione nel dispositivo o nell'host.  <br> <br> Lo stato rete viene visualizzato come Integro o Non integro. Se lo stato non è integro, è possibile che si sia verificato un problema di rete o che il dispositivo sia stato scollegato (ma in questo caso verrebbero visualizzati anche errori di Exchange e Microsoft Teams o Skype for Business).  <br><br> Lo stato di Exchange viene visualizzato come Connesso o come uno dei seguenti: Disconnesso, Connessione in corso, AutodiscoveryError (l'errore più comune), GeneralError o ServerVersionNotSupported. Se lo stato è Connessione, attendere l'invio del successivo messaggio di integrità. Per altri errori, il problema riguarda un amministratore con esperienza nella risoluzione dei problemi di Exchange.  <br><br>  Lo stato di accesso (a indicare che l'app è stata con accesso) viene visualizzato come Integro o Non integro. Se lo stato non è integro, inviare un tecnico per ulteriori analisi. |
| 3000  <br> Informazioni | Questo evento verifica che sia stato eseguito un controllo hardware e che sia stato rilevato un stato integro. Ogni 5 minuti, Microsoft Teams Room verifica che i componenti hardware configurati, ad esempio la visualizzazione anteriore, il microfono, l'altoparlante e la fotocamera, siano collegati e funzionanti. Se tutti i componenti sono integri, 3000 EventID viene scritto nel log eventi. Questo evento viene scritto ogni 5 minuti, a meno che non si sia verificato un problema con un dispositivo connesso.  <br> | {"Description":"HardwareCheckCheck Is healthy.", "ResourceState":"Healthy", "OperationName":"HardwareCheckCheck", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias <span></span> @contoso.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}  <br><br> In questo esempio sono stati passati tutti i controlli hardware. In caso di errori, l'app registrerebbe invece l'ID evento 3001. |
| 3001  <br> Evento di errore  | Si tratta di un evento di errore hardware. L'app Sale di Microsoft Teams ha un processo che verifica l'integrità dei componenti hardware connessi (davanti alla sala, al microfono, all'altoparlante, alla fotocamera) ogni 5 minuti. Se uno o più componenti non sono integri, scrive EventID 3001 nel log eventi. Questo evento viene scritto ogni 5 minuti finché il problema con il dispositivo non viene risolto.   | {"Descrizione":" **Stato davanti alla visualizzazione della sala: non integro.** Il numero di visualizzazione configurato è 2. Il numero di visualizzazione reale è 0. **Stato microfono conferenza: Non integro.** Stato relatore conferenza: integro. Stato altoparlante predefinito: Integro. Stato videocamera: integro.", "ResourceState":"Non integro", "NomeOscome":"HardwareCheckCheck", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.1198", "Alias":"alias <span></span> @contoso.com", "DisplayName":"Sala riunioni Yosemite", "AppVersion":"2.0.58.0", "IPv4Address":"10.10.10.10", "IPv6Address":"IPv6Address", "IPv4Address2":"10.10.10.10"} <br><br>  Le periferiche hardware vengono visualizzate come integre o non integre. <br> In questo esempio sono configurati due schermi davanti alla chat room e nessuno dei due è attualmente disponibile. Lo stato del microfono della conferenza non è integro, il che potrebbe causare diverse cause. Poiché almeno una risorsa non ha superato il controllo, ResourceState è elencato come Non integro. Inviare un tecnico per ulteriori indagini. |
| 4000  <br> Informazioni  <br> | Si tratta di un evento di riavvio dell'app. Ogni volta che viene riavviata, l'app registra questo evento nel registro eventi di Windows.  <br> | {"Description":"App restarts.", "ResourceState":"Healthy", "OperationName":"Restart", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias <span></span> @domain.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"} <br><br> L'app può essere riavviata per vari motivi. Confronta la frequenza di riavvio dei dispositivi nello stesso edificio e in edifici diversi. Tenere presente i problemi noti, come le fluttuazioni di potenza e i guasti, che possono fornire indicazioni sui problemi dell'infrastruttura.|

## <a name="related-topics"></a>Argomenti correlati
 

[Pianificare la gestione delle sale di Microsoft Teams con Azure Monitor](azure-monitor-plan.md)

[Distribuire la gestione delle sale di Microsoft Teams con Azure Monitor](azure-monitor-deploy.md)
