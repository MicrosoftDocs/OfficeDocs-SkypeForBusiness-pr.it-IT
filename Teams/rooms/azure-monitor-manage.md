---
title: Monitorare Microsoft Teams Rooms dispositivi con Monitoraggio di Azure
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f8109905-3279-475f-a64b-31d37af48bfe
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: Questo articolo illustra come monitorare Microsoft Teams Rooms dispositivi in modo integrato usando Monitor di Azure.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2f0878e7553e2d151f781c3f522a9b533b4b56d8
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268971"
---
# <a name="monitor-microsoft-teams-rooms-devices-with-azure-monitor"></a>Monitorare Microsoft Teams Rooms dispositivi con Monitoraggio di Azure

Questo articolo illustra come monitorare Microsoft Teams Rooms in modo integrato usando Monitor di Azure.

È possibile configurare Monitoraggio di Azure per fornire la telemetria di base per monitorare i dispositivi delle sale riunioni di Microsoft Teams. Per informazioni dettagliate, vedere [Pianificare Microsoft Teams Rooms gestione con Monitoraggio di Azure](azure-monitor-plan.md) e [Distribuire la gestione Microsoft Teams Rooms con Monitor di Azure](azure-monitor-deploy.md). Quando la soluzione di monitoraggio matura, è possibile usare altri dati e funzionalità di monitoraggio per creare una visualizzazione più dettagliata delle prestazioni del dispositivo.

## <a name="understand-the-log-entries"></a>Informazioni sulle voci del log

Le descrizioni degli eventi seguenti vengono inserite nel campo della descrizione del registro eventi ogni cinque minuti, quando l'app Microsoft Teams Rooms registra le informazioni corrispondenti nel registro eventi di Windows. L'Agente di monitoraggio Microsoft passa questi record a Log Analytics in Azure Monitor, che li analizza nel dashboard creato in [Distribuisci monitoraggio Microsoft Teams Rooms con Monitoraggio di Azure](azure-monitor-deploy.md). Con il dashboard, è possibile esaminare le singole voci del log per determinare i corsi d'azione, se necessario.

Gli ID evento 2000 e 3000 indicano che Teams Rooms funziona come previsto. Gli ID evento 2001 e 3001 indicano che è stato trovato un problema. L'ID evento 4000 può richiedere un'azione se visualizzato più spesso del previsto, rispetto a una previsione impostata o ad altri dispositivi distribuiti nell'organizzazione.

La comprensione di queste descrizioni degli eventi consente di segnalare rapidamente i problemi e fornisce un punto di partenza per ulteriori soluzioni.

| Livello ID&nbsp;evento&nbsp;|Comportamento dell'evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Descrizione evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> Informazioni | Questo è un evento sano del battito cardiaco. Ogni 5 minuti, Microsoft Teams Rooms verifica che sia connesso a Microsoft Teams o Skype for Business e disponga di connettività di rete ed Exchange. <br> Se tutti e tre i fattori sono veri, scrive l'ID evento 2000 nel registro eventi ogni 5 minuti finché il dispositivo non è offline o una o più condizioni non vengono più soddisfatte. | `{"Description":"Heartbeat is healthy.", "ResourceState":"Healthy", "OperationName":"Heartbeat", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com",  "DisplayName":"Display name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10",  "IPv6Address":"IP v6 address"}` <br><br> In questo esempio sono state soddisfatte tutte le condizioni del battito cardiaco e il dispositivo Microsoft Teams Rooms è stato contrassegnato come integro. In caso di errori, l'app registra invece l'ID evento 2001. |
| 2001  <br> Errore | Si tratta di un evento di errore dell'app. Ogni 5 minuti, Microsoft Teams Rooms verifica di aver eseguito l'accesso a Microsoft Teams o Skype for Business con connettività di rete ed Exchange. Se uno o più fattori non sono veri, scrive EventID 2001 nel registro eventi ogni 5 minuti finché il dispositivo non è offline o tutte le condizioni non vengono soddisfatte di nuovo.  | `{"Description":"Network status : Healthy. Exchange status : Connected. Sign in status: Unhealthy. Teams sign in status: Healthy.", "ResourceState":"Unhealthy", "OperationName":"Heartbeat", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br>  In questo esempio Microsoft Teams Rooms determinato che la connessione di rete era integro e che l'app era connessa a Exchange, ma la parte in grassetto indica che l'app non è connessa. Potrebbe trattarsi di un problema di configurazione nel dispositivo o nell'host.  <br> <br> Lo stato Rete è Integro o Non integro. Se lo stato non è integro, è possibile che si sia verificato un problema di rete o che il dispositivo sia stato scollegato (ma in questo caso si potrebbero verificare anche errori di Exchange e Microsoft Teams o di Skype for Business).  <br><br> Lo stato di Exchange viene visualizzato come Connesso o come uno dei seguenti: Disconnesso, Connessione, AutodiscoveryError (l'errore più comune), GeneralError o ServerVersionNotSupported. Se lo stato è Connessione, attendere l'invio del messaggio di integrità successivo. Per altri errori, indirizzare il problema a un amministratore esperto nella risoluzione dei problemi di Exchange.  <br><br>  Lo _stato_/ di accesso di _Teams di accesso_ (che indica che l'app ha eseguito l'accesso a Skype for Business o Teams) viene visualizzato come _Integro_ o _Non integro_. Se lo stato non è integro, invia un tecnico per ulteriori indagini. |
| 3000  <br> Informazioni | Questo evento verifica che sia stato eseguito un controllo hardware e che non sia stato rilevato un problema. Ogni 5 minuti Microsoft Teams Rooms verifica che i componenti hardware configurati, ad esempio la parte anteriore dello schermo della sala, il microfono, l'altoparlante e la fotocamera, siano collegati e funzionanti. Se tutti i componenti sono integri, scrive EventID 3000 nel registro eventi. Questo evento viene scritto ogni 5 minuti, a meno che non si sia verificato un problema con un dispositivo connesso.  <br> | `{"Description":"HardwareCheckEngine is healthy.",  "ResourceState":"Healthy", "OperationName":"HardwareCheckEngine",  "OperationResult":"Pass", "OS":"Windows 10",  "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0",  "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> In questo esempio sono stati passati tutti i controlli hardware. Se si verificassero errori, l'app registrava invece l'ID evento 3001. |
| 3001  <br> Evento errore  | Si tratta di un evento di errore hardware. L'app Microsoft Teams Rooms prevede un processo che controlla l'integrità dei componenti hardware connessi (davanti alla sala, microfono, altoparlante, fotocamera) ogni 5 minuti. Se uno o più componenti non sono integri, scrive EventID 3001 nel registro eventi. Questo evento viene scritto ogni 5 minuti fino a quando il problema con il dispositivo non viene risolto.   | `{"Description":" Front of Room Display status : Unhealthy. Configured display count is 2. Real display count is 0. Conference Microphone status : Unhealthy. Conference Speaker status : Healthy. Default Speaker status : Healthy. Camera status : Healthy.", "ResourceState":"Unhealthy", "OperationName":"HardwareCheckEngine", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.1198", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Yosemite conference room", "AppVersion":"2.0.58.0", "IPv4Address":"10.10.10.10", "IPv6Address":"IPv6Address", "IPv4Address2":"10.10.10.10"}` <br><br>  Le periferiche hardware vengono visualizzate come sane o non integro. <br> In questo esempio sono configurati due _schermi della sala_ e attualmente nessuno dei due è disponibile. Lo _stato del microfono conferenza_ non è _integro_, il che potrebbe avere diverse cause possibili. Poiché almeno una risorsa non ha superato il controllo, lo Stato Risorse è elencato come Non integro. Invia un tecnico per ulteriori indagini. |
| 4000  <br> Informazioni  <br> | Si tratta di un evento di riavvio dell'app. Ogni volta che l'app viene riavviata, l'evento viene registrato nel registro eventi di Windows.  <br> | `{"Description":"App restarts.", "ResourceState":"Healthy", "OperationName":"Restart", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@domain.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> L'app potrebbe essere riavviato per vari motivi. Confronta la frequenza di riavvio dei dispositivi nello stesso edificio e in edifici diversi. Tieni presente i problemi noti, come fluttuazioni di alimentazione e guasti, in quanto ciò può fornire indicazioni per i problemi dell'infrastruttura.|

## <a name="related-topics"></a>Argomenti correlati
 

[Pianificare il monitoraggio Microsoft Teams Rooms con Monitoraggio di Azure](azure-monitor-plan.md)

[Distribuire il monitoraggio Microsoft Teams Rooms con Monitoraggio di Azure](azure-monitor-deploy.md)
